MATRIZ DE OPORTUNIDADES SEO

Versión: 2.0
Estado: ACTIVO

---

1. FUNCIÓN

Esta matriz identifica y estructura oportunidades SEO potenciales.

Actúa entre:

EVIDENCIAS
↓
MATRIZ DE OPORTUNIDADES
↓
MOTOR DE DECISIÓN

La matriz:

- identifica oportunidades;
- organiza los datos;
- conserva evidencias;
- permite comparar oportunidades;
- prepara la información para el motor.

La matriz no decide por sí misma si debe crearse una landing.

La decisión corresponde al motor de decisión.

---

2. ESTRUCTURA DE OPORTUNIDAD

Cada oportunidad representa una combinación potencial de:

SERVICIO × LOCALIDAD

o:

SERVICIO × SUBSERVICIO × LOCALIDAD

Cada oportunidad debe disponer de un identificador único.

Formato:

OPP-001
OPP-002
OPP-003

Los identificadores no se reutilizan.

---

3. MODELO DE DATOS

Cada oportunidad debe contener, cuando corresponda:

- opportunity_id
- sector
- servicio
- subservicio
- tipo_pagina
- pais
- comunidad_autonoma
- provincia
- municipio
- localidad
- evidencias
- intencion
- demanda
- potencial_comercial
- relevancia_territorial
- competencia
- diferenciacion
- informacion_disponible
- riesgo_duplicacion
- estado_investigacion
- decision_seo
- url_propuesta
- observaciones
- historial

Los nombres y estructuras deben mantenerse alineados con:

"proyecto/seo/esquema-datos.md"

No deben crearse estructuras paralelas incompatibles.

---

4. DATOS DESCONOCIDOS

Los datos desconocidos no se inventan.

Según el tipo de campo se utilizará:

null

o:

UNKNOWN

La ausencia de información no equivale automáticamente a:

0

ni a:

NO

---

5. ESTADOS DE INVESTIGACIÓN

Los estados permitidos son:

DETECTADA
EN_INVESTIGACION
EVIDENCIA_SUFFICIENTE
EVIDENCIA_INSUFFICIENTE
VALIDADA

Estos estados describen el nivel de investigación de la oportunidad.

No deben confundirse con la decisión SEO.

---

6. DECISIONES SEO

Las únicas decisiones oficiales son:

CREAR
AGRUPAR
INVESTIGAR
NO CREAR

Cuando todavía no exista una decisión del motor:

PENDIENTE

La decisión debe proceder del:

"proyecto/seo/motor-decision.md"

---

7. VARIABLES DE EVALUACIÓN

La matriz puede conservar información sobre:

1. Intención.
2. Demanda.
3. Potencial comercial.
4. Relevancia territorial.
5. Competencia.
6. Diferenciación.
7. Información disponible.
8. Riesgo de duplicación.

Estas variables no deben convertirse automáticamente en una puntuación.

Cuando no exista evidencia suficiente:

UNKNOWN

---

8. EVIDENCIAS

Cada oportunidad debe poder relacionarse con las evidencias utilizadas para su análisis.

Las evidencias pueden proceder de:

- investigación SEO;
- SERP;
- fuentes públicas;
- datos territoriales;
- datos comerciales;
- competidores;
- herramientas SEO;
- bases de datos;
- fuentes verificables.

La matriz no necesita duplicar toda la información de las fuentes.

Debe conservar la referencia necesaria para mantener la trazabilidad.

---

9. INTENCIÓN

La matriz puede registrar la intención identificada.

Ejemplos:

LOCAL
LOCAL + COMMERCIAL
TRANSACTIONAL
INFORMATIONAL
EMERGENCY
SERVICE_SPECIFIC

La clasificación debe proceder de la investigación.

No se debe declarar una intención simplemente porque la combinación de palabras parezca lógica.

---

10. DEMANDA

La demanda puede registrarse cuando exista evidencia fiable.

Fuentes posibles:

- volumen de búsqueda;
- tendencias;
- herramientas SEO;
- SERP;
- datos propios;
- señales comerciales.

No se debe inventar volumen de búsqueda.

Si no existe una medición fiable:

demanda = UNKNOWN

---

11. POTENCIAL COMERCIAL

Puede registrarse:

ALTO
MEDIO
BAJO
UNKNOWN

cuando exista evidencia suficiente.

Debe considerar:

- probabilidad de contratación;
- urgencia;
- necesidad;
- valor económico;
- cercanía a la conversión.

---

12. RELEVANCIA TERRITORIAL

Puede registrar información como:

- población;
- actividad económica;
- turismo;
- tipo de vivienda;
- urbanizaciones;
- actividad empresarial;
- características geográficas;
- demanda potencial;
- cobertura real.

La localidad no debe utilizarse únicamente como keyword.

---

13. COMPETENCIA

La competencia se conserva como información descriptiva.

Puede incluir:

- cantidad de competidores relevantes;
- empresas locales;
- calidad de sus páginas;
- especialización;
- autoridad aparente;
- intención satisfecha por la SERP.

No se asignarán puntuaciones arbitrarias.

Si se desarrolla posteriormente una escala cuantitativa, deberá documentarse su metodología.

---

14. DIFERENCIACIÓN

La matriz debe registrar si existe una posible diferenciación real.

Debe responder:

«¿Qué información útil puede ofrecer esta oportunidad que no sea simplemente una copia de otra?»

Puede proceder de:

- necesidades locales;
- características del territorio;
- problemas específicos demostrados;
- particularidades del servicio;
- casos;
- procesos;
- cobertura;
- preguntas frecuentes específicas;
- datos comerciales verificables;
- intención diferenciada.

No se considera diferenciación suficiente:

- cambiar el nombre de la ciudad;
- cambiar sinónimos;
- modificar párrafos;
- cambiar títulos;
- generar texto diferente mediante IA sin datos diferentes.

---

15. RIESGO DE DUPLICACIÓN

Puede registrarse:

LOW
MEDIUM
HIGH
UNKNOWN

Se consideran:

- misma intención;
- mismo servicio;
- misma información;
- misma estructura;
- misma propuesta;
- misma finalidad;
- ausencia de información diferenciadora.

Un riesgo alto puede conducir a:

AGRUPAR

o:

NO CREAR

según el motor.

---

16. REGLA FUNDAMENTAL

La existencia de:

SERVICIO + LOCALIDAD

no implica automáticamente:

CREAR

La matriz únicamente identifica una oportunidad potencial.

El proceso completo es:

DATOS
↓
EVIDENCIAS
↓
OPORTUNIDAD
↓
MOTOR
↓
DECISIÓN

---

17. OPORTUNIDAD OPP-001

Identificación

Opportunity ID:

"OPP-001"

Sector:

Fontanería

Servicio:

Fontanero

Subservicio:

"null"

Tipo de página:

"servicio_localidad"

---

Localización

País:

España

Comunidad autónoma:

Andalucía

Provincia:

Málaga

Municipio:

Marbella

Localidad:

"null"

---

Evaluación actual

Variable| Estado
Intención| HIGH
Demanda| UNKNOWN
Potencial comercial| HIGH
Relevancia territorial| HIGH
Competencia| HIGH
Diferenciación| INSUFFICIENT
Información disponible| MEDIUM
Riesgo de duplicación| MEDIUM/HIGH

---

Estado de investigación

EVIDENCIA_INSUFICIENTE

---

Decisión SEO

INVESTIGAR

---

URL propuesta

/fontanero/marbella/

La URL es únicamente una propuesta.

No constituye autorización de creación.

La arquitectura de URL se aplica después de obtener una decisión:

CREAR

---

Motivo de INVESTIGAR

Existe evidencia de intención local comercial y de actividad profesional en Marbella.

Sin embargo, todavía debe completarse:

- demanda cuantitativa;
- diferenciación real;
- información local propia;
- análisis de solapamiento con subservicios;
- evaluación definitiva del riesgo de duplicación.

Por tanto:

DECISION_SEO = INVESTIGAR

---

Acción

CONTINUAR INVESTIGACIÓN

No se autoriza todavía:

- generación de contenido;
- creación de landing;
- publicación en WordPress.

---

18. PRUEBA TÉCNICA

OPP-001 puede utilizarse posteriormente como caso de prueba técnica del sistema.

Una prueba técnica no modifica:

decision_seo

La generación de una prueba no significa:

CREAR

ni:

PUBLICAR

Si se genera contenido experimental deberá quedar identificado como:

TEST

y permanecer fuera de producción.

---

19. FLUJO DE OPP-001

Actualmente:

INVESTIGACIÓN
↓
EVIDENCIAS
↓
OPP-001
↓
INVESTIGAR

Pendiente:

NUEVA EVIDENCIA
↓
REEVALUACIÓN
↓
CREAR / AGRUPAR / INVESTIGAR / NO CREAR

Si finalmente:

CREAR

entonces:

ARQUITECTURA
↓
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

20. RELACIÓN CON EL MOTOR

El motor utiliza esta matriz como entrada.

Archivo:

"proyecto/seo/motor-decision.md"

La matriz proporciona:

DATOS + EVIDENCIAS

El motor proporciona:

DECISIÓN

---

21. RELACIÓN CON EL REGISTRO

Una vez aplicada la decisión del motor, el resultado debe conservarse en:

"proyecto/seo/registro-decisiones.md"

Flujo:

MATRIZ
↓
MOTOR
↓
REGISTRO

La matriz conserva la oportunidad.

El registro conserva la decisión y su historial.

---

22. RELACIÓN CON ARQUITECTURA

Solo después de:

decision_seo = CREAR

se consolida:

- tipo de página;
- URL;
- canonical;
- parent URL;
- profundidad;
- relaciones con otras páginas.

La matriz puede contener una URL propuesta.

Nunca constituye por sí misma una autorización.

---

23. RELACIÓN CON LANDING

CREAR
→ puede generar landing

AGRUPAR
→ se integra en otra página

INVESTIGAR
→ permanece pendiente

NO CREAR
→ no genera landing

---

24. RELACIÓN CON IA

La IA puede utilizar la oportunidad y sus evidencias para:

- analizar información;
- estructurar datos;
- proponer contenido;
- detectar patrones;
- preparar hipótesis.

Pero la IA no puede transformar una hipótesis en evidencia confirmada.

La decisión SEO siempre procede del sistema de decisión.

---

25. RELACIÓN CON N8N

N8N podrá automatizar posteriormente el flujo:

DATOS
↓
INVESTIGACIÓN
↓
MATRIZ
↓
MOTOR
↓
DECISIÓN
↓
GENERACIÓN
↓
VALIDACIÓN
↓
WORDPRESS

N8N no debe saltarse la decisión del motor.

Una oportunidad con:

INVESTIGAR

o:

NO CREAR

no debe publicarse automáticamente.

---

26. CONTROL DE DUPLICADOS

Antes de crear una nueva oportunidad se comprobará:

- mismo servicio;
- mismo subservicio;
- mismo municipio;
- misma localidad;
- misma intención.

Si ya existe una oportunidad equivalente:

NO CREAR NUEVO OPPORTUNITY_ID

Se utilizará el identificador existente.

---

27. HISTORIAL OPP-001

2026-08-23

Estado inicial:

DETECTADA

Posteriormente evaluada mediante el motor.

Resultado:

INVESTIGAR

Motivos:

- intención local comercial;
- relevancia territorial;
- oferta profesional;
- competencia alta;
- demanda cuantitativa desconocida;
- diferenciación insuficientemente documentada;
- información local parcial;
- riesgo de duplicación medio/alto.

Estado actual:

INVESTIGAR

---

28. ACTUALIZACIÓN DE UNA OPORTUNIDAD

Cuando aparezcan nuevas evidencias:

1. No se elimina la información anterior sin motivo.
2. Se añade la nueva evidencia.
3. Se actualizan las variables afectadas.
4. Se vuelve a ejecutar el motor.
5. Se registra la nueva decisión.
6. Se conserva el historial.

---

29. HISTORIAL DE CAMBIOS DE DECISIÓN

Cuando cambie una decisión deberá conservarse:

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

---

30. REGLA DE NO INVENCIÓN

No se deben inventar:

- demanda;
- competencia;
- empresas;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- cobertura;
- zonas;
- reseñas;
- testimonios;
- experiencia;
- certificaciones;
- garantías;
- datos territoriales.

Cuando no exista evidencia:

UNKNOWN

o:

null

según corresponda.

---

31. ESCALABILIDAD

La estructura puede reutilizarse para:

- fontaneros;
- electricistas;
- abogados;
- carpinteros;
- pintores;
- jardineros;
- reformas;
- otros servicios profesionales.

Ejemplo:

OPP-001
sector = fontaneria

o:

OPP-001
sector = electricidad

La metodología permanece estable.

Los datos y variables específicas pueden cambiar según el sector.

---

32. PRINCIPIO DE CALIDAD

No se crearán oportunidades únicamente mediante:

SERVICIOS × LOCALIDADES

La combinación automática sirve para detectar candidatos.

La evidencia determina cuáles merecen ser evaluados.

El motor determina qué hacer.

---

33. ESTADO DEL DOCUMENTO

Estado:

"ACTIVO"

Versión:

"2.0"

Fecha:

2026-08-24

---

34. CAMBIOS DE LA VERSIÓN 2.0

Se consolida la matriz con el sistema general.

Se incorporan y refuerzan:

- separación entre oportunidad y decisión;
- separación entre decisión y landing;
- separación entre decisión y publicación;
- trazabilidad con evidencias;
- integración con el registro de decisiones;
- estados de investigación;
- estados de demanda desconocida;
- diferenciación;
- riesgo de duplicación;
- control de oportunidades duplicadas;
- relación con IA;
- relación con N8N;
- reutilización sectorial;
- regla de no invención;
- historial de cambios;
- versionado.

---

35. REGLA FINAL

La matriz responde:

¿QUÉ OPORTUNIDADES DEBEMOS EVALUAR?

El motor responde:

¿QUÉ HACEMOS CON CADA OPORTUNIDAD?

El registro responde:

¿QUÉ DECISIÓN TOMAMOS Y POR QUÉ?

La arquitectura responde:

¿QUÉ ESTRUCTURA TENDRÁ?

La IA responde:

¿CÓMO GENERAMOS EL CONTENIDO?

N8N responde:

¿CÓMO AUTOMATIZAMOS EL PROCESO?

WordPress responde:

¿DÓNDE SE PUBLICA?
