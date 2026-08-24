PROTOCOLO DE EJECUCIÓN DEL PROYECTO

Versión: 1.0
Estado: OBLIGATORIO
Propósito: mantener una ejecución secuencial, controlada y orientada a resultados.

---

1. OBJETIVO

Este documento establece las reglas que deben seguirse durante la construcción y evolución del proyecto.

Su finalidad es evitar desviaciones, rediseños innecesarios, retrocesos de fase y trabajo paralelo que no contribuya directamente al hito actual.

El proyecto debe avanzar de forma:

- secuencial;
- acumulativa;
- verificable;
- controlada;
- orientada a implementación.

---
2. FUENTE DE VERDAD DEL ESTADO

El estado y el orden de ejecución del proyecto están determinados por:

"proyecto/roadmap-proyecto.md"

Este documento NO determina qué fase o paso debe ejecutarse.

El roadmap del proyecto determina siempre:

- fase actual;
- paso actual;
- objetivo del paso;
- entregable esperado;
- pasos completados;
- siguiente paso;
- bloqueos conocidos.

"proyecto/roadmap-fabrica-webs.md" define el método general reutilizable.

"maestro.md" actúa como documento de control y obliga a recuperar el estado persistente antes de ejecutar.

Los demás documentos contienen especificaciones técnicas y no pueden cambiar por sí mismos el orden de ejecución.

Si un documento técnico propone un trabajo diferente al paso actual, esa propuesta no cambia el roadmap.

Solo una decisión explícita registrada en el roadmap puede cambiar el orden de ejecución.

---

3. REGLA PRINCIPAL: NO RETROCEDER SIN BLOQUEO REAL

NO SE RETROCEDE A UNA FASE ANTERIOR SIN UN BLOQUEO REAL.

Mientras exista un hito activo:

1. se trabaja sobre ese hito;
2. no se cambia de objetivo por iniciativa propia;
3. no se rediseña una fase anterior;
4. no se abre una nueva línea de trabajo porque aparezca una posible mejora.

Una mejora, duda, contradicción o posible optimización no constituye automáticamente un bloqueo.

---

4. QUÉ HACER CUANDO APARECE UN PROBLEMA

Si durante la construcción aparece un problema:

Paso 1 — Registrar

Identificar y registrar el problema.

Paso 2 — Determinar impacto

Preguntar:

«¿Este problema impide completar el hito actual?»

Si NO bloquea

- registrar el problema;
- dejarlo pendiente;
- continuar con el hito actual.

Si SÍ bloquea

- detener temporalmente la ejecución;
- resolver únicamente el bloqueo;
- comprobar que el bloqueo queda solucionado;
- volver inmediatamente al hito original.

---

5. DEFINICIÓN DE BLOQUEO REAL

Se considera bloqueo real únicamente un problema que impida materialmente continuar o completar el hito actual.

Ejemplos:

- una dependencia técnica imprescindible no existe;
- dos especificaciones incompatibles impiden implementar el componente;
- falta un dato imprescindible para ejecutar la tarea;
- el diseño actual hace imposible cumplir un requisito obligatorio;
- una implementación produciría un sistema incorrecto o inseguro.

No son bloqueos por sí mismos:

- una mejora futura;
- una optimización;
- una idea nueva;
- una posible refactorización;
- una contradicción que no afecta al hito actual;
- una documentación que podría estar mejor;
- una tecnología alternativa que podría ser mejor.

---

6. NO REDISEÑAR DURANTE LA IMPLEMENTACIÓN

Cuando un hito está en fase de construcción:

primero se construye; después se evalúa.

No se debe interrumpir continuamente una implementación para rediseñar la arquitectura completa.

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
REDISEÑAR
↓
VOLVER ATRÁS

---

7. TRABAJO SECUENCIAL

Cada hito debe tener:

HITO ACTUAL
↓
OBJETIVO
↓
ENTREGABLE
↓
IMPLEMENTACIÓN
↓
VERIFICACIÓN
↓
COMPLETADO
↓
SIGUIENTE HITO

No se debe trabajar simultáneamente en varios hitos salvo que exista una dependencia técnica justificada.

---

8. DEFINICIÓN DEL HITO ANTES DE TRABAJAR

Antes de comenzar un hito debe quedar claro:

HITO ACTUAL:
OBJETIVO:
ENTREGABLE:
BLOQUEOS CONOCIDOS:
SIGUIENTE HITO:

Esto permite comprobar en todo momento si el trabajo que se está realizando pertenece realmente al hito.

---

9. CRITERIO PARA DECIDIR SI UNA TAREA PERTENECE AL HITO

Antes de iniciar una tarea nueva se debe preguntar:

«¿Esta tarea contribuye directamente a completar el hito actual?»

Si la respuesta es:

SÍ

→ realizarla.

Si la respuesta es:

NO

→ no iniciar esa tarea salvo que sea necesaria para resolver un bloqueo real.

---

10. CAMBIOS DE ALCANCE

No se debe ampliar el alcance durante un hito sin una razón objetiva.

Si aparece una nueva funcionalidad:

IDEA
↓
REGISTRAR
↓
NO INTERRUMPIR
↓
EVALUAR POSTERIORMENTE

Las nuevas funcionalidades pasan a formar parte de futuros hitos si se aprueban.

---

11. RELACIÓN CON LA DOCUMENTACIÓN

La documentación sirve para:

- definir;
- registrar;
- justificar;
- controlar.

No debe convertirse en una actividad paralela que retrase indefinidamente la construcción.

Una vez que una decisión está suficientemente definida:

se implementa.

No se sigue documentando indefinidamente la misma decisión.

---

12. RELACIÓN CON LAS PRUEBAS

Las pruebas deben utilizarse para verificar componentes reales.

No se deben crear pruebas artificiales indefinidamente antes de construir el sistema cuando el objetivo del hito sea precisamente construirlo.

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

---

13. REVISIÓN DEL REPOSITORIO

Antes de comenzar un nuevo hito:

1. revisar "maestro.md";
2. identificar el hito actual;
3. revisar únicamente los documentos necesarios para ese hito;
4. comprobar dependencias;
5. comenzar la ejecución.

No es necesario volver a rediseñar todo el proyecto en cada sesión.

Una revisión completa del repositorio debe realizarse cuando:

- comienza una fase importante;
- existe un bloqueo;
- se detecta una contradicción que afecta al hito;
- se solicita explícitamente una auditoría completa.

---

14. REGLA CONTRA LA DESVIACIÓN

El asistente debe evitar especialmente este patrón:

HITO ACTUAL
↓
ENCUENTRA PROBLEMA SECUNDARIO
↓
ABRE NUEVA TAREA
↓
ENCUENTRA OTRO PROBLEMA
↓
RETROCEDE
↓
REDISEÑA
↓
NO TERMINA EL HITO

Debe utilizar:

HITO ACTUAL
↓
PROBLEMA
↓
¿BLOQUEA?
├── NO → REGISTRAR → CONTINUAR
└── SÍ → RESOLVER → VOLVER AL HITO
↓
COMPLETAR
↓
ACTUALIZAR MAESTRO
↓
SIGUIENTE HITO

---

15. ACTUALIZACIÓN DEL MAESTRO

Al completar un hito:

1. marcar el hito como COMPLETADO;
2. registrar brevemente qué se ha construido;
3. registrar problemas pendientes;
4. establecer el siguiente hito;
5. actualizar el estado general del proyecto.

No se debe avanzar al siguiente hito sin actualizar el estado cuando dicha actualización sea necesaria para mantener el control del proyecto.

---

16. CONTROL DE ESTADO

En cualquier momento, el proyecto debe poder responder claramente:

¿DÓNDE ESTAMOS?
¿QUÉ ESTAMOS CONSTRUYENDO?
¿QUÉ FALTA PARA TERMINARLO?
¿QUÉ BLOQUEOS EXISTEN?
¿QUÉ VIENE DESPUÉS?

Si alguna de estas respuestas no está clara, primero se debe recuperar el estado desde "maestro.md".

---

17. PROMPT OPERATIVO OBLIGATORIO

Antes de actuar sobre el proyecto, aplicar mentalmente estas instrucciones:

«Trabaja siempre sobre el hito actual definido en "maestro.md".

No cambies de hito por iniciativa propia.

No retrocedas a una fase anterior salvo que exista un bloqueo real que impida completar el hito actual.

Si encuentras un problema, regístralo y determina si bloquea el hito.

Si no bloquea, continúa.

Si bloquea, detén la ejecución, resuelve únicamente el bloqueo y vuelve al hito original.

Una mejora futura no es un bloqueo.

Una duda no es un bloqueo.

Una optimización no es un bloqueo.

Una contradicción que no afecta al hito actual no es un bloqueo.

No rediseñes el sistema mientras estás implementando un hito.

No crees documentación innecesaria.

No cambies la arquitectura por iniciativa propia durante una implementación.

Avanza de forma secuencial, verificable y acumulativa.

Cuando un hito termine, actualiza "maestro.md" y pasa al siguiente hito definido.»

---

18. REGLA DE PRIORIDAD

Cuando exista conflicto entre:

- una idea surgida durante la conversación;
- una mejora potencial;
- una tarea secundaria;
- y el hito actual definido en "maestro.md";

el hito actual tiene prioridad, salvo que exista un bloqueo real.

---

19. PRINCIPIO FINAL

CONSTRUIR → VERIFICAR → CORREGIR → COMPLETAR → AVANZAR.

No:

DISEÑAR → REDISEÑAR → DOCUMENTAR → REDISEÑAR → VOLVER ATRÁS.

El objetivo del protocolo es que cada sesión produzca progreso real y acumulativo hacia el sistema final.

---

FIN DEL PROTOCOLO DE EJECUCIÓN
