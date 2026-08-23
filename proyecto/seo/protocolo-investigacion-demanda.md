PROTOCOLO DE INVESTIGACIÓN DE DEMANDA

1. FUNCIÓN

Este documento define cómo se debe investigar la demanda de una oportunidad SEO antes de permitir que el motor tome una decisión definitiva.

El objetivo es transformar:

servicio + localidad

en datos de demanda verificables y trazables.

Este documento no decide si una landing debe crearse.

Define cómo obtener la información necesaria para que el motor pueda decidir.

---

2. PRINCIPIO

Nunca se debe inventar:

- volumen de búsquedas;
- tendencia;
- demanda;
- CPC;
- competencia;
- potencial comercial.

Si un dato no está disponible:

DESCONOCIDO

No se sustituye por una estimación presentada como dato real.

---

3. FUENTE PRINCIPAL

La fuente principal para volumen de búsqueda será:

Google Keyword Planner.

Keyword Planner proporciona estimaciones de búsquedas mensuales y permite limitar la investigación por ubicación.

---

4. FUENTES COMPLEMENTARIAS

Podrán utilizarse:

- Google Trends;
- SERP de Google;
- Search Console, cuando exista;
- datos propios del proyecto;
- otras herramientas SEO autorizadas.

Las fuentes complementarias no sustituyen automáticamente al dato principal de Keyword Planner.

---

5. GOOGLE KEYWORD PLANNER

Para cada oportunidad se deberá investigar:

servicio
localidad
provincia
idioma
ubicación
periodo

Ejemplo:

Servicio:
fontanero

Localidad:
Marbella

Provincia:
Málaga

Idioma:
Español

Ubicación:
Marbella / área definida

Periodo:
últimos 12 meses

Google indica que el promedio de búsquedas mensuales se calcula normalmente sobre un periodo de 12 meses, aunque el periodo puede modificarse.

---

6. KEYWORDS PRINCIPALES

La investigación debe comenzar por la combinación principal.

Ejemplo:

fontanero Marbella
fontaneros Marbella
fontanería Marbella
fontanero en Marbella

No todas las variantes tienen que terminar siendo URLs independientes.

Su función inicial es medir y comprender la intención.

---

7. KEYWORDS RELACIONADAS

Keyword Planner debe utilizarse también para descubrir términos relacionados.

Ejemplo:

fontanero urgente Marbella
fontanero 24 horas Marbella
reparación fontanería Marbella
fontanero barato Marbella
empresa fontanería Marbella

También podrán aparecer subservicios:

desatascos Marbella
fontanero fugas Marbella
reparación tuberías Marbella
cambiar termo Marbella

Estas keywords sirven para detectar intenciones.

No implican automáticamente que deba crearse una URL.

---

8. SUBSERVICIOS

Cada subservicio descubierto debe pasar posteriormente por el motor.

Ejemplo:

fontanero
+
desatascos
+
Marbella

puede convertirse en una oportunidad independiente si cumple las condiciones del sistema.

Pero la existencia de búsquedas no significa automáticamente:

CREAR URL

---

9. UBICACIÓN

La investigación debe utilizar la segmentación geográfica más adecuada disponible.

Cuando se evalúe una localidad concreta:

Marbella

no se debe sustituir automáticamente por:

España

porque eso distorsionaría la evaluación territorial.

Keyword Planner permite limitar las ideas por ciudades, regiones y otras ubicaciones.

---

10. IDIOMA

Para el proyecto principal:

Idioma:
Español

La configuración deberá mantenerse constante entre oportunidades comparables.

---

11. PERIODO

Por defecto:

12 meses

Cuando exista estacionalidad relevante se podrá analizar adicionalmente:

últimos 24 meses

o periodos mensuales específicos.

Google permite modificar el intervalo temporal para estudiar tendencias y estacionalidad.

---

12. DATOS A REGISTRAR

Para cada keyword relevante se registrará:

keyword
volumen_mensual
competencia_ads
cpc_bajo
cpc_alto
ubicacion
periodo
fuente
fecha_consulta

Cuando un dato no esté disponible:

null

---

13. EJEMPLO

{
  "keyword": "fontanero Marbella",
  "volumen_mensual": null,
  "competencia_ads": null,
  "cpc_bajo": null,
  "cpc_alto": null,
  "ubicacion": "Marbella",
  "periodo": "12 meses",
  "fuente": "Google Keyword Planner",
  "fecha_consulta": "2026-08-23"
}

El "null" es correcto cuando todavía no se ha realizado la consulta real.

---

14. GOOGLE TRENDS

Google Trends será una fuente secundaria.

Su función será analizar:

- evolución temporal;
- estacionalidad;
- interés relativo;
- comportamiento geográfico;
- comparación entre términos.

Google explica que Trends muestra la popularidad relativa de un término según ubicación y periodo, no un volumen absoluto de búsquedas.

Por tanto:

Google Trends ≠ volumen absoluto

---

15. USO DE TRENDS

Ejemplo:

fontanero Marbella

puede compararse con:

fontaneros Marbella
fontanería Marbella

para detectar qué formulaciones tienen mayor interés relativo.

No se utilizará Trends para afirmar:

"esta keyword tiene 500 búsquedas al mes"

---

16. SERP

La SERP se utilizará para analizar:

- intención;
- competencia;
- tipos de resultados;
- presencia de negocios locales;
- páginas específicas;
- directorios;
- mapas;
- anuncios;
- subservicios;
- formatos de contenido.

---

17. DATOS SERP

Registrar como mínimo:

keyword
fecha
ubicación
tipo_intencion
competidores_relevantes
numero_resultados_relevantes
presencia_paginas_locales
presencia_directorios
presencia_maps
observaciones

---

18. INTENCIÓN

La intención podrá clasificarse como:

LOCAL_COMERCIAL
LOCAL_INFORMATIVA
COMERCIAL
INFORMATIVA
NAVEGACIONAL
MIXTA
DESCONOCIDA

Para una oportunidad destinada a una landing de servicio local interesa principalmente:

LOCAL_COMERCIAL

---

19. COMPETENCIA ORGÁNICA

La existencia de competencia no significa automáticamente que no se pueda crear una landing.

Debe analizarse:

- calidad;
- relevancia;
- autoridad;
- profundidad;
- especialización;
- experiencia local;
- estructura;
- cobertura de intención;
- diferenciación.

---

20. COMPETENCIA PUBLICITARIA

Keyword Planner puede aportar información de competencia publicitaria y pujas.

Estos datos sirven como señales comerciales.

No deben confundirse con dificultad SEO orgánica.

---

21. CPC

Cuando esté disponible se registrará:

cpc_bajo
cpc_alto

El CPC es una señal de valor comercial.

No debe utilizarse por sí solo para aprobar una landing.

---

22. DEMANDA TOTAL DE LA OPORTUNIDAD

La demanda de una oportunidad no debe depender necesariamente de una sola keyword.

Ejemplo:

OPP-001

fontanero Marbella
fontaneros Marbella
fontanería Marbella
fontanero en Marbella

Se analizará el conjunto de términos relacionados.

---

23. AGRUPACIÓN

Las keywords deberán agruparse según intención.

Ejemplo:

GRUPO A
fontanero Marbella
fontaneros Marbella
fontanero en Marbella

Puede representar:

INTENCIÓN GENERAL

Mientras:

GRUPO B
desatascos Marbella
desatascos urgentes Marbella

puede representar:

SUBINTENCIÓN DESATASCOS

---

24. REGLA DE URL

La agrupación de keywords no decide por sí sola la URL.

La URL debe surgir de:

demanda
+
intención
+
arquitectura
+
diferenciación
+
riesgo de duplicación

---

25. CANIBALIZACIÓN

Antes de crear una nueva oportunidad se debe comprobar si ya existe:

- una URL equivalente;
- una URL demasiado próxima;
- una landing que cubra la misma intención;
- una landing de subservicio;
- una página general que pueda absorber la intención.

---

26. DIFERENCIACIÓN

La investigación debe responder:

¿Qué puede ofrecer esta landing que no sea simplemente repetir las páginas existentes?

La diferenciación puede proceder de:

- mejor cobertura de intención;
- estructura superior;
- información local útil;
- agrupación correcta de servicios;
- contenido realmente útil;
- experiencia de usuario;
- cobertura de preguntas;
- arquitectura interna;
- información propia.

No puede proceder de afirmaciones inventadas.

---

27. INFORMACIÓN LOCAL

Debe investigarse qué información local fiable puede incorporarse.

Ejemplos:

- cobertura territorial;
- características del municipio;
- necesidades del mercado;
- zonas servidas;
- contexto del servicio.

Solo se utilizarán datos verificables.

---

28. RESULTADO DE LA INVESTIGACIÓN

Cada oportunidad debe terminar con:

DEMANDA:
CONFIRMADA
DESCONOCIDA

INTENCIÓN:
CONFIRMADA
DUDOSA
NO CONFIRMADA

COMPETENCIA:
BAJA
MEDIA
ALTA
DESCONOCIDA

DIFERENCIACIÓN:
SUFICIENTE
INSUFICIENTE
DESCONOCIDA

SOLAPAMIENTO:
BAJO
MEDIO
ALTO
DESCONOCIDO

---

29. ESTADO DE INVESTIGACIÓN

Valores permitidos:

COMPLETE
PARTIAL
PENDING
ERROR

COMPLETE

Todos los datos necesarios para el motor están disponibles.

PARTIAL

Existen datos, pero falta información importante.

PENDING

Todavía no se ha realizado la investigación.

ERROR

La investigación no pudo completarse correctamente.

---

30. CRITERIO DE COMPLETITUD

Una investigación se considera completa cuando existen datos suficientes para evaluar:

1. intención
2. demanda
3. competencia
4. potencial comercial
5. diferenciación
6. solapamiento
7. relevancia territorial

---

31. NO INVENTAR

Si Google Keyword Planner no proporciona un dato:

null

Si Google Trends no permite una conclusión:

DESCONOCIDO

Si la SERP no permite confirmar una característica:

NO CONFIRMADO

---

32. EVIDENCIAS

Cada dato importante deberá poder rastrearse hasta una fuente.

Debe conservarse:

fuente
URL
fecha
dato
observación

---

33. FECHA DE CADUCIDAD

Los datos de demanda y SERP son temporales.

Por defecto:

revisión:
180 días

Para mercados muy cambiantes:

revisión:
90 días

---

34. ACTUALIZACIÓN

Cuando una oportunidad vuelva a investigarse:

no borrar automáticamente el histórico

Se añadirá una nueva observación.

---

35. HISTÓRICO

Ejemplo:

2026-08-23
volumen: X
competencia: X

2027-02-23
volumen: Y
competencia: Y

Esto permite detectar evolución.

---

36. AUTOMATIZACIÓN FUTURA

N8N podrá automatizar:

1. recibir oportunidad
2. preparar keywords
3. consultar fuentes autorizadas
4. recopilar resultados
5. estructurar datos
6. guardar evidencias
7. enviar datos al motor

La automatización deberá respetar los límites y condiciones de cada fuente.

---

37. IA

La IA podrá ayudar a:

- descubrir variantes;
- agrupar keywords;
- clasificar intención;
- resumir SERP;
- detectar patrones;
- proponer hipótesis.

Pero no podrá convertir una hipótesis en un dato confirmado.

---

38. MOTOR

El motor recibirá la investigación estructurada.

Ejemplo:

demanda = CONFIRMADA
intención = CONFIRMADA
competencia = ALTA
diferenciación = SUFICIENTE
solapamiento = BAJO
relevancia = CONFIRMADA

Entonces podrá evaluar:

CREAR

si todas las reglas correspondientes se cumplen.

---

39. INVESTIGAR

Si falta información crítica:

INVESTIGAR

La oportunidad no pasa a arquitectura de landing.

---

40. NO CREAR

Si los datos demuestran que la oportunidad no cumple los criterios:

NO CREAR

Debe registrarse el motivo.

---

41. REVISAR

Si existen datos contradictorios:

REVISAR

La IA no debe resolver unilateralmente una contradicción estratégica.

---

42. EJEMPLO FONTANERO MARBELLA

Para:

Fontanero
+
Marbella

la investigación debe producir como mínimo:

keywords principales
keywords relacionadas
volumen mensual
tendencia
competencia
CPC cuando esté disponible
SERP
intención
diferenciación
solapamiento
relevancia local

Hasta disponer de estos datos:

OPP-001 = INVESTIGAR

---

43. SALIDA ESTRUCTURADA

La investigación deberá poder convertirse en:

{
  "opportunity_id": "OPP-001",
  "service": "fontanero",
  "location": "Marbella",
  "research_status": "COMPLETE",
  "keywords": [],
  "demand": {},
  "trend": {},
  "serp": {},
  "competition": {},
  "commercial_intent": {},
  "differentiation": {},
  "overlap": {},
  "local_relevance": {},
  "sources": [],
  "observations": []
}

---

44. TRAZABILIDAD

Cada investigación debe conservar:

opportunity_id
fecha
fuentes
datos
version_protocolo

Ejemplo:

opportunity_id = OPP-001
protocol_version = 1.0
date = 2026-08-23

---

45. RELACIÓN CON OTROS DOCUMENTOS

Este protocolo se relaciona con:

proyecto/seo/matriz-servicios-fontaneria.md
proyecto/seo/matriz-localidades.md
proyecto/seo/evidencias-fontaneria.md
proyecto/seo/motor-decision.md
proyecto/seo/registro-decisiones.md
proyecto/seo/arquitectura-urls.md

La investigación alimenta al motor.

El motor produce la decisión.

La decisión habilita o bloquea la arquitectura.

---

46. REGLA DE PRIORIDAD

Este documento no puede contradecir:

metodología general
reglas del motor
arquitectura SEO

Si existe conflicto:

regla superior > protocolo de investigación

---

47. PRINCIPIO FINAL

El sistema debe preferir:

INVESTIGAR

antes que:

INVENTAR

y:

NO CREAR

antes que:

CREAR UNA LANDING SIN JUSTIFICACIÓN

La automatización debe aumentar la velocidad de la metodología sin eliminar su rigor.

---

48. ESTADO

DEFINIDO

Versión:

1.0

Fecha:

2026-08-23
