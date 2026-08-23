# ESQUEMA DE DATOS

## 1. FUNCIÓN

Este documento define el modelo de datos canónico del sistema.

Es la estructura común entre:

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

Los demás documentos pueden definir reglas específicas, pero no deben crear estructuras o valores que contradigan este esquema.

---

## 2. PRINCIPIO FUNDAMENTAL

Cada oportunidad debe poder identificarse, investigarse, decidirse, construirse y validarse de forma independiente.

Ejemplos:

OPP-0001
fontanero / Marbella

OPP-0002
fontanero / desatascos / Marbella

Una oportunidad conserva su propia información, decisión, arquitectura, contenido y trazabilidad.

---

# 3. IDENTIFICACIÓN

## opportunity_id

Tipo:

string

Obligatorio:

sí

Debe ser único.

Ejemplo:

OPP-0001

---

# 4. IDENTIDAD

Estructura:

identidad
├── sector
├── servicio
├── subservicio
└── tipo_pagina

### sector

Sector profesional.

Ejemplo:

servicios profesionales

### servicio

Servicio principal.

Ejemplo:

fontanero

### subservicio

Servicio específico.

Ejemplo:

desatascos

Puede ser:

null

cuando no exista.

### tipo_pagina

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

La IA no decide este valor.

---

# 5. LOCALIZACIÓN

Estructura:

localizacion
├── pais
├── comunidad_autonoma
├── provincia
├── municipio
├── localidad
└── zonas

Los datos territoriales deben proceder de información válida.

### municipio

Ejemplo:

Marbella

### provincia

Ejemplo:

Málaga

### localidad

Puede ser null cuando no sea necesaria.

### zonas

Lista de zonas confirmadas.

No se deben inventar zonas.

---

# 6. INTENCIÓN

Estructura:

intencion
├── tipo
├── confianza
└── evidencia

### tipo

Valores iniciales:

informacional
comercial
transaccional
navegacional
local
mixta

### confianza

Valores:

alta
media
baja

### evidencia

Referencia a la información que justifica la clasificación.

---

# 7. INVESTIGACIÓN

Estructura:

investigacion
├── fuentes
├── evidencias
├── demanda
├── competencia
├── tendencia
└── notas

## fuentes

Cada fuente puede contener:

- id
- tipo
- url
- fecha
- descripcion

## evidencias

Debe diferenciar:

- confirmado;
- incierto;
- no_disponible.

## demanda

Puede contener:

- keyword;
- volumen;
- tendencia;
- estacionalidad;
- fuente;
- fecha.

Los datos desconocidos deben ser null.

Nunca se inventan.

## competencia

Información sobre resultados, competidores y dificultad.

## tendencia

Información temporal relevante.

## notas

Observaciones adicionales.

---

# 8. DECISIÓN SEO

Campo:

decision_seo

Valores permitidos:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

Son los únicos resultados oficiales del motor.

---

# 9. CREAR

Significa que la oportunidad justifica una landing independiente.

Permite continuar hacia arquitectura y construcción.

---

# 10. AGRUPAR

Significa que la intención existe pero no justifica una página independiente.

Estructura:

agrupacion
├── pagina_destino
├── url_destino
└── motivo

No se genera una URL independiente.

La URL de destino debe existir o estar previamente autorizada.

---

# 11. INVESTIGAR

Significa que no existe información suficiente para tomar una decisión definitiva.

No se genera todavía una landing definitiva.

---

# 12. NO CREAR

Significa que existe información suficiente para determinar que no debe existir una página independiente.

No se genera landing.

---

# 13. ARQUITECTURA

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

# 14. TIPO DE PÁGINA

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

La elección procede de la arquitectura SEO.

La IA no puede modificarla.

---

# 15. URL

Campo:

arquitectura.url

Ejemplos:

/fontanero/marbella/

/fontanero/desatascos/marbella/

La URL debe estar determinada antes de generar contenido.

La IA nunca decide la URL.

---

# 16. TIPO DE URL

Campo:

arquitectura.url_tipo

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

---

# 17. CANONICAL

Campo:

arquitectura.canonical

Debe representar la URL canónica autorizada.

La IA no puede inventarlo ni modificarlo.

---

# 18. PÁGINA PADRE

Campo:

arquitectura.parent_url

Ejemplo:

/fontanero/

para:

/fontanero/marbella/

Puede ser null.

---

# 19. PROFUNDIDAD

Campo:

arquitectura.profundidad

Representa el nivel dentro de la arquitectura.

Ejemplos:

1
2
3

No representa la longitud de la URL.

---

# 20. DATOS LOCALES

Estructura:

datos_locales
├── disponible
├── informacion
├── puntos_interes
├── zonas
└── fuentes

Si:

disponible = false

no se debe generar contenido local específico.

---

# 21. COBERTURA

Estructura:

cobertura
├── confirmada
├── municipios
├── zonas
└── fuente

Solo se afirma cobertura cuando está respaldada.

---

# 22. DATOS COMERCIALES

Estructura:

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

Los campos pueden contener:

valor

o:

null

null significa dato no disponible.

Nunca significa permiso para inventarlo.

---

# 23. RESEÑAS

Estructura:

resenas
├── disponibles
├── fuente
├── cantidad
└── elementos

Cada elemento puede contener:

- autor;
- fecha;
- valoracion;
- texto;
- fuente.

Las reseñas deben ser reales.

---

# 24. BLOQUES

Estructura:

bloques
├── seleccionados
└── configuracion

Ejemplo:

[
  "B01",
  "B02",
  "B03",
  "B04",
  "B05",
  "B06"
]

La selección procede de la arquitectura de landing.

La IA no puede añadir bloques por iniciativa propia.

---

# 25. MAPA OFICIAL DE BLOQUES

Los identificadores oficiales son:

B01 = HEADER

B02 = NAVEGACIÓN

B03 = HERO

B04 = CONTENIDO PRINCIPAL

B05 = CTA PRINCIPAL

B06 = FOOTER

B07 = SUBSERVICIO

B08 = PROBLEMAS / NECESIDADES

B09 = INFORMACIÓN LOCAL

B10 = ZONAS / COBERTURA

B11 = PROCESO

B12 = ELEMENTOS DE CONFIANZA

B13 = DIFERENCIACIÓN

B14 = FAQ

B15 = SERVICIOS RELACIONADOS

B16 = LOCALIDADES RELACIONADAS

B17 = DATOS ESTRUCTURADOS

B18 = TESTIMONIOS

B19 = CASOS / EJEMPLOS

B20 = GALERÍA

B21 = PRECIO / TARIFAS

B22 = HORARIOS

B23 = MAPA / UBICACIÓN

Este mapa es vinculante.

---

# 26. CONFIGURACIÓN DE BLOQUES

Cada bloque puede disponer de configuración específica.

Ejemplo:

{
  "bloque_id": "B03",
  "enabled": true,
  "configuracion": {}
}

La configuración no puede contradecir:

- arquitectura;
- datos;
- restricciones;
- evidencias.

---

# 27. CONTENIDO

Estructura:

contenido
├── seo
├── bloques
└── estado

---

# 28. SEO DE CONTENIDO

Estructura:

contenido.seo
├── title
├── meta_description
├── h1
└── slug

El slug debe coincidir con la URL autorizada.

---

# 29. CONTENIDO DE BLOQUES

Cada bloque generado debe conservar:

bloque_id

type

enabled

data

Ejemplo:

{
  "bloque_id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {}
}

El type debe corresponder al identificador oficial.

---

# 30. TIPOS OFICIALES DE BLOQUE

B01 → header

B02 → navigation

B03 → hero

B04 → main_content

B05 → cta

B06 → footer

B07 → subservice

B08 → problems

B09 → local_context

B10 → coverage

B11 → process

B12 → trust

B13 → differentiation

B14 → faq

B15 → related_services

B16 → related_locations

B17 → structured_data

B18 → testimonials

B19 → cases

B20 → gallery

B21 → pricing

B22 → opening_hours

B23 → map

Un ID no puede utilizarse para otra función.

---

# 31. ESTADO DEL CONTENIDO

Valores:

NO_GENERADO
GENERADO
REVISAR
VALIDADO

Este estado pertenece exclusivamente al contenido.

No sustituye:

decision_seo

ni:

estado_landing

---

# 32. IMÁGENES

Estructura:

imagenes
├── necesarias
└── elementos

Cada elemento puede contener:

- tipo;
- descripcion;
- alt;
- fuente;
- url;
- estado.

La IA puede proponer descripciones y ALT.

No puede inventar URLs de imágenes.

---

# 33. ENLAZADO INTERNO

Estructura:

enlazado
├── entradas
└── salidas

Cada enlace contiene:

- url;
- anchor;
- tipo.

Las URLs deben proceder de la arquitectura existente.

---

# 34. DATOS ESTRUCTURADOS

Estructura:

schema
├── tipo
├── datos
└── estado

Solo puede utilizar información real disponible.

Nunca se inventan:

- valoraciones;
- precios;
- direcciones;
- horarios;
- empresas.

---

# 35. ESTADO DE OPORTUNIDAD

Campo:

estado_oportunidad

Valores:

DETECTADA
INVESTIGADA
EVALUADA
DECIDIDA
CERRADA

---

# 36. ESTADO DE LANDING

Solo existe cuando:

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

REVISAR es un estado operativo de landing.

No es una decisión SEO.

---

# 37. VALIDACIÓN

Estructura:

validacion
├── resultado
├── fecha
├── reglas
├── errores
└── observaciones

Valores de resultado:

APROBADA
RECHAZADA
REVISAR

---

# 38. ERRORES

Cada error contiene:

- codigo;
- elemento;
- descripcion;
- gravedad.

Ejemplo:

{
  "codigo": "DATA001",
  "elemento": "telefono",
  "descripcion": "No existe un teléfono validado.",
  "gravedad": "alta"
}

---

# 39. INCIDENCIAS

Estructura:

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

# 40. TRAZABILIDAD

Estructura:

trazabilidad
├── version_schema
├── version_motor
├── version_prompt
├── fecha_creacion
├── fecha_actualizacion
└── historial

---

# 41. VERSIONES

version_schema

Identifica la versión de este esquema.

Versión actual:

1.1

version_motor

Identifica la versión del motor de decisión.

version_prompt

Identifica la versión del prompt utilizado por la IA.

---

# 42. FECHAS

Debe conservarse:

fecha_creacion

fecha_actualizacion

en formato consistente.

---

# 43. HISTORIAL

Los cambios importantes deben conservarse.

Ejemplo:

{
  "fecha": "2026-08-23",
  "campo": "decision_seo",
  "anterior": "INVESTIGAR",
  "nuevo": "CREAR",
  "motivo": "Nueva evidencia disponible"
}

---

# 44. REGLA DE NO INVENCIÓN

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
- zonas;
- cobertura;
- testimonios;
- casos;
- imágenes;
- URLs.

Cuando un dato no existe:

null

o:

REVISAR

según corresponda.

---

# 45. REGLA DE IDENTIDAD

La identidad recibida debe conservarse exactamente.

Si:

servicio = fontanero

municipio = Marbella

no puede transformarse en otro servicio o municipio.

---

# 46. REGLA DE ARQUITECTURA

La arquitectura se determina antes de la generación de contenido.

La IA no decide:

- tipo de página;
- URL;
- canonical;
- parent_url;
- profundidad.

---

# 47. REGLA DE BLOQUES

La IA solo puede utilizar bloques incluidos en:

bloques.seleccionados

No puede añadir bloques nuevos.

---

# 48. REGLA DE DIFERENCIACIÓN

Una landing no se considera diferente simplemente por:

- cambiar la localidad;
- cambiar el título;
- cambiar sinónimos;
- cambiar el orden de párrafos;
- añadir palabras.

La diferenciación debe proceder de información, intención, servicio, contexto o evidencias realmente diferentes.

---

# 49. REGLA DE INFORMACIÓN LOCAL

El nombre de una localidad no constituye por sí mismo información local.

Si no existen datos locales suficientes:

- no inventar;
- no rellenar artificialmente;
- omitir el bloque cuando sea opcional;
- registrar la ausencia cuando sea relevante.

---

# 50. REGLA DE ENLACES

No se crean enlaces hacia URLs inexistentes o no autorizadas.

---

# 51. REGLA DE IA

La IA trabaja después de:

1. investigación;
2. evaluación;
3. decisión;
4. arquitectura;
5. selección de bloques;
6. preparación de datos.

La IA genera contenido.

No sustituye esas fases.

---

# 52. REGLA DE ESTADOS

Los estados tienen funciones diferentes:

decision_seo
→ decisión del motor.

estado_oportunidad
→ ciclo de vida de la oportunidad.

estado_landing
→ ciclo de construcción de la landing.

contenido.estado
→ estado del contenido.

validacion.resultado
→ resultado del control.

No deben utilizarse como equivalentes.

---

# 53. REGLA DE TRAZABILIDAD

Toda landing generada debe poder relacionarse con:

- oportunidad;
- investigación;
- decisión;
- arquitectura;
- bloques;
- versión del esquema;
- versión del motor;
- versión del prompt;
- fechas;
- validación.

---

# 54. EJEMPLO DE OPORTUNIDAD

Ejemplo conceptual:

{
  "opportunity_id": "OPP-0001",

  "identidad": {
    "sector": "servicios profesionales",
    "servicio": "fontanero",
    "subservicio": null,
    "tipo_pagina": "servicio_localidad"
  },

  "localizacion": {
    "pais": "España",
    "comunidad_autonoma": "Andalucía",
    "provincia": "Málaga",
    "municipio": "Marbella",
    "localidad": null,
    "zonas": []
  },

  "decision_seo": "INVESTIGAR",

  "arquitectura": null,

  "bloques": {
    "seleccionados": [],
    "configuracion": {}
  },

  "contenido": {
    "seo": null,
    "bloques": [],
    "estado": "NO_GENERADO"
  },

  "estado_oportunidad": "DECIDIDA",

  "estado_landing": null
}

Este ejemplo no implica que la oportunidad deba CREAR.

La decisión debe proceder del motor.

---

# 55. PRINCIPIO FINAL

El sistema debe seguir esta secuencia:

INVESTIGACIÓN

↓

DECISIÓN

↓

ARQUITECTURA

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

↓

PUBLICACIÓN

La IA nunca debe saltarse las capas anteriores.

La prioridad del sistema es:

1. veracidad;
2. trazabilidad;
3. coherencia;
4. utilidad;
5. escalabilidad.

---

# 56. CONTROL DE VERSIONES

Versión:

1.1

Fecha:

2026-08-23

Motivo:

Consolidación del modelo de datos canónico y alineación con:

- sistema de bloques;
- estados del sistema;
- arquitectura de landing;
- contrato IA → N8N.

Cambios principales:

- arquitectura agrupada bajo `arquitectura`;
- canonical y URL claramente separados de contenido;
- mapa oficial de bloques incorporado;
- separación estricta de estados;
- eliminación de ambigüedad entre decisión SEO y estado REVIEW;
- reglas explícitas de no invención;
- trazabilidad de versiones;
- estructura preparada para IA → N8N.
