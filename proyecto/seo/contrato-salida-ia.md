CONTRATO DE SALIDA IA → N8N

Versión: 3.1
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
- capaz de representar una página individual o una miniweb completa.

La IA genera contenido.

La IA no decide libremente qué páginas existen.

La arquitectura previamente autorizada determina:

- qué páginas forman parte del sitio;
- qué URLs tienen;
- qué relación existe entre ellas;
- qué bloques puede utilizar cada página;
- qué páginas pueden enlazarse.

---

2. PRINCIPIO FUNDAMENTAL DE LA VERSIÓN 3.1

La salida se considera un SITE_PACKAGE.

Un SITE_PACKAGE representa una unidad completa de generación o actualización.

Puede contener:

- una sola página;
- varias páginas pertenecientes a una misma miniweb;
- navegación común;
- relaciones entre páginas;
- bloques específicos por página;
- información SEO por página;
- datos compartidos del sitio.

La IA nunca puede ampliar el SITE_PACKAGE por iniciativa propia.

---

3. FLUJO OFICIAL

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
DECISIÓN = CREAR
↓
ARQUITECTURA SEO
↓
ARQUITECTURA DE MINIWEB
↓
MODELO DE DATOS
↓
BLOQUES AUTORIZADOS
↓
IA
↓
SITE_PACKAGE JSON
↓
VALIDADOR EXTERNO
↓
N8N
↓
WORDPRESS
↓
MINIWEB PUBLICADA

---

4. REGLA DE AUTORIDAD

La IA recibe información protegida.

No puede modificarla.

Campos protegidos:

- "opportunity_id"
- "sector"
- "service"
- "subservice"
- "country"
- "province"
- "municipality"
- "decision_seo"
- "site_type"
- "root_url"
- "authorized_pages"
- "authorized_blocks"
- "restrictions"

Los datos de arquitectura de cada página también están protegidos:

- "page_id"
- "page_type"
- "url"
- "canonical"
- "parent_url"
- "depth"
- "authorized_blocks"

Si existe una contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar la incidencia;
4. establecer "REVIEW";
5. impedir la publicación hasta resolverla.

---

5. FORMATO DE SALIDA

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

6. ESTRUCTURA PRINCIPAL

La estructura oficial es:

{
  "schema_version": "3.1",
  "opportunity_id": "",
  "status": "READY",
  "site": {},
  "identity": {},
  "architecture": {},
  "pages": [],
  "menu": {},
  "internal_links": [],
  "images": [],
  "schema": {},
  "validation": {},
  "issues": {},
  "traceability": {}
}

Los contenidos de una página pertenecen a "pages[]".

No existe un "blocks[]" global obligatorio.

Los bloques pertenecen exclusivamente a la página que los utiliza.

Esto evita duplicaciones y facilita que N8N procese cada página de forma independiente.

---

7. SCHEMA VERSION

Versión actual:

"3.1"

N8N debe comprobar la versión antes de procesar la respuesta.

Si la versión no es compatible:

"ERROR"

No se debe intentar interpretar una estructura desconocida.

---

8. STATUS

Valores permitidos:

"READY"

"REVIEW"

"ERROR"

READY

La salida cumple el contrato y puede continuar al proceso de validación/publicación.

REVIEW

Existe una incidencia que requiere revisión humana.

La salida no debe publicarse automáticamente.

ERROR

La salida no puede procesarse correctamente.

N8N debe detener el procesamiento.

---

9. SITE

El objeto "site" representa la miniweb completa.

Ejemplo:

{
  "site": {
    "type": "local_service_site",
    "name": "Fontanero en Marbella",
    "root_url": "/fontanero/marbella/",
    "page_count": 4
  }
}

El nombre, tipo, URL raíz y número de páginas deben coincidir con la arquitectura autorizada.

La IA no puede crear una miniweb arbitraria.

---

10. IDENTITY

Representa la identidad común del SITE_PACKAGE.

{
  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Marbella",
    "province": "Málaga",
    "country": "España"
  }
}

Los valores deben coincidir con la entrada autorizada.

La IA no puede cambiar:

- sector;
- servicio;
- subservicio;
- municipio;
- provincia;
- país.

---

11. ARCHITECTURE

Representa la arquitectura previamente autorizada.

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "/fontanero/marbella/",
    "authorized_pages": [],
    "authorized_blocks": []
  }
}

"authorized_pages" contiene las páginas que pueden existir.

"authorized_blocks" contiene los bloques que pueden utilizarse dentro del SITE_PACKAGE.

La IA no puede modificar estos valores.

---

12. AUTHORIZED PAGES

Cada página autorizada debe definirse antes de la generación.

Ejemplo conceptual:

{
  "page_id": "FON-MARB-P01",
  "page_type": "service_locality",
  "url": "/fontanero/marbella/",
  "canonical": "/fontanero/marbella/",
  "parent_url": null,
  "depth": 1,
  "authorized_blocks": [
    "B01",
    "B02",
    "B03",
    "B04",
    "B05",
    "B06",
    "B08",
    "B09",
    "B14"
  ]
}

La arquitectura puede autorizar otras páginas.

Por ejemplo:

P01 Inicio
P02 Desatascos
P03 24 horas
P04 Contacto

Pero una página como "24-horas" solo podrá existir si ha sido previamente autorizada y respaldada por la investigación y el motor.

---

13. PÁGINAS GENERADAS

"pages[]" representa únicamente las páginas que la IA debe generar en esta ejecución.

Cada página debe corresponder exactamente a una página autorizada.

Regla:

AUTHORIZED PAGE
↓
GENERACIÓN
↓
PAGE

Nunca:

IDEA DE IA
↓
NUEVA PAGE

Si una página no está autorizada:

NO SE GENERA.

---

14. ESTRUCTURA DE UNA PÁGINA

Cada elemento de "pages[]" debe contener:

{
  "page_id": "",
  "page_type": "",
  "url": "",
  "canonical": "",
  "parent_url": null,
  "depth": 1,
  "identity": {},
  "seo": {},
  "authorized_blocks": [],
  "blocks": [],
  "internal_links": [],
  "status": "READY",
  "issues": []
}

Los campos estructurales son protegidos.

La IA puede completar los campos de contenido, pero no modificar la arquitectura recibida.

---

15. IDENTIFICACIÓN ESTABLE DE PÁGINAS

Cada página debe disponer de un "page_id" estable.

Ejemplo:

FON-MARB-P01
FON-MARB-P02
FON-MARB-P03
FON-MARB-P04

El "page_id" debe mantenerse estable durante las actualizaciones.

No debe cambiar porque se modifique el contenido.

No se deben crear nuevos identificadores para una página existente.

---

16. URL

La URL debe coincidir exactamente con la arquitectura autorizada.

Ejemplo:

/fontanero/marbella/

/fontanero/marbella/desatascos/

La IA no puede modificar:

- slug;
- estructura;
- profundidad;
- parent_url;
- URL.

Si detecta que la URL autorizada parece incorrecta:

"REVIEW"

No la modifica por iniciativa propia.

---

17. CANONICAL

El canonical debe coincidir con el canonical autorizado.

No puede modificarse para resolver problemas detectados durante la generación.

Si existe contradicción:

"REVIEW"

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

Cada página indexable tendrá un único H1.

No se debe generar contenido prácticamente idéntico entre páginas.

---

19. MENU

El menú representa la navegación autorizada de la miniweb.

Ejemplo:

{
  "menu": {
    "items": [
      {
        "label": "Inicio",
        "url": "/fontanero/marbella/",
        "type": "internal"
      },
      {
        "label": "Desatascos",
        "url": "/fontanero/marbella/desatascos/",
        "type": "internal"
      },
      {
        "label": "24 horas",
        "url": "/fontanero/marbella/24-horas/",
        "type": "internal"
      },
      {
        "label": "Contacto",
        "url": "/fontanero/marbella/contacto/",
        "type": "internal"
      }
    ]
  }
}

Todas las URLs del menú deben existir en "authorized_pages".

La IA puede generar los textos de los elementos del menú, pero no puede crear nuevas páginas para completar el menú.

---

20. BLOQUES POR PÁGINA

Los bloques pertenecen a una página.

Ejemplo:

{
  "page_id": "FON-MARB-P01",
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

22. AUTHORIZED BLOCKS

Cada página debe indicar qué bloques puede utilizar.

Ejemplo:

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

Si intenta utilizar un bloque no autorizado:

"ERROR"

---

23. BLOQUES OBLIGATORIOS

Cuando la arquitectura determine una página funcional, como mínimo debe poder representar:

- identidad;
- navegación;
- contenido principal;
- CTA cuando exista un canal válido;
- footer.

No se debe inventar información para completar un bloque.

---

24. BLOQUES CONDICIONALES

Los bloques condicionales pueden omitirse cuando no exista información suficiente.

Ejemplos:

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

La omisión es válida.

---

25. CONTENIDO

El contenido debe ser:

- específico;
- útil;
- coherente con la intención;
- basado en datos recibidos;
- compatible con las restricciones;
- diferenciado cuando la intención o los datos sean diferentes.

No debe generarse contenido únicamente para aumentar:

- palabras;
- keywords;
- headings;
- enlaces;
- longitud.

---

26. DIFERENCIACIÓN ENTRE PÁGINAS

Las páginas de una misma miniweb pueden compartir:

- header;
- navegación;
- footer;
- diseño;
- determinados bloques.

Pero cada página debe responder a su propia intención.

Ejemplo:

/fontanero/marbella/

responde a la intención general.

/fontanero/marbella/desatascos/

responde a la intención específica de desatascos.

/fontanero/marbella/24-horas/

solo responde a esa intención si está respaldada.

/fontanero/marbella/contacto/

responde a la intención de contacto.

No deben convertirse todas las páginas en la misma landing cambiando únicamente el título.

---

27. REGLA DE DATOS INSUFICIENTES

Cuando una página esté autorizada pero no exista información suficiente para generar contenido fiable:

status = REVIEW

La IA debe registrar la incidencia.

No debe rellenar la página con contenido inventado.

La página no debe publicarse automáticamente.

---

28. NO INVENCIÓN

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

Cuando un dato no exista:

"null"

o:

"REVIEW"

si es imprescindible para la página.

---

29. CTA

La IA puede generar el texto del CTA.

No puede inventar el canal.

Ejemplo:

{
  "label": "Solicitar presupuesto",
  "action": "contact"
}

Los datos reales de contacto deben proceder del modelo de datos.

---

30. FAQ

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

31. INFORMACIÓN LOCAL

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

Repetir el nombre de la localidad no constituye información local.

---

32. COBERTURA

Cuando exista B10:

{
  "areas": []
}

Solo deben incluirse zonas respaldadas.

No se generan listas masivas artificiales.

---

33. CONFIANZA

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

34. DIFERENCIACIÓN

B13 solo puede utilizar información real que justifique la diferenciación.

No es suficiente:

- cambiar localidad;
- cambiar sinónimos;
- reordenar párrafos;
- cambiar títulos;
- modificar algunas frases;
- generar texto diferente sin datos diferentes.

---

35. SERVICIOS RELACIONADOS

B15 solo puede enlazar servicios existentes y autorizados.

No se crean URLs nuevas desde la IA.

---

36. LOCALIDADES RELACIONADAS

B16 solo puede utilizar localidades existentes en la arquitectura.

No se genera una red masiva de enlaces únicamente para SEO.

---

37. DATOS ESTRUCTURADOS

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

38. IMÁGENES

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

39. ENLACES INTERNOS

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

No se permiten enlaces hacia páginas inexistentes o no autorizadas.

---

40. VALIDATION

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

41. ISSUES

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

42. TRACEABILITY

La salida debe permitir rastrear el origen.

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "contract_version": "3.1"
  }
}

Esto permite saber qué documentación y qué oportunidad originaron la salida.

---

43. REGLAS DE INTEGRIDAD

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
- exista información obligatoria ausente;
- exista un "page_id" duplicado;
- exista una misma URL en más de una página;
- exista un bloque fuera de su página;
- una página utilice un bloque que no figure en sus "authorized_blocks".

Resultado:

"ERROR"

o:

"REVIEW"

según la naturaleza del problema.

---

44. IDEMPOTENCIA

El contrato debe permitir que N8N procese varias veces la misma salida sin crear duplicados.

Los identificadores estables son:

opportunity_id
page_id
url

El identificador principal de la oportunidad es:

"opportunity_id"

El identificador principal de una página es:

"page_id"

La URL debe permanecer asociada a la misma página mientras la arquitectura no cambie.

Si una página ya existe:

ACTUALIZAR

Si no existe:

CREAR

Nunca se deben crear duplicados simplemente porque el flujo vuelva a ejecutarse.

Si la arquitectura cambia, el cambio debe ser tratado como una modificación estructural y no como una simple actualización de contenido.

---

45. WORDPRESS

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

46. N8N

N8N será responsable de:

- recibir el JSON;
- validar la versión;
- validar las páginas;
- validar los bloques;
- comprobar identificadores;
- comprobar URLs;
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

47. CREACIÓN DE MINIWEB

Cuando la arquitectura autorice varias páginas, el SITE_PACKAGE debe representar todas las páginas autorizadas incluidas en esta ejecución.

Ejemplo:

SITE_PACKAGE
│
├── PAGE 01
│   └── /fontanero/marbella/
│
├── PAGE 02
│   └── /fontanero/marbella/desatascos/
│
├── PAGE 03
│   └── /fontanero/marbella/24-horas/
│
└── PAGE 04
    └── /fontanero/marbella/contacto/

Importante:

El ejemplo no autoriza esas páginas.

Solo la arquitectura real puede autorizar su existencia.

N8N debe recorrer:

"pages[]"

y procesar cada página independientemente.

---

48. RELACIÓN ENTRE PÁGINAS

Cada página debe poder identificar:

- página padre;
- profundidad;
- páginas relacionadas;
- enlaces de navegación.

Ejemplo:

{
  "page_id": "FON-MARB-P02",
  "url": "/fontanero/marbella/desatascos/",
  "parent_url": "/fontanero/marbella/",
  "depth": 2
}

Esto permite construir una miniweb coherente y no un conjunto de páginas aisladas.

---

49. ACTUALIZACIÓN DE UNA MINIWEB

El mismo contrato sirve para crear y actualizar.

Si una página cambia:

N8N debe actualizar únicamente la página afectada cuando sea posible.

Si cambia el contenido:

actualización de contenido

Si cambia la arquitectura:

REVISIÓN DE ARQUITECTURA
↓
NUEVA AUTORIZACIÓN
↓
NUEVA GENERACIÓN

La IA no puede alterar la arquitectura durante una actualización.

---

50. REGLA DE NO CREACIÓN AUTOMÁTICA

La IA no puede convertir automáticamente una idea en una página.

Ejemplo:

Si detecta:

fontanero + Marbella + reparación de caldera

no puede crear:

/fontanero/marbella/reparacion-caldera/

salvo que esa página esté previamente autorizada por la arquitectura.

---

51. RELACIÓN CON EL SISTEMA DE BLOQUES

El contrato utiliza exclusivamente los bloques definidos en:

"proyecto/seo/sistema-bloques.md"

El sistema de bloques define:

qué bloques existen.

Este contrato define:

cómo debe devolverlos la IA.

No deben existir IDs paralelos.

---

52. RELACIÓN CON ARQUITECTURA DE LANDING

"proyecto/seo/arquitectura-landing.md" determina la estructura funcional de cada página.

La arquitectura de miniweb determina además:

- qué páginas existen;
- qué relación tienen;
- qué URL tienen;
- qué bloques están autorizados.

Flujo:

ARQUITECTURA
↓
AUTHORIZED PAGES
↓
AUTHORIZED BLOCKS
↓
IA
↓
JSON

---

53. RELACIÓN CON MODELO DE DATOS

El contrato no crea un modelo de datos paralelo.

Los datos deben proceder del modelo canónico definido en:

"proyecto/seo/esquema-datos.md"

y de los documentos específicos que correspondan.

No se deben invent
