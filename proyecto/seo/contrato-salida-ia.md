CONTRATO DE SALIDA IA → N8N

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el contrato estructural que debe cumplir toda salida de IA destinada a N8N para generar y mantener páginas y miniwebs SEO locales.

---

1. FUNCIÓN

Este documento define exactamente qué debe devolver la IA después de recibir:

- una oportunidad previamente validada;
- una decisión SEO autorizada;
- una arquitectura autorizada;
- un modelo de datos válido;
- bloques autorizados;
- relaciones de interlinking autorizadas.

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
- capaz de representar relaciones entre páginas;
- capaz de representar interlinking entre localidades;
- capaz de representar interlinking entre servicios;
- capaz de representar interlinking entre pilares.

La IA genera contenido y propone relaciones autorizadas.

La IA no decide libremente qué páginas existen.

---

2. PRINCIPIO FUNDAMENTAL

La arquitectura tiene autoridad sobre las páginas.

El sistema de bloques tiene autoridad sobre los bloques.

El modelo de datos tiene autoridad sobre las entidades y relaciones.

La IA tiene autoridad únicamente sobre la generación del contenido y sobre la propuesta de relaciones dentro de los límites recibidos.

N8N tiene autoridad sobre el procesamiento.

WordPress tiene autoridad sobre el renderizado.

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
MODELO DE DATOS
↓
RELACIONES AUTORIZADAS
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

4. FORMATO DE SALIDA

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
- relaciones no autorizadas.

---

5. ESTRUCTURA PRINCIPAL

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
  "territorial_relations": [],
  "service_relations": [],
  "pillar_relations": [],
  "schema": {},
  "validation": {},
  "issues": {},
  "traceability": {}
}

---

6. SCHEMA VERSION

Versión actual:

"4.0"

N8N debe comprobar la versión antes de procesar la respuesta.

Si la versión no es compatible:

"ERROR"

No se debe intentar interpretar una estructura desconocida.

---

7. STATUS

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

8. OPPORTUNITY_ID

Debe conservar exactamente el identificador recibido.

Ejemplo:

"opportunity_id": "FON-EST-001"

La IA no puede modificarlo.

---

9. SITE

El objeto "site" representa la miniweb completa.

Ejemplo:

{
  "site": {
    "site_id": "SITE-FON-EST-001",
    "type": "local_service_site",
    "name": "Fontaneros en Estepona",
    "root_url": "/fontaneros/estepona/",
    "page_count": 8
  }
}

El número de páginas debe coincidir con las páginas autorizadas y generadas.

La IA no puede inventar una arquitectura nueva.

---

10. IDENTITY

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

Los campos protegidos deben coincidir exactamente con la entrada.

La IA no puede cambiar:

- sector;
- servicio;
- subservicio;
- municipio;
- provincia;
- país.

---

11. ARCHITECTURE

Representa la arquitectura previamente determinada.

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "/fontaneros/estepona/",
    "authorized_pages": [],
    "authorized_blocks": [],
    "authorized_relations": []
  }
}

La IA no decide libremente la arquitectura.

---

12. AUTHORIZED_PAGES

La IA solo puede generar páginas incluidas en:

"authorized_pages"

No puede:

- crear páginas adicionales;
- crear URLs arbitrarias;
- crear páginas por iniciativa propia;
- crear páginas únicamente porque exista una keyword;
- ampliar el número de páginas durante la generación.

---

13. PÁGINAS

Cada elemento de "pages" debe contener:

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

Cada página debe tener un "page_id" estable.

---

14. PAGE_ID

El "page_id" debe proceder de la arquitectura.

Ejemplo:

FON-EST-P01
FON-EST-P02
FON-EST-P03

La IA no debe reutilizar identificadores.

---

15. URL

La URL debe coincidir exactamente con la arquitectura autorizada.

La IA no puede modificar:

- slug;
- estructura;
- profundidad;
- dominio lógico;
- parent_url.

---

16. CANONICAL

El canonical debe coincidir exactamente con el canonical autorizado.

Ejemplo:

"canonical": "/fontaneros/estepona/desatascos/"

---

17. PARENT_URL

La relación jerárquica debe conservar la arquitectura.

Ejemplo:

{
  "url": "/fontaneros/estepona/desatascos/",
  "parent_url": "/fontaneros/estepona/",
  "depth": 2
}

---

18. SEO DE CADA PÁGINA

Cada página puede contener:

{
  "seo": {
    "primary_keyword": "",
    "secondary_keywords": [],
    "title": "",
    "meta_description": "",
    "h1": ""
  }
}

El contenido debe corresponder con la intención concreta de la página.

---

19. DIFERENCIACIÓN

Cada página debe responder a su propia intención.

No se permite crear páginas prácticamente idénticas cambiando únicamente:

- municipio;
- keyword;
- H1;
- título;
- algunas frases.

La diferenciación debe basarse en los datos disponibles y en la intención autorizada.

---

20. MENU

La navegación debe utilizar únicamente páginas autorizadas.

{
  "menu": {
    "items": [
      {
        "label": "Inicio",
        "url": "/fontaneros/estepona/",
        "type": "internal"
      }
    ]
  }
}

No se pueden añadir URLs que no existan en "pages".

---

21. BLOQUES

Los bloques deben corresponder al sistema oficial.

Formato:

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

---

22. BLOQUES AUTORIZADOS

La IA solo puede utilizar bloques incluidos en:

"authorized_blocks"

No puede inventar nuevos IDs.

---

23. MAPA OFICIAL DE BLOQUES

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

---

24. BLOQUES OBLIGATORIOS

Cuando la arquitectura determine una página funcional, como mínimo debe poder representar:

- identidad;
- navegación;
- contenido principal;
- CTA cuando exista canal válido;
- footer.

No se debe inventar información para completar un bloque.

---

25. BLOQUES CONDICIONALES

Los bloques pueden omitirse cuando no exista información suficiente.

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

---

26. CONTENIDO

El contenido debe ser:

- específico;
- útil;
- coherente con la intención;
- basado en datos;
- compatible con restricciones;
- diferenciado;
- verificable.

No debe generarse contenido únicamente para aumentar:

- palabras;
- keywords;
- headings;
- enlaces;
- longitud.

---

27. NO INVENCIÓN

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
- estadísticas;
- imágenes;
- URLs;
- datos comerciales.

Cuando un dato no existe:

"null"

Si el dato es imprescindible:

"REVIEW"

---

28. CTA

La IA puede generar el texto del CTA.

No puede inventar el canal.

Ejemplo:

{
  "label": "Solicitar presupuesto",
  "action": "contact"
}

Los datos reales de contacto deben proceder del modelo de datos.

---

29. FAQ

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

No se generan únicamente para introducir keywords.

---

30. INFORMACIÓN LOCAL

Cuando exista B09, la información debe estar respaldada.

No se inventan:

- barrios;
- calles;
- urbanizaciones;
- necesidades;
- características;
- cobertura;
- tiempos;
- particularidades.

Repetir el nombre de una localidad no constituye información local.

---

31. COBERTURA

Cuando exista B10:

{
  "areas": []
}

Solo deben incluirse zonas respaldadas.

No se generan listas masivas artificiales.

---

32. CONFIANZA

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

33. IMÁGENES

Formato:

{
  "images": [
    {
      "image_id": "",
      "url": "",
      "alt": "",
      "title": "",
      "type": ""
    }
  ]
}

La IA no puede inventar URLs de imágenes.

---

34. INTERLINKING

El contrato 4.0 incorpora explícitamente el interlinking.

La IA puede devolver relaciones únicamente dentro de las relaciones autorizadas.

La IA no puede inventar destinos.

---

35. INTERNAL_LINKS

Formato:

{
  "internal_links": [
    {
      "link_id": "",
      "source_page_id": "",
      "target_page_id": "",
      "relation": "",
      "anchor": "",
      "reason": "",
      "location": "",
      "priority": "MEDIUM",
      "status": "PROPOSED"
    }
  ]
}

---

36. LINK_ID

Cada enlace debe tener un identificador estable.

Ejemplo:

LINK-FON-EST-001

No debe reutilizarse.

---

37. SOURCE_PAGE_ID

Debe corresponder a una página existente.

La página fuente debe existir en "pages[]".

---

38. TARGET_PAGE_ID

Debe corresponder a una página existente y autorizada.

La IA no puede crear un enlace hacia una página que no esté autorizada.

---

39. RELATION

Valores oficiales:

- "parent_to_child"
- "child_to_parent"
- "related_location"
- "related_service"
- "related_subservice"
- "territorial"
- "contextual"
- "navigation"

No se permiten valores arbitrarios.

---

40. ANCHOR

Debe ser natural, descriptivo y útil para el usuario.

No debe utilizarse siempre la keyword exacta.

Ejemplo:

"fontaneros en Casares"

---

41. REASON

Debe explicar la utilidad de la relación.

Ejemplo:

"Casares es una localidad cercana y forma parte de las relaciones territoriales autorizadas."

---

42. LOCATION

Valores:

- "header"
- "navigation"
- "content"
- "related_services"
- "related_locations"
- "footer"
- "breadcrumb"
- "cta"

---

43. PRIORITY

Valores:

- "HIGH"
- "MEDIUM"
- "LOW"

La prioridad permite controlar la densidad de enlaces.

No es obligatorio enlazar todas las páginas entre sí.

---

44. LINK STATUS

Valores:

- "AUTHORIZED"
- "PROPOSED"
- "VALIDATED"
- "ACTIVE"
- "DISABLED"
- "ERROR"

La IA normalmente utilizará:

"PROPOSED"

El validador podrá convertirlo en:

"VALIDATED"

N8N podrá convertirlo en:

"ACTIVE"

---

45. RELACIONES TERRITORIALES

La salida puede contener:

{
  "territorial_relations": [
    {
      "relation_id": "",
      "source_page_id": "",
      "target_page_id": "",
      "relation": "nearby",
      "authorized": true
    }
  ]
}

Solo pueden utilizarse relaciones autorizadas.

---

46. RELACIONES ENTRE SERVICIOS

La salida puede contener:

{
  "service_relations": [
    {
      "relation_id": "",
      "source_page_id": "",
      "target_page_id": "",
      "relation": "related_service",
      "authorized": true
    }
  ]
}

Ejemplo conceptual:

Fontanería Estepona
        ↓
Electricidad Estepona

Esto solo será válido si la arquitectura y el modelo de datos lo autorizan.

---

47. RELACIONES ENTRE PILARES

La salida puede contener:

{
  "pillar_relations": [
    {
      "relation_id": "",
      "source_page_id": "",
      "target_page_id": "",
      "relation": "related_service",
      "authorized": true
    }
  ]
}

Ejemplo:

FONTANERÍA
    ↕
ELECTRICIDAD
    ↕
CARPINTERÍA
    ↕
PINTURA

No significa que todas las páginas deban enlazarse con todas las demás.

La relación debe aportar utilidad real y estar autorizada.

---

48. REGLA DE INTERLINKING

El objetivo no es crear el mayor número posible de enlaces.

El objetivo es construir una red:

- útil;
- coherente;
- temática;
- territorialmente lógica;
- navegable;
- no artificial.

---

49. NO SPAM

Está prohibido crear:

- cientos de enlaces desde una página;
- listas artificiales de localidades;
- enlaces repetidos;
- enlaces sin relación temática;
- enlaces únicamente para manipular rankings;
- enlaces entre pilares sin justificación.

---

50. RELACIONES BIDIRECCIONALES

No se exige que una relación sea bidireccional.

Puede existir:

Estepona → Casares

sin que obligatoriamente exista:

Casares → Estepona

La arquitectura y el contexto determinarán la dirección adecuada.

---

51. INTERLINKING ENTRE LOCALIDADES

Cuando existan páginas autorizadas de localidades relacionadas, la IA puede proponer enlaces.

Ejemplo:

Fontaneros Estepona
        ↓
Fontaneros Casares
        ↓
Fontaneros Manilva

Solo cuando estas páginas existan y la relación esté autorizada.

---

52. INTERLINKING ENTRE SERVICIOS

Cuando existan páginas relacionadas:

Fontaneros Estepona
        ↓
Desatascos Estepona
        ↓
Fontaneros 24 horas Estepona

La relación debe corresponder a la intención y a la arquitectura.

---

53. INTERLINKING ENTRE PILARES

Cuando el sistema disponga de varios pilares:

Fontaneros Estepona
        ↓
Electricistas Estepona

o:

Fontaneros Estepona
        ↓
Carpinteros Estepona

solo se utilizará cuando exista una relación autorizada.

---

54. PÁGINAS HUÉRFANAS

Si una página autorizada no dispone de ninguna relación lógica:

la IA debe registrar:

"REVIEW"

cuando la ausencia de relaciones pueda perjudicar la arquitectura.

No debe inventar enlaces únicamente para evitar una página huérfana.

---

55. ACTUALIZACIÓN

El mismo contrato sirve para:

- creación;
- actualización;
- regeneración;
- modificación de contenido;
- modificación de enlaces.

N8N debe utilizar:

"opportunity_id"

"site_id"

"page_id"

"link_id"

para localizar entidades existentes.

---

56. IDEMPOTENCIA

Si N8N recibe dos veces la misma salida:

no debe crear duplicados.

Debe actualizar las entidades existentes.

La misma salida procesada varias veces debe producir el mismo estado final.

---

57. VALIDATION

La IA puede devolver:

{
  "validation": {
    "valid": true,
    "checks": []
  }
}

Pero la validación definitiva corresponde al validador externo.

---

58. ISSUES

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

59. TRACEABILITY

Formato:

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "data_schema_version": "2.0",
    "contract_version": "4.0"
  }
}

Esto permite saber qué documentación originó la salida.

---

60. CAMPOS PROTEGIDOS

La IA no puede modificar:

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
- "page_id";
- "url";
- "canonical";
- "parent_url";
- "depth";
- "authorized_pages";
- "authorized_blocks";
- "authorized_relations";
- "restrictions".

Si existe contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar incidencia;
4. establecer "REVIEW" cuando corresponda.

---

61. REGLAS DE INTEGRIDAD

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
- exista modificación de campos protegidos;
- exista una relación no autorizada;
- exista un destino inexistente;
- exista un "link_id" duplicado;
- exista una relación equivalente duplicada;
- existan estructuras incompatibles;
- exista información obligatoria ausente.

---

62. PÁGINAS SIN CONTENIDO SUFICIENTE

Si una página autorizada no dispone de información suficiente:

la IA debe devolver:

"REVIEW"

No debe rellenarla con información inventada.

La página no debe publicarse hasta resolver la incidencia.

---

63. REGLA DE NO CREACIÓN

La IA no puede convertir una oportunidad o keyword en una página.

La página debe existir previamente en:

"authorized_pages"

---

64. MINIWEB COMPLETA

Cuando la arquitectura autorice varias páginas:

la salida debe representar todas las páginas dentro del mismo:

"SITE_PACKAGE"

Ejemplo conceptual:

SITE_PACKAGE
│
├── PAGE 01
│   └── /fontaneros/estepona/
│
├── PAGE 02
│   └── /fontaneros/estepona/desatascos/
│
├── PAGE 03
│   └── /fontaneros/estepona/urgencias/
│
├── PAGE 04
│   └── /fontaneros/estepona/servicios/
│
├── PAGE 05
│   └── /fontaneros/estepona/24-horas/
│
└── ...

El número no está limitado por defecto.

La arquitectura determina qué páginas existen.

---

65. PRINCIPIO DE AMPLITUD

El sistema debe partir de la arquitectura autorizada completa.

No debe existir un límite artificial de cinco páginas.

Si existen diez páginas autorizadas y justificadas:

la IA debe poder generar las diez.

Si existen veinte:

debe poder generar las veinte.

Si solo existen cuatro:

debe generar cuatro.

El número de páginas no debe estar fijado en el contrato.

---

66. PRINCIPIO DE BLOQUES

El mismo principio se aplica a los bloques.

No existe un número fijo de bloques por página.

Cada página debe utilizar todos los bloques autorizados que sean pertinentes y para los que exista información suficiente.

Los bloques innecesarios o sin información suficiente pueden omitirse.

---

67. PRINCIPIO DE CALIDAD

La IA no debe rellenar todos los bloques obligatoriamente con texto artificial.

Debe utilizar los bloques cuando aporten valor.

La amplitud estructural no significa generación indiscriminada.

---

68. WORDPRESS

La IA no genera HTML final.

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

WordPress representa visualmente:

- páginas;
- menú;
- bloques;
- enlaces;
- imágenes;
- datos estructurados.

---

69. N8N

N8N será responsable de:

- recibir el JSON;
- validar la versión;
- validar páginas;
- validar bloques;
- validar relaciones;
- comprobar identificadores;
- comprobar existencia;
- crear páginas;
- actualizar páginas;
- crear enlaces;
- actualizar enlaces;
- desactivar enlaces;
- construir navegación;
- sincronizar WordPress;
- registrar errores;
- registrar resultados.

N8N no debe reinterpretar arbitrariamente las decisiones SEO.

---

70. PUBLICACIÓN

La publicación requiere:

DECISIÓN
↓
ARQUITECTURA
↓
DATOS
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

La IA nunca publica directamente.

---

71. ACTUALIZACIÓN DE INTERLINKING

Cuando una nueva página sea publicada:

N8N debe comprobar automáticamen
