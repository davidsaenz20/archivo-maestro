ARQUITECTURA DE URLs

Versión: 2.0
Estado: ACTIVO
Función: transformar una oportunidad SEO validada en una URL única, coherente y automatizable.

---

1. FUNCIÓN

Este documento define cómo se transforma una oportunidad SEO validada por el motor de decisión en una URL concreta.

La URL debe ser:

- coherente;
- predecible;
- estable;
- escalable;
- reutilizable;
- comprensible;
- compatible con la automatización;
- independiente de decisiones arbitrarias de la IA.

La IA no decide libremente la estructura de las URLs.

---

2. PRINCIPIO FUNDAMENTAL

La URL representa una página que el sistema ha decidido crear.

Flujo:

EVIDENCIA
↓
OPORTUNIDAD
↓
DECISIÓN SEO
↓
URL
↓
LANDING
↓
CONTENIDO
↓
VALIDACIÓN
↓
PUBLICACIÓN

La existencia de una combinación de palabras clave no implica que deba existir una URL.

---

3. UNIDAD PRINCIPAL

La estructura inicial es:

"SERVICIO × LOCALIDAD"

Ejemplo:

"/fontanero/marbella/"

Cuando existe un subservicio con intención independiente y suficiente diferenciación:

"SERVICIO × SUBSERVICIO × LOCALIDAD"

Ejemplo:

"/fontanero/desatascos/marbella/"

---

4. ESTRUCTURA PRINCIPAL

Nivel 1

Formato:

"/{servicio}/{localidad}/"

Ejemplos:

"/fontanero/marbella/"

"/electricista/marbella/"

"/abogado/marbella/"

Nivel 2

Formato:

"/{servicio}/{subservicio}/{localidad}/"

Ejemplos:

"/fontanero/desatascos/marbella/"

"/fontanero/fugas-de-agua/marbella/"

"/abogado/divorcios/marbella/"

---

5. REGLA DE CREACIÓN

Una URL solo puede crearse cuando la oportunidad tenga una decisión:

"CREAR"

Las decisiones posibles son:

- "CREAR"
- "AGRUPAR"
- "INVESTIGAR"
- "NO_CREAR"

"AGRUPAR" significa que la intención se integra en otra página.

"INVESTIGAR" significa que falta información para decidir.

"NO_CREAR" significa que no existe suficiente justificación.

---

6. SERVICIO PRINCIPAL

El primer segmento representa el servicio principal.

Ejemplo:

"/fontanero/marbella/"

El servicio debe corresponder con la intención principal.

No se utilizarán servicios inventados ni combinaciones semánticamente incoherentes.

---

7. SUBSERVICIO

Un subservicio solo se incorpora cuando:

- tiene intención propia;
- está definido en el modelo;
- existe oportunidad suficiente;
- puede diferenciarse;
- aporta utilidad;
- no duplica otra página.

No debe utilizarse únicamente para añadir keywords.

---

8. AGRUPACIÓN

Si un subservicio no merece página independiente, se integra en una página superior.

Ejemplo:

Si "reparación de grifos + Marbella" no justifica una página propia:

"/fontanero/marbella/"

puede contener información sobre reparación de grifos.

No se crea:

"/fontanero/reparacion-de-grifos/marbella/"

salvo que la decisión SEO determine que merece una página independiente.

---

9. PROFUNDIDAD

La arquitectura inicial queda limitada a:

Nivel 1

"/servicio/localidad/"

Nivel 2

"/servicio/subservicio/localidad/"

No se añaden automáticamente niveles adicionales.

Ejemplo que no se genera por defecto:

"/fontanero/desatascos/urgente/marbella/"

Una estructura más profunda requeriría una decisión y validación específica.

---

10. LOCALIDAD

Cuando exista intención local, la localidad ocupa el último segmento.

Ejemplos:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

La localidad debe proceder de datos territoriales válidos.

No se crean localidades artificiales.

---

11. SLUGS

Los slugs deben ser:

- descriptivos;
- cortos;
- legibles;
- estables;
- en minúsculas;
- separados por guiones.

Ejemplos:

"fontanero"

"desatascos"

"fugas-de-agua"

"marbella"

No utilizar:

- espacios;
- cadenas artificiales;
- números sin significado;
- caracteres innecesarios.

---

12. INTENCIÓN

Cada URL debe corresponder a una intención identificable.

Ejemplo:

"/fontanero/marbella/"

Intención:

contratar un fontanero en Marbella.

Ejemplo:

"/fontanero/desatascos/marbella/"

Intención:

contratar un servicio de desatascos en Marbella.

La URL no debe representar únicamente una combinación de keywords.

---

13. CANONICAL

Cada página indexable debe tener una única URL canónica.

No deben existir múltiples URLs equivalentes para una misma intención.

La canonical debe corresponder con la URL oficial de la página.

---

14. DUPLICACIÓN

Antes de crear una URL se debe comprobar:

- si ya existe una página equivalente;
- si existe otra URL para la misma intención;
- si existe una página superior que resuelve correctamente la intención;
- si el contenido se solaparía;
- si la nueva página tendría diferenciación real.

Cuando exista solapamiento importante:

"AGRUPAR"

debe considerarse antes de crear una URL adicional.

---

15. URGENCIA

Términos como:

- urgente;
- 24 horas;
- emergencia;

no generan automáticamente nuevos niveles de URL.

El motor debe determinar si existe una intención suficientemente diferenciada.

Puede decidir:

- crear una página;
- agrupar;
- investigar;
- no crear.

---

16. VARIANTES LINGÜÍSTICAS

Sinónimos o variantes no generan automáticamente URLs diferentes.

Ejemplo:

"fontanero"

y

"fontanería"

deben analizarse según su intención real.

No se crean páginas únicamente porque existan dos términos diferentes.

---

17. MARCAS Y MODELOS

Las marcas y modelos no generan automáticamente niveles adicionales.

Ejemplo:

"/fontanero/termo/cointra/marbella/"

no debe crearse por defecto.

Para justificar una URL de este tipo deben existir:

- intención propia;
- demanda suficiente;
- utilidad;
- contenido diferenciado;
- oportunidad;
- ausencia de duplicación.

---

18. COHERENCIA SEMÁNTICA

La jerarquía debe tener sentido.

Ejemplo válido:

"/fontanero/desatascos/marbella/"

si "desatascos" está definido como subservicio de fontanería.

No se deben crear combinaciones semánticamente incoherentes aunque tengan potencial de búsqueda.

---

19. LOCALIDADES PEQUEÑAS

Una localidad pequeña no genera automáticamente una URL.

Debe pasar por los mismos criterios de decisión que cualquier otra localidad.

El resultado puede ser:

"CREAR"

"AGRUPAR"

"INVESTIGAR"

"NO_CREAR"

---

20. RELACIÓN CON EL MOTOR

El motor determina:

1. si existe oportunidad;
2. si merece una página;
3. si debe agruparse;
4. si necesita investigación;
5. si debe descartarse;
6. si el subservicio merece independencia.

La arquitectura de URLs transforma esa decisión en una estructura URL.

---

21. RELACIÓN CON LANDING

La separación es:

MOTOR SEO

decide qué debe existir.

↓

ARQUITECTURA URL

determina dónde existe.

↓

ARQUITECTURA LANDING

determina cómo se estructura.

↓

IA

genera el contenido autorizado.

---

22. URL COMO DATO

La URL debe formar parte del registro estructurado de la oportunidad.

Ejemplo:

opportunity_id: FON-DES-MARB
servicio: fontanero
subservicio: desatascos
localidad: Marbella
decision_seo: CREAR
url: /fontanero/desatascos/marbella/

La URL no debe construirse improvisadamente durante la generación de contenido.

---

23. RESPONSABILIDAD DE N8N

N8N puede utilizar la URL ya validada para:

- generar la página;
- enviar datos al CMS;
- crear enlaces;
- publicar;
- registrar resultados.

N8N no debe inventar URLs fuera de las reglas establecidas.

---

24. RESPONSABILIDAD DE LA IA

La IA recibe una URL previamente determinada.

Puede generar contenido para:

"/fontanero/desatascos/marbella/"

pero no puede decidir:

- crear la URL;
- modificar el slug;
- cambiar la localidad;
- añadir niveles;
- crear otra URL;
- modificar la arquitectura.

---

25. REUTILIZACIÓN

La estructura general puede reutilizarse:

Abogados

"/abogado/marbella/"

"/abogado/divorcios/marbella/"

Electricistas

"/electricista/marbella/"

"/electricista/boletin-electrico/marbella/"

Reformas

"/reformas/marbella/"

"/reformas/cocinas/marbella/"

Cada sector debe validar sus propias relaciones entre servicios y subservicios.

---

26. CONTROL CONTRA ESCALA INDISCRIMINADA

El sistema no debe utilizar la arquitectura para generar grandes cantidades de páginas casi idénticas.

Cada URL debe tener:

- intención;
- utilidad;
- datos;
- diferenciación;
- justificación.

El número de URLs no es un objetivo.

---

27. VALIDACIÓN PREVIA

Antes de aceptar una URL se debe comprobar:

- servicio válido;
- subservicio válido cuando exista;
- localidad válida;
- decisión "CREAR";
- intención identificable;
- ausencia de URL equivalente;
- ausencia de duplicación;
- estructura correcta;
- slug correcto;
- canonical definida.

Si falla una condición crítica:

"REVISAR"

o

"NO_CREAR"

según corresponda.

---

28. FLUJO DEFINITIVO

INVESTIGACIÓN
↓
MATRICES
↓
MOTOR DE DECISIÓN
↓
CREAR
↓
ARQUITECTURA URL
↓
LANDING
↓
DATOS
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

29. REGLA DE NO IMPROVISACIÓN

La URL debe existir antes de solicitar a la IA la generación de la landing.

Esto garantiza:

- consistencia;
- trazabilidad;
- control;
- automatización;
- escalabilidad.

Nunca:

KEYWORD
↓
IA
↓
URL improvisada

---

30. FUENTES DE AUTORIDAD

Este documento define la arquitectura de URLs.

No define:

- estado del proyecto;
- modelo completo de datos;
- bloques de landing;
- contenido;
- implementación WordPress;
- automatización completa.

Esas funciones pertenecen a sus documentos específicos.

No deben existir estructuras paralelas de URLs.

---

31. ESCALABILIDAD

La arquitectura debe permitir:

"1"

↓

"10"

↓

"100"

↓

"1.000"

↓

"ESCALA MAYOR"

sin perder:

- calidad;
- utilidad;
- diferenciación;
- trazabilidad;
- control.

La automatización debe ampliar un sistema validado, no sustituir la validación.

---

32. PRUEBAS

Antes de considerar la arquitectura completamente validada se deben probar casos reales como:

- Fontanero × Marbella.
- Desatascos × Marbella.
- Reparación de fugas × Marbella.
- Fontanero urgente × Marbella.
- Fontanero × localidad pequeña.

Debe comprobarse:

- decisión;
- intención;
- URL;
- diferenciación;
- duplicación;
- utilidad;
- escalabilidad.

Los resultados de estas pruebas pueden provocar modificaciones posteriores de esta arquitectura.

---

33. CONTROL DE VERSIONES

Versión: 2.0

Fecha: 2026-08-24

Motivo: consolidación posterior a la auditoría documental.

Cambios principales:

- separación entre decisión SEO y construcción de URL;
- alineación con "arquitectura-seo.md";
- alineación con "arquitectura-landing.md";
- refuerzo del motor como autoridad de decisión;
- refuerzo de la URL como dato estructurado;
- eliminación de decisiones de URL por parte de la IA;
- refuerzo de canonical y control de duplicación;
- preparación para N8N → WordPress;
- eliminación de estructuras paralelas.

---

FIN DE ARQUITECTURA DE URLs
