SISTEMA DE BLOQUES

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Proyecto: Plataforma de landings locales automatizadas

---

1. FUNCIÓN

Este documento define los bloques lógicos que pueden formar una landing SEO local.

Define:

- qué bloques existen;
- para qué sirve cada uno;
- cuándo puede utilizarse;
- qué información necesita;
- cuándo debe omitirse;
- qué restricciones tiene;
- cómo debe comunicarse con la IA, N8N y WordPress.

Este documento no decide si una landing debe existir.

La decisión procede del:

"proyecto/seo/motor-decision.md"

El flujo general es:

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
CREAR
↓
ARQUITECTURA URL
↓
ARQUITECTURA LANDING
↓
SISTEMA DE BLOQUES
↓
MODELO DE DATOS
↓
CONTRATO IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

---

2. PRINCIPIO FUNDAMENTAL

Los bloques no existen para rellenar páginas.

Cada bloque debe cumplir una función real.

Puede servir para:

- resolver una necesidad;
- explicar un servicio;
- aportar información local;
- facilitar una conversión;
- generar confianza;
- mejorar la navegación;
- responder preguntas;
- diferenciar la página;
- aportar información comercial;
- mostrar información visual útil.

Si un bloque no aporta valor o no dispone de información suficiente:

SE OMITE.

Es preferible una página con menos bloques útiles que una página llena de contenido artificial.

---

3. CATEGORÍAS

Existen tres categorías.

3.1 BLOQUES ESTRUCTURALES

Forman parte de la estructura general del sitio.

- B01 Header
- B02 Navegación
- B06 Footer

3.2 BLOQUES DE CONTENIDO

Forman el contenido principal de la landing.

- B03 Hero
- B04 Contenido principal
- B07 Subservicio
- B08 Problemas / necesidades
- B09 Información local
- B10 Zonas / cobertura
- B11 Proceso
- B12 Confianza
- B13 Diferenciación
- B14 FAQ
- B18 Testimonios
- B19 Casos / ejemplos
- B21 Precio / tarifas
- B22 Horarios
- B23 Mapa / ubicación

3.3 BLOQUES DE NAVEGACIÓN / CONVERSIÓN / DATOS

- B05 CTA
- B15 Servicios relacionados
- B16 Localidades relacionadas
- B17 Datos estructurados
- B20 Galería

---

4. IDENTIFICACIÓN OFICIAL

Los bloques utilizan identificadores estables:

B01
B02
B03
...
B23

Los identificadores forman parte del contrato entre:

SISTEMA DE BLOQUES
↓
CONTRATO IA
↓
N8N
↓
WORDPRESS

No deben modificarse sin actualizar la documentación dependiente.

La IA no puede inventar nuevos IDs.

---

5. B01 — HEADER

Función

Proporcionar identidad y navegación global.

Contenido

Puede incluir:

- logo;
- marca;
- navegación;
- CTA global.

Datos necesarios

- identidad de marca;
- URLs globales;
- CTA autorizado.

Condición

Siempre que la plantilla general lo utilice.

Restricciones

El header es global.

No se crea un header diferente para cada localidad.

---

6. B02 — NAVEGACIÓN

Función

Permitir al usuario acceder a las áreas principales del sitio.

Puede contener

- servicios;
- localidades estratégicas;
- contacto;
- páginas globales.

Datos necesarios

- URLs existentes;
- anchors;
- jerarquía de navegación.

Restricciones

No crear miles de enlaces únicamente por motivos SEO.

No enlazar URLs inexistentes.

No inventar URLs.

---

7. B03 — HERO

Función

Explicar inmediatamente:

qué servicio se ofrece y dónde.

Datos

h1
subtitulo
cta
confianza

Información necesaria

- servicio;
- subservicio cuando corresponda;
- localidad;
- intención;
- CTA autorizado.

Regla

El Hero debe identificar claramente la intención principal.

No debe limitarse a una frase genérica cambiando únicamente el municipio.

---

8. B04 — CONTENIDO PRINCIPAL

Función

Explicar la necesidad principal que resuelve la landing.

Puede contener

- explicación del servicio;
- problemas;
- situaciones;
- alcance;
- beneficios;
- información útil.

Datos necesarios

- servicio;
- subservicio;
- intención;
- evidencias;
- información validada.

Restricciones

No generar contenido genérico repetido.

No rellenar longitud artificialmente.

---

9. B05 — CTA PRINCIPAL

Función

Facilitar la conversión.

Acciones posibles

phone
whatsapp
contact
quote
appointment

Datos

type
text
destination

Restricciones

Nunca inventar:

- teléfono;
- WhatsApp;
- email;
- precio;
- disponibilidad;
- tiempos de respuesta;
- condiciones comerciales.

Si el canal real no existe:

no se crea el CTA correspondiente.

---

10. B06 — FOOTER

Función

Cerrar la página y proporcionar navegación global.

Puede contener

- servicios;
- contacto;
- navegación;
- información legal;
- localidades estratégicas.

Restricciones

No utilizarlo como mecanismo de generación masiva de enlaces SEO.

El footer es global.

---

11. B07 — SUBSERVICIO

Función

Explicar un subservicio específico.

Condición

Existe un subservicio validado.

Ejemplo:

Servicio: Fontanero
Subservicio: Desatascos
Localidad: Marbella

Regla

La página debe resolver una intención realmente específica.

No basta con cambiar el título de una landing general.

---

12. B08 — PROBLEMAS / NECESIDADES

Función

Mostrar los problemas concretos que puede resolver el servicio.

Ejemplo

Para desatascos:

- atasco de fregadero;
- obstrucción de tubería;
- problemas de desagüe;
- atascos.

Condición

Existen necesidades relevantes respaldadas por investigación o datos.

Restricciones

No inventar problemas.

No introducir keywords artificialmente.

---

13. B09 — INFORMACIÓN LOCAL

Función

Aportar información específica de la localidad cuando realmente ayuda al usuario.

Puede incluir

- características del municipio;
- contexto residencial;
- turismo;
- tipos de vivienda;
- necesidades específicas;
- particularidades geográficas;
- características relevantes del servicio.

Condición

Existe información local suficiente.

Restricciones

La localidad por sí sola no es contenido local.

No inventar particularidades.

No escribir una introducción genérica simplemente cambiando el nombre del municipio.

---

14. B10 — ZONAS / COBERTURA

Función

Mostrar las zonas realmente atendidas.

Puede incluir

- barrios;
- urbanizaciones;
- pedanías;
- zonas;
- municipios cercanos.

Condición

Existe información real sobre cobertura.

Restricciones

Solo incluir zonas realmente atendidas o justificadas.

No crear listas artificiales para SEO.

---

15. B11 — PROCESO

Función

Explicar cómo funciona el servicio.

Ejemplo

1. Contacto
2. Evaluación
3. Actuación
4. Resolución
5. Seguimiento

Condición

Explicar el proceso aporta valor.

Restricciones

El proceso debe corresponder a la realidad.

No inventar pasos.

---

16. B12 — ELEMENTOS DE CONFIANZA

Función

Mostrar señales reales que ayuden al usuario a confiar.

Puede incluir

- experiencia;
- certificaciones;
- garantías;
- horarios;
- reseñas;
- cobertura;
- datos comerciales.

Condición

Existe información verificable.

Restricciones

No fabricar:

- años de experiencia;
- certificaciones;
- garantías;
- reseñas;
- número de clientes;
- premios.

---

17. B13 — DIFERENCIACIÓN

Función

Aportar información que haga que la página sea realmente útil y distinta.

Puede proceder de

- intención específica;
- servicio;
- subservicio;
- información local;
- problemas;
- tipo de cliente;
- cobertura;
- datos propios;
- particularidades verificadas.

Regla fundamental

Cambiar únicamente:

- ciudad;
- título;
- URL;
- sinónimos;
- orden de párrafos;

NO constituye diferenciación.

La diferenciación debe proceder de información útil.

---

18. B14 — FAQ

Función

Resolver preguntas relevantes.

Estructura

question
answer

Fuentes

- investigación;
- preguntas observadas;
- información comercial;
- conocimiento validado;
- evidencias.

Restricciones

No crear preguntas artificiales únicamente para introducir keywords.

No inventar respuestas.

---

19. B15 — SERVICIOS RELACIONADOS

Función

Facilitar la navegación hacia servicios relacionados.

Puede enlazar hacia

- servicio superior;
- subservicios;
- servicios complementarios.

Datos

url
anchor
target
reason

Restricciones

La URL debe existir o estar previamente validada.

No crear enlaces por simple coincidencia semántica.

---

20. B16 — LOCALIDADES RELACIONADAS

Función

Facilitar la navegación entre localidades relevantes.

Condición

Las localidades forman parte de la arquitectura real.

Restricciones

No crear cientos de localidades.

No crear enlaces masivos.

La selección debe ser:

- limitada;
- relevante;
- útil;
- arquitectónicamente válida.

---

21. B17 — DATOS ESTRUCTURADOS

Función

Proporcionar información estructurada cuando proceda.

Puede incluir

- datos de negocio;
- servicio;
- ubicación;
- FAQ;
- otros tipos compatibles con la información disponible.

Condición

El tipo de página y los datos permiten utilizarlo correctamente.

Restricciones

No inventar datos estructurados.

No introducir información que no aparezca realmente en la página o que no esté respaldada.

La implementación técnica corresponde a WordPress.

---

22. B18 — TESTIMONIOS

Función

Aportar confianza mediante experiencias reales.

Condición

Existen testimonios reales y autorizados.

Datos

text
author
date
source

cuando estén disponibles.

Restricciones

No generar testimonios ficticios.

No atribuir opiniones a clientes inexistentes.

---

23. B19 — CASOS / EJEMPLOS

Función

Mostrar situaciones reales o ejemplos documentados.

Condición

Existe información suficiente.

Puede incluir

- problema;
- actuación;
- resultado;
- contexto.

Restricciones

No inventar trabajos realizados.

No presentar ejemplos hipotéticos como casos reales.

---

24. B20 — GALERÍA

Función

Mostrar imágenes relevantes.

Datos

id
url
alt
title
type
source
license

Condición

Existen imágenes reales y relevantes.

Restricciones

No utilizar imágenes inexistentes.

No atribuir al negocio una imagen que no corresponda.

---

25. B21 — PRECIO / TARIFAS

Función

Mostrar precios cuando sea útil y exista información comercial real.

Datos

price
currency
unit
conditions

Condición

Existe precio autorizado.

Restricciones

No inventar precios.

No presentar estimaciones como precios reales.

---

26. B22 — HORARIOS

Función

Mostrar horarios reales.

Datos

days
opening
closing
exceptions

Condición

Existe información actualizada.

Restricciones

No inferir horarios.

Si los horarios no están disponibles:

se omite.

---

27. B23 — MAPA / UBICACIÓN

Función

Mostrar ubicación cuando sea útil.

Puede contener

- dirección;
- coordenadas;
- mapa;
- zona de atención.

Condición

Existe información válida.

Restricciones

No inventar direcciones.

No inventar coordenadas.

No afirmar que existe un establecimiento físico si no está confirmado.

---

28. MATRIZ OFICIAL DE SELECCIÓN

Bloque| Categoría| Condición
B01| Estructural| Según plantilla global
B02| Estructural| Según navegación
B03| Estructural/contenido| Siempre en landing
B04| Contenido| Siempre en landing
B05| Conversión| Si existe CTA válido
B06| Estructural| Según plantilla global
B07| Condicional| Existe subservicio
B08| Condicional| Existen necesidades relevantes
B09| Condicional| Existe información local
B10| Condicional| Existe cobertura real
B11| Condicional| El proceso aporta valor
B12| Condicional| Existen señales verificables
B13| Condicional| Existe diferenciación real
B14| Condicional| Existen preguntas relevantes
B15| Condicional| Existen servicios relacionados válidos
B16| Condicional| Existen localidades relacionadas válidas
B17| Condicional| Procede y existen datos válidos
B18| Opcional| Existen testimonios reales
B19| Opcional| Existen casos reales
B20| Opcional| Existen imágenes
B21| Opcional| Existe precio autorizado
B22| Opcional| Existen horarios
B23| Opcional| Existe ubicación válida

---

29. ORDEN BASE

El orden recomendado es:

B01 HEADER
B02 NAVEGACIÓN
B03 HERO
B04 CONTENIDO PRINCIPAL

B07 SUBSERVICIO
B08 PROBLEMAS
B09 INFORMACIÓN LOCAL
B10 COBERTURA
B11 PROCESO
B12 CONFIANZA
B13 DIFERENCIACIÓN

B15 SERVICIOS RELACIONADOS
B16 LOCALIDADES RELACIONADAS
B14 FAQ

B05 CTA

B06 FOOTER

Los bloques opcionales pueden aparecer donde tengan sentido.

El orden puede modificarse cuando exista una razón de experiencia de usuario.

No se debe modificar únicamente para variar páginas automáticamente.

---

30. REGLA DE OMISIÓN

Un bloque debe omitirse cuando:

- no aporta valor;
- no existen datos;
- la información es demasiado débil;
- produciría contenido genérico;
- aumentaría el riesgo de duplicación;
- obligaría a la IA a inventar;
- no corresponde a la intención;
- no es útil para el usuario.

OMITIR ES UNA DECISIÓN VÁLIDA.

---

31. REGLA DE FALLBACK

Cuando un bloque no puede construirse correctamente:

DATOS ESPECÍFICOS DISPONIBLES
↓
VERSIÓN GENERAL SEGURA
↓
OMITIR
↓
REVISIÓN HUMANA

Nunca:

DATOS INSUFICIENTES
↓
INVENTAR

---

32. REGLA DE DIFERENCIACIÓN ENTRE LANDINGS

Dos páginas pueden utilizar los mismos bloques.

Eso no significa que tengan que tener el mismo contenido.

Ejemplo:

Fontanero + Desatascos + Marbella

y:

Fontanero + Desatascos + Cártama

pueden utilizar:

- B03;
- B04;
- B08;
- B09;
- B14;
- B05.

Pero los datos deben proceder de cada oportunidad.

Si no existe suficiente diferenciación:

AGRUPAR
o
NO CREAR

según el motor de decisión.

---

33. REGLA DE NO RELLENO

Está prohibido crear bloques para aumentar artificialmente:

- palabras;
- headings;
- keywords;
- enlaces;
- longitud;
- contenido.

Cada bloque debe responder a:

¿Qué aporta esto al usuario?

Si no existe una respuesta clara:

OMITIR.

---

34. COMPATIBILIDAD MULTISECTORIAL

Los bloques deben poder reutilizarse en diferentes sectores.

Ejemplo:

FONTANERO
DESATASCOS
MARBELLA

puede utilizar:

B03
B04
B08
B09
B10
B14
B05

Mientras:

ABOGADO
DERECHO LABORAL
MÁLAGA

puede utilizar:

B03
B04
B07
B11
B12
B13
B14
B05

La arquitectura de bloques es común.

La selección depende de:

- sector;
- servicio;
- subservicio;
- intención;
- datos;
- evidencias;
- necesidades del usuario.

---

35. ESTRUCTURA LÓGICA DEL BLOQUE

Cada bloque debe poder representarse conceptualmente como:

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
    "subtitle": "...",
    "cta": {}
  }
}

---

36. RELACIÓN CON EL CONTRATO IA

La IA solo puede devolver:

- bloques autorizados;
- IDs válidos;
- estructura válida;
- datos permitidos.

El contrato oficial es:

"proyecto/seo/contrato-salida-ia.md"

La IA no puede:

- inventar bloques;
- inventar campos;
- modificar IDs;
- cambiar la URL;
- cambiar la decisión SEO;
- inventar información.

---

37. RELACIÓN CON EL MODELO DE DATOS

El sistema de bloques define qué estructura tiene el contenido.

El modelo de datos define cómo se almacenan los datos.

El flujo es:

BLOQUE
↓
DATA
↓
MODELO DE DATOS
↓
N8N
↓
WORDPRESS

No deben existir estructuras paralelas incompatibles.

---

38. RELACIÓN CON WORDPRESS

WordPress será responsable de renderizar los bloques.

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

El bloque lógico y el componente visual no tienen que ser técnicamente idénticos.

Esto permite cambiar el diseño sin modificar la arquitectura lógica.

---

39. RELACIÓN CON N8N

N8N utilizará los identificadores de bloque para transportar y procesar la información.

Ejemplo:

blocks[]
↓
leer id
↓
validar id
↓
validar data
↓
enviar a WordPress

Si aparece un ID desconocido:

ERROR

No se publica.

---

40. VALIDACIÓN

Antes de publicar se debe comprobar:

- IDs válidos;
- bloques autorizados;
- posición válida;
- datos requeridos;
- restricciones;
- URLs;
- CTA;
- imágenes;
- FAQ;
- schema;
- ausencia de datos inventados.

Si falla una condición crítica:

NO PUBLICAR

---

41. VERSIONADO

El sistema de bloques se versiona.

Ejemplos:

v1.0
v1.1
v2.0

Cambios estructurales:

v2.0

Cambios menores:

v2.1

Cuando se modifique un bloque de forma incompatible deberán actualizarse los documentos dependientes.

---

42. VALIDACIÓN REAL

El sistema no se considera validado simplemente porque esté documentado.

Debe probarse con landings reales.

Se comprobarán:

- bloques obligatorios;
- bloques condicionales;
- bloques opcionales;
- omisión;
- fallback;
- diferenciación;
- datos insuficientes;
- casos ambiguos;
- diferentes sectores.

---

43. REGLA DE MODIFICACIÓN

Si durante una prueba se detecta que un bloque produce un resultado incorrecto:

1. registrar el caso;
2. explicar el problema;
3. identificar la regla responsable;
4. modificar la regla;
5. incrementar versión;
6. repetir las pruebas afectadas;
7. registrar el cambio.

No se modifica el sistema únicamente para conseguir un resultado previamente deseado.

---

44. PILOTO

La primera prueba se realizará con una landing real.

Ejemplo:

Fontanero + Marbella

El objetivo será comprobar:

DECISIÓN
↓
BLOQUES
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
LANDING

No se debe escalar antes de comprobar que el proceso completo funciona.

---

45. ESTADO ACTUAL

Versión: v2.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

El sistema de bloques queda definido como una capa lógica independiente de WordPress.

Los identificadores B01–B23 quedan establecidos.

La selección depende de:

- intención;
- datos;
- evidencias;
- utilidad;
- diferenciación;
- restricciones.

La ausencia de datos no debe provocar contenido inventado.

---

46. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza "sistema-bloques.md" a la versión v2.0.

Se consolida la relación entre:

- motor de decisión;
- arquitectura SEO;
- arquitectura de landing;
- sistema de bloques;
- modelo de datos;
- contrato IA;
- N8N;
- WordPress.

Se establecen formalmente los identificadores B01–B23.

Se refuerzan:

- reglas de selección;
- reglas de omisión;
- fallback;
- diferenciación;
- no relleno;
- compatibilidad multisectorial;
- validación;
- versionado;
- idempotencia conceptual;
- separación entre bloque lógico y componente WordPress.

El documento queda preparado para la implementación y validación mediante el primer piloto.
