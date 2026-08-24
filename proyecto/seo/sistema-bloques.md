SISTEMA DE BLOQUES WORDPRESS

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el sistema lógico de bloques que utilizará la plataforma para construir, actualizar y renderizar automáticamente páginas SEO locales y miniwebs.

---

1. FUNCIÓN

Este documento define los bloques lógicos disponibles para las páginas generadas por el sistema.

Los bloques representan componentes funcionales de contenido.

No definen directamente:

- diseño visual;
- colores;
- tipografías;
- CSS;
- maquetación final;
- HTML específico;
- plantilla concreta de WordPress.

El sistema separa:

CONTENIDO Y FUNCIÓN

de:

PRESENTACIÓN VISUAL

La IA genera los datos de los bloques.

N8N transporta y sincroniza esos datos.

WordPress renderiza los bloques.

---

2. PRINCIPIO FUNDAMENTAL

Una página no tiene un número fijo de bloques.

La arquitectura determina qué bloques están autorizados.

La IA puede utilizar los bloques autorizados que resulten necesarios para responder correctamente a la intención.

No existe una estructura obligatoria de cinco bloques ni de un número fijo de bloques.

El objetivo es:

«utilizar todos los bloques que aporten valor real y omitir los que no estén justificados.»

Nunca:

«añadir bloques únicamente para aumentar longitud.»

---

3. BLOQUES OFICIALES

Los bloques oficiales son:

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

No pueden crearse IDs adicionales sin modificar previamente este documento y el resto de documentación dependiente.

---

4. REGLA ID → TYPE

Cada bloque debe respetar exactamente esta correspondencia.

B01 → header
B02 → navigation
B03 → hero
B04 → main_content
B05 → cta
B06 → footer
B07 → subservice
B08 → problems
B09 → local_context
B10 → coverage
B11 → process
B12 → trust
B13 → differentiation
B14 → faq
B15 → related_services
B16 → related_locations
B17 → structured_data
B18 → testimonials
B19 → cases
B20 → gallery
B21 → pricing
B22 → opening_hours
B23 → map

Si el ID y el TYPE no coinciden:

ERROR

---

5. ESTRUCTURA GENERAL

Todo bloque debe seguir una estructura compatible con:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {}
}

Campos oficiales:

- "id"
- "type"
- "enabled"
- "data"

No deben añadirse campos arbitrarios.

---

6. ID

El ID identifica el tipo de bloque.

Ejemplo:

"id": "B03"

Los IDs son globales y estables.

No deben modificarse durante una actualización.

---

7. TYPE

Define la función del bloque.

Ejemplo:

"type": "hero"

Debe coincidir exactamente con el ID.

---

8. ENABLED

Valores:

true

o:

false

Cuando "enabled = false", el renderizador no debe mostrar el bloque.

El sistema puede conservar el bloque para futuras actualizaciones.

---

9. DATA

"data" contiene exclusivamente la información necesaria para representar el bloque.

Ejemplo:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "",
    "subtitle": "",
    "cta": null
  }
}

La estructura exacta de "data" depende del bloque.

---

10. B01 — HEADER

Función:

Representar la identidad principal de la página o sitio.

Estructura:

{
  "id": "B01",
  "type": "header",
  "enabled": true,
  "data": {
    "brand_name": "",
    "logo_url": null,
    "logo_alt": null
  }
}

No se inventa:

- nombre de empresa;
- logotipo;
- teléfono;
- dirección;
- información comercial.

Si todavía no existe empresa real:

"brand_name": null

---

11. B02 — NAVIGATION

Función:

Representar la navegación principal.

Estructura:

{
  "id": "B02",
  "type": "navigation",
  "enabled": true,
  "data": {
    "items": [
      {
        "label": "",
        "url": "",
        "type": "internal"
      }
    ]
  }
}

Las URLs deben estar autorizadas por la arquitectura.

No se crean enlaces hacia páginas inexistentes.

---

12. B03 — HERO

Función:

Presentar inmediatamente:

- servicio;
- localidad;
- propuesta principal;
- acción principal cuando exista.

Estructura:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "",
    "subtitle": "",
    "description": "",
    "cta": null,
    "image": null
  }
}

El contenido debe corresponder con la intención de la página.

---

13. B04 — MAIN_CONTENT

Función:

Contener el contenido principal de la página.

Estructura:

{
  "id": "B04",
  "type": "main_content",
  "enabled": true,
  "data": {
    "title": "",
    "sections": [
      {
        "heading": "",
        "content": ""
      }
    ]
  }
}

El bloque puede contener varias secciones cuando sean necesarias.

No debe utilizarse para introducir texto artificial.

---

14. B05 — CTA

Función:

Facilitar una acción comercial.

Estructura:

{
  "id": "B05",
  "type": "cta",
  "enabled": true,
  "data": {
    "title": "",
    "text": "",
    "label": "",
    "action": "contact",
    "target": null
  }
}

La IA puede generar el texto.

Los datos reales de contacto deben proceder del modelo de datos.

---

15. B06 — FOOTER

Función:

Representar información común de navegación y sitio.

Estructura:

{
  "id": "B06",
  "type": "footer",
  "enabled": true,
  "data": {
    "links": [],
    "copyright": null,
    "contact": null
  }
}

No se inventan datos comerciales.

---

16. B07 — SUBSERVICE

Función:

Presentar un subservicio autorizado.

Estructura:

{
  "id": "B07",
  "type": "subservice",
  "enabled": true,
  "data": {
    "title": "",
    "description": "",
    "items": []
  }
}

Los subservicios deben proceder de la arquitectura o del modelo de datos autorizado.

---

17. B08 — PROBLEMS

Función:

Explicar problemas o necesidades relacionados con la intención.

Estructura:

{
  "id": "B08",
  "type": "problems",
  "enabled": true,
  "data": {
    "title": "",
    "items": [
      {
        "problem": "",
        "description": ""
      }
    ]
  }
}

Los problemas deben ser relevantes para el servicio.

No deben inventarse situaciones específicas de una empresa.

---

18. B09 — LOCAL_CONTEXT

Función:

Aportar contexto local real.

Estructura:

{
  "id": "B09",
  "type": "local_context",
  "enabled": true,
  "data": {
    "title": "",
    "content": "",
    "areas": []
  }
}

Solo se incluye información local respaldada.

No se inventan:

- barrios;
- urbanizaciones;
- calles;
- características;
- problemas;
- tiempos;
- cobertura.

Mencionar repetidamente el nombre del municipio no constituye contexto local.

---

19. B10 — COVERAGE

Función:

Representar zonas de cobertura verificadas.

Estructura:

{
  "id": "B10",
  "type": "coverage",
  "enabled": true,
  "data": {
    "title": "",
    "areas": []
  }
}

Las zonas deben existir en los datos autorizados.

No se generan listas artificiales de localidades.

---

20. B11 — PROCESS

Función:

Explicar el proceso de contratación o prestación del servicio.

Estructura:

{
  "id": "B11",
  "type": "process",
  "enabled": true,
  "data": {
    "title": "",
    "steps": [
      {
        "number": 1,
        "title": "",
        "description": ""
      }
    ]
  }
}

El proceso debe basarse en información real cuando represente un proceso específico de empresa.

---

21. B12 — TRUST

Función:

Representar señales verificables de confianza.

Puede incluir:

- experiencia;
- certificaciones;
- garantías;
- reseñas verificadas;
- datos comerciales;
- cobertura;
- otros elementos documentados.

Estructura:

{
  "id": "B12",
  "type": "trust",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

Nunca se inventan señales de confianza.

---

22. B13 — DIFFERENTIATION

Función:

Explicar una diferenciación real.

Estructura:

{
  "id": "B13",
  "type": "differentiation",
  "enabled": true,
  "data": {
    "title": "",
    "content": "",
    "items": []
  }
}

La diferenciación debe estar respaldada por datos.

No constituye diferenciación:

- cambiar frases;
- cambiar sinónimos;
- cambiar el municipio;
- reordenar párrafos.

---

23. B14 — FAQ

Función:

Responder preguntas relevantes.

Estructura:

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

24. B15 — RELATED_SERVICES

Función:

Enlazar servicios relacionados existentes y autorizados.

Estructura:

{
  "id": "B15",
  "type": "related_services",
  "enabled": true,
  "data": {
    "title": "",
    "items": [
      {
        "label": "",
        "url": "",
        "description": null
      }
    ]
  }
}

Las URLs deben existir o estar autorizadas por arquitectura.

---

25. B16 — RELATED_LOCATIONS

Función:

Conectar páginas de localidades relacionadas dentro de la arquitectura global.

Este bloque es especialmente importante para el modelo de expansión territorial.

Estructura:

{
  "id": "B16",
  "type": "related_locations",
  "enabled": true,
  "data": {
    "title": "",
    "items": [
      {
        "label": "",
        "url": "",
        "description": null
      }
    ]
  }
}

Las localidades relacionadas deben proceder de la arquitectura autorizada.

No se crea una red indiscriminada.

---

26. B17 — STRUCTURED_DATA

Función:

Representar los datos necesarios para generar posteriormente datos estructurados.

Estructura:

{
  "id": "B17",
  "type": "structured_data",
  "enabled": true,
  "data": {
    "entities": [],
    "properties": {}
  }
}

No se inventan:

- ratings;
- reviews;
- precios;
- horarios;
- direcciones;
- empresas;
- personas.

El JSON-LD final será generado por el sistema de renderizado.

---

27. B18 — TESTIMONIALS

Función:

Representar testimonios reales disponibles.

Estructura:

{
  "id": "B18",
  "type": "testimonials",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

Si no existen testimonios reales:

"enabled": false

No se generan testimonios ficticios.

---

28. B19 — CASES

Función:

Representar casos reales documentados.

Estructura:

{
  "id": "B19",
  "type": "cases",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

No se inventan casos.

---

29. B20 — GALLERY

Función:

Representar imágenes reales disponibles.

Estructura:

{
  "id": "B20",
  "type": "gallery",
  "enabled": true,
  "data": {
    "title": "",
    "images": []
  }
}

Cada imagen debe proceder de un recurso real.

---

30. B21 — PRICING

Función:

Representar precios reales.

Estructura:

{
  "id": "B21",
  "type": "pricing",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

No se inventan precios.

Si no existen:

"enabled": false

---

31. B22 — OPENING_HOURS

Función:

Representar horarios reales.

Estructura:

{
  "id": "B22",
  "type": "opening_hours",
  "enabled": true,
  "data": {
    "title": "",
    "schedule": []
  }
}

No se inventan horarios.

---

32. B23 — MAP

Función:

Representar ubicación o mapa cuando exista información válida.

Estructura:

{
  "id": "B23",
  "type": "map",
  "enabled": true,
  "data": {
    "address": null,
    "latitude": null,
    "longitude": null,
    "embed_url": null
  }
}

No se inventa una dirección.

---

33. REGLA DE BLOQUES OBLIGATORIOS

No existe un número fijo de bloques.

Una página funcional debe poder representar como mínimo:

- identidad;
- navegación;
- contenido principal;
- CTA cuando exista una acción válida;
- footer.

En términos de bloques:

- B01;
- B02;
- B04;
- B05 cuando proceda;
- B06.

La arquitectura puede determinar excepciones justificadas.

---

34. REGLA DE BLOQUES CONDICIONALES

Los bloques siguientes son condicionales:

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
- B17;
- B18;
- B19;
- B20;
- B21;
- B22;
- B23.

Se incluyen cuando aporten valor y exista información suficiente.

---

35. REGLA "MÁXIMA COBERTURA → DESCARTE"

La arquitectura puede comenzar con un conjunto amplio de bloques potencialmente útiles.

Durante la investigación y generación se deben descartar los bloques que:

- no aporten valor;
- no estén respaldados;
- sean redundantes;
- no correspondan a la intención;
- no tengan información suficiente;
- aumenten el riesgo de contenido artificial.

Por tanto:

por defecto se evalúa la posibilidad de utilizar todos los bloques autorizados.

Después:

se descartan los innecesarios.

No se debe asumir una página mínima de cinco bloques.

---

36. ORDEN DE BLOQUES

El orden lógico recomendado es:

1. B01 — header
2. B02 — navigation
3. B03 — hero
4. B04 — main_content
5. B07 — subservice
6. B08 — problems
7. B09 — local_context
8. B10 — coverage
9. B11 — process
10. B12 — trust
11. B13 — differentiation
12. B14 — faq
13. B15 — related_services
14. B16 — related_locations
15. B18 — testimonials
16. B19 — cases
17. B20 — gallery
18. B21 — pricing
19. B22 — opening_hours
20. B23 — map
21. B05 — cta
22. B06 — footer

La arquitectura puede modificar este orden cuando exista una razón funcional.

B17 — structured_data no representa necesariamente un bloque visual.

---

37. BLOQUES NO VISUALES

B17 puede existir como componente lógico aunque no sea visible directamente.

Su función es proporcionar información para el renderizador.

Por tanto:

"enabled": true

no implica necesariamente representación visual.

---

38. BLOQUES REPETIBLES

Algunos bloques pueden contener múltiples elementos.

Ejemplos:

B07:

"items": []

B08:

"items": []

B14:

"items": []

B15:

"items": []

B16:

"items": []

B18:

"items": []

B19:

"items": []

B20:

"images": []

El número de elementos debe depender de la información disponible y de la utilidad real.

---

39. INTERLINKING

Los bloques B15 y B16 permiten representar parte del enlazado interno.

Además, cada página puede contener:

"internal_links": []

Estos enlaces deben ser posteriormente validados contra la arquitectura.

Nunca se crean enlaces hacia URLs inexistentes.

---

40. INTERLINKING ENTRE LOCALIDADES

Cuando existan varias localidades autorizadas dentro del mismo sistema, puede utilizarse B16 para conectar páginas territorialmente relacionadas.

Ejemplo:

Fontanero Estepona
      ↓
Fontanero Manilva
Fontanero Casares
Fontanero San Pedro

Pero el sistema no debe enlazar todas las localidades con todas.

Debe buscar una estructura razonable y útil.

---

41. INTERLINKING ENTRE SERVICIOS

Cuando exista arquitectura que conecte diferentes servicios, pueden utilizarse B15 o enlaces internos autorizados.

Ejemplo:

Fontanero
   ↓
Electricista
   ↓
Pintor
   ↓
Carpintero

Esto solo debe realizarse cuando exista una relación lógica para el usuario.

No se debe crear una red artificial de enlaces únicamente para manipular SEO.

---

42. INTERLINKING CONTEXTUAL

Los enlaces internos pueden aparecer dentro del contenido cuando tengan sentido.

Ejemplo:

Un contenido sobre una reforma puede enlazar hacia:

- fontanería;
- electricidad;
- pintura;
- carpintería.

El anchor debe ser natural y describir correctamente la página destino.

---

43. REGLA DE ANCHORS

Los anchors deben ser:

- descriptivos;
- naturales;
- relevantes;
- comprensibles.

No se debe repetir artificialmente exactamente la misma keyword en todos los enlaces.

---

44. REGLA DE URLs

Todas las URLs utilizadas por bloques o enlaces deben pertenecer a una de estas categorías:

1. URL de la propia página;
2. URL autorizada por la arquitectura;
3. URL existente registrada en el sistema.

Si no cumple una de ellas:

ERROR

---

45. DATOS FICTICIOS DE PILOTO

Durante las pruebas se permite utilizar datos ficticios claramente identificados como:

TEST_DATA

Estos datos nunca deben pasar a producción.

En producción:

los datos deben proceder del modelo de datos real.

---

46. DATOS PENDIENTES DE CLIENTE

El sistema debe permitir crear una página sin datos comerciales definitivos.

Ejemplo:

{
  "brand_name": null,
  "phone": null,
  "whatsapp": null,
  "email": null
}

Los CTA pueden quedar preparados para recibir posteriormente esos datos.

Esto permite construir activos SEO antes de disponer de un cliente alquilado.

---

47. ACTUALIZACIÓN

Los bloques deben poder actualizarse individualmente.

Ejemplo:

Si cambia:

B12 — trust

no es necesario regenerar:

B03 — hero

ni:

B04 — main_content.

N8N debe identificar la página y actualizar únicamente los elementos afectados cuando sea posible.

---

48. IDEMPOTENCIA

Cada página debe tener un identificador estable.

Cada bloque debe tener un ID estable.

El sistema debe poder ejecutar nuevamente una generación sin duplicar bloques.

La identificación principal será:

opportunity_id
+
page_id
+
block_id

---

49. RENDERIZADO WORDPRESS

WordPress recibe los bloques lógicos y los transforma en representación visual.

Flujo:

IA
↓
JSON
↓
VALIDADOR
↓
N8N
↓
WORDPRESS
↓
RENDERIZADOR
↓
PÁGINA

La IA no genera HTML final como contrato principal.

---

50. SEPARACIÓN ENTRE CONTENIDO Y DISEÑO

Los datos de un bloque deben poder representarse mediante diferentes diseños.

Por ejemplo:

B03 puede renderizarse como:

- hero clásico;
- hero minimalista;
- hero con imagen;
- hero con CTA;
- hero dividido.

El contenido lógico no debe depender del diseño.

---

51. VARIACIONES VISUALES

Las variaciones visuales pertenecen a WordPress.

Por tanto:

B03

define:

qué información existe

pero WordPress decide:

cómo se muestra.

Esto permite utilizar diferentes plantillas sin cambiar la lógica SEO.

---

52. REUTILIZACIÓN

Los mismos bloques pueden utilizarse en:

- páginas de servicio;
- páginas servicio + localidad;
- subservicios;
- páginas de problemas;
- páginas de contacto;
- otras páginas autorizadas.

La arquitectura decide qué combinación corresponde a cada caso.

---

53. REGLA CONTRA PÁGINAS CLÓNICAS

Dos páginas no deben convertirse en copias con únicamente:

- localidad distinta;
- H1 distinto;
- title distinto.

La arquitectura y los bloques deben permitir introducir diferencias reales cuando existan.

Si no existen diferencias suficientes:

la oportunidad debe reconsiderarse antes de crear la página.

---

54. RELACIÓN CON EL MOTOR DE DECISIÓN

El sistema de bloques no decide:

- CREAR;
- AGRUPAR;
- INVESTIGAR;
- NO CREAR.

Eso corresponde al:

"motor-decision-seo.md"

---

55. RELACIÓN CON ARQUITECTURA

La arquitectura determina:

- páginas;
- URLs;
- profundidad;
- bloques autorizados;
- relaciones.

Este documento determina:

- qué significa cada bloque;
- qué estructura tiene;
- qué datos puede contener;
- cómo debe comportarse.

---

56. RELACIÓN CON CONTRATO IA

La IA debe devolver bloques compatibles con este documento.

Si la IA devuelve:

B99

el validador debe rechazarlo.

Si devuelve:

B03 + type "faq"

el validador debe rechazarlo.

---

57. RELACIÓN CON N8N

N8N debe:

1. recibir bloques;
2. validar IDs;
3. validar tipos;
4. validar datos;
5. validar autorización;
6. localizar página;
7. crear o actualizar bloques;
8. enviar a WordPress;
9. registrar resultado.

---

58. VALIDACIÓN

El validador debe comprobar:

- ID válido;
- TYPE válido;
- correspondencia ID/TYPE;
- estructura correcta;
- datos compatibles;
- bloque autorizado;
- URLs autorizadas;
- ausencia de datos inventados;
- ausencia de estructuras arbitrarias;
- ausencia de duplicados.

---

59. ERRORES

Ejemplos:

UNKNOWN_BLOCK_ID

BLOCK_TYPE_MISMATCH

UNAUTHORIZED_BLOCK

UNAUTHORIZED_URL

INVALID_BLOCK_STRUCTURE

MISSING_REQUIRED_DATA

UNVERIFIED_DATA

DUPLICATE_BLOCK

---

60. PRINCIPIO DE NO INVENCIÓN

Los bloques no pueden utilizarse para introducir datos inexistentes.

Especialmente:

- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- reseñas;
- testimonios;
- certificaciones;
- experiencia;
- casos;
- cobertura;
- imágenes;
- mapas.

Cuando el dato no existe:

null

o:

"enabled": false

según corresponda.

---

6
