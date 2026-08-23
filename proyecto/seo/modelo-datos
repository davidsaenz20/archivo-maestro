MODELO DE DATOS

1. FUNCIÓN

Este documento define la estructura de datos que utilizará el sistema para representar una oportunidad, una landing y todos los elementos necesarios para generarla, validarla y publicarla.

Es el contrato común entre:

- investigación;
- matrices;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques;
- IA;
- N8N;
- validación;
- WordPress.

Su objetivo es evitar que la información quede repartida de forma ambigua y que cada componente interprete los datos de una manera diferente.

---

2. PRINCIPIO FUNDAMENTAL

La IA no debe tener que descubrir qué página debe crear.

La decisión estratégica debe estar previamente determinada.

La IA recibe datos estructurados y genera contenido dentro de unas reglas.

El flujo es:

INVESTIGACIÓN
↓
OPORTUNIDAD
↓
MATRICES
↓
MOTOR DE DECISIÓN
↓
DECISIÓN
↓
URL
↓
MODELO DE DATOS
↓
BLOQUES
↓
IA
↓
VALIDACIÓN
↓
N8N / WORDPRESS

---

3. IDENTIFICACIÓN DE LA OPORTUNIDAD

Cada oportunidad tendrá un identificador único.

opportunity_id

Ejemplo:

OPP-0001

El identificador debe permanecer estable durante todo el proceso.

No debe cambiar aunque se modifique posteriormente algún dato secundario.

---

4. IDENTIDAD DE LA PÁGINA

La identidad mínima de una landing estará formada por:

sector
servicio
subservicio
localidad
provincia

Ejemplo:

sector = servicios
servicio = fontanero
subservicio = desatascos
localidad = Marbella
provincia = Málaga

No todas las páginas tendrán subservicio.

Cuando no exista:

subservicio = null

---

5. DATOS DE LOCALIZACIÓN

La localización debe estructurarse de forma independiente.

Campos:

pais
comunidad_autonoma
provincia
municipio
localidad

En el modelo SEO local, el municipio será el elemento territorial principal salvo que la investigación determine otra estructura.

Ejemplo:

pais = España
comunidad_autonoma = Andalucía
provincia = Málaga
municipio = Marbella

---

6. INTENCIÓN

Cada oportunidad debe tener una intención definida.

Campo:

intencion

Ejemplos:

comercial
transaccional
informacional
navegacional
mixta

Para las landings de captación de servicios, normalmente será comercial o transaccional.

La intención no debe ser inventada por la IA.

---

7. DECISIÓN DEL MOTOR

La decisión estratégica debe quedar registrada.

Campo:

decision

Valores principales:

CREAR
NO_CREAR
REVISAR

La IA no puede cambiar esta decisión.

Si:

decision = NO_CREAR

no debe generarse una landing.

Si:

decision = REVISAR

la oportunidad debe quedar fuera de la publicación automática.

---

8. URL

La URL debe estar determinada antes de la generación del contenido.

Campo:

url

Ejemplo:

/fontanero/desatascos/marbella/

La URL debe ser coherente con:

- servicio;
- subservicio;
- localidad;
- arquitectura SEO;
- arquitectura de URLs;
- decisión del motor.

La IA no debe modificarla.

---

9. TIPO DE URL

Campo:

url_tipo

Valores posibles:

servicio_localidad
servicio_subservicio_localidad

Ejemplos:

/fontanero/marbella/

/fontanero/desatascos/marbella/

La estructura final dependerá de las reglas definidas en "arquitectura-urls.md".

---

10. CANONICAL

Campo:

canonical

Por defecto deberá corresponder a la URL canónica de la propia página.

Ejemplo:

https://dominio.com/fontanero/desatascos/marbella/

Nunca se debe generar una canonical arbitraria.

---

11. DATOS DE INVESTIGACIÓN

Cada oportunidad debe conservar la información que justifica su existencia.

Campos:

fuentes
evidencias
keywords
volumen
competencia
tendencia
demanda
intencion_detectada

No todos los campos tendrán necesariamente datos.

La ausencia de un dato debe quedar registrada como ausencia y no convertirse en una estimación inventada.

---

12. EVIDENCIAS

Las evidencias deben poder rastrearse hasta su origen.

Estructura conceptual:

evidencias:
  - id
  - tipo
  - fuente
  - dato
  - fecha
  - confianza

Ejemplo:

evidencias:
  - id: E001
    tipo: demanda
    fuente: fuente-investigacion
    dato: "..."
    fecha: "2026-08-23"
    confianza: alta

---

13. CONFIANZA DE LOS DATOS

Cada dato relevante podrá tener un nivel de confianza.

Valores:

alta
media
baja
desconocida

La confianza no significa que la IA pueda inventar cuando sea baja.

Al contrario:

- alta → utilizar normalmente;
- media → utilizar con prudencia;
- baja → validar antes de utilizar cuando sea relevante;
- desconocida → no utilizar como hecho.

---

14. INFORMACIÓN LOCAL

Los datos locales se almacenarán separados de los datos generales del servicio.

Campos posibles:

informacion_local
zonas
barrios
urbanizaciones
caracteristicas_locales
contexto_residencial
contexto_turistico
tipos_de_vivienda
necesidades_locales

No todos los campos serán obligatorios.

Solo se utilizarán aquellos que tengan respaldo suficiente.

---

15. COBERTURA

La cobertura territorial tendrá una estructura propia.

cobertura:
  municipio_principal
  zonas
  municipios_relacionados
  cobertura_confirmada

Ejemplo:

cobertura:
  municipio_principal: Marbella
  zonas:
    - ...
  municipios_relacionados:
    - ...
  cobertura_confirmada: true

Nunca se deben añadir municipios únicamente para generar enlaces SEO.

---

16. DATOS COMERCIALES

Los datos comerciales deben mantenerse separados de los datos SEO.

Campos posibles:

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
servicios

Cada dato debe tener una fuente o estar marcado como autorizado.

Nunca debe asumirse que un dato comercial es verdadero simplemente porque aparece en otro contexto.

---

17. REGLA DE DATOS COMERCIALES

La IA no puede inventar:

- teléfonos;
- emails;
- direcciones;
- precios;
- horarios;
- garantías;
- certificaciones;
- años de experiencia;
- disponibilidad;
- nombres;
- testimonios.

Si un dato comercial no existe:

null

o debe omitirse.

---

18. DATOS DE CONFIANZA

Los elementos de confianza se almacenarán por separado.

Ejemplo:

confianza:
  experiencia
  certificaciones
  garantias
  reseñas
  casos
  acreditaciones

Cada elemento debe poder comprobarse.

---

19. RESEÑAS

Las reseñas deben distinguirse de otros datos.

Campos:

reseñas:
  fuente
  contenido
  autor
  fecha
  rating
  autorizacion

No se deben generar reseñas ficticias.

Si no existen reseñas válidas:

reseñas = null

---

20. SERVICIOS RELACIONADOS

Los servicios relacionados se almacenarán estructuradamente.

Ejemplo:

servicios_relacionados:
  - servicio
    url
    relacion

Solo podrán utilizarse URLs existentes o previamente validadas.

---

21. LOCALIDADES RELACIONADAS

Estructura:

localidades_relacionadas:
  - localidad
    provincia
    url
    relacion

La relación debe tener una justificación.

No se deben generar listas indiscriminadas.

---

22. BLOQUES

Cada landing tendrá una lista de bloques seleccionados.

Ejemplo:

bloques:
  - B01
  - B02
  - B03
  - B04
  - B07
  - B08
  - B09
  - B14
  - B05
  - B06

Los bloques se definen en:

"proyecto/seo/sistema-bloques.md"

La IA no debe inventar nuevos bloques fuera del sistema salvo que el flujo permita expresamente una revisión.

---

23. BLOQUES Y DATOS

Cada bloque debe indicar qué datos necesita.

Ejemplo:

B09 Información local
requiere:
  - informacion_local

Si esos datos no existen:

B09 = OMITIR

No se debe rellenar el bloque con información inventada.

---

24. CONTENIDO

El contenido generado para una landing debe conservar una estructura por bloques.

Ejemplo:

contenido:
  hero:
    h1
    subtitulo
    cta

  contenido_principal:
    titulo
    texto

  problemas:
    titulo
    elementos

  faq:
    preguntas

  cta_final:
    titulo
    texto
    accion

El formato técnico definitivo dependerá de la implementación.

---

25. H1

Campo:

h1

Debe ser coherente con:

- intención;
- servicio;
- subservicio;
- localidad.

Ejemplo:

Desatascos en Marbella

La IA puede redactarlo dentro de las reglas, pero no cambiar la identidad de la página.

---

26. TITLE

Campo:

seo_title

Debe representar la intención de la página.

No debe convertirse en una acumulación artificial de keywords.

---

27. META DESCRIPTION

Campo:

meta_description

Debe:

- representar la página;
- ser útil;
- ser coherente con el contenido;
- no contener afirmaciones no verificadas.

---

28. HEADINGS

La estructura de headings debe almacenarse de manera que pueda validarse.

Conceptualmente:

headings:
  h1
  h2
  h3

No se deben crear headings únicamente para introducir keywords.

---

29. FAQ

Las FAQ deben estructurarse.

Ejemplo:

faq:
  - pregunta
    respuesta

Las preguntas deben estar relacionadas con la intención.

Las respuestas deben basarse en información disponible.

---

30. CTA

Estructura:

cta:
  tipo
  texto
  destino

Ejemplo:

cta:
  tipo: whatsapp
  texto: Solicitar información
  destino: dato-validado

Nunca se debe inventar el destino.

---

31. ENLAZADO INTERNO

Cada enlace interno debe poder identificarse.

Estructura:

enlaces_internos:
  - anchor
    url
    destino
    motivo

Ejemplo:

enlaces_internos:
  - anchor: "servicios de fontanería"
    url: "/fontanero/marbella/"
    destino: servicio
    motivo: navegación

---

32. IMÁGENES

Las imágenes deben gestionarse como datos.

Campos posibles:

imagenes:
  - url
  - alt
  - tipo
  - fuente
  - licencia

No se deben inventar URLs de imágenes.

---

33. DATOS ESTRUCTURADOS

Los datos estructurados deben construirse únicamente a partir de datos válidos.

Campos conceptuales:

schema:
  tipo
  datos
  validado

No debe utilizarse información falsa para completar un schema.

---

34. RESTRICCIONES

Cada oportunidad puede tener restricciones específicas.

Campo:

restricciones

Ejemplos:

restricciones:
  - no_inventar_precios
  - no_inventar_testimonios
  - no_afirmar_cobertura_no_confirmada

Las restricciones tienen prioridad sobre la generación de contenido.

---

35. REGLAS DE CONTENIDO

Campo:

reglas_contenido

Puede incluir:

tono
longitud
nivel_tecnico
audiencia
palabras_prohibidas
afirmaciones_prohibidas
elementos_obligatorios

Las reglas generales del proyecto tendrán prioridad sobre instrucciones particulares de la IA.

---

36. ESTADO DE LA LANDING

El estado de una oportunidad y el estado de una landing son conceptos diferentes.

Estado de oportunidad

detectada
investigada
evaluada
CREAR
NO_CREAR
REVISAR

Estado de landing

no_iniciada
datos_preparados
bloques_seleccionados
contenido_generado
validacion_pendiente
validada
publicada
rechazada

No deben mezclarse ambos estados.

---

37. VERSIONADO

Cada landing debe poder tener una versión.

Campo:

version

Ejemplo:

1.0

Si se modifica el contenido de manera relevante:

1.1

El sistema debe poder identificar qué versión está publicada.

---

38. TRAZABILIDAD

La landing debe poder rastrearse hasta su origen.

Campos:

opportunity_id
fuentes
evidencias
decision
fecha_creacion
version

Esto permite saber:

¿Por qué existe esta página?

y:

¿De dónde salió esta información?

---

39. FECHAS

Cuando sea necesario se podrán registrar:

fecha_deteccion
fecha_investigacion
fecha_decision
fecha_generacion
fecha_validacion
fecha_publicacion
fecha_actualizacion

Las fechas permiten mantener trazabilidad.

---

40. ESTADO DE VALIDACIÓN

La validación tendrá campos separados.

validacion:
  url
  identidad
  contenido
  datos
  seo
  enlaces
  bloques
  comercial
  resultado

Cada elemento podrá tener:

pendiente
ok
error

El resultado global podrá ser:

APROBADA
RECHAZADA
REVISAR

---

41. ERROR

Cuando exista un error, debe quedar registrado.

Estructura:

errores:
  - codigo
    elemento
    descripcion
    gravedad
    solucion

Ejemplo:

errores:
  - codigo: URL001
    elemento: url
    descripcion: URL no coincide con la oportunidad
    gravedad: critica
    solucion: corregir antes de publicar

---

42. PRIORIDAD DE LAS FUENTES

Cuando existan conflictos entre datos, se utilizará una jerarquía.

Prioridad conceptual:

1. Dato oficial o fuente primaria
2. Dato documentado y validado
3. Investigación secundaria fiable
4. Inferencia razonable
5. Suposición

Las suposiciones no deben presentarse como hechos.

---

43. REGLA DE NULL

Cuando un dato no exista, se utilizará:

null

o se omitirá el campo según la implementación.

No utilizar:

desconocido
no sé
probablemente
inventar

como sustituto de un dato.

---

44. OBJETO COMPLETO DE OPORTUNIDAD

Conceptualmente:

opportunity:
  opportunity_id

  identidad:
    sector
    servicio
    subservicio

  localizacion:
    pais
    comunidad_autonoma
    provincia
    municipio
    localidad

  estrategia:
    intencion
    decision

  seo:
    url
    url_tipo
    canonical
    keywords
    seo_title
    meta_description

  investigacion:
    fuentes
    evidencias
    volumen
    competencia
    tendencia
    demanda

  local:
    informacion_local
    zonas
    cobertura
    necesidades_locales

  comercial:
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

  confianza:
    reseñas
    casos
    acreditaciones

  arquitectura:
    bloques
    servicios_relacionados
    localidades_relacionadas

  contenido:
    hero
    contenido_principal
    problemas
    faq
    cta

  restricciones:
    ...

  validacion:
    ...

  estado:
    ...

  version:
    ...

  trazabilidad:
    ...

Este esquema es conceptual y no obliga todavía a utilizar exactamente esta sintaxis en N8N.

---

45. EJEMPLO REAL

opportunity_id = OPP-0001

sector = servicios
servicio = fontanero
subservicio = desatascos

provincia = Málaga
municipio = Marbella

intencion = comercial
decision = CREAR

url = /fontanero/desatascos/marbella/
url_tipo = servicio_subservicio_localidad

bloques =
  B01
  B02
  B03
  B04
  B07
  B08
  B09
  B14
  B05
  B06

El resto de campos se rellenarán únicamente cuando exista información válida.

---

46. EJEMPLO SIN SUBSERVICIO

servicio = fontanero
subservicio = null
municipio = Marbella

url = /fontanero/marbella/
url_tipo = servicio_localidad

En este caso no se seleccionará B07 — Subservicio.

---

47. EJEMPLO DE FALLBACK

Si una landing tiene:

municipio = Marbella

pero no existen datos fiables sobre barrios atendidos:

B10 = OMITIR

No se debe generar:

"Trabajamos en Nueva Andalucía, Puerto Banús..."

salvo que esos datos estén respaldados.

---

48. EJEMPLO DE CINCO LANDINGS

Si el sistema recibe:

OPP-001
OPP-002
OPP-003
OPP-004
OPP-005

cada oportunidad conserva su propio objeto de datos.

El sistema no debe mezclar:

- datos de localidades;
- teléfonos;
- evidencias;
- URLs;
- bloques;
- contenidos.

Cada landing es una entidad independiente.

---

49. RESPONSABILIDAD DE CADA COMPONENTE

Investigación

Obtiene datos y evidencias.

Matrices

Organizan y comparan oportunidades.

Motor

Decide:

CREAR
NO_CREAR
REVISAR

Arquitectura SEO

Define la lógica estructural.

Arquitectura de URLs

Determina la URL válida.

Arquitectura de landing

Define la estructura de la página.

Sistema de bloques

Determina qué bloques corresponden.

Modelo de datos

Transporta toda la información estructurada.

IA

Genera contenido utilizando los datos recibidos.

N8N

Orquesta el proceso.

Validación

Comprueba el resultado.

WordPress

Recibe y publica la landing aprobada.

---

50. REGLA FUNDAMENTAL DE RESPONSABILIDADES

Ningún componente debe asumir la responsabilidad de otro.

Especialmente:

IA ≠ motor de decisión
IA ≠ arquitectura de URLs
IA ≠ investigación
IA ≠ validación

La IA es principalmente el componente de generación de contenido.

---

51. ESCALABILIDAD

Este modelo debe poder representar:

1 oportunidad
5 oportunidades
50 oportunidades
500 oportunidades
5.000 oportunidades

sin cambiar la estructura conceptual.

Solo aumentará el número de objetos.

---

52. COMPATIBILIDAD MULTISERVICIO

El modelo debe poder utilizarse para:

- fontaneros;
- electricistas;
- abogados;
- carpinteros;
- pintores;
- jardineros;
- reformas;
- climatización;
- cualquier otro servicio incorporado posteriormente.

Los campos generales permanecen.

Los campos específicos del sector podrán añadirse mediante extensiones.

---

53. EXTENSIONES POR SECTOR

Un sector puede necesitar datos específicos.

Ejemplo:

sector = abogados

podría necesitar:

especialidad
jurisdiccion
tipo_de_procedimiento

Estos campos podrán existir como:

datos_sectoriales

No deben contaminar el modelo general.

Ejemplo:

datos_sectoriales:
  especialidad = derecho laboral
  jurisdiccion = laboral

---

54. REGLA PARA CAMPOS NUEVOS

No se debe añadir un campo nuevo simplemente porque una landing concreta lo necesita.

Antes se debe comprobar si:

1. Es específico del sector.
2. Es reutilizable.
3. Debe formar parte del modelo general.
4. Debe pertenecer a otro documento.

Si es específico de un sector:

datos_sectoriales

Si es general:

se incorpora al modelo común.

---

55. COMPATIBILIDAD CON N8N

El modelo está diseñado para poder convertirse posteriormente en:

- JSON;
- registros de Google Sheets;
- objetos internos de N8N;
- entradas para prompts;
- campos de WordPress.

La estructura conceptual debe mantenerse aunque cambie la implementación técnica.

---

56. COMPATIBILIDAD CON IA

La IA debe recibir un contexto estructurado.

Nunca debería recibir únicamente:

«"Hazme una landing de fontanero en Marbella."»

Debe recibir:

IDENTIDAD
URL
INTENCIÓN
DATOS
EVIDENCIAS
BLOQUES
RESTRICCIONES
REGLAS

y producir:

CONTENIDO POR BLOQUE

---

57. REGLA DE NO MEZCLAR DATOS CON INSTRUCCIONES

Los datos deben estar separados de las instrucciones.

Ejemplo:

DATOS:
servicio = fontanero
municipio = Marbella

y:

REGLAS:
no inventar datos
mantener intención
utilizar únicamente información disponible

Esto facilita el control del sistema.

---

58. REGLA DE NO MEZCLAR DATOS CON CONTENIDO FINAL

La información fuente y el contenido generado deben mantenerse separados.

Ejemplo:

datos:
experiencia = 15 años

no significa que automáticamente deba aparecer:

«"Tenemos 15 años de experiencia."»

La IA debe decidir cómo redactarlo dentro de las reglas.

---

59. VALIDACIÓN DE CONSISTENCIA

Antes de generar contenido se debe comprobar:

servicio ↔ subservicio
localidad ↔ provincia
URL ↔ identidad
decisión ↔ generación
bloques ↔ datos

Si existe una contradicción, la generación debe detenerse o pasar a revisión.

---

60. REGLA CRÍTICA

Nunca debe producirse:

decisión = NO_CREAR

junto con:

contenido_generado = true

Ni:

datos_insuficientes = true

junto con:

afirmaciones_inventadas = true

La consistencia de los datos tiene prioridad sobre la automatización.

---

61. ESTADO

MODELO DE DATOS DEFINIDO — PENDIENTE DE CONVERTIRSE EN ESQUEMA TÉCNICO

Este documento define el modelo conceptual común del sistema.

Todavía queda transformar este modelo en una estructura técnica concreta que pueda utilizar N8N.

La siguiente fase será definir:

"proyecto/seo/esquema-datos.md"

o, si se decide simplificar la documentación:

integrar el esquema técnico directamente en este documento.

---

62. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se crea el modelo de datos.

Se establece la separación entre:

- oportunidad;
- decisión;
- URL;
- investigación;
- evidencias;
- información local;
- datos comerciales;
- bloques;
- contenido;
- restricciones;
- validación;
- estado;
- versión;
- trazabilidad.

Se establece que la IA recibe datos estructurados y no decide la estrategia.

Se establece que el modelo debe ser reutilizable para múltiples servicios y escalable a grandes cantidades de landings.

Siguiente paso:

formalizar el esquema técnico que utilizarán N8N y la IA.
