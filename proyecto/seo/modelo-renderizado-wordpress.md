MODELO DE RENDERIZADO WORDPRESS

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Fecha: 2026-08-24

---

1. FUNCIÓN

Este documento define el puente técnico entre:

SITE_PACKAGE → N8N → WordPress → plantillas → página publicada

La arquitectura, el sistema de bloques y el contrato de salida de IA definen qué debe existir.

Este documento define cómo WordPress debe interpretar esa información.

---

2. PRINCIPIO FUNDAMENTAL

La IA no genera libremente el HTML ni el CSS final.

La IA genera:

- estructura;
- contenido;
- bloques autorizados;
- datos;
- relaciones;
- enlaces autorizados.

El renderizador utiliza esos datos para alimentar plantillas previamente creadas en WordPress.

---

3. INDEPENDENCIA DEL TEMA

El sistema lógico no dependerá de Kadence.

Kadence será únicamente el tema utilizado durante el piloto.

La estructura será:

BLOQUE LÓGICO
↓
RENDERIZADOR
↓
PLANTILLA VISUAL
↓
TEMA ACTUAL

Nunca:

B03 = Kadence

El objetivo es poder cambiar de tema en el futuro sin modificar la arquitectura SEO ni los datos.

---

4. RESPONSABILIDADES

Arquitectura

Decide:

- páginas;
- URLs;
- jerarquía;
- relaciones;
- bloques permitidos.

IA

Decide:

- contenido;
- datos variables;
- selección de bloques autorizados;
- enlaces autorizados.

Validador

Comprueba:

- estructura;
- datos;
- bloques;
- URLs;
- relaciones;
- integridad.

N8N

Gestiona:

- entrada;
- procesamiento;
- identificación;
- creación;
- actualización;
- sincronización;
- errores;
- registro.

WordPress

Gestiona:

- almacenamiento;
- plantillas;
- renderizado;
- publicación.

Tema

Gestiona:

- presentación;
- estilos;
- responsive;
- componentes visuales.

---

5. IDENTIFICADORES

Cada página tendrá identificadores estables.

site_id
opportunity_id
page_id
url
version
status

Cada bloque tendrá:

block_id
block_instance_id
block_version
enabled

Ejemplo

{
  "page_id": "FON-EST-HOME",
  "block_id": "B03",
  "block_instance_id": "FON-EST-HOME-B03-01",
  "block_version": 1,
  "enabled": true
}

"block_id" identifica el tipo de bloque.

"block_instance_id" identifica esa instancia concreta dentro de una página.

---

6. IDENTIFICADORES OFICIALES

Los únicos bloques permitidos son:

B01 Header
B02 Navigation
B03 Hero
B04 Main Content
B05 CTA
B06 Footer
B07 Subservice
B08 Problems
B09 Local Context
B10 Coverage
B11 Process
B12 Trust
B13 Differentiation
B14 FAQ
B15 Related Services
B16 Related Locations
B17 Structured Data
B18 Testimonials
B19 Cases
B20 Gallery
B21 Pricing
B22 Opening Hours
B23 Map

La IA no puede crear identificadores nuevos.

---

7. BLOQUE LÓGICO ≠ PLANTILLA VISUAL

Los 23 bloques lógicos no obligan a tener exactamente 23 plantillas visuales.

Varios bloques pueden compartir una plantilla si resulta adecuado.

La relación será:

B03 → renderer.hero → plantilla visual Hero

---

8. INSTANCIA DE BLOQUE

Una página puede contener varias instancias del mismo bloque.

Ejemplo:

B07-SUBSERVICE-01
B07-SUBSERVICE-02
B07-SUBSERVICE-03

Por tanto, nunca se debe identificar un bloque únicamente mediante "block_id".

Debe utilizarse:

page_id + block_instance_id

---

9. ORDEN

El orden será el definido por:

pages[].blocks[]

Ejemplo:

B01
B02
B03
B04
B07
B08
B09
B14
B15
B16
B05
B06

El renderizador debe respetarlo.

---

10. ESTRUCTURA DE UNA PÁGINA

Conceptualmente:

{
  "page_id": "FON-EST-HOME",
  "url": "/fontanero/estepona/",
  "blocks": [
    {
      "block_id": "B03",
      "block_instance_id": "FON-EST-HOME-B03-01",
      "enabled": true,
      "data": {}
    }
  ]
}

---

11. DATOS DEL BLOQUE

Cada instancia tendrá:

block_id
block_instance_id
enabled
data
links
metadata
version

Los datos variables se almacenan en "data".

---

12. DATOS NULOS

Cuando un dato no exista:

null

Nunca se debe inventar.

Especialmente:

- teléfonos;
- direcciones;
- precios;
- horarios;
- testimonios;
- empresas;
- certificaciones;
- imágenes;
- datos comerciales.

Los datos ficticios solo podrán utilizarse en entorno "TEST".

---

13. RENDERIZADO

Flujo:

SITE_PACKAGE
↓
VALIDADOR
↓
N8N
↓
PAGE
↓
BLOCK INSTANCE
↓
BLOCK ID
↓
RENDERER
↓
TEMPLATE
↓
DATA
↓
WORDPRESS
↓
HTML FINAL

---

14. PLANTILLAS

Las plantillas visuales se crearán manualmente durante la implementación del piloto.

Una vez creadas podrán reutilizarse en cientos o miles de páginas.

Ejemplo:

Plantilla Hero
↓
Fontanero Estepona
Fontanero Manilva
Fontanero Ronda
Fontanero Casares
Fontanero Cártama

Solo cambia el contenido.

---

15. DATOS Y DISEÑO

El contenido debe estar separado del diseño.

Ejemplo:

DATA
title = "Fontanero en Estepona"

La plantilla decide:

tipografía
tamaño
espaciado
colores
botón
estructura
responsive

---

16. NO HTML LIBRE

La IA no debe controlar directamente:

- CSS;
- clases;
- JavaScript;
- tamaños;
- colores;
- tipografías;
- estructura visual arbitraria.

El HTML final pertenece al sistema de renderizado.

---

17. ACTUALIZACIÓN INDIVIDUAL

N8N debe poder recibir:

{
  "operation": "UPDATE_BLOCK",
  "page_id": "FON-EST-HOME",
  "block_instance_id": "FON-EST-HOME-B14-01",
  "data": {}
}

El sistema debe actualizar únicamente esa instancia.

No debe reconstruir toda la página si no es necesario.

---

18. OPERACIONES PERMITIDAS

El renderizador debe soportar:

CREATE_PAGE
UPDATE_PAGE
CREATE_BLOCK
UPDATE_BLOCK
DISABLE_BLOCK
ENABLE_BLOCK
DELETE_BLOCK
UPDATE_LINKS
UPDATE_MENU
PUBLISH
UNPUBLISH

---

19. IDEMPOTENCIA

Una misma operación ejecutada dos veces no debe producir duplicados.

N8N debe localizar primero:

page_id

y después:

block_instance_id

Si existe:

UPDATE

Si no existe:

CREATE

---

20. CREACIÓN DE PÁGINA

Para crear:

{
  "operation": "CREATE_PAGE",
  "page_id": "FON-EST-HOME",
  "url": "/fontanero/estepona/",
  "blocks": []
}

Si "page_id" ya existe, no debe crearse una segunda página.

Debe producirse:

EXISTS

o:

UPDATE

según la instrucción recibida.

---

21. ACTUALIZACIÓN DE PÁGINA

Una actualización podrá afectar a:

- SEO;
- bloques;
- contenido;
- enlaces;
- menú;
- imágenes;
- datos estructurados.

Debe conservar los identificadores existentes.

---

22. ACTUALIZACIÓN PARCIAL

Ejemplo:

Página
├── B03 Hero
├── B04 Main Content
├── B08 Problems
├── B14 FAQ
└── B16 Related Locations

Si cambia únicamente FAQ:

UPDATE B14

No:

DELETE PAGE
CREATE PAGE

---

23. VERSIONADO

Cada página tendrá una versión.

Ejemplo:

page_version: 4

Cada bloque podrá tener:

block_version: 2

Una modificación debe incrementar la versión correspondiente.

---

24. CONTROL DE CAMBIOS

Debe poder registrarse:

page_id
block_instance_id
operation
previous_version
new_version
timestamp
result
error

---

25. INTERLINKING

Los enlaces forman parte de los datos del sistema.

Ejemplo:

{
  "source_block_instance_id": "FON-EST-HOME-B16-01",
  "target_page_id": "FON-MAN-HOME",
  "anchor": "fontanero en Manilva",
  "type": "related_location"
}

El renderizador transforma la relación en un enlace HTML real.

---

26. REGLA DE URL

La IA nunca debe inventar una URL.

Las URLs deben proceder de:

arquitectura autorizada
+
páginas existentes

---

27. INTERLINKING ENTRE LOCALIDADES

Permitido:

Estepona
↓
Manilva
↓
Casares
↓
San Pedro
↓
Marbella

siempre que las páginas estén autorizadas y existan.

---

28. INTERLINKING ENTRE SERVICIOS

También puede existir:

Fontanero
↓
Electricista
↓
Pintor
↓
Carpintero

pero únicamente cuando la arquitectura lo autorice.

No se debe crear una red artificial de enlaces.

---

29. ENLACES A PÁGINAS INEXISTENTES

Nunca se debe publicar:

target_page_id inexistente

La operación debe quedar:

REVIEW

hasta que exista el destino.

---

30. MENÚ

El menú podrá gestionarse mediante:

menu.items[]

Cada elemento debe contener:

label
target_page_id
url
order
enabled

N8N podrá:

- crear;
- actualizar;
- eliminar;
- ordenar.

---

31. SEO

Los datos SEO podrán incluir:

{
  "title": "",
  "meta_description": "",
  "h1": ""
}

La implementación concreta dependerá del sistema SEO instalado en WordPress.

---

32. IMÁGENES

Una imagen deberá disponer de datos válidos:

{
  "url": "",
  "alt": "",
  "title": "",
  "type": "hero"
}

Nunca se deben inventar URLs.

---

33. DATOS ESTRUCTURADOS

B17 contiene la información lógica necesaria.

El sistema técnico decide cómo convertirla al formato final compatible con WordPress.

No se deben publicar datos estructurados falsos.

---

34. TESTIMONIOS Y CASOS

B18 y B19 solo podrán utilizar información real o información explícitamente marcada como ficticia para "TEST".

Nunca se deben presentar datos ficticios como experiencias reales.

---

35. ENTORNOS

Debe existir separación:

TEST
PRODUCTION

Los datos ficticios de pruebas nunca deben pasar automáticamente a producción.

---

36. ERRORES

Errores críticos:

BLOCK_UNKNOWN
PAGE_NOT_FOUND
TEMPLATE_NOT_FOUND
INVALID_URL
INVALID_DATA
INVALID_JSON
DUPLICATE_PAGE
MISSING_REQUIRED_DATA

Una operación crítica fallida no debe publicar parcialmente una página incorrecta.

---

37. FALLBACK

No existe fallback para HTML libre.

Si falta una plantilla:

REVIEW

Si existe un error crítico:

ERROR

---

38. REGISTRO

Cada ejecución debe registrar como mínimo:

site_id
opportunity_id
page_id
url
operation
block_id
block_instance_id
version
result
error
timestamp

---

39. ESCALABILIDAD

El sistema debe funcionar progresivamente:

1 página
↓
3 páginas
↓
10 páginas
↓
50 páginas
↓
100 páginas
↓
1.000+ páginas

No se debe comenzar directamente con generación masiva.

---

40. CAMBIO DE TEMA

Los datos deben sobrevivir a un cambio de:

- tema;
- plantilla;
- diseño;
- sistema visual.

Ejemplo:

B03 + DATA
↓
Renderer
↓
Tema A

y posteriormente:

B03 + DATA
↓
Renderer
↓
Tema B

sin cambiar la arquitectura SEO.

---

41. RELACIÓN CON SISTEMA DE BLOQUES

"sistema-bloques.md" define:

- bloques existentes;
- finalidad;
- campos;
- reglas.

Este documento define:

- identificación;
- renderizado;
- actualización;
- sincronización;
- plantillas.

---

42. RELACIÓN CON ARQUITECTURA

La arquitectura define:

qué páginas existen
qué URLs existen
qué bloques pueden utilizarse
qué relaciones están autorizadas

El renderizador no puede crear estructuras nuevas por iniciativa propia.

---

43. RELACIÓN CON CONTRATO IA

El contrato IA define:

qué debe devolver la IA

Este documento define:

cómo interpretar esa salida

El contrato IA y este documento deben mantenerse compatibles.

---

44. RELACIÓN CON N8N

N8N no debe controlar el diseño visual.

N8N transmite principalmente:

page_id
block_id
block_instance_id
data
links
operation
version

WordPress se ocupa del renderizado.

---

45. CREACIÓN MASIVA

La entrada de una generación masiva podrá ser:

servicio
+
lista de localidades

Ejemplo:

Servicio: fontanero

Localidades:
Estepona
Manilva
Casares
Ronda
Cártama
Fuengirola
...

N8N procesa cada oportunidad individualmente.

---

46. FLUJO DE CREACIÓN

SERVICIO + LOCALIDAD
↓
INVESTIGACIÓN
↓
DECISIÓN
↓
ARQUITECTURA
↓
GENERACIÓN IA
↓
SITE_PACKAGE
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
PLANTILLAS
↓
PUBLICACIÓN

---

47. FLUJO DE ACTUALIZACIÓN

NUEVO DATO
↓
IA / SISTEMA DE DATOS
↓
VALIDACIÓN
↓
N8N
↓
page_id
↓
block_instance_id
↓
UPDATE
↓
WORDPRESS

No se crea una segunda página.

---

48. CAMBIO GLOBAL DE DISEÑO

Si se modifica una plantilla visual:

PLANTILLA
↓
PÁGINAS QUE LA UTILIZAN
↓
NUEVO RENDERIZADO

El contenido no debe necesitar regenerarse.

---

49. REGENERACIÓN DE CONTENIDO

Si cambia el contenido de un bloque:

DATA nueva
↓
block_instance_id
↓
UPDATE_BLOCK

La plantilla permanece intacta.

---

50. SEGURIDAD DE PUBLICACIÓN

No publicar automáticamente si existe:

- JSON inválido;
- bloque desconocido;
- URL no autorizada;
- página duplicada;
- plantilla inexistente;
- dato obligatorio ausente;
- contradicción crítica;
- destino de enlace inexistente.

---

51. PILOTO

Antes de escalar se probará:

1 página
↓
varios bloques
↓
creación
↓
actualización
↓
actualización parcial
↓
interlinking
↓
menú
↓
SEO
↓
publicación

Después:

1 → 3 → 10 → 50 → 100

---

52. IMPLEMENTACIÓN WORDPRESS

Durante el piloto habrá que crear manualmente las plantillas visuales necesarias.

No se asume que cada B01–B23 tenga obligatoriamente una plantilla independiente.

La implementación deberá determinar:

- qué bloques necesitan plantilla;
- cuáles pueden compartirla;
- cómo reciben datos;
- cómo se identifican;
- cómo se actualizan.

---

53. KADENCE COMO PILOTO

Kadence se utilizará únicamente como herramienta visual del piloto.

La documentación no debe utilizar nombres de funciones o estructuras exclusivas de Kadence como identificadores lógicos del sistema.

Esto permitirá sustituirlo posteriormente.

---

54. RESULTADO ESPERADO

Una entrada como:

Servicio: fontanero
Localidad: Estepona

debe poder producir una página completa mediante:

arquitectura
+
datos
+
IA
+
bloques
+
plantillas
+
interlinking
+
WordPress

sin diseñar manualmente cada página.

---

55. PRINCIPIO DE ESCALA

El proyecto no debe construir:

100 páginas × 100 diseños

sino:

1 sistema
+
plantillas reutilizables
+
datos variables
+
muchas páginas

---

56. PRINCIPIO FINAL

ARQUITECTURA
decide qué existe.

IA
decide qué contenido necesita.

N8N
transporta, sincroniza y actualiza.

WORDPRESS
almacena y renderiza.

TEMA
presenta visualmente.

PLANTILLAS
definen el diseño reutilizable.

Ninguna capa debe asumir responsabilidades de otra.

---

57. ESTADO

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Siguiente fase

1. Validar este contrato.
2. Validarlo contra "contrato-salida-ia.md".
3. Validarlo contra "sistema-bloques.md".
4. Validarlo contra "interlinking.md".
5. Pasar a la implementación real de las primeras plantillas en WordPress.
6. Probar creación y actualización de una landing.
7. Documentar el método técnico definitivo.
8. Conectar N8N.

---

FIN DE MODELO DE RENDERIZADO WORDPRESS
