VALIDADOR

Versión: 2.0
Estado: Preparado para implementación piloto
Proyecto: Plataforma de landings locales automatizadas

---

1. OBJETIVO

El validador comprueba que la salida de la IA cumple el contrato vigente antes de permitir que N8N la transforme y la envíe a WordPress.

IA
↓
SITE_PACKAGE
↓
VALIDADOR
↓
OK → TRANSFORMACIÓN → WORDPRESS
ERROR → BLOQUEAR

El validador:

- no genera contenido;
- no decide la arquitectura;
- no inventa datos;
- no modifica silenciosamente la salida;
- no publica.

Su función es determinar si la salida es válida.

---

2. CONTRATO DE ENTRADA

La entrada debe cumplir:

"contrato-salida-ia.md"

Versión vigente: 4.0

El validador debe rechazar:

- JSON inválido;
- estructura incompatible;
- versión no soportada;
- campos obligatorios ausentes;
- tipos incorrectos;
- bloques no autorizados;
- datos comerciales no autorizados;
- URLs inválidas;
- enlaces no permitidos;
- schema inválido.

---

3. RESULTADO

El resultado tendrá siempre esta estructura:

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

Regla principal

errors.length == 0
↓
CONTINUAR

errors.length > 0
↓
BLOQUEAR

---

4. ERRORES Y WARNINGS

ERROR

Bloquea la ejecución.

Ejemplos:

- JSON inválido;
- contrato inválido;
- bloque desconocido;
- bloque no autorizado;
- "page_id" inválido;
- "block_instance_id" inválido;
- URL inválida;
- dato comercial inventado;
- schema inválido;
- HTML peligroso.

WARNING

No bloquea automáticamente.

Ejemplos:

- información opcional ausente;
- contenido incompleto;
- interlinking mejorable;
- elemento que requiere revisión humana.

La política de publicación podrá convertir determinados warnings en bloqueantes.

---

5. ORDEN DE VALIDACIÓN

El proceso seguirá este orden:

1. JSON
2. schema_version
3. estructura
4. identidad
5. URL
6. bloques
7. instancias
8. datos de bloques
9. contenido
10. SEO
11. interlinking
12. imágenes
13. CTA
14. schema
15. datos comerciales
16. seguridad
17. resultado final

---

6. JSON

Comprobar:

- JSON correctamente formado;
- estructura válida;
- tipos correctos;
- ausencia de estructuras corruptas;
- "schema_version" soportada.

Errores:

INVALID_JSON
UNSUPPORTED_SCHEMA_VERSION
INVALID_DATA_TYPE
INVALID_STRUCTURE

---

7. IDENTIDAD

La landing debe contener:

site_id
opportunity_id
page_id

Cuando corresponda, comprobar también:

sector
servicio
subservicio
pais
comunidad_autonoma
provincia
municipio
localidad
intencion

Debe existir coherencia entre:

servicio + localidad + URL + contenido

Error:

IDENTITY_MISMATCH

---

8. PAGE_ID

"page_id":

- debe existir;
- debe ser string;
- no puede estar vacío;
- debe ser estable;
- debe respetar el formato definido por el proyecto.

La IA no puede cambiar arbitrariamente un "page_id" generado por el sistema.

Errores:

MISSING_PAGE_ID
INVALID_PAGE_ID

---

9. OPPORTUNITY_ID

"opportunity_id":

- debe existir;
- debe identificar la oportunidad que originó la landing;
- debe ser estable.

Error:

INVALID_OPPORTUNITY_ID

---

10. URL

Comprobar:

slug
url
canonical
url_tipo

El slug:

- no debe contener espacios;
- debe tener formato válido;
- debe corresponder a la arquitectura URL.

Errores:

INVALID_SLUG
INVALID_URL
INVALID_CANONICAL
CANONICAL_MISMATCH

---

11. CONSISTENCIA DE URL

Ejemplo:

servicio = fontanero
localidad = Estepona

La URL:

/fontanero/estepona/

es coherente.

No sería coherente:

/fontanero/marbella/

Error:

URL_IDENTITY_MISMATCH

---

12. BLOQUES

Solo se permiten los bloques definidos en:

"sistema-bloques.md"

Catálogo:

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

No se permite:

B24
Hero
CustomBlock
RandomBlock

si no están oficialmente definidos.

Error:

UNKNOWN_BLOCK

---

13. BLOQUES AUTORIZADOS

Además de existir en el catálogo, cada bloque debe estar autorizado para la página según la arquitectura vigente.

Si un bloque existe pero no está permitido:

UNAUTHORIZED_BLOCK

---

14. BLOCK_INSTANCE_ID

Cada instancia debe contener:

block_id
block_instance_id
block_version
position
enabled
data

"block_instance_id" debe ser:

- único dentro de su página;
- estable;
- string;
- no vacío.

Error:

INVALID_BLOCK_INSTANCE_ID
DUPLICATE_BLOCK_INSTANCE_ID

---

15. BLOQUES REPETIBLES

No todos los bloques tienen necesariamente la misma regla de multiplicidad.

La fuente de verdad es:

"sistema-bloques.md"

Si un bloque no permite múltiples instancias:

B03
B03

debe generar:

DUPLICATE_BLOCK

Si el bloque permite múltiples instancias, serán válidas siempre que cada una tenga un "block_instance_id" diferente.

---

16. POSICIÓN

Cada instancia debe tener:

position

Debe ser:

- numérica;
- válida;
- coherente;
- sin conflictos.

Error:

INVALID_BLOCK_POSITION
DUPLICATE_BLOCK_POSITION

---

17. ENABLED

Debe ser booleano:

{
  "enabled": true
}

o:

{
  "enabled": false
}

No se aceptarán valores como:

"true"
"false"
"yes"
"no"

cuando el contrato requiera booleano.

Error:

INVALID_ENABLED_VALUE

---

18. DATOS DE BLOQUE

Cada bloque debe utilizar únicamente los campos definidos para ese bloque.

La definición procede de:

"sistema-bloques.md"

No se aceptarán campos arbitrarios cuando el contrato los prohíba.

Error:

UNAUTHORIZED_BLOCK_FIELD

---

19. REGISTRO DE BLOQUES

El validador utilizará conceptualmente:

BLOCK_REGISTRY
├── B01
├── B02
├── B03
├── ...
└── B23

No se deben duplicar manualmente las reglas de los bloques en múltiples workflows.

---

20. CONTENIDO

Comprobar:

- campos obligatorios;
- tipos;
- valores vacíos;
- coherencia;
- ausencia de placeholders;
- ausencia de instrucciones internas;
- ausencia de datos inventados.

El validador no debe reescribir el contenido.

---

21. PLACEHOLDERS

Bloquear patrones como:

TODO
PLACEHOLDER
Lorem ipsum
INSERT HERE
[REEMPLAZAR]
{{variable}}
{{nombre}}
[LOCALIDAD]
[EMPRESA]

Error:

PROHIBITED_CONTENT

---

22. CONSISTENCIA DEL SERVICIO

Si:

servicio = fontanero

no puede producirse:

H1 = Electricista en Estepona

Error:

SERVICE_INCONSISTENCY

---

23. CONSISTENCIA LOCAL

Si:

localidad = Estepona

el contenido principal no debe referirse accidentalmente a otra localidad.

Ejemplo inválido:

H1 = Fontanero en Estepona
contenido = Servicio de fontanería en Marbella
canonical = /fontanero/marbella/

Error:

LOCALITY_INCONSISTENCY

---

24. SEO

Comprobar:

seo.title
seo.meta_description
seo.canonical
seo.robots

cuando sean obligatorios.

Comprobar:

- coherencia con servicio y localidad;
- longitud según las reglas SEO vigentes;
- ausencia de HTML no permitido;
- canonical válida;
- robots válido.

Errores:

INVALID_SEO_TITLE
INVALID_META_DESCRIPTION
INVALID_CANONICAL
INVALID_ROBOTS

---

25. INTERLINKING

Cada enlace interno debe contener, cuando corresponda:

source_block_instance_id
target_page_id
url
anchor
type
enabled

Comprobar:

- URL válida;
- destino permitido;
- anchor coherente;
- ausencia de destinos desconocidos;
- ausencia de enlaces rotos conocidos.

Errores:

INVALID_INTERNAL_LINK
INVALID_LINK_TARGET
INVALID_ANCHOR
UNKNOWN_INTERNAL_URL

---

26. DESTINOS INEXISTENTES

La IA no puede inventar destinos.

Si:

target_page_id

no pertenece al conjunto de páginas disponibles o autorizadas:

UNKNOWN_LINK_TARGET

El enlace se bloquea.

---

27. IMÁGENES

Cuando existan imágenes, comprobar:

url
alt
title
type

No aceptar:

- URLs ficticias;
- recursos inexistentes conocidos;
- protocolos peligrosos;
- contenido no autorizado.

Error:

INVALID_IMAGE

---

28. CTA

Cuando exista un CTA:

type
text
destination

debe ser válido.

Tipos autorizados dependerán del contrato, por ejemplo:

whatsapp
phone
contact
quote
appointment

El destino debe estar validado.

Nunca se debe inventar:

teléfono
WhatsApp
email
URL

Errores:

INVALID_CTA
UNAUTHORIZED_CTA_DESTINATION

---

29. DATOS COMERCIALES

Especial protección para:

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

El validador debe comprobar que proceden de datos autorizados.

Error:

UNAUTHORIZED_COMMERCIAL_DATA

---

30. DATOS AUSENTES

La ausencia de información no debe provocar invención.

Preferible:

{
  "telefono": null
}

que:

{
  "telefono": "600000000"
}

No utilizar valores ficticios como:

600000000
123456789
N/A
example@example.com

para rellenar datos reales.

---

31. SCHEMA

Cuando exista:

schema

comprobar:

- JSON válido;
- estructura válida;
- tipos permitidos;
- URLs válidas;
- coherencia con la landing;
- ausencia de datos comerciales inventados.

Errores:

INVALID_SCHEMA
SCHEMA_DATA_MISMATCH
UNAUTHORIZED_SCHEMA_DATA

---

32. HTML

La IA no debe generar HTML libre si el contrato utiliza datos estructurados.

Se rechazará HTML peligroso o no autorizado.

Especialmente:

<script>
<iframe>
<style>

y:

javascript:
onerror=
onclick=
onload=

Error:

UNSAFE_HTML

---

33. PROMPT INJECTION

El contenido público no puede contener instrucciones destinadas al sistema o a la IA.

Ejemplos:

ignore previous instructions
system:
assistant:
developer:

cuando aparezcan como instrucciones internas accidentales.

Error:

INTERNAL_INSTRUCTION_DETECTED

---

34. FAQ

Cada FAQ deberá contener:

question
answer

Comprobar:

- pregunta no vacía;
- respuesta no vacía;
- coherencia;
- ausencia de datos inventados;
- ausencia de HTML peligroso.

Errores:

INVALID_FAQ
EMPTY_FAQ

---

35. DATOS ESTRUCTURADOS Y COMERCIALES

Nunca se debe permitir que la IA complete automáticamente campos que requieran información real.

Regla:

DATO NO DISPONIBLE
↓
null / omitido

No:

DATO NO DISPONIBLE
↓
INVENTAR

---

36. SEGURIDAD

Bloquear:

- scripts;
- iframes no autorizados;
- URLs "javascript:";
- handlers HTML;
- código ejecutable;
- credenciales;
- secretos;
- instrucciones internas.

Errores:

UNSAFE_CONTENT
CREDENTIAL_EXPOSURE
INTERNAL_INSTRUCTION_DETECTED

---

37. TRAZABILIDAD

Cada validación debe asociarse a:

site_id
opportunity_id
page_id
schema_version
validator_version
timestamp
result
errors
warnings

Esto permite saber por qué una landing fue aceptada o rechazada.

---

38. FORMATO DE ERROR

Cada error debe tener:

{
  "code": "UNAUTHORIZED_BLOCK",
  "severity": "ERROR",
  "path": "landing.blocks[4].block_id",
  "message": "El bloque no está autorizado para esta landing"
}

Campos:

code
severity
path
message

---

39. FORMATO DE WARNING

{
  "code": "MISSING_OPTIONAL_DATA",
  "severity": "WARNING",
  "path": "landing.blocks[3].data.subtitle",
  "message": "Campo opcional vacío"
}

---

40. RESULTADO VÁLIDO

Ejemplo:

{
  "valid": true,
  "errors": [],
  "warnings": [],
  "metadata": {
    "schema_version": "4.0",
    "validator_version": "2.0",
    "page_id": "FON-EST-HOME"
  }
}

---

41. RESULTADO INVÁLIDO

Ejemplo:

{
  "valid": false,
  "errors": [
    {
      "code": "UNAUTHORIZED_BLOCK",
      "severity": "ERROR",
      "path": "landing.blocks[5].block_id",
      "message": "Bloque no autorizado"
    }
  ],
  "warnings": [],
  "metadata": {
    "schema_version": "4.0",
    "validator_version": "2.0",
    "page_id": "FON-EST-HOME"
  }
}

---

42. NO CORREGIR AUTOMÁTICAMENTE

El validador no debe cambiar silenciosamente:

- títulos;
- H1;
- URLs;
- bloques;
- datos;
- teléfonos;
- precios;
- enlaces;
- schema;
- contenido.

Si existe un error:

ERROR
↓
BLOQUEAR
↓
REGISTRAR
↓
CORREGIR ORIGEN
↓
VOLVER A VALIDAR

Esto mantiene la trazabilidad.

---

43. INTEGRACIÓN CON N8N

Flujo:

AI
↓
PARSE
↓
VALIDATOR
↓
IF valid == true
    ↓
TRANSFORMER
    ↓
WORDPRESS

Si:

valid == false

entonces:

ERROR HANDLER
↓
LOG
↓
NO WORDPRESS

---

44. RELACIÓN CON WORDPRESS

El validador valida el modelo antes de su transformación.

SITE_PACKAGE
↓
VALIDADOR
↓
MODELO WORDPRESS
↓
RENDERIZADOR

No valida el diseño visual final.

La comprobación del renderizado pertenece a la fase de verificación posterior.

---

45. IDEMPOTENCIA

El validador debe comprobar que:

page_id

es estable.

Y que:

block_instance_id

es estable dentro de su página.

La ejecución repetida de una misma entrada no debe producir nuevas identidades.

---

46. VERSIONES

Debe comprobarse:

schema_version

contra la versión soportada.

También se registrará:

validator_version

Esto permite evolucionar el sistema sin perder trazabilidad.

---

47. PRUEBAS MÍNIMAS

Antes del piloto se deberán probar:

Test 01

JSON válido.

Test 02

JSON inválido.

Test 03

"page_id" ausente.

Test 04

"page_id" duplicado/inválido.

Test 05

Bloque desconocido.

Test 06

Bloque no autorizado.

Test 07

"block_instance_id" duplicado.

Test 08

URL inválida.

Test 09

Canonical incorrecta.

Test 10

Dato comercial inventado.

Test 11

Enlace interno inexistente.

Test 12

Schema inválido.

Test 13

HTML peligroso.

Test 14

Placeholder.

Test 15

Contenido con prompt injection.

Test 16

Landing válida completa.

---

48. REGLA DE PUBLICACIÓN

Una landing solo puede continuar hacia publicación cuando:

valid == true

Durante el piloto:

VALIDADOR
↓
N8N
↓
WORDPRESS
↓
DRAFT

La publicación automática se habilitará después de superar las pruebas.

---

49. FUENTES DE VERDAD

modelo-datos.md
→ modelo común

contrato-salida-ia.md
→ contrato de IA

sistema-bloques.md
→ catálogo y reglas B01–B23

arquitectura-wordpress.md
→ arquitectura WordPress

modelo-datos-wordpress.md
→ modelo de datos WordPress

modelo-renderizado-wordpress.md
→ renderizado

integracion-n8n-wordpress.md
→ integración

El validador no debe redefinir esas fuentes.

Debe comprobarlas.

---

50. PRINCIPIO FINAL

IA
↓
GENERA

VALIDADOR
↓
COMPRUEBA

N8N
↓
ORQUESTA

WORDPRESS
↓
ALMACENA

RENDERIZADOR
↓
TRANSFORMA

PLANTILLAS
↓
PRESENTAN

TEMA
↓
ESTILIZA

El validador es la barrera de seguridad y calidad entre la IA y WordPress.

FIN
