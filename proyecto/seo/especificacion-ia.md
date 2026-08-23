ESPECIFICACIÓN DE IA

1. FUNCIÓN

La inteligencia artificial es el motor de generación de contenido del sistema.

Su función es transformar una oportunidad SEO previamente definida en una salida estructurada que pueda ser procesada automáticamente por N8N.

La IA:

- no decide la estrategia SEO;
- no decide qué URLs deben existir;
- no modifica la arquitectura recibida;
- no inventa datos;
- no publica directamente en WordPress;
- no sustituye al motor de decisión;
- no sustituye a N8N.

La IA genera contenido y estructura dentro de las reglas recibidas.

---

2. FLUJO

El flujo general es:

DATOS
↓
MOTOR DE DECISIÓN
↓
ARQUITECTURA SEO
↓
ARQUITECTURA DE LANDING
↓
SISTEMA DE BLOQUES
↓
IA
↓
CONTRATO DE SALIDA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

La IA entra después de que la oportunidad haya sido definida.

---

3. DOCUMENTOS DE REFERENCIA

La IA debe trabajar respetando los documentos maestros del sistema.

Documentos principales:

proyecto/seo/esquema-datos.md
proyecto/seo/matriz-servicios.md
proyecto/seo/matriz-localidades.md
proyecto/seo/arquitectura-urls.md
proyecto/seo/arquitectura-landing.md
proyecto/seo/sistema-bloques.md
proyecto/seo/contrato-salida-ia.md

Cuando exista una contradicción, prevalecen las reglas de autoridad establecidas en el sistema.

---

4. ENTRADA DE LA IA

La IA recibirá una oportunidad estructurada.

Como mínimo:

{
  "opportunity_id": "",
  "servicio": "",
  "subservicio": null,
  "municipio": "",
  "provincia": "",
  "decision_seo": "",
  "tipo_pagina": "",
  "url": "",
  "canonical": "",
  "bloques_autorizados": [],
  "restricciones": []
}

Estos datos no son una sugerencia.

Son la especificación que la IA debe respetar.

---

5. CAMPOS PROTEGIDOS

La IA no puede modificar:

opportunity_id
servicio
subservicio
municipio
provincia
decision_seo
tipo_pagina
url
canonical
bloques_autorizados
restricciones

Si detecta una contradicción:

status = REVIEW

y debe registrar la incidencia.

---

6. URL

La IA no decide la URL.

La URL procede de la arquitectura SEO.

Ejemplo:

servicio = fontanero
municipio = Marbella
subservicio = null

La arquitectura puede proporcionar:

/fontanero/marbella/

La IA debe utilizar exactamente esa URL.

---

7. EJEMPLO CON SUBSERVICIO

Si la oportunidad recibida es:

servicio = fontanero
subservicio = desatascos
municipio = Marbella

y la arquitectura determina:

/fontanero/desatascos/marbella/

la IA debe utilizar esa URL.

No puede cambiarla.

---

8. EJEMPLO SIN SUBSERVICIO

Si la oportunidad recibida es:

servicio = fontanero
subservicio = null
municipio = Marbella

y la arquitectura determina:

/fontanero/marbella/

la IA debe generar una landing de intención general de fontanero en Marbella.

No debe convertirla en una landing de desatascos.

---

9. OBJETIVO DE GENERACIÓN

La IA debe producir una landing:

- coherente;
- específica;
- útil;
- orientada a la intención de búsqueda;
- estructurada;
- diferenciada;
- compatible con el sistema de bloques;
- compatible con N8N;
- compatible con WordPress.

No debe limitarse a sustituir el nombre del municipio dentro de un texto genérico.

---

10. CONTENIDO ESPECÍFICO

La IA debe utilizar:

- servicio;
- subservicio cuando exista;
- municipio;
- provincia;
- datos locales disponibles;
- datos comerciales disponibles;
- información de cobertura disponible;
- información de servicios;
- preguntas relevantes;
- información adicional autorizada.

Debe evitar contenido vacío o genérico.

---

11. INFORMACIÓN LOCAL

El municipio por sí solo no constituye información local suficiente.

La IA solo puede utilizar datos locales respaldados por información disponible.

No debe inventar:

- barrios;
- calles;
- zonas;
- lugares;
- características geográficas;
- tiempos de desplazamiento;
- demanda local;
- problemas habituales;
- estadísticas.

---

12. DATOS COMERCIALES

Cuando exista información de una empresa concreta, la IA puede utilizarla.

Cuando no exista, no puede inventarla.

No debe inventar:

- nombre de empresa;
- teléfono;
- WhatsApp;
- email;
- dirección;
- horario;
- precios;
- garantías;
- años de experiencia;
- certificaciones;
- equipo;
- reseñas;
- valoraciones.

---

13. REGLA DE NO INVENCIÓN

La ausencia de información no debe solucionarse mediante imaginación.

Si un dato no está disponible:

null

o:

bloque desactivado

o:

REVIEW

según el caso.

---

14. ARQUITECTURA DE LANDING

La IA debe respetar la arquitectura de landing definida.

La landing puede incluir:

Header
Navegación
Hero
Contenido principal
Bloques de servicio
Información local
Cobertura
Proceso
Confianza
FAQ
CTA
Footer

No todos los bloques tienen que aparecer.

La selección depende de las reglas del sistema de bloques y de los datos disponibles.

---

15. SISTEMA DE BLOQUES

La IA solo puede utilizar bloques autorizados.

Los identificadores deben proceder de:

proyecto/seo/sistema-bloques.md

No puede inventar:

B99
B100
B-LOCALES

si no existen en el sistema.

---

16. BLOQUES OBLIGATORIOS

Los bloques marcados como obligatorios deben aparecer.

Si falta información necesaria para completarlos:

status = REVIEW

La IA no debe inventar contenido para completar el bloque.

---

17. BLOQUES CONDICIONALES

Los bloques condicionales solo deben aparecer cuando se cumplen sus condiciones.

Ejemplo:

información local disponible
→ bloque local

Si no:

bloque local = disabled

---

18. BLOQUES OPCIONALES

Los bloques opcionales deben utilizarse cuando aporten valor.

No se deben añadir bloques simplemente para hacer la página más larga.

---

19. HERO

El Hero debe reflejar la intención principal.

Para:

fontanero + Marbella

el H1 puede ser:

Fontanero en Marbella

Para:

fontanero + desatascos + Marbella

el H1 puede ser:

Desatascos en Marbella

si esa es la intención definida por la arquitectura.

La IA debe respetar el tipo de página recibido.

---

20. TÍTULO SEO

El title debe:

- representar la intención;
- ser natural;
- incluir los elementos principales cuando corresponda;
- evitar sobreoptimización;
- evitar promesas no verificadas.

---

21. META DESCRIPTION

Debe:

- describir la página;
- ser específica;
- resultar útil para el usuario;
- evitar afirmaciones no verificadas.

---

22. H1

Debe existir un único H1 principal.

Debe ser coherente con:

servicio
subservicio
municipio
tipo de página

---

23. CONTENIDO PRINCIPAL

Debe explicar claramente:

- qué servicio se ofrece;
- para qué necesidades sirve;
- qué puede encontrar el usuario;
- por qué esa página es relevante para la búsqueda.

No debe utilizar relleno artificial.

---

24. SERVICIOS RELACIONADOS

Solo deben incluirse servicios que:

- existan;
- estén autorizados;
- tengan sentido para la oportunidad.

No deben crearse URLs inexistentes.

---

25. ENLAZADO INTERNO

Los enlaces internos deben apuntar únicamente a:

- URLs existentes;
- URLs autorizadas;
- anchors internos válidos.

No se deben inventar páginas futuras como si ya existieran.

---

26. FAQ

Las preguntas deben:

- relacionarse con la intención;
- responder dudas reales;
- evitar repetir artificialmente palabras clave;
- no incluir afirmaciones comerciales no verificadas.

---

27. CTA

La IA puede generar:

- texto del CTA;
- etiqueta del botón;
- intención de acción.

Pero no puede inventar el destino comercial.

Ejemplo:

{
  "action": {
    "type": "contact",
    "label": "Solicitar servicio"
  }
}

Si existe teléfono o WhatsApp autorizado, podrá utilizarse.

---

28. IMÁGENES

La IA puede especificar:

- qué imagen sería adecuada;
- ubicación;
- descripción;
- texto ALT.

No debe inventar URLs de imágenes.

---

29. SCHEMA

La IA puede generar datos estructurados cuando sean aplicables y exista información suficiente.

No debe generar:

- reviews falsas;
- ratings falsos;
- precios inventados;
- información empresarial inexistente.

---

30. DIFERENCIACIÓN ENTRE LANDINGS

Dos landings distintas no deben ser copias con cambios superficiales.

Ejemplo:

/fontanero/marbella/

y:

/fontanero/estepona/

deben compartir arquitectura y reglas, pero pueden presentar contenido local y contextual diferente cuando existan datos que lo permitan.

---

31. ESCALABILIDAD

La misma especificación debe funcionar para:

1 landing
5 landings
100 landings
1.000 landings
10.000 landings

La IA debe trabajar de forma determinista dentro de las reglas recibidas.

---

32. SALIDA

La IA debe devolver exclusivamente el formato definido en:

proyecto/seo/contrato-salida-ia.md

La salida debe ser JSON válido.

No debe añadir explicaciones fuera del JSON.

---

33. ESTRUCTURA DE SALIDA

La salida tendrá como mínimo:

{
  "schema_version": "1.0",
  "opportunity_id": "",
  "status": "READY",
  "identity": {},
  "architecture": {},
  "seo": {},
  "menu": {},
  "blocks": [],
  "images": [],
  "internal_links": [],
  "schema": {},
  "validation": {},
  "issues": {},
  "traceability": {}
}

---

34. STATUS

Valores permitidos:

READY
REVIEW
ERROR

READY

La generación puede continuar.

REVIEW

Existe una incidencia que requiere revisión.

ERROR

No existe una salida válida.

---

35. VALIDACIÓN

Antes de devolver la salida, la IA debe comprobar:

1. URL correcta.
2. Canonical correcta.
3. Servicio correcto.
4. Subservicio correcto.
5. Municipio correcto.
6. Tipo de página correcto.
7. Bloques autorizados.
8. H1 coherente.
9. SEO coherente.
10. Ausencia de datos inventados.
11. Enlaces válidos.
12. JSON válido.

---

36. CONSISTENCIA

Debe existir coherencia entre:

identity
architecture
seo
menu
blocks
internal_links
schema
validation

La URL debe ser consistente en todas las partes donde aparezca.

---

37. TRAZABILIDAD

La salida debe conservar:

schema_version
prompt_version
source_opportunity_id
generated_at

Esto permite saber:

- qué versión generó la landing;
- qué oportunidad la originó;
- cuándo fue generada.

---

38. VERSIONADO DEL PROMPT

El prompt operativo de IA deberá tener una versión.

Ejemplo:

prompt_version = "1.0"

Cuando se modifique sustancialmente:

1.0 → 1.1

o:

1.0 → 2.0

según el alcance del cambio.

---

39. PROHIBICIONES

La IA no puede:

- decidir crear una URL no autorizada;
- cambiar una URL;
- cambiar el municipio;
- cambiar el servicio;
- cambiar la decisión SEO;
- inventar datos;
- inventar empresas;
- inventar teléfonos;
- inventar reseñas;
- crear enlaces inexistentes;
- publicar directamente;
- modificar las reglas maestras.

---

40. RESPONSABILIDADES

Motor SEO

Decide:

- oportunidades;
- estrategia;
- URL;
- arquitectura.

Arquitectura de landing

Define:

- estructura;
- orden;
- componentes.

Sistema de bloques

Define:

- bloques disponibles;
- condiciones;
- requisitos.

IA

Genera:

- textos;
- datos de bloques;
- SEO;
- FAQ;
- contenido contextual;
- salida estructurada.

N8N

Gestiona:

- automatización;
- validación;
- transformación;
- comunicación entre sistemas;
- creación/actualización de WordPress;
- registro.

WordPress

Gestiona:

- almacenamiento;
- renderizado;
- publicación.

---

41. REGLA DE PRIORIDAD

En caso de conflicto:

1. Reglas del sistema
2. Datos de entrada autorizados
3. Arquitectura SEO
4. Arquitectura de landing
5. Sistema de bloques
6. Esta especificación
7. Generación creativa de la IA

La creatividad nunca puede superar una regla superior.

---

42. EJEMPLO OPERATIVO

Entrada:

{
  "opportunity_id": "OPP-0001",
  "servicio": "fontanero",
  "subservicio": null,
  "municipio": "Marbella",
  "provincia": "Málaga",
  "decision_seo": "CREAR",
  "tipo_pagina": "servicio_localidad",
  "url": "/fontanero/marbella/",
  "canonical": "/fontanero/marbella/",
  "bloques_autorizados": [
    "B01",
    "B02",
    "B03",
    "B08",
    "B09"
  ],
  "restricciones": []
}

La IA debe producir una landing de:

Fontanero en Marbella

con:

URL:
/fontanero/marbella/

y no:

/fontanero/desatascos/marbella/

---

43. EJEMPLO CON SUBSERVICIO

Entrada:

{
  "opportunity_id": "OPP-0002",
  "servicio": "fontanero",
  "subservicio": "desatascos",
  "municipio": "Marbella",
  "provincia": "Málaga",
  "decision_seo": "CREAR",
  "tipo_pagina": "servicio_subservicio_localidad",
  "url": "/fontanero/desatascos/marbella/",
  "canonical": "/fontanero/desatascos/marbella/"
}

La IA debe producir una landing específica para:

Desatascos en Marbella

manteniendo la arquitectura recibida.

---

44. REGLA PARA DATOS INSUFICIENTES

Si los datos recibidos no permiten generar una landing fiable:

status = REVIEW

Debe explicar el problema en:

issues.items

No debe completar los huecos inventando información.

---

45. RELACIÓN CON EL CONTRATO

Esta especificación y:

proyecto/seo/contrato-salida-ia.md

forman conjuntamente la definición de la comunicación IA → N8N.

El contrato define qué formato debe devolver la IA.

Esta especificación define cómo debe comportarse la IA para producirlo.

---

46. REGLA DE CAMBIOS

Si se modifica:

- la arquitectura;
- los bloques;
- el esquema de datos;
- el contrato;
- las reglas SEO;

debe revisarse esta especificación.

No se deben modificar documentos de forma aislada cuando el cambio afecte al comportamiento de la IA.

---

47. ESTADO

DEFINIDO

La especificación establece el comportamiento operativo de la IA.

El siguiente documento necesario para completar el flujo técnico será la especificación:

N8N → WordPress

que definirá cómo N8N transforma el JSON recibido en una landing real.
