Protocolo de ejecución del proyecto

Versión: 3.0
Estado: OBLIGATORIO
Propósito: mantener una ejecución secuencial, controlada, verificable y orientada a resultados.

---

1. OBJETIVO

Este documento establece las reglas operativas que deben seguirse durante la construcción y evolución del proyecto.

Su finalidad es evitar:

- desviaciones;
- trabajo paralelo innecesario;
- rediseños prematuros;
- retrocesos injustificados;
- duplicación de información;
- pérdida del estado real del proyecto;
- ejecución de tareas que no contribuyen al objetivo actual.

El proyecto debe avanzar de forma:

- secuencial;
- acumulativa;
- verificable;
- controlada;
- orientada a implementación.

---

2. JERARQUÍA DE CONTROL

La información del proyecto debe interpretarse siguiendo esta jerarquía:

1. "maestro.md"
Contexto persistente, decisiones generales y reglas maestras.

2. "proyecto/roadmap-fabrica-webs.md"
Método universal y reutilizable de la fábrica.

3. "proyecto/roadmap-proyecto.md"
Orden concreto de ejecución del proyecto actual.

4. Documentación técnica
Define cómo debe construirse cada componente.

5. Ejecución
Implementa lo definido respetando las capas anteriores.

Cada documento tiene una función diferente.

Ningún documento técnico puede modificar por sí mismo el orden de ejecución.

Una idea surgida durante una conversación tampoco modifica por sí misma el estado del proyecto.

---

3. FUENTE DE VERDAD DEL ESTADO

La fuente de verdad del estado operativo es:

"proyecto/roadmap-proyecto.md"

Este documento determina:

- fase actual;
- paso actual;
- objetivo;
- entregable;
- estado;
- bloqueos;
- siguiente paso.

El protocolo establece cómo ejecutar, pero no establece cuál es el paso actual.

El roadmap universal establece el método general, pero tampoco sustituye al roadmap específico del proyecto.

"maestro.md" proporciona el contexto persistente necesario para interpretar correctamente el proyecto.

---

4. REGLA PRINCIPAL: TRABAJAR SOBRE EL PASO ACTUAL

Mientras exista un paso activo:

1. trabajar sobre ese paso;
2. mantener su objetivo;
3. completar su entregable;
4. verificar el resultado;
5. actualizar el estado;
6. avanzar únicamente al siguiente paso definido.

No se debe cambiar de objetivo por iniciativa propia.

No se debe abrir una nueva línea de trabajo simplemente porque aparezca una idea mejor.

---

5. NO RETROCEDER SIN BLOQUEO REAL

No se retrocede a una fase o paso anterior salvo que exista un bloqueo real que impida completar el paso actual.

Una mejora no es automáticamente un bloqueo.

Una duda no es automáticamente un bloqueo.

Una optimización no es automáticamente un bloqueo.

Una documentación mejorable no es automáticamente un bloqueo.

Una tecnología alternativa no es automáticamente un bloqueo.

Una contradicción que no afecta al paso actual no es automáticamente un bloqueo.

---

6. DEFINICIÓN DE BLOQUEO REAL

Existe un bloqueo real cuando un problema impide materialmente continuar o completar correctamente el paso actual.

Ejemplos:

- falta una dependencia imprescindible;
- falta un dato imprescindible;
- existen especificaciones incompatibles que impiden implementar;
- el diseño actual hace imposible cumplir un requisito obligatorio;
- continuar produciría un sistema incorrecto;
- continuar produciría un sistema inseguro;
- una decisión previa hace imposible completar el entregable actual.

Si el problema no impide completar el paso actual, no se considera bloqueo.

---

7. PROCEDIMIENTO ANTE UN PROBLEMA

Cuando aparezca un problema:

Paso 1 — Detectar

Identificar exactamente qué ocurre.

Paso 2 — Evaluar

Determinar:

¿Impide completar el paso actual?

Si NO

- registrar el problema;
- mantenerlo pendiente;
- continuar con el paso actual.

Si SÍ

- detener temporalmente la ejecución;
- resolver únicamente el bloqueo;
- verificar la solución;
- volver al paso original;
- continuar desde donde se interrumpió.

No se debe aprovechar un bloqueo para rediseñar partes no relacionadas del sistema.

---

8. NO REDISEÑAR DURANTE LA IMPLEMENTACIÓN

Cuando un paso está en construcción:

primero construir → después verificar → después corregir.

Si aparece una mejora estructural que no bloquea:

DETECTAR
↓
REGISTRAR
↓
CONTINUAR
↓
EVALUAR EN EL MOMENTO PLANIFICADO

No:

DETECTAR
↓
DETENER TODO
↓
REDISEÑAR TODO
↓
RETROCEDER
↓
NO TERMINAR EL PASO

---

9. EJECUCIÓN SECUENCIAL

La secuencia normal de cada paso es:

PASO ACTUAL
↓
OBJETIVO
↓
ENTREGABLE
↓
IMPLEMENTACIÓN
↓
VERIFICACIÓN
↓
CORRECCIÓN
↓
VALIDACIÓN
↓
COMPLETADO
↓
ACTUALIZACIÓN DEL ESTADO
↓
SIGUIENTE PASO

No se deben ejecutar simultáneamente varios pasos independientes.

Solo se permite trabajo paralelo cuando exista una dependencia técnica real que lo justifique.

---

10. DEFINICIÓN DEL PASO ANTES DE EJECUTAR

Antes de comenzar un paso se debe identificar:

FASE ACTUAL:
PASO ACTUAL:
OBJETIVO:
ENTREGABLE:
DEPENDENCIAS:
BLOQUEOS CONOCIDOS:
CRITERIO DE FINALIZACIÓN:
SIGUIENTE PASO:

La información debe recuperarse del:

"proyecto/roadmap-proyecto.md"

Si esa información no está clara, primero debe recuperarse el estado.

No se debe comenzar trabajo sustancial basándose en una suposición sobre el estado.

---

11. CRITERIO PARA INICIAR UNA TAREA

Antes de iniciar una tarea nueva:

¿Contribuye directamente a completar el paso actual?

SÍ

Ejecutarla.

NO

No ejecutarla ahora, salvo que sea necesaria para resolver un bloqueo real.

La tarea puede registrarse para evaluarla posteriormente.

---

12. CONTROL DEL ALCANCE

No se debe ampliar el alcance durante un paso sin una razón objetiva.

Si aparece una nueva funcionalidad:

IDEA
↓
REGISTRAR
↓
NO INTERRUMPIR
↓
EVALUAR POSTERIORMENTE

Si se aprueba, deberá incorporarse al roadmap en el punto correspondiente.

Una funcionalidad nueva no pasa automáticamente a formar parte del paso actual.

---

13. GESTIÓN DE CAMBIOS

Cuando una decisión cambie una parte relevante del proyecto, debe quedar registrada en la fuente documental correspondiente.

La modificación debe hacerse en el documento que sea responsable de esa información.

No se debe duplicar la misma decisión innecesariamente en varios documentos.

La regla es:

una información → una fuente de autoridad.

Los demás documentos pueden hacer referencia a ella, pero no deben mantener copias contradictorias.

---

14. RELACIÓN CON LA DOCUMENTACIÓN

La documentación sirve para:

- definir;
- especificar;
- registrar;
- justificar;
- controlar.

No debe convertirse en una actividad paralela infinita.

Cuando una decisión está suficientemente definida:

se implementa.

No se debe continuar documentando indefinidamente una decisión que ya permite ejecutar.

La documentación técnica explica cómo construir.

El roadmap determina qué construir y cuándo.

El protocolo determina cómo ejecutar el trabajo.

---

15. RELACIÓN CON LAS PRUEBAS

Las pruebas deben verificar componentes reales.

La secuencia preferente es:

DISEÑAR
↓
CONSTRUIR
↓
PROBAR
↓
CORREGIR
↓
VALIDAR

No se deben crear pruebas artificiales indefinidamente si el objetivo del paso es construir primero el componente.

La validación debe producir evidencia suficiente para considerar el entregable completado.

---

16. REVISIÓN DEL REPOSITORIO

Antes de comenzar una nueva sesión de trabajo relevante:

1. revisar "maestro.md";
2. recuperar el método universal;
3. revisar "proyecto/roadmap-proyecto.md";
4. comprobar el estado actual;
5. identificar el paso activo;
6. revisar únicamente la documentación técnica necesaria;
7. comprobar dependencias;
8. ejecutar.

No es necesario rediseñar todo el proyecto en cada sesión.

---

17. CUÁNDO REALIZAR UNA AUDITORÍA COMPLETA

Una auditoría completa del repositorio se realizará cuando:

- comience una fase importante;
- exista un bloqueo estructural;
- aparezca una contradicción que afecte al paso actual;
- exista una modificación importante de arquitectura;
- se solicite explícitamente una auditoría completa.

Una auditoría no debe convertirse en una excusa para retrasar indefinidamente la ejecución.

Una vez finalizada, sus conclusiones deben convertirse en acciones concretas.

---

18. ACTUALIZACIÓN DEL ESTADO

Al completar un paso:

1. marcarlo como completado;
2. registrar brevemente qué se ha ejecutado;
3. registrar los problemas pendientes;
4. registrar las decisiones relevantes;
5. establecer el siguiente paso;
6. actualizar el estado general.

La actualización operativa debe realizarse en:

"proyecto/roadmap-proyecto.md"

No se debe utilizar este protocolo como sustituto del estado del proyecto.

---

19. CONTROL CONTINUO DEL ESTADO

En cualquier momento debe poder responderse:

¿DÓNDE ESTAMOS?

¿QUÉ ESTAMOS CONSTRUYENDO?

¿QUÉ FALTA?

¿QUÉ BLOQUEOS EXISTEN?

¿QUÉ VIENE DESPUÉS?

La respuesta operativa debe obtenerse del:

"proyecto/roadmap-proyecto.md"

Si alguna respuesta no está clara, se debe recuperar primero el estado persistente.

---

20. REGLA CONTRA LA DESVIACIÓN

Debe evitarse este patrón:

PASO ACTUAL
↓
PROBLEMA SECUNDARIO
↓
NUEVA TAREA
↓
OTRO PROBLEMA
↓
RETROCESO
↓
REDISEÑO
↓
NO SE TERMINA EL PASO

Debe utilizarse:

PASO ACTUAL
↓
PROBLEMA
↓
¿BLOQUEA?

NO → REGISTRAR → CONTINUAR

SÍ → RESOLVER → VOLVER AL PASO

↓
COMPLETAR

↓
ACTUALIZAR ESTADO

↓
SIGUIENTE PASO

---

21. REGLA DE PRIORIDAD

Cuando exista conflicto entre:

- una idea surgida durante la conversación;
- una mejora potencial;
- una tarea secundaria;
- una nueva funcionalidad;
- y el paso actual;

tiene prioridad el paso actual definido en "proyecto/roadmap-proyecto.md", salvo que exista un bloqueo real.

---

22. PRINCIPIO DE EJECUCIÓN

El objetivo no es producir documentación continuamente.

El objetivo es producir progreso real, verificable y acumulativo.

La secuencia fundamental es:

CONSTRUIR
↓
VERIFICAR
↓
CORREGIR
↓
VALIDAR
↓
COMPLETAR
↓
ACTUALIZAR ESTADO
↓
AVANZAR

---

23. REGLA DE REUTILIZACIÓN

Este protocolo forma parte del núcleo reutilizable de la fábrica.

Debe poder utilizarse para:

- webs de servicios;
- webs locales;
- directorios;
- sistemas de ayudas y subvenciones;
- sistemas de generación automática;
- otros proyectos de automatización.

El protocolo no depende de un sector concreto.

El método universal define el proceso general.

El roadmap del proyecto define el orden específico.

La documentación técnica define la construcción de cada componente.

La ejecución implementa esas decisiones.

---

24. PROMPT OPERATIVO OBLIGATORIO

Antes de actuar sobre el proyecto, aplicar estas instrucciones:

«Trabaja siempre sobre el paso actual definido en "proyecto/roadmap-proyecto.md".

No cambies de paso por iniciativa propia.

No retrocedas salvo que exista un bloqueo real que impida completar el paso actual.

Si encuentras un problema, determina primero si bloquea.

Si no bloquea, regístralo y continúa.

Si bloquea, resuelve únicamente el bloqueo y vuelve al paso original.

Una mejora futura no es un bloqueo.

Una duda no es un bloqueo.

Una optimización no es un bloqueo.

Una contradicción que no afecta al paso actual no es un bloqueo.

No rediseñes el sistema completo durante una implementación.

No crees documentación innecesaria.

No dupliques información que ya tiene una fuente de autoridad.

Avanza de forma secuencial, verificable y acumulativa.

Cuando un paso termine, actualiza "proyecto/roadmap-proyecto.md".

Después pasa únicamente al siguiente paso definido.»

---

FIN DEL PROTOCOLO DE EJECUCIÓN
