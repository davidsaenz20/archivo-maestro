ESQUEMA DE DATOS

Versión: 3.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el modelo de datos canónico del sistema SEO automatizado.

---

1. FUNCIÓN

Este documento define el modelo de datos común utilizado por:

- investigación;
- evidencias;
- matrices;
- oportunidades;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques;
- generación mediante IA;
- validación;
- N8N;
- WordPress;
- publicación;
- actualización;
- trazabilidad.

Los documentos especializados pueden definir reglas adicionales, pero no deben crear estructuras incompatibles con este modelo.

---

2. PRINCIPIO FUNDAMENTAL

El sistema debe poder representar una web completa, no solamente una página aislada.

Una oportunidad puede generar:

- una landing principal;
- páginas de servicios;
- páginas de subservicios;
- páginas informativas;
- página de contacto;
- otras páginas justificadas por la arquitectura.

Ejemplo:

OPORTUNIDAD:

Fontanero + Marbella

Puede producir:

/fontanero/marbella/
├── /fontanero/marbella/desatascos/
├── /fontanero/marbella/24-horas/
├── /fontanero/marbella/reparaciones/
└── /fontanero/marbella/contacto/

Las páginas hijas no se crean automáticamente por existir una combinación de keywords.

Cada página debe estar autorizada por la arquitectura y disponer de una razón funcional.

---

3. IDENTIDAD DE LA OPORTUNIDAD

Campo:

"opportunity_id"

Tipo:

"string"

Obligatorio:

sí.

Debe ser único y estable.

Ejemplo:

"OPP-0001"

No debe cambiar durante el ciclo de vida de la oportunidad.

---

4. IDENTIDAD DEL PROYECTO

Cada oportunidad pertenece a un proyecto.

project
├── project_id
├── project_name
├── sector
├── business_model
└── status

Ejemplo:

project_id: PROJ-SEO-001
project_name: Fontanería Marbella
sector: fontanería
business_model: alquiler_lead_generation
status: ACTIVE

---

5. IDENTIDAD DEL SERVICIO

identity
├── sector
├── service
├── subservice
├── page_type
├── country
├── autonomous_community
├── province
├── municipality
└── locality

"service"

Servicio principal.

Ejemplo:

"fontanero"

"subservice"

Servicio específico.

Ejemplo:

"desatascos"

Puede ser:

"null"

"page_type"

Debe proceder de la arquitectura.

Valores iniciales:

- "servicio_localidad"
- "servicio_subservicio_localidad"
- "servicio_localidad_subpagina"
- "servicio_subservicio_localidad_subpagina"

No se deben utilizar tipos nuevos sin documentarlos.

---

6. LOCALIZACIÓN

location
├── country
├── autonomous_community
├── province
├── municipality
├── locality
└── zones

Los datos territoriales deben proceder de información válida.

No se inventan:

- barrios;
- urbanizaciones;
- zonas;
- pedanías;
- municipios;
- cobertura.

Los datos desconocidos se representan mediante:

"null"

---

7. INTENCIÓN

intent
├── type
├── confidence
└── evidence

Tipos iniciales:

- "informational"
- "commercial"
- "transactional"
- "navigational"
- "local"
- "mixed"

Confianza:

- "high"
- "medium"
- "low"
- "unknown"

La intención debe estar respaldada por evidencias.

La IA puede clasificar información, pero no convertir una hipótesis en evidencia confirmada.

---

8. INVESTIGACIÓN

research
├── sources
├── evidence
├── demand
├── competition
├── trend
└── notes

Cada fuente puede contener:

id
type
url
date
description

Cada evidencia debe clasificarse como:

- "observed"
- "inference"
- "hypothesis"
- "unknown"

---

9. DEMANDA

demand
├── keyword
├── volume
├── trend
├── seasonality
├── source
└── date

Cuando no exista una medición fiable:

"null"

Nunca se inventa volumen.

"null" no significa cero.

---

10. COMPETENCIA

competition
├── relevant_results
├── competitors
├── quality
├── difficulty
└── observations

La competencia debe conservar su evidencia.

No se asignan puntuaciones arbitrarias.

---

11. DECISIÓN SEO

Campo:

"decision_seo"

Valores oficiales:

- "CREAR"
- "AGRUPAR"
- "INVESTIGAR"
- "NO CREAR"

Son los únicos resultados oficiales del motor.

La IA no puede modificar esta decisión.

---

12. AGRUPACIÓN

Cuando:

"decision_seo = AGRUPAR"

debe poder indicarse:

grouping
├── destination_page_id
├── destination_url
└── reason

No se crea una página independiente.

---

13. ARQUITECTURA

Solo existe arquitectura definitiva cuando:

"decision_seo = CREAR"

architecture
├── site
├── pages
├── navigation
└── hierarchy

---

14. IDENTIDAD DE PÁGINA

Cada página de la miniweb debe disponer de un identificador único.

page_id

Ejemplos:

PAGE-0001
PAGE-0002
PAGE-0003

El "page_id" no se reutiliza.

---

15. DATOS DE CADA PÁGINA

page
├── page_id
├── page_type
├── purpose
├── parent_page_id
├── architecture
├── intent
├── blocks
├── content
├── seo
├── links
├── validation
├── publication
└── status

---

16. ARQUITECTURA DE URL

architecture
├── url
├── url_type
├── canonical
├── parent_url
├── depth
└── indexable

Ejemplo:

url: /fontanero/marbella/desatascos/
url_type: servicio_subservicio_localidad_subpagina
canonical: /fontanero/marbella/desatascos/
parent_url: /fontanero/marbella/
depth: 3
indexable: true

La URL debe estar determinada antes de generar contenido.

La IA no decide la URL.

---

17. JERARQUÍA DE PÁGINAS

La miniweb debe poder representar:

SITE
│
├── PÁGINA PRINCIPAL
│
├── SERVICIOS
│   ├── SUBSERVICIO
│   └── SUBSERVICIO
│
├── PÁGINAS ESPECÍFICAS
│
└── CONTACTO

Cada página debe conocer su página padre cuando exista.

Esto permite construir automáticamente:

- menú;
- breadcrumbs;
- enlaces internos;
- navegación;
- footer;
- estructura jerárquica.

---

18. REGLA DE CREACIÓN DE SUBPÁGINAS

Una subpágina solo puede crearse cuando:

1. está autorizada por la arquitectura;
2. tiene una finalidad independiente;
3. existe intención suficiente;
4. existe información suficiente;
5. existe diferenciación;
6. no supone una duplicación artificial;
7. su URL está autorizada.

No se deben crear automáticamente todas las combinaciones posibles.

---

19. MENÚ

navigation
├── main
├── secondary
└── footer

Cada elemento puede contener:

label
url
target_page_id
position
enabled

Las URLs deben proceder de páginas existentes o autorizadas.

La IA no crea enlaces arbitrarios.

---

20. BLOQUES

blocks
├── selected
└── configuration

La selección procede de:

"proyecto/seo/arquitectura-landing.md"

y:

"proyecto/seo/sistema-bloques.md"

---

21. IDENTIFICADORES DE BLOQUE

Mapa oficial:

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

---

22. CONFIGURACIÓN DE BLOQUES

Cada bloque puede contener:

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

La IA no puede inventar IDs.

---

23. DATOS LOCALES

local_data
├── available
├── information
├── points_of_interest
├── zones
└── sources

Si:

"available = false"

no se genera contenido local específico.

---

24. COBERTURA

coverage
├── confirmed
├── municipalities
├── zones
└── sources

Solo se afirma cobertura respaldada.

---

25. DATOS COMERCIALES

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

Cada dato puede contener:

- valor real;
- "null";
- "REVIEW".

Nunca se utiliza "null" como permiso para inventar.

---

26. RESEÑAS Y TESTIMONIOS

reviews
├── available
├── source
├── count
└── items

Los testimonios reales pueden representarse mediante:

author
date
rating
text
source

No se generan testimonios ficticios.

---

27. CONTENIDO

content
├── seo
├── blocks
└── status

El contenido solo se genera cuando:

"decision_seo = CREAR"

y la arquitectura está preparada.

---

28. SEO

content.seo
├── title
├── meta_description
└── h1

El slug no se genera libremente.

La URL procede de:

"architecture.url"

---

29. IMÁGENES

images
├── required
└── items

Cada imagen puede contener:

id
type
description
alt
source
url
license
status

No se inventan URLs.

No se atribuyen imágenes al negocio sin evidencia.

---

30. ENLACES INTERNOS

internal_links
├── incoming
└── outgoing

Cada enlace puede contener:

url
anchor
target_page_id
reason

Los enlaces deben corresponder con la arquitectura.

---

31. DATOS ESTRUCTURADOS

schema
├── type
├── data
└── status

Solo puede utilizar información real.

No se inventan:

- valoraciones;
- precios;
- direcciones;
- horarios;
- empresas;
- personas.

---

32. ESTADO DE OPORTUNIDAD

Campo:

"opportunity_status"

Valores:

- "DETECTED"
- "RESEARCHED"
- "EVALUATED"
- "DECIDED"
- "CLOSED"

Este estado describe la oportunidad.

No sustituye a "decision_seo".

---

33. ESTADO DE LA MINIWEB

Campo:

"site_status"

Valores:

- "NOT_STARTED"
- "ARCHITECTURE_READY"
- "PAGES_DEFINED"
- "DATA_READY"
- "CONTENT_GENERATED"
- "VALIDATION_PENDING"
- "VALIDATED"
- "PUBLISHED"
- "REVIEW"
- "REJECTED"

---

34. ESTADO DE CADA PÁGINA

Campo:

"page_status"

Valores:

- "NOT_STARTED"
- "DATA_READY"
- "ARCHITECTURE_READY"
- "BLOCKS_SELECTED"
- "CONTENT_GENERATED"
- "VALIDATION_PENDING"
- "VALIDATED"
- "PUBLISHED"
- "REVIEW"
- "REJECTED"

---

35. ESTADO DEL CONTENIDO

Valores:

- "NOT_GENERATED"
- "GENERATED"
- "REVIEW"
- "VALIDATED"

No sustituye a:

- "decision_seo";
- "opportunity_status";
- "page_status";
- "site_status".

---

36. VALIDACIÓN

validation
├── result
├── date
├── rules
├── errors
└── observations

Valores:

- "APPROVED"
- "REJECTED"
- "REVIEW"

La validación definitiva no corresponde a la IA.

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

- "OPEN"
- "IN_REVIEW"
- "RESOLVED"
- "DISMISSED"

---

39. PUBLICACIÓN

publication
├── status
├── wordpress_id
├── wordpress_url
├── published_at
└── updated_at

Estados iniciales:

- "NOT_PUBLISHED"
- "PUBLISHED"
- "UPDATE_PENDING"
- "ERROR"

N8N no debe considerar publicada una página si WordPress no confirma correctamente la operación.

---

40. ACTUALIZACIÓN

La información publicada debe poder actualizarse sin destruir la identidad de la página.

update
├── source
├── date
├── fields_changed
├── reason
└── status

Una actualización puede afectar:

- contenido;
- horarios;
- precios;
- cobertura;
- enlaces;
- imágenes;
- datos comerciales.

La URL no debe cambiar salvo que la arquitectura lo autorice.

---

41. TRAZABILIDAD

traceability
├── schema_version
├── decision_engine_version
├── prompt_version
├── contract_version
├── blocks_version
├── created_at
├── updated_at
└── history

Debe permitir conocer:

- qué oportunidad originó la página;
- qué versión del motor decidió;
- qué versión del esquema se utilizó;
- qué versión de bloques se utilizó;
- qué contrato recibió la IA;
- qué prompt generó el contenido;
- cuándo se creó;
- cuándo se actualizó.

---

42. HISTORIAL

Los cambios importantes deben conservarse.

Ejemplo:

{
  "date": "2026-08-24",
  "field": "page_status",
  "previous": "CONTENT_GENERATED",
  "new": "VALIDATED",
  "reason": "Validación completada"
}

---

43. REGLA DE NO INVENCIÓN

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

Cuando un dato no existe:

"null"

o:

"REVIEW"

cuando sea imprescindible para continuar.

---

44. REGLA DE DATOS DESCONOCIDOS

Un dato desconocido no equivale automáticamente a:

"0"

ni a:

"false"

ni a:

"no existe".

Debe conservarse como:

"null"

hasta disponer de evidencia.

---

45. REGLA DE IA

La IA puede:

- interpretar datos;
- clasificar información;
- redactar contenido;
- detectar patrones;
- proponer hipótesis;
- estructurar datos.

La IA no puede:

- decidir crear una página;
- modificar "decision_seo";
- inventar URLs;
- inventar páginas;
- inventar bloques;
- inventar datos;
- modificar la arquitectura;
- inventar información comercial.

---

46. CONTRATO IA

La IA recibe como contexto mínimo:

project
opportunity
identity
location
intent
research
decision_seo
architecture
pages
blocks
data
restrictions

La IA devuelve únicamente información compatible con el esquema.

El contrato formal se define en:

"proyecto/seo/contrato-salida-ia.md"

---

47. RELACIÓN CON N8N

N8N actúa como sistema de transporte y automatización.

Flujo conceptual:

OPORTUNIDAD
↓
ARQUITECTURA
↓
PÁGINAS
↓
DATOS
↓
BLOQUES
↓
IA
↓
VALIDACIÓN
↓
WORDPRESS
↓
PUBLICACIÓN

N8N no debe tomar decisiones SEO que correspondan al motor.

---

48. RELACIÓN CON WORDPRESS

WordPress recibe una estructura previamente validada.

Puede recibir:

- páginas;
- contenido;
- bloques;
- imágenes;
- enlaces;
- SEO;
- datos estructurados.

WordPress es la capa de presentación y publicación.

No debe utilizarse como lugar donde se decida qué páginas deben existir.

---

49. IDEMPOTENCIA

Una misma oportunidad procesada varias veces no debe crear duplicados.

El sistema debe utilizar identificadores estables:

project_id
opportunity_id
page_id
block_id

Si una página ya existe:

- se actualiza;
- se revisa;
- o se mantiene;

pero no se crea otra página idéntica.

---

50. REGLA DE CONSISTENCIA

Los siguientes elementos deben permanecer sincronizados:

OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
↓
PÁGINAS
↓
BLOQUES
↓
CONTENIDO
↓
VALIDACIÓN
↓
PUBLICACIÓN

Una capa no puede contradecir a una capa anterior.

---

51. EJEMPLO COMPLETO

Proyecto:

"PROJ-SEO-001"

Oportunidad:

"OPP-0001"

Servicio:

"fontanero"

Localidad:

"Marbella"

Decisión:

"CREAR"

Página principal:

page_id: PAGE-0001
url: /fontanero/marbella/

Subpágina:

page_id: PAGE-0002
url: /fontanero/marbella/desatascos/
parent_page_id: PAGE-0001

Otra subpágina:

page_id: PAGE-0003
url: /fontanero/marbella/24-horas/
parent_page_id: PAGE-0001

Contacto:

page_id: PAGE-0004
url: /fontanero/marbella/contacto/
parent_page_id: PAGE-0001

Las páginas solo existen si la arquitectura y la evidencia justifican su creación.

---

52. REGLA DE MINIWEB

Cuando una oportunidad represente una web alquilable o un proyecto de presencia local completa, el sistema debe poder generar:

1. página principal;
2. páginas de servicios;
3. páginas de subservicios;
4. páginas comerciales;
5. contacto;
6. navegación;
7. footer;
8. enlaces internos.

No todas las páginas son obligatorias.

La arquitectura decide cuáles existen.

---

53. ESCALABILIDAD

El mismo modelo debe permitir:

- una página;
- una miniweb;
- 10 miniwebs;
- 100 miniwebs;
- 1.000 miniwebs.

La estructura de datos debe permanecer estable.

Lo que cambia es:

- proyecto;
- sector;
- servicio;
- localidad;
- evidencias;
- datos;
- arquitectura;
- páginas;
- contenido.

---

54. MULTISECTOR

El modelo debe poder utilizarse para:

- fontaneros;
- electricistas;
- abogados;
- carpinteros;
- pintores;
- jardineros;
- reformas;
- otros servicios.

El modelo general permanece estable.

---

55. REGLA DE SEPARACIÓN

Cada capa tiene una responsabilidad diferente:

INVESTIGACIÓN
→ obtiene información.

OPORTUNIDAD
→ estructura la posibilidad.

MOTOR
→ decide.

ARQUITECTURA
→ define la estructura.

PÁGINAS
→ define qué páginas forman el proyecto.

BLOQUES
→ define cómo se organiza cada página.

DATOS
→ proporciona la información.

IA
→ genera contenido.

VALIDACIÓN
→ comprueba.

N8N
→ automatiza.

WORDPRESS
→ publica.

Ninguna capa debe asumir las responsabilidades de otra.

---

56. ESTADO ACTUAL

Versión:

"v3.0"

Estado:

"PREPARADO PARA IMPLEMENTACIÓN PILOTO"

El modelo queda preparado para representar tanto una landing individual como una miniweb local completa.

---

57. REGISTRO DE ACTUALIZACIÓN

2026-08-24 — v3.0

Se actualiza el modelo de datos después de la consolidación del:

- motor de decisión;
- matriz de oportunidades;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques.

Cambios principales:

- incorporación formal del concepto de proyecto;
- incorporación de "page_id";
- incorporación de múltiples páginas por oportunidad;
- soporte para miniwebs locales completas;
- soporte para páginas hijas;
- soporte para jerarquía de páginas;
- soporte para navegación;
- soporte para publicación;
- soporte para actualización;
- refuerzo de idempotencia;
- alineación con B01–B23;
- separación entre oportunidad, página y bloque;
- preparación para IA → N8N → WordPress;
- mantenimiento de la regla de no invención;
- mantenimiento de trazabilidad y versionado.

El esquema queda preparado para la siguiente capa del sistema: el contrato de salida de IA y la posterior automatización.

---

FIN DE ESQUEMA DE DATOS
