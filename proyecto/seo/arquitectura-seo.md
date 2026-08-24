ARQUITECTURA SEO DEL PROYECTO

Versión: 2.0
Estado: ACTIVO
Función: definir las reglas generales de arquitectura SEO del sistema de generación de páginas.

---

1. OBJETIVO

Crear una plataforma capaz de generar páginas específicas combinando de forma controlada:

- servicio;
- especialidad;
- localidad;
- intención de búsqueda;
- tipo de cliente;
- cobertura territorial;
- información local.

El objetivo no es generar miles de páginas idénticas.

El objetivo es construir páginas:

- útiles;
- diferenciadas;
- justificadas;
- trazables;
- verificables;
- escalables.

---

2. PRINCIPIO FUNDAMENTAL

La arquitectura SEO no parte directamente de una keyword.

Parte de:

EVIDENCIA
↓
OPORTUNIDAD
↓
DECISIÓN SEO
↓
ARQUITECTURA
↓
DATOS
↓
CONTENIDO
↓
VALIDACIÓN
↓
PUBLICACIÓN

La existencia de una combinación "SERVICIO × LOCALIDAD" no implica automáticamente que deba existir una página.

---

3. UNIDAD DE ANÁLISIS

La unidad principal es:

"SERVICIO × LOCALIDAD"

Puede ampliarse mediante:

- especialidad;
- problema;
- urgencia;
- tipo de cliente;
- intención;
- cobertura;
- contexto local.

Ejemplos:

- Fontanero Marbella.
- Desatascos Marbella.
- Reparación de fugas Marbella.
- Fontanero urgente Marbella.

Cada combinación debe evaluarse individualmente.

---

4. CRITERIOS DE DECISIÓN

El sistema debe valorar como mínimo:

- existencia real del servicio;
- intención;
- demanda;
- relevancia territorial;
- especialización;
- tipo de cliente;
- competencia;
- potencial comercial;
- diferenciación;
- información local disponible;
- riesgo de duplicación;
- utilidad para el usuario;
- disponibilidad de evidencias.

Si la combinación no tiene suficiente justificación, no se genera como página independiente.

---

5. DECISIONES SEO

Las decisiones oficiales son:

CREAR

Crear una página independiente.

AGRUPAR

Integrar la intención dentro de otra página.

INVESTIGAR

Existe una oportunidad potencial, pero falta información crítica.

NO_CREAR

No existe suficiente justificación para una página independiente.

Estas decisiones deben quedar registradas en el modelo de datos y no deben ser decididas por la IA durante la generación.

---

6. ESTRUCTURA TERRITORIAL

El sistema puede trabajar con:

- país;
- comunidad autónoma;
- provincia;
- ciudad;
- municipio;
- localidad;
- zona;
- barrio;
- urbanización.

La profundidad territorial depende de:

- demanda;
- relevancia;
- competencia;
- potencial comercial;
- información disponible;
- posibilidad de diferenciación.

No se deben crear niveles territoriales artificiales.

---

7. TIPOS DE PÁGINA

Tipos iniciales:

SERVICIO_GENERAL

Ejemplo:

"Fontanería"

SERVICIO_LOCALIDAD

Ejemplo:

"Fontanero Marbella"

ESPECIALIDAD_LOCALIDAD

Ejemplo:

"Desatascos Marbella"

URGENCIA_LOCALIDAD

Ejemplo:

"Fontanero urgente Marbella"

SERVICIO_ESPECIALIZADO_LOCALIDAD

Ejemplo:

"Reparación de termos Marbella"

Los tipos adicionales deben definirse documentalmente antes de utilizarse.

---

8. DIFERENCIACIÓN LOCAL

Una página local debe incorporar información específica cuando exista.

Puede incluir:

- zonas atendidas;
- barrios;
- urbanizaciones;
- características del municipio;
- tipos de vivienda;
- problemas habituales;
- necesidades específicas;
- contexto turístico;
- segundas residencias;
- perfil de cliente;
- horarios;
- urgencias;
- información comercial;
- preguntas frecuentes específicas.

No es suficiente cambiar el nombre de una localidad dentro de una plantilla.

---

9. DIFERENCIACIÓN REAL

No constituye diferenciación:

- cambiar únicamente una ciudad;
- cambiar algunas palabras;
- duplicar una plantilla;
- añadir texto artificial;
- introducir keywords repetidas.

Una página debe tener una función clara y aportar información útil.

Debe poder responder:

- qué intención satisface;
- qué valor aporta;
- por qué merece existir;
- qué información específica puede contener;
- cómo se diferencia de otras páginas.

---

10. FONTANERÍA

Fontanería es el primer sector utilizado para investigar y validar el sistema.

La clasificación sectorial puede incluir:

- fontanería general;
- reparación de fugas;
- detección de fugas;
- desatascos;
- tuberías;
- agua caliente;
- termos;
- calentadores;
- urgencias;
- instalaciones;
- mantenimiento;
- otros servicios identificados mediante investigación.

Esta clasificación es específica del sector.

No debe copiarse automáticamente a otros sectores.

---

11. CAPA GENERAL Y CAPA SECTORIAL

El sistema debe separar:

CAPA GENERAL

Reglas comunes de:

- investigación;
- clasificación;
- evaluación;
- decisión;
- arquitectura;
- validación;
- medición;
- escalado.

CAPA SECTORIAL

Características específicas de cada servicio:

- servicios;
- especialidades;
- intenciones;
- clientes;
- particularidades territoriales;
- potencial comercial;
- excepciones;
- parámetros;
- reglas específicas.

La arquitectura general se reutiliza.

Las reglas sectoriales deben investigarse independientemente.

---

12. MOTOR DE DECISIÓN

El motor de decisión está definido en:

"proyecto/seo/motor-decision.md"

Debe determinar, como mínimo:

- existencia de oportunidad;
- necesidad de página independiente;
- tipo de página;
- profundidad territorial;
- información local necesaria;
- contenidos que deben evitarse;
- decisión final.

La arquitectura no sustituye al motor de decisión.

---

13. RELACIÓN CON LA ARQUITECTURA DE LANDING

Una vez tomada la decisión "CREAR", la oportunidad pasa a:

"proyecto/seo/arquitectura-landing.md"

La arquitectura SEO determina qué página debe existir.

La arquitectura de landing determina cómo se estructura esa página.

Por tanto:

ARQUITECTURA SEO
→ decide la estructura y existencia de páginas.

ARQUITECTURA LANDING
→ define los bloques funcionales de una página concreta.

No deben duplicarse estas funciones.

---

14. RELACIÓN CON URLS

La arquitectura SEO define la lógica de tipos de página.

La estructura concreta de URLs se documenta en:

"proyecto/seo/arquitectura-urls.md"

No se deben crear estructuras paralelas.

---

15. RELACIÓN CON DATOS

La arquitectura utiliza el modelo definido en:

"proyecto/seo/esquema-datos.md"

Los datos deben ser:

- estructurados;
- trazables;
- verificables;
- reutilizables.

La arquitectura no crea una segunda representación de los mismos datos.

---

16. RELACIÓN CON IA

La IA recibe como contexto:

- oportunidad;
- decisión;
- servicio;
- localidad;
- intención;
- arquitectura;
- evidencias;
- datos;
- bloques;
- restricciones.

La IA genera contenido dentro de esos límites.

La IA no puede decidir unilateralmente:

- si una página debe existir;
- URL;
- canonical;
- servicio;
- localidad;
- arquitectura;
- decisión SEO;
- bloques no autorizados.

---

17. AUTOMATIZACIÓN

Herramientas como N8N pueden automatizar el flujo:

DATOS
↓
OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
↓
CONTEXTO
↓
IA
↓
VALIDACIÓN
↓
WORDPRESS
↓
PUBLICACIÓN

La automatización debe ejecutar reglas previamente definidas.

La tecnología no debe utilizarse para automatizar una lógica todavía no validada.

---

18. VALIDACIÓN

Antes de publicar una página debe comprobarse:

- identidad;
- servicio;
- especialidad;
- localidad;
- intención;
- decisión;
- arquitectura;
- URL;
- canonical;
- contenido;
- datos;
- evidencias;
- bloques;
- enlaces;
- diferenciación;
- ausencia de invenciones;
- ausencia de duplicación problemática.

Una página que no supera la validación no debe publicarse automáticamente.

---

19. NO INVENCIÓN

El sistema no puede inventar:

- servicios;
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
- certificaciones;
- garantías;
- experiencia;
- reseñas;
- testimonios;
- casos;
- datos locales;
- imágenes;
- URLs.

Los datos desconocidos deben representarse mediante "null" o provocar "REVISAR" cuando sean necesarios.

---

20. RIESGO PROGRAMÁTICO

La generación masiva puede producir:

- contenido repetitivo;
- páginas de poco valor;
- canibalización;
- problemas de indexación;
- costes innecesarios;
- mala experiencia;
- errores a escala.

Por ello:

AUTOMATIZACIÓN ≠ GENERACIÓN INDISCRIMINADA

La automatización debe estar subordinada a:

DECISIÓN + ARQUITECTURA + DATOS + VALIDACIÓN

---

21. ESCALABILIDAD

La arquitectura debe permitir aumentar:

- servicios;
- localidades;
- especialidades;
- páginas.

Sin perder:

- utilidad;
- diferenciación;
- calidad;
- trazabilidad;
- control;
- validación.

El crecimiento debe producirse mediante reglas y datos, no mediante duplicación indiscriminada.

---

22. INDEPENDENCIA SECTORIAL

Cada nuevo sector debe investigarse de forma independiente.

No deben heredarse automáticamente de otro sector:

- servicios;
- pesos;
- umbrales;
- intenciones;
- niveles territoriales;
- excepciones;
- decisiones;
- reglas comerciales.

La reutilización debe producirse en la metodología y arquitectura general, no en datos sectoriales no validados.

---

23. REGLA DE CALIDAD

Antes de crear una nueva combinación:

"SERVICIO × LOCALIDAD"

debe poder explicarse:

1. Qué intención satisface.
2. Qué valor aporta.
3. Por qué merece existir.
4. Qué información específica puede contener.
5. Cómo se diferencia.

Si no puede justificarse:

"INVESTIGAR"

o

"NO_CREAR"

según corresponda.

---

24. REGLA DE CONTROL

La arquitectura debe ser definida antes de generar contenido.

El orden correcto es:

OPORTUNIDAD
↓
DECISIÓN
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

Nunca:

KEYWORD
↓
PLANTILLA
↓
CAMBIO DE LOCALIDAD
↓
PUBLICACIÓN MASIVA

---

25. RELACIÓN CON LA METODOLOGÍA UNIVERSAL

Esta arquitectura forma parte del proceso general:

INVESTIGAR
↓
ESTRUCTURAR
↓
DECIDIR
↓
ARQUITECTAR
↓
GENERAR
↓
VALIDAR
↓
PROBAR
↓
MEDIR
↓
MEJORAR
↓
AUTOMATIZAR
↓
ESCALAR

La arquitectura no debe adelantarse a una fase que todavía no haya sido validada.

---

26. FUENTES DE AUTORIDAD

Este documento define la arquitectura SEO general.

No define:

- estado del proyecto;
- roadmap de ejecución;
- modelo de datos completo;
- bloques funcionales;
- estructura concreta de URLs;
- implementación WordPress;
- implementación N8N.

Para ello se utilizan respectivamente los documentos especializados correspondientes.

No deben existir fuentes paralelas de autoridad.

---

27. REGLA FINAL

Una página solo debe existir cuando exista una relación justificable entre:

INTENCIÓN
+
OPORTUNIDAD
+
DATOS
+
ARQUITECTURA
+
UTILIDAD
+
DIFERENCIACIÓN

La escala nunca debe convertirse en un objetivo superior a la calidad.

---

28. CONTROL DE VERSIONES

Versión: 2.0

Fecha: 2026-08-24

Motivo: consolidación posterior a la auditoría documental.

Cambios principales:

- separación entre arquitectura SEO y arquitectura de landing;
- alineación con el modelo de decisión;
- alineación con el modelo de datos;
- separación entre capa general y sectorial;
- refuerzo de trazabilidad;
- refuerzo de no invención;
- eliminación de funciones duplicadas;
- preparación para IA → N8N → WordPress;
- definición clara de fuentes de autoridad.

---

FIN DE ARQUITECTURA SEO DEL PROYECTO
