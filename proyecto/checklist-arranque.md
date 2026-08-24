CHECKLIST DE ARRANQUE DEL PROYECTO

Versión: 1.1
Estado: OBLIGATORIO
Propósito: garantizar que cualquier sesión de trabajo comienza desde el estado persistente real del proyecto y no desde suposiciones o memoria.

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
- [ ] Identificar la fase actual en el roadmap del proyecto.
- [ ] Identificar el PASO ACTUAL.
- [ ] Identificar el objetivo del paso.
- [ ] Identificar el entregable esperado.
- [ ] Identificar los pasos completados.
- [ ] Identificar el siguiente paso.
- [ ] Identificar los bloqueos conocidos.

El "roadmap-proyecto.md" es la fuente de verdad del estado y del orden de ejecución.

La memoria de conversación no determina el estado del proyecto.
---

3. RECUPERACIÓN DE LA METODOLOGÍA

Leer obligatoriamente:

"proyecto/protocolo-ejecucion.md"

Comprobar:

- [ ] No retroceder sin bloqueo real.
- [ ] No cambiar de hito por iniciativa propia.
- [ ] No rediseñar durante la implementación.
- [ ] Registrar problemas que no bloqueen.
- [ ] Resolver únicamente problemas que bloqueen.
- [ ] Volver al hito original después de resolver un bloqueo.
- [ ] Priorizar construcción sobre documentación innecesaria.

---

4. DOCUMENTACIÓN DEL HITO

Identificar qué documentos son necesarios para ejecutar el hito actual.

Leer los documentos relevantes para ese trabajo antes de ejecutarlo.

Comprobar:

- [ ] Arquitectura relevante.
- [ ] Modelo de datos relevante.
- [ ] Contratos relevantes.
- [ ] Especificaciones relevantes.
- [ ] Dependencias técnicas relevantes.

No es necesario revisar todo el repositorio en cada sesión.

Una revisión completa solo se realiza cuando:

- comienza una fase importante;
- existe un bloqueo real;
- existe una contradicción que afecta al hito;
- se solicita expresamente una auditoría completa.

---

5. COMPROBACIÓN DEL OBJETIVO

Antes de ejecutar una tarea preguntar:

«¿Esta tarea contribuye directamente a completar el HITO ACTUAL?»

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
- una documentación mejorable;
- una contradicción que no afecta al hito;

NO cambiar el objetivo.

Registrar para evaluación posterior y continuar.

---

7. CONTROL DE BLOQUEOS

Cuando aparece un problema:

PROBLEMA
   ↓
¿BLOQUEA EL HITO?
   ↓
 ┌───────────────┐
 │               │
 NO              SÍ
 │               │
 ▼               ▼
REGISTRAR      DETENER
 │               │
 ▼               ▼
CONTINUAR      RESOLVER
                 │
                 ▼
             VOLVER AL
             HITO ORIGINAL

---

8. CONFIRMACIÓN ANTES DE EJECUTAR

Antes de comenzar el trabajo debe poder responderse:

FASE:
HITO ACTUAL:
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

- [ ] Ejecutar únicamente la tarea correspondiente al hito.
- [ ] No abrir nuevos frentes innecesarios.
- [ ] No retroceder a fases anteriores.
- [ ] No rediseñar componentes que no sean necesarios.
- [ ] Mantener coherencia con los documentos fuente.

---

10. FINALIZACIÓN DE LA TAREA

Al terminar:

- [ ] Comprobar qué se ha construido.
- [ ] Comprobar si el hito está completo.
- [ ] Registrar problemas pendientes.
- [ ] Determinar el siguiente paso.
- [ ] Si el hito está COMPLETADO, actualizar "maestro.md".

---

11. REGLA DE PERSISTENCIA

Las decisiones importantes deben quedar registradas en GitHub.

No depender exclusivamente de:

- memoria de conversación;
- contexto temporal;
- explicaciones anteriores;
- suposiciones.

El repositorio debe permitir reconstruir el estado del proyecto.

---

12. REGLA PARA CADA "SIGUE"

Cuando el usuario indique:

«Sigue»

debe interpretarse como:

«Continuar desde el HITO ACTUAL del proyecto.»

No significa:

- buscar una tarea diferente;
- volver a una fase anterior;
- rediseñar la arquitectura;
- iniciar una nueva línea de trabajo.

Antes de continuar se debe aplicar este checklist.

---

13. PRINCIPIO FINAL

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
