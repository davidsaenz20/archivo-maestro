ESQUEMA DE DATOS

1. FUNCIÓN

Este documento define la estructura de datos que utiliza el sistema para representar una oportunidad SEO y, cuando corresponde, la landing asociada.

Es el esquema común entre:

- investigación;
- matrices;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques;
- inteligencia artificial;
- N8N;
- validación;
- publicación.

Los documentos pueden definir reglas adicionales, pero no deben utilizar estructuras o valores que contradigan este esquema.

---

2. PRINCIPIO FUNDAMENTAL

Cada oportunidad debe poder identificarse y procesarse de forma independiente.

Ejemplo:

OPP-0001
fontanero / Marbella

o:

OPP-0002
fontanero / desatascos / Marbella

Cada oportunidad debe conservar su propia información, decisión, arquitectura, contenido y trazabilidad.

---

3. IDENTIFICADOR

Campo:

opportunity_id

Tipo:

string

Obligatorio:

sí

Debe ser único.

Ejemplo:

OPP-0001

---

4. IDENTIDAD

La identidad define exactamente qué representa la oportunidad.

identidad
├── sector
├── servicio
├── subservicio
└── tipo_pagina

sector

Ejemplo:

servicios profesionales

servicio

Ejemplo:

fontanero

subservicio

Ejemplo:

desatascos

Puede ser:

null

cuando no exista subservicio.

tipo_pagina

Define qué tipo de página representa la oportunidad.

Ejemplos:

servicio_localidad
servicio_subservicio_localidad

---

5. LOCALIZACIÓN

localizacion
├── pais
├── comunidad_autonoma
├── provincia
├── municipio
├── localidad
└── zonas

Los campos territoriales deben proceder de datos válidos.

provincia

Ejemplo:

Málaga

municipio

Ejemplo:

Marbella

localidad

Puede utilizarse cuando sea necesario distinguir una localidad de un municipio.

Puede ser:

null

zonas

Lista de zonas confirmadas.

Ejemplo:

[
  "Nueva Andalucía",
  "San Pedro de Alcántara"
]

No deben incluirse zonas no confirmadas.

---

6. INTENCIÓN

intencion
├── tipo
├── confianza
└── evidencia

tipo

Ejemplos:

informacional
comercial
transaccional
navegacional
local
mixta

La taxonomía definitiva puede ampliarse, pero debe mantenerse estable.

confianza

Valor que representa la confianza en la clasificación.

Ejemplo:

alta
media
baja

evidencia

Referencia a la información que permite justificar la intención.

---

7. INVESTIGACIÓN

investigacion
├── fuentes
├── evidencias
├── demanda
├── competencia
├── tendencia
└── notas

fuentes

Lista de fuentes utilizadas.

Cada fuente debe conservar, cuando sea posible:

id
tipo
url
fecha
descripcion

evidencias

Información obtenida de las fuentes.

Debe diferenciarse entre:

dato confirmado
dato incierto
dato no disponible

demanda

Información relacionada con demanda de búsqueda.

Puede incluir:

keyword
volumen
tendencia
estacionalidad
fuente
fecha

Cuando no exista un dato:

null

No se debe inventar.

competencia

Información sobre competidores o resultados existentes.

tendencia

Información temporal relevante.

notas

Observaciones adicionales de investigación.

---

8. DECISIÓN SEO

Campo:

decision_seo

Valores permitidos:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

Estos son los únicos resultados oficiales del motor.

---

9. CREAR

Significa que la oportunidad justifica una landing independiente.

Cuando:

decision_seo = CREAR

puede continuar hacia arquitectura y construcción.

---

10. AGRUPAR

Significa que la intención existe, pero no justifica una página independiente.

Debe registrarse, cuando corresponda:

agrupacion
├── pagina_destino
└── motivo

No se genera una URL independiente.

---

11. INVESTIGAR

Significa que no existe suficiente información para tomar una decisión definitiva.

La oportunidad queda pendiente de investigación.

No se genera todavía una landing ni una URL definitiva.

---

12. NO CREAR

Significa que existe suficiente información para determinar que no debe existir una página independiente.

No se genera landing.

---

13. AGRUPACIÓN

Cuando:

decision_seo = AGRUPAR

puede utilizarse:

agrupacion
├── pagina_destino
├── url_destino
└── motivo

La URL de destino debe ser una URL existente o previamente determinada.

La IA no debe inventarla.

---

14. ARQUITECTURA

Solo debe existir una arquitectura definitiva cuando:

decision_seo = CREAR

Estructura:

arquitectura
├── tipo_pagina
├── url
├── url_tipo
├── canonical
├── parent_url
└── profundidad

---

15. TIPO DE PÁGINA

Ejemplos:

servicio_localidad
servicio_subservicio_localidad

La elección debe proceder de la arquitectura SEO y de URLs.

No de la IA.

---

16. URL

Campo:

arquitectura.url

Ejemplo:

/fontanero/marbella/

o:

/fontanero/desatascos/marbella/

La URL debe estar determinada antes de generar el contenido definitivo.

---

17. TIPO DE URL

Campo:

url_tipo

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

Puede ampliarse cuando la arquitectura del proyecto lo requiera.

---

18. CANONICAL

Campo:

canonical

Debe representar la URL canónica de la página.

La IA no debe inventarla.

---

19. PÁGINA PADRE

Campo:

parent_url

Representa la página jerárquicamente superior cuando exista.

Ejemplo:

/fontanero/

para:

/fontanero/marbella/

---

20. PROFUNDIDAD

Campo:

profundidad

Representa el nivel de la página dentro de la arquitectura.

Ejemplo:

1
2
3

No debe confundirse con la longitud de la URL.

---

21. DATOS LOCALES

datos_locales
├── disponible
├── informacion
├── puntos_interes
├── zonas
└── fuentes

Si:

disponible = false

la IA no debe inventar información local.

---

22. COBERTURA

cobertura
├── confirmada
├── municipios
├── zonas
└── fuente

La cobertura solo puede afirmarse cuando esté respaldada.

---

23. DATOS COMERCIALES

datos_comerciales
├── empresa
├── telefono
├── whatsapp
├── email
├── direccion
├── horarios
├── precio
├── garantia
├── experiencia
└── certificaciones

Los campos pueden ser:

valor
null

"null" significa que el dato no está disponible.

Nunca debe interpretarse como permiso para inventarlo.

---

24. RESEÑAS

resenas
├── disponibles
├── fuente
├── cantidad
└── elementos

Los elementos pueden incluir:

autor
fecha
valoracion
texto
fuente

Las reseñas deben ser reales.

---

25. BLOQUES

bloques
├── seleccionados
└── configuracion

seleccionados

Lista de identificadores de bloques.

Ejemplo:

[
  "B01",
  "B02",
  "B03",
  "B07",
  "B09"
]

configuracion

Datos necesarios para cada bloque.

La selección procede de la arquitectura de landing y del sistema de bloques.

La IA no puede añadir bloques por iniciativa propia.

---

26. CONTENIDO

contenido
├── seo
├── bloques
└── estado

---

27. SEO

contenido.seo
├── title
├── meta_description
├── h1
└── slug

El "slug" debe coincidir con la arquitectura de URL.

---

28. CONTENIDO DE BLOQUES

Cada bloque debe identificarse:

bloque_id

y contener su contenido correspondiente.

Ejemplo conceptual:

{
  "bloque_id": "B01",
  "contenido": {}
}

---

29. ESTADO DE CONTENIDO

El contenido puede encontrarse en:

NO_GENERADO
GENERADO
REVISAR
VALIDADO

Este estado pertenece al contenido.

No sustituye a:

decision_seo

ni a:

estado_landing

---

30. IMÁGENES

imagenes
├── necesarias
└── elementos

Cada elemento puede contener:

tipo
descripcion
alt
fuente
url
estado

La IA puede proponer descripciones y textos alternativos.

No debe inventar URLs de imágenes existentes.

---

31. ENLAZADO INTERNO

enlazado
├── entradas
└── salidas

Cada enlace debe contener:

url
anchor
tipo

Las URLs deben proceder de la arquitectura existente.

---

32. DATOS ESTRUCTURADOS

schema
├── tipo
├── datos
└── estado

Los datos estructurados solo pueden utilizar información real disponible.

No deben generarse:

- valoraciones inventadas;
- precios inventados;
- direcciones inventadas;
- horarios inventados;
- empresas inventadas.

---

33. ESTADO DE OPORTUNIDAD

Campo:

estado_oportunidad

Valores:

DETECTADA
INVESTIGADA
EVALUADA
DECIDIDA
CERRADA

---

34. DETECTADA

La oportunidad ha sido identificada.

Todavía no se ha investigado suficientemente.

---

35. INVESTIGADA

La información necesaria para evaluarla ha sido recopilada.

---

36. EVALUADA

La oportunidad ha sido analizada según los criterios del motor.

---

37. DECIDIDA

El motor ha producido una decisión:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

---

38. CERRADA

La oportunidad ya no requiere ninguna acción dentro del flujo actual.

Puede corresponder a:

AGRUPAR

o:

NO CREAR

o a una oportunidad ya procesada completamente.

---

39. ESTADO DE LANDING

Solo debe existir cuando:

decision_seo = CREAR

Valores:

NO_INICIADA
DATOS_PREPARADOS
ARQUITECTURA_PREPARADA
BLOQUES_SELECCIONADOS
CONTENIDO_GENERADO
VALIDACION_PENDIENTE
VALIDADA
PUBLICADA
RECHAZADA
REVISAR

---

40. NO_INICIADA

La oportunidad ha sido marcada para crear una landing, pero todavía no ha comenzado su construcción.

---

41. DATOS_PREPARADOS

Los datos necesarios para la construcción han sido preparados.

---

42. ARQUITECTURA_PREPARADA

Se han determinado:

- tipo de página;
- URL;
- canonical;
- jerarquía;
- página padre cuando corresponda.

---

43. BLOQUES_SELECCIONADOS

Se han determinado los bloques que formarán la landing.

---

44. CONTENIDO_GENERADO

La IA ha generado el contenido.

Todavía puede estar pendiente de validación.

---

45. VALIDACION_PENDIENTE

El contenido está generado pero todavía no ha superado la validación.

---

46. VALIDADA

La landing ha superado los controles obligatorios.

---

47. PUBLICADA

La landing ha sido publicada.

Debe conservarse:

url_publicada
fecha_publicacion
version

---

48. RECHAZADA

La landing no puede publicarse en su estado actual.

Debe existir una explicación.

---

49. REVISAR

La landing necesita intervención.

Ejemplos:

- dato contradictorio;
- URL incorrecta;
- bloque incompleto;
- contenido problemático;
- error de validación;
- problema técnico.

"REVISAR" no modifica automáticamente "decision_seo".

---

50. VALIDACIÓN

validacion
├── resultado
├── fecha
├── reglas
├── errores
└── observaciones

---

51. RESULTADO DE VALIDACIÓN

Valores:

APROBADA
RECHAZADA
REVISAR

---

52. ERRORES

Cada error debe contener:

codigo
elemento
descripcion
gravedad

Ejemplo:

{
  "codigo": "DATA001",
  "elemento": "telefono",
  "descripcion": "El CTA requiere teléfono pero no existe un teléfono validado.",
  "gravedad": "alta"
}

---

53. INCIDENCIAS

incidencias
├── codigo
├── elemento
├── descripcion
├── gravedad
└── estado

Estados:

ABIERTA
EN_REVISION
RESUELTA
DESCARTADA

---

54. TRAZABILIDAD

trazabilidad
├── version_schema
├── version_motor
├── version_prompt
├── fecha_creacion
├── fecha_actualizacion
└── historial

---

55. VERSION_SCHEMA

Indica la versión del esquema utilizada.

Ejemplo:

1.0

---

56. VERSION_MOTOR

Indica qué versión del motor tomó la decisión.

Ejemplo:

1.0

Esto permite saber por qué una oportunidad fue clasificada de una determinada manera.

---

57. VERSION_PROMPT

Indica qué versión del prompt utilizó la IA.

Ejemplo:

1.0

---

58. FECHAS

Debe conservarse:

fecha_creacion
fecha_actualizacion

en formato consistente.

---

59. HISTORIAL

Los cambios importantes deben quedar registrados.

Ejemplo:

{
  "fecha": "2026-08-23",
  "campo": "decision_seo",
  "anterior": "INVESTIGAR",
  "nuevo": "CREAR",
  "motivo": "Nueva evidencia disponible"
}

---

60. REGLA DE NO INVENCIÓN

Cuando un dato no esté disponible:

null

Debe utilizarse "null" en lugar de:

- inventar;
- estimar;
- suponer;
- copiar de otra oportunidad;
- completar mediante conocimiento no respaldado.

---

61. REGLA DE IDENTIDAD

Los siguientes campos deben ser coherentes entre sí:

servicio
subservicio
municipio
provincia
tipo_pagina
url

Si existe una contradicción, debe producirse una incidencia.

---

62. REGLA DE URL

La URL se determina después de:

decision_seo = CREAR

La IA recibe la URL ya determinada.

La IA no debe crear una URL alternativa.

---

63. REGLA DE BLOQUES

La IA recibe los bloques autorizados.

No puede:

- crear bloques nuevos;
- eliminar bloques obligatorios;
- cambiar el orden;
- modificar las condiciones de aplicación.

Salvo que el flujo explícitamente lo permita.

---

64. REGLA DE IA

La IA puede modificar:

- redacción;
- estructura interna del contenido de cada bloque;
- títulos;
- textos;
- FAQ;
- CTA textual;

siempre dentro de las reglas recibidas.

La IA no puede modificar:

decision_seo
tipo_pagina
url
servicio
subservicio
municipio
provincia
bloques_autorizados

---

65. REGLA DE N8N

N8N utiliza este esquema como contrato entre los diferentes componentes.

Conceptualmente:

INVESTIGACIÓN
↓
DATOS
↓
MOTOR
↓
DECISIÓN SEO
↓
ARQUITECTURA
↓
URL
↓
BLOQUES
↓
IA
↓
CONTENIDO
↓
VALIDACIÓN
↓
WORDPRESS

---

66. DECISIONES Y ESTADOS

Debe mantenerse siempre la siguiente separación:

decision_seo
CREAR / AGRUPAR / INVESTIGAR / NO CREAR

estado_oportunidad
DETECTADA / INVESTIGADA / EVALUADA / DECIDIDA / CERRADA

estado_landing
NO_INICIADA / DATOS_PREPARADOS / ARQUITECTURA_PREPARADA /
BLOQUES_SELECCIONADOS / CONTENIDO_GENERADO /
VALIDACION_PENDIENTE / VALIDADA / PUBLICADA /
RECHAZADA / REVISAR

validacion.resultado
APROBADA / RECHAZADA / REVISAR

---

67. EJEMPLO COMPLETO

{
  "opportunity_id": "OPP-0001",

  "identidad": {
    "sector": "fontanería",
    "servicio": "fontanero",
    "subservicio": "desatascos",
    "tipo_pagina": "servicio_subservicio_localidad"
  },

  "localizacion": {
    "pais": "España",
    "comunidad_autonoma": "Andalucía",
    "provincia": "Málaga",
    "municipio": "Marbella",
    "localidad": null,
    "zonas": []
  },

  "intencion": {
    "tipo": "comercial",
    "confianza": "alta",
    "evidencia": []
  },

  "decision_seo": "CREAR",

  "arquitectura": {
    "tipo_pagina": "servicio_subservicio_localidad",
    "url": "/fontanero/desatascos/marbella/",
    "url_tipo": "servicio_subservicio_localidad",
    "canonical": "/fontanero/desatascos/marbella/",
    "parent_url": "/fontanero/",
    "profundidad": 3
  },

  "investigacion": {
    "fuentes": [],
    "evidencias": [],
    "demanda": null,
    "competencia": null,
    "tendencia": null,
    "notas": []
  },

  "datos_locales": {
    "disponible": false,
    "informacion": [],
    "puntos_interes": [],
    "zonas": [],
    "fuentes": []
  },

  "cobertura": {
    "confirmada": true,
    "municipios": ["Marbella"],
    "zonas": [],
    "fuente": []
  },

  "datos_comerciales": {
    "empresa": null,
    "telefono": null,
    "whatsapp": null,
    "email": null,
    "direccion": null,
    "horarios": null,
    "precio": null,
    "garantia": null,
    "experiencia": null,
    "certificaciones": []
  },

  "resenas": {
    "disponibles": false,
    "fuente": null,
    "cantidad": 0,
    "elementos": []
  },

  "bloques": {
    "seleccionados": [
      "B01",
      "B02",
      "B03"
    ],
    "configuracion": {}
  },

  "contenido": {
    "seo": {
      "title": null,
      "meta_description": null,
      "h1": null,
      "slug": "fontanero/desatascos/marbella"
    },
    "bloques": [],
    "estado": "NO_GENERADO"
  },

  "imagenes": {
    "necesarias": [],
    "elementos": []
  },

  "enlazado": {
    "entradas": [],
    "salidas": []
  },

  "schema": {
    "tipo": null,
    "datos": {},
    "estado": "NO_GENERADO"
  },

  "estado_oportunidad": "DECIDIDA",

  "estado_landing": "NO_INICIADA",

  "validacion": {
    "resultado": null,
    "fecha": null,
    "reglas": [],
    "errores": [],
    "observaciones": []
  },

  "incidencias": [],

  "trazabilidad": {
    "version_schema": "1.0",
    "version_motor": "1.0",
    "version_prompt": null,
    "fecha_creacion": null,
    "fecha_actualizacion": null,
    "historial": []
  }
}

---

68. REGLA MULTISERVICIO

Este esquema debe poder utilizarse para cualquier servicio del proyecto.

Ejemplos:

fontanero
electricista
carpintero
pintor
jardinero
abogado
reformas

No debe crearse un esquema diferente para cada servicio.

Las diferencias específicas deben incorporarse mediante:

- datos sectoriales;
- reglas sectoriales;
- bloques específicos;
- criterios específicos;
- fuentes específicas.

---

69. ESCALABILIDAD

El mismo esquema debe poder representar:

1 oportunidad
5 oportunidades
100 oportunidades
1.000 oportunidades
10.000 oportunidades

sin cambiar su estructura fundamental.

---

70. RELACIÓN CON LA ARQUITECTURA DE URLs

La arquitectura de URLs utiliza este esquema para determinar:

tipo_pagina
url_tipo
url
parent_url
profundidad

Pero la decisión de crear la página siempre procede previamente del motor.

---

71. RELACIÓN CON LA ARQUITECTURA DE LANDING

La arquitectura de landing utiliza:

identidad
intencion
datos
bloques

para determinar la composición de la página.

---

72. RELACIÓN CON LA IA

La IA recibe:

identidad
localizacion
intencion
decision_seo
arquitectura
datos
bloques
restricciones

y devuelve:

contenido
imagenes
enlazado
schema
incidencias

sin modificar las decisiones estructurales.

---

73. RELACIÓN CON N8N

N8N utilizará el esquema como contrato de datos entre:

fuentes
↓
investigación
↓
motor
↓
arquitectura
↓
IA
↓
validación
↓
WordPress

---

74. REGLA DE ORO

El sistema debe distinguir siempre:

QUÉ ES LA OPORTUNIDAD

QUÉ DECIDIÓ EL MOTOR

DÓNDE ESTÁ LA OPORTUNIDAD EN EL PROCESO

QUÉ LANDING SE ESTÁ CONSTRUYENDO

QUÉ HA DEVUELTO LA IA

SI LA LANDING HA SIDO VALIDADA

QUÉ SE HA PUBLICADO

No se deben mezclar estos conceptos.

---

75. ESTADO DEL DOCUMENTO

CONSOLIDADO

Este esquema debe considerarse el contrato de datos común del proyecto.

Cualquier documento posterior que necesite nuevos campos debe:

1. justificar el campo;
2. mantener la nomenclatura existente;
3. evitar duplicar información;
4. mantener la separación entre decisión, estados y validación;
5. actualizar este documento si el nuevo campo pasa a formar parte del modelo común.
