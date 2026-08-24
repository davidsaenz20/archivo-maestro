ARQUITECTURA DE LANDING

Versión: 2.0
Estado: ACTIVO
Función: definir la arquitectura funcional de una landing SEO local antes de generar contenido.

---

1. FUNCIÓN

Define la estructura funcional de una landing SEO local generada a partir de una oportunidad validada.

La landing no se genera directamente desde keywords.

Flujo:

EVIDENCIAS
↓
OPORTUNIDAD
↓
DECISIÓN SEO
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

La arquitectura debe poder reutilizarse a escala sin producir páginas prácticamente idénticas.

La arquitectura se determina antes de generar contenido.

La IA no puede modificar unilateralmente la arquitectura.

---

3. CONDICIÓN DE ENTRADA

Solo se inicia la construcción cuando:

"decision_seo = CREAR"

La oportunidad debe utilizar el modelo definido en:

"proyecto/seo/esquema-datos.md"

Como mínimo debe existir:

- "opportunity_id"
- "identidad"
- "localizacion"
- "intencion"
- "investigacion"
- "decision_seo"
- "arquitectura"
- "datos disponibles"
- "restricciones"

Si falta información necesaria:

- utilizar "null" cuando el dato pueda permanecer ausente;
- utilizar "REVISAR" cuando la ausencia impida construir correctamente la página.

---

4. ARQUITECTURA

La arquitectura define como mínimo:

- "tipo_pagina"
- "url"
- "url_tipo"
- "canonical"
- "parent_url"
- "profundidad"

Estos elementos deben estar determinados antes de generar contenido.

La IA recibe estos elementos como contexto y no puede modificarlos.

---

5. TIPOS DE PÁGINA

Valores iniciales:

"servicio_localidad"

"servicio_subservicio_localidad"

Ejemplos:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

Los tipos adicionales deberán definirse documentalmente antes de utilizarse.

---

6. ESTRUCTURA GLOBAL

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
- arquitectura;
- utilidad real del bloque.

---

7. SISTEMA DE BLOQUES

La selección se realiza mediante:

"bloques.seleccionados"

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

La definición técnica está en:

"proyecto/seo/sistema-bloques.md"

No se deben crear identificadores paralelos.

---

8. BLOQUES OBLIGATORIOS

Los bloques obligatorios se determinan por la arquitectura y el tipo de página.

Como mínimo una landing funcional debe poder representar:

- identidad;
- intención;
- contenido principal;
- navegación;
- CTA;
- footer.

No se debe inventar contenido para completar un bloque.

---

9. BLOQUES CONDICIONALES

Se utilizan únicamente cuando existen datos suficientes y aportan valor real.

Ejemplos:

- B07 Subservicio
- B08 Problemas
- B09 Información local
- B10 Cobertura
- B11 Proceso
- B12 Confianza
- B13 Diferenciación
- B14 FAQ
- B15 Servicios relacionados
- B16 Localidades relacionadas
- B18 Testimonios
- B19 Casos
- B20 Galería
- B21 Precio
- B22 Horarios
- B23 Mapa

---

10. HERO

Debe identificar inmediatamente:

- servicio;
- localidad;
- intención;
- acción principal.

Puede contener:

- H1;
- subtítulo;
- CTA.

No puede incluir afirmaciones comerciales no verificadas.

---

11. H1

Cada landing indexable tendrá un único H1.

Debe corresponder con:

- servicio;
- subservicio cuando exista;
- localidad;
- intención.

Ejemplos:

"Fontanero en Marbella"

"Desatascos en Marbella"

---

12. CONTENIDO PRINCIPAL

Debe explicar la necesidad principal del usuario.

Puede incluir:

- servicio;
- alcance;
- problemas;
- situaciones habituales;
- información útil.

No debe utilizarse para rellenar longitud artificialmente.

---

13. INFORMACIÓN LOCAL

Solo se incorpora información local respaldada.

Puede incluir:

- zonas;
- barrios;
- urbanizaciones;
- características relevantes;
- tipos de vivienda;
- necesidades locales;
- cobertura.

El nombre del municipio por sí solo no constituye contenido local.

---

14. COBERTURA

Solo se incluyen zonas o localidades cuando la cobertura esté confirmada o exista una justificación documental válida.

No se crean listas masivas para aumentar relevancia SEO.

---

15. PROCESO

Puede explicar el proceso real del servicio.

No se inventan:

- procedimientos comerciales;
- tiempos;
- garantías;
- disponibilidad.

---

16. CONFIANZA

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

17. DIFERENCIACIÓN

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
- evidencias.

Cambiar únicamente la localidad no es diferenciación.

---

18. FAQ

Las preguntas deben proceder de:

- intención;
- investigación;
- conocimiento válido del servicio.

No deben generarse únicamente para introducir keywords.

Las respuestas deben ser verificables.

---

19. CTA

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
- tiempos de respuesta.

---

20. NAVEGACIÓN

Solo puede enlazar a URLs autorizadas por la arquitectura.

Puede incluir:

- servicios;
- localidades;
- páginas superiores;
- contacto.

No se debe enlazar indiscriminadamente a miles de páginas.

---

21. ENLAZADO INTERNO

Los enlaces deben proceder de la arquitectura existente.

No se crean enlaces hacia:

- URLs inexistentes;
- páginas no autorizadas;
- páginas generadas únicamente para crear enlaces.

---

22. SEO ON-PAGE

La landing debe poder generar:

- title;
- meta description;
- H1;
- headings;
- canonical;
- enlaces internos;
- datos estructurados cuando proceda;
- ALT de imágenes.

La IA trabaja dentro de la arquitectura recibida.

---

23. DATOS

La arquitectura utiliza como fuente:

"proyecto/seo/esquema-datos.md"

No se deben crear estructuras paralelas.

Los datos ausentes se representan mediante:

"null"

o provocan:

"REVISAR"

cuando sean necesarios para completar correctamente la página.

---

24. NO INVENCIÓN

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
- URLs.

---

25. RELACIÓN CON IA

La IA recibe:

- identidad;
- intención;
- URL;
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
- bloques no autorizados.

---

26. RELACIÓN CON N8N

Flujo:

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

---

27. VALIDACIÓN

Antes de publicar:

- identidad correcta;
- servicio correcto;
- subservicio correcto;
- localidad correcta;
- URL correcta;
- canonical correcto;
- intención correcta;
- contenido específico;
- datos respaldados;
- bloques correctos;
- ausencia de invenciones;
- ausencia de duplicación evidente;
- enlaces válidos.

---

28. ESCALABILIDAD

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
- diferenciación.

---

29. EJEMPLO

Oportunidad:

"fontanero + Marbella"

URL:

"/fontanero/marbella/"

Estructura posible:

B01 HEADER
B02 NAVEGACIÓN
B03 HERO
B04 CONTENIDO PRINCIPAL
B08 PROBLEMAS
B09 INFORMACIÓN LOCAL
B11 PROCESO
B13 DIFERENCIACIÓN
B14 FAQ
B05 CTA
B06 FOOTER

Los bloques B08, B09, B11, B13 y B14 solo se utilizan si los datos y la intención los justifican.

---

30. REGLA FINAL

La arquitectura debe conseguir:

INTENCIÓN CORRECTA
↓
ESTRUCTURA CORRECTA
↓
DATOS REALES
↓
BLOQUES JUSTIFICADOS
↓
CONTENIDO ÚTIL
↓
VALIDACIÓN
↓
PUBLICACIÓN

Nunca:

KEYWORD
↓
PLANTILLA
↓
CAMBIO DE LOCALIDAD
↓
PUBLICACIÓN MASIVA

---

31. RELACIÓN CON OTROS DOCUMENTOS

Este documento define la arquitectura funcional de la landing.

No define:

- el estado actual del proyecto;
- el roadmap de ejecución;
- el modelo de datos completo;
- la implementación técnica de los bloques;
- el flujo técnico completo de N8N.

Para ello se utilizan respectivamente:

"proyecto/roadmap-proyecto.md"

"proyecto/seo/esquema-datos.md"

"proyecto/seo/sistema-bloques.md"

y la documentación técnica de automatización.

No deben crearse fuentes paralelas para estas funciones.

---

32. CONTROL DE VERSIONES

Versión: 2.0

Fecha: 2026-08-24

Motivo:

Alineación posterior a la auditoría y consolidación documental.

Cambios principales:

- separación clara entre arquitectura y estado del proyecto;
- alineación con el modelo de datos canónico;
- alineación con el sistema oficial B01-B23;
- refuerzo de la autoridad de la arquitectura;
- separación entre arquitectura, datos, contenido e implementación;
- eliminación de referencias obsoletas;
- refuerzo de las reglas de no invención;
- preparación para IA → N8N → WordPress;
- eliminación de estructuras documentales paralelas.

---

FIN DE ARQUITECTURA DE LANDING
