ESPECIFICACIÓN DE PLANTILLAS VISUALES

Versión: 1.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir cómo deben diseñarse las plantillas visuales de WordPress que representan los bloques lógicos del sistema.

---

1. FUNCIÓN

Este documento define la especificación visual y funcional de las plantillas que utilizará WordPress para representar los bloques lógicos definidos por el proyecto.

La implementación inicial utilizará:

WordPress + Kadence

Kadence es la implementación visual inicial, pero no forma parte del modelo lógico central.

El sistema debe poder sustituir Kadence en el futuro sin modificar:

- investigación;
- motor de decisión;
- arquitectura SEO;
- modelo de datos;
- contrato IA;
- sistema de bloques;
- interlinking;
- N8N.

---

2. PRINCIPIO FUNDAMENTAL

El proyecto separa:

BLOQUE LÓGICO
↓
PLANTILLA VISUAL
↓
DATOS
↓
RENDERIZADO

Ejemplo:

B03
↓
Plantilla Hero
↓
title
subtitle
cta
↓
WordPress

La plantilla define cómo se ve.

Los datos definen qué se muestra.

---

3. 23 BLOQUES LÓGICOS

Los bloques oficiales son:

ID| TYPE
B01| header
B02| navigation
B03| hero
B04| main_content
B05| cta
B06| footer
B07| subservice
B08| problems
B09| local_context
B10| coverage
B11| process
B12| trust
B13| differentiation
B14| faq
B15| related_services
B16| related_locations
B17| structured_data
B18| testimonials
B19| cases
B20| gallery
B21| pricing
B22| opening_hours
B23| map

Este listado debe coincidir exactamente con:

"proyecto/seo/sistema-bloques.md"

---

4. PRINCIPIO DE REUTILIZACIÓN

No se debe crear una plantilla diferente para cada localidad.

Ejemplo:

B03 Hero
│
├── Fontanero Estepona
├── Fontanero Manilva
├── Fontanero Casares
├── Fontanero Ronda
├── Fontanero Cártama
└── Fontanero Fuengirola

Todas utilizan la misma plantilla visual.

Cambian los datos.

---

5. NO ES OBLIGATORIO CREAR 23 PLANTILLAS INDEPENDIENTES

Los 23 bloques son bloques lógicos.

No significa que debamos construir obligatoriamente 23 diseños completamente diferentes.

Podrán existir:

- plantillas independientes;
- variantes;
- patrones reutilizables;
- componentes compartidos;
- bloques que se integren directamente en una plantilla de página;
- bloques que no necesiten una representación visual independiente.

La implementación real se decidirá durante el piloto.

---

6. B01 — HEADER

Tipo: header

Función

Representar la cabecera común de la web.

Elementos posibles

- logotipo;
- nombre comercial;
- información básica;
- elemento de contacto cuando exista;
- elementos visuales de identidad.

Datos variables

- logo;
- nombre;
- teléfono;
- WhatsApp;
- email;
- URL.

Regla

Los datos comerciales deben proceder del modelo de datos.

No se inventan.

Implementación

Preferentemente como elemento global de Kadence.

---

7. B02 — NAVIGATION

Tipo: navigation

Función

Representar la navegación principal.

Datos

menu.items[]

Cada elemento tendrá:

- label;
- URL;
- tipo;
- orden.

Regla

No se crean elementos hacia páginas no autorizadas.

Implementación

Preferentemente mediante el sistema de menús de WordPress/Kadence.

---

8. B03 — HERO

Tipo: hero

Función

Presentar inmediatamente:

- servicio;
- localidad;
- propuesta principal;
- acción.

Elementos

- H1;
- subtítulo;
- CTA;
- imagen opcional.

Datos

title
subtitle
cta
image

Reglas

El H1 debe corresponder con la intención de la página.

No debe utilizarse el mismo H1 para todas las páginas cambiando únicamente la localidad si la intención es diferente.

---

9. B04 — MAIN CONTENT

Tipo: main_content

Función

Contener el contenido principal.

Elementos

- título;
- párrafos;
- subtítulos;
- listas;
- contenido estructurado.

Datos

El contenido procederá de la IA y del modelo de datos.

Regla

No debe utilizarse para generar texto de relleno.

---

10. B05 — CTA

Tipo: cta

Función

Facilitar una acción.

Elementos

- título;
- texto;
- botón.

Datos

label
action
url

Regla

La IA puede generar el texto.

No puede inventar el destino real.

---

11. B06 — FOOTER

Tipo: footer

Función

Pie común de la web.

Elementos posibles

- identidad;
- navegación;
- contacto;
- información legal;
- enlaces autorizados.

Implementación

Preferentemente global en Kadence.

---

12. B07 — SUBSERVICE

Tipo: subservice

Función

Presentar un subservicio relacionado con la página.

Elementos

- título;
- descripción;
- CTA;
- enlace.

Regla

Solo puede utilizar subservicios autorizados.

---

13. B08 — PROBLEMS

Tipo: problems

Función

Explicar problemas o necesidades que el servicio puede resolver.

Elementos

- título;
- lista de problemas;
- explicación opcional.

Regla

Los problemas deben estar relacionados con la intención.

No deben inventarse problemas locales.

---

14. B09 — LOCAL CONTEXT

Tipo: local_context

Función

Incorporar información territorial útil.

Elementos

- título;
- contenido;
- referencias locales verificadas.

Regla crítica

No debe utilizarse simplemente para repetir el nombre de la localidad.

No se inventan:

- barrios;
- calles;
- urbanizaciones;
- características locales;
- necesidades;
- tiempos.

---

15. B10 — COVERAGE

Tipo: coverage

Función

Mostrar zonas de cobertura.

Elementos

- título;
- lista de zonas;
- enlaces opcionales.

Regla

Solo se incluyen zonas respaldadas por los datos.

No se crean listas masivas artificiales.

---

16. B11 — PROCESS

Tipo: process

Función

Explicar el proceso de trabajo.

Elementos

- pasos;
- títulos;
- descripción.

Regla

Debe basarse en un proceso real o claramente definido para el proyecto.

No se deben inventar certificaciones o procedimientos profesionales.

---

17. B12 — TRUST

Tipo: trust

Función

Mostrar señales verificables de confianza.

Elementos posibles

- experiencia;
- certificaciones;
- garantías;
- reseñas;
- cobertura;
- datos comerciales.

Regla crítica

No se inventan señales de confianza.

---

18. B13 — DIFFERENTIATION

Tipo: differentiation

Función

Explicar por qué una empresa o servicio puede diferenciarse.

Regla

Debe existir una base real.

No constituye diferenciación:

- cambiar sinónimos;
- cambiar localidad;
- reordenar párrafos;
- generar frases diferentes.

---

19. B14 — FAQ

Tipo: faq

Elementos

- título;
- preguntas;
- respuestas.

Datos

items[]

Cada elemento:

question
answer

Regla

Las preguntas deben proceder de:

- intención;
- investigación;
- conocimiento válido;
- datos disponibles.

---

20. B15 — RELATED SERVICES

Tipo: related_services

Función

Mostrar servicios relacionados.

Elementos

- nombre;
- descripción;
- enlace.

Regla

Solo enlaces autorizados.

No se inventan URLs.

---

21. B16 — RELATED LOCATIONS

Tipo: related_locations

Función

Conectar localidades relacionadas.

Ejemplo:

Fontanero Estepona
↓
Fontanero Manilva
↓
Fontanero Casares

Regla

Solo deben enlazarse páginas existentes y autorizadas.

---

22. B17 — STRUCTURED DATA

Tipo: structured_data

Función

Representar información lógica necesaria para datos estructurados.

Regla

No se muestran necesariamente como contenido visual.

Puede ser procesado por el sistema de renderizado.

Nunca se inventan:

- reviews;
- ratings;
- precios;
- empresas;
- personas;
- horarios;
- direcciones.

---

23. B18 — TESTIMONIALS

Tipo: testimonials

Función

Mostrar testimonios reales cuando existan.

Elementos

- nombre;
- texto;
- valoración si está verificada.

Regla crítica

No se generan testimonios ficticios para producción.

---

24. B19 — CASES

Tipo: cases

Función

Mostrar casos reales.

Elementos

- título;
- problema;
- solución;
- resultado.

Regla

Solo datos documentados.

---

25. B20 — GALLERY

Tipo: gallery

Función

Mostrar imágenes disponibles.

Datos

- URL;
- alt;
- título;
- tipo.

Regla

No se inventan URLs.

---

26. B21 — PRICING

Tipo: pricing

Función

Mostrar precios cuando existan datos comerciales reales.

Regla

No se inventan precios.

Si no existen:

enabled = false

o:

data = null

según el contrato.

---

27. B22 — OPENING HOURS

Tipo: opening_hours

Función

Mostrar horarios.

Regla

Solo datos reales.

No se inventan horarios.

---

28. B23 — MAP

Tipo: map

Función

Mostrar ubicación cuando exista una ubicación válida.

Regla

No se inventan direcciones ni coordenadas.

---

29. CAMPOS DINÁMICOS

Cada plantilla debe identificar claramente qué campos recibe.

Ejemplo B03:

title
subtitle
cta.label
cta.action
cta.url
image.url
image.alt

El diseño debe permanecer fijo.

---

30. CAMPOS OPCIONALES

Los elementos opcionales no deben romper el diseño.

Ejemplo:

image = null

La plantilla debe poder renderizar el Hero sin imagen.

---

31. CONDICIONES DE VISIBILIDAD

Cada plantilla debe soportar:

enabled = true

o:

enabled = false

Cuando está desactivada:

no se renderiza.

---

32. RESPONSIVE

Todas las plantillas deben funcionar correctamente en:

- móvil;
- tablet;
- escritorio.

La prioridad inicial será:

móvil primero.

---

33. CONSISTENCIA

Las plantillas deben compartir:

- tipografía;
- colores;
- botones;
- espaciado;
- bordes;
- sombras;
- ancho de contenido;
- comportamiento responsive.

No debe parecer que cada bloque pertenece a una web diferente.

---

34. SISTEMA DE DISEÑO

Antes de crear todas las plantillas se definirá:

- paleta;
- tipografías;
- tamaños;
- botones;
- espaciados;
- contenedores;
- imágenes;
- iconografía.

Kadence será utilizado para mantener estos elementos globales.

---

35. COMPONENTES COMPARTIDOS

Cuando varios bloques utilicen los mismos componentes:

BOTÓN
TARJETA
ICONO
CONTENEDOR
TÍTULO
LISTA

deben reutilizarse.

No se deben recrear manualmente.

---

36. ESTRUCTURA DE UNA PÁGINA

Una página podrá representarse conceptualmente como:

HEADER
NAVIGATION
        ↓
HERO
        ↓
MAIN CONTENT
        ↓
PROBLEMS
        ↓
LOCAL CONTEXT
        ↓
SERVICES
        ↓
FAQ
        ↓
CTA
        ↓
FOOTER

Pero el orden exacto dependerá de la arquitectura autorizada.

---

37. NO CREACIÓN DE BLOQUES POR LA IA

La IA nunca podrá decir:

B24

si B24 no existe.

El validador deberá rechazarlo.

---

38. NO CREACIÓN DE PLANTILLAS POR LA IA

La IA tampoco podrá crear una nueva plantilla visual.

Si necesita algo que no existe:

REVIEW

La nueva plantilla deberá ser creada y aprobada por el sistema documental.

---

39. INTERLINKING

Las plantillas que muestran enlaces deben recibir las URLs desde los datos.

Ejemplo:

B15
↓
related_services[]

o:

B16
↓
related_locations[]

La plantilla únicamente representa los enlaces.

---

40. ANCHOR TEXT

El texto del enlace puede ser dinámico.

Ejemplo:

Desatascos en Estepona

El destino debe estar autorizado.

---

41. ACTUALIZACIONES

Una plantilla debe poder actualizarse sin destruir el contenido.

Ejemplo:

Plantilla B03 v1
↓
Plantilla B03 v2

Las páginas que utilizan B03 deben poder beneficiarse de la actualización cuando la implementación elegida permita esa reutilización.

---

42. DATOS COMERCIALES

Los datos comerciales deben estar separados del diseño.

Ejemplo:

empresa
logo
phone
whatsapp
email
address
opening_hours

Esto permite que una web creada inicialmente como activo del proyecto pueda ser posteriormente adaptada a un cliente real.

---

43. MODO TEST

El sistema debe poder trabajar con datos ficticios durante el desarrollo.

Debe existir una identificación clara:

environment = TEST

Los datos ficticios no pueden llegar accidentalmente a producción.

---

44. MODO PRODUCCIÓN

En producción:

environment = PRODUCTION

Los datos comerciales deben proceder del modelo de datos real.

---

45. CAMBIO DE CLIENTE

Una misma estructura visual podrá reutilizarse para distintos clientes.

Ejemplo:

Plantillas
+
Cliente A

y:

Plantillas
+
Cliente B

El diseño no debe estar ligado a una empresa concreta.

---

46. GENERACIÓN MASIVA

El sistema debe permitir utilizar las mismas plantillas para:

Fontanero Málaga
Fontanero Marbella
Fontanero Estepona
Fontanero Manilva
...

sin duplicar manualmente el diseño.

---

47. CONTROL DE CALIDAD VISUAL

Antes de escalar:

comprobar:

- móvil;
- escritorio;
- legibilidad;
- botones;
- enlaces;
- imágenes;
- espacios;
- jerarquía visual;
- navegación;
- accesibilidad básica;
- velocidad razonable.

---

48. CONTROL DE CALIDAD SEO

Las plantillas no deben:

- ocultar contenido importante;
- crear headings innecesarios;
- duplicar títulos;
- generar texto automáticamente sin datos;
- crear enlaces no autorizados;
- generar contenido invisible.

---

49. RENDIMIENTO

Las plantillas deben evitar:

- scripts innecesarios;
- imágenes excesivamente pesadas;
- CSS duplicado;
- elementos visuales innecesarios;
- dependencias excesivas.

El objetivo es mantener páginas rápidas.

---

50. PORTABILIDAD

El sistema lógico no debe depender exclusivamente de Kadence.

La documentación debe poder traducirse en el futuro a:

- otro tema;
- otro constructor;
- bloques nativos de WordPress;
- un sistema propio de renderizado.

---

51. IMPLEMENTACIÓN INICIAL

La implementación inicial recomendada es:

WordPress
+
Kadence
+
plantillas/patrones reutilizables
+
datos dinámicos

No se recomienda inicialmente:

plugin visual complejo
+
HTML generado por IA
+
CSS generado automáticamente

---

52. ORDEN DE CONSTRUCCIÓN

No se deben construir las 23 plantillas de golpe.

Orden recomendado:

FASE 1

Construir:

- B01 Header;
- B02 Navigation;
- B03 Hero;
- B04 Main Content;
- B05 CTA;
- B06 Footer.

FASE 2

Construir:

- B07 Subservice;
- B08 Problems;
- B09 Local Context;
- B10 Coverage;
- B11 Process.

FASE 3

Construir:

- B12 Trust;
- B13 Differentiation;
- B14 FAQ;
- B15 Related Services;
- B16 Related Locations.

FASE 4

Construir según necesidad real:

- B17 Structured Data;
- B18 Testimonials;
- B19 Cases;
- B20 Gallery;
- B21 Pricing;
- B22 Opening Hours;
- B23 Map.

---

53. PRIMER PILOTO

El primer piloto debe utilizar una página real de prueba.

Ejemplo:

Fontanero en Estepona

Debe comprobar:

B01
B02
B03
B04
B05
B06

Después se añadirán bloques condicionales.

---

54. SEGUNDO PILOTO

Después:

Fontanero en Estepona
+
Desatascos
+
FAQ
+
Local Context
+
Related Services
+
Related Locations

Se comprobará que la arquitectura y el sistema visual continúan funcionando.

---

55. TERCER PILOTO

Crear varias localidades utilizando las mismas plantillas:

Estepona
Manilva
Casares
Ronda
Cártama
Fuengirola

El objetivo será demostrar que:

los datos cambian, pero el sistema visual se reutiliza.

---

56. NO ESCALAR TODAVÍA

Aunque el sistema permita generar cientos de páginas, no se debe comenzar con cientos.

Primero:

1
↓
3
↓
10

Después evaluar.

Solo entonces:

50
↓
100
↓
500+

---

57. CRITERIO DE ÉXITO

El sistema será considerado correcto cuando pueda:

1. recibir datos;
2. seleccionar bloques autorizados;
3. utilizar las plantillas correctas;
4. rellenarlas;
5. crear una página;
6. generar enlaces funcionales;
7. generar navegación;
8. actualizar la página;
9. mantener el diseño;
10. evitar duplicados.

---

58. RELACIÓN CON N8N

N8N no debe controlar el diseño.

N8N debe transportar:

page_id
block_id
data

WordPress/Kadence se encargará de la representación visual.

---

59. RELACIÓN CON LA IA

La IA no diseña.

La IA genera contenido y estructura lógica.

La IA no decide:

- colores;
- CSS;
- tipografías;
- tamaños;
- layout visual;
- animaciones.

---

60. PRINCIPIO FINAL

El sistema debe funcionar como:

CONTENIDO
+
ESTRUCTURA
+
PLANTILLAS
=
PÁGINA

y no como:

IA
↓
HTML libre
↓
CSS libre
↓
Página

La primera arquitectura es más controlable, escalable y mantenible.

---

61. ESTADO DEL DOCUMENTO

Versión: 1.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha: 2026-08-24

Implementación visual inicial: WordPress + Kadence

Siguiente fase: construcción y prueba de las primeras plantillas visuales en WordPress.

---

FIN DE ESPECIFICACIÓN DE PLANTILLAS VISUALES
