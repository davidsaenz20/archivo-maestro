VALIDADOR

Versión: 1.0
Estado: Diseño técnico
Proyecto: Plataforma de landings locales automatizadas

---

1. OBJETIVO

El validador comprueba que la salida de la IA cumple el contrato definido antes de permitir que N8N la transforme y la envíe a WordPress.

IA
↓
JSON
↓
VALIDADOR
↓
OK → N8N
ERROR → BLOQUEAR

El validador no genera contenido.

No corrige automáticamente contenido.

No decide la arquitectura.

Su función es determinar si la salida es válida.

---

2. ENTRADA

La entrada esperada es el JSON producido según "contrato-salida-ia.md".

Debe contener como mínimo:

schema_version
landing

La estructura exacta debe coincidir con el contrato vigente.

---

3. RESULTADO

El validador devuelve siempre:

{
  "valid": true,
  "errors": [],
  "warnings": [],
  "metadata": {}
}

o:

{
  "valid": false,
  "errors": [],
  "warnings": [],
  "metadata": {}
}

---

4. SEVERIDADES

ERROR

Impide continuar.

Ejemplos:

- JSON inválido.
- Campo obligatorio ausente.
- Tipo de dato incorrecto.
- Bloque no autorizado.
- Bloque duplicado cuando no está permitido.
- URL inválida.
- Schema inválido.
- Datos comerciales no autorizados.
- Incumplimiento del contrato.

WARNING

No bloquea automáticamente.

Ejemplos:

- campo opcional vacío;
- información incompleta;
- interlinking insuficiente;
- contenido que requiere revisión humana.

La decisión final de publicación podrá establecer que determinados warnings también bloqueen.

---

5. VALIDACIÓN POR CAPAS

El proceso seguirá este orden:

1. JSON
2. schema
3. estructura
4. identidad
5. bloques
6. contenido
7. SEO
8. URLs
9. interlinking
10. schema.org
11. datos comerciales
12. reglas de seguridad
13. resultado final

Si una capa crítica falla, el proceso puede detenerse.

---

6. JSON

Comprobar:

- JSON correctamente formado.
- No existen claves estructurales inesperadas cuando estén prohibidas.
- No existen valores de tipos incorrectos.
- No existen estructuras corruptas.
- "schema_version" coincide con la versión soportada.

ERROR:

INVALID_JSON
UNSUPPORTED_SCHEMA_VERSION
INVALID_DATA_TYPE
INVALID_STRUCTURE

---

7. IDENTIDAD

Comprobar:

landing_id
sector
servicio
pais
provincia
municipio/localidad

cuando sean obligatorios según la arquitectura.

Comprobar coherencia:

servicio + localidad

y que no existan contradicciones entre campos.

Ejemplo de error:

IDENTITY_MISMATCH

---

8. LANDING_ID

"landing_id" debe:

- existir;
- ser string;
- no estar vacío;
- tener formato válido;
- ser estable.

No se permitirá que la IA cambie arbitrariamente el identificador proporcionado por el motor.

ERROR:

MISSING_LANDING_ID
INVALID_LANDING_ID

---

9. BLOQUES

El validador debe comprobar que cada bloque pertenece al catálogo oficial:

B01
B02
...
B23

No se permite:

B24
B25
Hero
CustomBlock

si no están definidos como bloques válidos.

ERROR:

UNKNOWN_BLOCK

---

10. BLOQUES AUTORIZADOS

La IA solo puede utilizar los bloques incluidos en:

bloques_autorizados

Si la IA genera:

B08

pero "B08" no está autorizado:

UNAUTHORIZED_BLOCK

El validador bloquea la salida.

---

11. BLOQUES DUPLICADOS

Por defecto un bloque no podrá aparecer más de una vez salvo que la definición oficial permita múltiples instancias.

Ejemplo:

B03
B03

ERROR:

DUPLICATE_BLOCK

La regla podrá modificarse posteriormente para bloques repetibles.

---

12. ORDEN

Cada bloque debe tener una posición coherente.

Ejemplo:

{
  "id": "B03",
  "position": 3
}

Comprobar:

- posición existente;
- posición numérica;
- ausencia de conflictos;
- orden coherente.

ERROR:

INVALID_BLOCK_POSITION

---

13. DATOS DE BLOQUE

Cada bloque debe contener únicamente los campos permitidos por su definición.

No se aceptarán campos arbitrarios introducidos por la IA cuando el contrato no los contemple.

Ejemplo:

B03

no puede convertirse en:

B03
├── h1
├── subtitle
├── precio_inventado
├── telefono_inventado
└── random_data

ERROR:

UNAUTHORIZED_BLOCK_FIELD

cuando corresponda.

---

14. B01–B23

El validador utilizará el catálogo definido en "sistema-bloques.md".

La definición de cada bloque será la fuente de verdad.

No se duplicará manualmente una definición diferente en cada workflow.

Conceptualmente:

BLOCK_REGISTRY
├── B01
├── B02
├── ...
└── B23

---

15. CAMPOS COMERCIALES

Los siguientes datos requieren especial protección:

telefono
whatsapp
email
direccion
precio
horarios
garantia
experiencia
certificaciones
reseñas

El validador debe comprobar que:

- proceden de datos autorizados;
- no aparecen cuando están prohibidos;
- no han sido inventados por la IA.

ERROR:

UNAUTHORIZED_COMMERCIAL_DATA

---

16. DATOS AUSENTES

La ausencia de información no debe provocar invención.

Es preferible:

{
  "telefono": null
}

que:

{
  "telefono": "600000000"
}

si el teléfono no existe en las fuentes autorizadas.

No se permite utilizar valores ficticios como:

N/A
123456789
600000000
ejemplo@example.com

para completar campos comerciales.

---

17. SEO

Comprobar:

seo_title
meta_description
canonical
robots

cuando sean obligatorios.

Comprobar:

- no estén vacíos cuando sean obligatorios;
- longitud según las reglas SEO vigentes;
- ausencia de HTML no permitido;
- coherencia con servicio/localidad;
- canonical válida.

Errores:

INVALID_SEO_TITLE
INVALID_META_DESCRIPTION
INVALID_CANONICAL
INVALID_ROBOTS

---

18. SLUG

El slug debe:

- existir;
- ser único cuando se publique;
- utilizar formato válido;
- no contener espacios;
- no contener caracteres prohibidos;
- corresponder a la arquitectura URL.

Ejemplo válido:

fontanero-marbella

Ejemplo inválido:

Fontanero en Marbella!!!

ERROR:

INVALID_SLUG

---

19. CANONICAL

La canonical debe:

- corresponder a la landing;
- ser válida;
- no apuntar accidentalmente a otra localidad;
- no generar una cadena de redirecciones;
- respetar la arquitectura URL.

ERROR:

CANONICAL_MISMATCH

---

20. INTERLINKING

Cada enlace interno debe comprobar:

url
anchor
target

cuando sean obligatorios.

Comprobar:

- URL válida;
- destino permitido;
- anchor coherente;
- ausencia de enlaces rotos conocidos;
- ausencia de URLs externas cuando solo se permiten internas.

Errores:

INVALID_INTERNAL_LINK
INVALID_LINK_TARGET
INVALID_ANCHOR

---

21. ENLACES INVENTADOS

La IA no puede inventar URLs.

Si el destino no existe en el conjunto de URLs disponibles:

UNKNOWN_INTERNAL_URL

El validador bloqueará el enlace.

---

22. SCHEMA

Cuando exista "schema", comprobar:

- JSON válido;
- estructura válida;
- tipos permitidos;
- URLs válidas;
- datos coherentes con la landing;
- ausencia de datos comerciales inventados.

Errores:

INVALID_SCHEMA
SCHEMA_DATA_MISMATCH
UNAUTHORIZED_SCHEMA_DATA

---

23. CONTENIDO PROHIBIDO

El validador debe detectar patrones conocidos de:

- datos comerciales ficticios;
- placeholders;
- texto de prueba;
- instrucciones para la IA;
- comentarios internos;
- metadatos que no deben aparecer públicamente;
- HTML no permitido;
- contenido fuera del contrato.

Ejemplos:

TODO
PLACEHOLDER
Lorem ipsum
INSERT HERE
{{variable}}
[REEMPLAZAR]

ERROR:

PROHIBITED_CONTENT

---

24. HTML

La salida de la IA no debe utilizarse como HTML arbitrario si el contrato establece contenido estructurado.

Se rechazará HTML no autorizado.

Especialmente:

<script>
iframe
style
event handlers
javascript:

cuando no estén explícitamente permitidos.

ERROR:

UNSAFE_HTML

---

25. PROMPT INJECTION / INSTRUCCIONES INTERNAS

El contenido destinado a publicación no puede contener instrucciones destinadas al sistema o a la IA.

Ejemplos:

ignore previous instructions
system:
assistant:
developer:

si aparecen como contenido accidental de la landing.

ERROR:

INTERNAL_INSTRUCTION_DETECTED

---

26. FAQ

Cada FAQ debe contener:

question
answer

Comprobar:

- pregunta no vacía;
- respuesta no vacía;
- ausencia de datos inventados;
- ausencia de HTML peligroso.

Errores:

INVALID_FAQ
EMPTY_FAQ

---

27. IMÁGENES

Comprobar:

url
alt
type

cuando corresponda.

No aceptar:

- URLs ficticias;
- recursos inexistentes;
- URLs peligrosas;
- contenido no autorizado.

Error:

INVALID_IMAGE

---

28. CTA

Un CTA debe tener:

type
text
destination

cuando la arquitectura lo requiera.

El destino debe estar autorizado.

No se puede crear:

whatsapp → número inventado
phone → número inventado

Error:

INVALID_CTA
UNAUTHORIZED_CTA_DESTINATION

---

29. CONSISTENCIA LOCAL

El validador debe comprobar que la localidad aparece de forma coherente.

Ejemplo:

servicio = fontanero
localidad = Marbella

No debe producirse:

H1 = Fontanero en Marbella
contenido = Fontanero en Estepona
canonical = /fontanero-malaga/

ERROR:

LOCALITY_INCONSISTENCY

---

30. CONSISTENCIA DEL SERVICIO

Igualmente:

servicio = fontanero

no puede producir:

H1 = Electricista en Marbella

ERROR:

SERVICE_INCONSISTENCY

---

31. PUBLICACIÓN

El validador debe devolver explícitamente:

valid = true

solo cuando no existan errores bloqueantes.

Estados:

VALID
INVALID

N8N no deberá enviar a WordPress una salida:

valid = false

---

32. FORMATO DE ERROR

Cada error deberá ser estructurado:

{
  "code": "UNAUTHORIZED_BLOCK",
  "severity": "ERROR",
  "path": "landing.bloques[4].id",
  "message": "El bloque B08 no está autorizado para esta landing"
}

Campos:

code
severity
path
message

---

33. FORMATO DE WARNING

{
  "code": "MISSING_OPTIONAL_DATA",
  "severity": "WARN",
  "path": "landing.bloques[3].data.subtitulo",
  "message": "El campo opcional está vacío"
}

---

34. RESULTADO COMPLETO

Ejemplo válido:

{
  "valid": true,
  "errors": [],
  "warnings": [
    {
      "code": "MISSING_OPTIONAL_DATA",
      "severity": "WARN",
      "path": "landing.bloques[2].data.subtitulo",
      "message": "Campo opcional vacío"
    }
  ],
  "metadata": {
    "schema_version": "1.1",
    "landing_id": "LANDING-fontanero-marbella"
  }
}

Ejemplo inválido:

{
  "valid": false,
  "errors": [
    {
      "code": "UNAUTHORIZED_BLOCK",
      "severity": "ERROR",
      "path": "landing.bloques[5].id",
      "message": "Bloque no autorizado"
    }
  ],
  "warnings": [],
  "metadata": {
    "schema_version": "1.1",
    "landing_id": "LANDING-fontanero-marbella"
  }
}

---

35. REGLA DE CONTINUACIÓN

La regla principal es:

errors.length == 0
        ↓
CONTINUAR

Si:

errors.length > 0

entonces:

BLOQUEAR

Los warnings no bloquean salvo que una regla de publicación específica los convierta en bloqueantes.

---

36. NO CORREGIR AUTOMÁTICAMENTE

El validador no debe cambiar silenciosamente:

- H1;
- URLs;
- bloques;
- teléfonos;
- precios;
- schema;
- enlaces;
- contenido.

Si existe un error:

ERROR
↓
devolver error
↓
corregir origen
↓
volver a validar

Esto evita que el sistema publique información modificada sin trazabilidad.

---

37. INTEGRACIÓN CON N8N

N8N ejecutará:

AI NODE
↓
VALIDATOR
↓
IF valid == true
    ↓
TRANSFORM
    ↓
WORDPRESS

Y:

IF valid == false
    ↓
ERROR HANDLER
    ↓
LOG
    ↓
NO PUBLICAR

---

38. TRAZABILIDAD

Cada validación debe poder asociarse a:

landing_id
schema_version
timestamp
resultado
errores
warnings

Esto permitirá saber por qué una landing fue rechazada.

---

39. VERSIONADO

El validador deberá versionarse junto al contrato.

Ejemplo:

contrato IA: 1.1
validador: 1.1

Una modificación importante del contrato deberá implicar revisión del validador.

No se debe actualizar uno sin comprobar el otro.

---

40. FUENTES DE VERDAD

El validador depende de:

modelo-datos.md
sistema-bloques.md
contrato-salida-ia.md
arquitectura-landing.md
arquitectura-wordpress.md
modelo-datos-wordpress.md
integracion-n8n-wordpress.md

Si existe una contradicción, debe resolverse en el documento propietario antes de modificar el comportamiento del validador.

---

41. IMPLEMENTACIÓN FUTURA

La primera implementación podrá realizarse como:

JavaScript / TypeScript

o mediante código ejecutado dentro de N8N.

La arquitectura debe mantener separadas:

REGLAS
↓
VALIDADOR
↓
N8N

para permitir sustituir posteriormente la implementación sin cambiar las reglas de negocio.

---

42. OBJETIVO DE LA PRIMERA VERSIÓN

La primera versión del validador debe ser capaz de:

✓ recibir JSON
✓ comprobar contrato
✓ comprobar bloques
✓ comprobar identidad
✓ comprobar SEO
✓ comprobar URLs
✓ comprobar interlinking
✓ comprobar schema
✓ detectar datos comerciales no autorizados
✓ devolver errores estructurados
✓ bloquear salidas inválidas
✓ permitir salidas válidas

No se añadirá complejidad adicional hasta que esta versión funcione.

---

43. FLUJO DEFINITIVO

MOTOR
  ↓
ARQUITECTURA
  ↓
BLOQUES AUTORIZADOS
  ↓
IA
  ↓
JSON
  ↓
VALIDADOR
  ↓
┌───────────────┐
│               │
VALID            INVALID
│               │
↓               ↓
N8N             LOG
↓               ↓
WORDPRESS       NO PUBLICAR

---

44. SIGUIENTE PASO

Una vez guardado este documento, dejamos de crear documentación de arquitectura.

El siguiente paso será:

IMPLEMENTAR EL VALIDADOR

y posteriormente:

N8N
↓
WORDPRESS

La implementación real comenzará cuando dispongamos de ordenador.

---

ACTUALIZACIÓN — CONTRATO 1.1

Fecha: 2026-08-24
Versión del validador: 1.1
Estado: Diseño técnico consolidado

41. CONTRATO VIGENTE

A partir de esta versión, la estructura de entrada oficial del validador es exclusivamente la definida en:

"proyecto/seo/contrato-salida-ia.md"

Versión vigente:

"schema_version = "1.1""

La referencia anterior:

schema_version
landing

queda OBSOLETA como estructura de entrada.

El validador no debe exigir un objeto raíz "landing".

La estructura raíz vigente es:

{
  schema_version,
  opportunity_id,
  status,
  identity,
  architecture,
  seo,
  menu,
  blocks,
  images,
  internal_links,
  schema,
  validation,
  issues,
  traceability
}

42. CAMPOS PROTEGIDOS

El validador debe comprobar que la IA respeta los datos recibidos desde el contexto de oportunidad.

Campos protegidos:

opportunity_id
identity.sector
identity.service
identity.subservice
identity.municipality
identity.province
architecture.page_type
architecture.url
architecture.canonical
architecture.parent_url

Cuando existan datos equivalentes en el contexto protegido, la IA no puede sustituirlos.

Una contradicción debe producir:

IDENTITY_MISMATCH
ARCHITECTURE_MISMATCH
PROTECTED_DATA_MISMATCH

según corresponda.

43. ESTADO

Los estados válidos del contrato son:

READY
REVIEW
ERROR

El validador técnico no debe convertir silenciosamente:

ERROR → READY

ni:

REVIEW → READY

La decisión de publicación corresponde al flujo superior de validación.

44. BLOQUES

La entrada oficial utiliza:

blocks[]

Cada bloque debe tener como mínimo:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {}
}

La validación debe comprobar:

id válido
type compatible con id
enabled boolean
data objeto

Los identificadores válidos son exclusivamente:

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

La fuente de verdad del catálogo continúa siendo:

"proyecto/seo/sistema-bloques.md"

45. BLOQUES AUTORIZADOS

La IA no tiene autoridad para ampliar el conjunto de bloques.

El validador debe comprobar que:

blocks[].id

pertenece al conjunto de:

bloques_autorizados

Si no pertenece:

UNAUTHORIZED_BLOCK

→ ERROR.

46. SEO

La estructura SEO vigente se encuentra en:

seo.title
seo.meta_description
seo.h1
seo.slug

Debe comprobarse su coherencia con:

identity
architecture

Especialmente:

seo.slug

debe ser compatible con:

architecture.url

Una contradicción produce:

SEO_ARCHITECTURE_MISMATCH

47. MENÚ

La navegación utiliza:

menu.items[]

Cada elemento debe respetar el contrato vigente.

No se permiten URLs inventadas.

Los tipos autorizados son:

current
internal
anchor

Una URL no autorizada produce:

UNKNOWN_INTERNAL_URL

48. INTERLINKING

La estructura vigente utiliza:

internal_links[]

Los enlaces internos deben apuntar únicamente a URLs conocidas o autorizadas.

No se permite que la IA cree páginas inexistentes simplemente para generar enlaces.

49. IMÁGENES

La estructura vigente utiliza:

images[]

Las imágenes deben poder ser procesadas posteriormente por N8N/WordPress.

No se deben aceptar URLs ficticias ni datos inventados.

50. SCHEMA

La estructura vigente utiliza:

schema

El validador comprobará:

- estructura válida;
- coherencia con la identidad;
- coherencia con la URL;
- ausencia de datos comerciales inventados;
- ausencia de datos incompatibles con la oportunidad.

51. VALIDACIÓN

El proceso completo queda definido como:

1. JSON
2. schema_version
3. estructura contrato 1.1
4. identidad
5. arquitectura
6. bloques
7. bloques autorizados
8. datos de bloques
9. SEO
10. menú
11. URLs
12. interlinking
13. imágenes
14. schema
15. datos comerciales
16. seguridad
17. coherencia global
18. resultado

52. RESULTADO PARA N8N

El validador debe producir una salida normalizada:

{
  "valid": true,
  "errors": [],
  "warnings": [],
  "metadata": {
    "schema_version": "1.1",
    "opportunity_id": "",
    "validator_version": "1.1"
  }
}

Si existe al menos un error bloqueante:

valid = false

N8N no puede continuar hacia WordPress.

53. RELACIÓN CON VALIDADOR-LANDING

"validador.md" realiza principalmente la validación técnica del contrato.

"validador-landing.md" realiza la validación de integridad de la landing respecto al contexto protegido.

No se fusionan.

Flujo:

CONTRATO IA 1.1
       ↓
VALIDADOR TÉCNICO
       ↓
VALIDADOR DE LANDING
       ↓
READY / REVIEW / ERROR
       ↓
N8N

54. FUENTE DE VERDAD

En caso de contradicción entre versiones antiguas de este documento y el contrato vigente:

contrato-salida-ia.md

tiene prioridad.

En caso de contradicción sobre bloques:

sistema-bloques.md

tiene prioridad.

En caso de contradicción sobre arquitectura:

arquitectura-wordpress.md
arquitectura-landing.md

tienen prioridad según el ámbito correspondiente.

---

FIN DE ACTUALIZACIÓN 1.1
