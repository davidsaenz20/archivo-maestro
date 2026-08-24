ESPECIFICACIÓN DE IMPLEMENTACIÓN DE PLANTILLAS WORDPRESS

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Fecha: 2026-08-24

---

1. OBJETIVO

Definir cómo convertir los bloques lógicos B01–B23 en componentes visuales reutilizables dentro de WordPress.

La implementación debe ser independiente del tema utilizado.

El sistema lógico no depende de Kadence ni de ningún otro tema o constructor visual.

---

2. ARQUITECTURA

La arquitectura definitiva es:

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
PLANTILLA VISUAL
↓
DESIGN SYSTEM
↓
TEMA
↓
HTML FINAL

Cada capa tiene una responsabilidad diferente.

IA

Genera contenido estructurado.

Motor SEO

Decide qué página debe existir y qué bloques necesita.

N8N

Orquesta, valida, transforma y sincroniza.

WordPress

Almacena y sirve los datos.

Renderer

Convierte bloques lógicos en representación visual.

Plantilla

Define la composición visual.

Tema

Aporta estilos y comportamiento global.

---

3. PRINCIPIO DE INDEPENDENCIA

El nombre del tema no forma parte del modelo lógico.

No debe aparecer como dependencia en:

- IDs de bloques;
- datos;
- contratos IA;
- arquitectura SEO;
- interlinking;
- identificadores de instancia;
- reglas de validación.

Kadence puede utilizarse durante el piloto.

Si posteriormente se cambia a otro sistema:

MISMO CONTENIDO
+
MISMA ARQUITECTURA
+
MISMOS BLOQUES
↓
NUEVO RENDERER / PLANTILLAS

---

4. MODELO DE BLOQUE

Cada instancia debe poder identificarse mediante:

page_id
block_id
type
block_instance_id
block_version
position
enabled
data

Ejemplo:

{
  "page_id": "FON-EST-001",
  "block_id": "B03",
  "type": "hero",
  "block_instance_id": "FON-EST-001-B03-01",
  "block_version": 1,
  "position": 3,
  "enabled": true,
  "data": {}
}

---

5. BLOCK_ID

Identifica el tipo lógico.

Ejemplo:

B03

Debe corresponder exactamente con el bloque definido en "sistema-bloques.md".

---

6. TYPE

Identifica funcionalmente el bloque.

Ejemplo:

B03 → hero

"block_id" y "type" deben coincidir.

Si no coinciden:

BLOCK_TYPE_MISMATCH

---

7. BLOCK_INSTANCE_ID

Identifica una instancia concreta.

Ejemplo:

FON-EST-001-B03-01

Debe ser único dentro de la página.

Permite:

- actualizaciones parciales;
- trazabilidad;
- debugging;
- identificación de errores;
- sincronización.

---

8. BLOCK_VERSION

Identifica la versión lógica del bloque.

Ejemplo:

block_version: 1

Si cambia el contrato estructural del bloque, se incrementa la versión.

La versión lógica es independiente de:

- versión del tema;
- versión del renderer;
- versión CSS;
- versión WordPress.

---

9. POSITION

Indica la posición lógica dentro de la página.

Ejemplo:

B03 → 3
B04 → 4
B14 → 14

El renderer ordenará las instancias por "position".

---

10. ENABLED

Valores permitidos:

true
false

Cuando es "false", el bloque no debe renderizarse.

No debe dejar espacios ni contenedores vacíos.

---

SISTEMA DE RENDERIZADO

11. RENDERER

Cada bloque lógico será atendido por un renderer.

Ejemplo:

B03
↓
HeroRenderer
↓
HeroVariant
↓
HTML

El renderer recibe los datos.

No decide qué bloques necesita la página.

---

12. VARIANTES VISUALES

Un bloque puede tener varias variantes.

Ejemplo:

B03
├── hero_default
├── hero_split
├── hero_image
└── hero_minimal

La variante pertenece a la capa visual.

No cambia:

- "block_id";
- "block_instance_id";
- "page_id";
- estructura lógica.

---

13. FALLBACK DE VARIANTES

Si una variante solicitada no existe:

VARIANTE SOLICITADA
↓
NO DISPONIBLE
↓
VARIANTE FALLBACK AUTORIZADA

Nunca se debe crear una variante improvisada durante el renderizado.

---

14. COMPONENTES REUTILIZABLES

Los renderers deben utilizar componentes comunes.

Componentes mínimos:

Container
Section
Heading
Text
Button
Card
Grid
List
Link
Image
Badge
Icon

Los componentes comunes forman parte del Design System.

---

15. DESIGN SYSTEM

Antes de construir los bloques se definirán globalmente:

- colores;
- tipografías;
- tamaños;
- espaciado;
- ancho máximo;
- botones;
- enlaces;
- tarjetas;
- bordes;
- radios;
- sombras;
- breakpoints;
- responsive.

Los bloques no deben introducir valores arbitrarios que rompan la identidad visual.

---

16. RESPONSIVE

Toda plantilla debe funcionar correctamente en:

MÓVIL
TABLET
ESCRITORIO

Prioridad:

MOBILE FIRST

---

17. ACCESIBILIDAD

Las plantillas deben utilizar:

- HTML semántico;
- headings correctamente jerarquizados;
- enlaces descriptivos;
- botones reales;
- labels;
- foco visible;
- contraste suficiente;
- atributos "alt";
- navegación por teclado.

---

18. SEGURIDAD

Los datos recibidos deben escaparse y sanitizarse antes de renderizarse.

No se permite introducir directamente:

<script>
javascript:
HTML peligroso
event handlers
iframes no autorizados

---

IMPLEMENTACIÓN DE LOS BLOQUES

19. B01 — HEADER

Tipo:

GLOBAL

Puede representar:

- logo;
- marca;
- teléfono;
- WhatsApp;
- CTA;
- enlace principal.

Los datos comerciales deben proceder de información validada.

---

20. B02 — NAVIGATION

Tipo:

GLOBAL

Recibe:

items[]

Cada elemento puede contener:

label
url
type
position

Solo se muestran URLs autorizadas.

---

21. B03 — HERO

Tipo:

REUSABLE PATTERN

Datos:

title
subtitle
description
cta
image

Debe existir como mínimo una variante sin imagen.

Variantes iniciales:

hero_default
hero_split
hero_image
hero_minimal

---

22. B04 — MAIN CONTENT

Tipo:

REUSABLE CONTENT COMPONENT

Debe permitir:

- headings;
- párrafos;
- listas;
- destacados;
- contenido estructurado.

No se utiliza para rellenar longitud artificial.

---

23. B05 — CTA

Tipo:

REUSABLE PATTERN

Datos:

title
text
label
action
target

Variantes iniciales:

cta_inline
cta_card
cta_banner
cta_section

El destino procede de datos validados.

---

24. B06 — FOOTER

Tipo:

GLOBAL

Puede contener:

- identidad;
- navegación;
- contacto;
- información legal;
- enlaces autorizados.

---

25. B07 — SUBSERVICE

Tipo:

REUSABLE PATTERN

Variantes:

subservice_cards
subservice_list
subservice_grid

Los datos proceden de subservicios autorizados.

---

26. B08 — PROBLEMS

Tipo:

REUSABLE PATTERN

Variantes:

problem_list
problem_cards
problem_grid

No debe introducir problemas específicos no verificados.

---

27. B09 — LOCAL CONTEXT

Tipo:

REUSABLE PATTERN

Puede representar:

- contexto local;
- zonas;
- características territoriales;
- información geográfica útil.

No se permite generar contexto local ficticio.

---

28. B10 — COVERAGE

Tipo:

REUSABLE PATTERN

Variantes:

coverage_list
coverage_cards
coverage_grid

Solo se muestran zonas autorizadas.

---

29. B11 — PROCESS

Tipo:

REUSABLE PATTERN

Variantes:

process_steps
process_timeline
process_cards

Debe adaptarse a un número variable de pasos.

---

30. B12 — TRUST

Tipo:

REUSABLE PATTERN

Puede representar:

- experiencia;
- certificaciones;
- garantías;
- reseñas verificadas;
- señales comerciales verificadas.

Nunca se inventan elementos de confianza.

---

31. B13 — DIFFERENTIATION

Tipo:

REUSABLE PATTERN

Variantes:

differentiation_cards
differentiation_list
differentiation_feature

Solo se muestran diferenciadores reales.

---

32. B14 — FAQ

Tipo:

REUSABLE PATTERN

Variantes:

faq_list
faq_accordion
faq_cards

Debe aceptar cualquier cantidad válida de preguntas.

---

33. B15 — RELATED SERVICES

Tipo:

REUSABLE PATTERN

Entrada:

related_services[]

Cada elemento:

label
url
description

El renderer no crea URLs.

---

34. B16 — RELATED LOCATIONS

Tipo:

REUSABLE PATTERN

Entrada:

related_locations[]

Solo se muestran localidades autorizadas.

---

35. B17 — STRUCTURED DATA

Tipo:

NON-VISUAL

No necesita representación visual.

Flujo:

B17
↓
StructuredDataRenderer
↓
JSON-LD
↓
HTML / HEAD

No debe duplicar innecesariamente información visible.

---

36. B18 — TESTIMONIALS

Tipo:

REUSABLE PATTERN

Variantes:

testimonial_cards
testimonial_list
testimonial_slider

Solo se activa cuando existen testimonios reales.

---

37. B19 — CASES

Tipo:

REUSABLE PATTERN

Variantes:

case_cards
case_list
case_feature

Solo se muestran casos documentados.

---

38. B20 — GALLERY

Tipo:

REUSABLE PATTERN

Variantes:

gallery_grid
gallery_masonry
gallery_slider
gallery_feature

Debe soportar:

0 imágenes
1 imagen
varias imágenes

sin romper el layout.

---

39. B21 — PRICING

Tipo:

REUSABLE PATTERN

Variantes:

pricing_cards
pricing_table
pricing_list

Solo precios reales.

Si no existen:

enabled = false

---

40. B22 — OPENING HOURS

Tipo:

REUSABLE PATTERN

Variantes:

hours_list
hours_table
hours_card

Solo horarios validados.

---

41. B23 — MAP

Tipo:

REUSABLE PATTERN

Variantes:

map_embed
map_card
map_with_address

Solo se muestra con información de ubicación válida.

---

REGLAS DE PÁGINA

42. NO TODAS LAS PÁGINAS UTILIZAN TODOS LOS BLOQUES

La arquitectura SEO decide qué bloques están autorizados.

Una página puede utilizar:

B01
B02
B03
B04
B05
B06

o una combinación mayor.

No se añaden bloques únicamente para aumentar contenido.

---

43. ORDEN DE RENDERIZADO

El orden final se determina mediante "position".

Ejemplo:

B03 position 3
B04 position 4
B09 position 5
B14 position 6
B05 position 7

El renderer representa:

B03
↓
B04
↓
B09
↓
B14
↓
B05

---

44. INTERLINKING

El interlinking procede de los datos.

B15
↓
related_services[]

B16
↓
related_locations[]

Los enlaces deben:

- existir;
- estar autorizados;
- tener destino válido;
- ser útiles para el usuario.

---

45. ACTUALIZACIÓN PARCIAL

Una página existente debe poder actualizar una única instancia.

Ejemplo:

page_id
FON-EST-001

block_instance_id
FON-EST-001-B12-01

El sistema actualiza únicamente esa instancia.

No es necesario reconstruir toda la página.

---

46. IDEMPOTENCIA

Si N8N recibe dos veces la misma instancia:

page_id
+
block_instance_id

no debe crear duplicados.

Regla:

NO EXISTE
↓
CREATE

EXISTE
↓
UPDATE

---

47. MODO TEST

Durante desarrollo:

environment = TEST

Se permiten datos ficticios únicamente para comprobar:

- renderizado;
- responsive;
- navegación;
- actualización;
- interlinking.

Los datos de prueba no deben llegar a producción.

---

48. MODO PRODUCCIÓN

Durante producción:

environment = PRODUCTION

Los datos comerciales deben estar validados.

Si un dato no existe:

null

o se desactiva el elemento.

Nunca se inventa.

---

ORDEN DE CONSTRUCCIÓN

49. FASE 1 — SISTEMA GLOBAL

Antes de construir bloques:

Design System
↓
Container
↓
Typography
↓
Buttons
↓
Cards
↓
Grid
↓
Responsive

---

50. FASE 2 — ESTRUCTURA GLOBAL

Construir:

B01 Header
B02 Navigation
B06 Footer

Validar antes de continuar.

---

51. FASE 3 — LANDING MÍNIMA

Construir:

B03 Hero
B04 Main Content
B05 CTA

Con:

B01
B02
B06

Resultado:

HEADER
NAVIGATION
HERO
MAIN CONTENT
CTA
FOOTER

Esta será la primera página funcional.

---

52. FASE 4 — CONTENIDO SEO

Añadir:

B07 Subservice
B08 Problems
B09 Local Context
B10 Coverage
B11 Process
B14 FAQ

---

53. FASE 5 — CONVERSIÓN Y CONFIANZA

Añadir:

B12 Trust
B13 Differentiation
B18 Testimonials
B19 Cases
B21 Pricing
B22 Opening Hours

Solo cuando los datos existan.

---

54. FASE 6 — INTERLINKING Y ELEMENTOS ESPECIALES

Añadir:

B15 Related Services
B16 Related Locations
B17 Structured Data
B20 Gallery
B23 Map

---

CRITERIOS DE ACEPTACIÓN

55. UNA PLANTILLA ESTÁ TERMINADA CUANDO

Cumple:

- renderizado correcto;
- responsive;
- accesibilidad básica;
- datos variables;
- datos opcionales;
- "enabled";
- "position";
- "block_instance_id";
- variantes;
- fallback;
- URLs válidas;
- ausencia de contenido ficticio;
- reutilización;
- independencia de localidad;
- independencia del tema.

---

56. PRUEBAS MÍNIMAS

Cada renderer debe probarse con:

datos completos
datos parciales
datos nulos
enabled=true
enabled=false
una instancia
múltiples instancias
móvil
tablet
escritorio

---

57. PRUEBA DE CAMBIO DE TEMA

La prueba definitiva será:

MISMO JSON
↓
TEMA / RENDERER A
↓
PÁGINA

MISMO JSON
↓
TEMA / RENDERER B
↓
PÁGINA

Los datos y la arquitectura deben permanecer intactos.

---

58. NO DUPLICACIÓN DE PLANTILLAS

No se debe crear una plantilla para cada combinación:

Fontanero Estepona
Fontanero Manilva
Fontanero Casares

Las páginas utilizan los mismos bloques y plantillas.

Cambian los datos.

---

59. ESCALABILIDAD

La implementación debe poder manejar:

1 página
10 páginas
100 páginas
1.000 páginas
10.000 páginas

sin crear manualmente una plantilla por página.

---

60. MANTENIMIENTO

Los componentes compartidos deben poder actualizarse centralmente.

Ejemplo:

Button v1
↓
Button v2
↓
todas las plantillas compatibles

---

61. N8N NO MAQUETA

N8N no debe contener la lógica completa del diseño.

N8N:

recibe
↓
valida
↓
transforma
↓
sincroniza

WordPress/renderer:

renderiza

---

62. WORDPRESS NO DECIDE LA ARQUITECTURA SEO

WordPress recibe la estructura ya decidida.

No debe decidir automáticamente:

- qué páginas crear;
- qué localidades utilizar;
- qué bloques son necesarios;
- qué enlaces crear.

---

63. IA NO DECIDE EL DISEÑO VISUAL

La IA genera:

contenido estructurado

No genera como contrato principal:

HTML
CSS
maquetación
clases visuales específicas del tema

---

64. CAMBIO DE TEMA

Cambiar el tema debe afectar principalmente a:

templates
renderers
design system
CSS

No debe obligar a modificar:

SEO
arquitectura
datos
contrato IA
interlinking
block_instance_id

---

65. PRIMER PILOTO

La primera implementación real será únicamente:

B01 Header
B02 Navigation
B03 Hero
B04 Main Content
B05 CTA
B06 Footer

Objetivo:

demostrar que el sistema completo puede generar y renderizar una landing funcional antes de construir los 23 bloques.

---

66. SIGUIENTE PASO PRÁCTICO

Una vez validado este documento:

1. Construir B01 Header
2. Probar
3. Construir B02 Navigation
4. Probar
5. Construir B06 Footer
6. Probar
7. Construir B03 Hero
8. Probar

No se avanza al siguiente bloque si el anterior no funciona correctamente.

---

67. REGLA MAESTRA

NO CONSTRUIR 23 BLOQUES A CIEGAS.

CONSTRUIR
↓
PROBAR
↓
VALIDAR
↓
DOCUMENTAR
↓
CONTINUAR

La arquitectura debe permanecer desacoplada de la implementación visual concreta.

FIN
