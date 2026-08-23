METODOLOGÍA DEL PROYECTO

1. OBJETIVO

Definir un sistema reproducible para investigar, diseñar, validar y automatizar una plataforma de páginas SEO locales para servicios profesionales.

El sistema debe poder aplicarse inicialmente a fontanería y posteriormente a otros sectores como:

- Abogados.
- Electricistas.
- Reformas.
- Carpinteros.
- Pintores.
- Jardineros.
- Cerrajeros.
- Climatización.
- Otros servicios profesionales.

La metodología debe permitir pasar desde la investigación inicial hasta la generación y publicación automatizada de páginas mediante IA + N8N + WordPress u otra infraestructura compatible.

---

2. PRINCIPIO FUNDAMENTAL

El proyecto no consiste simplemente en generar miles de páginas.

El objetivo es construir un sistema capaz de:

1. Investigar un mercado.
2. Identificar servicios.
3. Identificar localidades.
4. Analizar demanda e intención.
5. Analizar competencia.
6. Detectar oportunidades.
7. Decidir qué páginas tienen sentido.
8. Definir qué información debe contener cada página.
9. Generar contenido útil y diferenciado.
10. Automatizar la producción.
11. Publicar.
12. Medir resultados.
13. Aprender de los resultados.
14. Mejorar las reglas.

La automatización debe ejecutar decisiones previamente justificadas.

---

3. JERARQUÍA DE DOCUMENTOS

El proyecto utiliza diferentes niveles documentales.

NIVEL 1 — MAESTRO

"maestro.md"

Es el documento de control general del proyecto.

Contiene:

- Estado general.
- Principios.
- Arquitectura documental.
- Reglas de prioridad.
- Actualizaciones importantes.
- Situación actual.
- Próximos pasos.

---

NIVEL 2 — METODOLOGÍA

"proyecto/metodologia.md"

Define:

- Cómo trabajamos.
- En qué orden trabajamos.
- Qué documentos debemos crear.
- Qué debe comprobarse antes de avanzar.
- Cómo se investiga un nuevo servicio.
- Cómo se pasa de investigación a automatización.

---

NIVEL 3 — DOCUMENTOS ESTRUCTURALES

Incluyen documentos como:

- Arquitectura SEO.
- Motor de decisión.
- Arquitectura de landing.
- Sistema de bloques.
- Sistema de contenido.
- Datos de entrada.
- Automatización.

Definen cómo funciona el sistema.

---

NIVEL 4 — DOCUMENTACIÓN SECTORIAL

Ejemplos:

- Investigación de fontanería.
- Matriz de servicios de fontanería.
- Matriz de localidades.
- Investigación de abogados.
- Matriz de servicios jurídicos.

Contienen información específica de cada mercado.

---

4. REGLA DE PRIORIDAD

Cuando dos documentos entren en contradicción:

1. Primero se comprueba la fecha.
2. Se comprueba si existe una actualización posterior.
3. Se analiza la evidencia que originó cada decisión.
4. Se aplica la información más reciente y mejor fundamentada.
5. Se actualizan los documentos afectados.
6. Se registra el cambio.

No debe darse prioridad automática al documento maestro si existe información posterior y válida en documentos especializados.

El maestro actúa como índice y documento de control, no como una fuente eterna que pueda invalidar trabajo posterior.

---

5. SISTEMA DE ACTUALIZACIONES

Las decisiones importantes deben poder actualizarse sin borrar necesariamente el historial.

Los documentos que evolucionen deben registrar:

- Fecha.
- Cambio.
- Motivo.
- Evidencia.
- Consecuencia.

Cuando una actualización contradiga información anterior, debe indicarse expresamente.

La información posterior y suficientemente fundamentada puede sustituir a una decisión anterior.

---

6. FASES DEL PROYECTO

FASE 1 — INVESTIGACIÓN

Objetivo:

Comprender el mercado antes de diseñar la estructura definitiva.

Se investiga:

- Servicios.
- Intenciones.
- Localidades.
- Competencia.
- SERP.
- Directorios.
- Empresas.
- Demanda.
- Potencial comercial.
- Diferenciación.
- Características territoriales.

Resultado

Documentación sectorial y territorial.

---

7. FASE 2 — MATRICES

Se estructuran los datos obtenidos.

Principales matrices:

- Servicios.
- Localidades.
- Competencia.
- Oportunidades.

La combinación principal es:

SERVICIO × LOCALIDAD

Resultado

Universo de combinaciones posibles para analizar.

---

8. FASE 3 — MOTOR DE DECISIÓN

El motor analiza cada combinación.

Variables principales:

- Demanda.
- Intención.
- Potencial comercial.
- Relevancia territorial.
- Competencia.
- Diferenciación.
- Información disponible.
- Riesgo de duplicación.

Resultados posibles

- CREAR.
- AGRUPAR.
- INVESTIGAR.
- NO CREAR.

El motor está actualmente:

DEFINIDO — PENDIENTE DE VALIDACIÓN REAL

Los pesos y umbrales actuales son experimentales.

---

9. FASE 4 — ARQUITECTURA DE LANDING

Esta fase es obligatoria antes de automatizar la generación de páginas.

Su objetivo es definir:

- Estructura de la landing.
- Bloques.
- Orden.
- Función de cada bloque.
- Información necesaria.
- Elementos variables.
- Elementos fijos.
- Elementos opcionales.
- Reglas de combinación.
- Reglas de exclusión.

No se debe pasar directamente del motor a N8N.

Primero debe existir una estructura de landing suficientemente definida.

Resultado

Una plantilla lógica de landing reutilizable.

---

10. FASE 5 — SISTEMA DE BLOQUES

Cada landing estará formada por bloques independientes.

Ejemplos potenciales:

- Hero.
- Propuesta de valor.
- Servicios.
- Problemas.
- Cobertura.
- Información local.
- Proceso.
- Urgencias.
- FAQ.
- CTA.
- Elementos de confianza.
- SEO.
- Datos estructurados.

La lista definitiva debe determinarse mediante investigación y pruebas.

Cada bloque deberá definir:

- Objetivo.
- Datos de entrada.
- Reglas.
- Contenido que puede generar la IA.
- Contenido que no debe inventar.
- Condiciones de aparición.
- Variables.
- Salida esperada.

---

11. FASE 6 — SISTEMA DE CONTENIDO

Una vez definidos los bloques se determinará cómo se genera el contenido.

La IA no recibirá simplemente:

«"Escribe una landing de fontanero en Marbella."»

Recibirá información estructurada.

Ejemplo:

servicio
localidad
intención
tipo_de_cliente
zonas
servicios_relacionados
datos_locales
información_comercial
urgencia
faq
diferenciadores
restricciones

La IA deberá generar únicamente contenido compatible con los datos disponibles.

No debe inventar:

- empresas;
- precios;
- direcciones;
- teléfonos;
- disponibilidad;
- certificaciones;
- testimonios;
- cobertura;
- datos locales no verificados.

---

12. FASE 7 — DATOS DE ENTRADA

Debe definirse un modelo estructurado para cada oportunidad.

Ejemplo conceptual:

ID
SERVICIO
LOCALIDAD
PROVINCIA
INTENCIÓN
DEMANDA
COMPETENCIA
POTENCIAL_COMERCIAL
DIFERENCIACIÓN
INFORMACIÓN_DISPONIBLE
COBERTURA
URGENCIA
TIPO_CLIENTE
SERVICIOS_RELACIONADOS
BLOQUES_ACTIVOS
DECISIÓN

Este modelo será utilizado posteriormente por N8N.

---

13. FASE 8 — GENERACIÓN CON IA

La IA recibirá:

1. Datos estructurados.
2. Arquitectura de landing.
3. Bloques seleccionados.
4. Reglas de contenido.
5. Información verificable.
6. Restricciones.

La IA producirá:

- Contenido.
- Metadatos.
- Elementos SEO.
- FAQ cuando corresponda.
- Datos estructurados cuando corresponda.

La generación debe ser controlada.

---

14. FASE 9 — AUTOMATIZACIÓN N8N

N8N será la capa de orquestación.

Flujo conceptual:

DATOS

↓

MOTOR

↓

DECISIÓN

↓

SELECCIÓN DE BLOQUES

↓

RECOPILACIÓN DE INFORMACIÓN

↓

IA

↓

VALIDACIÓN

↓

WORDPRESS

↓

PUBLICACIÓN

↓

MEDICIÓN

N8N no debe tomar decisiones estratégicas que correspondan al motor.

---

15. FASE 10 — PUBLICACIÓN

Antes de publicar una página debe comprobarse:

- Contenido completo.
- Información coherente.
- Variables correctas.
- Localidad correcta.
- Servicio correcto.
- Ausencia de información inventada.
- Diferenciación suficiente.
- SEO técnico.
- Enlaces.
- CTA.
- Datos estructurados cuando proceda.

---

16. FASE 11 — MEDICIÓN

Una vez publicadas las páginas se medirán:

- Impresiones.
- Clics.
- Posiciones.
- CTR.
- Conversiones.
- Contactos.
- Llamadas.
- Formularios.
- Rendimiento por servicio.
- Rendimiento por localidad.

---

17. FASE 12 — APRENDIZAJE

Los resultados reales pueden utilizarse para modificar:

- Pesos.
- Umbrales.
- Bloques.
- Contenido.
- Reglas.
- Priorización.
- Arquitectura.

Una decisión no debe modificarse únicamente por un resultado aislado.

Debe existir suficiente evidencia.

---

18. INVESTIGACIÓN DE UN NUEVO SERVICIO

Cuando se incorpore un nuevo sector:

Paso 1

Crear carpeta/documentación específica.

Paso 2

Investigar el mercado.

Paso 3

Identificar servicios.

Paso 4

Identificar intenciones.

Paso 5

Investigar competencia.

Paso 6

Investigar localidades relevantes.

Paso 7

Crear matrices.

Paso 8

Adaptar variables sectoriales del motor.

Paso 9

Validar oportunidades.

Paso 10

Adaptar arquitectura de landing si el sector lo requiere.

Paso 11

Definir bloques específicos.

Paso 12

Definir datos de entrada.

Paso 13

Integrar con el sistema general.

Paso 14

Automatizar.

---

19. REGLA DE REUTILIZACIÓN

El sistema debe separar:

COMPONENTES GENERALES

Reutilizables:

- Metodología.
- Arquitectura general.
- Motor.
- Modelo de datos.
- Sistema de bloques.
- Automatización.
- Validación.
- Medición.

COMPONENTES SECTORIALES

Específicos:

- Servicios.
- Intenciones.
- Variables.
- Reglas.
- Excepciones.
- Contenido.
- Bloques específicos.
- Datos territoriales.

Nunca se debe copiar automáticamente una conclusión sectorial a otro servicio.

---

20. REGLA DE NO AUTOMATIZAR DEMASIADO PRONTO

No se debe comenzar la automatización completa mientras no estén suficientemente definidos:

1. Motor.
2. Arquitectura de landing.
3. Sistema de bloques.
4. Modelo de datos.
5. Reglas de contenido.
6. Validaciones.

Esto evita construir una automatización sobre una arquitectura todavía cambiante.

---

21. ORDEN ACTUAL DEL TRABAJO

Estado actual:

COMPLETADO

- Maestro.
- Metodología base.
- Investigación inicial de fontanería.
- Matriz de servicios.
- Matriz territorial.
- Arquitectura SEO.
- Motor de decisión.

EN CURSO

Diseño de la arquitectura de landing y sistema de bloques.

DESPUÉS

1. Arquitectura de landing.
2. Sistema de bloques.
3. Modelo de datos de cada landing.
4. Sistema de prompts/contenido.
5. Sistema de validación.
6. Diseño del flujo N8N.
7. Integración con WordPress.
8. Primera prueba controlada.
9. Medición.
10. Optimización.

---

22. CONTROL DE COHERENCIA

Antes de pasar de una fase a otra se debe comprobar:

- Que los documentos no se contradigan.
- Que las reglas estén actualizadas.
- Que el maestro refleje el estado real.
- Que las decisiones nuevas estén registradas.
- Que no se haya perdido información de investigación.
- Que el siguiente paso esté claramente definido.

Si existe una contradicción, se detiene el avance y se corrigen primero los documentos.

---

23. REGLA PARA EL TRABAJO CON IA

La IA debe interpretar siempre:

1. Maestro.
2. Metodología.
3. Documentos estructurales relevantes.
4. Documentación sectorial relevante.
5. Actualizaciones posteriores.

No debe asumir que un documento antiguo tiene prioridad simplemente por ser más general.

Cuando exista contradicción, debe analizar:

- fecha;
- evidencia;
- contexto;
- actualización;
- dependencia entre documentos.

---

24. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se actualiza la metodología para reflejar correctamente el estado actual del proyecto.

El motor de decisión queda definido, aunque todavía pendiente de validación real.

Se incorpora explícitamente una nueva fase entre el motor y la automatización:

ARQUITECTURA DE LANDING → SISTEMA DE BLOQUES → SISTEMA DE CONTENIDO → DATOS DE ENTRADA → IA → N8N

Se establece que N8N no debe diseñar la arquitectura ni tomar decisiones estratégicas.

También se define que la plataforma debe separar componentes generales reutilizables de componentes específicos de cada sector.

El siguiente trabajo prioritario es diseñar la arquitectura de landing y los bloques que permitirán posteriormente generar páginas mediante IA de forma controlada y reutilizable.
