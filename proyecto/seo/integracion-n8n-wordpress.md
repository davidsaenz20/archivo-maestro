INTEGRACIÓN N8N → WORDPRESS

Versión: 1.1
Estado: Diseño técnico
Proyecto: Plataforma de landings locales automatizadas

---

1. OBJETIVO

Definir la comunicación entre el sistema de generación/validación y WordPress.

N8N actúa como orquestador.

WordPress actúa como sistema de almacenamiento y renderizado.

N8N no debe delegar en WordPress decisiones estratégicas de SEO, arquitectura, bloques o contenido.

Flujo:

ARQUITECTURA
↓
CONTEXTO
↓
IA
↓
JSON
↓
VALIDADOR
↓
TRANSFORMADOR
↓
WORDPRESS
↓
VERIFICACIÓN

---

2. CONTRATO DE ENTRADA

N8N recibe una salida compatible con:

contrato-salida-ia.md

Versión soportada:

schema_version: "1.1"

La salida debe contener un objeto "landing".

No se procesa una salida que no cumpla el contrato.

---

3. IDENTIFICADOR

La unidad de publicación se identifica mediante:

landing_id

Ejemplo:

LANDING-fontanero-marbella

"landing_id" debe ser estable.

No debe depender del ID interno de WordPress.

---

4. IDEMPOTENCIA

Antes de crear una landing:

buscar landing_id

Si no existe:

CREATE

Si existe:

UPDATE

Nunca se deben crear duplicados por ejecutar dos veces el mismo workflow.

---

5. WORKFLOW

El workflow conceptual será:

01 TRIGGER
      ↓
02 CARGAR CONTEXTO
      ↓
03 GENERAR IA
      ↓
04 PARSEAR JSON
      ↓
05 VALIDAR
      ↓
06 ¿VALID?
    ↙       ↘
   NO        SÍ
   ↓         ↓
 ERROR    TRANSFORMAR
             ↓
       BUSCAR LANDING
             ↓
        CREATE / UPDATE
             ↓
       VERIFICAR RESULTADO
             ↓
           LOG

---

6. NODOS

Nodo 01 — Trigger

Inicia el proceso.

Puede ser:

- manual;
- webhook;
- ejecución programada;
- entrada desde otro workflow.

---

Nodo 02 — Contexto

Carga los datos necesarios para generar la landing:

identidad
servicio
localidad
arquitectura
bloques autorizados
datos disponibles
restricciones

La IA no debe recibir información innecesaria.

---

Nodo 03 — IA

Genera exclusivamente la estructura definida por:

contrato-salida-ia.md

No genera HTML libre.

No decide qué bloques existen.

No puede crear bloques fuera del catálogo.

---

Nodo 04 — Parse JSON

Convierte la respuesta de IA en objeto estructurado.

Si el JSON es inválido:

ERROR
→ no continuar

---

Nodo 05 — Validador

Ejecuta las reglas de:

validador.md

Entrada:

JSON IA

Salida:

valid
errors
warnings
metadata

Si:

valid = false

se detiene el flujo de publicación.

---

Nodo 06 — IF VALID

Condición:

valid == true

Rama TRUE:

TRANSFORMAR

Rama FALSE:

ERROR HANDLER

---

7. ERROR HANDLER

Cuando la validación falla:

guardar landing_id
guardar errores
guardar warnings
guardar timestamp
guardar versión

No publicar.

No actualizar WordPress.

El error debe ser trazable.

---

8. TRANSFORMADOR

El transformador convierte la salida validada al modelo esperado por WordPress.

Conceptualmente:

IA JSON
↓
MODELO COMÚN
↓
MODELO WORDPRESS

El transformador no debe modificar contenido semántico.

Solo adapta estructura.

---

9. DATOS WORDPRESS

La proyección debe respetar:

modelo-datos-wordpress.md

Datos principales:

landing_id
identidad
slug
SEO
bloques
interlinking
images
schema
estado

---

10. BLOQUES

El sistema utiliza exclusivamente el catálogo oficial:

B01
B02
B03
B04
B05
B06
B07
B08
B09
B10
B11
B12
B13
B14
B15
B16
B17
B18
B19
B20
B21
B22
B23

La definición funcional de cada bloque pertenece a:

sistema-bloques.md

N8N no crea bloques nuevos.

---

11. CREATE

Si "landing_id" no existe:

POST /wp-json/...

La implementación definitiva del endpoint dependerá de la API WordPress elegida.

Estado inicial:

draft

La primera fase de producción no debe publicar automáticamente.

---

12. UPDATE

Si "landing_id" existe:

UPDATE

El contenido existente debe sustituirse únicamente después de que la nueva versión haya pasado el validador.

No actualizar parcialmente una landing con datos inválidos.

---

13. WORDPRESS

WordPress debe recibir datos estructurados.

No debe recibir una página HTML completa generada arbitrariamente por IA.

Conceptualmente:

{
  "landing_id": "LANDING-fontanero-marbella",
  "status": "draft",
  "slug": "fontanero-marbella",
  "seo": {},
  "blocks": [],
  "internal_links": [],
  "images": [],
  "schema": null
}

---

14. API

La comunicación utilizará HTTPS.

La autenticación deberá realizarse mediante credenciales almacenadas de forma segura en N8N.

Nunca incluir:

- contraseñas;
- tokens;
- claves API;

dentro del contenido generado por IA.

---

15. SEGURIDAD

Las credenciales deben mantenerse fuera del JSON de contenido.

N8N utilizará su sistema de credenciales.

WordPress deberá aceptar únicamente solicitudes autenticadas para creación/actualización.

---

16. VERIFICACIÓN POSTERIOR

Después de crear o actualizar:

consultar WordPress

Comprobar:

landing_id
slug
estado
bloques
SEO

Si la respuesta no coincide:

ERROR

---

17. LOG

Cada ejecución deberá registrar:

landing_id
timestamp
schema_version
validator_version
operation
wordpress_id
status
result
errors
warnings

No almacenar innecesariamente información sensible.

---

18. RETRIES

Los errores temporales de red pueden reintentarse.

Los errores de validación NO deben reintentarse automáticamente sin cambiar la entrada.

Separación:

ERROR DE RED
→ retry

ERROR DE CONTRATO
→ stop

ERROR DE VALIDACIÓN
→ stop

ERROR WORDPRESS 4xx
→ stop/revisión

ERROR WORDPRESS 5xx
→ retry controlado

---

19. IDEMPOTENCIA Y REINTENTOS

Una ejecución repetida con el mismo:

landing_id
version
contenido

no debe generar una segunda landing.

El workflow debe poder ejecutarse de nuevo de forma segura.

---

20. ESTADO DEL WORKFLOW

Estados conceptuales:

RECEIVED
GENERATING
VALIDATING
VALIDATED
TRANSFORMING
CREATING
UPDATING
VERIFYING
COMPLETED
FAILED

---

21. REGLA DE PUBLICACIÓN

Durante la fase inicial:

IA
↓
VALIDADOR
↓
N8N
↓
WORDPRESS
↓
DRAFT

No se habilitará publicación automática hasta comprobar:

- validador;
- renderizado;
- SEO;
- URLs;
- interlinking;
- schema;
- idempotencia.

---

22. SEPARACIÓN DE RESPONSABILIDADES

IA

Genera contenido estructurado.

Validador

Determina si cumple las reglas.

N8N

Orquesta.

Transformador

Adapta estructura.

WordPress

Almacena y renderiza.

Plantilla

Presenta los datos.

Ningún componente debe asumir responsabilidades de otro.

---

23. FUENTES DE VERDAD

modelo-datos.md
sistema-bloques.md
contrato-salida-ia.md
validador.md
arquitectura-wordpress.md
modelo-datos-wordpress.md

Este documento define exclusivamente la integración.

---

24. VERSIONADO

Actualmente:

integración: 1.1
contrato IA: 1.1

Cualquier cambio de contrato debe revisarse contra:

validador
transformador
N8N
WordPress

---

25. SIGUIENTE PASO

Una vez guardada esta versión, se deja de ampliar la documentación.

El siguiente trabajo será construir:

N8N WORKFLOW V1

con los nodos definidos anteriormente.

Después:

VALIDADOR V1
↓
WORDPRESS API
↓
PLANTILLA
↓
PRIMERA LANDING
