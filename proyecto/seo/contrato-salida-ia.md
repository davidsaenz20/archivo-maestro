CONTRATO DE SALIDA IA → N8N

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el contrato estructural que debe cumplir toda salida de IA destinada a N8N para generar y mantener una miniweb SEO local.

---

1. FUNCIÓN

Este documento define exactamente qué debe devolver la IA después de recibir una oportunidad previamente validada y una arquitectura autorizada.

La salida debe ser:

- estructurada;
- predecible;
- validable;
- trazable;
- compatible con N8N;
- compatible con el modelo de datos;
- compatible con WordPress;
- independiente del diseño visual;
- capaz de representar una página individual o una miniweb completa;
- capaz de representar un número variable de páginas y bloques.

La IA genera contenido y estructura lógica dentro de los límites recibidos.

La IA no decide libremente qué páginas existen.

La arquitectura previamente autorizada determina:

- qué páginas pueden existir;
- qué URLs pueden utilizarse;
- qué relación existe entre ellas;
- qué bloques pueden utilizar cada página;
- qué oportunidades han sido descartadas;
- qué páginas pueden enlazarse.

---

2. CAMBIO FUNDAMENTAL DE LA VERSIÓN 4.0

La versión 4.0 elimina cualquier supuesto de que una miniweb deba tener un número fijo de páginas.

No existe un número predeterminado de páginas.

Una miniweb puede contener:

- 1 página;
- 2 páginas;
- 5 páginas;
- 10 páginas;
- 20 páginas;
- o cualquier otro número que resulte de la arquitectura y de las reglas de validación.

El sistema debe partir de un universo amplio de posibilidades y permitir descartar aquellas que:

- no tengan intención propia;
- no aporten suficiente valor;
- no tengan información suficiente;
- produzcan duplicación;
- no sean competitivas;
- no tengan justificación comercial;
- no estén respaldadas por la investigación;
- no sean necesarias para la arquitectura.

Por tanto:

POSIBILIDADES
↓
EVALUACIÓN
↓
DESCARTE
↓
PÁGINAS AUTORIZADAS
↓
GENERACIÓN

No:

5 PÁGINAS POR DEFECTO
↓
RELLENAR

---

3. PRINCIPIO DE NÚMERO VARIABLE

El contrato no contiene ningún número fijo de páginas.

"page_count" debe ser siempre:

count(pages[])

Nunca debe utilizarse:

page_count = 5

como regla de generación.

La cantidad final dependerá exclusivamente de:

- arquitectura;
- oportunidades detectadas;
- intención;
- demanda;
- potencial comercial;
- competencia;
- diferenciación;
- información disponible;
- riesgo de duplicación;
- utilidad para el usuario.

---

4. FLUJO OFICIAL

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
OPORTUNIDADES
↓
ARQUITECTURA SEO
↓
UNIVERSO DE PÁGINAS POSIBLES
↓
DESCARTE / AGRUPACIÓN
↓
PÁGINAS AUTORIZADAS
↓
ARQUITECTURA DE LANDING
↓
UNIVERSO DE BLOQUES POSIBLES
↓
DESCARTE DE BLOQUES NO ÚTILES
↓
IA
↓
SITE_PACKAGE JSON
↓
VALIDADOR
↓
N8N
↓
WORDPRESS
↓
MINIWEB PUBLICADA

---

5. REGLA DE AUTORIDAD

La IA recibe información protegida.

No puede modificarla.

Campos protegidos:

- "opportunity_id";
- "sector";
- "service";
- "subservice";
- "municipality";
- "province";
- "country";
- "decision_seo";
- "site_type";
- "page_type";
- "url";
- "canonical";
- "parent_url";
- "depth";
- "authorized_pages";
- "authorized_blocks";
- "restrictions".

Si existe una contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar la incidencia;
4. establecer "REVIEW" cuando corresponda.

---

6. FORMATO DE SALIDA

La salida oficial es:

JSON válido y exclusivamente JSON.

No puede existir contenido fuera del JSON.

No se permite:

- Markdown;
- explicaciones;
- comentarios;
- texto antes del JSON;
- texto después del JSON;
- campos arbitrarios;
- estructuras no definidas;
- páginas no autorizadas;
- bloques no autorizados.

La respuesta debe poder ser procesada automáticamente por N8N.

---

7. ESTRUCTURA PRINCIPAL

La estructura oficial es:

{
  "schema_version": "4.0",
  "opportunity_id": "",
  "status": "READY",
  "site": {},
  "identity": {},
  "architecture": {},
  "pages": [],
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

8. SCHEMA VERSION

Versión actual:

4.0

N8N debe comprobar la versión antes de procesar la respuesta.

Si la versión no es compatible:

ERROR

No se debe intentar interpretar una estructura desconocida.

---

9. STATUS

Valores permitidos:

READY
REVIEW
ERROR

READY

La salida cumple el contrato y puede continuar.

REVIEW

Existe una incidencia que requiere revisión humana.

ERROR

La salida no puede procesarse correctamente.

---

10. SITE

El objeto "site" representa la miniweb completa.

Ejemplo:

{
  "site": {
    "type": "local_service_site",
    "name": "Fontaneros en Fuengirola",
    "root_url": "/fontaneros/fuengirola/",
    "page_count": 11
  }
}

"page_count" debe coincidir exactamente con el número real de elementos de "pages[]".

La IA no puede inventar una estructura de sitio independiente de la arquitectura.

---

11. IDENTITY

Representa la identidad común del sitio.

{
  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Fuengirola",
    "province": "Málaga",
    "country": "España"
  }
}

Los valores deben coincidir con la entrada autorizada.

La IA no puede cambiar:

- localidad;
- municipio;
- provincia;
- servicio;
- sector.

---

12. ARCHITECTURE

Representa la arquitectura previamente determinada.

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "/fontaneros/fuengirola/",
    "authorized_pages": [],
    "authorized_blocks": []
  }
}

La IA no decide la arquitectura.

La arquitectura debe existir antes de la generación.

---

13. UNIVERSO DE PÁGINAS

La arquitectura puede proporcionar un conjunto amplio de oportunidades de página.

Estas oportunidades pueden incluir:

- servicio principal;
- variantes del servicio;
- subservicios;
- problemas;
- necesidades;
- servicios urgentes;
- servicios especializados;
- tipos de cliente;
- páginas comerciales;
- contacto;
- presupuesto;
- otras intenciones relevantes.

La existencia de una posibilidad no significa que deba publicarse.

Cada posibilidad debe superar las reglas correspondientes.

---

14. DESCARTE DE PÁGINAS

Una página candidata debe descartarse cuando:

- no tiene intención propia;
- duplica otra intención;
- no aporta valor;
- no existe información suficiente;
- no existe diferenciación;
- genera riesgo elevado de contenido repetitivo;
- no tiene justificación comercial;
- no está respaldada por la investigación;
- no es necesaria dentro de la arquitectura.

El descarte debe prevalecer sobre la generación artificial.

---

15. REGLA DE NO CREACIÓN DE PÁGINAS POR LA IA

La IA no puede crear una URL simplemente porque detecte:

- una keyword;
- un sinónimo;
- un servicio relacionado;
- una idea comercial;
- una pregunta;
- una localidad;
- una posible oportunidad.

La IA solo puede generar páginas que formen parte de:

authorized_pages

Si una página no está autorizada:

NO SE GENERA.

---

16. PÁGINAS

El objeto "pages" representa todas las páginas finalmente autorizadas que forman parte de la miniweb.

Ejemplo:

{
  "pages": [
    {
      "page_id": "FUE-FON-P01",
      "page_type": "service_locality",
      "url": "/fontaneros/fuengirola/",
      "canonical": "/fontaneros/fuengirola/",
      "parent_url": null,
      "depth": 1
    },
    {
      "page_id": "FUE-FON-P02",
      "page_type": "subservice_locality",
      "url": "/fontaneros/fuengirola/desatascos/",
      "canonical": "/fontaneros/fuengirola/desatascos/",
      "parent_url": "/fontaneros/fuengirola/",
      "depth": 2
    }
  ]
}

No existe un límite artificial de páginas.

---

17. ESTRUCTURA DE UNA PÁGINA

Cada página puede contener:

{
  "page_id": "",
  "page_type": "",
  "url": "",
  "canonical": "",
  "parent_url": null,
  "depth": 1,
  "identity": {},
  "seo": {},
  "menu": {},
  "authorized_blocks": [],
  "blocks": [],
  "internal_links": []
}

Cada página es una unidad independiente dentro del "SITE_PACKAGE".

---

18. SEO DE CADA PÁGINA

Cada página puede contener:

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": ""
  }
}

El contenido debe corresponder con la intención concreta de esa página.

No se debe generar contenido prácticamente idéntico entre páginas con intenciones diferentes.

---

19. MENU

La salida debe permitir construir la navegación de la miniweb.

Ejemplo:

{
  "menu": {
    "items": [
      {
        "label": "Fontaneros en Fuengirola",
        "url": "/fontaneros/fuengirola/",
        "type": "internal"
      },
      {
        "label": "Desatascos",
        "url": "/fontaneros/fuengirola/desatascos/",
        "type": "internal"
      },
      {
        "label": "Fontanero 24 horas",
        "url": "/fontaneros/fuengirola/24-horas/",
        "type": "internal"
      },
      {
        "label": "Presupuesto",
        "url": "/fontaneros/fuengirola/presupuesto/",
        "type": "internal"
      },
      {
        "label": "Contacto",
        "url": "/fontaneros/fuengirola/contacto/",
        "type": "internal"
      }
    ]
  }
}

Este ejemplo no implica que esas páginas deban existir.

Todas las URLs deben estar previamente autorizadas.

La IA no puede inventar páginas para completar el menú.

---

20. BLOQUES

Los bloques pertenecen a una página concreta.

Ejemplo:

{
  "page_id": "FUE-FON-P01",
  "blocks": [
    {
      "id": "B03",
      "type": "hero",
      "enabled": true,
      "data": {}
    }
  ]
}

Los identificadores deben corresponder exactamente con:

"proyecto/seo/sistema-bloques.md"

La IA no puede inventar nuevos IDs.

---

21. MAPA OFICIAL DE BLOQUES

ID| TYPE
B01| header
B02| navigation
B03| hero
B04| main_content
B05| cta
B06| footer
B07| subservice
B08| problems
B09| local_context
B10| coverage
B11| process
B12| trust
B13| differentiation
B14| faq
B15| related_services
B16| related_locations
B17| structured_data
B18| testimonials
B19| cases
B20| gallery
B21| pricing
B22| opening_hours
B23| map

El "type" debe corresponder exactamente al "id".

---

22. UNIVERSO DE BLOQUES

Para cada página, la arquitectura puede autorizar un conjunto amplio de bloques posibles.

El sistema debe considerar inicialmente todos los bloques compatibles con:

- tipo de página;
- intención;
- sector;
- información disponible;
- restricciones.

Posteriormente deben descartarse aquellos que no aporten valor.

No existe una obligación de utilizar todos los bloques.

---

23. DESCARTE DE BLOQUES

Un bloque debe omitirse cuando:

- no aporta valor;
- no existe información suficiente;
- la información es demasiado débil;
- produciría contenido genérico;
- aumenta el riesgo de duplicación;
- obliga a inventar información;
- no corresponde a la intención;
- no es útil para el usuario.

La ausencia de un bloque es una salida válida.

---

24. BLOQUES AUTORIZADOS POR PÁGINA

Cada página debe indicar:

{
  "authorized_blocks": [
    "B01",
    "B02",
    "B03",
    "B04",
    "B08",
    "B09",
    "B14",
    "B05",
    "B06"
  ]
}

La IA solo puede utilizar esos bloques.

El número de bloques puede variar entre páginas.

No existe una cantidad fija de bloques por página.

---

25. BLOQUES OBLIGATORIOS

Cuando la arquitectura determine una página funcional, como mínimo debe poder representar:

- identidad;
- contenido principal;
- navegación cuando corresponda;
- CTA cuando exista canal válido;
- cierre/navegación global cuando corresponda.

No se debe inventar información para completar un bloque.

---

26. BLOQUES CONDICIONALES Y OPCIONALES

Los bloques pueden omitirse cuando no exista información suficiente o cuando no aporten valor.

Esto incluye:

- B07;
- B08;
- B09;
- B10;
- B11;
- B12;
- B13;
- B14;
- B15;
- B16;
- B18;
- B19;
- B20;
- B21;
- B22;
- B23.

La selección final debe depender de la información y de la intención.

---

27. CONTENIDO

El contenido debe ser:

- específico;
- útil;
- coherente con la intención;
- basado en los datos recibidos;
- compatible con las restricciones;
- suficientemente diferenciado cuando la intención lo requiera.

No debe generarse contenido únicamente para aumentar:

- palabras;
- keywords;
- headings;
- enlaces;
- longitud.

---

28. DIFERENCIACIÓN ENTRE PÁGINAS

Las páginas pueden compartir:

- header;
- navegación;
- footer;
- estilo;
- componentes;
- determinadas estructuras.

Pero cada página debe responder a su propia intención.

Por ejemplo:

/fontaneros/fuengirola/

puede responder a la intención general.

/fontaneros/fuengirola/desatascos/

puede responder a una necesidad específica.

/fontaneros/fuengirola/presupuesto/

puede responder a una intención comercial concreta, si ha sido autorizada.

No deben convertirse todas las páginas en una misma landing cambiando únicamente el título.

---

29. NO INVENCIÓN

Está prohibido inventar:

- empresas;
- profesionales;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- disponibilidad;
- cobertura;
- certificaciones;
- garantías;
- experiencia;
- reseñas;
- testimonios;
- casos;
- datos locales;
- imágenes;
- URLs;
- estadísticas;
- datos comerciales.

Cuando un dato no existe:

null

o:

REVIEW

si resulta imprescindible para publicar.

Para el piloto podrán utilizarse datos ficticios únicamente cuando el entorno esté expresamente marcado como TEST y nunca deben confundirse con datos reales de producción.

---

30. CTA

La IA puede generar el texto del CTA.

No puede inventar el canal ni los datos de contacto.

Ejemplo:

{
  "label": "Solicitar presupuesto",
  "action": "contact"
}

Los datos reales deben proceder del modelo de datos.

En un entorno de producción, un CTA sin destino real debe:

- omitirse;
- quedar deshabilitado;
- o marcarse como "REVIEW";

según las reglas del sistema.

Nunca debe publicarse un dato ficticio como si fuera un dato real.

---

31. FAQ

Formato:

{
  "id": "B14",
  "type": "faq",
  "enabled": true,
  "data": {
    "title": "",
    "items": [
      {
        "question": "",
        "answer": ""
      }
    ]
  }
}

Las preguntas deben proceder de:

- intención;
- investigación;
- conocimiento válido;
- datos disponibles.

No deben generarse únicamente para introducir keywords.

---

32. INFORMACIÓN LOCAL

Cuando exista B09, la información debe estar respaldada.

No se inventan:

- barrios;
- calles;
- urbanizaciones;
- características;
- necesidades;
- cobertura;
- tiempos;
- particularidades.

Repetir el nombre del municipio no constituye información local.

---

33. COBERTURA

Cuando exista B10:

{
  "areas": []
}

Solo deben incluirse zonas respaldadas.

No se generan listas masivas artificiales.

---

34. CONFIANZA

B12 solo puede utilizar señales verificables:

- experiencia;
- certificaciones;
- garantías;
- reseñas;
- datos comerciales;
- cobertura;
- otros datos proporcionados.

Nunca se inventan señales de confianza.

---

35. DIFERENCIACIÓN

B13 solo puede utilizar información real que justifique la diferenciación.

No es suficiente:

- cambiar localidad;
- cambiar sinónimos;
- reordenar párrafos;
- cambiar títulos;
- modificar algunas frases;
- generar texto diferente sin datos diferentes.

---

36. SERVICIOS RELACIONADOS

B15 solo puede enlazar servicios existentes y autorizados.

No se crean URLs nuevas desde la IA.

---

37. LOCALIDADES RELACIONADAS

B16 solo puede utilizar localidades existentes en la arquitectura.

No se genera una red masiva de enlaces únicamente para SEO.

---

38. DATOS ESTRUCTURADOS

B17 y "schema" solo pueden utilizar datos verificables.

No se inventan:

- ratings;
- reviews;
- precios;
- horarios;
- direcciones;
- empresas;
- personas.

El JSON-LD final será responsabilidad del sistema de renderizado.

---

39. IMÁGENES

Formato:

{
  "images": [
    {
      "url": "",
      "alt": "",
      "title": "",
      "type": ""
    }
  ]
}

La URL debe corresponder a un recurso real disponible.

La IA no puede inventar imágenes ni URLs de imágenes.

---

40. ENLACES INTERNOS

Formato:

{
  "internal_links": [
    {
      "url": "",
      "anchor": "",
      "target": "",
      "reason": ""
    }
  ]
}

Las URLs deben proceder de la arquitectura autorizada.

No deben generarse enlaces hacia páginas descartadas.

---

41. VALIDATION

La IA puede devolver:

{
  "validation": {
    "valid": true,
    "checks": []
  }
}

Pero la validación definitiva corresponde al validador externo.

La IA no es la autoridad final.

---

42. ISSUES

Formato:

{
  "issues": {
    "items": [
      {
        "code": "",
        "severity": "",
        "field": "",
        "page_id": "",
        "message": ""
      }
    ]
  }
}

La IA debe registrar problemas detectados en lugar de ocultarlos.

---

43. TRACEABILITY

La salida debe permitir rastrear el origen.

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "contract_version": "4.0"
  }
}

Esto permite saber qué documentación y qué oportunidad originaron la salida.

---

44. REGLAS DE INTEGRIDAD

N8N debe rechazar la salida cuando:

- no sea JSON válido;
- falte "schema_version";
- falte "opportunity_id";
- falte "status";
- falte "site";
- falte "pages";
- exista una página no autorizada;
- exista un bloque no autorizado;
- exista un ID desconocido;
- el "type" no corresponda al ID;
- la URL no coincida con la arquitectura;
- el canonical no coincida con la arquitectura;
- exista una modificación de campos protegidos;
- existan estructuras incompatibles;
- existan URLs no autorizadas;
- exista información obligatoria ausente.

Resultado:

ERROR

o:

REVIEW

según la naturaleza del problema.

---

45. REGLA DE CONSISTENCIA DEL NÚMERO DE PÁGINAS

El contrato debe comprobar:

site.page_count == count(pages[])

Si no coincide:

ERROR

La IA no puede indicar un número de páginas diferente al contenido real de "pages[]".

---

46. REGLA DE CONSISTENCIA DE BLOQUES

Para cada página:

blocks[].id ⊆ authorized_blocks[]

Si un bloque no pertenece a los bloques autorizados:

ERROR

No se publica.

---

47. IDEMPOTENCIA

El contrato debe permitir que N8N procese varias veces la misma salida sin crear duplicados.

El identificador principal es:

opportunity_id

Cada página debe tener además:

page_id

N8N utilizará estos identificadores para localizar páginas existentes.

Si una página ya existe:

actualizar

Si no existe:

crear

Nunca crear duplicados simplemente porque el flujo se ejecute nuevamente.

---

48. WORDPRESS

La IA no genera directamente HTML final para WordPress.

Flujo:

IA
↓
JSON
↓
VALIDADOR
↓
N8N
↓
MODELO WORDPRESS
↓
RENDERIZADO

WordPress será responsable de representar visualmente:

- páginas;
- menú;
- bloques;
- enlaces;
- imágenes;
- datos estructurados.

La IA trabaja con contenido y estructura lógica.

---

49. N8N

N8N será responsable de:

- recibir el JSON;
- validar la versión;
- validar las páginas;
- validar los bloques;
- comprobar identificadores;
- comprobar existencia;
- crear páginas;
- actualizar páginas;
- construir relaciones;
- construir navegación;
- enviar datos a WordPress;
- registrar errores;
- registrar resultados.

N8N no debe reinterpretar arbitrariamente las decisiones SEO.

---

50. CREACIÓN DE MINIWEB

Cuando la arquitectura autorice varias páginas, la salida debe representar todas ellas dentro del mismo "SITE_PACKAGE".

Ejemplo conceptual:

SITE_PACKAGE
│
├── PAGE 01
│   └── /fontaneros/fuengirola/
│
├── PAGE 02
│   └── /fontaneros/fuengirola/desatascos/
│
├── PAGE 03
│   └── /fontaneros/fuengirola/24-horas/
│
├── PAGE 04
│   └── /fontaneros/fuengirola/presupuesto/
│
├── PAGE 05
│   └── /fontaneros/fuengirola/reparaciones/
│
└── PAGE N
    └── ...

Este esquema es conceptual.

No existe un número fijo de páginas.

N8N debe poder recorrer:

pages[]

y procesar cada página de forma independiente.

---

51. RELACIÓN ENTRE PÁGINAS

Cada página debe poder identificar:

- página padre;
- profundidad;
- páginas relacionadas;
- enlaces de navegación.

Ejemplo:

{
  "page_id": "FUE-FON-P02",
  "url": "/fontaneros/f
