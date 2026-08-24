MODELO DE RENDERIZADO WORDPRESS

Versión: 1.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir cómo se transforma la estructura lógica generada por la IA en páginas reales de WordPress utilizando un tema visual y plantillas reutilizables, con Kadence como referencia para el piloto.

---

1. FUNCIÓN

Este documento define el puente entre:

JSON generado por IA → N8N → WordPress → plantillas visuales → página publicada

El documento no define el diseño visual definitivo.

Define cómo debe funcionar técnicamente el sistema de renderizado.

La IA genera:

- estructura;
- contenido;
- datos;
- bloques autorizados;
- relaciones;
- enlaces.

WordPress se encarga de:

- utilizar las plantillas;
- aplicar el diseño;
- renderizar el contenido;
- generar el HTML final;
- mostrar la página al usuario.

---

2. PRINCIPIO FUNDAMENTAL

La IA no debe generar libremente el HTML final de WordPress.

La IA trabaja con bloques lógicos previamente definidos.

Ejemplo:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "Fontanero en Estepona",
    "subtitle": "Servicio de fontanería para particulares y negocios",
    "cta": {
      "label": "Solicitar presupuesto",
      "action": "contact"
    }
  }
}

El sistema de WordPress interpreta:

B03 → plantilla Hero

y rellena esa plantilla con los datos recibidos.

---

3. OBJETIVO

El sistema debe permitir:

- crear páginas automáticamente;
- actualizar páginas existentes;
- reutilizar diseños;
- mantener coherencia visual;
- modificar el diseño global sin reconstruir todas las páginas;
- generar cientos o miles de páginas sin crear manualmente cada una;
- mantener separación entre contenido y diseño.

---

4. TEMA VISUAL

Para el piloto se utilizará:

Kadence

Kadence será responsable principalmente de:

- estilos;
- tipografías;
- colores;
- espaciado;
- responsive;
- columnas;
- botones;
- estructura visual;
- componentes reutilizables.

El sistema debe evitar crear un CSS independiente para cada página.

---

5. SEPARACIÓN DE RESPONSABILIDADES

IA

Responsable de:

- contenido;
- textos;
- títulos;
- preguntas;
- respuestas;
- datos estructurados;
- relaciones;
- enlaces;
- selección de bloques autorizados.

Arquitectura

Responsable de:

- páginas;
- URLs;
- jerarquía;
- profundidad;
- bloques autorizados.

Validador

Responsable de:

- comprobar integridad;
- detectar bloques no autorizados;
- detectar URLs incorrectas;
- detectar datos incompatibles;
- impedir publicación cuando exista un error crítico.

N8N

Responsable de:

- recibir el JSON;
- procesarlo;
- comprobar identificadores;
- localizar páginas;
- enviar datos a WordPress;
- crear;
- actualizar;
- registrar resultados;
- gestionar errores.

WordPress

Responsable de:

- almacenar páginas;
- utilizar plantillas;
- renderizar bloques;
- aplicar diseño;
- generar HTML;
- publicar.

Kadence

Responsable de:

- presentación visual.

---

6. CONCEPTO DE PLANTILLA

Cada bloque lógico no implica necesariamente una plantilla visual independiente.

Ejemplo:

B03 puede utilizar una plantilla visual Hero.

B08 puede utilizar una plantilla Problems.

Pero varios bloques pueden compartir una misma estructura visual si resulta conveniente.

Por tanto:

23 bloques lógicos ≠ necesariamente 23 plantillas visuales independientes.

El sistema debe permitir reutilización.

---

7. IDENTIFICADORES

Los bloques utilizarán los identificadores oficiales:

- B01
- B02
- B03
- B04
- B05
- B06
- B07
- B08
- B09
- B10
- B11
- B12
- B13
- B14
- B15
- B16
- B17
- B18
- B19
- B20
- B21
- B22
- B23

No se permiten nuevos identificadores creados libremente por la IA.

---

8. MAPA LÓGICO

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

El mapa debe coincidir con "proyecto/seo/sistema-bloques.md".

---

9. MAPA DE RENDERIZADO

El sistema deberá disponer de una correspondencia:

B01 → Header
B02 → Navigation
B03 → Hero
B04 → Main Content
B05 → CTA
B06 → Footer
B07 → Subservice
B08 → Problems
B09 → Local Context
B10 → Coverage
B11 → Process
B12 → Trust
B13 → Differentiation
B14 → FAQ
B15 → Related Services
B16 → Related Locations
B17 → Structured Data
B18 → Testimonials
B19 → Cases
B20 → Gallery
B21 → Pricing
B22 → Opening Hours
B23 → Map

Este mapa será utilizado por N8N y WordPress.

---

10. PLANTILLAS REUTILIZABLES

Las plantillas deben diseñarse una sola vez.

Ejemplo:

B03 Hero
    ↓
Plantilla Hero Kadence
    ↓
Datos de la página

Si existen:

- Fontanero Estepona;
- Fontanero Manilva;
- Fontanero Casares;
- Fontanero Ronda;

todas pueden utilizar la misma plantilla Hero.

Lo único que cambia son los datos.

---

11. CONTENIDO VARIABLE

Los elementos variables podrán incluir:

- título;
- subtítulo;
- texto;
- listas;
- preguntas;
- respuestas;
- CTA;
- URLs;
- anchors;
- imágenes;
- datos comerciales reales;
- información local respaldada.

El diseño no debe depender del texto concreto.

---

12. CONTENIDO FIJO

Puede existir contenido visual o estructural común:

- clases;
- estructura HTML;
- estilos;
- iconos;
- composición;
- espaciado;
- elementos decorativos;
- componentes visuales.

El contenido fijo no debe utilizarse para introducir afirmaciones comerciales falsas.

---

13. DATOS NULOS

Si un campo no existe:

null

El renderizador debe saber manejar valores nulos.

No debe generar:

- texto falso;
- teléfonos ficticios en páginas reales;
- precios inventados;
- horarios inventados;
- testimonios inventados.

---

14. CAMPOS OPCIONALES

Los bloques pueden contener campos opcionales.

Ejemplo:

{
  "cta": {
    "label": "Solicitar presupuesto",
    "action": "contact",
    "url": null
  }
}

Si no existe un canal de contacto real, el renderizador no debe inventarlo.

---

15. BLOQUES DESACTIVADOS

Un bloque puede tener:

"enabled": false

En ese caso WordPress no debe renderizarlo.

Esto permite conservar una arquitectura común sin mostrar contenido innecesario.

---

16. ORDEN DE LOS BLOQUES

El orden de los bloques será el orden definido en:

pages[].blocks[]

Ejemplo:

B01
B02
B03
B04
B08
B09
B14
B05
B06

WordPress debe respetar ese orden.

---

17. EJEMPLO DE PÁGINA

Conceptualmente:

PAGE
│
├── B01 Header
├── B02 Navigation
├── B03 Hero
├── B04 Main Content
├── B08 Problems
├── B09 Local Context
├── B14 FAQ
├── B05 CTA
└── B06 Footer

El renderizador convierte cada elemento en su representación visual.

---

18. RENDERIZADO

El proceso conceptual será:

SITE_PACKAGE JSON
        ↓
N8N
        ↓
VALIDACIÓN
        ↓
PAGE
        ↓
BLOCK
        ↓
BLOCK ID
        ↓
PLANTILLA
        ↓
DATOS
        ↓
WORDPRESS
        ↓
HTML FINAL

---

19. NO GENERAR HTML LIBRE

La IA no debe controlar directamente:

- clases CSS;
- estilos;
- estructura visual;
- tamaños;
- colores;
- tipografías;
- código JavaScript;
- CSS personalizado.

La IA controla principalmente:

qué contenido debe aparecer.

---

20. WORDPRESS COMO SISTEMA DE RENDERIZADO

WordPress debe recibir una estructura que permita saber:

qué bloque
+
qué datos
+
en qué página
+
en qué posición

El sistema WordPress deberá convertir esa información en una representación visual.

---

21. IMPLEMENTACIÓN CON KADENCE

Durante el piloto se evaluará la forma más sencilla de utilizar Kadence:

- bloques reutilizables;
- patrones;
- plantillas;
- elementos globales;
- campos dinámicos;
- componentes equivalentes disponibles en Kadence.

No se debe asumir todavía una implementación técnica concreta si no ha sido probada.

La elección definitiva se realizará durante la implementación.

---

22. REUTILIZACIÓN

Una misma plantilla puede utilizarse en muchas páginas.

Ejemplo:

B03 Hero
│
├── Estepona
├── Manilva
├── Casares
├── Ronda
├── Cártama
└── Fuengirola

Cada página utiliza los mismos componentes visuales pero diferentes datos.

---

23. ACTUALIZACIÓN GLOBAL

Si se modifica una plantilla global:

B03 Hero

el cambio debe poder afectar a las páginas que utilizan dicha plantilla.

Esto permite mejorar el diseño del proyecto sin editar cientos de páginas manualmente.

---

24. ACTUALIZACIÓN INDIVIDUAL

Si cambia el contenido de una página:

Fontanero en Estepona

N8N debe poder actualizar únicamente sus datos.

No debe ser necesario reconstruir toda la web.

---

25. IDEMPOTENCIA

Cada página tendrá:

opportunity_id
page_id
url

N8N debe utilizar estos identificadores para determinar si debe:

- crear;
- actualizar;
- ignorar;
- revisar.

Una segunda ejecución no debe crear duplicados.

---

26. INTERLINKING

Los enlaces internos también forman parte de los datos.

Ejemplo:

{
  "url": "/fontanero/estepona/desatascos/",
  "anchor": "desatascos en Estepona",
  "target": "FON-EST-P02",
  "reason": "related_service"
}

El renderizador debe convertirlos en enlaces HTML funcionales.

La IA no debe inventar URLs.

Las URLs deben proceder de la arquitectura autorizada.

---

27. INTERLINKING ENTRE LOCALIDADES

El sistema podrá conectar páginas relacionadas:

Fontanero Estepona
        ↓
Fontanero San Pedro
        ↓
Fontanero Manilva
        ↓
Fontanero Casares

Siempre que esas páginas existan y estén autorizadas.

No se deben crear enlaces hacia páginas inexistentes.

---

28. INTERLINKING ENTRE SERVICIOS

También podrá existir:

Fontanero
   ↓
Electricista
   ↓
Pintor
   ↓
Carpintero

pero únicamente cuando la arquitectura del proyecto autorice esa relación.

El enlazado entre pilares debe estar controlado.

No se debe crear una red artificial de enlaces.

---

29. ENLACES EXTERNOS

En este documento, "enlace externo" no significa necesariamente un enlace fuera del dominio.

Los enlaces entre diferentes páginas del mismo proyecto son:

enlaces internos.

Ejemplo:

/fontanero/estepona/

→

/fontanero/manilva/

sigue siendo enlazado interno si ambas páginas pertenecen al mismo dominio.

---

30. IMÁGENES

Las imágenes deberán proceder de datos válidos.

El renderizador recibirá:

{
  "url": "https://...",
  "alt": "...",
  "title": "...",
  "type": "hero"
}

WordPress utilizará el recurso disponible.

No se inventarán URLs de imágenes.

---

31. DATOS ESTRUCTURADOS

B17 puede contener información lógica para datos estructurados.

El renderizador será responsable de generar el formato técnico final cuando corresponda.

La IA no debe generar datos estructurados falsos.

---

32. SEO

El sistema debe poder recibir:

{
  "title": "",
  "meta_description": "",
  "h1": ""
}

y utilizar estos datos para la página.

La implementación concreta dependerá del sistema SEO utilizado en WordPress.

---

33. MENÚ

El menú será generado a partir de:

menu.items[]

Cada elemento deberá apuntar a una URL autorizada.

WordPress deberá poder:

- crear;
- actualizar;
- eliminar;
- ordenar

los elementos del menú mediante N8N.

---

34. PÁGINAS DINÁMICAS

El sistema debe soportar la creación de muchas páginas.

Ejemplo:

Fontanero Málaga
Fontanero Marbella
Fontanero Estepona
Fontanero Manilva
Fontanero Casares
Fontanero Ronda
Fontanero Cártama
...

Todas pueden utilizar el mismo sistema visual.

---

35. ESCALABILIDAD

El diseño debe permitir:

1 página
↓
10 páginas
↓
100 páginas
↓
1.000 páginas

sin necesidad de crear manualmente un diseño diferente para cada localidad.

---

36. CAMBIO DE TEMA

Aunque el piloto utilice Kadence, la estructura lógica no debe depender completamente de Kadence.

El objetivo es:

B03
↓
Renderer
↓
Tema actual

y no:

B03 = código específico inseparable de Kadence

Esto permite cambiar de tema en el futuro.

---

37. PRINCIPIO DE PORTABILIDAD

Los datos de contenido deben poder mantenerse aunque cambie:

- tema;
- diseño;
- plantilla;
- sistema visual.

La información debe estar separada del diseño.

---

38. ERRORES

Si WordPress recibe:

- bloque desconocido;
- datos incompatibles;
- plantilla inexistente;
- página inexistente para actualización;
- URL no autorizada;

debe producirse un error controlado.

No debe generarse una página parcialmente incorrecta sin registrar la incidencia.

---

39. FALLBACK

No debe existir un fallback que permita a la IA generar HTML arbitrario.

Si falta una plantilla:

REVIEW

o:

ERROR

según la gravedad.

---

40. REGISTRO

Cada operación debe poder registrar:

- opportunity_id;
- page_id;
- URL;
- bloque;
- fecha;
- operación;
- resultado;
- error si existe;
- versión del sistema.

Esto permitirá reconstruir qué ocurrió.

---

41. VERSIONADO

El sistema deberá mantener versiones de:

- contrato IA;
- bloques;
- arquitectura;
- renderizador;
- plantillas;
- modelo de datos.

Esto permite saber con qué versión se generó una página.

---

42. FLUJO DE CREACIÓN

El flujo completo será:

LOCALIDAD
+
SERVICIO
↓
INVESTIGACIÓN
↓
DECISIÓN
↓
ARQUITECTURA
↓
DATOS
↓
IA
↓
SITE_PACKAGE JSON
↓
VALIDADOR
↓
N8N
↓
WORDPRESS
↓
PLANTILLAS KADENCE
↓
RENDERIZADO
↓
PÁGINA

---

43. FLUJO DE ACTUALIZACIÓN

NUEVA INFORMACIÓN
↓
IA / DATOS
↓
JSON
↓
VALIDADOR
↓
N8N
↓
page_id
↓
WORDPRESS
↓
ACTUALIZAR DATOS
↓
RENDERIZAR

No se debe crear una segunda página.

---

44. FLUJO DE CAMBIO DE DISEÑO

MODIFICAR PLANTILLA KADENCE
↓
PLANTILLA ACTUALIZADA
↓
PÁGINAS QUE LA UTILIZAN
↓
NUEVO RENDERIZADO

La modificación visual debe mantenerse separada del contenido.

---

45. PILOTO

Antes de automatizar cientos de páginas se deberá probar:

- 1 página;
- varios bloques;
- actualización;
- enlaces internos;
- menú;
- responsive;
- SEO;
- imágenes;
- datos estructurados;
- duplicación;
- errores.

Después:

1 → 3 → 10 → 50 → 100

y únicamente después escalar.

---

46. REGLA DE SEGURIDAD

Nunca debe publicarse automáticamente una página cuando:

- el JSON no sea válido;
- exista un bloque desconocido;
- exista una URL no autorizada;
- falten datos obligatorios;
- exista una plantilla inexistente;
- exista una contradicción de datos protegidos;
- exista un error crítico.

---

47. PRINCIPIO DE NO INVENCIÓN

El renderizador nunca debe inventar contenido.

Si recibe:

"phone": null

no debe convertirlo en:

600 000 000

ni ningún otro número ficticio.

El sistema de datos de prueba podrá utilizar datos ficticios exclusivamente en entornos marcados como:

TEST

---

48. ENTORNO DE PRUEBA

Debe existir una separación entre:

TEST

y:

PRODUCTION

Los datos ficticios utilizados para las pruebas nunca deben publicarse accidentalmente en producción.

---

49. RESPONSABILIDAD DEL DISEÑO

El diseño visual no pertenece a la IA.

Pertenece a:

WordPress + Kadence + plantillas

La IA únicamente determina:

- qué bloques utilizar;
- qué contenido introducir;
- qué relaciones establecer;
- qué enlaces autorizados utilizar.

---

50. RESPONSABILIDAD DEL HTML

El HTML final debe ser producido por WordPress y su sistema de plantillas/renderizado.

La IA no debe tener control directo sobre el HTML final.

---

51. RESPONSABILIDAD DEL CSS

El CSS debe proceder principalmente del tema y de las plantillas.

No se debe generar CSS individual para cada localidad.

---

52. RESULTADO ESPERADO

El sistema final debe permitir que una entrada como:

Servicio: fontanero
Localidad: Estepona

pueda producir automáticamente una página completa utilizando:

arquitectura autorizada
+
bloques autorizados
+
contenido generado
+
plantillas visuales
+
interlinking

sin diseñar manualmente la página.

---

53. PRINCIPIO DE ESCALA

El objetivo no es construir:

100 páginas × 100 diseños

sino:

1 sistema visual
+
plantillas reutilizables
+
datos variables
+
muchas páginas

---

54. SIGUIENTE FASE

Una vez aprobado este modelo documental, la siguiente fase será:

IMPLEMENTACIÓN WORDPRESS

Se deberá:

1. instalar/configurar Kadence;
2. crear las primeras plantillas;
3. comprobar cómo representar los bloques;
4. definir el método técnico de inserción de datos;
5. probar una página;
6. comprobar actualización;
7. comprobar interlinking;
8. documentar el método definitivo.

No se debe construir todavía una automatización masiva.

---

55. RELACIÓN CON N8N

N8N no debe conocer detalles visuales.

N8N debe transmitir:

page_id
+
block_id
+
data

WordPress decide cómo renderizarlo.

Esto mantiene separadas:

automatización

de

presentación visual.

---

56. RELACIÓN CON EL CONTRATO IA

El contrato IA define:

qué debe devolver la IA.

Este documento define:

cómo se debe interpretar esa salida para producir una página WordPress.

Ninguno sustituye al otro.

---

57. RELACIÓN CON SISTEMA DE BLOQUES

"proyecto/seo/sistema-bloques.md"

define:

- qué bloques existen;
- qué significa cada bloque;
- qué datos puede utilizar.

Este documento define:

- cómo se representan;
- cómo se relacionan con WordPress;
- cómo se renderizan;
- cómo se reutilizan.

---

58. RELACIÓN CON ARQUITECTURA

La arquitectura determina:

- qué páginas existen;
- qué bloques puede utilizar cada página;
- qué relaciones existen.

El renderizador no puede crear páginas ni bloques por iniciativa propia.

---

59. PRINCIPIO FINAL

La arquitectura decide:

qué existe.

La IA decide:

qué contenido necesita.

N8N decide:

cómo transportar y sincronizar los datos.

WordPress decide:

cómo almacenar y renderizar.

Kadence decide:

cómo se presenta visualmente.

El resultado final debe mantener estas responsabilidades separadas.

---

60. ESTADO DEL DOCUMENTO

Versión: 1.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha: 2026-08-24

Siguiente paso: implementación de las primeras plantillas visuales en WordPress/Kadence y prueba del mecanismo de alimentación de datos.

---

FIN DE MODELO DE RENDERIZADO WORDPRESS
