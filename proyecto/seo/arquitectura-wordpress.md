MODELO DE DATOS WORDPRESS

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Proyecto: Plataforma de landings locales automatizadas

---

1. FUNCIÓN

Este documento define la proyección del modelo de datos común hacia WordPress.

No sustituye a:

- "proyecto/seo/modelo-datos.md"
- "proyecto/seo/sistema-bloques.md"
- "proyecto/seo/contrato-salida-ia.md"
- "proyecto/seo/arquitectura-wordpress.md"

WordPress almacena y renderiza una landing previamente decidida y validada.

No decide:

- la estrategia SEO;
- la creación de una página;
- la arquitectura de URL;
- los bloques que corresponden;
- el contenido que debe generar la IA.

Flujo:

MODELO DE DATOS COMÚN
        ↓
DECISIÓN SEO
        ↓
ARQUITECTURA
        ↓
CONTRATO IA
        ↓
VALIDACIÓN
        ↓
N8N
        ↓
MODELO WORDPRESS
        ↓
PLANTILLA
        ↓
HTML FINAL

---

2. PRINCIPIO DE PROYECCIÓN

No todo el modelo común debe almacenarse como campo público de WordPress.

Se separan tres grupos:

1. Datos necesarios para renderizar.
2. Datos necesarios para SEO/publicación.
3. Datos de trazabilidad o control interno.

Los datos de investigación, evidencias y razonamiento del motor no deben exponerse innecesariamente en la página pública.

---

3. ENTIDAD PRINCIPAL

Tipo conceptual:

"Landing"

Implementación prevista:

"Custom Post Type: landing"

Cada registro representa una única landing.

La decisión definitiva del CPT y del sistema de campos se realizará durante la implementación técnica.

La implementación debe permitir:

- creación;
- actualización;
- identificación estable;
- renderizado mediante una plantilla común;
- publicación controlada.

---

4. IDENTIFICACIÓN

Campo| Tipo| Origen| Almacenamiento| Público
"landing_id"| string| motor/N8N| meta| no
"opportunity_id"| string| investigación/motor| meta| no
"version"| string| sistema| meta| no
"estado_landing"| enum| workflow| meta| no

"landing_id" debe ser estable e idempotente.

La IA no puede modificarlo.

---

5. IDENTIDAD

Campo| Tipo| Origen| Almacenamiento| Renderizado
"sector"| string| modelo común| estructurado| indirecto
"servicio"| string| motor| estructurado| sí
"subservicio"| string/null| motor| estructurado| condicional
"pais"| string| modelo común| estructurado| condicional
"comunidad_autonoma"| string| modelo común| estructurado| condicional
"provincia"| string| modelo común| estructurado| condicional
"municipio"| string| motor| estructurado| sí
"localidad"| string| motor| estructurado| sí
"intencion"| enum| motor| meta/control| indirecto

La identidad de la landing procede de la arquitectura validada.

No puede ser modificada libremente por la IA.

---

6. URL

Campo| Tipo| Origen| Almacenamiento| Función
"slug"| string| arquitectura URL| post slug| URL
"url"| string| arquitectura URL| derivada/validada| URL
"canonical"| URL| arquitectura SEO| meta/SEO| head
"url_tipo"| enum| arquitectura URL| meta| control

WordPress no debe recalcular una URL estratégica de forma autónoma.

La URL debe proceder de la arquitectura validada.

---

7. SEO

Campo| Tipo| Origen| Función
"seo_title"| string| IA dentro de reglas| "<title>"
"meta_description"| string| IA dentro de reglas| "<meta>"
"h1"| string| contrato IA| encabezado principal
"robots"| enum/string| sistema| head
"canonical"| URL| arquitectura| head

El mecanismo concreto de almacenamiento SEO dependerá de la solución WordPress elegida.

No se permitirá que WordPress o la IA alteren arbitrariamente elementos SEO protegidos.

---

8. BLOQUES

Campo principal:

"bloques[]"

Cada elemento debe conservar como mínimo:

id
position
data

Ejemplo:

{
  "id": "B03",
  "position": 3,
  "data": {
    "h1": "Fontanero en Marbella",
    "subtitulo": "...",
    "cta": {}
  }
}

Los identificadores B01–B23 son los definidos por:

"proyecto/seo/sistema-bloques.md"

La IA no puede introducir identificadores no autorizados.

WordPress resolverá cada identificador mediante el componente correspondiente.

---

9. MAPA B01–B23 → DATOS

Bloque| Datos principales
B01 Header| marca, logo, navegación, CTA global
B02 Navegación| URLs globales y estratégicas validadas
B03 Hero| h1, subtítulo, CTA, confianza disponible
B04 Contenido principal| títulos, textos, problemas, alcance
B05 CTA principal| tipo, texto, canal/destino validado
B06 Footer| navegación, contacto, legal, enlaces globales
B07 Subservicio| servicio, subservicio, contenido específico
B08 Problemas/necesidades| elementos respaldados
B09 Información local| datos locales verificados
B10 Zonas/cobertura| zonas y cobertura confirmada
B11 Proceso| pasos reales del servicio
B12 Confianza| experiencia, certificaciones, garantías, reseñas válidas
B13 Diferenciación| información específica y verificable
B14 FAQ| preguntas y respuestas
B15 Servicios relacionados| URL, anchor, relación
B16 Localidades relacionadas| localidad, URL, relación
B17 Datos estructurados| schema válido
B18 Testimonios| testimonios reales/autorizados
B19 Casos/ejemplos| casos reales/documentados
B20 Galería| recursos de imagen reales
B21 Precio/tarifas| precio autorizado
B22 Horarios| horarios reales
B23 Mapa/ubicación| ubicación válida

---

10. FAQ

Campo:

"faq[]"

Estructura:

question
answer

Las FAQ deben proceder del contenido validado.

No pueden inventar:

- precios;
- horarios;
- servicios;
- condiciones;
- garantías;
- datos comerciales.

---

11. CTA

Estructura conceptual:

cta:
  type
  text
  destination

Tipos posibles:

whatsapp
phone
contact
quote
appointment

El destino debe ser real y previamente validado.

No se almacenará un teléfono, email o WhatsApp inventado.

---

12. DATOS COMERCIALES

Los datos comerciales públicos deben estar separados y validados.

Ejemplos:

empresa
marca
telefono
whatsapp
email
direccion
horarios
precio
garantia
experiencia
certificaciones

Regla:

ausencia de dato
        ↓
null / omitido

Nunca se debe inferir o inventar un dato comercial.

---

13. INTERLINKING

Campo:

"internal_links[]"

Cada enlace deberá contener:

url
anchor
target
reason

Ejemplo:

{
  "url": "/fontanero/estepona/",
  "anchor": "Fontanero en Estepona",
  "target": "localidad",
  "reason": "localidad relacionada"
}

Solo se almacenarán URLs existentes o previamente validadas.

La plantilla utilizará estos datos para renderizar los enlaces correspondientes.

La IA no puede inventar URLs.

---

14. IMÁGENES

Campo:

"images[]"

Estructura conceptual:

id
url
alt
title
type
source
license

WordPress podrá convertir los recursos válidos en IDs de Media Library durante la implementación.

La URL del recurso debe ser real.

No se publicarán imágenes inexistentes.

---

15. SCHEMA

Campo:

"schema"

Debe contener únicamente datos estructurados válidos y derivados de información autorizada.

La salida final será JSON-LD en el HTML.

No se permitirá completar campos del schema con información ficticia.

El tipo de schema debe corresponder con la información realmente disponible.

---

16. DATOS INTERNOS

No deben formar parte del contenido público salvo que una regla lo determine expresamente:

fuentes
evidencias
confianza
decision
restricciones
errores internos
logs
fecha_generacion
fecha_validacion

Pueden almacenarse para:

- trazabilidad;
- administración;
- auditoría;
- automatización;
- diagnóstico.

Estos datos no deben mezclarse con el contenido público de la landing.

---

17. VALIDACIÓN

Antes de crear o actualizar una landing, N8N debe comprobar como mínimo:

- "landing_id" válido;
- identidad coherente;
- URL y slug válidos;
- bloques autorizados;
- datos obligatorios presentes;
- ausencia de datos prohibidos;
- URLs internas válidas;
- schema válido;
- CTA y datos comerciales autorizados;
- idempotencia.

WordPress no sustituye al validador previo.

Si la validación falla:

NO PUBLICAR

y el sistema deberá registrar el error correspondiente.

---

18. RENDERIZADO

La plantilla seguirá esta lógica conceptual:

Landing
   ↓
leer identidad / SEO
   ↓
leer bloques[]
   ↓
resolver componente por ID
   ↓
pasar data del bloque
   ↓
renderizar HTML
   ↓
insertar interlinking
   ↓
insertar schema

La IA no genera directamente el HTML final de la página.

El HTML final pertenece a la capa de presentación de WordPress.

---

19. REGLA DE COMPONENTES

Existirá una correspondencia lógica:

B01 → Header
B02 → Navigation
B03 → Hero
...
B23 → Map

La implementación podrá utilizar:

- PHP;
- bloques dinámicos;
- componentes;
- campos estructurados;
- combinación de varias soluciones.

Pero la interfaz lógica permanecerá basada en los identificadores B01–B23.

Esto permite cambiar la presentación sin cambiar la arquitectura lógica.

---

20. CREAR / ACTUALIZAR

N8N utilizará "landing_id" para determinar la operación.

no existe landing_id
        ↓
CREATE

existe landing_id
        ↓
UPDATE

La operación debe ser idempotente.

Ejecutar dos veces la misma información no debe crear dos landings.

Durante la primera fase, la creación automática deberá utilizar:

"draft"

hasta completar las pruebas.

---

21. FIXTURE DE PRUEBA

Se utilizará una primera landing de prueba para validar el modelo.

Ejemplo conceptual:

landing_id: LANDING-fontanero-marbella
servicio: fontanero
subservicio: null
pais: España
comunidad_autonoma: Andalucía
provincia: Málaga
municipio: Marbella
localidad: Marbella
slug: fontanero-marbella

Los datos comerciales no disponibles permanecerán vacíos/null.

No se deben inventar:

- teléfono;
- WhatsApp;
- dirección;
- precio;
- horarios;
- certificaciones;
- experiencia;
- reseñas.

El fixture permitirá comprobar:

MODELO
   ↓
VALIDACIÓN
   ↓
N8N
   ↓
WORDPRESS
   ↓
PLANTILLA
   ↓
LANDING

---

22. IDEMPOTENCIA

La identidad de la landing debe permanecer estable.

Una combinación ya creada debe poder localizarse posteriormente para actualizarla.

Conceptualmente:

landing_id
        ↓
identidad estable
        ↓
CREATE / UPDATE

No se debe utilizar una identificación temporal generada por cada ejecución.

---

23. DECISIONES TÉCNICAS PENDIENTES

Todavía no se fija:

- plugin de campos;
- ACF u otra solución;
- estructura exacta de meta fields;
- tablas personalizadas;
- endpoints REST definitivos;
- autenticación;
- tema;
- constructor visual;
- implementación concreta de cada componente.

Estas decisiones pertenecen a la fase de implementación técnica.

El modelo lógico debe permanecer estable aunque posteriormente cambie la tecnología utilizada para implementarlo.

---

24. FUENTES DE VERDAD

modelo-datos.md
        ↓
modelo común

sistema-bloques.md
        ↓
B01–B23

contrato-salida-ia.md
        ↓
salida de IA

arquitectura-wordpress.md
        ↓
arquitectura de WordPress

modelo-datos-wordpress.md
        ↓
proyección del modelo dentro de WordPress

Si aparece una contradicción:

1. Identificar qué documento es propietario de la decisión.
2. Corregir ese documento.
3. Actualizar las dependencias.
4. Evitar resolver la contradicción mediante memoria informal.

El repositorio debe actuar como fuente de verdad del proyecto.

---

25. RELACIÓN CON N8N

N8N será responsable de transformar y transportar los datos validados hacia WordPress.

Conceptualmente:

DATOS
 ↓
IA
 ↓
VALIDACIÓN
 ↓
N8N
 ↓
WORDPRESS

N8N no debe alterar decisiones SEO protegidas.

WordPress no debe asumir funciones que corresponden al motor o al validador.

---

26. RELACIÓN CON LA IA

La IA genera únicamente los campos permitidos por el contrato de salida.

No puede modificar:

- "landing_id";
- decisión SEO;
- URL estratégica;
- bloques no autorizados;
- datos comerciales no disponibles;
- información factual no respaldada.

La IA puede generar contenido, pero no puede convertir una hipótesis en un dato confirmado.

---

27. RELACIÓN CON LA ARQUITECTURA WORDPRESS

"arquitectura-wordpress.md" define:

- cómo se estructura WordPress;
- responsabilidades;
- plantilla;
- componentes;
- renderizado;
- publicación;
- escalabilidad.

Este documento define:

- qué datos recibe WordPress;
- cómo se organizan;
- qué campos existen;
- cómo se representan los bloques;
- qué información es pública;
- qué información es interna.

Ambos documentos deben mantenerse coherentes.

---

28. ESTADO ACTUAL

Versión: v2.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

El modelo lógico de datos WordPress queda definido.

La implementación técnica concreta se realizará durante el piloto.

---

29. SIGUIENTE PASO

El siguiente paso será construir y validar una primera landing piloto.

Flujo:

MODELO
 ↓
DATOS DE PRUEBA
 ↓
VALIDACIÓN
 ↓
N8N
 ↓
WORDPRESS
 ↓
PLANTILLA
 ↓
RENDERIZADO

Primero se comprobará que una landing funciona correctamente.

Después se probará:

- CREATE;
- UPDATE;
- idempotencia;
- validación;
- bloques;
- SEO;
- interlinking;
- schema;
- imágenes.

Solo después se escalará el sistema.

---

30. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza "modelo-datos-wordpress.md" de la versión v1.0 — Diseño a v2.0 — Preparado para implementación piloto.

Se consolida la proyección del modelo común hacia WordPress.

Se refuerza:

- identidad estable;
- "landing_id";
- idempotencia;
- separación entre datos públicos e internos;
- bloques B01–B23;
- renderizado mediante componentes;
- separación entre contenido y HTML;
- validación previa;
- operaciones CREATE/UPDATE;
- publicación inicial mediante DRAFT;
- control de datos comerciales;
- control de URLs;
- control de schema;
- relación con N8N;
- relación con la IA;
- coherencia con la arquitectura WordPress.

El modelo queda preparado para su utilización durante la implementación del piloto.
