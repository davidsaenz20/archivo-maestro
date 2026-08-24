ARQUITECTURA DE LANDING SEO

Versión: 2.1
Estado: ACTIVO
Función: definir la arquitectura funcional de una landing SEO antes de generar contenido.

---

1. FUNCIÓN

Define la estructura funcional de una landing SEO generada a partir de una oportunidad que ya ha sido evaluada por el sistema.

La landing no se genera directamente desde keywords.

Flujo:

EVIDENCIAS
↓
OPORTUNIDAD
↓
MOTOR DE DECISIÓN
↓
CREAR
↓
ARQUITECTURA
↓
DATOS
↓
BLOQUES
↓
IA
↓
VALIDACIÓN
↓
PUBLICACIÓN

---

2. PRINCIPIO FUNDAMENTAL

Una landing debe responder a una intención concreta y aportar información útil, específica y diferenciada.

Cambiar únicamente el nombre de una localidad no constituye diferenciación.

La arquitectura debe permitir trabajar a escala sin convertir el sistema en una fábrica de páginas prácticamente idénticas.

La arquitectura se determina antes de generar contenido.

La IA no puede modificar unilateralmente la arquitectura.

---

3. CONDICIÓN DE ENTRADA

Solo se inicia la construcción cuando:

decision_seo = CREAR

La oportunidad debe proceder de:

"proyecto/seo/matriz-oportunidades.md"

y utilizar el modelo definido en:

"proyecto/seo/esquema-datos.md"

Como mínimo debe existir información suficiente sobre:

- opportunity_id;
- sector;
- servicio;
- subservicio, cuando corresponda;
- localización;
- intención;
- evidencias;
- decisión SEO;
- arquitectura necesaria;
- datos disponibles;
- restricciones.

Si falta información necesaria:

null

cuando pueda permanecer ausente.

Si la ausencia impide construir correctamente la página:

REVISAR

---

4. AUTORIDAD DE LA ARQUITECTURA

La arquitectura de landing determina cómo debe construirse la página.

La IA no puede decidir por sí misma:

- crear una página;
- cambiar la URL;
- cambiar el canonical;
- cambiar el servicio;
- cambiar la localidad;
- añadir bloques no autorizados;
- eliminar bloques obligatorios;
- crear enlaces hacia páginas no autorizadas.

Si durante la generación se detecta un problema arquitectónico:

REVISAR

La IA no debe resolverlo modificando silenciosamente la arquitectura.

---

5. ELEMENTOS ARQUITECTÓNICOS

La arquitectura define como mínimo:

- "tipo_pagina"
- "url"
- "url_tipo"
- "canonical"
- "parent_url"
- "profundidad"
- "bloques.seleccionados"

Estos elementos deben estar determinados antes de generar contenido.

---

6. TIPOS DE PÁGINA

Valores iniciales:

servicio_localidad
servicio_subservicio_localidad

Ejemplos:

/fontanero/marbella/

/fontanero/desatascos/marbella/

Los tipos adicionales deberán definirse documentalmente antes de utilizarse.

No se deben crear nuevos tipos de página únicamente porque una combinación de keywords lo sugiera.

---

7. URL

La URL procede de:

"proyecto/seo/arquitectura-urls.md"

La URL no debe utilizarse para justificar la existencia de una página.

Primero:

MOTOR
↓
CREAR

Después:

ARQUITECTURA
↓
URL

La URL debe ser coherente con:

- servicio;
- subservicio;
- localidad;
- tipo de página;
- jerarquía.

---

8. CANONICAL

El canonical debe proceder de la arquitectura definida.

No se genera de forma independiente por la IA.

Debe representar la URL que el sistema considera canónica para esa página.

No se utilizará canonical para ocultar una mala decisión de creación.

---

9. PARENT_URL

Cuando exista jerarquía, "parent_url" debe representar la relación con la página superior.

Ejemplo:

/fontanero/marbella/

puede depender de:

/fontanero/

y:

/fontanero/desatascos/marbella/

puede depender de:

/fontanero/desatascos/

La relación debe proceder de la arquitectura de URLs.

---

10. PROFUNDIDAD

La profundidad representa el nivel de la página dentro de la arquitectura.

No se aumenta la profundidad únicamente para crear más URLs.

Debe existir una relación lógica entre:

- página principal;
- servicio;
- subservicio;
- localidad;
- posibles niveles territoriales adicionales.

---

11. ESTRUCTURA GLOBAL

Una landing puede contener:

1. Header
2. Navegación
3. Hero
4. Contenido principal
5. Problemas / necesidades
6. Información local
7. Cobertura
8. Proceso
9. Confianza
10. Diferenciación
11. FAQ
12. Servicios relacionados
13. Localidades relacionadas
14. CTA
15. Footer

No todas las páginas necesitan todos los elementos.

La selección depende de:

- tipo de página;
- intención;
- datos disponibles;
- evidencias;
- utilidad;
- arquitectura;
- modelo comercial.

---

12. SISTEMA DE BLOQUES

La selección se realiza mediante:

bloques.seleccionados

Identificadores oficiales:

- B01 HEADER
- B02 NAVEGACIÓN
- B03 HERO
- B04 CONTENIDO PRINCIPAL
- B05 CTA PRINCIPAL
- B06 FOOTER
- B07 SUBSERVICIO
- B08 PROBLEMAS / NECESIDADES
- B09 INFORMACIÓN LOCAL
- B10 ZONAS / COBERTURA
- B11 PROCESO
- B12 ELEMENTOS DE CONFIANZA
- B13 DIFERENCIACIÓN
- B14 FAQ
- B15 SERVICIOS RELACIONADOS
- B16 LOCALIDADES RELACIONADAS
- B17 DATOS ESTRUCTURADOS
- B18 TESTIMONIOS
- B19 CASOS / EJEMPLOS
- B20 GALERÍA
- B21 PRECIO / TARIFAS
- B22 HORARIOS
- B23 MAPA / UBICACIÓN

La definición y reglas de los bloques están en:

"proyecto/seo/sistema-bloques.md"

No se deben crear identificadores paralelos.

---

13. BLOQUES OBLIGATORIOS

Una landing funcional debe poder representar como mínimo:

- identidad;
- intención;
- contenido principal;
- navegación;
- CTA;
- footer.

La selección definitiva de bloques debe quedar registrada antes de generar el contenido.

No se debe inventar contenido para completar un bloque.

---

14. BLOQUES CONDICIONALES

Se utilizan únicamente cuando existen datos suficientes y aportan valor real.

Ejemplos:

- B07 Subservicio
- B08 Problemas / necesidades
- B09 Información local
- B10 Zonas / cobertura
- B11 Proceso
- B12 Elementos de confianza
- B13 Diferenciación
- B14 FAQ
- B15 Servicios relacionados
- B16 Localidades relacionadas
- B18 Testimonios
- B19 Casos / ejemplos
- B20 Galería
- B21 Precio / tarifas
- B22 Horarios
- B23 Mapa / ubicación

---

15. REGLA DE BLOQUES

Un bloque no se añade porque exista en la biblioteca.

Debe existir una razón para utilizarlo.

Ejemplo:

B18 TESTIMONIOS solo debe utilizarse si existen testimonios reales y verificables.

B21 PRECIO solo debe utilizarse si existen precios o información comercial válida.

B22 HORARIOS solo debe utilizarse si existen horarios reales.

B23 MAPA solo debe utilizarse cuando la ubicación tenga sentido y exista información válida.

---

16. HERO

Debe identificar inmediatamente:

- servicio;
- subservicio cuando corresponda;
- localidad;
- intención;
- acción principal.

Puede contener:

- H1;
- subtítulo;
- CTA.

No puede incluir afirmaciones comerciales no verificadas.

---

17. H1

Cada landing indexable tendrá un único H1.

Debe corresponder con:

- servicio;
- subservicio cuando exista;
- localidad;
- intención.

Ejemplos:

Fontanero en Marbella

Desatascos en Marbella

El H1 no debe utilizarse para crear una falsa diferenciación entre páginas.

---

18. CONTENIDO PRINCIPAL

Debe explicar la necesidad principal del usuario.

Puede incluir:

- servicio;
- alcance;
- problemas;
- situaciones habituales;
- información útil;
- proceso;
- contexto específico.

No debe utilizarse para rellenar longitud artificialmente.

---

19. INFORMACIÓN LOCAL

Solo se incorpora información local respaldada por evidencias.

Puede incluir:

- zonas;
- barrios;
- urbanizaciones;
- características relevantes;
- tipos de vivienda;
- necesidades locales;
- cobertura;
- contexto territorial.

El nombre del municipio por sí solo no constituye contenido local.

La información local debe aportar utilidad real.

---

20. COBERTURA

Solo se incluyen zonas o localidades cuando:

- la cobertura esté confirmada;
- exista una fuente válida;
- o exista una justificación documental suficiente.

No se crean listas masivas de localidades para aumentar artificialmente la relevancia SEO.

---

21. PROCESO

Puede explicar el proceso real del servicio.

No se inventan:

- procedimientos comerciales;
- tiempos;
- garantías;
- disponibilidad;
- condiciones.

Si el proceso no está documentado:

REVISAR

o se omite el bloque.

---

22. CONFIANZA

Solo se utilizan elementos verificables:

- experiencia;
- certificaciones;
- garantías;
- horarios;
- cobertura;
- reseñas;
- datos comerciales.

Nunca se inventan señales de confianza.

---

23. DIFERENCIACIÓN

Una página debe tener una razón real para existir.

Puede proceder de:

- intención específica;
- servicio;
- subservicio;
- problema;
- contexto local;
- tipo de cliente;
- cobertura;
- información comercial;
- evidencias;
- características reales del mercado.

Cambiar únicamente la localidad no es diferenciación.

La diferenciación debe estar respaldada por los datos de la oportunidad.

---

24. FAQ

Las preguntas deben proceder de:

- intención;
- investigación;
- conocimiento válido del servicio;
- dudas reales del usuario.

No deben generarse únicamente para introducir keywords.

Las respuestas deben ser verificables.

---

25. CTA

Debe corresponder con el modelo comercial disponible.

Ejemplos:

- llamar;
- WhatsApp;
- solicitar presupuesto;
- pedir cita;
- contactar.

No se inventan:

- teléfonos;
- WhatsApp;
- disponibilidad;
- tiempos de respuesta;
- precios.

---

26. NAVEGACIÓN

Solo puede enlazar a URLs autorizadas por la arquitectura.

Puede incluir:

- servicios;
- localidades;
- páginas superiores;
- contacto;
- páginas relacionadas autorizadas.

No se debe enlazar indiscriminadamente a miles de páginas.

---

27. ENLAZADO INTERNO

Los enlaces deben proceder de la arquitectura existente.

No se crean enlaces hacia:

- URLs inexistentes;
- páginas no autorizadas;
- páginas generadas únicamente para crear enlaces;
- páginas descartadas;
- oportunidades que todavía estén en "INVESTIGAR".

---

28. SEO ON-PAGE

La landing debe poder generar:

- title;
- meta description;
- H1;
- headings;
- canonical;
- enlaces internos;
- datos estructurados cuando proceda;
- ALT de imágenes.

Estos elementos se generan a partir de la arquitectura y los datos disponibles.

La IA trabaja dentro de las restricciones recibidas.

---

29. DATOS

La arquitectura utiliza como fuente:

"proyecto/seo/esquema-datos.md"

No se deben crear estructuras paralelas.

Los datos ausentes se representan mediante:

null

o provocan:

REVISAR

cuando sean necesarios para completar correctamente la página.

---

30. EVIDENCIA

Las afirmaciones importantes de la landing deben poder relacionarse con los datos y evidencias de la oportunidad.

La IA no debe presentar como hecho una información que el sistema haya marcado como:

HYPOTHESIS

o:

UNKNOWN

---

31. NO INVENCIÓN

Está prohibido inventar:

- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- disponibilidad;
- empresas;
- técnicos;
- experiencia;
- certificaciones;
- garantías;
- reseñas;
- testimonios;
- zonas;
- cobertura;
- casos;
- imágenes;
- URLs;
- datos territoriales.

La ausencia de información no se soluciona inventándola.

---

32. RELACIÓN CON IA

La IA recibe:

- identidad;
- servicio;
- subservicio;
- localidad;
- intención;
- URL;
- canonical;
- parent_url;
- arquitectura;
- evidencias;
- datos;
- bloques;
- restricciones.

La IA genera contenido.

La IA no decide:

- si la página debe existir;
- URL;
- canonical;
- localidad;
- servicio;
- arquitectura;
- bloques no autorizados;
- publicación.

---

33. RELACIÓN CON N8N

N8N podrá automatizar posteriormente:

OPORTUNIDAD VALIDADA
↓
PREPARAR DATOS
↓
ARQUITECTURA
↓
SELECCIONAR BLOQUES
↓
PREPARAR CONTEXTO
↓
IA
↓
VALIDACIÓN
↓
WORDPRESS
↓
PUBLICACIÓN

N8N no debe saltarse:

- la decisión SEO;
- la arquitectura;
- la validación.

Una oportunidad con:

INVESTIGAR

o:

NO CREAR

no debe publicarse automáticamente.

---

34. VALIDACIÓN

Antes de publicar se comprobará:

- identidad correcta;
- servicio correcto;
- subservicio correcto;
- localidad correcta;
- URL correcta;
- canonical correcto;
- parent_url correcto cuando corresponda;
- intención correcta;
- contenido específico;
- datos respaldados;
- bloques correctos;
- ausencia de invenciones;
- ausencia de duplicación evidente;
- enlaces válidos;
- CTA válido;
- estructura correcta.

Si una comprobación fundamental falla:

NO PUBLICAR

y:

REVISAR

---

35. CONTROL DE DUPLICACIÓN

Antes de publicar una landing se debe comprobar que no sea sustancialmente equivalente a otra página existente.

Se compararán, cuando corresponda:

- intención;
- servicio;
- subservicio;
- información;
- estructura;
- propuesta;
- cobertura;
- contenido local;
- finalidad.

Cambiar únicamente:

- ciudad;
- keyword;
- título;
- URL;

no convierte una página en diferente.

---

36. ESCALABILIDAD

La misma arquitectura debe permitir generar:

- 1 página;
- 10 páginas;
- 100 páginas;
- 1.000 páginas;

sin cambiar las reglas fundamentales.

La escalabilidad nunca justifica reducir:

- calidad;
- veracidad;
- utilidad;
- diferenciación;
- validación.

El sistema debe poder detener automáticamente una página cuando no exista información suficiente.

---

37. EJEMPLO

Oportunidad:

fontanero + Marbella

Decisión:

CREAR

URL:

/fontanero/marbella/

Estructura posible:

B01 HEADER
B02 NAVEGACIÓN
B03 HERO
B04 CONTENIDO PRINCIPAL
B08 PROBLEMAS / NECESIDADES
B09 INFORMACIÓN LOCAL
B11 PROCESO
B13 DIFERENCIACIÓN
B14 FAQ
B05 CTA PRINCIPAL
B06 FOOTER

Los bloques B08, B09, B11, B13 y B14 solo se utilizan si los datos y la intención los justifican.

---

38. EJEMPLO DE SUBSERVICIO

Oportunidad:

fontanero + desatascos + Marbella

Decisión:

CREAR

URL:

/fontanero/desatascos/marbella/

La arquitectura puede incluir:

B01 HEADER
B02 NAVEGACIÓN
B03 HERO
B07 SUBSERVICIO
B04 CONTENIDO PRINCIPAL
B08 PROBLEMAS / NECESIDADES
B09 INFORMACIÓN LOCAL
B10 ZONAS / COBERTURA
B11 PROCESO
B13 DIFERENCIACIÓN
B14 FAQ
B05 CTA PRINCIPAL
B06 FOOTER

La selección definitiva dependerá de los datos reales disponibles.

---

39. REGLA CONTRA LA PUBLICACIÓN MASIVA

El sistema nunca debe funcionar como:

KEYWORD
↓
PLANTILLA
↓
CAMBIO DE LOCALIDAD
↓
IA
↓
PUBLICACIÓN MASIVA

El flujo correcto es:

EVIDENCIA
↓
OPORTUNIDAD
↓
MOTOR
↓
CREAR
↓
ARQUITECTURA
↓
DATOS
↓
BLOQUES
↓
IA
↓
VALIDACIÓN
↓
PUBLICACIÓN

---

40. RELACIÓN CON OTROS DOCUMENTOS

Este documento define la arquitectura funcional de la landing.

No define:

- el estado general del proyecto;
- el roadmap;
- el modelo de datos completo;
- la implementación técnica de WordPress;
- la implementación técnica de N8N;
- el contenido final de cada página.

Las referencias principales son:

"proyecto/roadmap-proyecto.md"

"proyecto/seo/esquema-datos.md"

"proyecto/seo/motor-decision.md"

"proyecto/seo/matriz-oportunidades.md"

"proyecto/seo/arquitectura-urls.md"

"proyecto/seo/sistema-bloques.md"

---

41. CONTROL DE VERSIONES

Versión: 2.1

Fecha: 2026-08-24

Cambios

- Consolidación con la matriz de oportunidades v2.0.
- Refuerzo de la condición "decision_seo = CREAR".
- Clarificación de la autoridad de la arquitectura.
- Integración explícita de "parent_url".
- Integración explícita de "bloques.seleccionados".
- Refuerzo de la trazabilidad entre oportunidad, evidencias y landing.
- Refuerzo de las reglas de no invención.
- Incorporación de control de duplicación antes de publicación.
- Clarificación de la relación entre IA, N8N y WordPress.
- Refuerzo de la regla de no publicación cuando existan datos insuficientes.
- Eliminación de posibles interpretaciones que permitan a la IA modificar la arquitectura.

---

42. REGLA FINAL

La arquitectura responde:

¿CÓMO DEBE ESTRUCTURARSE ESTA PÁGINA?

El motor responde:

¿DEBE EXISTIR ESTA PÁGINA?

La matriz responde:

¿QUÉ OPORTUNIDAD ESTAMOS EVALUANDO?

El registro responde:

¿QUÉ DECISIÓN SE TOMÓ Y POR QUÉ?

La IA responde:

¿CÓMO GENERAMOS EL CONTENIDO?

N8N responde:

¿CÓMO AUTOMATIZAMOS EL PROCESO?

WordPress responde:

¿DÓNDE SE CONSTRUYE Y PUBLICA?

Ninguna capa debe saltarse a las anteriores.

---

FIN
