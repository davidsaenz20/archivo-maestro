SISTEMA DE BLOQUES

Versión: 3.0
Estado: PREPARADO PARA PILOTO DE MINIWEB
Proyecto: Plataforma de miniwebs locales automatizadas

---

1. FUNCIÓN

Este documento define los bloques lógicos que pueden utilizarse para construir las páginas de una miniweb local.

No define solamente una landing.

Define el sistema reutilizable para:

- página principal;
- páginas de servicios;
- páginas de subservicios;
- páginas comerciales;
- contacto;
- otras páginas autorizadas.

El sistema debe permitir construir una miniweb completa manteniendo una estructura común y evitando contenido artificial.

---

2. PRINCIPIO FUNDAMENTAL

Los bloques no existen para rellenar páginas.

Cada bloque debe tener una función.

Puede servir para:

- explicar un servicio;
- resolver una necesidad;
- aportar información local;
- facilitar la conversión;
- mejorar la navegación;
- generar confianza;
- responder preguntas;
- mostrar información comercial;
- mostrar información visual;
- diferenciar una página.

Si un bloque no aporta valor o no dispone de información suficiente:

SE OMITE.

---

3. FLUJO GENERAL

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
MINIWEB
↓
MAPA DE PÁGINAS
↓
ARQUITECTURA DE URL
↓
SELECCIÓN DE BLOQUES
↓
DATOS
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

---

4. UNIDAD DE TRABAJO

El sistema trabaja sobre una página concreta.

Cada página pertenece a una miniweb.

Ejemplo:

miniweb:
FONTANERO-MARBELLA

página:
INICIO

url:
/fontanero-marbella/

Otra página:

miniweb:
FONTANERO-MARBELLA

página:
DESATASCOS

url:
/fontanero-marbella/desatascos/

Los bloques se seleccionan para cada página.

---

5. CATEGORÍAS

5.1 BLOQUES ESTRUCTURALES

- B01 Header
- B02 Navegación
- B06 Footer

5.2 BLOQUES DE CONTENIDO

- B03 Hero
- B04 Contenido principal
- B07 Subservicio
- B08 Problemas / necesidades
- B09 Información local
- B10 Zonas / cobertura
- B11 Proceso
- B12 Elementos de confianza
- B13 Diferenciación
- B14 FAQ
- B18 Testimonios
- B19 Casos / ejemplos
- B20 Galería
- B21 Precio / tarifas
- B22 Horarios
- B23 Mapa / ubicación

5.3 BLOQUES DE CONVERSIÓN / NAVEGACIÓN / DATOS

- B05 CTA
- B15 Servicios relacionados
- B16 Localidades relacionadas
- B17 Datos estructurados

---

6. IDENTIFICADORES OFICIALES

Los identificadores son:

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

Son identificadores estables.

No deben modificarse durante el piloto.

La IA no puede inventar nuevos identificadores.

N8N debe rechazar identificadores desconocidos.

---

7. B01 — HEADER

Función

Proporcionar identidad global de la miniweb.

Puede contener:

- logo;
- nombre;
- navegación;
- CTA global.

Datos

- identidad;
- marca cuando exista;
- URLs autorizadas;
- CTA autorizado.

Restricciones

El header pertenece a la plantilla visual de la miniweb.

No debe generarse un header completamente diferente para cada localidad salvo que el sistema visual lo determine.

---

8. B02 — NAVEGACIÓN

Función

Permitir acceder a las páginas principales de la miniweb.

Puede enlazar a:

- Inicio;
- Servicios;
- subservicios;
- páginas comerciales;
- Contacto.

Datos

- URL;
- anchor;
- prioridad;
- página destino.

Restricciones

Solo enlaza a páginas autorizadas.

No crea URLs.

No debe utilizarse para generar miles de enlaces SEO.

---

9. B03 — HERO

Función

Identificar inmediatamente:

- qué servicio;
- para quién;
- dónde;
- qué acción puede realizar.

Puede contener:

- H1;
- subtítulo;
- CTA;
- elemento visual.

Datos

- servicio;
- subservicio;
- localidad;
- intención;
- CTA autorizado.

Restricciones

No inventar afirmaciones comerciales.

---

10. B04 — CONTENIDO PRINCIPAL

Función

Explicar la necesidad principal de la página.

Puede incluir:

- descripción;
- alcance;
- situaciones;
- problemas;
- beneficios;
- información útil.

Regla

No se utiliza para alcanzar una longitud determinada.

La prioridad es:

UTILIDAD > LONGITUD

---

11. B05 — CTA PRINCIPAL

Función

Facilitar una acción.

Puede utilizar:

phone
whatsapp
email
contact
quote
appointment

Solo se utilizan canales existentes.

Restricciones

Nunca inventar:

- teléfono;
- WhatsApp;
- email;
- precio;
- disponibilidad;
- tiempo de respuesta.

Si no existe un canal válido:

OMITIR CTA DE ESE TIPO.

---

12. B06 — FOOTER

Función

Cerrar la página y proporcionar navegación global.

Puede incluir:

- navegación;
- servicios;
- contacto;
- información legal;
- enlaces estratégicos.

Restricciones

No utilizarlo para crear una red masiva de enlaces SEO.

---

13. B07 — SUBSERVICIO

Función

Explicar un servicio específico.

Ejemplo:

Fontanero
↓
Desatascos

Puede utilizarse en:

"/fontanero-marbella/desatascos/"

Condición

Debe existir una intención específica suficientemente justificada.

---

14. B08 — PROBLEMAS / NECESIDADES

Función

Explicar problemas que el servicio puede resolver.

Ejemplo:

- fregadero atascado;
- desagüe obstruido;
- tubería bloqueada.

Condición

Debe existir evidencia o conocimiento suficientemente válido.

No se generan problemas únicamente para introducir keywords.

---

15. B09 — INFORMACIÓN LOCAL

Función

Aportar información específica de la localidad.

Puede incluir:

- características territoriales;
- contexto residencial;
- urbanizaciones;
- tipos de vivienda;
- necesidades locales;
- características relevantes.

Condición

Debe existir información real.

El simple nombre de la localidad no constituye información local.

---

16. B10 — ZONAS / COBERTURA

Función

Mostrar dónde se presta realmente el servicio.

Puede incluir:

- barrios;
- urbanizaciones;
- zonas;
- municipios;
- localidades cercanas.

Restricciones

Solo utilizar información verificada.

No crear listas artificiales para SEO.

---

17. B11 — PROCESO

Función

Explicar cómo funciona realmente el servicio.

Ejemplo:

Contacto
↓
Evaluación
↓
Actuación
↓
Resolución

No se inventan pasos.

---

18. B12 — ELEMENTOS DE CONFIANZA

Puede incluir:

- experiencia;
- certificaciones;
- garantías;
- reseñas;
- horarios;
- cobertura;
- datos comerciales.

Solo si están respaldados.

Nunca inventar señales de confianza.

---

19. B13 — DIFERENCIACIÓN

Función

Aportar información que justifique que la página tenga valor propio.

Puede proceder de:

- intención;
- servicio;
- subservicio;
- problema;
- información local;
- tipo de cliente;
- cobertura;
- datos reales;
- características verificadas.

Cambiar únicamente:

- localidad;
- título;
- URL;
- sinónimos;
- orden de párrafos;

no constituye diferenciación.

---

20. B14 — FAQ

Función

Responder preguntas relevantes.

Las preguntas pueden proceder de:

- investigación;
- intención;
- preguntas reales;
- información comercial;
- conocimiento válido.

No se crean FAQ artificiales únicamente para SEO.

---

21. B15 — SERVICIOS RELACIONADOS

Función

Conectar la página con otros servicios relevantes de la misma miniweb.

Ejemplo:

Desatascos
↓
Fugas
↓
Reparación de tuberías

Solo enlaza a páginas existentes o previamente autorizadas.

---

22. B16 — LOCALIDADES RELACIONADAS

Función

Facilitar navegación hacia otras miniwebs o localidades cuando corresponda.

Debe utilizarse de forma limitada.

No se genera una lista masiva de municipios.

---

23. B17 — DATOS ESTRUCTURADOS

Función

Representar información estructurada cuando proceda.

Puede incluir información sobre:

- negocio;
- servicio;
- ubicación;
- FAQ;
- otros tipos compatibles.

Restricciones

Nunca inventar datos estructurados.

La información estructurada debe corresponder con los datos reales de la página.

---

24. B18 — TESTIMONIOS

Solo cuando existan testimonios reales y autorizados.

Datos posibles:

- texto;
- autor;
- fecha;
- fuente.

Nunca generar testimonios ficticios.

---

25. B19 — CASOS / EJEMPLOS

Puede mostrar:

- problema;
- contexto;
- actuación;
- resultado.

Solo cuando exista información suficiente.

No presentar casos inventados como reales.

---

26. B20 — GALERÍA

Puede mostrar imágenes relevantes.

Datos:

- URL;
- ALT;
- título;
- fuente;
- licencia;
- relación con la página.

No se atribuyen imágenes a un negocio si no corresponde.

---

27. B21 — PRECIO / TARIFAS

Solo cuando exista información comercial real.

Datos:

- precio;
- moneda;
- unidad;
- condiciones.

Nunca inventar precios.

---

28. B22 — HORARIOS

Solo cuando existan horarios reales.

Datos:

- días;
- apertura;
- cierre;
- excepciones.

Si no existen:

OMITIR.

---

29. B23 — MAPA / UBICACIÓN

Puede incluir:

- dirección;
- coordenadas;
- mapa;
- zona de atención.

Solo si existe información válida.

No inventar una ubicación física.

---

30. BLOQUES OBLIGATORIOS DE UNA PÁGINA

Como base:

B01 HEADER
B02 NAVEGACIÓN
B03 HERO
B04 CONTENIDO PRINCIPAL
B06 FOOTER

B05 CTA será obligatorio cuando exista un canal de conversión válido.

---

31. BLOQUES CONDICIONALES

Se seleccionan según la página.

Ejemplo para:

"/fontanero-marbella/desatascos/"

podrían utilizarse:

B03 HERO
B04 CONTENIDO
B07 SUBSERVICIO
B08 PROBLEMAS
B09 INFORMACIÓN LOCAL
B10 COBERTURA
B11 PROCESO
B13 DIFERENCIACIÓN
B14 FAQ
B15 SERVICIOS RELACIONADOS
B05 CTA

No tienen que utilizarse todos.

---

32. BLOQUES DE LA MINIWEB COMPLETA

La miniweb no debe depender de una única landing.

Ejemplo:

FONTANERO MARBELLA

INICIO
B01
B02
B03
B04
B15
B05
B06

SERVICIOS
B01
B02
B03
B04
B15
B06

DESATASCOS
B01
B02
B03
B04
B07
B08
B09
B10
B11
B13
B14
B15
B05
B06

24 HORAS
B01
B02
B03
B04
B08
B11
B13
B14
B05
B06

CONTACTO
B01
B02
B04
B05
B23
B06

Esta estructura es orientativa.

Los bloques definitivos dependerán de los datos disponibles.

---

33. REGLA DE SELECCIÓN

Para cada página se debe determinar:

page_id
↓
tipo_pagina
↓
intención
↓
datos disponibles
↓
bloques necesarios
↓
bloques opcionales
↓
bloques omitidos

La selección debe quedar registrada antes de generar el contenido.

---

34. REGLA DE OMISIÓN

Un bloque se omite cuando:

- no aporta valor;
- no existe información;
- la información es insuficiente;
- generaría contenido genérico;
- aumenta el riesgo de duplicación;
- obliga a inventar;
- no corresponde a la intención.

OMITIR ES CORRECTO.

---

35. REGLA DE FALLBACK

Cuando un bloque no pueda construirse:

DATOS ESPECÍFICOS
↓
VERSIÓN GENERAL SEGURA
↓
OMITIR
↓
REVISIÓN

Nunca:

DATOS INSUFICIENTES
↓
INVENTAR

---

36. DIFERENCIACIÓN ENTRE PÁGINAS

Dos páginas pueden utilizar los mismos bloques.

Eso no significa que deban tener el mismo contenido.

Ejemplo:

Desatascos Marbella

y:

Desatascos Cártama

pueden utilizar:

- Hero;
- contenido;
- problemas;
- FAQ;
- CTA.

Pero la información específica debe proceder de cada contexto.

Si no existe diferenciación suficiente:

AGRUPAR / NO CREAR

según el motor.

---

37. REGLA DE NO RELLENO

No se crean bloques para aumentar:

- palabras;
- keywords;
- headings;
- enlaces;
- longitud.

Cada bloque debe responder:

¿Qué aporta al usuario?

Si no existe una respuesta clara:

OMITIR.

---

38. ESTRUCTURA LÓGICA

Cada bloque tendrá conceptualmente:

id
type
position
enabled
data
conditions
restrictions
fallback

Ejemplo:

{
  "id": "B03",
  "type": "hero",
  "position": 3,
  "enabled": true,
  "data": {
    "h1": "Fontanero en Marbella",
    "subtitle": null,
    "cta": null
  }
}

---

39. RELACIÓN CON EL CONTRATO IA

La IA recibe:

- page_id;
- miniweb_id;
- tipo de página;
- URL;
- intención;
- datos;
- evidencias;
- bloques autorizados;
- restricciones.

La IA puede generar contenido dentro de esos límites.

No puede:

- crear nuevos bloques;
- modificar IDs;
- cambiar URL;
- cambiar localidad;
- cambiar servicio;
- crear páginas adicionales;
- cambiar la arquitectura.

---

40. RELACIÓN CON N8N

N8N transportará:

miniweb
↓
página
↓
bloques
↓
datos
↓
contenido

Debe validar:

- ID de página;
- ID de bloque;
- URL;
- datos obligatorios;
- restricciones.

Si aparece un bloque desconocido:

ERROR

La página no debe publicarse automáticamente.

---

41. RELACIÓN CON WORDPRESS

WordPress será responsable de representar visualmente los bloques.

Conceptualmente:

B03
↓
COMPONENTE HERO

B08
↓
COMPONENTE PROBLEMAS

B14
↓
COMPONENTE FAQ

El bloque lógico y el componente visual pueden ser diferentes internamente.

Esto permite cambiar el diseño sin modificar el sistema lógico.

---

42. MENÚ Y NAVEGACIÓN

La navegación forma parte de la miniweb.

N8N podrá construir el menú a partir de las páginas autorizadas.

Ejemplo:

Inicio
Servicios
Desatascos
24 horas
Fugas
Contacto

El menú no debe incluir automáticamente todas las páginas existentes.

La selección dependerá de:

- importancia;
- navegación;
- conversión;
- experiencia de usuario.

---

43. VALIDACIÓN

Antes de publicar:

- IDs válidos;
- páginas válidas;
- URLs válidas;
- bloques autorizados;
- datos correctos;
- servicio correcto;
- localidad correcta;
- intención correcta;
- CTA válido;
- imágenes válidas;
- FAQ válida;
- datos estructurados válidos;
- ausencia de invenciones;
- ausencia de duplicación evidente.

Si existe un error crítico:

NO PUBLICAR.

---

44. ESCALABILIDAD

El mismo sistema debe permitir:

1 miniweb
↓
10 miniwebs
↓
100 miniwebs
↓
1.000 miniwebs

manteniendo:

- calidad;
- trazabilidad;
- estructura;
- utilidad;
- diferenciación;
- control.

La automatización permite escalar un sistema validado.

No sustituye la validación.

---

45. COMPATIBILIDAD MULTISECTORIAL

Los bloques son reutilizables para:

- fontaneros;
- electricistas;
- abogados;
- carpinteros;
- pintores;
- jardineros;
- reformas;
- otros servicios.

La estructura general permanece.

Los datos cambian según:

- sector;
- servicio;
- localidad;
- intención;
- evidencia.

---

46. PILOTO FONTANERO MARBELLA

El primer piloto debe comprobar una miniweb completa:

FONTANERO MARBELLA
│
├── Inicio
├── Servicios
├── Desatascos
├── 24 horas
├── Fugas
├── Reparación de tuberías
├── Sobre nosotros
└── Contacto

El sistema debe ser capaz de seleccionar bloques diferentes para cada página.

No se debe asumir que todas las páginas utilizan la misma plantilla de contenido.

---

47. REGLA DE NO INVENCIÓN

Está prohibido inventar:

- empresas;
- profesionales;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- disponibilidad;
- cobertura;
- garantías;
- certificaciones;
- experiencia;
- testimonios;
- reseñas;
- casos;
- imágenes;
- datos territoriales;
- URLs.

Los datos desconocidos serán:

"null"

o provocarán:

"REVISAR"

cuando sean imprescindibles.

---

48. VALIDACIÓN DEL SISTEMA

El sistema no se considera validado por estar documentado.

El piloto debe comprobar:

1. selección de bloques;
2. omisión;
3. fallback;
4. diferenciación;
5. generación de varias páginas;
6. navegación;
7. menú;
8. URLs;
9. datos;
10. IA;
11. N8N;
12. WordPress.

---

49. REGLA DE MODIFICACIÓN

Si el piloto detecta un error:

1. registrar el caso;
2. identificar el bloque afectado;
3. identificar la regla responsable;
4. modificar la documentación;
5. incrementar versión;
6. repetir la prueba;
7. registrar el cambio.

No se modifica el sistema para forzar un resultado.

---

50. ESTADO ACTUAL

Versión: 3.0

Estado: PREPARADO PARA PILOTO DE MINIWEB

El sistema de bloques queda preparado para trabajar no solo con landings individuales, sino con miniwebs completas y sus páginas internas.

Los IDs B01–B23 permanecen estables.

La selección depende de:

- página;
- intención;
- datos;
- evidencias;
- utilidad;
- diferenciación;
- restricciones.

---

51. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza el sistema de bloques a la versión 3.0.

Cambios principales:

- adaptación del sistema de bloques al concepto de miniweb;
- diferenciación entre página principal y páginas internas;
- incorporación explícita del concepto de "page_id" y "miniweb_id";
- definición de selección de bloques por página;
- preparación para construcción de menú y navegación;
- preparación para generación de varias páginas;
- alineación con arquitectura de URLs v3.0;
- mantenimiento de los identificadores B01–B23;
- refuerzo de las reglas de omisión y fallback;
- preparación para el piloto completo de Fontanero Marbella;
- separación entre bloque lógico y componente visual de WordPress.

---

FIN DEL SISTEMA DE BLOQUES
