ESQUEMA DE DATOS

1. FUNCIÓN

Este documento transforma el modelo conceptual definido en "modelo-datos.md" en un esquema estructurado preparado para su futura implementación en N8N, IA, almacenamiento y WordPress.

Este documento define:

- campos;
- tipos;
- obligatoriedad;
- valores permitidos;
- relaciones;
- dependencias;
- reglas de validación.

No define la estrategia SEO.

No decide qué landing debe existir.

No sustituye al motor de decisión.

Su función es garantizar que todos los componentes utilicen una estructura de datos común.

---

2. PRINCIPIO

Una oportunidad debe poder viajar por todo el sistema sin perder información.

La misma entidad debe poder pasar por:

INVESTIGACIÓN
↓
MATRICES
↓
MOTOR
↓
DECISIÓN
↓
URL
↓
DATOS
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

sin cambiar su significado.

---

3. IDENTIFICADOR PRINCIPAL

opportunity_id

Tipo

"string"

Obligatorio

Sí.

Ejemplo

OPP-0001

Regla

Debe ser único.

No debe reutilizarse para otra oportunidad.

---

4. IDENTIDAD

sector

Tipo:

"string"

Obligatorio:

Sí.

Ejemplo:

servicios

---

servicio

Tipo:

"string"

Obligatorio:

Sí.

Ejemplo:

fontanero

---

subservicio

Tipo:

"string | null"

Obligatorio:

No.

Ejemplo:

desatascos

Si no existe:

null

---

5. LOCALIZACIÓN

pais

Tipo:

"string"

Obligatorio:

Sí.

Ejemplo:

España

---

comunidad_autonoma

Tipo:

"string"

Obligatorio:

Cuando esté disponible.

Ejemplo:

Andalucía

---

provincia

Tipo:

"string"

Obligatorio:

Sí para una landing local provincial.

Ejemplo:

Málaga

---

municipio

Tipo:

"string"

Obligatorio:

Sí para landing municipal.

Ejemplo:

Marbella

---

localidad

Tipo:

"string | null"

Obligatorio:

No.

Se utilizará cuando la oportunidad corresponda a una localidad diferente del municipio principal.

---

6. INTENCIÓN

intencion

Tipo:

"enum"

Valores permitidos:

comercial
transaccional
informacional
navegacional
mixta

Obligatorio:

Sí.

Regla

La intención debe proceder de la investigación y del análisis de la oportunidad.

La IA no puede modificarla.

---

7. DECISIÓN

decision

Tipo:

"enum"

Valores:

CREAR
NO_CREAR
REVISAR

Obligatorio:

Sí.

Regla crítica

Si:

decision = NO_CREAR

no puede generarse una landing.

Si:

decision = REVISAR

no puede publicarse automáticamente.

---

8. TIPO DE PÁGINA

tipo_pagina

Tipo:

"enum"

Valores iniciales:

landing_servicio_localidad
landing_servicio_subservicio_localidad
pagina_servicio
pagina_subservicio
pagina_localidad
otra

Obligatorio:

Sí cuando la decisión sea "CREAR".

Regla

El tipo de página debe ser coherente con la arquitectura SEO y la URL.

---

9. URL

url

Tipo:

"string"

Obligatorio:

Sí cuando:

decision = CREAR

Ejemplo:

/fontanero/desatascos/marbella/

---

url_tipo

Tipo:

"enum"

Valores:

servicio_localidad
servicio_subservicio_localidad
otra

---

canonical

Tipo:

"string"

Obligatorio:

Sí antes de publicación.

---

10. DATOS SEO

keywords

Tipo:

"array[string]"

Obligatorio:

No.

Contiene las consultas o términos relevantes detectados durante la investigación.

---

seo_title

Tipo:

"string"

Obligatorio:

Sí antes de publicación.

---

meta_description

Tipo:

"string"

Obligatorio:

Sí antes de publicación.

---

h1

Tipo:

"string"

Obligatorio:

Sí antes de publicación.

---

headings

Tipo:

"object"

Estructura:

h2: array[string]
h3: array[string]

---

11. INVESTIGACIÓN

fuentes

Tipo:

"array[object]"

Cada fuente puede contener:

id
tipo
url
nombre
fecha
fiabilidad

---

evidencias

Tipo:

"array[object]"

Cada evidencia debe contener:

id
tipo
fuente_id
dato
fecha
confianza

---

demanda

Tipo:

"object | null"

Puede contener:

nivel
dato
fuente
fecha

---

volumen

Tipo:

"number | null"

Cuando exista un dato cuantitativo fiable.

---

competencia

Tipo:

"object | null"

Puede contener:

nivel
observaciones
fuente

---

tendencia

Tipo:

"object | null"

Puede contener:

direccion
dato
periodo
fuente

---

12. CONFIANZA

confianza_datos

Tipo:

"enum"

Valores:

alta
media
baja
desconocida

Regla

Una confianza baja no autoriza a la IA a completar información mediante imaginación.

---

13. INFORMACIÓN LOCAL

informacion_local

Tipo:

"object"

Puede contener:

descripcion
caracteristicas
contexto_residencial
contexto_turistico
tipos_vivienda
necesidades
otros

Todos los campos son opcionales.

Solo deben rellenarse cuando exista información respaldada.

---

14. ZONAS

zonas

Tipo:

"array[object]"

Cada zona puede contener:

nombre
tipo
confirmada
fuente

Ejemplo:

[
  {
    "nombre": "Zona X",
    "tipo": "urbanización",
    "confirmada": true,
    "fuente": "E001"
  }
]

---

15. COBERTURA

cobertura

Tipo:

"object"

Campos:

municipio_principal
zonas
municipios_relacionados
cobertura_confirmada

Regla

"cobertura_confirmada" debe ser "true" antes de presentar cobertura como hecho.

---

16. DATOS COMERCIALES

datos_comerciales

Tipo:

"object"

Puede contener:

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

---

17. FUENTE DE DATOS COMERCIALES

Cada dato comercial importante debe poder rastrearse.

Estructura conceptual:

dato
fuente
fecha
estado

Estado:

validado
pendiente
caducado

Regla

Los datos caducados no deben utilizarse automáticamente.

---

18. CONFIANZA

confianza

Tipo:

"object"

Puede contener:

experiencia
certificaciones
garantias
reseñas
casos
acreditaciones

Cada elemento debe poder relacionarse con una fuente.

---

19. RESEÑAS

resenas

Tipo:

"array[object]"

Campos:

fuente
autor
contenido
fecha
rating
autorizacion

Regla

Nunca crear reseñas ficticias.

---

20. SERVICIOS RELACIONADOS

servicios_relacionados

Tipo:

"array[object]"

Campos:

servicio
url
relacion
validada

Solo pueden utilizarse enlaces con:

validada = true

---

21. LOCALIDADES RELACIONADAS

localidades_relacionadas

Tipo:

"array[object]"

Campos:

localidad
provincia
url
relacion
validada

---

22. BLOQUES

bloques

Tipo:

"array[object]"

Cada elemento:

id
tipo
obligatorio
seleccionado
motivo
datos_requeridos

Ejemplo:

[
  {
    "id": "B03",
    "tipo": "hero",
    "obligatorio": true,
    "seleccionado": true,
    "motivo": "bloque obligatorio",
    "datos_requeridos": [
      "servicio",
      "subservicio",
      "municipio",
      "intencion"
    ]
  }
]

---

23. CONTENIDO

contenido

Tipo:

"object"

El contenido se almacena por bloques.

Estructura conceptual:

hero
contenido_principal
subservicio
problemas
informacion_local
cobertura
proceso
confianza
servicios_relacionados
faq
cta
footer

No todos los objetos deben existir.

Si un bloque se omite:

null

o se elimina según la implementación.

---

24. HERO

contenido.hero

Campos:

h1
subtitulo
cta

---

25. CONTENIDO PRINCIPAL

contenido.contenido_principal

Campos:

titulo
texto

---

26. PROBLEMAS

contenido.problemas

Tipo:

"object | null"

Campos:

titulo
introduccion
elementos

---

27. FAQ

contenido.faq

Tipo:

"object | null"

Campos:

titulo
preguntas

Cada pregunta:

pregunta
respuesta

---

28. CTA

contenido.cta

Tipo:

"object"

Campos:

tipo
titulo
texto
destino

---

29. IMÁGENES

imagenes

Tipo:

"array[object]"

Campos:

url
alt
tipo
fuente
licencia

Regla

No se deben inventar URLs de imágenes.

---

30. DATOS ESTRUCTURADOS

schema

Tipo:

"object | null"

Campos:

tipo
datos
validado

Solo se utilizarán schemas apropiados y respaldados por datos reales.

---

31. RESTRICCIONES

restricciones

Tipo:

"array[string]"

Ejemplos:

no_inventar_precios
no_inventar_testimonios
no_afirmar_cobertura_no_confirmada
no_inventar_horarios

Las restricciones son obligatorias.

---

32. REGLAS DE CONTENIDO

reglas_contenido

Tipo:

"object"

Campos posibles:

tono
audiencia
nivel_tecnico
longitud
palabras_prohibidas
afirmaciones_prohibidas
elementos_obligatorios

---

33. ESTADO DE LA OPORTUNIDAD

estado_oportunidad

Tipo:

"enum"

Valores:

detectada
investigada
evaluada
CREAR
NO_CREAR
REVISAR

---

34. ESTADO DE LA LANDING

estado_landing

Tipo:

"enum"

Valores:

no_iniciada
datos_preparados
bloques_seleccionados
contenido_generado
validacion_pendiente
validada
publicada
rechazada

---

35. VERSION

version

Tipo:

"string"

Ejemplo:

1.0

---

36. TRAZABILIDAD

trazabilidad

Tipo:

"object"

Campos:

opportunity_id
fuentes
fecha_deteccion
fecha_investigacion
fecha_decision
fecha_generacion
fecha_validacion
fecha_publicacion
fecha_actualizacion

---

37. VALIDACIÓN

validacion

Tipo:

"object"

Campos:

identidad
url
seo
datos
bloques
contenido
enlaces
comercial
resultado
errores
fecha

Cada área puede tener:

pendiente
ok
error

---

38. RESULTADO DE VALIDACIÓN

validacion.resultado

Valores:

APROBADA
RECHAZADA
REVISAR

Una landing solo puede publicarse automáticamente cuando:

resultado = APROBADA

---

39. ERRORES

errores

Tipo:

"array[object]"

Campos:

codigo
elemento
descripcion
gravedad
solucion

Gravedad:

critica
alta
media
baja

---

40. REGLAS DE CONSISTENCIA

Antes de generar contenido se comprobará:

servicio ↔ subservicio
municipio ↔ provincia
identidad ↔ URL
decision ↔ estado_landing
bloques ↔ datos

---

41. REGLA DE GENERACIÓN

Solo puede iniciarse la generación cuando:

decision = CREAR

y:

url != null

y:

servicio != null

y:

municipio != null

cuando el tipo de página sea municipal.

---

42. REGLA DE BLOQUES

Un bloque puede seleccionarse si:

obligatorio = true

o si:

condiciones = cumplidas

y:

datos_requeridos = disponibles

Si los datos requeridos no existen:

seleccionado = false

salvo que el bloque disponga de un fallback explícitamente permitido.

---

43. REGLA DE PUBLICACIÓN

Una landing solo puede pasar a publicación si:

decision = CREAR

y:

estado_landing = validada

y:

validacion.resultado = APROBADA

---

44. REGLA DE NO INVENCIÓN

La ausencia de un campo nunca debe provocar la creación automática de un dato.

Ejemplo:

telefono = null

no permite generar:

telefono = "600000000"

La salida correcta es:

telefono = null

y el bloque que lo necesite deberá omitirse o pasar a revisión.

---

45. REGLA DE SEPARACIÓN

Debe mantenerse separada la información:

DATOS

de:

INSTRUCCIONES

y de:

CONTENIDO GENERADO

Esto evita que la IA confunda una afirmación fuente con una instrucción.

---

46. ESTRUCTURA MAESTRA

La estructura completa de una oportunidad será conceptualmente:

{
  opportunity_id,

  identidad: {
    sector,
    servicio,
    subservicio
  },

  localizacion: {
    pais,
    comunidad_autonoma,
    provincia,
    municipio,
    localidad
  },

  estrategia: {
    intencion,
    decision,
    tipo_pagina
  },

  seo: {
    url,
    url_tipo,
    canonical,
    keywords,
    seo_title,
    meta_description,
    h1,
    headings
  },

  investigacion: {
    fuentes,
    evidencias,
    demanda,
    volumen,
    competencia,
    tendencia
  },

  local: {
    informacion_local,
    zonas,
    cobertura
  },

  comercial: {
    datos_comerciales,
    confianza,
    resenas
  },

  arquitectura: {
    bloques,
    servicios_relacionados,
    localidades_relacionadas
  },

  contenido: {
    hero,
    contenido_principal,
    problemas,
    faq,
    cta
  },

  restricciones,

  reglas_contenido,

  estado_oportunidad,

  estado_landing,

  version,

  trazabilidad,

  validacion,

  errores
}

---

47. EJEMPLO COMPLETO

{
  "opportunity_id": "OPP-0001",

  "identidad": {
    "sector": "servicios",
    "servicio": "fontanero",
    "subservicio": "desatascos"
  },

  "localizacion": {
    "pais": "España",
    "comunidad_autonoma": "Andalucía",
    "provincia": "Málaga",
    "municipio": "Marbella",
    "localidad": null
  },

  "estrategia": {
    "intencion": "comercial",
    "decision": "CREAR",
    "tipo_pagina": "landing_servicio_subservicio_localidad"
  },

  "seo": {
    "url": "/fontanero/desatascos/marbella/",
    "url_tipo": "servicio_subservicio_localidad",
    "canonical": null,
    "keywords": [],
    "seo_title": null,
    "meta_description": null,
    "h1": null,
    "headings": null
  },

  "investigacion": {
    "fuentes": [],
    "evidencias": [],
    "demanda": null,
    "volumen": null,
    "competencia": null,
    "tendencia": null
  },

  "local": {
    "informacion_local": null,
    "zonas": [],
    "cobertura": null
  },

  "comercial": {
    "datos_comerciales": {},
    "confianza": {},
    "resenas": []
  },

  "arquitectura": {
    "bloques": [],
    "servicios_relacionados": [],
    "localidades_relacionadas": []
  },

  "contenido": {},

  "restricciones": [
    "no_inventar_precios",
    "no_inventar_testimonios",
    "no_afirmar_cobertura_no_confirmada"
  ],

  "reglas_contenido": {},

  "estado_oportunidad": "CREAR",

  "estado_landing": "no_iniciada",

  "version": "1.0",

  "trazabilidad": {},

  "validacion": {},

  "errores": []
}

---

48. COMPATIBILIDAD MULTISERVICIO

Este esquema debe poder utilizarse para cualquier servicio.

Ejemplo:

fontanero

puede utilizar:

servicio
subservicio
municipio
cobertura
problemas

Mientras:

abogado

puede añadir:

datos_sectoriales

con:

especialidad
tipo_procedimiento
jurisdiccion

El modelo general no debe cambiar.

---

49. DATOS SECTORIALES

datos_sectoriales

Tipo:

"object"

Este campo permite añadir información específica de un sector sin modificar el modelo general.

Ejemplo:

datos_sectoriales: {
  especialidad: "derecho laboral",
  tipo_procedimiento: "despido"
}

---

50. REGLA DE EXTENSIÓN

Antes de añadir un campo al modelo general se comprobará si:

1. Es universal.
2. Es reutilizable.
3. Es específico de un sector.
4. Debe pertenecer a otro documento.

Si es específico de un sector, deberá utilizar:

datos_sectoriales

---

51. RESPONSABILIDADES

Investigación

Produce fuentes y evidencias.

Matrices

Producen datos comparativos.

Motor

Produce la decisión.

Arquitectura SEO

Define la estructura estratégica.

Arquitectura de URLs

Define la URL.

Arquitectura de landing

Define la estructura de la página.

Sistema de bloques

Define los bloques.

Modelo de datos

Define qué información debe existir.

Esquema de datos

Define cómo se estructura técnicamente.

IA

Genera el contenido.

N8N

Orquesta el proceso.

Validación

Comprueba el resultado.

WordPress

Publica.

---

52. REGLA DE RESPONSABILIDAD

Ningún componente debe asumir las funciones de otro.

Especialmente:

IA ≠ motor
IA ≠ investigación
IA ≠ arquitectura de URLs
IA ≠ validación

La IA trabaja con información previamente preparada.

---

53. OBJETIVO FINAL

El esquema debe permitir que N8N reciba una oportunidad estructurada y pueda ejecutar:

1. comprobar decisión
2. comprobar URL
3. comprobar datos
4. seleccionar bloques
5. preparar contexto
6. enviar a IA
7. recibir contenido
8. validar
9. preparar WordPress
10. publicar

sin necesidad de interpretar manualmente la documentación.

---

54. ESTADO

ESQUEMA DE DATOS DEFINIDO — PENDIENTE DE IMPLEMENTACIÓN TÉCNICA

Este documento ya establece la estructura necesaria para que posteriormente podamos convertirla en:

- JSON;
- Google Sheets;
- variables de N8N;
- objetos para prompts;
- campos de WordPress.

La implementación concreta se realizará cuando se diseñe el flujo técnico.

---

55. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se crea el esquema técnico de datos.

Se establece:

- estructura de oportunidad;
- identidad;
- localización;
- intención;
- decisión;
- tipo de página;
- URL;
- SEO;
- investigación;
- evidencias;
- información local;
- datos comerciales;
- bloques;
- contenido;
- restricciones;
- validación;
- estados;
- trazabilidad;
- versionado;
- extensiones sectoriales.

Se establece que el esquema será el contrato técnico común entre la documentación, N8N, IA y WordPress.

Siguiente fase:

diseñar el sistema de prompts y la especificación que recibirá la IA para construir cada landing.
