ESQUEMA DE DATOS SEO

Versión: 3.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el modelo canónico de datos utilizado por el sistema SEO local automatizado.

---

1. FUNCIÓN

Este documento define cómo se representan los datos del proyecto SEO.

Es la fuente canónica para:

- oportunidades;
- investigación;
- decisiones;
- arquitectura;
- páginas;
- miniwebs;
- bloques;
- SEO;
- competencia;
- evidencias;
- trazabilidad;
- validación.

No genera contenido.

No decide por sí mismo.

No publica.

---

2. PRINCIPIO DE AUTORIDAD

El modelo de datos es la estructura canónica utilizada por:

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
ARQUITECTURA
↓
BLOQUES
↓
CONTRATO IA
↓
N8N
↓
WORDPRESS

No deben crearse modelos paralelos incompatibles.

Cuando otro documento necesite información:

debe utilizar este modelo.

---

3. REGLA DE NO INVENCIÓN

Los datos deben proceder de:

- evidencias;
- investigación;
- fuentes verificables;
- datos proporcionados;
- decisiones documentadas.

No se inventan datos para completar campos.

Cuando un dato no esté disponible:

"null"

Cuando la ausencia impida continuar:

"REVIEW"

---

4. IDENTIFICADORES

Los identificadores principales son estables.

Opportunity

Formato:

"OPP-001"

"OPP-002"

"OPP-003"

No se reutilizan.

Page

Formato conceptual:

"FON-MARB-P01"

"FON-MARB-P02"

El identificador debe permanecer estable durante la vida de la página.

---

5. OPPORTUNITY

Objeto conceptual:

{
  "opportunity_id": "OPP-001",
  "sector": "",
  "service": "",
  "subservice": null,
  "page_type": "",
  "location": {},
  "intent": {},
  "demand": {},
  "commercial": {},
  "territorial": {},
  "competition": {},
  "differentiation": {},
  "information": {},
  "duplication": {},
  "research": {},
  "decision": {},
  "architecture": {},
  "evidence": [],
  "observations": [],
  "history": []
}

---

6. IDENTIDAD

Campos:

- sector;
- service;
- subservice;
- page_type.

Ejemplo:

{
  "sector": "fontaneria",
  "service": "fontanero",
  "subservice": null,
  "page_type": "service_locality"
}

Los valores deben proceder de la oportunidad y de la arquitectura autorizada.

---

7. LOCALIZACIÓN

La localización debe representarse separando los niveles territoriales.

{
  "location": {
    "country": "España",
    "community": "Andalucía",
    "province": "Málaga",
    "municipality": "Marbella",
    "locality": null,
    "postal_code": null
  }
}

No se deben confundir:

- municipio;
- localidad;
- provincia;
- comunidad autónoma.

---

8. INTENCIÓN

La intención representa lo que realmente busca el usuario.

Campos:

{
  "intent": {
    "primary": "",
    "secondary": [],
    "commercial": "",
    "urgency": "",
    "confidence": ""
  }
}

Valores orientativos:

primary:

- local_service;
- informational;
- transactional;
- contact;
- emergency;
- service_specific.

commercial:

- HIGH;
- MEDIUM;
- LOW;
- UNKNOWN.

urgency:

- HIGH;
- MEDIUM;
- LOW;
- UNKNOWN.

confidence:

- HIGH;
- MEDIUM;
- LOW.

---

9. DEMANDA

La demanda debe diferenciar entre:

dato conocido;

estimación;

dato desconocido.

{
  "demand": {
    "level": "UNKNOWN",
    "volume": null,
    "source": null,
    "confidence": "LOW"
  }
}

Valores de level:

- HIGH;
- MEDIUM;
- LOW;
- UNKNOWN.

No se inventan volúmenes.

No se presentan estimaciones como datos reales.

---

10. POTENCIAL COMERCIAL

{
  "commercial": {
    "potential": "HIGH",
    "lead_value": null,
    "conversion_potential": null,
    "rental_potential": null,
    "confidence": "MEDIUM",
    "evidence": []
  }
}

Valores:

HIGH

MEDIUM

LOW

UNKNOWN

El potencial de alquiler de una miniweb puede registrarse como hipótesis.

No se debe presentar como ingreso garantizado.

---

11. RELEVANCIA TERRITORIAL

{
  "territorial": {
    "relevance": "HIGH",
    "service_location_fit": "HIGH",
    "local_context_available": true,
    "confidence": "MEDIUM"
  }
}

Valores:

HIGH

MEDIUM

LOW

UNKNOWN

La existencia del nombre de una localidad no demuestra relevancia territorial.

---

12. COMPETENCIA

La competencia se divide en:

- cantidad;
- calidad;
- fortaleza;
- dificultad.

{
  "competition": {
    "level": "HIGH",
    "competitor_count": null,
    "competitor_strength": "UNKNOWN",
    "serp_quality": "UNKNOWN",
    "difficulty": "UNKNOWN",
    "competitors": []
  }
}

---

13. NIVELES DE COMPETENCIA

level:

- LOW;
- MEDIUM;
- HIGH;
- VERY_HIGH;
- UNKNOWN.

No se debe utilizar únicamente el número de competidores.

---

14. FORTALEZA DE COMPETIDORES

competitor_strength:

- LOW;
- MEDIUM;
- HIGH;
- VERY_HIGH;
- UNKNOWN.

Debe considerar, cuando exista evidencia:

- autoridad;
- contenido;
- arquitectura;
- backlinks;
- reseñas;
- especialización;
- señales comerciales;
- experiencia de usuario;
- presencia local.

---

15. CALIDAD DE SERP

serp_quality:

- LOW;
- MEDIUM;
- HIGH;
- VERY_HIGH;
- UNKNOWN.

Debe representar la calidad de los resultados que dominan la búsqueda.

Puede considerar:

- empresas;
- directorios;
- grandes marcas;
- páginas especializadas;
- páginas locales;
- marketplaces;
- Map Pack;
- anuncios;
- contenido informativo.

---

16. DIFICULTAD

difficulty:

- LOW;
- MEDIUM;
- HIGH;
- VERY_HIGH;
- UNKNOWN.

La dificultad no es equivalente automáticamente a competencia.

Debe considerar:

- calidad de los competidores;
- intención;
- autoridad;
- contenido;
- enlaces;
- señales locales;
- posibilidad de diferenciación.

---

17. COMPETIDORES

Cada competidor puede representarse como:

{
  "competitor_id": "",
  "name": "",
  "url": "",
  "type": "",
  "strength": "",
  "relevance": "",
  "observations": [],
  "evidence": []
}

No se inventan empresas.

No se inventan URLs.

---

18. DIFERENCIACIÓN

La diferenciación es un objeto propio.

{
  "differentiation": {
    "level": "STRONG",
    "possible": true,
    "reasons": [],
    "evidence": [],
    "confidence": "MEDIUM"
  }
}

Valores:

STRONG

MEDIUM

WEAK

INSUFFICIENT

UNKNOWN.

---

19. REGLA DE DIFERENCIACIÓN

No se considera diferenciación:

- cambiar localidad;
- cambiar H1;
- cambiar URL;
- cambiar sinónimos;
- reordenar párrafos;
- cambiar frases;
- generar texto diferente sin datos diferentes.

Debe existir información útil que justifique la existencia de la página.

---

20. INFORMACIÓN DISPONIBLE

{
  "information": {
    "level": "MEDIUM",
    "local": "MEDIUM",
    "commercial": "UNKNOWN",
    "service": "HIGH",
    "coverage": "UNKNOWN",
    "confidence": "MEDIUM"
  }
}

Valores:

HIGH

MEDIUM

LOW

INSUFFICIENT

UNKNOWN.

---

21. INFORMACIÓN LOCAL

Puede incluir:

- barrios;
- urbanizaciones;
- zonas;
- características territoriales;
- tipos de vivienda;
- necesidades;
- contexto turístico;
- particularidades del servicio.

Solo cuando exista evidencia.

Ejemplo:

{
  "local": {
    "available": true,
    "areas": [],
    "context": [],
    "evidence": []
  }
}

---

22. COBERTURA

{
  "coverage": {
    "confirmed": false,
    "areas": [],
    "municipalities": [],
    "evidence": []
  }
}

No se crean listas de cobertura para SEO si no existe cobertura real.

---

23. RIESGO DE DUPLICACIÓN

{
  "duplication": {
    "risk": "MEDIUM_HIGH",
    "reason": "",
    "similar_opportunities": [],
    "similar_pages": []
  }
}

Valores:

LOW

MEDIUM

MEDIUM_HIGH

HIGH

UNKNOWN.

---

24. INVESTIGACIÓN

{
  "research": {
    "status": "EVIDENCE_INSUFFICIENT",
    "completed_at": null,
    "sources": [],
    "missing_information": [],
    "next_actions": []
  }
}

Estados:

DETECTED

IN_RESEARCH

EVIDENCE_SUFFICIENT

EVIDENCE_INSUFFICIENT

VALIDATED.

---

25. EVIDENCIAS

Cada evidencia debe poder rastrearse.

{
  "evidence_id": "",
  "type": "",
  "source": "",
  "url": "",
  "date": "",
  "field": "",
  "value": null,
  "confidence": "",
  "notes": ""
}

No se consideran evidencias válidas las afirmaciones sin fuente cuando requieren verificación.

---

26. FUENTES

Una fuente puede contener:

{
  "source_id": "",
  "type": "",
  "name": "",
  "url": "",
  "date_accessed": "",
  "reliability": ""
}

Tipos posibles:

- search;
- website;
- business;
- directory;
- official;
- map;
- review;
- dataset;
- user_provided;
- other.

---

27. DECISIÓN

{
  "decision": {
    "seo": "INVESTIGATE",
    "reason": "",
    "confidence": "MEDIUM",
    "decided_at": "",
    "decided_by": "motor"
  }
}

Valores oficiales:

CREATE

GROUP

INVESTIGATE

DO_NOT_CREATE

En la documentación española:

CREAR

AGRUPAR

INVESTIGAR

NO_CREAR

Los valores técnicos utilizados por la implementación deben permanecer estables.

---

28. REGLA DE DECISIÓN

La decisión debe considerar conjuntamente:

- intención;
- demanda;
- potencial comercial;
- relevancia territorial;
- competencia;
- calidad SERP;
- fortaleza competitiva;
- dificultad;
- diferenciación;
- información;
- duplicación;
- arquitectura;
- utilidad.

No existe una única métrica que determine la decisión.

---

29. ARQUITECTURA

Cuando la oportunidad esté preparada para CREAR:

{
  "architecture": {
    "site_type": "local_service_site",
    "root_url": "",
    "pages": [],
    "navigation": {},
    "version": ""
  }
}

La arquitectura no se genera desde la IA.

Debe existir previamente.

---

30. MINIWEB

El modelo permite representar una miniweb completa.

{
  "site_type": "local_service_site",
  "root_url": "/fontanero/marbella/",
  "pages": []
}

Las páginas pueden incluir:

- página principal;
- servicios;
- subservicios;
- variantes;
- contacto;
- otras páginas justificadas.

No se crean automáticamente por existir keywords.

---

31. PÁGINAS AUTORIZADAS

Cada página debe disponer de:

{
  "page_id": "",
  "page_type": "",
  "url": "",
  "canonical": "",
  "parent_url": null,
  "depth": 1,
  "intent": {},
  "authorized_blocks": []
}

---

32. TIPOS DE PÁGINA

Valores iniciales:

- service_locality;
- subservice_locality;
- service_variant;
- contact;
- other_authorized.

Cualquier nuevo tipo debe documentarse antes de utilizarse.

---

33. BLOQUES

Los bloques se representan mediante:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {}
}

Los IDs oficiales son:

B01–B23.

La lista completa está definida en:

"proyecto/seo/sistema-bloques.md"

---

34. BLOQUES AUTORIZADOS

Cada página debe tener:

{
  "authorized_blocks": [
    "B01",
    "B02",
    "B03",
    "B04",
    "B05",
    "B06"
  ]
}

La IA no puede utilizar bloques fuera de esta lista.

---

35. SEO

Cada página puede contener:

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": "",
    "headings": []
  }
}

El contenido debe responder a la intención concreta de la página.

---

36. MENÚ

{
  "menu": {
    "items": [
      {
        "label": "",
        "url": "",
        "type": "internal",
        "target_page_id": ""
      }
    ]
  }
}

Solo se utilizan páginas autorizadas.

---

37. ENLACES INTERNOS

{
  "internal_links": [
    {
      "url": "",
      "anchor": "",
      "target_page_id": "",
      "reason": ""
    }
  ]
}

El enlace debe tener una razón funcional.

No se crean redes artificiales.

---

38. DATOS COMERCIALES

{
  "commercial_data": {
    "phone": null,
    "whatsapp": null,
    "email": null,
    "address": null,
    "opening_hours": null,
    "prices": null,
    "availability": null
  }
}

Todos los valores requieren evidencia.

---

39. CONFIANZA

{
  "trust": {
    "experience": null,
    "certifications": [],
    "guarantees": [],
    "reviews": [],
    "awards": [],
    "evidence": []
  }
}

Nunca se inventan señales de confianza.

---

40. IMÁGENES

{
  "images": [
    {
      "image_id": "",
      "url": "",
      "alt": "",
      "title": "",
      "type": "",
      "source": "",
      "license": null
    }
  ]
}

La imagen debe existir realmente.

---

41. DATOS ESTRUCTURADOS

{
  "structured_data": {
    "types": [],
    "data": {},
    "evidence": []
  }
}

Solo se utilizan datos verificables.

---

42. VALIDACIÓN

{
  "validation": {
    "status": "REVIEW",
    "valid": false,
    "checks": [],
    "errors": [],
    "warnings": []
  }
}

La validación definitiva corresponde al sistema externo.

---

43. ESTADOS DE VALIDACIÓN

Valores:

READY

REVIEW

ERROR

Una salida con error crítico:

NO PUBLICAR.

---

44. ISSUES

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

La incidencia debe registrarse.

No se ocultan problemas para conseguir una salida READY.

---

45. TRAZABILIDAD

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "decision_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "contract_version": ""
  }
}

Debe permitir reconstruir el origen de una página.

---

46. HISTORIAL

Toda oportunidad y toda página relevante debe poder mantener historial.

{
  "history": [
    {
      "date": "",
      "event": "",
      "previous_value": null,
      "new_value": null,
      "reason": "",
      "source": ""
    }
  ]
}

Esto permite modificar decisiones sin perder el histórico.

---

47. IDEMPOTENCIA

Los identificadores estables son esenciales.

Oportunidad:

"opportunity_id"

Página:

"page_id"

N8N debe utilizar estos identificadores para:

- localizar;
- crear;
- actualizar;
- evitar duplicados.

Una segunda ejecución no debe crear otra página idéntica.

---

48. REGLA DE IDENTIDAD

La identidad de una oportunidad debe mantenerse.

Una oportunidad no puede cambiar silenciosamente de:

- servicio;
- municipio;
- provincia;
- sector.

Si la investigación demuestra que la oportunidad inicial era incorrecta:

se registra una incidencia.

No se sobrescribe silenciosamente.

---

49. REGLA DE ARQUITECTURA

La arquitectura debe permanecer separada de los datos.

Los datos pueden cambiar.

La arquitectura puede evolucionar.

Pero ninguna IA puede modificarla silenciosamente durante la generación.

---

50. REGLA DE CONTENIDO

El modelo de datos no almacena contenido artificial.

El contenido generado por IA debe estar vinculado a:

- oportunidad;
- página;
- bloque;
- datos;
- evidencias.

Esto permite saber por qué existe cada contenido.

---

51. REGLA DE CALIDAD

No se debe medir el sistema por:

- número de páginas;
- número de palabras;
- número de keywords;
- número de localidades.

Se debe medir por:

- utilidad;
- intención;
- diferenciación;
- calidad;
- veracidad;
- capacidad comercial;
- capacidad de competir;
- trazabilidad.

---

52. RELACIÓN CON EL MOTOR

El motor consume:

- oportunidad;
- investigación;
- competencia;
- SERP;
- diferenciación;
- datos.

El motor produce:

decision
reason
confidence

El modelo de datos almacena el resultado.

---

53. RELACIÓN CON ARQUITECTURA

Cuando:

"decision = CREATE"

la arquitectura puede definir:

- site_type;
- root_url;
- páginas;
- URLs;
- canonical;
- parent_url;
- profundidad;
- navegación;
- bloques autorizados.

---

54. RELACIÓN CON SISTEMA DE BLOQUES

El modelo de datos proporciona los datos.

El sistema de bloques define cómo pueden organizarse.

Flujo:

DATA
↓
BLOCK
↓
CONTENT
↓
IA

---

55. RELACIÓN CON CONTRATO IA

El contrato IA recibe datos desde este modelo.

La IA no debe inventar campos estructurales.

Debe utilizar únicamente los campos autorizados.

---

56. RELACIÓN CON N8N

N8N utiliza el modelo para:

- validar;
- transportar;
- transformar;
- crear;
- actualizar;
- sincronizar;
- registrar.

N8N no debe reinterpretar decisiones.

---

57. RELACIÓN CON WORDPRESS

WordPress representa visualmente los datos.

No debe convertirse en la fuente primaria de verdad del sistema.

La fuente primaria es el modelo documental y de datos.

---

58. EJEMPLO: FONTANERO MARBELLA

{
  "opportunity_id": "OPP-001",

  "sector": "fontaneria",

  "service": "fontanero",

  "subservice": null,

  "location": {
    "country": "España",
    "community": "Andalucía",
    "province": "Málaga",
    "municipality": "Marbella",
    "locality": null
  },

  "intent": {
    "primary": "local_service",
    "commercial": "HIGH",
    "urgency": "UNKNOWN",
    "confidence": "HIGH"
  },

  "demand": {
    "level": "UNKNOWN",
    "volume": null,
    "confidence": "LOW"
  },

  "commercial": {
    "potential": "HIGH",
    "rental_potential": null,
    "confidence": "MEDIUM"
  },

  "territorial": {
    "relevance": "HIGH",
    "local_context_available": false,
    "confidence": "MEDIUM"
  },

  "competition": {
    "level": "HIGH",
    "competitor_count": null,
    "competitor_strength": "UNKNOWN",
    "serp_quality": "UNKNOWN",
    "difficulty": "UNKNOWN"
  },

  "differentiation": {
    "level": "UNKNOWN",
    "possible": null,
    "confidence": "LOW"
  },

  "information": {
    "level": "MEDIUM",
    "local": "LOW",
    "commercial": "UNKNOWN",
    "service": "HIGH"
  },

  "duplication": {
    "risk": "MEDIUM_HIGH"
  },

  "research": {
    "status": "IN_RESEARCH"
  },

  "decision": {
    "seo": "INVESTIGATE",
    "reason": "Falta evidencia suficiente sobre demanda, fortaleza competitiva, SERP y diferenciación.",
    "confidence": "MEDIUM"
  }
}

---

59. PRINCIPIO DEL CASO MARBELLA

El caso Marbella demuestra que una localidad atractiva comercialmente no implica automáticamente:

CREATE.

La oportunidad debe demostrar:

- intención;
- demanda;
- valor;
- diferenciación;
- capacidad competitiva;
- información suficiente.

---

60. PRINCIPIO DEL CASO MANILVA

El caso Manilva demuestra que la investigación competitiva debe formar parte del modelo.

Si existen webs claramente mejores:

se registra.

No se ignora.

Pero tampoco se convierte automáticamente en:

NO_CREAR.

Debe analizarse:

- qué hacen mejor;
- qué información tienen;
- qué autoridad poseen;
- qué intención cubren;
- qué podemos aportar nosotros;
- si existe una oportunidad más específica.

---

61. REGLA DE INVESTIGACIÓN COMPETITIVA

Cuando la competencia sea:

HIGH

o:

VERY_HIGH

debe ser posible registrar:

- competidores principales;
- fortalezas;
- debilidades;
- SERP;
- oportunidades de diferenciación.

Si esta información es crítica y no existe:

decision = INVESTIGATE.

---

62. REGLA DE MINIWEB

Una oportunidad puede representar un activo compuesto.

Ejemplo:

OPP-001
│
└── SITE
    ├── P01 Inicio
    ├── P02 Desatascos
    ├── P03 24 horas
    └── P04 Contacto

Pero cada página debe tener:

- intención;
- utilidad;
- datos;
- arquitectura;
- bloques;
- contenido propio.

---

63. NO CREACIÓN MASIVA

No se deben generar automáticamente:

servicio × todas_localidades

y después intentar justificar las páginas.

El proceso correcto es:

DETECTAR
↓
INVESTIGAR
↓
EVALUAR
↓
DECIDIR
↓
ARQUITECTURA
↓
GENERAR

---

64. INTEGRIDAD DEL MODELO

N8N debe rechazar una estructura cuando:

- falta opportunity_id;
- existe identidad contradictoria;
- existe página no autorizada;
- existe bloque desconocido;
- existe URL no autorizada;
- existe dato comercial sin evidencia;
- existe contenido obligatorio sin datos;
- existe estructura incompatible;
- existe información inventada;
- existe duplicación no controlada.

---

65. VERSIONADO

Versión mayor:

3.0

Cambios incompatibles:

incrementar versión mayor.

Cambios compatibles:

incrementar versión menor.

Toda modificación estructural debe quedar registrada.

---

66. REGISTRO DE CAMBIOS

2026-08-24

Versión 3.0.

Cambios:

- incorporación formal del análisis competitivo;
- incorporación de calidad de SERP;
- incorporación de fortaleza de competidores;
- incorporación de dificultad;
- incorporación de diferenciación;
- incorporación de información local;
- incorporación de cobertura;
- incorporación de potencial de miniweb;
- separación de datos de decisión;
- incorporación de trazabilidad;
- refuerzo de idempotencia;
- adaptación a páginas múltiples;
- adaptación a miniwebs locales;
- alineación con motor de decisión v3.0;
- alineación con sistema de bloques v2.0;
- preparación para contrato IA v3.0;
- preparación para implementación N8N → WordPress.

---

67. REGLA FINAL

El modelo de datos responde:

¿QUÉ SABEMOS?

El motor responde:

¿QUÉ HACEMOS?

La arquitectura responde:

¿QUÉ CONSTRUIMOS?

El sistema de bloques responde:

¿CÓMO SE ESTRUCTURA?

La IA responde:

¿CÓMO GENERAMOS EL CONTENIDO?

N8N responde:

¿CÓMO LO AUTOMATIZAMOS?

WordPress responde:

¿CÓMO LO RENDERIZAMOS?

Ninguna capa debe sustituir a otra.

---

FIN DE ESQUEMA DE DATOS SEO
