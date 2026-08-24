ESPECIFICACIÓN DE PLANTILLAS VISUALES

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir cómo WordPress representa visualmente los bloques lógicos del sistema sin acoplar la arquitectura a un tema concreto.

---

1. PRINCIPIO FUNDAMENTAL

El proyecto separa completamente:

BLOQUE LÓGICO
↓
DATOS
↓
RENDERER
↓
PLANTILLA VISUAL
↓
TEMA / CSS
↓
HTML FINAL

El bloque lógico define qué es.

Los datos definen qué contiene.

El renderer decide cómo transformar esos datos.

La plantilla define cómo se presenta.

El tema aporta estilos globales y recursos visuales.

---

2. INDEPENDENCIA DEL TEMA

La arquitectura no depende de:

- Kadence;
- Astra;
- GeneratePress;
- Elementor;
- Divi;
- Gutenberg;
- cualquier otro constructor concreto.

Kadence puede utilizarse durante el piloto como implementación visual, pero no debe formar parte del contrato lógico.

Si posteriormente se cambia de tema:

BLOQUES
↓
DATOS
↓
RENDERER

deben permanecer intactos.

Solo cambia:

PLANTILLAS
+
SISTEMA VISUAL

---

3. BLOQUES OFICIALES

Las plantillas deben representar los 23 bloques definidos en:

"proyecto/seo/sistema-bloques.md"

B01 header
B02 navigation
B03 hero
B04 main_content
B05 cta
B06 footer
B07 subservice
B08 problems
B09 local_context
B10 coverage
B11 process
B12 trust
B13 differentiation
B14 faq
B15 related_services
B16 related_locations
B17 structured_data
B18 testimonials
B19 cases
B20 gallery
B21 pricing
B22 opening_hours
B23 map

---

4. NO ES NECESARIO CREAR 23 DISEÑOS COMPLETAMENTE INDEPENDIENTES

Los 23 elementos son bloques lógicos.

La implementación visual podrá utilizar:

- plantillas independientes;
- variantes;
- componentes reutilizables;
- patrones;
- componentes compartidos;
- bloques compuestos;
- bloques sin representación visual.

Por ejemplo:

B07 subservice
↓
Service Card

La misma tarjeta puede reutilizarse en diferentes contextos.

---

5. IDENTIDAD DE INSTANCIA

Cada instancia visual recibirá:

page_id
block_instance_id
block_version
position
enabled
data

Ejemplo:

{
  "page_id": "FON-EST-001",
  "block_instance_id": "FON-EST-001-B03-01",
  "block_id": "B03",
  "block_version": 1,
  "position": 3,
  "enabled": true,
  "data": {}
}

La plantilla no debe crear estas identidades.

Las recibe del modelo.

---

6. BLOCK_INSTANCE_ID

La plantilla debe poder utilizar el identificador para:

- trazabilidad;
- debugging;
- actualizaciones;
- identificación de errores;
- pruebas.

No debe modificarlo.

---

7. BLOCK_VERSION

La plantilla debe ser compatible con la versión del bloque recibida.

Ejemplo:

B03
block_version = 1

Una nueva implementación visual puede soportar varias versiones si resulta necesario.

La versión visual no debe confundirse con:

block_version

ni con:

schema_version

---

8. POSITION

El renderer debe respetar:

position

para determinar el orden de representación.

La plantilla no debe alterar arbitrariamente el orden lógico.

Puede existir una excepción si una plantilla de página define una composición específica aprobada.

---

9. ENABLED

Si:

enabled = false

el bloque no debe renderizarse.

No debe dejar:

- contenedores vacíos;
- espacios innecesarios;
- títulos huérfanos;
- separadores innecesarios.

---

10. DATOS OPCIONALES

Las plantillas deben soportar datos ausentes.

Ejemplo:

image = null

Debe poder renderizarse:

Hero sin imagen

sin romper el diseño.

---

11. DATOS NULOS

No se deben mostrar automáticamente:

null
undefined
N/A
-

cuando un campo no tenga valor.

El renderer decide si:

- oculta el elemento;
- utiliza una variante alternativa;
- muestra un fallback visual autorizado.

---

ESPECIFICACIÓN DE BLOQUES

12. B01 — HEADER

Función: cabecera principal.

Puede contener:

- logo;
- nombre;
- navegación secundaria;
- contacto;
- CTA.

La plantilla no inventa datos comerciales.

---

13. B02 — NAVIGATION

Función: navegación.

Recibe:

items[]

Cada elemento puede contener:

label
url
type
position

Solo se renderizan destinos autorizados.

---

14. B03 — HERO

Función: presentación principal.

Datos habituales:

title
subtitle
description
cta
image

Debe existir al menos una variante sin imagen.

Variantes posibles:

hero_default
hero_split
hero_image
hero_minimal
hero_cta

Las variantes son visuales.

No modifican el contrato lógico.

---

15. B04 — MAIN_CONTENT

Función: contenido principal.

Puede representar:

- párrafos;
- subtítulos;
- listas;
- contenido estructurado;
- elementos destacados.

El contenido no debe depender del diseño.

La misma información debe poder renderizarse con diferentes estilos.

---

16. B05 — CTA

Función: llamada a la acción.

Datos:

title
text
label
action
target

La plantilla representa la acción.

No determina el destino real.

Variantes posibles:

cta_inline
cta_card
cta_banner
cta_section

---

17. B06 — FOOTER

Función: pie global.

Puede contener:

- navegación;
- contacto;
- identidad;
- enlaces legales;
- información corporativa.

Debe poder funcionar como componente global.

---

18. B07 — SUBSERVICE

Función: mostrar subservicios.

Puede utilizar:

card
list
grid
accordion

según la variante visual.

La información procede del sistema.

---

19. B08 — PROBLEMS

Función: representar problemas o necesidades.

Puede utilizar:

problem_list
problem_cards
problem_grid

No debe introducir afirmaciones locales no verificadas.

---

20. B09 — LOCAL_CONTEXT

Función: presentar contexto territorial útil.

Puede utilizar:

- texto;
- tarjetas;
- referencias;
- elementos geográficos.

No debe utilizarse para generar contenido local artificial.

---

21. B10 — COVERAGE

Función: representar zonas de cobertura.

Puede visualizarse como:

coverage_list
coverage_grid
coverage_cards

Las zonas proceden de datos autorizados.

---

22. B11 — PROCESS

Función: representar pasos.

Variantes:

process_steps
process_timeline
process_cards

Debe funcionar correctamente con distinto número de pasos.

---

23. B12 — TRUST

Función: mostrar señales de confianza.

Puede visualizar:

- experiencia;
- certificaciones;
- garantías;
- datos verificables.

Cada elemento debe poder ocultarse individualmente si falta información.

---

24. B13 — DIFFERENTIATION

Función: mostrar diferenciadores reales.

Variantes:

differentiation_cards
differentiation_list
differentiation_feature

No debe utilizarse como generador automático de ventajas ficticias.

---

25. B14 — FAQ

Función: preguntas frecuentes.

Debe soportar:

faq_list
faq_accordion
faq_cards

La cantidad de preguntas puede variar.

La plantilla debe adaptarse automáticamente.

---

26. B15 — RELATED_SERVICES

Función: mostrar servicios relacionados.

Debe utilizar componentes de enlace reutilizables.

Cada elemento debe poder representar:

label
description
url

No se generan URLs.

---

27. B16 — RELATED_LOCATIONS

Función: mostrar localidades relacionadas.

Puede utilizar:

location_grid
location_list
location_cards

Solo destinos existentes o autorizados.

---

28. B17 — STRUCTURED_DATA

Este bloque puede no tener representación visual.

Su función principal es proporcionar datos al sistema de renderizado.

Ejemplo:

B17
↓
Structured Data Renderer
↓
JSON-LD
↓
<head>

No debe convertirse automáticamente en contenido visible.

---

29. B18 — TESTIMONIALS

Función: representar testimonios reales.

Variantes:

testimonial_cards
testimonial_list
testimonial_slider

No se generan testimonios ficticios.

---

30. B19 — CASES

Función: representar casos reales.

Puede utilizar:

case_cards
case_list
case_feature

Los datos deben proceder de casos documentados.

---

31. B20 — GALLERY

Función: mostrar imágenes.

Variantes:

gallery_grid
gallery_masonry
gallery_slider
gallery_feature

La plantilla debe soportar:

0 imágenes
1 imagen
varias imágenes

sin romperse.

---

32. B21 — PRICING

Función: mostrar precios reales.

Variantes:

pricing_cards
pricing_table
pricing_list

Si no existen precios:

enabled = false

No se generan precios ficticios.

---

33. B22 — OPENING_HOURS

Función: mostrar horarios reales.

Variantes:

hours_list
hours_table
hours_card

No se inventan horarios.

---

34. B23 — MAP

Función: representar ubicación.

Puede utilizar:

map_embed
map_card
map_with_address

La ubicación debe proceder de datos válidos.

No se inventan coordenadas.

---

SISTEMA VISUAL

35. DESIGN SYSTEM

El sistema visual debe centralizar:

colors
typography
spacing
buttons
cards
containers
icons
forms
shadows
borders
breakpoints

Los bloques no deben definir valores globales duplicados.

---

36. COMPONENTES COMPARTIDOS

Componentes reutilizables:

Container
Section
Heading
Text
Button
Card
Grid
List
Icon
Image
Link
Badge

Los bloques los utilizan.

No los reinventan.

---

37. VARIANTES

Una variante visual debe identificarse independientemente del bloque.

Ejemplo:

{
  "block_id": "B03",
  "variant": "hero_split"
}

La variante no modifica:

block_id
block_instance_id
page_id

---

38. FALLBACK

Si una variante no está disponible:

variant solicitada
↓
variant no disponible
↓
fallback autorizado

Nunca:

variant no disponible
↓
crear diseño improvisado

---

39. RESPONSIVE

Todas las plantillas deben funcionar en:

- móvil;
- tablet;
- escritorio.

Prioridad:

MOBILE FIRST

---

40. ACCESIBILIDAD

Las plantillas deben contemplar:

- HTML semántico;
- jerarquía correcta de headings;
- contraste suficiente;
- navegación por teclado;
- labels;
- alt de imágenes;
- foco visible;
- botones reales;
- enlaces comprensibles.

---

41. SEO TÉCNICO

La plantilla debe respetar:

- un H1 principal;
- jerarquía correcta de headings;
- enlaces HTML válidos;
- imágenes optimizadas;
- atributos alt;
- canonical gestionada por la capa correspondiente;
- datos estructurados gestionados por el renderer.

El bloque visual no debe duplicar automáticamente metadatos SEO.

---

42. HTML

El HTML final pertenece a la capa de renderizado.

La IA no debe ser responsable del HTML final.

Esto permite cambiar:

renderer
tema
CSS
plantilla

sin modificar el contenido generado.

---

43. SEGURIDAD

Las plantillas deben escapar y sanitizar los datos antes de mostrarlos.

No debe permitirse:

<script>
javascript:
iframe no autorizado
event handlers
HTML peligroso

---

44. IMÁGENES

Las imágenes deben procesarse mediante una capa común.

Debe contemplarse:

src
alt
width
height
loading

cuando corresponda.

El sistema debe evitar saltos de diseño producidos por imágenes sin dimensiones.

---

45. VELOCIDAD

Las plantillas deben priorizar:

- poco JavaScript;
- CSS eficiente;
- imágenes optimizadas;
- carga diferida cuando corresponda;
- evitar plugins innecesarios;
- evitar componentes visuales pesados.

---

46. COMPONENTES GLOBALES

Los elementos comunes de todo el sitio podrán ser:

Header
Navigation
Footer
Global CTA
Cookie / consent
Legal

Su gestión debe estar separada de las landings individuales cuando corresponda.

---

47. PLANTILLA DE PÁGINA

Una plantilla de página será responsable de:

1. recibir el "page_id";
2. cargar las instancias;
3. ordenarlas por "position";
4. comprobar "enabled";
5. seleccionar renderer;
6. seleccionar variante;
7. pasar "data";
8. generar HTML.

Conceptualmente:

PAGE
↓
BLOCK INSTANCES
↓
SORT POSITION
↓
ENABLED?
↓
BLOCK RENDERER
↓
VARIANT
↓
HTML

---

48. RENDERER

Cada bloque debe tener un renderer lógico.

Ejemplo:

B03
↓
HeroRenderer
↓
HeroVariant
↓
HTML

Esto evita que N8N tenga que conocer detalles visuales.

---

49. N8N NO DEBE MAQUETAR

N8N debe encargarse de:

- generación;
- validación;
- transformación;
- sincronización;
- actualización;
- logs.

N8N no debe contener la lógica completa del diseño visual.

---

50. WORDPRESS

WordPress debe recibir una estructura de datos limpia.

El contenido almacenado debe permitir reconstruir la página.

No depender exclusivamente de HTML generado manualmente.

---

51. CAMBIO DE TEMA

Para cambiar de tema:

Tema A
↓
Renderer / templates
↓
Tema B

Los datos permanecen iguales.

El objetivo es que el coste del cambio sea principalmente visual.

---

52. VERSIONADO VISUAL

Las plantillas podrán tener versiones.

Ejemplo:

HeroRenderer v1
HeroRenderer v2

La versión visual puede evolucionar sin cambiar el contrato lógico.

---

53. TESTING VISUAL

Cada bloque debe probarse con:

- datos completos;
- datos parciales;
- datos nulos;
- muchas instancias;
- una instancia;
- "enabled=false";
- móvil;
- tablet;
- escritorio.

---

54. TESTING DE CONTENIDO

Debe comprobarse que:

mismo JSON
+
misma plantilla
=
resultado determinista

salvo elementos explícitamente dinámicos.

---

55. TESTING DE CAMBIO DE TEMA

Durante el piloto se debe comprobar que el modelo lógico no contiene referencias obligatorias al tema.

Una prueba futura consistirá en:

Renderer/Tema A
↓
misma página
↓
Renderer/Tema B

sin modificar:

page_id
block_id
block_instance_id
data

---

56. NO DUPLICACIÓN

No crear una plantilla distinta para:

Fontanero Estepona
Fontanero Manilva
Fontanero Casares

si únicamente cambian los datos.

La plantilla es reutilizable.

---

57. ESCALABILIDAD

El sistema debe poder representar:

1 página
10 páginas
100 páginas
1.000 páginas
10.000 páginas

sin crear manualmente una plantilla nueva por página.

---

58. MANTENIMIENTO

Una modificación visual de un componente compartido debe poder propagarse a todas las páginas que lo utilizan.

Ejemplo:

Button v1
↓
Button v2
↓
todas las plantillas compatibles

---

59. NO ACOPLAMIENTO A KADENCE

Cualquier referencia a Kadence debe limitarse a:

IMPLEMENTACIÓN DEL PILOTO

Nunca debe aparecer como requisito del modelo lógico.

---

60. IMPLEMENTACIÓN DEL PILOTO

La implementación inicial puede utilizar el sistema visual que resulte más rápido y estable para construir el primer prototipo.

La decisión del tema es una decisión de implementación.

No modifica:

- arquitectura;
- datos;
- bloques;
- contrato IA;
- validador;
- interlinking;
- motor SEO.

---

61. ARQUITECTURA FINAL

DATOS
  ↓
BLOQUES LÓGICOS
  ↓
VALIDADOR
  ↓
N8N
  ↓
WORDPRESS
  ↓
RENDERER
  ↓
PLANTILLAS
  ↓
DESIGN SYSTEM
  ↓
TEMA
  ↓
HTML

---

62. REGLA MAESTRA

La plataforma nunca debe confundir:

CONTENIDO

con:

DISEÑO

ni:

BLOQUE LÓGICO

con:

IMPLEMENTACIÓN VISUAL

Esta separación es la que permite escalar y cambiar de tema en el futuro.

---

63. ESTADO

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Siguiente fase

ESPECIFICACIÓN DE PLANTILLAS
↓
MODELO DE RENDERIZADO WORDPRESS
↓
INTEGRACIÓN N8N ↔ WORDPRESS
↓
CONSTRUCCIÓN REAL DE BLOQUES
↓
PRIMERA LANDING
↓
PRUEBAS

FIN
