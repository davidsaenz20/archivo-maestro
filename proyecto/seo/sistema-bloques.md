Ha pensado durante 1m 15s

SISTEMA DE BLOQUES WORDPRESS

Versión: 5.0
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
- tema concreto;
- plantilla concreta de WordPress.

El sistema separa:

CONTENIDO Y FUNCIÓN

de:

PRESENTACIÓN VISUAL

La IA genera los datos de los bloques.

N8N transporta, valida y sincroniza esos datos.

WordPress los almacena y renderiza mediante plantillas.

---

2. PRINCIPIO FUNDAMENTAL

Una página no tiene un número fijo de bloques.

La arquitectura determina qué bloques están autorizados.

La IA puede utilizar los bloques autorizados que resulten necesarios para responder correctamente a la intención.

No se añaden bloques únicamente para aumentar longitud.

La regla es:

utilizar los bloques que aporten valor real y omitir los que no estén justificados.

---

3. BLOQUES OFICIALES

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

No pueden crearse IDs adicionales sin modificar previamente este documento y la documentación dependiente.

---

4. REGLA ID → TYPE

Cada bloque debe respetar exactamente esta correspondencia:

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

Si ID y TYPE no coinciden:

ERROR

---

5. ESTRUCTURA DE UNA INSTANCIA

Una instancia de bloque utilizará:

{
  "id": "B03",
  "type": "hero",
  "block_instance_id": "FON-EST-HOME-B03-01",
  "block_version": 1,
  "position": 3,
  "enabled": true,
  "data": {}
}

Campos oficiales:

- "id"
- "type"
- "block_instance_id"
- "block_version"
- "position"
- "enabled"
- "data"

No deben añadirse campos arbitrarios.

---

6. ID

El "id" identifica el tipo lógico de bloque.

Ejemplo:

"id": "B03"

Los IDs son globales y estables.

No deben modificarse durante una actualización.

---

7. TYPE

"type" define la función del bloque.

Ejemplo:

"type": "hero"

Debe coincidir exactamente con "id".

---

8. BLOCK_INSTANCE_ID

"block_instance_id" identifica una instancia concreta del bloque.

Ejemplo:

"block_instance_id": "FON-EST-HOME-B03-01"

Debe ser:

- único dentro de la página;
- estable;
- no vacío.

Dos instancias del mismo bloque pueden existir si tienen IDs diferentes.

Ejemplo:

FON-EST-HOME-B07-01
FON-EST-HOME-B07-02

---

9. BLOCK_VERSION

"block_version" identifica la versión lógica de la instancia.

Ejemplo:

"block_version": 2

Debe incrementarse cuando cambie la estructura o versión lógica del bloque.

No depende de la versión del tema.

---

10. POSITION

"position" determina el orden lógico del bloque dentro de la página.

Ejemplo:

B03 → position 3
B04 → position 4
B14 → position 14

El renderizador utilizará este orden.

---

11. ENABLED

Valores permitidos:

true
false

Cuando:

"enabled": false

el renderizador no debe mostrar la instancia.

La instancia puede conservarse para futuras actualizaciones.

---

12. DATA

"data" contiene exclusivamente la información necesaria para representar el bloque.

Ejemplo:

{
  "id": "B03",
  "type": "hero",
  "block_instance_id": "FON-EST-HOME-B03-01",
  "block_version": 1,
  "position": 3,
  "enabled": true,
  "data": {
    "title": "Fontanero en Estepona",
    "subtitle": "Servicio de fontanería en Estepona",
    "description": "",
    "cta": null,
    "image": null
  }
}

La estructura exacta de "data" depende del bloque.

---

BLOQUES

13. B01 — HEADER

Función: representar la identidad principal de la página o sitio.

{
  "id": "B01",
  "type": "header",
  "data": {
    "brand_name": null,
    "logo_url": null,
    "logo_alt": null
  }
}

No se inventan:

- empresa;
- logotipo;
- teléfono;
- dirección;
- información comercial.

---

14. B02 — NAVIGATION

Función: representar la navegación principal.

{
  "id": "B02",
  "type": "navigation",
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

Las URLs deben estar autorizadas.

No se enlazan páginas inexistentes.

---

15. B03 — HERO

Función: presentar inmediatamente servicio, localidad, propuesta principal y acción cuando proceda.

{
  "id": "B03",
  "type": "hero",
  "data": {
    "title": "",
    "subtitle": "",
    "description": "",
    "cta": null,
    "image": null
  }
}

Debe corresponder con la intención de la página.

---

16. B04 — MAIN_CONTENT

Función: contener el contenido principal.

{
  "id": "B04",
  "type": "main_content",
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

Puede contener varias secciones cuando estén justificadas.

No debe utilizarse para introducir texto artificial.

---

17. B05 — CTA

Función: facilitar una acción.

{
  "id": "B05",
  "type": "cta",
  "data": {
    "title": "",
    "text": "",
    "label": "",
    "action": "contact",
    "target": null
  }
}

El texto puede ser generado por IA.

Los datos reales de contacto proceden del modelo de datos.

---

18. B06 — FOOTER

Función: información común de navegación y sitio.

{
  "id": "B06",
  "type": "footer",
  "data": {
    "links": [],
    "copyright": null,
    "contact": null
  }
}

No se inventan datos comerciales.

---

19. B07 — SUBSERVICE

Función: presentar subservicios autorizados.

{
  "id": "B07",
  "type": "subservice",
  "data": {
    "title": "",
    "description": "",
    "items": []
  }
}

Los subservicios deben proceder de información autorizada.

---

20. B08 — PROBLEMS

Función: explicar problemas o necesidades relacionados con la intención.

{
  "id": "B08",
  "type": "problems",
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

No se inventan problemas específicos de una empresa.

---

21. B09 — LOCAL_CONTEXT

Función: aportar contexto local real.

{
  "id": "B09",
  "type": "local_context",
  "data": {
    "title": "",
    "content": "",
    "areas": []
  }
}

No se inventan:

- barrios;
- urbanizaciones;
- calles;
- características;
- problemas;
- tiempos;
- cobertura.

Repetir el nombre de la localidad no constituye contexto local.

---

22. B10 — COVERAGE

Función: representar zonas de cobertura verificadas.

{
  "id": "B10",
  "type": "coverage",
  "data": {
    "title": "",
    "areas": []
  }
}

Las zonas deben existir en los datos autorizados.

---

23. B11 — PROCESS

Función: explicar el proceso de contratación o prestación.

{
  "id": "B11",
  "type": "process",
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

Si representa un proceso específico de empresa, debe basarse en información real.

---

24. B12 — TRUST

Función: representar señales verificables de confianza.

Puede incluir:

- experiencia;
- certificaciones;
- garantías;
- reseñas verificadas;
- datos comerciales;
- cobertura;
- otros elementos documentados.

{
  "id": "B12",
  "type": "trust",
  "data": {
    "title": "",
    "items": []
  }
}

Nunca se inventan señales de confianza.

---

25. B13 — DIFFERENTIATION

Función: explicar una diferenciación real.

{
  "id": "B13",
  "type": "differentiation",
  "data": {
    "title": "",
    "content": "",
    "items": []
  }
}

Cambiar palabras, sinónimos o localidades no constituye diferenciación real.

---

26. B14 — FAQ

Función: responder preguntas relevantes.

{
  "id": "B14",
  "type": "faq",
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

No se crean únicamente para introducir keywords.

---

27. B15 — RELATED_SERVICES

Función: enlazar servicios relacionados existentes y autorizados.

{
  "id": "B15",
  "type": "related_services",
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

Las URLs deben existir o estar autorizadas.

---

28. B16 — RELATED_LOCATIONS

Función: conectar páginas de localidades relacionadas.

{
  "id": "B16",
  "type": "related_locations",
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

No se crea una red indiscriminada de localidades.

---

29. B17 — STRUCTURED_DATA

Función: proporcionar datos para la generación posterior de datos estructurados.

{
  "id": "B17",
  "type": "structured_data",
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

El JSON-LD final será generado por el renderizador.

B17 puede ser lógico/no visual.

---

30. B18 — TESTIMONIALS

Función: representar testimonios reales disponibles.

{
  "id": "B18",
  "type": "testimonials",
  "data": {
    "title": "",
    "items": []
  }
}

Si no existen testimonios reales:

enabled = false

No se generan testimonios ficticios.

---

31. B19 — CASES

Función: representar casos reales documentados.

{
  "id": "B19",
  "type": "cases",
  "data": {
    "title": "",
    "items": []
  }
}

No se inventan casos.

---

32. B20 — GALLERY

Función: representar imágenes reales disponibles.

{
  "id": "B20",
  "type": "gallery",
  "data": {
    "title": "",
    "images": []
  }
}

Cada imagen debe proceder de un recurso real.

---

33. B21 — PRICING

Función: representar precios reales.

{
  "id": "B21",
  "type": "pricing",
  "data": {
    "title": "",
    "items": []
  }
}

No se inventan precios.

Si no existen:

enabled = false

---

34. B22 — OPENING_HOURS

Función: representar horarios reales.

{
  "id": "B22",
  "type": "opening_hours",
  "data": {
    "title": "",
    "schedule": []
  }
}

No se inventan horarios.

---

35. B23 — MAP

Función: representar ubicación o mapa cuando exista información válida.

{
  "id": "B23",
  "type": "map",
  "data": {
    "address": null,
    "latitude": null,
    "longitude": null,
    "embed_url": null
  }
}

No se inventan direcciones ni coordenadas.

---

REGLAS DEL SISTEMA

36. BLOQUES OBLIGATORIOS

No existe un número fijo de bloques.

Una landing funcional debe poder representar, cuando corresponda:

- identidad;
- navegación;
- contenido principal;
- CTA si existe una acción válida;
- footer.

Esto suele corresponder a:

B01
B02
B04
B05 → cuando proceda
B06

La arquitectura puede establecer excepciones.

---

37. BLOQUES CONDICIONALES

Son condicionales:

B07
B08
B09
B10
B11
B12
B13
B14
B15
B16
B17
B18
B19
B20
B21
B22
B23

Se utilizan únicamente cuando aporten valor y exista información suficiente.

---

38. REGLA DE MÁXIMA COBERTURA

Durante la fase de decisión se evalúa la posibilidad de utilizar todos los bloques autorizados.

Después se descartan los que:

- no aporten valor;
- no estén respaldados;
- sean redundantes;
- no correspondan a la intención;
- carezcan de información suficiente;
- aumenten el riesgo de contenido artificial.

---

39. ORDEN DE BLOQUES

Orden lógico recomendado:

1.  B01 — header
2.  B02 — navigation
3.  B03 — hero
4.  B04 — main_content
5.  B07 — subservice
6.  B08 — problems
7.  B09 — local_context
8.  B10 — coverage
9.  B11 — process
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

La arquitectura puede modificar este orden por razones funcionales.

B17 no tiene por qué ocupar una posición visual.

---

40. BLOQUES REPETIBLES

Una página puede contener múltiples instancias de un mismo bloque cuando esté permitido.

Ejemplo:

FON-EST-HOME-B07-01
FON-EST-HOME-B07-02
FON-EST-HOME-B07-03

Cada instancia debe conservar su propio:

block_instance_id
block_version
position
enabled

---

41. INTERLINKING

B15 y B16 permiten representar parte del enlazado interno.

Además, la página puede tener una estructura global:

internal_links[]

Todos los enlaces deben ser validados contra la arquitectura.

Nunca se enlazan destinos inexistentes.

---

42. INTERLINKING ENTRE LOCALIDADES

Ejemplo:

Fontanero Estepona
        ↓
Fontanero Manilva
Fontanero Casares
Fontanero San Pedro

La relación debe ser útil para el usuario.

No se enlazan automáticamente todas las localidades con todas.

---

43. INTERLINKING ENTRE SERVICIOS

Ejemplo:

Fontanero
   ↓
Electricista
   ↓
Pintor
   ↓
Carpintero

Solo cuando exista una relación lógica y autorizada.

No se crea una red artificial únicamente para SEO.

---

44. INTERLINKING CONTEXTUAL

Los enlaces pueden aparecer dentro del contenido cuando tengan sentido.

El anchor debe:

- describir el destino;
- ser natural;
- ser relevante;
- ser comprensible.

---

45. REGLA DE ANCHORS

No se debe repetir artificialmente la misma keyword exacta en todos los enlaces.

El anchor debe corresponder a la página de destino.

---

46. REGLA DE URLs

Toda URL utilizada por un bloque debe pertenecer a una de estas categorías:

1. URL de la propia página;
2. URL autorizada por arquitectura;
3. URL existente registrada en el sistema.

En otro caso:

ERROR

---

47. DATOS DE PRUEBA

Durante el piloto pueden utilizarse datos ficticios claramente identificados como:

TEST_DATA

Nunca deben llegar a producción.

---

48. DATOS COMERCIALES PENDIENTES

Una página puede existir sin datos comerciales definitivos.

Ejemplo:

{
  "brand_name": null,
  "phone": null,
  "whatsapp": null,
  "email": null
}

No se deben inventar datos para completar el bloque.

---

49. ACTUALIZACIÓN PARCIAL

Los bloques deben poder actualizarse individualmente.

Ejemplo:

UPDATE_BLOCK
page_id = FON-EST-HOME
block_instance_id = FON-EST-HOME-B12-01

No es necesario regenerar toda la página si solo cambia B12.

---

50. IDEMPOTENCIA

La identidad completa de una instancia es:

page_id
+
block_instance_id

El sistema no debe crear una segunda instancia cuando recibe dos veces la misma operación.

Regla:

NO EXISTE
↓
CREATE

EXISTE
↓
UPDATE

---

51. RENDERIZADO WORDPRESS

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
PLANTILLA
↓
TEMA
↓
HTML FINAL

La IA no genera el HTML final como contrato principal.

---

52. SEPARACIÓN ENTRE CONTENIDO Y DISEÑO

B03 define qué información contiene el Hero.

La plantilla decide cómo se visualiza.

Ejemplos de posibles variantes:

- hero clásico;
- hero minimalista;
- hero con imagen;
- hero dividido;
- hero con CTA.

El contenido lógico permanece independiente.

---

53. INDEPENDENCIA DEL TEMA

Este documento no contiene referencias obligatorias a:

- Kadence;
- Astra;
- GeneratePress;
- Divi;
- Elementor;
- cualquier otro tema.

El sistema debe poder cambiar de tema sin cambiar los IDs ni los datos de los bloques.

---

54. PLANTILLAS

Cada "block_id" debe poder ser asociado posteriormente a una plantilla o componente visual.

Conceptualmente:

B03
 ↓
Renderer
 ↓
Template
 ↓
Data

La plantilla puede cambiar sin modificar el contenido lógico.

---

55. REUTILIZACIÓN

Los mismos bloques pueden utilizarse en:

- páginas de servicio;
- páginas servicio + localidad;
- subservicios;
- páginas de problemas;
- páginas de contacto;
- otras páginas autorizadas.

La arquitectura determina qué combinación corresponde a cada caso.

---

56. REGLA CONTRA PÁGINAS CLÓNICAS

Dos páginas no deben convertirse en copias cambiando únicamente:

- localidad;
- H1;
- title.

Debe existir suficiente diferenciación real.

Si no existe:

RECONSIDERAR OPORTUNIDAD

antes de generar la página.

---

57. RELACIÓN CON MOTOR DE DECISIÓN

Este documento no decide:

- crear;
- agrupar;
- investigar;
- no crear.

Eso corresponde al motor de decisión SEO.

---

58. RELACIÓN CON ARQUITECTURA

La arquitectura determina:

- páginas;
- URLs;
- profundidad;
- relaciones;
- bloques autorizados.

Este documento determina:

- qué significa cada bloque;
- qué estructura tiene;
- qué datos puede contener;
- cómo debe comportarse.

---

59. RELACIÓN CON CONTRATO IA

La IA debe devolver bloques compatibles con este documento.

Ejemplos inválidos:

B99

id = B03
type = faq

block_instance_id inexistente

El validador debe rechazarlos.

---

60. RELACIÓN CON N8N

N8N debe:

1. recibir bloques;
2. validar IDs;
3. validar tipos;
4. validar instancias;
5. validar versiones;
6. validar posiciones;
7. validar datos;
8. validar autorización;
9. localizar la página;
10. crear o actualizar bloques;
11. enviar a WordPress;
12. registrar resultado.

---

61. VALIDACIÓN

El validador debe comprobar:

- ID válido;
- TYPE válido;
- correspondencia ID/TYPE;
- "block_instance_id";
- "block_version";
- "position";
- "enabled";
- estructura correcta;
- datos compatibles;
- bloque autorizado;
- URLs autorizadas;
- ausencia de datos inventados;
- ausencia de duplicados.

---

62. ERRORES

Códigos mínimos:

UNKNOWN_BLOCK_ID
BLOCK_TYPE_MISMATCH
UNAUTHORIZED_BLOCK
UNAUTHORIZED_URL
INVALID_BLOCK_STRUCTURE
MISSING_REQUIRED_DATA
UNVERIFIED_DATA
DUPLICATE_BLOCK
DUPLICATE_BLOCK_INSTANCE
INVALID_BLOCK_INSTANCE_ID
INVALID_BLOCK_VERSION
INVALID_BLOCK_POSITION

---

63. PRINCIPIO DE NO INVENCIÓN

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

enabled = false

según corresponda.

---

64. REGLA DE COMPATIBILIDAD FUTURA

La estructura lógica de los bloques debe mantenerse independiente de:

tema
CSS
constructor visual
plantilla
HTML

El sistema debe permitir cambiar la capa visual sin reconstruir la arquitectura SEO.

---

65. ESTADO

Versión: 5.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Siguiente fase:

SISTEMA DE BLOQUES
        ↓
MODELO DE RENDERIZADO WORDPRESS
        ↓
INTEGRACIÓN N8N ↔ WORDPRESS
        ↓
PLANTILLAS WORDPRESS
        ↓
PRIMERA LANDING
        ↓
PRUEBAS

FIN
