SISTEMA DE BLOQUES

1. FUNCIÓN

Este documento define los bloques que pueden formar una landing SEO local y las reglas que determinan cuándo deben utilizarse.

Su función es convertir la arquitectura general de landing en una estructura que pueda interpretar una IA y posteriormente ejecutar N8N.

Este documento no decide si una landing debe existir.

La decisión de crear una landing procede del motor de decisión.

El flujo es:

OPORTUNIDAD

↓

MOTOR

↓

CREAR

↓

URL

↓

ARQUITECTURA DE LANDING

↓

SISTEMA DE BLOQUES

↓

MODELO DE DATOS

↓

IA

↓

VALIDACIÓN

↓

PUBLICACIÓN

---

2. PRINCIPIO FUNDAMENTAL

Los bloques no deben utilizarse para rellenar páginas.

Cada bloque debe cumplir al menos una función real:

- Resolver una necesidad del usuario.
- Explicar el servicio.
- Aportar información local.
- Facilitar una conversión.
- Generar confianza mediante información verificable.
- Mejorar la navegación.
- Resolver una pregunta relevante.
- Diferenciar la página de otras páginas.

Si un bloque no aporta valor o no dispone de datos suficientes, debe omitirse.

---

3. TIPOS DE BLOQUES

Existen tres categorías.

3.1 BLOQUES OBLIGATORIOS

Elementos estructurales mínimos que normalmente deben existir en toda landing.

3.2 BLOQUES CONDICIONALES

Se utilizan únicamente cuando la intención, los datos o las evidencias justifican su presencia.

3.3 BLOQUES OPCIONALES

Se utilizan cuando aportan valor adicional y existen datos suficientes.

---

4. BLOQUES OBLIGATORIOS

B01 — HEADER

Función

Proporcionar la navegación global y la identidad del sitio.

Contenido

- Logo.
- Marca.
- Navegación principal.
- CTA global cuando corresponda.

Datos necesarios

- Identidad de marca.
- URLs globales.
- CTA comercial.

Regla

El header es global.

No debe generarse uno diferente para cada municipio.

---

B02 — NAVEGACIÓN

Función

Permitir acceder a las áreas principales del sitio.

Puede incluir

- Servicios.
- Localidades estratégicas.
- Contacto.
- Otras páginas globales.

Regla

Solo se enlazarán URLs existentes o previamente validadas.

No se deben generar miles de enlaces únicamente por motivos SEO.

---

B03 — HERO

Función

Explicar inmediatamente qué ofrece la página y dónde.

Contenido

- H1.
- Subtítulo.
- CTA principal.
- Elementos de confianza cuando existan.

Datos necesarios

- Servicio.
- Subservicio.
- Localidad.
- Intención.
- CTA.

Regla

El hero debe identificar claramente la intención principal.

---

B04 — CONTENIDO PRINCIPAL

Función

Explicar el servicio o necesidad principal de la página.

Contenido

Dependerá de la oportunidad.

Puede incluir:

- explicación del servicio;
- problemas que resuelve;
- situaciones habituales;
- alcance;
- información útil.

Datos necesarios

- Servicio.
- Subservicio.
- Intención.
- Evidencias.
- Información validada.

Regla

Nunca debe convertirse en texto genérico repetido.

---

B05 — CTA PRINCIPAL

Función

Facilitar la acción principal del usuario.

Posibles acciones

- Llamar.
- WhatsApp.
- Solicitar presupuesto.
- Solicitar cita.
- Contactar.

Datos necesarios

- Canal de contacto real.
- CTA autorizado.

Regla

Nunca inventar teléfonos, disponibilidad, tiempos de respuesta o precios.

---

B06 — FOOTER

Función

Cerrar la navegación y proporcionar información global.

Puede contener

- Servicios.
- Navegación.
- Contacto.
- Información legal.
- Localidades estratégicas.

Regla

El footer es global y no debe utilizarse para crear una red masiva de enlaces.

---

5. BLOQUES CONDICIONALES

B07 — SUBSERVICIO

Se utiliza cuando

La oportunidad tiene un subservicio definido.

Ejemplo:

Servicio: Fontanero
Subservicio: Desatascos
Localidad: Marbella

Función

Explicar específicamente el subservicio.

Regla

La página debe estar centrada en el subservicio y no limitarse a cambiar el título de una página genérica.

---

B08 — PROBLEMAS / NECESIDADES

Se utiliza cuando

La investigación demuestra que existen problemas o necesidades concretas relacionadas con la intención.

Ejemplo

Para desatascos:

- atasco de fregadero;
- atasco de tubería;
- problemas de desagüe;
- obstrucciones.

Regla

Solo se incluyen problemas relevantes y respaldados por información disponible.

---

B09 — INFORMACIÓN LOCAL

Se utiliza cuando

Existe información local suficiente y relevante.

Puede contener

- características del municipio;
- contexto residencial;
- contexto turístico;
- tipos de vivienda;
- necesidades específicas;
- particularidades locales.

Regla

No se debe inventar información local.

La localidad por sí sola no constituye contenido local suficiente.

---

B10 — ZONAS / COBERTURA

Se utiliza cuando

Existe información real sobre las zonas atendidas.

Puede contener

- barrios;
- urbanizaciones;
- pedanías;
- zonas;
- municipios cercanos.

Regla

Solo incluir zonas realmente atendidas o documentalmente justificadas.

No crear listas artificiales de localidades.

---

B11 — PROCESO

Se utiliza cuando

Explicar el proceso aporta valor al usuario.

Estructura posible

1. Contacto.
2. Evaluación.
3. Actuación.
4. Resolución.
5. Seguimiento.

Regla

El proceso debe corresponder a la realidad del servicio.

---

B12 — ELEMENTOS DE CONFIANZA

Se utiliza cuando

Existen señales reales y verificables.

Puede incluir

- experiencia;
- certificaciones;
- garantías;
- horarios;
- reseñas;
- cobertura;
- datos comerciales.

Regla

No fabricar ninguna señal de confianza.

---

B13 — DIFERENCIACIÓN

Se utiliza cuando

Existe información que hace que la página sea sustancialmente útil y distinta.

Puede proceder de

- intención específica;
- servicio;
- subservicio;
- información local;
- problema concreto;
- tipo de cliente;
- cobertura;
- información propia.

Regla

Cambiar únicamente el nombre del municipio no constituye diferenciación.

---

B14 — FAQ

Se utiliza cuando

La investigación o la intención muestran preguntas relevantes.

Fuentes posibles

- preguntas observadas;
- investigación;
- conocimiento real del servicio;
- información comercial;
- evidencias.

Regla

No crear preguntas artificiales únicamente para introducir keywords.

Las respuestas deben poder justificarse.

---

B15 — SERVICIOS RELACIONADOS

Se utiliza cuando

Existen servicios relacionados que ayudan al usuario y tienen una URL válida.

Puede enlazar hacia

- servicio superior;
- subservicios;
- servicios complementarios.

Regla

No enlazar a páginas inexistentes.

No generar enlaces únicamente por coincidencia semántica.

---

B16 — LOCALIDADES RELACIONADAS

Se utiliza cuando

Existen localidades relacionadas que forman parte de la arquitectura real del sitio.

Función

Facilitar navegación entre localidades relevantes.

Regla

No crear bloques con cientos de localidades.

La selección debe ser limitada y relevante.

---

B17 — DATOS ESTRUCTURADOS

Se utiliza cuando

El tipo de página y los datos disponibles permiten utilizar datos estructurados válidos.

Regla

Nunca generar datos estructurados con información inventada.

La implementación técnica se definirá en la fase correspondiente.

---

6. BLOQUES OPCIONALES

B18 — TESTIMONIOS

Solo puede utilizarse si existen testimonios reales y autorizados.

No se deben generar testimonios ficticios.

---

B19 — CASOS / EJEMPLOS

Puede utilizarse cuando existan casos reales o ejemplos suficientemente documentados.

No deben inventarse trabajos realizados.

---

B20 — GALERÍA

Puede utilizarse cuando existan imágenes reales y relevantes.

Las imágenes deben corresponder al servicio o negocio.

---

B21 — PRECIO / TARIFAS

Solo puede utilizarse cuando exista información comercial real y autorizada.

No se deben inventar precios.

---

B22 — HORARIOS

Solo puede utilizarse cuando existan horarios reales.

No se deben inferir horarios.

---

B23 — MAPA / UBICACIÓN

Solo cuando exista información de ubicación válida y su inclusión tenga sentido.

No se deben inventar direcciones.

---

7. REGLAS DE SELECCIÓN

La IA no debe decidir libremente qué bloques utilizar.

Debe recibir una selección de bloques determinada por reglas.

Conceptualmente:

OPORTUNIDAD
↓
DATOS DISPONIBLES
↓
INTENCIÓN
↓
REGLAS
↓
BLOQUES SELECCIONADOS

---

8. MATRIZ DE SELECCIÓN

Bloque| Tipo| Condición
Header| Obligatorio| Siempre
Navegación| Obligatorio| Siempre
Hero| Obligatorio| Siempre
Contenido principal| Obligatorio| Siempre
CTA| Obligatorio| Siempre
Footer| Obligatorio| Siempre
Subservicio| Condicional| Existe subservicio
Problemas| Condicional| Existen necesidades relevantes
Información local| Condicional| Existen datos locales útiles
Cobertura| Condicional| Existe cobertura confirmada
Proceso| Condicional| Aporta valor y existe información
Confianza| Condicional| Existen señales verificables
Diferenciación| Condicional| Existe información diferenciadora
FAQ| Condicional| Existen preguntas relevantes
Servicios relacionados| Condicional| Existen URLs válidas
Localidades relacionadas| Condicional| Existen relaciones relevantes
Datos estructurados| Condicional| Procede y existen datos válidos
Testimonios| Opcional| Existen testimonios reales
Casos| Opcional| Existen casos reales
Galería| Opcional| Existen imágenes reales
Precio| Opcional| Existe precio autorizado
Horarios| Opcional| Existen horarios reales
Mapa| Opcional| Existe ubicación válida

---

9. ORDEN DE BLOQUES

El orden base recomendado es:

HEADER

NAVEGACIÓN

HERO

CONTENIDO PRINCIPAL

SUBSERVICIO
(si corresponde)

PROBLEMAS / NECESIDADES
(si corresponde)

INFORMACIÓN LOCAL
(si corresponde)

COBERTURA
(si corresponde)

PROCESO
(si corresponde)

ELEMENTOS DE CONFIANZA
(si corresponde)

SERVICIOS RELACIONADOS
(si corresponde)

FAQ
(si corresponde)

CTA

FOOTER

Los bloques opcionales podrán insertarse donde su función tenga sentido.

---

10. REGLA DE OMISIÓN

Un bloque debe omitirse cuando:

- no aporta valor;
- no existe información suficiente;
- necesita datos que no están disponibles;
- provocaría contenido genérico;
- produciría duplicación;
- podría obligar a la IA a inventar información.

Omitir un bloque es preferible a rellenarlo artificialmente.

---

11. REGLA DE FALLBACK

Cuando un bloque condicional no puede construirse correctamente:

Nivel 1

Utilizar información específica disponible.

Nivel 2

Utilizar una versión general y segura.

Nivel 3

Omitir el bloque.

Nivel 4

Enviar a revisión humana.

Nunca utilizar contenido inventado como fallback.

---

12. REGLA DE DIFERENCIACIÓN

Dos landings pueden compartir bloques.

Eso no significa que deban compartir el mismo contenido.

La diferenciación debe proceder de los datos reales de cada oportunidad.

Ejemplo:

Landing A
Fontanero + Desatascos + Marbella

Landing B
Fontanero + Desatascos + Cártama

Ambas pueden tener:

- Hero.
- Servicio.
- Problemas.
- FAQ.
- CTA.

Pero el contenido específico debe depender de:

- localidad;
- intención;
- evidencias;
- información local;
- cobertura;
- datos disponibles.

---

13. REGLA DE NO RELLENO

Está prohibido generar bloques únicamente para aumentar:

- longitud;
- número de palabras;
- densidad de keywords;
- número de headings;
- número de enlaces.

La pregunta siempre debe ser:

¿Este bloque ayuda realmente al usuario?

Si la respuesta es no, se elimina.

---

14. REGLA DE COMPATIBILIDAD CON CUALQUIER SERVICIO

El sistema de bloques debe ser reutilizable para otros sectores.

Ejemplo:

Fontanero
↓
Desatascos
↓
Marbella

puede utilizar:

Hero
Servicio
Problemas
Local
Cobertura
FAQ
CTA

Mientras que:

Abogado
↓
Derecho laboral
↓
Málaga

puede utilizar:

Hero
Servicio
Situaciones
Proceso
Especialización
FAQ
CTA

La arquitectura es común.

La selección de bloques depende del servicio y de la información disponible.

---

15. IDENTIFICACIÓN DE BLOQUES

Cada bloque tendrá un identificador estable.

Ejemplo:

B01 = HEADER
B02 = NAVEGACIÓN
B03 = HERO
B04 = CONTENIDO PRINCIPAL
B05 = CTA
B06 = FOOTER
B07 = SUBSERVICIO
...

Los identificadores no deben cambiar sin documentar la modificación.

Esto permitirá que N8N y la IA trabajen con bloques de forma estructurada.

---

16. ESTRUCTURA DE UN BLOQUE

Cada bloque deberá poder representarse conceptualmente como:

id
nombre
tipo
función
posición
condiciones
datos_necesarios
reglas
restricciones
fallback

Ejemplo:

id = B10
nombre = Información local
tipo = condicional
función = aportar contexto local útil
posición = después del contenido principal
condiciones = existen datos locales relevantes
datos_necesarios = información_local
fallback = omitir

---

17. RELACIÓN CON IA

La IA no recibe únicamente:

«"Crea una landing de fontanero en Marbella."»

Recibe una especificación estructurada.

Ejemplo:

SERVICIO
Fontanero

SUBSERVICIO
Desatascos

LOCALIDAD
Marbella

URL
/fontanero/desatascos/marbella/

BLOQUES
B01
B02
B03
B04
B07
B08
B09
B10
B14
B05
B06

DATOS
...

RESTRICCIONES
...

EVIDENCIAS
...

La IA genera contenido dentro de esta estructura.

---

18. RELACIÓN CON N8N

N8N debe poder convertir los bloques seleccionados en entradas para la IA.

Flujo conceptual:

Oportunidad
↓
Datos
↓
Reglas de bloques
↓
Lista de bloques
↓
Preparación de contexto
↓
IA
↓
Contenido por bloque
↓
Validación
↓
WordPress

---

19. SALIDA ESPERADA

La IA no debería devolver únicamente un texto largo.

Debe devolver contenido identificable por bloque.

Ejemplo conceptual:

B03_HERO
{
  h1: "...",
  subtitulo: "...",
  cta: "..."
}

B04_CONTENIDO
{
  titulo: "...",
  contenido: "..."
}

B08_PROBLEMAS
{
  titulo: "...",
  elementos: [...]
}

B14_FAQ
{
  preguntas: [...]
}

B05_CTA
{
  titulo: "...",
  texto: "...",
  accion: "..."
}

El formato técnico definitivo se definirá en el modelo de datos y en la implementación de N8N.

---

20. VALIDACIÓN POR BLOQUE

Cada bloque deberá poder validarse independientemente.

Ejemplos:

B03_HERO
✓ H1 existe
✓ localidad correcta
✓ servicio correcto
✓ CTA válido

B09_LOCAL
✓ datos respaldados
✓ localidad correcta
✓ no contiene afirmaciones inventadas

B14_FAQ
✓ preguntas relevantes
✓ respuestas verificables

Esto permite detectar errores antes de publicar toda la página.

---

21. BLOQUES Y SEO

Los bloques no se crean exclusivamente para SEO.

SEO es una consecuencia de una arquitectura útil y correctamente estructurada.

Cada bloque debe priorizar:

1. utilidad;
2. claridad;
3. intención;
4. información real;
5. diferenciación.

Las keywords se incorporarán naturalmente cuando correspondan.

---

22. BLOQUES Y CONVERSIÓN

Los bloques también deben ayudar a convertir cuando la intención sea comercial.

El sistema debe identificar:

- momento adecuado para CTA;
- información necesaria antes de contactar;
- objeciones;
- preguntas;
- señales de confianza.

No se debe saturar la página con CTAs.

---

23. REUTILIZACIÓN A ESCALA

La misma biblioteca de bloques debe poder utilizarse para:

- 1 página;
- 5 páginas;
- 100 páginas;
- 1.000 páginas.

La diferencia debe proceder de los datos y reglas.

No de copiar y pegar contenido.

---

24. EJEMPLO

Oportunidad:

Servicio: Fontanero
Subservicio: Desatascos
Localidad: Marbella
Decisión: CREAR
URL: /fontanero/desatascos/marbella/

Bloques seleccionados:

B01 Header
B02 Navegación
B03 Hero
B04 Contenido principal
B07 Subservicio
B08 Problemas
B09 Información local
B10 Cobertura
B11 Proceso
B12 Confianza
B14 FAQ
B05 CTA
B06 Footer

Si no existen datos reales para B10 Cobertura:

B10 = OMITIR

No se inventan zonas.

---

25. EJEMPLO DE CINCO LANDINGS

Si entran cinco oportunidades:

OPP001
OPP002
OPP003
OPP004
OPP005

cada una pasa por las mismas reglas.

Resultado:

OPP001
→ URL001
→ bloques001
→ contenido001

OPP002
→ URL002
→ bloques002
→ contenido002

OPP003
→ URL003
→ bloques003
→ contenido003

OPP004
→ URL004
→ bloques004
→ contenido004

OPP005
→ URL005
→ bloques005
→ contenido005

No es obligatorio que las cinco tengan exactamente los mismos bloques.

---

26. REGLA DE CONSISTENCIA

Todas las landings deben mantener consistencia en:

- navegación;
- identidad de marca;
- estructura general;
- CTA global;
- diseño;
- componentes técnicos;
- convenciones SEO.

La personalización debe producirse principalmente en:

- servicio;
- subservicio;
- localidad;
- intención;
- datos;
- evidencias;
- bloques condicionales;
- contenido.

---

27. DEPENDENCIAS

Este documento depende de:

- "metodologia.md"
- "arquitectura-seo.md"
- "arquitectura-urls.md"
- "arquitectura-landing.md"
- motor de decisión
- matrices
- evidencias
- oportunidades

Y alimentará posteriormente:

- "modelo-datos.md"
- "prompts.md"
- "validacion.md"
- automatización N8N
- integración WordPress.

---

28. ESTADO

SISTEMA DE BLOQUES DEFINIDO — PENDIENTE DE FORMALIZACIÓN DEL MODELO DE DATOS

Este documento define:

- biblioteca de bloques;
- tipos;
- funciones;
- condiciones;
- orden;
- reglas;
- fallback;
- relación con IA;
- relación con N8N.

No define todavía todos los campos técnicos de entrada y salida.

Eso corresponde a:

"proyecto/seo/modelo-datos.md"

---

29. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se crea el sistema de bloques.

Se establece:

- separación entre bloques obligatorios, condicionales y opcionales;
- identificación estable de cada bloque;
- reglas de selección;
- reglas de omisión;
- reglas contra la invención;
- fallback;
- estructura de salida por bloque;
- validación independiente;
- reutilización para múltiples servicios;
- escalabilidad para múltiples landings.

Siguiente documento:

"proyecto/seo/modelo-datos.md"
