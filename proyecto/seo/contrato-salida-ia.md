CONTRATO DE SALIDA IA → N8N

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el contrato estructural que debe cumplir toda salida de IA destinada a N8N para generar y mantener miniwebs SEO locales.

---

1. FUNCIÓN

Este documento define exactamente qué debe devolver la IA después de recibir una oportunidad previamente validada, una arquitectura autorizada y las relaciones de interlinking permitidas.

La salida debe ser:

- estructurada;
- predecible;
- validable;
- trazable;
- compatible con N8N;
- compatible con el modelo de datos;
- compatible con WordPress;
- independiente del diseño visual;
- capaz de representar una página individual;
- capaz de representar una miniweb completa;
- capaz de representar relaciones internas entre páginas autorizadas.

La IA genera contenido y estructura lógica.

La IA no decide libremente:

- qué páginas existen;
- qué URLs existen;
- qué servicios deben crearse;
- qué localidades deben crearse;
- qué relaciones de interlinking existen.

La arquitectura y el sistema de interlinking tienen autoridad sobre esas decisiones.

---

2. PRINCIPIO FUNDAMENTAL

El contrato debe separar:

DECISIÓN

de:

ARQUITECTURA

de:

CONTENIDO

de:

INTERLINKING

La IA no puede modificar una capa superior.

Flujo:

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
ARQUITECTURA
↓
MODELO DE DATOS
↓
INTERLINKING AUTORIZADO
↓
BLOQUES AUTORIZADOS
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

3. FORMATO DE SALIDA

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
- URLs no autorizadas;
- enlaces no autorizados.

La respuesta debe poder ser procesada automáticamente por N8N.

---

4. ESTRUCTURA PRINCIPAL

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
  "interlinking": {},
  "schema": {},
  "validation": {},
  "issues": {},
  "traceability": {}
}

---

5. SCHEMA VERSION

Versión actual:

"4.0"

N8N debe comprobar la versión antes de procesar la respuesta.

Si la versión no es compatible:

"ERROR"

No se debe intentar interpretar una estructura desconocida.

---

6. STATUS

Valores permitidos:

"READY"

"REVIEW"

"ERROR"

READY

La salida cumple el contrato y puede continuar.

REVIEW

Existe una incidencia que requiere revisión humana.

ERROR

La salida no puede procesarse correctamente.

---

7. REGLA DE AUTORIDAD

La IA recibe información protegida.

No puede modificarla.

Campos protegidos:

- "opportunity_id"
- "sector"
- "service"
- "subservice"
- "municipality"
- "province"
- "country"
- "decision_seo"
- "site_type"
- "page_type"
- "url"
- "canonical"
- "parent_url"
- "depth"
- "authorized_pages"
- "authorized_blocks"
- "authorized_internal_links"
- "restrictions"

Si existe una contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar la incidencia;
4. establecer "REVIEW" cuando corresponda.

---

8. SITE

El objeto "site" representa la miniweb completa.

Ejemplo:

{
  "site": {
    "type": "local_service_site",
    "name": "Fontanero en Estepona",
    "root_url": "/fontanero/estepona/",
    "page_count": 8
  }
}

El número de páginas debe proceder de la arquitectura autorizada.

La IA no puede fijar por defecto un número determinado de páginas.

No existe ninguna regla que establezca:

- 5 páginas;
- 3 servicios;
- 1 contacto;
- cualquier otro número fijo.

La cantidad de páginas debe depender de la arquitectura autorizada.

---

9. IDENTITY

Representa la identidad común del sitio.

{
  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Estepona",
    "province": "Málaga",
    "country": "España"
  }
}

Los valores deben coincidir con la entrada.

La IA no puede cambiar:

- localidad;
- municipio;
- provincia;
- servicio;
- sector.

---

10. ARCHITECTURE

Representa la arquitectura previamente determinada.

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "/fontanero/estepona/",
    "authorized_pages": [],
    "authorized_blocks": [],
    "authorized_internal_links": []
  }
}

La IA no decide la arquitectura.

La arquitectura debe existir antes de la generación.

---

11. PÁGINAS

El objeto "pages" representa todas las páginas autorizadas.

No existe un número mínimo o máximo fijo de páginas.

Ejemplo:

{
  "pages": [
    {
      "page_id": "FON-EST-P01",
      "page_type": "service_locality",
      "url": "/fontanero/estepona/",
      "canonical": "/fontanero/estepona/",
      "parent_url": null,
      "depth": 1
    },
    {
      "page_id": "FON-EST-P02",
      "page_type": "subservice_locality",
      "url": "/fontanero/estepona/desatascos/",
      "canonical": "/fontanero/estepona/desatascos/",
      "parent_url": "/fontanero/estepona/",
      "depth": 2
    }
  ]
}

Cada página debe tener un identificador estable.

Los identificadores no se reutilizan.

---

12. REGLA DE PÁGINAS AUTORIZADAS

La IA solo puede generar páginas incluidas en:

"authorized_pages"

No puede:

- crear páginas adicionales;
- crear URLs por iniciativa propia;
- crear páginas únicamente porque exista una keyword;
- crear páginas únicamente para aumentar el número de URLs;
- crear páginas que no estén justificadas por la arquitectura.

Si una página no está autorizada:

NO SE GENERA.

La arquitectura puede contener inicialmente un conjunto amplio de posibilidades.

El proceso de decisión podrá descartar posteriormente las páginas que no superen los criterios establecidos.

---

13. ESTRUCTURA DE UNA PÁGINA

Cada elemento de "pages" puede contener:

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

La página es una unidad independiente dentro del "SITE_PACKAGE".

---

14. SEO DE CADA PÁGINA

Cada página puede contener:

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": ""
  }
}

El contenido debe corresponder con la intención concreta de esa página.

No se debe generar contenido prácticamente idéntico entre páginas.

---

15. MENU

La salida debe permitir construir la navegación de la miniweb.

Ejemplo:

{
  "menu": {
    "items": [
      {
        "label": "Inicio",
        "url": "/fontanero/estepona/",
        "type": "internal"
      },
      {
        "label": "Desatascos",
        "url": "/fontanero/estepona/desatascos/",
        "type": "internal"
      }
    ]
  }
}

Todas las URLs deben estar previamente autorizadas.

La IA no puede inventar páginas para completar el menú.

---

16. BLOQUES

Los bloques deben pertenecer a una página concreta.

Ejemplo:

{
  "page_id": "FON-EST-P01",
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

17. MAPA OFICIAL DE BLOQUES

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

El "type" debe corresponder exactamente al ID.

---

18. BLOQUES POR PÁGINA

Cada página debe indicar qué bloques está autorizada a utilizar.

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

No existe un número fijo de bloques por página.

---

19. REGLA DE BLOQUES

La arquitectura puede autorizar inicialmente un conjunto amplio de bloques.

La IA puede utilizar los bloques autorizados que tengan sentido para la intención y los datos disponibles.

No debe rellenar bloques simplemente para aumentar la longitud.

Un bloque autorizado pero innecesario puede permanecer:

{
  "enabled": false
}

o ser omitido cuando el contrato lo permita.

---

20. BLOQUES OBLIGATORIOS

Cuando la arquitectura determine una página funcional, como mínimo debe poder representar:

- identidad;
- navegación;
- contenido principal;
- CTA cuando exista canal válido;
- footer.

No se debe inventar información para completar un bloque.

---

21. BLOQUES CONDICIONALES

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

22. CONTENIDO

El contenido debe ser:

- específico;
- útil;
- coherente con la intención;
- basado en los datos recibidos;
- compatible con las restricciones;
- diferente cuando la intención o los datos sean diferentes.

No debe generarse contenido únicamente para aumentar:

- palabras;
- keywords;
- headings;
- enlaces;
- longitud.

---

23. DIFERENCIACIÓN ENTRE PÁGINAS

Las páginas de una misma miniweb pueden compartir:

- header;
- navegación;
- footer;
- estilo;
- determinados bloques.

Pero cada página debe responder a su propia intención.

No deben convertirse todas las páginas en una misma landing cambiando solamente:

- localidad;
- H1;
- título;
- sinónimos;
- algunas frases.

---

24. NO INVENCIÓN

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

"null"

o:

"REVIEW"

si es imprescindible.

---

25. CTA

La IA puede generar el texto del CTA.

No puede inventar el canal.

Ejemplo:

{
  "label": "Solicitar presupuesto",
  "action": "contact"
}

Los datos reales de contacto deben proceder del modelo de datos.

Durante el piloto pueden utilizarse valores de prueba claramente identificados como datos ficticios.

Nunca deben presentarse datos ficticios como datos reales.

---

26. FAQ

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

27. INFORMACIÓN LOCAL

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

Repetir el nombre de una localidad no constituye información local.

---

28. COBERTURA

Cuando exista B10:

{
  "areas": []
}

Solo deben incluirse zonas respaldadas.

No se generan listas masivas artificiales.

---

29. CONFIANZA

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

30. DIFERENCIACIÓN

B13 solo puede utilizar información real que justifique la diferenciación.

No es suficiente:

- cambiar localidad;
- cambiar sinónimos;
- reordenar párrafos;
- cambiar títulos;
- generar texto diferente sin datos diferentes.

---

31. SERVICIOS RELACIONADOS

B15 solo puede enlazar servicios existentes y autorizados.

No se crean URLs nuevas desde la IA.

---

32. LOCALIDADES RELACIONADAS

B16 solo puede utilizar localidades existentes y autorizadas en la arquitectura o en el sistema de interlinking.

No se genera una red masiva de enlaces únicamente para SEO.

---

33. INTERLINKING

El contrato incorpora un sistema explícito de interlinking.

El interlinking debe distinguir entre:

1. enlaces dentro de la misma miniweb;
2. enlaces entre páginas de una misma localidad;
3. enlaces entre localidades del mismo servicio;
4. enlaces entre servicios diferentes;
5. enlaces entre páginas relacionadas por intención.

La IA puede materializar estos enlaces en el contenido únicamente cuando estén previamente autorizados.

La IA no puede decidir libremente la red de enlaces.

---

34. AUTORIDAD DEL SISTEMA DE INTERLINKING

Las relaciones válidas proceden de:

"proyecto/seo/interlinking.md"

y de las relaciones autorizadas en el modelo de datos.

La IA recibe dichas relaciones como entrada.

Ejemplo:

{
  "authorized_internal_links": [
    {
      "source_url": "/fontanero/estepona/",
      "target_url": "/fontanero/san-pedro/",
      "relation_type": "same_service_related_location"
    }
  ]
}

La IA no puede crear una relación que no aparezca en las relaciones autorizadas.

---

35. INTERLINKING ENTRE LOCALIDADES

Puede existir enlazado entre páginas del mismo servicio en diferentes localidades.

Ejemplo:

/fontanero/estepona/
/fontanero/san-pedro/
/fontanero/casares/

Una página puede enlazar a otra cuando el sistema haya autorizado la relación.

No deben enlazarse todas las localidades con todas las demás automáticamente.

El sistema debe controlar:

- relevancia;
- proximidad;
- relación territorial;
- prioridad;
- número de enlaces;
- riesgo de sobreoptimización.

---

36. INTERLINKING ENTRE SERVICIOS

Puede existir enlazado entre diferentes pilares de servicios.

Ejemplo:

/fontanero/estepona/
/carpintero/estepona/
/pintor/estepona/

Un enlace entre ellos puede existir si la relación está autorizada.

La IA no debe crear enlaces arbitrarios simplemente porque los servicios pertenezcan a la misma web.

Debe existir una relación lógica.

---

37. INTERLINKING ENTRE SUBSERVICIOS

Los subservicios relacionados pueden enlazarse cuando estén autorizados.

Ejemplo:

/fontanero/estepona/
/fontanero/estepona/desatascos/
/fontanero/estepona/fugas-de-agua/

Los enlaces deben respetar la arquitectura jerárquica.

---

38. ESTRUCTURA DE INTERNAL_LINKS

Formato:

{
  "internal_links": [
    {
      "url": "/fontanero/san-pedro/",
      "anchor": "Fontanero en San Pedro",
      "target": "FON-SP-P01",
      "reason": "same_service_related_location",
      "relation_type": "same_service_related_location"
    }
  ]
}

Campos:

- "url";
- "anchor";
- "target";
- "reason";
- "relation_type".

El "target" debe corresponder a una página autorizada.

---

39. OBJETO INTERLINKING

La salida puede contener:

{
  "interlinking": {
    "enabled": true,
    "links_generated": [],
    "links_skipped": [],
    "relations_used": []
  }
}

Esto permite saber:

- qué enlaces fueron generados;
- qué enlaces fueron descartados;
- qué relaciones fueron utilizadas.

---

40. ENLACES OMITIDOS

Cuando exista una relación autorizada pero no tenga sentido colocarla en una página concreta, puede registrarse:

{
  "source_url": "/fontanero/estepona/",
  "target_url": "/fontanero/casares/",
  "reason": "no_contextual_placement",
  "status": "SKIPPED"
}

No es obligatorio utilizar todas las relaciones autorizadas.

La autorización significa que el enlace puede existir.

No significa que deba aparecer siempre.

---

41. REGLA DE CALIDAD DEL INTERLINKING

El objetivo no es maximizar el número de enlaces.

El objetivo es crear una red útil para:

- usuarios;
- navegación;
- descubrimiento de páginas;
- arquitectura temática;
- contexto territorial;
- relación entre servicios.

No se generan enlaces artificiales para aumentar el número de enlaces internos.

---

42. DATOS ESTRUCTURADOS

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

43. IMÁGENES

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

44. VALIDATION

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

45. ISSUES

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

46. TRACEABILITY

La salida debe permitir rastrear el origen.

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "interlinking_version": "",
    "contract_version": "4.0"
  }
}

Esto permite saber qué documentación y qué oportunidad originaron la salida.

---

47. REGLAS DE INTEGRIDAD

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
- exista un enlace interno no autorizado;
- exista una relación de interlinking inexistente;
- un enlace apunte a una página no autorizada.

Resultado:

"ERROR"

o:

"REVIEW"

según la naturaleza del problema.

---

48. IDEMPOTENCIA

El contrato debe permitir que N8N procese varias veces la misma salida sin crear duplicados.

El identificador principal es:

"opportunity_id"

Cada página debe tener además:

"page_id"

N8N utilizará estos identificadores para localizar páginas existentes.

Si una página ya existe:

actualizar

Si no existe:

crear

Nunca crear duplicados simplemente porque el flujo se ejecute nuevamente.

Lo mismo debe aplicarse a las relaciones de interlinking.

---

49. ACTUALIZACIÓN

El contrato sirve tanto para:

- creación;
- actualización;
- mantenimiento.

Si una página cambia:

N8N debe actualizar únicamente la página afectada cuando sea posible.

Si cambia una relación de interlinking:

N8N debe actualizar únicamente las páginas afectadas.

Si cambia la arquitectura:

la modificación debe pasar primero por el sistema documental correspondiente.

La IA no puede alterar la arquitectura durante una actualización.

---

50. WORDPRESS

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

51. N8N

N8N será responsable de:

- recibir el JSON;
- validar la versión;
- validar las páginas;
- validar los bloques;
- validar los enlaces;
- comprobar identificadores;
- comprobar relaciones;
- comprobar existencia;
- crear páginas;
- actualizar páginas;
- construir relaciones;
- construir navegación;
- sincronizar interlinking;
- enviar datos a WordPress;
- registrar errores;
- registrar resultados.

N8N no debe reinterpretar arbitrariamente las decisiones SEO ni las relaciones autorizadas.

---

52. CREACIÓN DE MINIWEB

Cuando la arquitectura autorice varias páginas, la salida debe representar todas ellas dentro del mismo "SITE_PACKAGE".

Ejemplo:

SITE_PACKAGE
│
├── PAGE 01
│   └── /fontanero/estepona/
│
├── PAGE 02
│   └── /fon
