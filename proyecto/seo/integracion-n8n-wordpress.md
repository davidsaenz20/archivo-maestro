

INTEGRACIÓN N8N → WORDPRESS

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Proyecto: Plataforma de landings locales automatizadas

---

1. OBJETIVO

Definir la comunicación entre:

ARQUITECTURA → IA → VALIDACIÓN → N8N → WORDPRESS → PLANTILLAS → PÁGINA

N8N actúa como orquestador.

WordPress actúa como sistema de almacenamiento y renderizado.

La IA no controla directamente el diseño visual.

---

2. CONTRATO DE ENTRADA

N8N recibe exclusivamente una salida compatible con:

"contrato-salida-ia.md"

Versión actual del contrato IA:

"4.0"

La salida debe contener un "SITE_PACKAGE" válido.

N8N no debe procesar una salida que no cumpla el contrato.

---

3. IDENTIFICACIÓN

La identidad lógica de una página será:

site_id
opportunity_id
page_id
url

"page_id" debe ser estable.

No debe depender del ID interno de WordPress.

Ejemplo:

FON-EST-HOME

El ID interno de WordPress será únicamente un dato técnico de almacenamiento.

---

4. IDENTIFICACIÓN DE BLOQUES

Cada instancia de bloque tendrá:

block_id
block_instance_id
block_version
enabled

Ejemplo:

block_id:
B14

block_instance_id:
FON-EST-HOME-B14-01

"block_id" identifica el tipo de bloque.

"block_instance_id" identifica una instancia concreta dentro de una página.

---

5. IDEMPOTENCIA

Antes de crear una página:

BUSCAR page_id

Si no existe:

CREATE_PAGE

Si existe:

UPDATE_PAGE

Nunca deben generarse duplicados por ejecutar dos veces el mismo workflow.

---

6. IDEMPOTENCIA DE BLOQUES

Antes de crear una instancia:

BUSCAR page_id + block_instance_id

Si no existe:

CREATE_BLOCK

Si existe:

UPDATE_BLOCK

La ejecución repetida debe ser segura.

---

7. OPERACIONES

N8N podrá enviar:

CREATE_PAGE
UPDATE_PAGE
CREATE_BLOCK
UPDATE_BLOCK
ENABLE_BLOCK
DISABLE_BLOCK
DELETE_BLOCK
UPDATE_LINKS
UPDATE_MENU
PUBLISH
UNPUBLISH

Las operaciones deben estar validadas antes de ejecutarse.

---

8. WORKFLOW PRINCIPAL

01 TRIGGER
      ↓
02 CARGAR OPORTUNIDAD
      ↓
03 CARGAR ARQUITECTURA
      ↓
04 CARGAR CONTEXTO
      ↓
05 IA
      ↓
06 PARSEAR SITE_PACKAGE
      ↓
07 VALIDAR
      ↓
08 ¿VÁLIDO?
    ↙       ↘
   NO        SÍ
   ↓         ↓
 ERROR    TRANSFORMAR
             ↓
       BUSCAR PAGE_ID
          ↙       ↘
       NUEVA     EXISTENTE
         ↓           ↓
       CREATE      UPDATE
          \         /
           ↓       ↓
          BLOQUES
             ↓
        INTERLINKING
             ↓
            SEO
             ↓
        VERIFICACIÓN
             ↓
             LOG

---

9. NODO TRIGGER

Puede iniciarse mediante:

- ejecución manual;
- formulario;
- webhook;
- otro workflow;
- listado de oportunidades;
- ejecución programada.

Para generación masiva, N8N deberá procesar las oportunidades individualmente o en lotes controlados.

---

10. CARGA DE CONTEXTO

N8N recopilará:

site_id
opportunity_id
servicio
localidad
arquitectura
páginas existentes
bloques autorizados
relaciones autorizadas
datos disponibles
restricciones

La IA no debe recibir información innecesaria.

---

11. IA

La IA genera únicamente:

- contenido;
- datos;
- estructura;
- bloques autorizados;
- enlaces autorizados;
- metadatos definidos por contrato.

No genera HTML libre.

No genera CSS.

No crea nuevos tipos de bloque.

No puede modificar la arquitectura por iniciativa propia.

---

12. PARSEADO

N8N convierte la respuesta de IA en un objeto estructurado.

Si el JSON no es válido:

ERROR
↓
STOP

No se continúa hacia WordPress.

---

13. VALIDACIÓN

La salida se valida mediante las reglas definidas en:

"validador.md"

Debe comprobar como mínimo:

schema
page_id
URL
bloques
block_id
block_instance_id
datos obligatorios
interlinking
destinos
SEO

Resultado:

valid
errors
warnings
metadata

Si:

valid = false

no se publica ni actualiza WordPress.

---

14. TRANSFORMADOR

El transformador convierte:

SITE_PACKAGE
↓
MODELO COMÚN
↓
MODELO WORDPRESS

No debe alterar el significado del contenido.

Solo adapta la estructura necesaria para WordPress.

---

15. MODELO WORDPRESS

La proyección debe respetar:

"modelo-renderizado-wordpress.md"

La información principal será:

page_id
url
status
version
seo
blocks
links
menu
images
schema

---

16. PÁGINA

Ejemplo conceptual:

{
  "page_id": "FON-EST-HOME",
  "url": "/fontanero/estepona/",
  "version": 1,
  "status": "draft",
  "blocks": []
}

El "page_id" permanece estable aunque cambie el ID interno de WordPress.

---

17. BLOQUES

Solo pueden utilizarse:

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

La definición funcional pertenece a:

"sistema-bloques.md"

N8N no puede inventar bloques.

---

18. PLANTILLAS

WordPress tendrá plantillas visuales reutilizables.

La plantilla no se identifica por el nombre de un tema concreto.

La relación lógica será:

block_id
↓
renderer
↓
template
↓
data

Kadence puede utilizarse durante el piloto, pero no forma parte del contrato lógico.

---

19. CREACIÓN

Si "page_id" no existe:

CREATE_PAGE

Estado inicial:

draft

Después se crean las instancias de bloques necesarias.

---

20. ACTUALIZACIÓN COMPLETA

Si "page_id" existe y llega una nueva versión completa:

UPDATE_PAGE

Se actualizan los datos correspondientes.

Los identificadores existentes deben conservarse.

---

21. ACTUALIZACIÓN PARCIAL

Si solamente cambia un bloque:

{
  "operation": "UPDATE_BLOCK",
  "page_id": "FON-EST-HOME",
  "block_instance_id": "FON-EST-HOME-B14-01",
  "data": {}
}

N8N debe localizar esa instancia y actualizarla.

No debe reconstruir toda la página.

---

22. DESACTIVACIÓN

Para ocultar temporalmente un bloque:

{
  "operation": "DISABLE_BLOCK",
  "page_id": "FON-EST-HOME",
  "block_instance_id": "FON-EST-HOME-B14-01"
}

La instancia permanece identificada.

No se debe crear una nueva instancia al volver a activarla.

---

23. ELIMINACIÓN

"DELETE_BLOCK" solo debe utilizarse cuando la instancia deba eliminarse realmente.

Cuando sea suficiente ocultarla:

DISABLE_BLOCK

es preferible.

---

24. INTERLINKING

Los enlaces forman parte del modelo de datos.

Ejemplo:

{
  "source_page_id": "FON-EST-HOME",
  "source_block_instance_id": "FON-EST-HOME-B16-01",
  "target_page_id": "FON-MAN-HOME",
  "anchor": "fontanero en Manilva",
  "type": "related_location"
}

N8N no debe inventar destinos.

---

25. ACTUALIZACIÓN DE INTERLINKING

Si cambia la red de enlaces:

UPDATE_LINKS

No es necesario regenerar todo el contenido de la página.

Ejemplo:

Estepona
↓
Manilva
↓
Casares

podrá modificarse posteriormente a:

Estepona
↓
Manilva
↓
Casares
↓
San Pedro

si las páginas están autorizadas.

---

26. ENLACES ENTRE SERVICIOS

También podrán existir relaciones como:

Fontanero
↓
Electricista
↓
Pintor
↓
Carpintero

si están autorizadas por la arquitectura.

No se debe crear enlazado artificial únicamente para aumentar el número de enlaces.

---

27. DESTINOS INEXISTENTES

Si un enlace apunta a una página que todavía no existe:

REVIEW

No se publica el enlace roto.

Cuando la página destino exista, N8N podrá ejecutar:

UPDATE_LINKS

---

28. MENÚ

El menú podrá actualizarse independientemente.

Cada elemento tendrá:

label
target_page_id
url
order
enabled

N8N podrá:

CREATE
UPDATE
DELETE
REORDER

---

29. SEO

N8N transmitirá los datos SEO estructurados.

Ejemplo:

{
  "title": "",
  "meta_description": "",
  "h1": ""
}

La implementación concreta dependerá del sistema SEO instalado en WordPress.

---

30. IMÁGENES

Las imágenes deberán contener datos válidos:

url
alt
title
type

No se deben inventar URLs.

---

31. DATOS ESTRUCTURADOS

B17 contiene la información lógica.

El transformador/renderizador será responsable de convertirla al formato compatible con WordPress.

No se deben generar datos estructurados falsos.

---

32. VERIFICACIÓN

Después de CREATE o UPDATE:

CONSULTAR WORDPRESS

Comprobar:

page_id
URL
estado
versión
bloques
block_instance_id
SEO
interlinking

Si no coincide:

ERROR

---

33. VERSIONADO

Cada página tendrá:

page_version

Cada bloque:

block_version

Una actualización de bloque incrementa su versión.

Una actualización completa de página incrementa la versión de página.

---

34. REGISTRO DE CAMBIOS

N8N deberá registrar:

page_id
block_instance_id
operation
previous_version
new_version
timestamp
result
error

Esto permitirá saber qué cambió y cuándo.

---

35. LOG GENERAL

Cada ejecución deberá registrar:

site_id
opportunity_id
page_id
url
operation
block_id
block_instance_id
schema_version
validator_version
wordpress_id
status
result
errors
warnings
timestamp

No almacenar información sensible innecesaria.

---

36. ERRORES

Errores principales:

INVALID_JSON
INVALID_CONTRACT
VALIDATION_ERROR
PAGE_NOT_FOUND
BLOCK_UNKNOWN
BLOCK_INSTANCE_NOT_FOUND
TEMPLATE_NOT_FOUND
INVALID_URL
INVALID_DATA
DUPLICATE_PAGE
MISSING_REQUIRED_DATA
WORDPRESS_ERROR

---

37. RETRIES

Errores temporales:

NETWORK_ERROR
TIMEOUT
WORDPRESS_5XX

pueden reintentarse de forma controlada.

Errores de contrato o validación:

STOP

No deben reintentarse automáticamente sin modificar la entrada.

---

38. SEGURIDAD

Las credenciales de WordPress permanecerán en el sistema de credenciales de N8N.

Nunca deberán aparecer dentro de:

- prompts;
- JSON generado;
- logs;
- contenido publicado.

La comunicación deberá utilizar HTTPS.

---

39. ESTADOS

Estados conceptuales:

RECEIVED
GENERATING
PARSING
VALIDATING
VALIDATED
TRANSFORMING
CREATING
UPDATING
UPDATING_BLOCK
UPDATING_LINKS
VERIFYING
COMPLETED
FAILED

---

40. PUBLICACIÓN

Durante el piloto:

IA
↓
VALIDADOR
↓
N8N
↓
WORDPRESS
↓
DRAFT

No se habilitará publicación automática hasta validar:

- contenido;
- renderizado;
- SEO;
- enlaces;
- schema;
- idempotencia;
- actualizaciones parciales.

---

41. ESCALABILIDAD

El sistema debe poder trabajar progresivamente:

1
↓
3
↓
10
↓
50
↓
100
↓
1.000+

No se recomienda lanzar inicialmente cientos de generaciones simultáneas.

N8N deberá utilizar procesamiento por lotes y límites de concurrencia.

---

42. CREACIÓN MASIVA

La entrada puede ser:

SERVICIO
+
LISTA DE LOCALIDADES

Ejemplo:

fontanero

Estepona
Manilva
Casares
Ronda
Cártama
Fuengirola
...

N8N convierte cada combinación en una oportunidad independiente.

Ejemplo:

fontanero + Estepona
fontanero + Manilva
fontanero + Casares

Cada una obtiene su propio:

opportunity_id
page_id

---

43. CONTROL DE CONCURRENCIA

N8N debe poder limitar cuántas oportunidades procesa simultáneamente.

Esto será especialmente importante cuando se utilicen APIs de IA gratuitas o con límites.

Ejemplo conceptual:

LISTA 100 LOCALIDADES
↓
QUEUE
↓
1–3 GENERACIONES SIMULTÁNEAS
↓
VALIDACIÓN
↓
WORDPRESS

El límite será configurable.

---

44. CAMBIO DE TEMA

El contenido y los identificadores no deben depender de Kadence.

Si posteriormente se cambia el tema:

MISMA DATA
+
MISMO page_id
+
MISMOS block_id
↓
NUEVAS PLANTILLAS

Las páginas no necesitan regenerarse semánticamente.

---

45. FUENTES DE VERDAD

Este documento debe coordinarse con:

modelo-datos.md
sistema-bloques.md
contrato-salida-ia.md
validador.md
arquitectura-wordpress.md
modelo-datos-wordpress.md
modelo-renderizado-wordpress.md
interlinking.md

Cada documento debe tener una responsabilidad concreta.

---

46. REGLA DE NO DUPLICACIÓN

No se deben crear dos sistemas diferentes para resolver la misma función.

Especialmente:

page_id
block_instance_id
versionado
interlinking

deben tener una única definición oficial.

---

47. PRINCIPIO DE ACTUALIZACIÓN

La arquitectura permite dos niveles:

Actualización completa

UPDATE_PAGE

Actualización parcial

UPDATE_BLOCK
UPDATE_LINKS
UPDATE_MENU

Siempre que sea posible se utilizará la actualización parcial.

---

48. PRINCIPIO FINAL

IA
↓
genera datos estructurados.

VALIDADOR
↓
comprueba que son correctos.

N8N
↓
orquesta y sincroniza.

WORDPRESS
↓
almacena y renderiza.

PLANTILLAS
↓
definen la presentación.

TEMA
↓
aporta el sistema visual.

---

49. SIGUIENTE FASE

Una vez actualizado este documento:

1. Validar integración.
2. Definir el workflow N8N V1.
3. Definir el transformador.
4. Definir la estructura exacta de WordPress.
5. Crear las primeras plantillas.
6. Probar una landing.
7. Probar actualización completa.
8. Probar actualización de un bloque.
9. Probar actualización de interlinking.
10. Probar 3 landings.
11. Escalar progresivamente.

---

50. ESTADO

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fin del documento.
