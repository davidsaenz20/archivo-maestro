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
3. Identificar subservicios y especialidades.
4. Identificar localidades.
5. Analizar demanda e intención.
6. Analizar competencia.
7. Detectar oportunidades.
8. Decidir qué combinaciones merecen una página.
9. Determinar la estructura URL correspondiente.
10. Definir qué información debe contener cada página.
11. Generar contenido útil y diferenciado.
12. Validar el contenido.
13. Automatizar la producción.
14. Publicar.
15. Medir resultados.
16. Aprender de los resultados.
17. Mejorar las reglas.

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
- Qué responsabilidades tiene cada capa del sistema.

---

NIVEL 3 — DOCUMENTOS ESTRUCTURALES

Incluyen documentos como:

- Arquitectura SEO.
- Motor de decisión.
- Arquitectura de URLs.
- Arquitectura de landing.
- Sistema de bloques.
- Modelo de datos.
- Sistema de contenido.
- Validación.
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

NIVEL 5 — EVIDENCIAS Y DECISIONES

Debe conservarse la información necesaria para poder reconstruir por qué se tomó una decisión.

Puede incluir:

- Fuentes consultadas.
- URLs analizadas.
- SERP observadas.
- Competidores.
- Observaciones.
- Datos relevantes.
- Fecha de investigación.
- Decisiones derivadas.
- Versiones del motor utilizadas.
- Resultados de validaciones.

La memoria de la conversación no sustituye esta documentación.

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

El maestro actúa como documento de control y referencia general, no como una fuente inmutable que pueda invalidar trabajo posterior.

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

El proyecto seguirá las siguientes fases.

FASE 1 — INVESTIGACIÓN

Objetivo:

Comprender el mercado antes de diseñar la estructura definitiva.

Se investiga:

- Servicios.
- Subservicios.
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
- Información local.

Resultado

Documentación sectorial, territorial y evidencias.

---

7. FASE 2 — MATRICES

Se estructuran los datos obtenidos.

Principales matrices:

- Servicios.
- Subservicios.
- Localidades.
- Competencia.
- Oportunidades.

La combinación principal es:

SERVICIO × LOCALIDAD

También pueden existir:

SERVICIO × SUBSERVICIO × LOCALIDAD

Resultado

Universo de combinaciones posibles para analizar.

Las matrices deben conservar suficiente información para saber de dónde procede cada conclusión importante.

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
- Utilidad potencial.

Resultados posibles

- CREAR.
- AGRUPAR.
- INVESTIGAR.
- NO CREAR.

El motor está actualmente:

DEFINIDO — PENDIENTE DE VALIDACIÓN REAL

Los pesos y umbrales actuales son experimentales hasta completar las pruebas.

---

9. FASE 4 — ARQUITECTURA DE URLs

Esta fase transforma una oportunidad aprobada por el motor en una URL concreta.

La estructura base es:

"/{servicio}/{localidad}/"

o:

"/{servicio}/{subservicio}/{localidad}/"

Ejemplos:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

La existencia de un servicio, subservicio y localidad no genera automáticamente una URL.

Primero debe existir una decisión válida del motor.

Responsabilidades

El motor decide:

- Si existe oportunidad.
- Si merece una página.
- Si debe agruparse.
- Si necesita investigación.
- Si debe descartarse.

La arquitectura de URLs determina:

- Estructura.
- Jerarquía.
- Slugs.
- Profundidad.
- Relación entre servicio, subservicio y localidad.

La IA no decide libremente la URL.

Resultado

Una URL estructurada y asociada a una oportunidad concreta.

---

10. FASE 5 — ARQUITECTURA DE LANDING

Esta fase define la estructura de la página correspondiente a una URL validada.

Debe determinar:

- Estructura.
- Orden de bloques.
- Función de cada bloque.
- Información necesaria.
- Elementos variables.
- Elementos fijos.
- Elementos opcionales.
- Reglas de combinación.
- Reglas de exclusión.

Resultado

Una plantilla lógica de landing reutilizable.

---

11. FASE 6 — SISTEMA DE BLOQUES

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

Resultado

Un sistema modular de bloques reutilizable.

---

12. FASE 7 — MODELO DE DATOS

Debe definirse un modelo estructurado para cada oportunidad y cada landing.

Ejemplo conceptual:

ID
SERVICIO
SUBSERVICIO
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
URL

El modelo podrá ampliarse cuando las pruebas lo requieran.

Resultado

Una estructura de datos que pueda ser utilizada posteriormente por IA, N8N y WordPress.

---

13. FASE 8 — SISTEMA DE CONTENIDO E IA

La IA no recibirá simplemente:

«"Escribe una landing de fontanero en Marbella."»

Recibirá información estructurada.

Ejemplo:

servicio
subservicio
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
url
bloques_activos

La IA deberá generar únicamente contenido compatible con los datos disponibles.

No debe inventar:

- Empresas.
- Precios.
- Direcciones.
- Teléfonos.
- Disponibilidad.
- Certificaciones.
- Testimonios.
- Cobertura.
- Datos locales no verificados.

Resultado

Contenido estructurado y controlado para cada landing.

---

14. FASE 9 — VALIDACIÓN

Antes de publicar una página debe comprobarse:

- URL correcta.
- Servicio correcto.
- Subservicio correcto.
- Localidad correcta.
- Intención correcta.
- Contenido completo.
- Información coherente.
- Variables correctas.
- Ausencia de información inventada.
- Diferenciación suficiente.
- SEO técnico.
- Enlaces.
- CTA.
- Datos estructurados cuando proceda.

Si una página no supera la validación:

NO SE PUBLICA.

Resultado

Página preparada para publicación.

---

15. FASE 10 — AUTOMATIZACIÓN N8N

N8N será la capa de orquestación.

Flujo conceptual:

DATOS

↓

MOTOR

↓

DECISIÓN

↓

URL

↓

SELECCIÓN DE LANDING

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

16. FASE 11 — PUBLICACIÓN

La publicación debe realizarse únicamente después de superar la validación.

La infraestructura podrá ser:

- WordPress.
- Otra plataforma compatible.
- Sistema propio si posteriormente se considera conveniente.

La tecnología concreta no debe determinar la arquitectura estratégica.

---

17. FASE 12 — MEDICIÓN

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
- Rendimiento por tipo de página.

---

18. FASE 13 — APRENDIZAJE

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

19. RELACIÓN ENTRE LAS CAPAS

La relación oficial del sistema es:

INVESTIGACIÓN

↓

MATRICES

↓

MOTOR DE DECISIÓN

↓

ARQUITECTURA DE URL

↓

ARQUITECTURA DE LANDING

↓

BLOQUES

↓

MODELO DE DATOS

↓

IA / CONTENIDO

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS

↓

MEDICIÓN

↓

APRENDIZAJE

Ninguna capa debe saltarse sin justificación.

---

20. RESPONSABILIDAD DE CADA CAPA

Investigación

Descubre y conserva información.

Matrices

Estructuran la información.

Motor

Toma decisiones.

Arquitectura URL

Convierte la decisión en una URL.

Arquitectura de landing

Define cómo será la página.

Bloques

Definen las piezas de la página.

Modelo de datos

Define qué información recibe el sistema.

IA

Genera contenido utilizando los datos y reglas proporcionados.

Validación

Comprueba el resultado.

N8N

Orquesta el proceso.

WordPress

Publica.

Medición

Observa resultados.

Aprendizaje

Permite mejorar el sistema.

---

21. REGLA DE NO AUTOMATIZAR DEMASIADO PRONTO

No se debe comenzar la automatización completa mientras no estén suficientemente definidos:

1. Investigación.
2. Matrices.
3. Motor.
4. Arquitectura de URLs.
5. Arquitectura de landing.
6. Sistema de bloques.
7. Modelo de datos.
8. Reglas de contenido.
9. Validaciones.

Esto evita construir una automatización sobre una arquitectura todavía cambiante.

---

22. INVESTIGACIÓN DE UN NUEVO SERVICIO

Cuando se incorpore un nuevo sector:

Paso 1

Crear documentación específica del sector.

Paso 2

Investigar el mercado.

Paso 3

Identificar servicios.

Paso 4

Identificar subservicios.

Paso 5

Identificar intenciones.

Paso 6

Investigar competencia.

Paso 7

Investigar localidades relevantes.

Paso 8

Crear matrices.

Paso 9

Adaptar las variables sectoriales del motor.

Paso 10

Validar oportunidades.

Paso 11

Aplicar la arquitectura de URLs.

Paso 12

Adaptar la arquitectura de landing si el sector lo requiere.

Paso 13

Definir bloques específicos.

Paso 14

Definir datos de entrada.

Paso 15

Definir reglas de contenido.

Paso 16

Integrar con el sistema general.

Paso 17

Automatizar.

---

23. REGLA DE REUTILIZACIÓN

El sistema debe separar:

COMPONENTES GENERALES

Reutilizables:

- Metodología.
- Arquitectura general.
- Motor.
- Modelo de datos.
- Arquitectura URL.
- Sistema de bloques.
- Automatización.
- Validación.
- Medición.

COMPONENTES SECTORIALES

Específicos:

- Servicios.
- Subservicios.
- Intenciones.
- Variables.
- Reglas.
- Excepciones.
- Contenido.
- Bloques específicos.
- Datos territoriales.

Nunca se debe copiar automáticamente una conclusión sectorial a otro servicio.

---

24. REGISTRO DE DECISIONES

Las decisiones relevantes deben registrarse para mantener trazabilidad.

Una decisión podrá contener:

FECHA
SECTOR
SERVICIO
SUBSERVICIO
LOCALIDAD
DATOS_UTILIZADOS
PUNTUACIÓN
DECISIÓN
URL
MOTIVO
VERSIÓN_MOTOR
EVIDENCIA
CAMBIO_POSTERIOR

Esto permitirá conocer en el futuro por qué se creó, agrupó, investigó o descartó una combinación.

---

25. CONTROL DE COHERENCIA

Antes de pasar de una fase a otra se debe comprobar:

- Que los documentos no se contradigan.
- Que las reglas estén actualizadas.
- Que el maestro refleje el estado real.
- Que las decisiones nuevas estén registradas.
- Que no se haya perdido información de investigación.
- Que cada dato tenga un documento de destino.
- Que no existan duplicaciones documentales innecesarias.
- Que el siguiente paso esté claramente definido.

Si existe una contradicción, se detiene el avance y se corrigen primero los documentos.

---

26. REGLA DE CONSERVACIÓN DEL TRABAJO

Todo trabajo de investigación que produzca una conclusión, matriz, decisión, regla, URL, estructura o criterio debe quedar documentado en el repositorio antes de considerarse terminado.

La conversación puede servir para trabajar.

El repositorio debe servir para conservar.

La memoria de la IA no sustituye la documentación persistente.

---

27. REGLA DE AUDITORÍA

Cuando se termine una fase importante se realizará una auditoría documental.

La auditoría comprobará:

1. Qué se ha hecho.
2. Qué está documentado.
3. Qué evidencia existe.
4. Qué decisiones se han tomado.
5. Qué archivos dependen de esas decisiones.
6. Qué contradicciones existen.
7. Qué información falta.
8. Qué debe actualizarse.
9. Cuál es el siguiente paso.

No se avanzará a una nueva fase si existe una pérdida documental relevante.

---

28. ESTADO ACTUAL DEL PROYECTO

COMPLETADO

- Investigación inicial de fontanería.
- Matriz de servicios.
- Matriz de localidades.
- Arquitectura SEO.
- Motor de decisión definido.
- Arquitectura de URLs definida.

EN VALIDACIÓN

- Motor de decisión.
- Arquitectura de URLs.

PENDIENTE

- Arquitectura de landing.
- Sistema de bloques.
- Modelo de datos.
- Sistema de contenido/prompt.
- Validación automática.
- Automatización N8N.
- Integración WordPress.
- Primera publicación controlada.
- Medición.
- Optimización.

---

29. SIGUIENTE PASO OFICIAL

Antes de diseñar la arquitectura de landing se debe realizar una validación real del sistema:

MATRIZ

↓

MOTOR

↓

DECISIÓN

↓

URL

Se utilizarán combinaciones reales de fontanería.

Se comprobará:

- Si el motor puntúa correctamente.
- Si la decisión es razonable.
- Si la URL resultante es coherente.
- Si existe riesgo de duplicación.
- Si la combinación merece una landing independiente.

Los resultados se documentarán.

Una vez superada esta validación:

ARQUITECTURA DE LANDING será la siguiente fase.

---

30. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se actualiza la metodología para incorporar explícitamente la arquitectura de URLs como fase independiente entre el motor de decisión y la arquitectura de landing.

Se establece oficialmente la cadena:

INVESTIGACIÓN → MATRICES → MOTOR → URL → LANDING → BLOQUES → DATOS → IA → VALIDACIÓN → N8N → WORDPRESS → MEDICIÓN → APRENDIZAJE

Se establece que la IA no decide libremente las URLs.

Se incorpora un sistema de conservación de evidencias y decisiones para evitar depender de la memoria de la conversación.

Se incorpora una regla de auditoría documental antes de avanzar entre fases.

El motor de decisión continúa definido pero pendiente de validación real.

La arquitectura de URLs está definida pero pendiente de validación real.

El siguiente trabajo oficial será validar conjuntamente:

MOTOR DE DECISIÓN + ARQUITECTURA DE URLs

utilizando datos reales de la investigación de fontanería.
