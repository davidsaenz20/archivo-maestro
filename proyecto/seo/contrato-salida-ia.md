CONTRATO DE SALIDA IA → N8N

Versión: 3.0
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

2. CAMBIO FUNDAMENTAL DE LA VERSIÓN 3.0

La versión anterior estaba orientada principalmente a una landing individual.

La versión 3.0 permite representar un:

SITE_PACKAGE

Es decir, un conjunto coherente de páginas pertenecientes a una misma miniweb local.

Ejemplo:

FONTANERO MARBELLA

/
├── fontanero/
├── fontanero/marbella/
├── fontanero/marbella/desatascos/
├── fontanero/marbella/24-horas/
└── fontanero/marbella/contacto/

La estructura exacta dependerá siempre de la arquitectura autorizada.

La IA no puede crear automáticamente páginas adicionales porque considere que serían útiles para SEO.

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
ARQUITECTURA DE LANDING / MINIWEB
↓
MODELO DE DATOS
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

4. REGLA DE AUTORIDAD

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
- "restrictions"

Si existe una contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar la incidencia;
4. establecer "REVIEW" cuando corresponda.

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
- páginas no autorizadas.

La respuesta debe poder ser procesada automáticamente por N8N.

---

6. ESTRUCTURA PRINCIPAL

La estructura oficial de la versión 3.0 es:

{
  "schema_version": "3.0",
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

7. SCHEMA VERSION

Versión actual:

"3.0"

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

La salida cumple el contrato y puede continuar.

REVIEW

Existe una incidencia que requiere revisión humana.

ERROR

La salida no puede procesarse correctamente.

---

9. SITE

El objeto "site" representa la miniweb completa.

Ejemplo:

{
  "site": {
    "type": "local_service_site",
    "name": "Fontanero en Marbella",
    "root_url": "/fontanero/marbella/",
    "page_count": 5
  }
}

El nombre y la estructura deben proceder de los datos y la arquitectura autorizada.

La IA no puede crear una miniweb arbitraria.

---

10. IDENTITY

Representa la identidad común de todo el sitio.

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

Los valores deben coincidir con la entrada.

La IA no puede cambiar:

- localidad;
- municipio;
- provincia;
- servicio;
- sector.

---

11. ARCHITECTURE

Representa la arquitectura previamente determinada.

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "/fontanero/marbella/",
    "authorized_pages": [],
    "authorized_blocks": []
  }
}

La IA no decide la arquitectura.

La arquitectura debe existir antes de la generación.

---

12. PÁGINAS

El objeto "pages" representa todas las páginas autorizadas que forman parte de la miniweb.

Ejemplo:

{
  "pages": [
    {
      "page_id": "FON-MARB-P01",
      "page_type": "service_locality",
      "url": "/fontanero/marbella/",
      "canonical": "/fontanero/marbella/",
      "parent_url": null,
      "depth": 1
    },
    {
      "page_id": "FON-MARB-P02",
      "page_type": "subservice_locality",
      "url": "/fontanero/marbella/desatascos/",
      "canonical": "/fontanero/marbella/desatascos/",
      "parent_url": "/fontanero/marbella/",
      "depth": 2
    }
  ]
}

Cada página debe tener un identificador estable.

Los identificadores no se reutilizan.

---

13. REGLA DE PÁGINAS AUTORIZADAS

La IA solo puede generar las páginas incluidas en:

"authorized_pages"

No puede:

- crear páginas adicionales;
- crear URLs por iniciativa propia;
- crear páginas únicamente porque exista una keyword;
- crear páginas únicamente para aumentar el número de URLs;
- crear páginas que no estén justificadas por la arquitectura.

Si una página no está autorizada:

NO SE GENERA.

---

14. ESTRUCTURA DE UNA PÁGINA

Cada elemento de "pages" debe poder contener:

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

15. SEO DE CADA PÁGINA

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

16. MENU

La salida debe permitir construir la navegación de la miniweb.

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

Todas las URLs deben estar previamente autorizadas.

La IA no puede inventar páginas para completar el menú.

---

17. BLOQUES

Los bloques deben pertenecer a una página concreta.

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

18. MAPA OFICIAL DE BLOQUES

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

19. BLOQUES POR PÁGINA

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

Ejemplo:

"/fontanero/marbella/"

responde a la intención general de fontanería.

"/fontanero/marbella/desatascos/"

responde a la intención específica de desatascos.

"/fontanero/marbella/24-horas/"

responde a la intención específica relacionada con disponibilidad urgente o servicio 24 horas, únicamente si está respaldado.

"/fontanero/marbella/contacto/"

responde a la intención de contacto.

No deben convertirse todas las páginas en una misma landing cambiando el título.

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

Repetir el nombre de Marbella no constituye información local.

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
- modificar algunas frases;
- generar texto diferente sin datos diferentes.

---

31. SERVICIOS RELACIONADOS

B15 solo puede enlazar servicios existentes y autorizados.

No se crean URLs nuevas desde la IA.

---

32. LOCALIDADES RELACIONADAS

B16 solo puede utilizar localidades existentes en la arquitectura.

No se genera una red masiva de enlaces únicamente para SEO.

---

33. DATOS ESTRUCTURADOS

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

34. IMÁGENES

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

35. ENLACES INTERNOS

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

---

36. VALIDATION

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

37. ISSUES

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

38. TRACEABILITY

La salida debe permitir rastrear el origen.

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "contract_version": "3.0"
  }
}

Esto permite saber qué documentación y qué oportunidad originaron la salida.

---

39. REGLAS DE INTEGRIDAD

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

"ERROR"

o:

"REVIEW"

según la naturaleza del problema.

---

40. IDEMPOTENCIA

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

---

41. WORDPRESS

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

42. N8N

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

43. CREACIÓN DE MINIWEB

Cuando la arquitectura autorice varias páginas, la salida debe representar todas ellas dentro del mismo "SITE_PACKAGE".

Ejemplo conceptual:

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

N8N debe poder recorrer:

"pages[]"

y procesar cada página de forma independiente.

---

44. RELACIÓN ENTRE PÁGINAS

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

45. PÁGINAS SIN CONTENIDO SUFICIENTE

Si una página autorizada no dispone de información suficiente para generar contenido fiable:

La IA debe devolver:

"REVIEW"

No debe rellenar la página con contenido inventado.

La página no debe publicarse hasta resolver la incidencia.

---

46. REGLA DE NO CREACIÓN AUTOMÁTICA

La IA no puede convertir automáticamente una idea en una página.

Ejemplo:

Si detecta:

"fontanero + Marbella + reparación de caldera"

no puede crear:

"/fontanero/marbella/reparacion-caldera/"

salvo que esa página esté previamente autorizada por la arquitectura.

---

47. ACTUALIZACIÓN DE UNA MINIWEB

El mismo contrato sirve para crear y actualizar.

Si una página cambia:

N8N debe actualizar únicamente la página afectada cuando sea posible.

Si cambia la arquitectura:

la modificación debe pasar primero por el sistema documental correspondiente.

La IA no puede alterar la arquitectura durante una actualización.

---

48. EJEMPLO DE SITE_PACKAGE

Ejemplo conceptual:

{
  "schema_version": "3.0",
  "opportunity_id": "FON-MARB-001",
  "status": "READY",

  "site": {
    "type": "local_service_site",
    "name": "Fontanero en Marbella",
    "root_url": "/fontanero/marbella/",
    "page_count": 4
  },

  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Marbella",
    "province": "Málaga",
    "country": "España"
  },

  "pages": [
    {
      "page_id": "FON-MARB-P01",
      "page_type": "service_locality",
      "url": "/fontanero/marbella/",
      "canonical": "/fontanero/marbella/",
      "parent_url": null,
      "depth": 1,
      "seo": {},
      "authorized_blocks": [],
      "blocks": [],
      "internal_links": []
    },
    {
      "page_id": "FON-MARB-P02",
      "page_type": "subservice_locality",
      "url": "/fontanero/marbella/desatascos/",
      "canonical": "/fontanero/marbella/desatascos/",
      "parent_url": "/fontanero/marbella/",
      "depth": 2,
      "seo": {},
      "authorized_blocks": [],
      "blocks": [],
      "internal_links": []
    },
    {
      "page_id": "FON-MARB-P03",
      "page_type": "service_variant",
      "url": "/fontanero/marbella/24-horas/",
      "canonical": "/fontanero/marbella/24-horas/",
      "parent_url": "/fontanero/marbella/",
      "depth": 2,
      "seo": {},
      "authorized_blocks": [],
      "blocks": [],
      "internal_links": []
    },
    {
      "page_id": "FON-MARB-P04",
      "page_type": "contact",
      "url": "/fontanero/marbella/contacto/",
      "canonical": "/fontanero/marbella/contacto/",
      "parent_url": "/fontanero/marbella/",
      "depth": 2,
      "seo": {},
      "authorized_blocks": [],
      "blocks": [],
      "internal_links": []
    }
  ],

  "menu": {
    "items": []
  },

  "blocks": [],

  "images": [],
  "internal_links": [],
  "schema": {},
  "validation": {},
  "issues": {
    "items": []
  },

  "traceability": {
    "opportunity_id": "FON-MARB-001",
    "contract_version": "3.0"
  }
}

Este ejemplo es únicamente estructural.

No autoriza por sí mismo esas cuatro páginas.

---

49. RELACIÓN CON EL SISTEMA DE BLOQUES

El contrato utiliza exclusivamente los bloques definidos en:

"proyecto/seo/sistema-bloques.md"

El sistema de bloques define:

qué bloques existen.

Este contrato define:

cómo debe devolverlos la IA.

---

50. RELACIÓN CON ARQUITECTURA DE LANDING

"arquitectura-landing.md" determina la estructura funcional de cada página.

Este contrato transforma esa estructura en una salida que puede procesar N8N.

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

51. RELACIÓN CON MODELO DE DATOS

El contrato no crea un modelo de datos paralelo.

Los datos deben proceder del modelo canónico definido en:

"proyecto/seo/esquema-datos.md"

y de los documentos específicos que correspondan.

---

52. VALIDACIÓN REAL

El contrato no se considera
