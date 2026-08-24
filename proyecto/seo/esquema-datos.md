ESQUEMA DE DATOS SEO

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir el modelo de datos canónico utilizado para investigar, evaluar, decidir, arquitecturar, generar y mantener activos SEO locales escalables.

---

1. FUNCIÓN

Este documento define el modelo de datos central del sistema SEO.

El modelo debe poder representar:

- oportunidades SEO;
- servicios;
- subservicios;
- variantes;
- problemas;
- intenciones;
- localidades;
- evidencias;
- competencia;
- SERP;
- diferenciación;
- páginas potenciales;
- páginas autorizadas;
- bloques autorizados;
- relaciones entre páginas;
- datos comerciales;
- datos de contacto;
- estado de una oportunidad;
- historial de decisiones;
- trazabilidad.

El modelo no debe limitar artificialmente el número de posibilidades.

No existe un número predeterminado de:

- páginas;
- servicios;
- subservicios;
- variantes;
- bloques;
- enlaces.

El número final dependerá de la investigación y de la arquitectura resultante.

---

2. PRINCIPIO FUNDAMENTAL

El sistema debe trabajar con:

DESCUBRIR → EVALUAR → DESCARTAR → AUTORIZAR

y no con:

LIMITAR → GENERAR → RELLENAR

Por tanto, el modelo debe permitir inicialmente almacenar todas las posibilidades razonables detectadas durante la investigación.

Posteriormente cada posibilidad podrá clasificarse como:

- AUTORIZADA;
- AGRUPADA;
- DESCARTADA;
- INVESTIGAR;
- NO CREAR.

---

3. REGLA DE NO LIMITACIÓN

El modelo no puede contener reglas como:

- máximo 5 páginas;
- exactamente 5 páginas;
- 3 servicios por defecto;
- 1 página principal + 3 servicios + contacto;
- número fijo de subpáginas;
- número fijo de bloques.

Esas cantidades no forman parte del modelo.

El número de elementos debe ser dinámico.

---

4. ESTRUCTURA GENERAL

La oportunidad puede representarse conceptualmente así:

OPORTUNIDAD
│
├── IDENTIDAD
│
├── LOCALIZACIÓN
│
├── SERVICIO
│   ├── SERVICIO PRINCIPAL
│   ├── SUBSERVICIOS
│   ├── VARIANTES
│   └── PROBLEMAS
│
├── INTENCIONES
│
├── KEYWORDS
│
├── EVIDENCIAS
│
├── SERP
│
├── COMPETENCIA
│
├── DIFERENCIACIÓN
│
├── PÁGINAS POTENCIALES
│
├── AGRUPACIONES
│
├── DECISIÓN SEO
│
├── ARQUITECTURA
│
├── DATOS COMERCIALES
│
└── TRAZABILIDAD

---

5. IDENTIDAD DE LA OPORTUNIDAD

Cada oportunidad debe tener un identificador estable.

Ejemplo:

{
  "opportunity_id": "FON-FUE-001"
}

El identificador debe permanecer estable durante todo el ciclo de vida de la oportunidad.

No debe reutilizarse.

---

6. IDENTIDAD SEO

{
  "identity": {
    "sector": "",
    "service": "",
    "subservice": null,
    "variant": null,
    "problem": null,
    "municipality": "",
    "province": "",
    "country": ""
  }
}

Los campos pueden ser "null" cuando todavía no estén determinados.

---

7. SERVICIO PRINCIPAL

Ejemplo:

{
  "service": {
    "id": "SRV-FONTANERIA",
    "name": "Fontanero",
    "status": "ACTIVE"
  }
}

El servicio principal puede tener múltiples subservicios.

No existe un límite.

---

8. SUBSERVICIOS

Los subservicios deben almacenarse como colección.

Ejemplo:

{
  "subservices": [
    {
      "id": "SUB-DESATASCOS",
      "name": "Desatascos",
      "status": "CANDIDATE"
    },
    {
      "id": "SUB-FUGAS",
      "name": "Reparación de fugas",
      "status": "CANDIDATE"
    },
    {
      "id": "SUB-CALDERAS",
      "name": "Reparación de calderas",
      "status": "CANDIDATE"
    }
  ]
}

La investigación puede descubrir:

3, 5, 10, 20 o más subservicios.

No existe un número predeterminado.

---

9. VARIANTES

Una variante puede representar una intención o modalidad específica del servicio.

Ejemplo:

{
  "variants": [
    {
      "id": "VAR-24H",
      "name": "24 horas",
      "status": "CANDIDATE"
    },
    {
      "id": "VAR-URGENTE",
      "name": "Urgente",
      "status": "CANDIDATE"
    }
  ]
}

Una variante solo podrá convertirse en página cuando tenga intención propia y justificación suficiente.

---

10. PROBLEMAS

El modelo puede representar problemas concretos:

{
  "problems": [
    {
      "id": "PROB-FUGA-AGUA",
      "name": "Fuga de agua",
      "status": "CANDIDATE"
    }
  ]
}

Los problemas pueden generar oportunidades de página independientes si la investigación lo justifica.

---

11. INTENCIONES

Cada oportunidad debe poder tener múltiples intenciones detectadas.

{
  "intents": [
    {
      "id": "INT-001",
      "type": "TRANSACTIONAL",
      "description": "Buscar un fontanero para contratar el servicio",
      "confidence": "HIGH"
    }
  ]
}

Valores de "type":

- INFORMATIONAL
- COMMERCIAL
- TRANSACTIONAL
- NAVIGATIONAL
- LOCAL_TRANSACTIONAL
- LOCAL_INFORMATIONAL
- MIXED
- UNKNOWN

---

12. KEYWORDS

Las keywords son evidencias, no instrucciones automáticas para crear URLs.

{
  "keywords": [
    {
      "keyword": "fontaneros en Fuengirola",
      "intent_id": "INT-001",
      "source": "RESEARCH",
      "status": "ACTIVE"
    }
  ]
}

Una keyword no implica automáticamente una página.

---

13. LOCALIZACIÓN

{
  "location": {
    "municipality": {
      "name": "Fuengirola",
      "verified": true
    },
    "province": {
      "name": "Málaga",
      "verified": true
    },
    "country": {
      "name": "España",
      "verified": true
    }
  }
}

No deben inventarse datos geográficos.

---

14. LOCALIDADES RELACIONADAS

La investigación puede detectar localidades relacionadas.

{
  "related_locations": [
    {
      "name": "Mijas",
      "relationship": "NEARBY",
      "verified": true
    }
  ]
}

Una localidad relacionada no se convierte automáticamente en página.

Debe pasar por evaluación independiente.

---

15. EVIDENCIAS

Toda decisión debe poder rastrearse hasta evidencias.

{
  "evidence": [
    {
      "id": "EVD-001",
      "type": "SERP",
      "source": "",
      "date": "",
      "description": "",
      "reliability": "HIGH"
    }
  ]
}

Tipos posibles:

- KEYWORD_RESEARCH
- SERP
- COMPETITOR
- LOCAL_DATA
- COMMERCIAL
- USER_INTENT
- BUSINESS_DATA
- SEARCH_ENGINE
- OTHER

---

16. SERP

{
  "serp": {
    "analysed": true,
    "quality": "HIGH",
    "dominant_intent": "LOCAL_TRANSACTIONAL",
    "map_pack": true,
    "ads": true,
    "organic_results": 10,
    "relevant_local_results": 6,
    "directories": 2,
    "specialized_pages": 4,
    "strong_domains": 3
  }
}

Cuando un dato no haya sido comprobado:

null

No se inventan métricas.

---

17. COMPETIDORES

{
  "competitors": [
    {
      "id": "COMP-001",
      "url": "",
      "domain": "",
      "type": "LOCAL_BUSINESS",
      "strength": "HIGH",
      "content_quality": "HIGH",
      "local_relevance": "HIGH",
      "technical_quality": "MEDIUM",
      "trust_signals": "HIGH",
      "specialization": "HIGH"
    }
  ]
}

No todos los competidores tienen el mismo peso.

---

18. FORTALEZA COMPETITIVA

Valores:

- LOW
- MEDIUM
- HIGH
- VERY_HIGH
- UNKNOWN

La fortaleza debe proceder de evidencia.

---

19. DIFERENCIACIÓN

{
  "differentiation": {
    "level": "STRONG",
    "sources": [
      "LOCAL_CONTEXT",
      "SERVICE_SPECIALIZATION",
      "USER_INTENT"
    ],
    "description": ""
  }
}

Valores:

- STRONG
- MEDIUM
- WEAK
- INSUFFICIENT
- UNKNOWN

---

20. INFORMACIÓN DISPONIBLE

{
  "information": {
    "level": "HIGH",
    "commercial": "MEDIUM",
    "local": "HIGH",
    "service": "HIGH",
    "trust": "LOW"
  }
}

Valores:

- HIGH
- MEDIUM
- LOW
- INSUFFICIENT
- UNKNOWN

---

21. RIESGO DE DUPLICACIÓN

{
  "duplication_risk": "MEDIUM"
}

Valores:

- LOW
- MEDIUM
- MEDIUM_HIGH
- HIGH
- UNKNOWN

---

22. PÁGINAS POTENCIALES

Este es uno de los cambios fundamentales del modelo 4.0.

La investigación puede descubrir numerosas páginas potenciales.

Ejemplo:

{
  "candidate_pages": [
    {
      "candidate_id": "CP-001",
      "type": "SERVICE_LOCALITY",
      "subject": "Fontanero",
      "location": "Fuengirola",
      "intent_id": "INT-001",
      "status": "CANDIDATE"
    },
    {
      "candidate_id": "CP-002",
      "type": "SUBSERVICE_LOCALITY",
      "subject": "Desatascos",
      "location": "Fuengirola",
      "intent_id": "INT-002",
      "status": "CANDIDATE"
    },
    {
      "candidate_id": "CP-003",
      "type": "SUBSERVICE_LOCALITY",
      "subject": "Reparación de fugas",
      "location": "Fuengirola",
      "intent_id": "INT-003",
      "status": "CANDIDATE"
    }
  ]
}

La cantidad de candidatos es ilimitada.

---

23. REGLA DE CANDIDATOS

El sistema debe favorecer:

descubrir candidatos primero.

Después:

evaluar candidatos.

Después:

descartar candidatos débiles.

Finalmente:

autorizar candidatos válidos.

Esto permite evitar que una arquitectura inicial demasiado pequeña limite las oportunidades reales descubiertas durante la investigación.

---

24. ESTADOS DE CANDIDATO

Valores:

- CANDIDATE
- EVALUATING
- AUTHORIZED
- GROUPED
- DISCARDED
- INVESTIGATE
- NO_CREATE

---

25. AGRUPACIONES

Varias oportunidades pueden pertenecer a una misma página.

{
  "groups": [
    {
      "group_id": "GRP-001",
      "members": [
        "CP-001",
        "CP-004",
        "CP-007"
      ],
      "reason": "SAME_INTENT"
    }
  ]
}

Esto evita crear URLs innecesarias.

---

26. REGLA DE AGRUPACIÓN

Antes de autorizar una página independiente debe comprobarse:

- intención;
- necesidad del usuario;
- diferenciación;
- SERP;
- contenido potencial;
- valor comercial.

Si varias oportunidades responden esencialmente a lo mismo:

AGRUPAR.

---

27. DECISIÓN INDIVIDUAL

Cada candidato debe poder recibir su propia evaluación.

{
  "decision": {
    "status": "CREATE",
    "reason": "",
    "confidence": "HIGH"
  }
}

Valores:

- CREATE
- GROUP
- INVESTIGATE
- NO_CREATE

---

28. PÁGINAS AUTORIZADAS

Después de la evaluación se genera:

{
  "authorized_pages": []
}

Esta colección representa únicamente las páginas que pueden pasar a arquitectura.

No existe un límite.

Puede contener:

- 1 página;
- 5 páginas;
- 10 páginas;
- 20 páginas;
- 50 páginas;

siempre que cada una esté justificada.

---

29. REGLA FUNDAMENTAL DE AUTORIZACIÓN

Una página no se autoriza porque:

- exista una keyword;
- exista una localidad;
- exista un servicio;
- queramos aumentar el número de URLs.

Se autoriza porque:

existe una intención y una oportunidad suficientemente diferenciada y justificada.

---

30. ARQUITECTURA RESULTANTE

{
  "architecture": {
    "site_type": "LOCAL_SERVICE_SITE",
    "root_url": "",
    "pages": [],
    "relationships": []
  }
}

La arquitectura se construye después de la decisión.

---

31. URL

Las URLs pertenecen a la arquitectura.

El modelo de datos puede almacenar la URL propuesta:

{
  "url": "/fontanero/fuengirola/desatascos/"
}

Pero la IA no puede inventarla libremente si ya existe una arquitectura autorizada.

---

32. DATOS COMERCIALES

Los datos comerciales deben estar separados de la oportunidad SEO.

{
  "business": {
    "name": null,
    "logo": null,
    "phone": null,
    "whatsapp": null,
    "email": null,
    "address": null,
    "opening_hours": null
  }
}

Durante la fase de generación sin cliente:

los datos pueden permanecer "null".

---

33. DATOS DE DEMO

Para pruebas internas se pueden utilizar datos ficticios.

Deben marcarse explícitamente:

{
  "business": {
    "mode": "DEMO"
  }
}

Los datos DEMO nunca deben publicarse como datos reales.

---

34. CONTACTO

Los canales de contacto pueden tener:

{
  "contact": {
    "phone": null,
    "whatsapp": null,
    "email": null,
    "mode": "DISABLED"
  }
}

Valores de "mode":

- REAL
- DEMO
- DISABLED

---

35. REGLA DE PREALQUILER

Una web no alquilada puede existir como activo SEO en desarrollo sin datos comerciales definitivos.

Por tanto:

SEO
+
CONTENIDO
+
ARQUITECTURA
+
ESTRUCTURA
+
DISEÑO

pueden existir antes de:

CLIENTE
+
LOGO
+
TELÉFONO
+
WHATSAPP
+
EMAIL

Los datos comerciales se incorporarán posteriormente.

---

36. BLOQUES

Los bloques pertenecen a la arquitectura y al contrato IA.

El modelo debe poder almacenar:

{
  "authorized_blocks": []
}

No existe un número máximo.

---

37. ESTADO DE BLOQUE

Valores:

- AUTHORIZED
- OPTIONAL
- OMITTED
- DISCARDED
- REVIEW

---

38. ENLACES INTERNOS

{
  "internal_links": [
    {
      "source_page": "",
      "target_page": "",
      "anchor": "",
      "reason": ""
    }
  ]
}

Las relaciones deben apuntar únicamente a páginas existentes o autorizadas.

---

39. DATOS ESTRUCTURADOS

{
  "structured_data": {
    "available": true,
    "types": []
  }
}

Nunca deben introducirse datos falsos.

---

40. IMÁGENES

{
  "images": [
    {
      "id": "",
      "url": null,
      "alt": "",
      "type": "",
      "source": ""
    }
  ]
}

Si no existe una imagen real:

"url = null"

---

41. HISTORIAL

Toda oportunidad debe poder mantener historial.

{
  "history": [
    {
      "date": "",
      "stage": "",
      "decision": "",
      "reason": ""
    }
  ]
}

Esto permite saber cómo cambió la oportunidad.

---

42. TRAZABILIDAD

{
  "traceability": {
    "opportunity_id": "",
    "research_version": "",
    "decision_version": "",
    "architecture_version": "",
    "blocks_version": "",
    "contract_version": ""
  }
}

---

43. VALIDACIÓN

El modelo debe permitir almacenar el resultado de la validación.

{
  "validation": {
    "status": "VALID",
    "checks": []
  }
}

Valores:

- VALID
- REVIEW
- ERROR

---

44. ISSUES

{
  "issues": [
    {
      "code": "",
      "severity": "",
      "field": "",
      "message": ""
    }
  ]
}

La IA y los procesos automáticos deben registrar incidencias.

No deben ocultarlas.

---

45. IDEMPOTENCIA

Los identificadores principales son:

opportunity_id
candidate_id
group_id
page_id

N8N utilizará estos identificadores para evitar duplicados.

Una ejecución repetida no debe crear nuevas entidades idénticas.

---

46. REGLA DE ACTUALIZACIÓN

Cuando una oportunidad vuelva a investigarse:

- no se debe crear otra oportunidad idéntica;
- se actualiza la existente;
- se añade nueva evidencia;
- se registra el cambio;
- puede cambiar la decisión.

---

47. MODELO DE CICLO DE VIDA

DISCOVERED
↓
RESEARCH
↓
CANDIDATE
↓
EVALUATING
↓
AUTHORIZED
↓
ARCHITECTED
↓
GENERATED
↓
VALIDATED
↓
PUBLISHED

Una entidad también puede pasar a:

GROUPED
DISCARDED
NO_CREATE
REVIEW

---

48. REGLA DE DESCUBRIMIENTO

La fase de investigación debe ser deliberadamente amplia.

Si encuentra:

- subservicios;
- problemas;
- variantes;
- intenciones;
- preguntas;
- servicios relacionados;
- páginas potenciales;

debe registrarlos.

No debe descartarlos simplemente porque la arquitectura inicial no los contemplara.

La arquitectura debe poder ampliarse después de la investigación si el sistema documental lo autoriza.

---

49. REGLA DE DESCARTE

Descubrir algo no significa aprobarlo.

El sistema debe poder almacenar:

DESCUBIERTO
↓
EVALUADO
↓
DESCARTADO

Esto es importante para conservar trazabilidad.

---

50. REGLA DE APRENDIZAJE

Los descartes y agrupaciones también son información.

Ejemplo:

"Fontanero Fuengirola"
"Fontaneros Fuengirola"
"Fontanería Fuengirola"

pueden terminar agrupados.

El sistema debe conservar esa decisión para evitar repetir el análisis innecesariamente.

---

51. MINIWEB

Una miniweb puede contener cualquier número de páginas justificadas.

Ejemplo:

SITE
│
├── HOME
├── SERVICE
├── SUBSERVICE
├── SUBSERVICE
├── SUBSERVICE
├── SUBSERVICE
├── VARIANT
├── PROBLEM
├── FAQ
├── CONTACT
└── ...

Los puntos suspensivos representan posibilidades dinámicas, no páginas obligatorias.

---

52. NO EXISTE UNA MINIWEB POR DEFECTO DE CINCO PÁGINAS

Queda expresamente eliminado como criterio del modelo.

No existe:

1 HOME
+
3 SERVICES
+
1 CONTACT
=
5

como estructura automática.

Una miniweb puede tener:

2 páginas

o:

7 páginas

o:

15 páginas

o cualquier otro número justificado.

---

53. REGLA DE MÁXIMA COBERTURA INICIAL

Durante la investigación se debe favorecer la detección de:

todas las oportunidades razonables.

Posteriormente se eliminan:

- duplicadas;
- irrelevantes;
- débiles;
- no diferenciadas;
- no comerciales;
- no verificables;
- excesivamente competitivas sin ventaja;
- incompatibles con el modelo de negocio.

Esto permite maximizar la cobertura sin caer en publicación masiva.

---

54. REGLA DE MÍNIMO VALOR

Una página solo debe sobrevivir al proceso si tiene:

- intención propia;
- utilidad;
- diferenciación;
- justificación;
- información suficiente;
- posibilidad razonable de competir.

---

55. RELACIÓN CON MOTOR DE DECISIÓN

El motor utiliza este modelo para evaluar oportunidades.

MODELO DE DATOS
↓
MOTOR DE DECISIÓN
↓
DECISIÓN

El motor no modifica arbitrariamente los datos originales.

---

56. RELACIÓN CON ARQUITECTURA

La arquitectura recibe las oportunidades autorizadas.

CANDIDATE_PAGES
↓
DECISIÓN
↓
AUTHORIZED_PAGES
↓
ARQUITECTURA

---

57. RELACIÓN CON CONTRATO IA

La IA recibe únicamente la información que corresponde a una oportunidad y arquitectura autorizadas.

MODELO DE DATOS
↓
MOTOR
↓
ARQUITECTURA
↓
CONTRATO IA
↓
GENERACIÓN

---

58. RELACIÓN CON N8N

N8N utilizará los identificadores para:

- crear;
- actualizar;
- eliminar;
- agrupar;
- relacionar;
- sincronizar.

No debe tomar decisiones SEO nuevas durante la ejecución.

---

59. REGLA DE NO INVENCIÓN

El modelo no permite inventar:

- empresas;
- profesionales;
- teléfonos;
- emails;
- direcciones;
- precios;
- horarios;
- reseñas;
- testimonios;
- certificaciones;
- garantías;
- experiencia;
- cobertura;
- estadísticas;
- datos locales;
- imágenes reales;
- resultados de búsqueda;
- autoridad;
- backlinks.

Cuando no exista evidencia:

UNKNOWN

o:

null

según el campo.

---

60. REGLA PARA DATOS FICTICIOS

Los datos ficticios solo pueden utilizarse en:

DEMO
TEST
STAGING

Nunca deben mezclarse silenciosamente con datos reales.

---

61. EJEMPLO DE OPORTUNIDAD COMPLETA

{
  "opportunity_id": "FON-FUE-001",

  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "variant": null,
    "problem": null,
    "municipality": "Fuengirola",
    "province": "Málaga",
    "country": "España"
  },

  "subservices": [
    {
      "id": "SUB-001",
      "name": "Desatascos",
      "status": "CANDIDATE"
    },
    {
      "id": "SUB-002",
      "name": "Reparación de fugas",
      "status": "CANDIDATE"
    },
    {
      "id": "SUB-003",
      "name": "Reparación de tuberías",
      "status": "CANDIDATE"
    }
  ],

  "variants": [
    {
      "id": "VAR-001",
      "name": "24 horas",
      "status": "CANDIDATE"
    }
  ],

  "problems": [],

  "candidate_pages": [],

  "authorized_pages": [],

  "groups": [],

  "evidence": [],

  "competitors": [],

  "business": {
    "mode": "DISABLED",
    "name": null,
    "phone": null,
    "whatsapp": null,
    "email": null
  },

  "history": [],

  "issues": [],

  "traceability": {}
}

Este ejemplo es estructural.

No autoriza automáticamente ninguna de las páginas mencionadas.

---

62. PRINCIPIO DE ESCALABILIDAD

El modelo debe poder manejar:

1 oportunidad
↓
N candidatos
↓
M agrupaciones
↓
K páginas autorizadas

donde:

N, M y K

son variables.

No existe un número fijo.

---

63. PRINCIPIO DE CALIDAD

La escalabilidad no consiste en:

SERVICIO × TODOS LOS PUEBLOS = PÁGINAS

La escalabilidad correcta es:

SERVICIO × LOCALIDAD
↓
INVESTIGACIÓN
↓
DESCUBRIMIENTO DE OPORTUNIDADES
↓
EVALUACIÓN
↓
DESCARTE
↓
AGRUPACIÓN
↓
AUTORIZACIÓN
↓
ARQUITECTURA
↓
GENERACIÓN

---

64. OBJETIVO

El modelo debe permitir construir un sistema capaz de investigar miles de combinaciones sin obligar a crear miles de páginas.

La automatización debe servir para:

- investigar más;
- descubrir más;
- analizar mejor;
- descartar mejor;
- construir únicamente lo que merece la pena.

---

65. CAMBIO PRINCIPAL DE VERSIÓN 4.0

La versión 4.0 introduce:

- eliminación del supuesto de cinco páginas;
- número dinámico de páginas;
- número dinámico de subservicios;
- número dinámico de variantes;
- número dinámico de candidatos;
- descubrimiento amplio antes de descartar;
- almacenamiento de oportunidades descartadas;
- agrupación explícita;
- páginas candidatas;
- páginas autorizada
