CHECKLIST DE ARRANQUE DEL PROYECTO

Versión: 2.0
Estado: OBLIGATORIO
Propósito: garantizar que cualquier sesión comienza desde el estado persistente real del proyecto y respeta la jerarquía documental.

---

1. REGLA PRINCIPAL

NO SE DEBE COMENZAR TRABAJO TÉCNICO SIN COMPLETAR ESTE CHECKLIST.

Antes de realizar cualquier tarea sobre el proyecto se debe recuperar el estado persistente desde GitHub.

La memoria de la conversación no sustituye a los archivos del proyecto.

---

2. RECUPERACIÓN DEL ESTADO

Antes de trabajar:

- [ ] Leer "maestro.md".
- [ ] Leer "proyecto/roadmap-fabrica-webs.md".
- [ ] Leer "proyecto/roadmap-proyecto.md".
- [ ] Leer "proyecto/protocolo-ejecucion.md".
- [ ] Identificar la fase actual.
- [ ] Identificar el paso actual.
- [ ] Identificar el objetivo.
- [ ] Identificar el entregable.
- [ ] Identificar los pasos completados.
- [ ] Identificar el siguiente paso.
- [ ] Identificar los bloqueos conocidos.

"proyecto/roadmap-proyecto.md" es la fuente de verdad del estado y del orden de ejecución.

La memoria de conversación no determina el estado del proyecto.

---

3. RECUPERACIÓN DE LA METODOLOGÍA

Comprobar que el trabajo respeta:

- [ ] El roadmap universal.
- [ ] El protocolo de ejecución.
- [ ] La jerarquía documental.
- [ ] La regla de no retroceder sin bloqueo real.
- [ ] La regla de no cambiar de paso por iniciativa propia.
- [ ] La regla de no rediseñar durante la implementación.
- [ ] La regla de registrar problemas no bloqueantes.
- [ ] La regla de resolver únicamente bloqueos reales.
- [ ] La regla de volver al paso original después de resolver un bloqueo.
- [ ] La regla de priorizar construcción sobre documentación innecesaria.

---

4. DOCUMENTACIÓN DEL PASO ACTUAL

Identificar qué documentos son necesarios para ejecutar el paso actual.

Leer únicamente los documentos relevantes para ese trabajo.

Comprobar:

- [ ] Arquitectura relevante.
- [ ] Modelo de datos relevante.
- [ ] Contratos relevantes.
- [ ] Especificaciones relevantes.
- [ ] Dependencias técnicas relevantes.

No es necesario revisar todo el repositorio en cada sesión.

Una auditoría completa solo se realiza cuando:

- comienza una fase importante;
- existe un bloqueo estructural;
- existe una contradicción que afecta al paso actual;
- se solicita expresamente.

---

5. COMPROBACIÓN DEL OBJETIVO

Antes de ejecutar una tarea preguntar:

«¿Esta tarea contribuye directamente a completar el PASO ACTUAL?»

Si SÍ

Continuar.

Si NO

No iniciar la tarea salvo que sea necesaria para resolver un bloqueo real.

---

6. CONTROL DE DESVIACIÓN

Si durante la revisión aparece:

- una mejora;
- una optimización;
- una idea nueva;
- una posible refactorización;
- documentación mejorable;
- una contradicción que no afecta al paso actual;

NO cambiar el objetivo.

Registrar para evaluación posterior y continuar.

---

7. CONTROL DE BLOQUEOS

Cuando aparece un problema:

PROBLEMA
↓
¿BLOQUEA EL PASO ACTUAL?

NO

REGISTRAR
↓
CONTINUAR

SÍ

DETENER
↓
RESOLVER
↓
VERIFICAR
↓
VOLVER AL PASO ORIGINAL

---

8. CONFIRMACIÓN ANTES DE EJECUTAR

Antes de comenzar el trabajo debe poder responderse:

FASE:
PASO ACTUAL:
OBJETIVO:
ENTREGABLE:
DOCUMENTOS CONSULTADOS:
BLOQUEOS:
TAREA ACTUAL:

Si alguna respuesta no está clara:

NO EJECUTAR TODAVÍA.

Primero recuperar la información necesaria desde GitHub.

---

9. EJECUCIÓN

Una vez completados los pasos anteriores:

- [ ] Ejecutar únicamente la tarea correspondiente al paso actual.
- [ ] No abrir nuevos frentes innecesarios.
- [ ] No retroceder a fases anteriores.
- [ ] No rediseñar componentes que no sean necesarios.
- [ ] Mantener coherencia con los documentos fuente.
- [ ] Verificar el resultado antes de considerar completada la tarea.

---

10. FINALIZACIÓN DE LA TAREA

Al terminar:

- [ ] Comprobar qué se ha ejecutado.
- [ ] Comprobar si el paso está completo.
- [ ] Registrar problemas pendientes.
- [ ] Registrar decisiones relevantes cuando corresponda.
- [ ] Determinar el siguiente paso.
- [ ] Actualizar "proyecto/roadmap-proyecto.md".

El estado operativo se actualiza en el roadmap del proyecto.

No utilizar "maestro.md" como registro rutinario del estado de cada paso.

---

11. REGLA DE PERSISTENCIA

Las decisiones importantes deben quedar registradas en GitHub en el documento que sea su fuente de autoridad.

No depender exclusivamente de:

- memoria de conversación;
- contexto temporal;
- explicaciones anteriores;
- suposiciones.

El repositorio debe permitir reconstruir el estado del proyecto.

---

12. REGLA PARA CADA «SIGUE»

Cuando el usuario indique:

«Sigue»

debe interpretarse como:

«Continuar desde el PASO ACTUAL del proyecto.»

Antes de continuar:

1. recuperar el estado;
2. aplicar este checklist;
3. comprobar el paso actual;
4. comprobar bloqueos;
5. continuar desde el punto correspondiente.

«Sigue» no significa:

- buscar una tarea diferente;
- volver a una fase anterior;
- rediseñar la arquitectura;
- iniciar una nueva línea de trabajo.

---

13. JERARQUÍA DOCUMENTAL

La información debe interpretarse así:

"maestro.md"
→ contexto persistente y reglas maestras.

"proyecto/roadmap-fabrica-webs.md"
→ metodología universal.

"proyecto/roadmap-proyecto.md"
→ estado y orden del proyecto actual.

Documentación técnica
→ especificaciones de construcción.

Implementación
→ ejecución de las especificaciones.

En caso de duda, no crear una segunda fuente de verdad.

---

14. PRINCIPIO FINAL

LEER
↓
UBICAR
↓
COMPROBAR
↓
EJECUTAR
↓
VERIFICAR
↓
REGISTRAR
↓
AVANZAR

Nunca:

RECORDAR
↓
SUPONER
↓
DESVIARSE

---

FIN DEL CHECKLIST DE ARRANQUE
