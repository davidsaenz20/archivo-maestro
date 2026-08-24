REGISTRO DE DECISIONES SEO

Versión del registro: 2.0
Estado: ACTIVO

---

1. FUNCIÓN

Este documento registra las decisiones tomadas por el motor SEO sobre oportunidades concretas.

El registro conserva:

- la oportunidad analizada;
- las evidencias utilizadas;
- la decisión obtenida;
- las razones;
- las versiones utilizadas;
- las acciones posteriores;
- los cambios de decisión.

No sustituye:

- el modelo de datos;
- las matrices;
- las evidencias;
- el motor de decisión;
- la arquitectura SEO;
- la arquitectura de URLs.

Su función es conservar el resultado de aplicar el sistema a casos reales.

---

2. DECISIONES VÁLIDAS

Las únicas decisiones SEO válidas son:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

"REVISAR" no es una decisión SEO.

Los estados operativos de una landing pertenecen al sistema de construcción y publicación.

---

3. ESTRUCTURA DE UNA DECISIÓN

Cada decisión debe conservar como mínimo:

opportunity_id
date
identity
intent
research
decision
reason
architecture
landing_status
versions
next_action
history

---

DECISIÓN OPP-001

4. IDENTIFICACIÓN

Opportunity ID: "OPP-001"

Servicio: Fontanero

Subservicio: "null"

Localidad: Marbella

Provincia: Málaga

País: España

Tipo de página: "servicio_localidad"

Fecha inicial: 2026-08-23

---

5. INTENCIÓN

Tipo: "local + commercial"

Confianza: "high"

Estado de evidencia: "observed"

Existe intención local y comercial identificable para usuarios que buscan servicios de fontanería en Marbella.

La evidencia procede del análisis de resultados y oferta existente.

---

6. DEMANDA

Estado: "unknown"

Actualmente no existe un dato cuantitativo suficientemente documentado de volumen de búsqueda.

Por tanto:

demanda = UNKNOWN

No se utilizarán estimaciones como datos reales.

---

7. POTENCIAL COMERCIAL

Estado: "probable alto"

La intención está relacionada con contratación directa de servicios de fontanería.

Se observan señales comerciales relacionadas con:

- reparaciones;
- urgencias;
- fugas;
- desatascos;
- instalaciones;
- mantenimiento.

---

8. RELEVANCIA TERRITORIAL

Estado: "confirmed"

Marbella es una localidad claramente diferenciada.

Existe oferta profesional específica orientada a esta localidad.

---

9. COMPETENCIA

Estado: "high"

Se han identificado múltiples empresas y páginas orientadas a:

fontanero + Marbella

La existencia de competencia demuestra actividad comercial, pero no garantiza por sí misma que deba crearse una nueva landing.

---

10. DIFERENCIACIÓN

Estado: "insufficient"

La competencia utiliza argumentos habituales como:

- urgencias;
- rapidez;
- reparaciones;
- fugas;
- desatascos;
- presupuestos;
- experiencia;
- disponibilidad.

Todavía no existe evidencia suficiente de una diferenciación propia que justifique una landing independiente.

---

11. RIESGO DE DUPLICACIÓN

Estado: "medium/high"

La intención general de fontanería puede solaparse con futuras páginas de:

- desatascos;
- fugas;
- reparaciones;
- termos;
- calderas;
- grifería;
- sanitarios;
- instalaciones;
- urgencias.

La futura arquitectura deberá separar claramente las intenciones cuando exista evidencia suficiente.

---

12. INFORMACIÓN LOCAL

Estado: "partial"

Existe información suficiente para identificar:

- localidad;
- provincia;
- oferta profesional;
- contexto comercial.

Todavía no existe información propia suficiente para construir una diferenciación territorial profunda.

No se deben inventar datos locales.

---

13. EVIDENCIAS

Las evidencias utilizadas deben mantenerse en:

proyecto/seo/evidencias-fontaneria.md

Las fuentes concretas deberán conservarse allí o en los documentos de investigación correspondientes.

---

14. MOTOR UTILIZADO

Documento: "proyecto/seo/motor-decision.md"

Versión: "v1.0"

La decisión se obtiene aplicando las reglas del motor vigente en el momento del análisis.

---

15. DECISIÓN ACTUAL

DECISIÓN = INVESTIGAR

---

16. RAZÓN DE LA DECISIÓN

Resumen:

Variable| Estado
Intención| Confirmada
Demanda| Desconocida
Potencial comercial| Probablemente alto
Relevancia territorial| Confirmada
Competencia| Alta
Diferenciación| Insuficiente
Información disponible| Parcial
Riesgo de duplicación| Medio/alto

No se cumplen todavía todas las condiciones mínimas necesarias para:

CREAR

Por tanto, el motor mantiene:

INVESTIGAR

---

17. ARQUITECTURA PROPUESTA

La arquitectura prevista, si posteriormente se aprueba la creación, es:

/fontanero/marbella/

Esta URL es únicamente una propuesta arquitectónica.

No constituye autorización de creación.

La decisión SEO precede siempre a la URL.

---

18. LANDING

Estado actual:

NOT_STARTED

La landing no está autorizada para generación.

---

19. BLOQUES

No se activa todavía el sistema de bloques.

Los bloques solamente se seleccionarán cuando:

decision_seo = CREAR

---

20. IA

NO EJECUTAR

La IA no debe generar la landing mientras la decisión sea:

INVESTIGAR

---

21. N8N

NO EJECUTAR PUBLICACIÓN

N8N podrá utilizar esta oportunidad para investigación o actualización de datos en el futuro, pero no debe crear una landing mientras la decisión no sea "CREAR".

---

22. WORDPRESS

NO CREAR

No debe existir todavía una landing pública para esta oportunidad.

---

23. ACCIONES PENDIENTES

Para poder volver a evaluar OPP-001:

1. Obtener evidencia cuantitativa de demanda.
2. Completar el análisis competitivo.
3. Identificar diferenciación real.
4. Analizar el solapamiento con subservicios.
5. Completar la información local disponible.
6. Ejecutar nuevamente el motor.

---

24. PRÓXIMA EVALUACIÓN

Cuando aparezcan nuevas evidencias:

NUEVAS EVIDENCIAS
↓
ACTUALIZACIÓN DE DATOS
↓
MOTOR
↓
NUEVA DECISIÓN

La decisión anterior no se elimina.

Se conserva en el historial.

---

25. HISTORIAL

2026-08-23 — Decisión inicial

Motor: "v1.0"

Resultado:

INVESTIGAR

Motivo principal:

Demanda cuantitativa desconocida, diferenciación insuficientemente documentada e información local todavía parcial.

Acción:

Continuar investigación.

---

26. REGLA DE ACTUALIZACIÓN

Una decisión modificada debe conservar:

date
previous_decision
new_decision
new_evidence
reason
engine_version

Ejemplo:

{
  "date": "2026-08-24",
  "previous_decision": "INVESTIGAR",
  "new_decision": "CREAR",
  "new_evidence": [],
  "reason": "",
  "engine_version": "v1.1"
}

No se debe modificar una decisión únicamente para obtener el resultado deseado.

---

27. TRAZABILIDAD

Cada decisión debe poder relacionarse con:

opportunity_id
→ evidencias
→ motor
→ arquitectura
→ landing
→ validación
→ publicación

Esto permite reconstruir por qué se creó, agrupó, investigó o descartó una oportunidad.

---

28. REGLA DE NO INVENCIÓN

Este registro no puede utilizar datos no demostrados como hechos.

Cuando un dato sea desconocido:

null

o:

unknown

según el modelo correspondiente.

Una hipótesis de la IA no puede convertirse en evidencia confirmada sin validación.

---

29. ESTADO DEL REGISTRO

Actualmente:

OPP-001
↓
INVESTIGAR
↓
LANDING: NO
IA: NO
N8N: NO PUBLICAR
WORDPRESS: NO

---

30. SIGUIENTE PASO DEL SISTEMA

El siguiente objetivo es aplicar el motor a nuevas oportunidades reales de la investigación.

Cada nueva oportunidad tendrá su propio:

OPP-ID

y seguirá el mismo proceso:

DATOS
↓
EVIDENCIAS
↓
MOTOR
↓
DECISIÓN
↓
ARQUITECTURA
↓
REGISTRO

Solo las oportunidades con:

CREAR

continuarán hacia:

BLOQUES
↓
IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

---

31. VERSIÓN

Registro: "v2.0"

Modelo de datos: "v2.0"

Motor de decisión utilizado por OPP-001: "v1.0"

---

32. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza el registro a la versión "v2.0".

Se consolida la estructura de registro con el modelo de datos común.

Se incorporan:

- identificador estable de oportunidad;
- estados separados;
- trazabilidad;
- versionado;
- historial de decisiones;
- separación entre decisión SEO y estado de landing;
- separación entre decisión SEO y ejecución de IA;
- separación entre decisión SEO y publicación mediante N8N/WordPress;
- clasificación explícita de datos desconocidos;
- conservación de decisiones anteriores.

La decisión OPP-001 permanece actualmente como:

INVESTIGAR

No se autoriza todavía la generación ni publicación de la landing.
