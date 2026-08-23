ESTADOS DEL SISTEMA

1. FUNCIÓN

Este documento define los estados y resultados oficiales utilizados por el sistema.

Su objetivo es evitar que distintos documentos utilicen palabras diferentes para representar la misma situación.

Este documento actúa como referencia común para:

- metodología;
- investigación;
- matrices;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URLs;
- arquitectura de landing;
- sistema de bloques;
- IA;
- N8N;
- validación;
- publicación.

---

2. PRINCIPIO FUNDAMENTAL

Debe distinguirse entre:

1. DECISIÓN SEO
2. ESTADO DEL PROCESO
3. RESULTADO DE VALIDACIÓN
4. INCIDENCIA

No son conceptos equivalentes.

---

3. DECISIÓN SEO

La decisión SEO pertenece exclusivamente al motor de decisión.

Los únicos valores permitidos son:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

No se permite utilizar "REVISAR" como decisión SEO.

---

4. CREAR

Significa que existe suficiente evidencia para justificar una página independiente.

Condiciones generales:

- intención suficientemente clara;
- utilidad independiente;
- información suficiente;
- diferenciación real;
- riesgo de duplicación aceptable;
- coherencia con la arquitectura;
- URL determinable.

Cuando el resultado es:

CREAR

la oportunidad puede continuar hacia la arquitectura de URL y posteriormente hacia la construcción de la landing.

---

5. AGRUPAR

Significa que la intención existe, pero no justifica una página independiente.

La intención puede resolverse dentro de otra página existente.

Ejemplos:

- intención demasiado similar;
- falta de diferenciación;
- contenido que puede integrarse;
- varias combinaciones que representan la misma necesidad.

Resultado:

AGRUPAR

La oportunidad no genera una landing independiente.

Debe registrarse la página de destino o agrupación cuando exista.

---

6. INVESTIGAR

Significa que todavía no existe información suficiente para tomar una decisión fiable.

Ejemplos:

- demanda desconocida;
- intención ambigua;
- información territorial insuficiente;
- evidencias contradictorias;
- diferenciación todavía no demostrada.

Resultado:

INVESTIGAR

La oportunidad queda pendiente de nueva investigación.

No se crea una landing.

---

7. NO CREAR

Significa que existe suficiente información para concluir que la combinación no justifica una página independiente.

Ejemplos:

- intención inexistente o irrelevante;
- duplicación evidente;
- ausencia de utilidad independiente;
- combinación creada únicamente por permutación;
- bajo valor y sin diferenciación.

Resultado:

NO CREAR

No se crea una landing.

---

8. REVISAR NO ES UNA DECISIÓN SEO

"REVISAR" no pertenece al motor.

Es un estado operativo que indica:

«Existe algún problema que requiere intervención humana o una nueva comprobación.»

Puede aparecer después de:

- generación;
- validación;
- comprobación de datos;
- comprobación de URL;
- comprobación de bloques;
- comprobación técnica.

Ejemplo:

decisión_seo = CREAR
estado_landing = REVISAR

Esto significa:

«El motor decidió crear la página, pero posteriormente apareció un problema.»

No significa que el motor haya decidido "REVISAR".

---

9. ESTADO DE OPORTUNIDAD

El estado de oportunidad representa dónde se encuentra una oportunidad dentro del proceso.

Valores:

DETECTADA
INVESTIGADA
EVALUADA
DECIDIDA
CERRADA

---

10. DETECTADA

La oportunidad ha sido identificada pero todavía no ha sido investigada suficientemente.

Ejemplo:

fontanero × Marbella

ha sido detectado como posible combinación.

Todavía no existe una decisión definitiva.

---

11. INVESTIGADA

Existe información suficiente para que pueda evaluarse la oportunidad.

Esto no significa que vaya a crearse.

Puede terminar en:

CREAR
AGRUPAR
NO CREAR

o permanecer en:

INVESTIGAR

si todavía faltan datos.

---

12. EVALUADA

La información ya ha sido analizada mediante los criterios del motor.

Todavía debe registrarse el resultado.

---

13. DECIDIDA

El motor ha producido uno de los cuatro resultados oficiales:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

La decisión debe registrarse.

---

14. CERRADA

La oportunidad ya no requiere ninguna acción dentro del flujo actual.

Puede corresponder a:

AGRUPAR

o:

NO CREAR

o a una oportunidad ya procesada completamente.

---

15. ESTADO DE LANDING

Solo existe para oportunidades cuya decisión sea:

CREAR

Valores:

NO_INICIADA
DATOS_PREPARADOS
ARQUITECTURA_PREPARADA
BLOQUES_SELECCIONADOS
CONTENIDO_GENERADO
VALIDACION_PENDIENTE
VALIDADA
PUBLICADA
RECHAZADA
REVISAR

---

16. NO_INICIADA

La decisión es:

CREAR

pero todavía no se ha iniciado la construcción de la landing.

---

17. DATOS_PREPARADOS

Los datos necesarios para construir la landing han sido preparados.

Debe existir la información mínima definida por el esquema de datos.

---

18. ARQUITECTURA_PREPARADA

Ya están determinados:

- tipo de página;
- URL;
- estructura;
- relación con otras páginas.

---

19. BLOQUES_SELECCIONADOS

Los bloques que compondrán la landing ya han sido determinados.

La IA no debe inventar bloques fuera de esta selección.

---

20. CONTENIDO_GENERADO

La IA ha generado el contenido correspondiente a los bloques seleccionados.

Todavía no significa que el contenido sea válido.

---

21. VALIDACION_PENDIENTE

La landing está generada pero todavía no ha superado la validación.

---

22. VALIDADA

La landing ha superado los controles establecidos.

Puede pasar al proceso de publicación si no existe ningún bloqueo técnico.

---

23. PUBLICADA

La landing ha sido publicada correctamente.

Debe conservarse:

- URL;
- fecha;
- versión;
- identificador;
- resultado de validación.

---

24. RECHAZADA

La landing no puede publicarse en su estado actual.

Debe existir una explicación registrada.

---

25. REVISAR

La landing necesita intervención.

Ejemplos:

- dato contradictorio;
- URL incorrecta;
- bloque sin datos;
- contenido problemático;
- error de validación;
- problema técnico.

"REVISAR" no cambia automáticamente la decisión SEO original.

---

26. RESULTADO DE VALIDACIÓN

La validación utiliza sus propios resultados.

Valores:

APROBADA
RECHAZADA
REVISAR

---

27. APROBADA

Todos los controles obligatorios han sido superados.

---

28. RECHAZADA

Existe un problema que impide considerar válida la landing.

---

29. REVISAR

Existe un problema que requiere comprobación o intervención antes de aprobar.

---

30. INCIDENCIA

Una incidencia describe un problema concreto.

Ejemplo:

codigo = DATA001
elemento = telefono
gravedad = alta
estado = abierta

---

31. ESTADO DE INCIDENCIA

Valores:

ABIERTA
EN_REVISION
RESUELTA
DESCARTADA

---

32. RELACIÓN ENTRE DECISIÓN Y LANDING

La relación válida es:

CREAR
↓
NO_INICIADA
↓
DATOS_PREPARADOS
↓
ARQUITECTURA_PREPARADA
↓
BLOQUES_SELECCIONADOS
↓
CONTENIDO_GENERADO
↓
VALIDACION_PENDIENTE
↓
VALIDADA
↓
PUBLICADA

---

33. CAMINO DE ERROR

En cualquier fase posterior pueden aparecer:

REVISAR

o:

RECHAZADA

La oportunidad no debe volver automáticamente al motor.

Solo vuelve al motor si el problema afecta a la decisión SEO original.

---

34. EJEMPLO

Supongamos:

servicio = fontanero
subservicio = desatascos
municipio = Marbella

El motor determina:

decision_seo = CREAR

Entonces:

estado_oportunidad = DECIDIDA

Después:

estado_landing = DATOS_PREPARADOS

Después:

estado_landing = ARQUITECTURA_PREPARADA

Después:

estado_landing = BLOQUES_SELECCIONADOS

Después:

estado_landing = CONTENIDO_GENERADO

Durante la validación se detecta que falta un dato necesario.

Entonces:

estado_landing = REVISAR

La decisión SEO continúa siendo:

CREAR

No se cambia a:

REVISAR

porque "REVISAR" no es una decisión SEO.

---

35. EJEMPLO DE INVESTIGACIÓN

Si el motor determina:

decision_seo = INVESTIGAR

no existe todavía:

estado_landing

porque todavía no debe construirse una landing.

El flujo será:

INVESTIGAR
↓
nueva investigación
↓
reevaluación
↓
CREAR / AGRUPAR / NO CREAR

---

36. EJEMPLO DE AGRUPACIÓN

Si el motor determina:

decision_seo = AGRUPAR

no se genera una landing independiente.

Debe registrarse:

pagina_destino
motivo_agrupacion

cuando estén disponibles.

---

37. EJEMPLO DE NO CREAR

Si:

decision_seo = NO CREAR

la oportunidad queda cerrada para esa combinación.

No se genera:

- URL;
- landing;
- contenido;
- publicación.

---

38. REGLA DE URL

La URL solo se genera después de:

decision_seo = CREAR

Por tanto:

NO CREAR → no URL
AGRUPAR → no URL independiente
INVESTIGAR → no URL definitiva
CREAR → determinar URL

---

39. REGLA DE ARQUITECTURA

La arquitectura de URL nunca determina por sí misma la decisión SEO.

El orden es:

INVESTIGACIÓN
↓
MOTOR
↓
DECISIÓN
↓
ARQUITECTURA
↓
URL

---

40. REGLA DE IA

La IA recibe la decisión ya tomada.

No puede cambiar:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

durante la generación.

Si detecta un problema:

REVISAR

como estado operativo o incidencia.

---

41. REGLA DE N8N

N8N debe utilizar los estados para decidir qué nodo ejecutar.

Ejemplo:

decision_seo = CREAR

→ continuar construcción.

decision_seo = AGRUPAR

→ registrar agrupación.

decision_seo = INVESTIGAR

→ enviar a investigación.

decision_seo = NO CREAR

→ cerrar.

---

42. REGLA DE VALIDACIÓN

La validación nunca modifica directamente la decisión SEO.

Si detecta un problema de contenido:

decision_seo = CREAR
estado_landing = REVISAR

Si detecta que la oportunidad realmente fue mal evaluada:

volver a evaluación del motor

y se registra el cambio.

---

43. TRAZABILIDAD

Cada oportunidad debe conservar como mínimo:

opportunity_id
decision_seo
version_motor
estado_oportunidad
estado_landing
resultado_validacion
incidencias

---

44. REGLA DE VERSIONADO

Cada decisión debe registrar la versión del motor que la produjo.

Ejemplo:

decision_seo = CREAR
version_motor = 1.0

Si el motor cambia a "1.1", las nuevas decisiones utilizarán:

version_motor = 1.1

No se debe sobrescribir históricamente una decisión anterior sin dejar trazabilidad.

---

45. TABLA DE REFERENCIA

Concepto| Valores
Decisión SEO| CREAR / AGRUPAR / INVESTIGAR / NO CREAR
Estado oportunidad| DETECTADA / INVESTIGADA / EVALUADA / DECIDIDA / CERRADA
Estado landing| NO_INICIADA / DATOS_PREPARADOS / ARQUITECTURA_PREPARADA / BLOQUES_SELECCIONADOS / CONTENIDO_GENERADO / VALIDACION_PENDIENTE / VALIDADA / PUBLICADA / RECHAZADA / REVISAR
Validación| APROBADA / RECHAZADA / REVISAR
Incidencia| ABIERTA / EN_REVISION / RESUELTA / DESCARTADA

---

46. REGLA DE ORO

Nunca utilizar una misma palabra para representar conceptos diferentes.

Especialmente:

REVISAR ≠ decisión SEO

y:

INVESTIGAR ≠ REVISAR

"INVESTIGAR" significa que faltan evidencias para decidir.

"REVISAR" significa que existe un problema en una fase ya iniciada.

---

47. ESTADO DEL DOCUMENTO

DEFINIDO

Este documento establece el vocabulario oficial de estados del sistema.

Debe utilizarse como referencia para alinear los documentos que ya existen.

Siguiente trabajo:

1. corregir "esquema-datos.md";
2. corregir "especificacion-ia.md";
3. comprobar "registro-decisiones.md";
4. comprobar "modelo-datos";
5. después continuar con el prompt operativo de IA/N8N.

No se deben crear nuevas arquitecturas hasta terminar esta consolidación.
