MAESTRO DEL PROYECTO

1. FUNCIÓN DEL DOCUMENTO

Este archivo es el documento maestro de control del proyecto.

Su función es mantener una visión general y actualizada de:

- Qué es el proyecto.
- Qué principios lo gobiernan.
- Cómo está organizado.
- Qué documentos existen.
- Qué fase está completada.
- Qué fase está en curso.
- Qué queda pendiente.
- Qué decisiones importantes se han tomado.
- Qué información debe prevalecer cuando existan contradicciones.

El maestro NO sustituye a los documentos especializados.

Los documentos especializados contienen el detalle de cada área.

---

2. PRINCIPIO DE FUENTE DE VERDAD

El repositorio es la memoria persistente del proyecto.

La memoria de la conversación de ChatGPT no sustituye a la documentación del repositorio.

Todo trabajo importante debe terminar documentado en el repositorio.

Esto incluye:

- Investigación.
- Evidencias.
- Matrices.
- Reglas.
- Decisiones.
- Arquitectura.
- URLs.
- Bloques.
- Modelos de datos.
- Prompts.
- Validaciones.
- Automatizaciones.
- Resultados.

---

3. REGLA DE PRIORIDAD ENTRE DOCUMENTOS

El maestro es el documento de control general.

Los documentos especializados contienen la información detallada.

Cuando exista una contradicción:

1. Comprobar la fecha de cada información.
2. Comprobar si existe una actualización posterior.
3. Comprobar la evidencia que originó la decisión.
4. Dar prioridad a la información posterior y mejor fundamentada.
5. Actualizar los documentos afectados.
6. Registrar el cambio.

No se debe dar prioridad automática a una información antigua simplemente porque aparezca en "maestro.md".

Una actualización posterior y suficientemente fundamentada puede sustituir una decisión anterior.

El maestro debe actualizarse después para reflejar la nueva situación.

---

4. SISTEMA DE ACTUALIZACIONES

Las decisiones importantes deben conservar historial.

Cada actualización relevante debe poder identificar:

- Fecha.
- Documento afectado.
- Información anterior.
- Nueva información.
- Motivo.
- Evidencia.
- Consecuencia.

Las actualizaciones posteriores prevalecen sobre la información anterior cuando exista contradicción y estén suficientemente justificadas.

No se debe borrar el historial de decisiones importantes.

---

5. OBJETIVO DEL PROYECTO

Crear un sistema escalable para generar páginas SEO locales de servicios profesionales.

El sistema debe permitir combinar:

SERVICIO × LOCALIDAD

y, cuando esté justificado:

SERVICIO × SUBSERVICIO × LOCALIDAD

para detectar oportunidades y generar páginas útiles, diferenciadas y automatizables.

El proyecto no pretende generar miles de páginas por volumen.

Pretende identificar y crear únicamente páginas que tengan:

- intención clara;
- utilidad;
- oportunidad;
- diferenciación;
- coherencia;
- capacidad de aportar valor real.

---

6. ARQUITECTURA GENERAL DEL SISTEMA

El flujo oficial es:

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

SISTEMA DE BLOQUES

↓

MODELO DE DATOS

↓

IA / CONTENIDO

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS / PUBLICACIÓN

↓

MEDICIÓN

↓

APRENDIZAJE

Ninguna fase debe saltarse sin justificación.

---

7. ARQUITECTURA DOCUMENTAL

CONTROL GENERAL

"maestro.md"

Control general del proyecto.

---

METODOLOGÍA

"proyecto/metodologia.md"

Define cómo se trabaja y en qué orden.

---

SEO

"proyecto/seo/"

Arquitectura SEO

"proyecto/seo/arquitectura-seo.md"

Define la arquitectura SEO general.

Arquitectura de URLs

"proyecto/seo/arquitectura-urls.md"

Define cómo se transforma una oportunidad aprobada en una URL.

Estructuras base:

"/{servicio}/{localidad}/"

"/{servicio}/{subservicio}/{localidad}/"

La IA no decide libremente la estructura de URL.

Motor de decisión

"proyecto/seo/motor-decision.md"

Define cómo se decide:

- CREAR.
- AGRUPAR.
- INVESTIGAR.
- NO CREAR.

Investigación de fontanería

"proyecto/seo/investigacion-fontaneria.md"

Contiene la investigación realizada sobre el sector.

Matriz de servicios de fontanería

"proyecto/seo/matriz-servicios-fontaneria.md"

Contiene la estructura de servicios y subservicios investigados.

Matriz de localidades

"proyecto/seo/matriz-localidades.md"

Contiene la información territorial utilizada para las decisiones.

---

8. DOCUMENTOS FUTUROS

Todavía deberán crearse o definirse los documentos necesarios para:

Arquitectura de landing

Definirá la estructura lógica de las páginas.

Sistema de bloques

Definirá los bloques reutilizables.

Modelo de datos

Definirá los datos necesarios para construir cada página.

Sistema de contenido / IA

Definirá prompts, reglas y restricciones de generación.

Validación

Definirá las comprobaciones antes de publicar.

Registro de decisiones

Conservará las decisiones concretas tomadas sobre combinaciones reales.

Automatización

Documentará N8N y sus workflows.

Publicación

Documentará la integración con WordPress u otra plataforma.

Medición

Documentará métricas, resultados y aprendizaje.

Estos documentos no deben crearse antes de que llegue su fase correspondiente, salvo que exista una razón documentada.

---

9. METODOLOGÍA

La metodología oficial está definida en:

"proyecto/metodologia.md"

El orden de trabajo es:

1. Investigación.
2. Matrices.
3. Motor.
4. Arquitectura de URLs.
5. Arquitectura de landing.
6. Bloques.
7. Modelo de datos.
8. IA/contenido.
9. Validación.
10. N8N.
11. Publicación.
12. Medición.
13. Aprendizaje.

La metodología debe ser aplicable posteriormente a otros servicios.

---

10. MOTOR DE DECISIÓN

El motor utiliza variables como:

- Demanda.
- Intención.
- Potencial comercial.
- Relevancia territorial.
- Competencia.
- Diferenciación.
- Información disponible.
- Riesgo de duplicación.
- Utilidad potencial.

Resultados:

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

El motor está:

DEFINIDO

pero:

PENDIENTE DE VALIDACIÓN REAL

No se considera definitivamente validado hasta probarlo con datos reales.

---

11. ARQUITECTURA DE URL

La arquitectura está definida.

Estructura principal:

"/{servicio}/{localidad}/"

Estructura secundaria:

"/{servicio}/{subservicio}/{localidad}/"

Ejemplos:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

La existencia de una combinación no implica automáticamente la creación de una URL.

La combinación debe pasar primero por el motor.

La arquitectura está:

DEFINIDA

pero:

PENDIENTE DE VALIDACIÓN CON EL MOTOR

---

12. RELACIÓN MOTOR → URL

El flujo correcto es:

DATOS

↓

MOTOR

↓

DECISIÓN

↓

URL

Ejemplo conceptual:

SERVICIO = fontanero
SUBSERVICIO = desatascos
LOCALIDAD = Marbella

DECISIÓN = CREAR

URL = /fontanero/desatascos/marbella/

La IA recibe posteriormente esta información.

La IA no debe decidir libremente si existe una página ni qué URL utilizar.

---

13. INVESTIGACIÓN DE FONTANERÍA

La investigación inicial de fontanería está documentada.

Incluye:

- Observaciones del mercado.
- Patrones encontrados.
- Servicios.
- Subservicios.
- Localidades.
- Competencia.
- SERP.
- Hipótesis.
- Conclusiones.

Esta investigación sirve como base para validar el sistema.

No debe tratarse como una verdad universal para otros sectores.

---

14. MATRICES

Las matrices son la representación estructurada de la investigación.

Actualmente se dispone de:

- Matriz de servicios de fontanería.
- Matriz de localidades.

Las matrices deben mantenerse actualizadas cuando aparezca información nueva suficientemente fundamentada.

No deben sobrescribirse decisiones anteriores sin conservar el historial cuando el cambio sea relevante.

---

15. REGLA DE TRAZABILIDAD

Cada decisión importante debería poder relacionarse con:

EVIDENCIA

↓

DATO

↓

MATRIZ

↓

MOTOR

↓

DECISIÓN

↓

URL

↓

LANDING

Esto permitirá reconstruir posteriormente por qué se creó una página.

---

16. REGISTRO DE DECISIONES

Las decisiones concretas que se obtengan durante la validación se documentarán en un archivo específico.

Ese archivo será independiente del motor.

El motor contiene:

REGLAS

El registro de decisiones contiene:

RESULTADOS DE APLICAR LAS REGLAS

Ejemplo:

Fecha:
2026-08-23

Servicio:
Fontanero

Subservicio:
Desatascos

Localidad:
Marbella

Datos utilizados:
...

Resultado del motor:
CREAR

URL:
 /fontanero/desatascos/marbella/

Motivo:
...

Versión del motor:
...

Evidencia:
...

Esto evita mezclar reglas generales con resultados concretos.

---

17. REGLA DE CONSERVACIÓN

Todo trabajo de investigación que produzca una conclusión, matriz, decisión, regla, URL, estructura o criterio debe quedar documentado.

No debemos depender de:

- memoria de la IA;
- historial de conversación;
- recuerdos personales;
- reconstrucciones posteriores.

El repositorio debe contener la información necesaria para continuar el proyecto.

---

18. AUDITORÍA DOCUMENTAL

Antes de avanzar entre fases se debe comprobar:

- Que los documentos sean coherentes.
- Que no existan contradicciones.
- Que el maestro refleje el estado real.
- Que las decisiones importantes estén documentadas.
- Que las matrices estén disponibles.
- Que las reglas utilizadas estén identificadas.
- Que la información no esté duplicada innecesariamente.
- Que el siguiente paso esté definido.

Si existe una pérdida documental relevante, se detiene el avance y se corrige primero.

---

19. REGLA PARA NUEVOS SERVICIOS

Cuando se trabaje con un nuevo servicio, no se copiarán automáticamente las conclusiones de fontanería.

Se reutilizará:

- La metodología.
- La arquitectura general.
- El sistema documental.
- Las reglas generales.
- El modelo técnico.

Pero se realizará una investigación específica del nuevo sector.

Ejemplo:

ABOGADOS

Investigación específica.

↓

Matriz de servicios jurídicos.

↓

Matriz territorial.

↓

Adaptación del motor.

↓

Validación.

↓

Arquitectura URL.

↓

Landing.

↓

Bloques.

↓

Datos.

↓

IA.

↓

Automatización.

---

20. PRINCIPIO DE IA

La IA es una herramienta de ejecución y generación.

No debe sustituir las decisiones estratégicas previamente definidas.

La IA no debe decidir arbitrariamente:

- Qué servicios existen.
- Qué páginas deben crearse.
- Qué URLs utilizar.
- Qué localidades inventar.
- Qué datos comerciales utilizar.
- Qué afirmaciones realizar.

La IA recibe datos y reglas y trabaja dentro de ellas.

---

21. PRINCIPIO DE AUTOMATIZACIÓN

N8N debe ejecutar el proceso definido.

No debe utilizarse para ocultar decisiones todavía no resueltas.

La automatización completa se realizará cuando estén suficientemente definidas:

- Investigación.
- Matrices.
- Motor.
- URLs.
- Landing.
- Bloques.
- Datos.
- IA.
- Validación.

---

22. ESTADO ACTUAL

COMPLETADO

- Investigación inicial de fontanería.
- Matriz de servicios.
- Matriz de localidades.
- Arquitectura SEO.
- Motor de decisión definido.
- Arquitectura de URLs definida.
- Metodología actualizada.
- Arquitectura documental definida.

EN VALIDACIÓN

- Motor de decisión.
- Arquitectura de URLs.

PENDIENTE

- Registro de decisiones.
- Arquitectura de landing.
- Sistema de bloques.
- Modelo de datos.
- Sistema de contenido/IA.
- Validación automática.
- Automatización N8N.
- Integración WordPress.
- Publicación controlada.
- Medición.
- Aprendizaje.

---

23. SIGUIENTE PASO OFICIAL

El siguiente paso es:

VALIDAR EL MOTOR DE DECISIÓN Y LA ARQUITECTURA DE URL CON DATOS REALES

Se utilizarán combinaciones reales procedentes de las matrices de fontanería.

Para cada combinación se comprobará:

1. Datos de entrada.
2. Puntuación.
3. Decisión.
4. Justificación.
5. Riesgo de duplicación.
6. URL resultante.
7. Si merece una landing independiente.
8. Si existe información suficiente para construirla.

Los resultados se documentarán en el futuro:

"proyecto/seo/registro-decisiones.md"

No se debe diseñar todavía la arquitectura definitiva de landing hasta completar esta validación.

---

24. REGLA DE NO AVANZAR POR IMPULSO

El proyecto debe avanzar por fases.

No se debe crear un archivo simplemente porque parezca útil en ese momento.

Antes de crear un documento nuevo hay que determinar:

- Qué función tiene.
- Qué información contendrá.
- De qué documentos depende.
- Qué documentos dependen de él.
- Si esa información ya existe.
- Dónde encaja dentro de la metodología.

Esto evita:

- duplicaciones;
- contradicciones;
- pérdida de información;
- archivos innecesarios;
- arquitectura documental desordenada.

---

25. REGISTRO DE ACTUALIZACIONES

2026-08-23

Se actualiza el documento maestro para sincronizarlo con la metodología y la arquitectura actual del proyecto.

Se incorpora explícitamente:

- Arquitectura de URLs.
- Relación Motor → URL.
- Sistema de trazabilidad.
- Registro futuro de decisiones.
- Auditoría documental.
- Regla de conservación de información.
- Separación entre reglas del motor y resultados del motor.

Se establece oficialmente:

INVESTIGACIÓN → MATRICES → MOTOR → URL → LANDING → BLOQUES → DATOS → IA → VALIDACIÓN → N8N → PUBLICACIÓN → MEDICIÓN → APRENDIZAJE

Se establece que el motor y la arquitectura de URLs están definidos pero pendientes de validación real.

Se establece que el siguiente paso es validar ambos utilizando datos reales de las matrices de fontanería.

No se debe avanzar a arquitectura de landing hasta completar esta validación.
