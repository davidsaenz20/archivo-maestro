Motor de Decisión del Proyecto

1. Propósito

Este documento define el sistema mediante el cual el proyecto decide si una combinación:

SERVICIO × LOCALIDAD

debe:

- CREAR una página independiente.
- AGRUPAR el servicio con otra página.
- NO CREAR una página.

El motor debe ser reutilizable para cualquier sector.

Fontanería es el primer caso de aplicación.

---

2. Principio fundamental

El motor no debe maximizar el número de páginas.

Debe maximizar la relación entre:

DEMANDA + INTENCIÓN + VALOR COMERCIAL + DIFERENCIACIÓN + UTILIDAD

y

COSTE + RIESGO + REDUNDANCIA + BAJA DEMANDA

Por tanto:

más URLs ≠ mejor proyecto

---

3. Inputs del motor

El motor recibe información procedente de:

- Investigación.
- Matriz de servicios.
- Matriz territorial.
- Datos de búsqueda.
- SERP.
- Competencia.
- Información local.
- Datos comerciales.
- Resultados de pruebas anteriores.

---

4. Unidad de análisis

La unidad básica es:

SERVICIO × LOCALIDAD

Ejemplo:

Desatascos × Marbella

El motor no decide únicamente sobre el servicio ni únicamente sobre la localidad.

Decide sobre la combinación.

---

5. Variables principales

Cada combinación será evaluada mediante las siguientes dimensiones.

5.1 Demanda

Determina si existe suficiente interés potencial.

Puede utilizar:

- Volumen de búsquedas.
- Variantes.
- Tendencias.
- Consultas relacionadas.
- Evidencia SERP.
- Datos propios posteriores.

La ausencia de volumen conocido no significa automáticamente demanda cero.

Debe distinguirse entre:

dato conocido

y

dato desconocido.

---

6. Intención

Determina qué quiere conseguir el usuario.

Clasificaciones posibles:

- Comercial.
- Comercial urgente.
- Problema + solución.
- Instalación.
- Reparación.
- Mantenimiento.
- Informacional.
- Mixta.

La intención debe ser compatible con el objetivo de la página.

---

7. Competencia

Debe analizarse:

- Número de competidores relevantes.
- Calidad de las páginas.
- Autoridad aproximada.
- Especialización.
- Calidad del contenido.
- Presencia local.
- Directorios.
- Empresas reales.
- SERP dominante.

La competencia alta no significa automáticamente:

NO CREAR

Puede existir oportunidad si existe una vía clara de diferenciación.

---

8. Potencial comercial

Debe analizarse:

- Valor del servicio.
- Urgencia.
- Probabilidad de contratación.
- Margen potencial.
- Frecuencia.
- Valor para el profesional.
- Valor de cliente.

Un servicio con pocas búsquedas puede ser interesante si tiene elevado valor comercial.

---

9. Relevancia territorial

Debe analizarse:

- Población.
- Actividad económica.
- Turismo.
- Viviendas.
- Urbanizaciones.
- Empresas.
- Tipo de mercado.
- Distancia/cobertura.
- Demanda local.

No debe utilizarse únicamente la población como criterio.

---

10. Diferenciación

Debe responderse:

¿Podemos crear una página que aporte algo realmente específico para esta combinación?

Posibles elementos:

- Información local.
- Problemas específicos.
- Cobertura.
- Tipos de vivienda.
- Urbanizaciones.
- Empresas.
- Turismo.
- Casuística.
- Servicios relacionados.
- Información práctica.

Si no existe diferenciación suficiente, debe considerarse AGRUPAR o NO CREAR.

---

11. Información disponible

Debe determinarse si existe suficiente información real para crear una página útil.

Se debe distinguir:

Información confirmada

Datos obtenidos de fuentes reales.

Información inferida

Conclusiones razonables basadas en datos.

Información desconocida

Datos que todavía no se han investigado.

Información inventada

Información que no debe utilizarse.

Nunca se debe rellenar una página con datos inventados para justificar su existencia.

---

12. Riesgo de contenido duplicado

Debe analizarse:

- Similitud entre páginas.
- Repetición de estructuras.
- Cambios mínimos entre localidades.
- Canibalización.
- Thin content.
- Páginas prácticamente idénticas.

Si dos páginas responderían esencialmente a la misma intención, debe estudiarse AGRUPAR.

---

13. Puntuación conceptual

El motor puede utilizar una puntuación para ordenar oportunidades.

Las dimensiones principales son:

- Demanda.
- Intención.
- Potencial comercial.
- Relevancia territorial.
- Diferenciación.
- Información disponible.
- Competencia.
- Riesgo de duplicación.

La puntuación debe servir para priorizar, no para sustituir el análisis.

---

14. No utilizar pesos universales sin validación

Los pesos definitivos NO deben considerarse universales.

Los pesos pueden cambiar según:

- Sector.
- Tipo de servicio.
- Modelo comercial.
- Localidad.
- Datos obtenidos.
- Resultados reales.

Por tanto:

motor general ≠ pesos idénticos para todos los sectores

---

15. Decisión CREAR

Una combinación puede clasificarse como:

CREAR

cuando existe evidencia suficiente de que:

- La intención está clara.
- Existe demanda o una oportunidad razonable.
- Existe potencial comercial.
- Existe relevancia territorial.
- Puede generarse contenido útil.
- Existe diferenciación suficiente.
- El riesgo de duplicación es aceptable.
- La página tiene una función clara dentro de la arquitectura.

---

16. Decisión AGRUPAR

Una combinación debe considerar:

AGRUPAR

cuando:

- Existe intención relacionada con otro servicio.
- La demanda independiente es insuficiente.
- La separación produciría contenido pobre.
- La información local no permite suficiente diferenciación.
- Varias búsquedas pueden resolverse mejor desde una página común.
- La agrupación mejora la experiencia del usuario.

Agrupar NO significa ignorar el servicio.

Significa integrarlo dentro de una página más adecuada.

---

17. Decisión NO CREAR

Una combinación puede clasificarse como:

NO CREAR

cuando:

- La demanda es insuficiente y no existe otra oportunidad relevante.
- El potencial comercial es muy bajo.
- No existe intención clara.
- No existe información suficiente.
- No existe diferenciación.
- La página sería redundante.
- Existe elevado riesgo de contenido pobre.
- La combinación no tiene una función clara.

---

18. Datos insuficientes

Si faltan datos importantes:

NO asumir automáticamente NO CREAR.

Debe clasificarse como:

PENDIENTE DE INVESTIGACIÓN

cuando la combinación podría ser relevante.

Esto evita eliminar oportunidades simplemente por falta de información.

---

19. Estados posibles

El motor utilizará conceptualmente estos estados:

PENDIENTE

Todavía no existe información suficiente.

INVESTIGAR

Hace falta obtener datos adicionales.

CREAR

La combinación supera los criterios.

AGRUPAR

Debe integrarse en otra página.

NO CREAR

No existe suficiente justificación.

VALIDAR

La decisión necesita comprobarse mediante una prueba.

VALIDADO

La decisión ha sido comprobada con resultados reales.

---

20. Flujo de decisión

Para cada combinación:

1. Identificar servicio

↓

2. Identificar localidad

↓

3. Determinar intención

↓

4. Analizar demanda

↓

5. Analizar competencia

↓

6. Analizar potencial comercial

↓

7. Analizar relevancia territorial

↓

8. Analizar diferenciación

↓

9. Comprobar información disponible

↓

10. Comprobar riesgo de duplicación

↓

11. Determinar estado

↓

12. CREAR / AGRUPAR / INVESTIGAR / NO CREAR

↓

13. Validar mediante prueba cuando corresponda

---

21. Profundidad de la página

El motor no solo debe decidir:

crear / no crear

También debe determinar la profundidad adecuada.

Posibilidades:

Nivel básico

Una página general de servicio + localidad.

Nivel intermedio

Servicio + localidad con especialidades relacionadas.

Nivel avanzado

Servicio + localidad + especialidades + zonas relevantes.

La profundidad dependerá de la evidencia.

---

22. No crear profundidad artificial

No se deben crear:

- barrios;
- urbanizaciones;
- subservicios;
- urgencias;
- páginas adicionales;

solo para aumentar el número de URLs.

Cada nivel debe tener una razón real.

---

23. Excepciones

El motor debe permitir excepciones justificadas.

Ejemplos:

- Servicio de alto valor con poca demanda aparente.
- Servicio urgente.
- Mercado turístico.
- Localidad con características especiales.
- Sector regulado.
- Servicio con alta estacionalidad.
- Nicho con poca competencia.
- Información comercial excepcional.

Toda excepción debe quedar registrada y explicada.

---

24. Registro de excepciones

Una excepción debe indicar:

- Combinación afectada.
- Regla general que se modifica.
- Motivo.
- Evidencia.
- Decisión.
- Fecha.

Esto permite revisar posteriormente si la excepción debe convertirse en regla general.

---

25. Aplicación a fontanería

Fontanería será la primera aplicación real.

Ejemplo:

Fontanero × Marbella

puede tener:

- Demanda elevada.
- Intención comercial.
- Mercado turístico.
- Alta actividad residencial.
- Competencia.
- Potencial comercial.

El motor evaluará todos los factores antes de decidir.

Otro ejemplo:

Servicio muy específico × municipio pequeño

podría terminar en:

AGRUPAR

aunque el servicio exista realmente.

---

26. Aplicación a abogados

El mismo motor debe poder utilizarse para:

Abogado × localidad

Ejemplos:

- Abogado laboralista × Málaga.
- Abogado de extranjería × Marbella.
- Abogado de divorcios × Madrid.
- Abogado de herencias × Sevilla.

Pero:

NO se deben copiar automáticamente los servicios, pesos ni umbrales de fontanería.

La metodología se mantiene.

Los datos y reglas específicas se adaptan al sector.

---

27. Adaptación por sector

Cada nuevo sector debe definir:

- Sus servicios.
- Sus intenciones.
- Sus tipos de cliente.
- Sus particularidades territoriales.
- Sus riesgos.
- Sus excepciones.
- Sus variables comerciales.

El motor general permanece.

Las reglas específicas pueden añadirse como una capa sectorial.

---

28. Arquitectura de dos capas

El sistema debe evolucionar hacia:

Capa 1 — Motor general

Reglas comunes:

- Investigar.
- Evaluar.
- Comparar.
- Decidir.
- Validar.
- Medir.

Capa 2 — Reglas sectoriales

Características propias de:

- Fontanería.
- Abogados.
- Electricistas.
- Carpinteros.
- Pintores.
- Jardineros.
- Reformas.
- Etc.

Esto permite escalar sin convertir cada nuevo servicio en un proyecto completamente independiente.

---

29. Validación del motor

Antes de automatizar se debe probar el motor manualmente.

Se seleccionará una muestra de combinaciones.

Ejemplo:

- 10 combinaciones claramente buenas.
- 10 combinaciones dudosas.
- 10 combinaciones aparentemente malas.

Se aplicará el motor.

Después se revisará:

- ¿Las decisiones tienen sentido?
- ¿Existen falsos positivos?
- ¿Existen falsos negativos?
- ¿Hay demasiadas páginas?
- ¿Hay demasiadas agrupaciones?
- ¿Faltan variables?

---

30. Aprendizaje

Los resultados de la primera prueba pueden modificar:

- Pesos.
- Umbrales.
- Variables.
- Excepciones.
- Reglas sectoriales.

El motor no debe considerarse inmutable.

Debe evolucionar con evidencia.

---

31. Regla de evidencia

Una decisión importante debe poder responder:

¿Por qué hemos tomado esta decisión?

Por ello el sistema debe conservar:

- Datos utilizados.
- Fuentes.
- Fecha.
- Interpretación.
- Resultado.

Esto permitirá auditar cualquier decisión posteriormente.

---

32. Regla contra la memoria

El motor no debe depender de que ChatGPT recuerde conversaciones anteriores.

Toda regla consolidada debe existir en documentación.

La conversación sirve para trabajar.

Los archivos sirven para conservar.

---

33. Regla contra contradicciones

Si aparece una información nueva que contradice una regla anterior:

1. Detectar la contradicción.
2. Revisar la fecha.
3. Revisar la evidencia.
4. Determinar qué información es más reciente y válida.
5. Actualizar la decisión.
6. Registrar el cambio.
7. Actualizar "maestro.md" cuando afecte al estado general.

Nunca ignorar silenciosamente una contradicción.

---

34. Salida del motor

Cada combinación debería terminar produciendo una estructura equivalente a:

Servicio:
Localidad:
Intención:
Demanda:
Competencia:
Potencial comercial:
Relevancia territorial:
Diferenciación:
Información disponible:
Riesgo de duplicación:
Decisión:
Nivel de página:
Motivo:
Estado:
Fecha:

---

35. Orden de prioridad

Cuando existan muchas combinaciones, el motor debe permitir priorizarlas.

Prioridad alta:

- Alta oportunidad.
- Alta intención.
- Alto potencial comercial.
- Buena diferenciación.
- Información suficiente.

Prioridad media:

- Oportunidad razonable.
- Algunos datos pendientes.

Prioridad baja:

- Poco potencial.
- Alta incertidumbre.
- Baja diferenciación.

---

36. Regla de automatización

El motor debe validarse manualmente antes de automatizarlo.

Primero:

MOTOR MANUAL

↓

PRUEBA

↓

CORRECCIÓN

↓

MOTOR SEMIAUTOMÁTICO

↓

VALIDACIÓN

↓

AUTOMATIZACIÓN

↓

ESCALADO

---

37. Relación con la metodología

La metodología establece:

INVESTIGAR → CONSERVAR → ESTRUCTURAR → DECIDIR → VALIDAR → PROBAR → MEDIR → CORREGIR → AUTOMATIZAR → ESCALAR

El motor ejecuta principalmente la parte:

DECIDIR

pero utiliza información generada por las fases anteriores y devuelve información para las fases posteriores.

---

38. Estado

Motor de decisión:

DEFINIDO — PENDIENTE DE VALIDACIÓN REAL

Metodología:

DEFINIDA

Investigación de fontanería:

CONSOLIDADA

Matriz de servicios:

ESTRUCTURADA

Matriz territorial:

ESTRUCTURADA

Arquitectura:

DEFINIDA CONCEPTUALMENTE

Primera prueba:

PENDIENTE

Automatización:

PENDIENTE

Escalado:

PENDIENTE

---

39. Próximo paso

Una vez guardado este documento:

1. Auditar todos los documentos.
2. Corregir estados desactualizados.
3. Corregir referencias de rutas.
4. Actualizar "maestro.md".
5. Seleccionar la primera muestra real.
6. Aplicar manualmente el motor.
7. Detectar errores.
8. Ajustar el motor.
9. Repetir la prueba.
10. Solo después diseñar la automatización.

---

40. Regla final

El motor no existe para generar páginas.

Existe para tomar decisiones justificadas.

La pregunta fundamental siempre será:

«¿Esta página aporta suficiente valor como para existir de forma independiente?»

Si la respuesta es sí:

CREAR.

Si puede resolverse mejor junto a otra:

AGRUPAR.

Si no existe justificación suficiente:

NO CREAR.

Si todavía no sabemos lo suficiente:

INVESTIGAR.

Nunca inventar datos para forzar una decisión.
