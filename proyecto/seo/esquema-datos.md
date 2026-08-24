ESQUEMA DE DATOS

Versión: 2.0
Estado: ACTIVO
Función: definir el modelo de datos canónico del sistema SEO automatizado.

---

1. FUNCIÓN

Este documento define el modelo de datos común utilizado por:

- investigación;
- evidencias;
- matrices;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques;
- IA;
- N8N;
- validación;
- WordPress;
- publicación;
- trazabilidad.

Los documentos especializados pueden definir reglas adicionales, pero no deben crear estructuras que contradigan este modelo.

---

2. PRINCIPIO FUNDAMENTAL

Cada oportunidad debe poder:

1. identificarse;
2. investigarse;
3. evaluarse;
4. decidirse;
5. arquitectarse;
6. generarse;
7. validarse;
8. publicarse o descartarse;
9. actualizarse posteriormente.

Cada oportunidad mantiene una identidad estable.

Ejemplo:

OPP-0001
fontanero / Marbella

OPP-0002
fontanero / desatascos / Marbella

---

3. IDENTIFICACIÓN

opportunity_id

Tipo:

"string"

Obligatorio:

"sí"

Debe ser único y estable.

Ejemplo:

"OPP-0001"

No debe cambiar durante el ciclo de vida de la oportunidad.

---

4. IDENTIDAD

identity
├── sector
├── service
├── subservice
├── page_type
├── municipality
├── province
├── country
└── locality

sector

Sector profesional.

service

Servicio principal.

Ejemplo:

"fontanero"

subservice

Servicio específico.

Ejemplo:

"desatascos"

Puede ser:

"null"

page_type

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

La IA no decide este valor.

---

5. LOCALIZACIÓN

location
├── country
├── autonomous_community
├── province
├── municipality
├── locality
└── zones

Los datos territoriales deben proceder de información válida.

municipality

Ejemplo:

"Marbella"

province

Ejemplo:

"Málaga"

locality

Puede ser "null" cuando no sea necesaria.

zones

Lista de zonas confirmadas.

No se deben inventar zonas.

---

6. INTENCIÓN

intent
├── type
├── confidence
└── evidence

type

Valores iniciales:

informational
commercial
transactional
navigational
local
mixed

confidence

high
medium
low
unknown

evidence

Referencia a las evidencias que justifican la clasificación.

---

7. INVESTIGACIÓN

research
├── sources
├── evidence
├── demand
├── competition
├── trend
└── notes

sources

Cada fuente puede contener:

id
type
url
date
description

evidence

Cada evidencia debe diferenciar:

observed
inference
hypothesis
unknown

Una hipótesis no equivale a un dato confirmado.

demand

Puede contener:

keyword
volume
trend
seasonality
source
date

Cuando no exista medición fiable:

"null"

No se inventa volumen.

competition

Puede contener:

- resultados relevantes;
- competidores;
- calidad;
- dificultad;
- observaciones.

trend

Información temporal relevante.

notes

Observaciones adicionales.

---

8. DECISIÓN SEO

Campo:

"decision_seo"

Valores permitidos:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

Son los únicos resultados oficiales del motor.

La IA no modifica esta decisión.

---

9. CREAR

Significa que la oportunidad justifica una landing independiente.

Permite continuar hacia:

arquitectura
→ bloques
→ contenido
→ validación
→ publicación

---

10. AGRUPAR

Significa que la intención existe pero no justifica una página independiente.

grouping
├── destination_page
├── destination_url
└── reason

No se genera una URL independiente.

La URL de destino debe existir o estar previamente autorizada.

---

11. INVESTIGAR

Significa que no existe información suficiente para tomar una decisión fiable.

No se genera todavía una landing definitiva.

La oportunidad permanece pendiente de investigación.

---

12. NO CREAR

Significa que existe evidencia suficiente para determinar que no debe existir una página independiente.

No se genera landing.

---

13. ARQUITECTURA

Solo debe existir una arquitectura definitiva cuando:

decision_seo = CREAR

Estructura:

architecture
├── page_type
├── url
├── url_type
├── canonical
├── parent_url
└── depth

---

14. TIPO DE PÁGINA

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

La elección procede de la arquitectura SEO.

La IA no puede modificarla.

---

15. URL

Campo:

"architecture.url"

Ejemplos:

/fontanero/marbella/

/fontanero/desatascos/marbella/

La URL debe determinarse antes de generar contenido.

La IA nunca decide la URL.

---

16. TIPO DE URL

Campo:

"architecture.url_type"

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

---

17. CANONICAL

Campo:

"architecture.canonical"

Debe representar la URL canónica autorizada.

La IA no puede inventarlo ni modificarlo.

---

18. PÁGINA PADRE

Campo:

"architecture.parent_url"

Ejemplo:

/fontanero/

para:

/fontanero/marbella/

Puede ser "null".

---

19. PROFUNDIDAD

Campo:

"architecture.depth"

Representa el nivel lógico dentro de la arquitectura.

Ejemplo:

1
2
3

No representa simplemente el número de barras de la URL.

---

20. DATOS LOCALES

local_data
├── available
├── information
├── points_of_interest
├── zones
└── sources

Si:

available = false

no se debe generar contenido local específico.

La ausencia de información local no autoriza a inventarla.

---

21. COBERTURA

coverage
├── confirmed
├── municipalities
├── zones
└── source

Solo se afirma cobertura cuando está respaldada.

No se crean listas artificiales de localidades o zonas.

---

22. DATOS COMERCIALES

commercial_data
├── company
├── phone
├── whatsapp
├── email
├── address
├── opening_hours
├── price
├── guarantee
├── experience
└── certifications

Los campos pueden contener:

- un valor real;
- "null".

"null" significa:

dato no disponible.

Nunca significa permiso para inventarlo.

---

23. RESEÑAS Y TESTIMONIOS

reviews
├── available
├── source
├── count
└── items

Cada elemento puede contener:

author
date
rating
text
source

Las reseñas deben ser reales.

Los testimonios deben estar autorizados.

Nunca se generan reseñas o testimonios ficticios.

---

24. BLOQUES

blocks
├── selected
└── configuration

La selección procede de la arquitectura de landing.

Ejemplo:

[
  "B01",
  "B02",
  "B03",
  "B04",
  "B05",
  "B06"
]

La IA no puede añadir bloques por iniciativa propia.

---

25. MAPA OFICIAL DE BLOQUES

B01 = header
B02 = navigation
B03 = hero
B04 = main_content
B05 = cta
B06 = footer
B07 = subservice
B08 = problems
B09 = local_context
B10 = coverage
B11 = process
B12 = trust
B13 = differentiation
B14 = faq
B15 = related_services
B16 = related_locations
B17 = structured_data
B18 = testimonials
B19 = cases
B20 = gallery
B21 = pricing
B22 = opening_hours
B23 = map

Este mapa es vinculante.

Los identificadores proceden de:

"proyecto/seo/sistema-bloques.md"

---

26. CONFIGURACIÓN DE BLOQUES

Cada bloque puede disponer de:

block_id
type
position
enabled
data
conditions
restrictions
fallback

Ejemplo:

{
  "block_id": "B03",
  "type": "hero",
  "position": 3,
  "enabled": true,
  "data": {}
}

El "type" debe corresponder con el identificador oficial.

---

27. CONTENIDO

content
├── seo
├── blocks
└── status

El contenido se genera únicamente después de que:

decision_seo = CREAR

y exista arquitectura válida.

---

28. SEO DEL CONTENIDO

content.seo
├── title
├── meta_description
└── h1

El slug no pertenece a la generación libre de contenido.

La URL procede de:

"architecture.url"

---

29. CONTENIDO DE BLOQUES

Cada bloque generado debe conservar:

block_id
type
position
enabled
data

Ejemplo:

{
  "block_id": "B03",
  "type": "hero",
  "position": 3,
  "enabled": true,
  "data": {
    "title": "",
    "subtitle": ""
  }
}

---

30. IMÁGENES

images
├── required
└── items

Cada elemento puede contener:

id
type
description
alt
source
url
status

La IA puede generar descripciones y textos ALT.

No puede inventar URLs de imágenes.

---

31. ENLAZADO INTERNO

internal_links
├── incoming
└── outgoing

Cada enlace puede contener:

url
anchor
target
reason

Las URLs deben proceder de la arquitectura existente o de un conjunto expresamente autorizado.

La IA no crea URLs arbitrarias.

---

32. DATOS ESTRUCTURADOS

schema
├── type
├── data
└── status

Solo puede utilizar información real disponible.

Nunca se inventan:

- valoraciones;
- precios;
- direcciones;
- horarios;
- empresas;
- personas.

El renderizado final de JSON-LD corresponde a la capa de presentación.

---

33. ESTADO DE OPORTUNIDAD

Campo:

"opportunity_status"

Valores:

DETECTED
RESEARCHED
EVALUATED
DECIDED
CLOSED

Este estado describe el ciclo de la oportunidad.

No sustituye a "decision_seo".

---

34. ESTADO DE LANDING

Solo existe cuando:

decision_seo = CREAR

Valores:

NOT_STARTED
DATA_READY
ARCHITECTURE_READY
BLOCKS_SELECTED
CONTENT_GENERATED
VALIDATION_PENDING
VALIDATED
PUBLISHED
REJECTED
REVIEW

Este estado describe el ciclo de construcción/publicación.

No sustituye a la decisión SEO.

---

35. ESTADO DEL CONTENIDO

Valores:

NOT_GENERATED
GENERATED
REVIEW
VALIDATED

No sustituye:

- "decision_seo";
- "opportunity_status";
- "landing_status".

Cada estado tiene una función diferente.

---

36. VALIDACIÓN

validation
├── result
├── date
├── rules
├── errors
└── observations

Valores:

APPROVED
REJECTED
REVIEW

La validación definitiva corresponde al validador externo.

La IA puede informar de problemas, pero no es la autoridad final.

---

37. ERRORES

Cada error debe contener:

code
element
description
severity

Ejemplo:

{
  "code": "DATA001",
  "element": "phone",
  "description": "No existe un teléfono validado.",
  "severity": "high"
}

---

38. INCIDENCIAS

issues
├── code
├── element
├── description
├── severity
└── status

Estados:

OPEN
IN_REVIEW
RESOLVED
DISMISSED

---

39. TRAZABILIDAD

traceability
├── schema_version
├── decision_engine_version
├── prompt_version
├── contract_version
├── created_at
├── updated_at
└── history

Debe permitir identificar:

- qué oportunidad fue utilizada;
- qué versión del motor decidió;
- qué versión del contrato se utilizó;
- qué versión del prompt generó el contenido;
- cuándo se creó;
- cuándo se actualizó.

---

40. VERSIONES

schema_version

Identifica la versión de este esquema.

Versión actual:

"2.0"

decision_engine_version

Identifica la versión del motor de decisión utilizada.

Ejemplo:

"v1.0"

contract_version

Identifica la versión del contrato IA → N8N.

Ejemplo:

"2.0"

prompt_version

Identifica la versión del prompt utilizado por la IA.

---

41. HISTORIAL

Los cambios importantes deben conservarse.

Ejemplo:

{
  "date": "2026-08-24",
  "field": "decision_seo",
  "previous": "INVESTIGAR",
  "new": "CREAR",
  "reason": "Nueva evidencia disponible"
}

---

42. REGLA DE NO INVENCIÓN

Ninguna capa del sistema puede inventar información factual.

Especialmente:

- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- horarios;
- precios;
- empresas;
- experiencia;
- certificaciones;
- garantías;
- reseñas;
- valoraciones;
- testimonios;
- cobertura;
- imágenes;
- estadísticas;
- datos locales;
- URLs.

Cuando un dato no exista:

null

o:

REVIEW

cuando sea imprescindible.

---

43. REGLA DE DATOS DESCONOCIDOS

Un dato desconocido no equivale automáticamente a:

"0"

ni a:

"false"

ni a:

"NO EXISTE".

Debe utilizarse:

"null"

o un estado explícito de desconocimiento.

Esto es especialmente importante para:

- demanda;
- volumen;
- competencia;
- datos locales;
- cobertura;
- precios;
- horarios.

---

44. RELACIÓN CON EL MOTOR DE DECISIÓN

El flujo es:

investigación
↓
matrices
↓
motor
↓
decision_seo

El motor utiliza los datos y evidencias del modelo.

El esquema de datos no decide por sí mismo si una oportunidad debe crearse.

---

45. RELACIÓN CON WORDPRESS

Cuando:

decision_seo = CREAR

y el contenido ha sido validado:

modelo de datos
↓
N8N
↓
WordPress
↓
Landing

WordPress utiliza principalmente:

- identidad;
- arquitectura;
- SEO;
- bloques;
- imágenes;
- enlaces;
- schema;
- datos comerciales autorizados.

---

46. RELACIÓN CON N8N

N8N utiliza este esquema como estructura de transporte y transformación.

Debe poder:

- localizar una oportunidad;
- determinar si existe una landing;
- crear;
- actualizar;
- validar;
- registrar errores;
- registrar resultados.

El identificador estable evita duplicaciones.

---

47. IDEMPOTENCIA

Una misma oportunidad procesada varias veces no debe generar múltiples landings.

La identidad estable será:

"opportunity_id"

El sistema podrá utilizar además un identificador estable de landing cuando corresponda.

Regla:

NO EXISTE
→ CREATE

EXISTE
→ UPDATE

---

48. REGLA DE IA

La IA puede:

- clasificar;
- extraer;
- redactar;
- estructurar;
- proponer hipótesis;
- generar contenido.

No puede:

- cambiar la decisión;
- cambiar la URL;
- inventar datos;
- inventar bloques;
- modificar campos protegidos;
- convertir hipótesis en hechos.

---

49. MODELO CANÓNICO

La estructura conceptual completa es:

OPPORTUNITY
│
├── identity
├── location
├── intent
├── research
├── decision
├── architecture
├── local_data
├── coverage
├── commercial_data
├── reviews
├── blocks
├── content
├── images
├── internal_links
├── schema
├── opportunity_status
├── landing_status
├── validation
├── issues
└── traceability

Esta estructura constituye el modelo canónico.

---

50. REGLA DE AUTORIDAD

Cuando dos documentos entren en contradicción:

1. identificar qué documento es propietario de la decisión;
2. mantener la fuente de verdad;
3. corregir el documento dependiente;
4. registrar el cambio;
5. evitar resolver la contradicción mediante memoria informal.

El repositorio debe permanecer como fuente de verdad del proyecto.

---

51. ESTADO ACTUAL

Versión: v2.0

Estado: ACTIVO

El esquema queda consolidado para trabajar conjuntamente con:

- motor de decisión v1.0;
- arquitectura SEO v2.0;
- arquitectura URL v2.0;
- arquitectura landing v2.0;
- sistema de bloques v2.0;
- arquitectura WordPress v2.0;
- modelo de datos WordPress v2.0;
- contrato IA → N8N v2.0.

---

52. SIGUIENTE PASO

Utilizar este esquema durante el piloto.

Primero:

OPORTUNIDAD REAL
↓
MODELO DE DATOS
↓
DECISIÓN
↓
ARQUITECTURA
↓
BLOQUES
↓
IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

Durante el piloto se comprobará si el modelo necesita ajustes.

Los cambios estructurales deberán incrementar la versión.

---

53. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza "esquema-datos.md" a la versión v2.0.

Se consolida como modelo canónico del proyecto.

Se incorporan y alinean:

- identidad estable;
- localización;
- intención;
- clasificación de evidencias;
- investigación;
- decisión SEO;
- arquitectura;
- datos locales;
- cobertura;
- datos comerciales;
- reseñas y testimonios;
- bloques B01–B23;
- contenido;
- imágenes;
- enlazado interno;
- datos estructurados;
- estados independientes;
- validación;
- incidencias;
- trazabilidad;
- versiones;
- idempotencia;
- integración N8N;
- integración WordPress;
- restricciones de IA.

La versión anterior del esquema queda sustituida por esta versión consolidada.
