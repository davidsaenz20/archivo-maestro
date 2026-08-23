ARQUITECTURA DE URLs

1. Función del documento

Este documento define cómo se transforma una oportunidad SEO validada por el motor de decisión en una URL concreta.

La arquitectura de URLs debe ser:

- coherente;
- predecible;
- escalable;
- reutilizable;
- comprensible para usuarios y buscadores;
- compatible con la automatización mediante N8N;
- independiente de decisiones arbitrarias de la IA.

La IA no decide libremente la estructura de las URLs.

La estructura se determina mediante las reglas definidas en este documento.

---

2. Principio fundamental

La URL representa la combinación que el motor ha decidido convertir en una página.

La unidad principal es:

SERVICIO × LOCALIDAD

Cuando existe un subservicio suficientemente diferenciado, puede utilizarse:

SERVICIO × SUBSERVICIO × LOCALIDAD

---

3. Estructura principal

Nivel 1 — Servicio + localidad

Formato:

"/{servicio}/{localidad}/"

Ejemplos:

"/fontanero/marbella/"

"/electricista/marbella/"

"/abogado/marbella/"

---

4. Nivel 2 — Servicio + subservicio + localidad

Cuando existe un subservicio con intención propia y suficiente diferenciación:

"/{servicio}/{subservicio}/{localidad}/"

Ejemplos:

"/fontanero/desatascos/marbella/"

"/fontanero/fugas-de-agua/marbella/"

"/abogado/divorcios/marbella/"

"/abogado/derecho-laboral/marbella/"

---

5. Regla de no generación automática

La existencia de:

- un servicio;
- un subservicio;
- una localidad;

no implica automáticamente que deba existir una URL.

La combinación debe pasar previamente por el motor de decisión.

El resultado debe ser:

- CREAR;
- AGRUPAR;
- INVESTIGAR;
- NO CREAR.

Solo una oportunidad que termine justificadamente en:

CREAR

puede convertirse en candidata a URL.

---

6. Regla de servicio principal

El primer nivel de la URL representa el servicio principal.

Ejemplo:

"/fontanero/marbella/"

El servicio principal debe corresponder con la intención principal de la página.

---

7. Regla de subservicio

El subservicio se incorpora a la URL únicamente cuando representa una intención suficientemente diferenciada.

Ejemplo:

"/fontanero/desatascos/marbella/"

puede utilizarse si “desatascos” constituye una oportunidad independiente.

No debe utilizarse simplemente para añadir palabras clave.

---

8. Regla de agrupación

Si un subservicio no justifica una página independiente, no se crea una URL específica.

Ejemplo:

Si el motor determina que:

"Fontanero + Marbella"

debe ser una única página y que “reparación de grifos” no tiene suficiente entidad independiente, entonces:

"/fontanero/marbella/"

puede contener información sobre reparación de grifos.

No se crea:

"/fontanero/reparacion-de-grifos/marbella/"

salvo que el motor determine que merece una página propia.

---

9. Regla de profundidad

La arquitectura debe evitar niveles innecesarios.

Como regla general:

Nivel 1

"/servicio/localidad/"

Nivel 2

"/servicio/subservicio/localidad/"

No se deben añadir niveles adicionales automáticamente.

Ejemplo que NO debe generarse por defecto:

"/fontanero/desatascos/urgente/marbella/"

Solo podría existir una estructura más profunda si una futura validación demuestra que es necesaria y aporta valor real.

---

10. La IA no decide la URL

La IA no debe inventar la estructura de URL.

El sistema debe proporcionarle una URL ya determinada.

Ejemplo:

SERVICIO = fontanero
SUBSERVICIO = desatascos
LOCALIDAD = Marbella
DECISIÓN = CREAR
URL = /fontanero/desatascos/marbella/

La IA genera el contenido correspondiente a esa URL.

No decide:

- qué niveles tiene;
- qué slug utilizar;
- si debe existir una página;
- si debe crear una nueva combinación.

---

11. Responsabilidad del motor

El motor decide:

1. Si existe oportunidad.
2. Si debe crearse página.
3. Si debe agruparse.
4. Si necesita más investigación.
5. Si debe descartarse.
6. Si la intención justifica un subservicio independiente.

La arquitectura de URLs transforma esa decisión en una estructura URL.

---

12. Responsabilidad de la capa de contenido

Una vez definida la URL, la arquitectura de landing determina:

- bloques;
- información;
- variables;
- contenido;
- elementos SEO;
- CTA.

Por tanto:

MOTOR

↓

URL

↓

LANDING

↓

CONTENIDO

---

13. Slugs

Los slugs deben ser:

- descriptivos;
- cortos;
- legibles;
- estables;
- en minúsculas;
- separados mediante guiones.

Ejemplos:

"fontanero"

"desatascos"

"fugas-de-agua"

"marbella"

No se utilizarán:

- espacios;
- caracteres innecesarios;
- cadenas artificiales;
- números sin significado.

---

14. Regla de localidad

La localidad debe aparecer como último segmento de la URL cuando la página tenga intención local.

Ejemplo:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

Esto permite mantener una estructura coherente:

servicio → especialización → territorio

---

15. Canonical

Cada página indexable debe tener una URL canónica única.

No deben existir múltiples URLs equivalentes para la misma intención.

Ejemplo:

Si la página oficial es:

"/fontanero/desatascos/marbella/"

no debe existir otra URL equivalente que compita por la misma intención.

---

16. Evitar duplicaciones

Antes de crear una URL debe comprobarse:

- si ya existe una página para esa intención;
- si existe una URL equivalente;
- si el contenido se solaparía;
- si existe una página superior que resuelve correctamente la intención.

Si existe solapamiento importante, debe estudiarse:

AGRUPAR

en lugar de crear otra URL.

---

17. Relación entre URL y intención

Cada URL debe corresponder a una intención identificable.

Ejemplo:

"/fontanero/marbella/"

Intención principal:

contratar un fontanero en Marbella

Ejemplo:

"/fontanero/desatascos/marbella/"

Intención principal:

contratar un servicio de desatascos en Marbella

La URL no debe representar simplemente una combinación de palabras clave.

---

18. Regla de coherencia semántica

La jerarquía debe tener sentido.

Ejemplo:

"/fontanero/desatascos/marbella/"

es coherente si “desatascos” está definido como subservicio dentro del modelo de fontanería.

Pero una combinación que no tenga relación semántica no debe crearse simplemente porque tenga búsquedas.

---

19. Relación con localidades

La arquitectura territorial se basa inicialmente en:

SERVICIO + LOCALIDAD

o:

SERVICIO + SUBSERVICIO + LOCALIDAD

La localidad utilizada debe proceder de la matriz territorial y estar correctamente identificada.

No se crearán URLs para localidades inventadas o variantes artificiales.

---

20. Localidades pequeñas

Una localidad pequeña no debe generar automáticamente una URL.

Debe superar los criterios del motor.

Si no existe suficiente oportunidad:

NO CREAR

o:

AGRUPAR

según corresponda.

---

21. Urgencia

Términos como:

- urgente;
- 24 horas;
- emergencia;

no generan automáticamente un nuevo nivel de URL.

Ejemplo:

No debe crearse automáticamente:

"/fontanero/urgente/marbella/"

El motor debe comprobar primero si existe una intención suficientemente diferenciada.

Puede terminar:

- creando una URL independiente;
- integrando la urgencia dentro de "/fontanero/marbella/";
- agrupándola;
- investigándola.

---

22. Variantes lingüísticas

Sinónimos o variantes no deben generar automáticamente URLs diferentes.

Ejemplo:

“fontanero” y “fontanería” pueden tener relaciones semánticas diferentes, pero no deben generar dos páginas únicamente porque existan dos palabras.

Debe analizarse la intención real.

---

23. Marcas y modelos

Las marcas o modelos no generan automáticamente niveles adicionales de URL.

Ejemplo:

No se debe crear automáticamente:

"/fontanero/termo/cointra/marbella/"

La creación de una URL de este tipo requeriría:

- intención propia;
- demanda suficiente;
- contenido diferenciado;
- utilidad;
- oportunidad comercial;
- ausencia de duplicación.

---

24. URL y plantilla

La URL determina la identidad de la página.

La plantilla determina su estructura.

Ejemplo:

URL:
 /fontanero/desatascos/marbella/

DATOS:
 servicio = fontanero
 subservicio = desatascos
 localidad = Marbella

PLANTILLA:
 hero
 servicio
 problema
 información local
 cobertura
 proceso
 FAQ
 CTA

La plantilla no debe modificar la URL.

---

25. URL como dato estructurado

La URL debe formar parte de los datos de entrada del sistema.

Ejemplo:

id = FON-DES-MARB
servicio = fontanero
subservicio = desatascos
localidad = Marbella
decisión = CREAR
url = /fontanero/desatascos/marbella/

N8N utilizará posteriormente este dato para construir/publicar la página.

---

26. Reutilización entre sectores

La estructura general:

"/{servicio}/{localidad}/"

y:

"/{servicio}/{subservicio}/{localidad}/"

puede reutilizarse en otros sectores.

Ejemplos:

Abogados

"/abogado/marbella/"

"/abogado/divorcios/marbella/"

Electricistas

"/electricista/marbella/"

"/electricista/boletin-electrico/marbella/"

Reformas

"/reformas/marbella/"

"/reformas/cocinas/marbella/"

Sin embargo, cada sector debe validar sus propias relaciones entre servicio y subservicio.

---

27. Regla contra el contenido escalado sin valor

La arquitectura de URLs no debe utilizarse para generar grandes cantidades de páginas casi idénticas.

Cada URL creada debe tener una razón funcional y SEO.

Debe existir capacidad para aportar:

- información específica;
- utilidad;
- diferenciación;
- intención clara.

El número de URLs no es un objetivo.

---

28. Flujo definitivo

El proceso será:

INVESTIGACIÓN

↓

MATRICES

↓

MOTOR DE DECISIÓN

↓

DECISIÓN CREAR

↓

ARQUITECTURA DE URL

↓

SELECCIÓN DE PLANTILLA

↓

SELECCIÓN DE BLOQUES

↓

DATOS DE CONTENIDO

↓

IA

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS

↓

PUBLICACIÓN

---

29. Regla de no improvisación

Una URL no debe ser inventada durante la generación de contenido.

La URL debe existir antes de solicitar a la IA la generación de la landing.

Esto garantiza:

- consistencia;
- control;
- trazabilidad;
- escalabilidad;
- automatización.

---

30. Estado actual

La estructura base queda definida como:

SERVICIO + LOCALIDAD

y:

SERVICIO + SUBSERVICIO + LOCALIDAD

La decisión de utilizar una estructura u otra dependerá del resultado del motor de decisión y de las reglas de diferenciación.

La IA no tiene libertad para modificar esta arquitectura.

---

31. Pendiente de validación

Antes de considerar esta arquitectura definitiva se deben probar combinaciones reales de fontanería.

Ejemplos:

- Fontanero × Marbella.
- Desatascos × Marbella.
- Reparación de fugas × Marbella.
- Fontanero urgente × Marbella.
- Fontanero × localidad pequeña.

Se comprobará:

- decisión del motor;
- intención;
- estructura URL;
- riesgo de duplicación;
- utilidad de la landing;
- escalabilidad.

Los resultados de estas pruebas podrán modificar esta arquitectura.

---

32. Registro de actualización

2026-08-23

Se crea la primera versión de la arquitectura de URLs.

Se establece como estructura base:

"/{servicio}/{localidad}/"

y:

"/{servicio}/{subservicio}/{localidad}/"

Se establece que:

- El motor decide si existe una oportunidad.
- La arquitectura determina la URL.
- La IA no decide libremente la estructura.
- Los subservicios no generan automáticamente URLs.
- La profundidad debe mantenerse limitada.
- La localidad ocupa inicialmente el último segmento.
- Cada URL debe representar una intención identificable.
- Debe evitarse la duplicación.
- La arquitectura queda pendiente de validación con casos reales.
