ESPECIFICACIÓN DE IMPLEMENTACIÓN DE PLANTILLAS WORDPRESS

Versión: 1.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Fecha: 2026-08-24

---

1. OBJETIVO

Definir cómo convertir los bloques lógicos B01–B23 en componentes visuales reutilizables dentro de WordPress.

La documentación debe ser independiente del tema visual utilizado.

La implementación inicial podrá utilizar Kadence, pero el sistema no dependerá de Kadence.

---

2. PRINCIPIO FUNDAMENTAL

El sistema separa:

BLOQUE LÓGICO
↓
PLANTILLA / PATRÓN WORDPRESS
↓
DATOS
↓
RENDERIZADO

La IA no diseña.

N8N no diseña.

El motor SEO no diseña.

WordPress no decide qué bloques necesita una página.

Cada capa mantiene su función.

---

3. INDEPENDENCIA DEL TEMA

Las especificaciones B01–B23 deben poder implementarse utilizando diferentes temas o sistemas visuales compatibles con WordPress.

Ejemplos posibles:

- Kadence;
- GeneratePress;
- Astra;
- otros temas compatibles;
- Gutenberg y patrones nativos;
- sistemas de bloques compatibles.

El nombre del tema utilizado durante el piloto no forma parte del contrato lógico del sistema.

---

4. IMPLEMENTACIÓN INICIAL

Para el primer piloto se podrá utilizar:

WordPress + Gutenberg + Kadence

porque proporciona:

- sistema visual;
- estilos globales;
- responsive;
- bloques;
- patrones;
- reutilización;
- buena integración con WordPress.

Pero cualquier decisión específica de Kadence deberá considerarse una decisión de implementación, no una regla del sistema.

---

5. TIPOS DE IMPLEMENTACIÓN

Cada bloque puede implementarse como:

GLOBAL

Ejemplos:

- B01 Header;
- B02 Navigation;
- B06 Footer.

PATRÓN REUTILIZABLE

Ejemplos:

- B03 Hero;
- B05 CTA;
- B07 Subservice;
- B14 FAQ.

COMPONENTE DENTRO DE UNA PLANTILLA

Ejemplos:

- B04 Main Content;
- B08 Problems;
- B09 Local Context;
- B10 Coverage;
- B11 Process.

BLOQUE NO VISUAL

Ejemplo:

- B17 Structured Data.

No es obligatorio que los 23 bloques sean 23 diseños visuales completamente independientes.

---

6. SISTEMA GLOBAL DE DISEÑO

Antes de construir los bloques se establecerán globalmente:

- colores;
- tipografía;
- tamaños;
- botones;
- espaciado;
- ancho máximo;
- bordes;
- radios;
- sombras;
- estilos de enlaces;
- comportamiento responsive.

Los bloques utilizarán estos valores globales.

No deberán contener estilos arbitrarios que rompan la identidad visual.

---

7. ORDEN DE CONSTRUCCIÓN

FASE A — ESTRUCTURA GLOBAL

1. B01 Header
2. B02 Navigation
3. B06 Footer

FASE B — ESTRUCTURA PRINCIPAL

4. B03 Hero
5. B04 Main Content
6. B05 CTA

FASE C — CONTENIDO

7. B07 Subservice
8. B08 Problems
9. B09 Local Context
10. B10 Coverage
11. B11 Process

FASE D — CONVERSIÓN Y CONFIANZA

12. B12 Trust
13. B13 Differentiation
14. B14 FAQ
15. B18 Testimonials
16. B19 Cases
17. B21 Pricing
18. B22 Opening Hours

FASE E — INTERLINKING

19. B15 Related Services
20. B16 Related Locations

FASE F — ELEMENTOS ESPECIALES

21. B17 Structured Data
22. B20 Gallery
23. B23 Map

---

8. B01 — HEADER

Implementación:

Componente global de WordPress.

Debe poder recibir:

- logo;
- nombre comercial;
- teléfono;
- WhatsApp;
- CTA;
- URL.

Durante TEST:

los datos comerciales pueden estar vacíos.

No se deben publicar datos ficticios en producción.

---

9. B02 — NAVIGATION

Implementación:

Sistema de navegación global de WordPress.

Los elementos procederán de:

menu.items[]

Cada elemento:

label
url
type
position

Solo se mostrarán URLs autorizadas.

---

10. B03 — HERO

Implementación:

Patrón reutilizable de WordPress.

Debe admitir:

- H1;
- subtítulo;
- CTA;
- imagen opcional;
- elemento de confianza opcional.

La estructura visual permanece estable.

Los textos cambian.

---

11. B04 — MAIN CONTENT

Implementación:

Patrón reutilizable de contenido.

Debe permitir:

- títulos;
- párrafos;
- listas;
- destacados;
- contenido estructurado.

No debe utilizarse para rellenar espacio.

---

12. B05 — CTA

Implementación:

Patrón reutilizable.

Debe admitir:

label
action
url

El destino procede de datos validados.

---

13. B06 — FOOTER

Implementación:

Componente global de WordPress.

Puede contener:

- identidad;
- navegación;
- contacto;
- información legal;
- enlaces autorizados.

---

14. B07–B14

Los bloques de contenido deberán construirse como patrones reutilizables siempre que sea técnicamente posible.

Cada patrón debe:

1. tener un diseño estable;
2. tener campos claramente identificados;
3. soportar contenido variable;
4. soportar ausencia de datos opcionales;
5. ser responsive;
6. poder reutilizarse en múltiples páginas.

---

15. B15 — RELATED SERVICES

Patrón reutilizable.

Entrada:

related_services[]

Cada elemento:

label
url
description

La plantilla solo renderiza los enlaces recibidos.

No genera URLs.

---

16. B16 — RELATED LOCATIONS

Patrón reutilizable.

Entrada:

related_locations[]

Ejemplo:

Fontanero en Estepona
Fontanero en Manilva
Fontanero en Casares

Solo se muestran destinos válidos.

---

17. B17 — STRUCTURED DATA

No será necesariamente un patrón visual.

Su función será insertar los datos estructurados válidos correspondientes a la página.

No debe mostrar información ficticia al usuario.

---

18. B18 — TESTIMONIALS

Patrón reutilizable.

Solo se activa cuando existan testimonios válidos.

Si no existen:

enabled = false

El espacio no debe quedar vacío.

---

19. B19 — CASES

Patrón reutilizable.

Solo se muestra cuando existen casos documentados.

---

20. B20 — GALLERY

Patrón reutilizable.

Solo utiliza imágenes existentes y autorizadas.

---

21. B21 — PRICING

Patrón reutilizable.

Solo se activa con precios reales.

Si no existen:

enabled = false

---

22. B22 — OPENING HOURS

Patrón reutilizable.

Solo muestra horarios validados.

---

23. B23 — MAP

Patrón reutilizable.

Solo se muestra cuando existe información de ubicación válida.

---

24. DATOS Y DISEÑO

Regla fundamental:

DATOS ≠ DISEÑO

Ejemplo:

title = "Fontanero en Estepona"

No modifica la estructura del patrón.

Solo modifica el contenido mostrado.

---

25. BLOQUES OPCIONALES

Todos los bloques deberán poder funcionar con:

enabled = true

o:

enabled = false

Cuando estén desactivados:

no deben renderizarse.

Esto permite que cada página utilice únicamente los bloques autorizados por su arquitectura.

---

26. PÁGINA COMPLETA

Conceptualmente:

B01 Header
↓
B02 Navigation
↓
B03 Hero
↓
B04 Main Content
↓
B07 Subservices
↓
B08 Problems
↓
B09 Local Context
↓
B10 Coverage
↓
B11 Process
↓
B12 Trust
↓
B13 Differentiation
↓
B14 FAQ
↓
B15 Related Services
↓
B16 Related Locations
↓
B18 Testimonials
↓
B19 Cases
↓
B20 Gallery
↓
B21 Pricing
↓
B22 Opening Hours
↓
B23 Map
↓
B05 CTA
↓
B06 Footer

El orden real dependerá de la arquitectura de cada página.

No todas las páginas deben contener todos los bloques.

---

27. INTERLINKING

Los enlaces entre páginas se generan mediante datos.

Ejemplo:

B15
↓
related_services[]

y:

B16
↓
related_locations[]

La plantilla convierte esos datos en enlaces HTML normales de WordPress.

Por tanto, en la página publicada:

el usuario podrá hacer clic y navegar a la URL correspondiente.

---

28. ACTUALIZACIONES

Una página ya creada debe poder recibir nuevos datos sin reconstruir manualmente toda la página.

Conceptualmente:

PÁGINA EXISTENTE
↓
NUEVOS DATOS
↓
VALIDACIÓN
↓
ACTUALIZACIÓN
↓
WORDPRESS

Los bloques existentes se actualizan.

Los bloques nuevos se añaden.

Los bloques que ya no correspondan pueden desactivarse.

---

29. MODO TEST

Durante el desarrollo:

environment = TEST

Se permiten datos ficticios únicamente para comprobar:

- diseño;
- renderizado;
- navegación;
- responsive;
- actualización;
- interlinking.

Las páginas de prueba no deben confundirse con páginas de producción.

---

30. MODO PRODUCCIÓN

environment = PRODUCTION

Los datos comerciales deberán ser reales y validados.

Si no existe un dato:

null

o se desactiva el elemento.

Nunca se rellena automáticamente con información inventada.

---

31. COMPATIBILIDAD FUTURA

La implementación deberá evitar dependencias innecesarias del tema utilizado.

Si posteriormente se cambia de tema:

MISMA LÓGICA
↓
NUEVA IMPLEMENTACIÓN VISUAL

No debería ser necesario modificar:

- motor SEO;
- arquitectura;
- contrato IA;
- sistema de interlinking;
- estructura de datos.

Solo se adaptará la capa visual.

---

32. PRIMER PILOTO

Antes de construir los 23 bloques:

se construirá una primera página utilizando:

B01
B02
B03
B04
B05
B06

Objetivo:

demostrar que la estructura visual funciona.

---

33. SEGUNDO PILOTO

Añadir:

B07
B08
B09
B10
B11
B14
B15
B16

Objetivo:

demostrar que una landing SEO local completa puede construirse mediante patrones reutilizables.

---

34. CRITERIOS DE ACEPTACIÓN

Una plantilla se considera válida cuando:

- funciona en móvil;
- funciona en escritorio;
- mantiene el diseño global;
- acepta datos variables;
- acepta datos opcionales;
- puede desactivarse;
- no genera contenido ficticio;
- no crea URLs no autorizadas;
- permite interlinking;
- puede reutilizarse;
- no depende de una localidad concreta;
- no depende innecesariamente de un tema concreto.

---

35. REGLA DE IMPLEMENTACIÓN

No construir los 23 bloques a ciegas.

Primero:

B01
↓
prueba
↓
B02
↓
prueba
↓
B06
↓
prueba

Después:

B03
↓
B04
↓
B05

Y así sucesivamente.

Cada grupo se valida antes de continuar.

---

36. SIGUIENTE PASO

El siguiente paso práctico será:

B01 — HEADER

Primero se definirá su estructura visual y sus campos.

Después se construirá en WordPress.

La implementación inicial podrá hacerse con Kadence, pero el diseño lógico deberá permanecer independiente del tema.

---

FIN
