ESQUEMA DE DATOS SEO

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el modelo de datos canónico utilizado por el sistema SEO local, incluyendo oportunidades, arquitectura, páginas, bloques e interlinking.

---

1. FUNCIÓN

Este documento define cómo se representan los datos del proyecto SEO.

El modelo debe permitir:

- investigar oportunidades;
- tomar decisiones;
- construir arquitecturas;
- generar páginas;
- representar miniwebs;
- relacionar páginas;
- gestionar interlinking;
- actualizar páginas;
- evitar duplicados;
- mantener trazabilidad;
- permitir procesamiento automático mediante N8N;
- representar múltiples pilares SEO.

Este documento define datos.

No genera contenido.

No decide qué páginas deben existir.

No decide qué bloques debe utilizar una página.

No publica en WordPress.

---

2. PRINCIPIO FUNDAMENTAL

Existe un único modelo de datos canónico.

Las diferentes capas del sistema deben utilizarlo.

Flujo:

INVESTIGACIÓN
↓
OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
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

Ninguna capa debe crear un modelo paralelo incompatible.

---

3. IDENTIFICADOR PRINCIPAL

Cada oportunidad debe tener:

"opportunity_id"

Ejemplo:

"FON-EST-001"

Debe ser:

- único;
- estable;
- reutilizable;
- trazable.

N8N utilizará este identificador para garantizar idempotencia.

---

4. IDENTIDAD DE LA OPORTUNIDAD

Una oportunidad puede contener:

{
  "opportunity_id": "",
  "sector": "",
  "service": "",
  "subservice": null,
  "municipality": "",
  "province": "",
  "country": ""
}

Los datos territoriales y de servicio deben proceder de fuentes autorizadas.

No se inventan.

---

5. DECISIÓN SEO

Cada oportunidad debe almacenar:

{
  "decision_seo": "",
  "decision_reason": "",
  "decision_confidence": ""
}

Valores de "decision_seo":

- "CREAR"
- "AGRUPAR"
- "INVESTIGAR"
- "NO_CREAR"
- "PENDIENTE"

Valores de "decision_confidence":

- "ALTA"
- "MEDIA"
- "BAJA"

---

6. EVIDENCIAS

La oportunidad debe poder conservar las evidencias utilizadas para tomar la decisión.

Ejemplo:

{
  "evidence": {
    "demand": {},
    "commercial": {},
    "territorial": {},
    "serp": {},
    "competition": {},
    "differentiation": {}
  }
}

Los datos desconocidos deben representarse como:

"null"

o:

"DESCONOCIDO"

según corresponda.

No se inventan métricas.

---

7. COMPETENCIA

La información competitiva debe poder almacenarse.

{
  "competition": {
    "level": "",
    "competitor_strength": "",
    "serp_quality": "",
    "competitors": []
  }
}

Valores:

"level"

- "BAJA"
- "MEDIA"
- "ALTA"
- "MUY_ALTA"
- "DESCONOCIDA"

"competitor_strength"

- "BAJA"
- "MEDIA"
- "ALTA"
- "MUY_ALTA"
- "DESCONOCIDA"

"serp_quality"

- "BAJA"
- "MEDIA"
- "ALTA"
- "MUY_ALTA"
- "DESCONOCIDA"

---

8. DIFERENCIACIÓN

{
  "differentiation": {
    "level": "",
    "signals": []
  }
}

Valores:

- "FUERTE"
- "DEBIL"
- "INSUFICIENTE"
- "DESCONOCIDA"

Los "signals" deben describir diferencias reales.

---

9. SITE

Cuando una oportunidad se convierte en una miniweb:

{
  "site_id": "",
  "site_type": "local_service_site",
  "name": "",
  "root_url": "",
  "status": ""
}

"site_id" debe ser único y estable.

---

10. PÁGINAS

Cada página debe tener un identificador estable.

{
  "page_id": "",
  "site_id": "",
  "page_type": "",
  "url": "",
  "canonical": "",
  "parent_url": null,
  "depth": 1,
  "status": ""
}

Valores posibles de "status":

- "AUTHORIZED"
- "GENERATED"
- "VALIDATED"
- "PUBLISHED"
- "UPDATE_REQUIRED"
- "DISABLED"
- "REVIEW"
- "ERROR"

---

11. REGLA DE URL

La URL debe proceder de la arquitectura autorizada.

El modelo de datos no permite que la IA cree URLs arbitrarias.

Una URL debe poder relacionarse con:

- "site_id";
- "page_id";
- "opportunity_id".

---

12. CANONICAL

Cada página debe almacenar su canonical.

{
  "canonical": "/fontaneros/estepona/"
}

El canonical debe coincidir con la arquitectura.

---

13. JERARQUÍA

Cada página puede tener:

{
  "parent_url": null,
  "depth": 1
}

Ejemplo:

/fontaneros/estepona/
    ↓
/fontaneros/estepona/desatascos/

La segunda página tendrá:

{
  "parent_url": "/fontaneros/estepona/",
  "depth": 2
}

---

14. INTENCIÓN

Cada página debe poder almacenar su intención:

{
  "intent": {
    "type": "",
    "description": ""
  }
}

La intención debe proceder de la investigación.

No se inventa durante la generación.

---

15. SEO DE LA PÁGINA

{
  "seo": {
    "primary_keyword": "",
    "secondary_keywords": [],
    "title": "",
    "meta_description": "",
    "h1": ""
  }
}

Las keywords son datos de investigación.

No se deben generar páginas únicamente porque exista una keyword.

---

16. BLOQUES AUTORIZADOS

Cada página debe almacenar los bloques que puede utilizar:

{
  "authorized_blocks": [
    "B01",
    "B02",
    "B03"
  ]
}

La IA no puede utilizar bloques fuera de esta lista.

---

17. BLOQUES GENERADOS

Los bloques utilizados en una página deben poder almacenarse:

{
  "blocks": [
    {
      "id": "B03",
      "type": "hero",
      "enabled": true,
      "data": {}
    }
  ]
}

Los IDs deben corresponder al sistema oficial de bloques.

---

18. INFORMACIÓN COMERCIAL

Cuando exista información real de una empresa:

{
  "business": {
    "name": null,
    "legal_name": null,
    "phone": null,
    "whatsapp": null,
    "email": null,
    "address": null,
    "logo_url": null,
    "website": null
  }
}

Durante las pruebas puede utilizarse:

"null"

No se deben inventar datos comerciales para producción.

---

19. COBERTURA

{
  "coverage": {
    "areas": [],
    "municipalities": [],
    "provinces": []
  }
}

Solo deben incluirse zonas respaldadas.

---

20. IMÁGENES

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

Las URLs deben corresponder a recursos reales.

---

21. INTERLINKING

El modelo de datos incorpora un sistema específico para relaciones entre páginas.

Cada enlace interno debe ser una entidad independiente.

{
  "link_id": "",
  "source_page_id": "",
  "target_page_id": "",
  "relation": "",
  "anchor": "",
  "reason": "",
  "location": "",
  "status": ""
}

---

22. LINK_ID

Cada relación debe tener un identificador estable.

Ejemplo:

"LINK-FON-EST-CAS-001"

El identificador permite:

- evitar duplicados;
- actualizar enlaces;
- eliminar enlaces;
- rastrear cambios;
- procesar repetidamente mediante N8N.

---

23. SOURCE_PAGE_ID

Representa la página desde la que sale el enlace.

Ejemplo:

"source_page_id": "FON-EST-P01"

Debe existir.

---

24. TARGET_PAGE_ID

Representa la página destino.

Ejemplo:

"target_page_id": "FON-CAS-P01"

Debe existir y estar autorizada.

---

25. RELATION

Valores oficiales iniciales:

- "parent_to_child"
- "child_to_parent"
- "related_location"
- "related_service"
- "related_subservice"
- "territorial"
- "contextual"
- "navigation"

No deben crearse tipos arbitrarios.

---

26. ANCHOR

El anchor debe almacenarse:

"anchor": "fontaneros en Casares"

Debe ser natural y descriptivo.

No debe utilizarse siempre la keyword exacta.

---

27. REASON

Debe explicar por qué existe la relación.

Ejemplo:

"reason": "Localidad cercana y autorizada dentro de la misma zona de servicio."

Esto permite trazabilidad.

---

28. LOCATION

Indica dónde aparece el enlace.

Valores iniciales:

- "header"
- "navigation"
- "content"
- "related_services"
- "related_locations"
- "footer"
- "breadcrumb"
- "cta"

---

29. STATUS DEL ENLACE

Valores:

- "AUTHORIZED"
- "PROPOSED"
- "VALIDATED"
- "ACTIVE"
- "DISABLED"
- "ERROR"

La IA puede generar "PROPOSED".

El validador puede convertirlo en:

"VALIDATED"

N8N puede convertirlo en:

"ACTIVE"

---

30. RELACIÓN TERRITORIAL

Las relaciones entre localidades deben poder almacenarse separadamente.

{
  "territorial_relations": [
    {
      "source_municipality": "Estepona",
      "target_municipality": "Casares",
      "relation": "nearby",
      "authorized": true
    }
  ]
}

Valores de relación:

- "nearby"
- "same_area"
- "service_area"
- "strategic"
- "commercial"
- "review"

No se inventan relaciones geográficas.

---

31. RELACIÓN ENTRE PILARES

Debe poder almacenarse:

{
  "pillar_relations": [
    {
      "source_service": "fontaneria",
      "target_service": "electricidad",
      "relation": "related_service",
      "authorized": true
    }
  ]
}

Esto permite construir una red temática entre diferentes servicios.

---

32. REGLA DE PILARES

Ejemplo:

FONTANERÍA
    ↓
ELECTRICIDAD
    ↓
CARPINTERÍA
    ↓
PINTURA

No significa que cada página de un pilar deba enlazar con todas las páginas de los demás pilares.

Las relaciones deben estar autorizadas.

---

33. RELACIONES DE SERVICIO

{
  "service_relations": [
    {
      "source_service": "fontanero",
      "target_service": "desatascos",
      "relation": "related_subservice",
      "authorized": true
    }
  ]
}

Estas relaciones permiten que N8N determine qué páginas pueden relacionarse.

---

34. PÁGINAS RELACIONADAS

Una página puede tener una lista calculada de relaciones:

{
  "related_pages": [
    {
      "page_id": "",
      "relation": "",
      "priority": 1
    }
  ]
}

"priority" permite ordenar las relaciones.

Valores:

- "1"
- "2"
- "3"
- etc.

Cuanto menor sea el número, mayor prioridad.

---

35. PRIORIDAD DE ENLACE

Las relaciones pueden clasificarse:

- "HIGH"
- "MEDIUM"
- "LOW"

Ejemplo:

La página padre puede tener prioridad "HIGH".

Una localidad relacionada puede tener prioridad "MEDIUM".

Una relación transversal puede tener prioridad "LOW".

---

36. ENLACES BIDIRECCIONALES

No todos los enlaces tienen que ser bidireccionales.

El modelo debe permitir:

A → B

sin exigir:

B → A

Esto evita crear redes artificialmente simétricas.

---

37. PÁGINAS HUÉRFANAS

El modelo debe permitir detectar páginas sin relaciones.

Una página será considerada potencialmente huérfana cuando:

- no tenga enlaces entrantes;
- no tenga relación con su padre;
- no forme parte de navegación;
- no tenga ninguna relación contextual autorizada.

El sistema deberá marcarla:

"REVIEW"

cuando corresponda.

---

38. DENSIDAD DE ENLACES

El modelo debe permitir calcular:

{
  "link_metrics": {
    "incoming": 0,
    "outgoing": 0,
    "contextual": 0,
    "navigation": 0
  }
}

Estas métricas serán calculadas por el sistema.

No serán inventadas por la IA.

---

39. REGLA DE NO DUPLICACIÓN

Antes de crear un enlace:

comprobar:

"link_id"

"source_page_id"

"target_page_id"

"relation"

Si ya existe una relación equivalente:

no crear otra.

---

40. ACTUALIZACIONES

Cuando una página cambie:

N8N debe poder actualizar:

- contenido;
- SEO;
- bloques;
- enlaces;
- relaciones;
- imágenes;
- datos comerciales.

Los cambios deben quedar registrados.

---

41. NUEVA PÁGINA

Cuando se cree una nueva página:

N8N debe comprobar:

1. qué página es su padre;
2. qué páginas hijas existen;
3. qué servicios relacionados existen;
4. qué localidades relacionadas existen;
5. qué relaciones entre pilares existen;
6. qué enlaces entrantes deberían crearse;
7. qué enlaces salientes deberían crearse.

---

42. PÁGINA ELIMINADA

Si una página deja de estar autorizada:

N8N debe:

1. desactivar la página;
2. desactivar enlaces entrantes;
3. desactivar enlaces salientes;
4. actualizar navegación;
5. eliminar relaciones obsoletas;
6. registrar la modificación.

No deben quedar enlaces activos hacia una página eliminada.

---

43. IDEMPOTENCIA

Todo procesamiento debe ser repetible.

Si N8N recibe dos veces la misma información:

no debe crear:

- páginas duplicadas;
- enlaces duplicados;
- relaciones duplicadas.

Debe localizar los registros mediante sus identificadores estables.

---

44. HISTORIAL

Las modificaciones importantes deben poder registrarse.

{
  "history": [
    {
      "timestamp": "",
      "action": "",
      "entity_type": "",
      "entity_id": "",
      "reason": ""
    }
  ]
}

Ejemplos de "action":

- "CREATE"
- "UPDATE"
- "DISABLE"
- "REVALIDATE"
- "RELINK"

---

45. TRAZABILIDAD

Cada entidad debe poder relacionarse con:

- "opportunity_id";
- "site_id";
- "page_id";
- versión de arquitectura;
- versión de datos;
- versión de bloques;
- versión del contrato IA.

---

46. ESTRUCTURA GLOBAL

Conceptualmente, una oportunidad completa puede representarse así:

{
  "opportunity": {},
  "site": {},
  "identity": {},
  "competition": {},
  "differentiation": {},
  "pages": [],
  "services": [],
  "locations": [],
  "blocks": [],
  "links": [],
  "territorial_relations": [],
  "service_relations": [],
  "pillar_relations": [],
  "history": {},
  "traceability": {}
}

---

47. REGLA DE SEPARACIÓN

El modelo de datos no debe contener contenido editorial final generado por la IA como parte de la definición estructural.

Debe almacenar:

- identidad;
- relaciones;
- arquitectura;
- metadatos;
- autorizaciones;
- estados;
- referencias.

El contenido generado pertenece a la capa de generación.

---

48. VALIDACIÓN

El validador debe comprobar:

- identificadores únicos;
- URLs válidas;
- páginas autorizadas;
- relaciones válidas;
- destinos existentes;
- relaciones territoriales autorizadas;
- relaciones entre pilares autorizadas;
- bloques válidos;
- ausencia de duplicados;
- ausencia de enlaces rotos;
- trazabilidad completa.

---

49. ERROR

Errores posibles:

"DUPLICATE_ID"

"INVALID_PAGE"

"INVALID_URL"

"UNAUTHORIZED_PAGE"

"UNAUTHORIZED_RELATION"

"INVALID_LINK"

"DUPLICATE_LINK"

"MISSING_PARENT"

"ORPHAN_PAGE"

"INVALID_BLOCK"

"MISSING_TRACEABILITY"

---

50. PRINCIPIO DE ESCALABILIDAD

El modelo debe funcionar para:

- 1 oportunidad;
- 10 oportunidades;
- 1.000 oportunidades;
- 100.000 oportunidades.

Debe permitir gestionar miles de páginas sin depender de relaciones escritas manualmente.

---

51. PRINCIPIO FINAL

El modelo de datos debe permitir representar:

OPORTUNIDAD
↓
SITE
↓
PÁGINAS
↓
SERVICIOS
↓
LOCALIDADES
↓
SUBSERVICIOS
↓
BLOQUES
↓
RELACIONES
↓
INTERLINKING

De esta forma, N8N puede construir y mantener automáticamente una red SEO coherente.

---

52. ESTADO DEL DOCUMENTO

Versión:

2.0

Estado:

PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha:

2026-08-24

Cambios principales:

- incorporación del sistema de interlinking;
- incorporación de relaciones entre páginas;
- incorporación de relaciones territoriales;
- incorporación de relaciones entre servicios;
- incorporación de relaciones entre pilares;
- incorporación de estados de enlaces;
- incorporación de prioridades;
- incorporación de métricas de enlaces;
- incorporación de detección de páginas huérfanas;
- refuerzo de idempotencia;
- incorporación de historial;
- incorporación de trazabilidad.

---

FIN DEL ESQUEMA DE DATOS SEO
