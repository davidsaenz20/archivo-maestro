CONTRATO DE SALIDA IA → N8N

1. FUNCIÓN

Este documento define exactamente qué debe devolver la inteligencia artificial después de procesar una oportunidad SEO.

La salida de la IA debe ser estructurada y predecible para que N8N pueda:

1. recibirla;
2. validarla;
3. transformarla;
4. crear o actualizar una landing;
5. enviar los datos a WordPress;
6. registrar el resultado.

La IA no decide la estrategia SEO.

La IA recibe una oportunidad previamente procesada y genera la información necesaria para construir la landing dentro de las reglas establecidas.

---

2. PRINCIPIO FUNDAMENTAL

La IA debe devolver datos estructurados, no HTML libre.

N8N será responsable de transformar esos datos en los elementos técnicos necesarios para WordPress.

Flujo:

DATOS DE OPORTUNIDAD
↓
IA
↓
JSON ESTRUCTURADO
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
LANDING

---

3. FORMATO

La salida oficial será:

JSON

No debe contener:

- explicaciones fuera del JSON;
- Markdown;
- comentarios;
- texto antes del JSON;
- texto después del JSON;
- campos no definidos por este contrato.

---

4. REGLA DE AUTORIDAD

La IA recibe determinados campos que son de autoridad superior.

La IA no puede modificarlos.

Campos protegidos:

opportunity_id
servicio
subservicio
municipio
provincia
decision_seo
tipo_pagina
url
canonical
bloques_autorizados
restricciones

Si existe una contradicción entre los datos recibidos y lo que la IA considera conveniente, debe informar de la incidencia.

No debe modificar el dato.

---

5. ESTRUCTURA GENERAL

La respuesta tendrá esta estructura:

{
  "schema_version": "1.0",
  "opportunity_id": "",
  "status": "",
  "identity": {},
  "architecture": {},
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

6. SCHEMA_VERSION

Indica la versión del contrato utilizado.

Ejemplo:

{
  "schema_version": "1.0"
}

N8N debe poder comprobar esta versión antes de procesar la respuesta.

---

7. OPPORTUNITY_ID

Debe coincidir exactamente con el identificador recibido.

Ejemplo:

{
  "opportunity_id": "OPP-0001"
}

La IA no puede modificarlo.

---

8. STATUS

Indica si la IA ha podido completar correctamente la generación.

Valores permitidos:

READY
REVIEW
ERROR

READY

La IA ha podido generar la salida completa dentro de las reglas.

REVIEW

Existe algún problema que requiere revisión.

ERROR

No ha sido posible producir una salida válida.

---

9. IDENTITY

Representa la identidad de la landing.

{
  "identity": {
    "sector": "",
    "service": "",
    "subservice": null,
    "municipality": "",
    "province": ""
  }
}

Los valores deben coincidir con la entrada.

---

10. ARCHITECTURE

Representa la arquitectura que la IA ha recibido.

{
  "architecture": {
    "page_type": "",
    "url": "",
    "canonical": "",
    "parent_url": null
  }
}

La IA no debe crear una URL diferente.

---

11. SEO

La IA genera los elementos SEO derivados de la identidad y de las reglas.

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": "",
    "slug": ""
  }
}

title

Debe representar la intención principal.

meta_description

Debe describir la página sin promesas no respaldadas.

h1

Debe representar claramente:

- servicio;
- subservicio cuando corresponda;
- localidad.

slug

Debe coincidir con la arquitectura recibida.

---

12. EJEMPLO SEO

Entrada:

servicio = fontanero
subservicio = null
municipio = Marbella

URL:

/fontanero/marbella/

Salida:

{
  "seo": {
    "title": "Fontanero en Marbella | Servicios de fontanería",
    "meta_description": "Servicios de fontanería en Marbella para reparaciones, averías e instalaciones.",
    "h1": "Fontanero en Marbella",
    "slug": "fontanero/marbella"
  }
}

El contenido es ilustrativo.

Los textos definitivos deben respetar las evidencias y restricciones disponibles.

---

13. MENU

La IA puede devolver la estructura de navegación específica de la landing.

{
  "menu": {
    "items": []
  }
}

Cada elemento:

{
  "label": "",
  "url": "",
  "type": ""
}

Ejemplo:

{
  "menu": {
    "items": [
      {
        "label": "Fontanería",
        "url": "/fontanero/marbella/",
        "type": "current"
      },
      {
        "label": "Servicios",
        "url": "#servicios",
        "type": "anchor"
      },
      {
        "label": "Preguntas frecuentes",
        "url": "#faq",
        "type": "anchor"
      },
      {
        "label": "Contacto",
        "url": "#contacto",
        "type": "anchor"
      }
    ]
  }
}

N8N deberá validar las URLs.

La IA no debe crear enlaces a páginas que no hayan sido autorizadas.

---

14. BLOQUES

La parte principal de la respuesta será:

{
  "blocks": []
}

Cada bloque tendrá:

{
  "id": "",
  "type": "",
  "enabled": true,
  "data": {}
}

---

15. ID DEL BLOQUE

El "id" debe corresponder a un bloque definido en:

proyecto/seo/sistema-bloques.md

Ejemplo:

B01
B02
B03

La IA no puede inventar identificadores.

---

16. TYPE

El tipo debe coincidir con el bloque autorizado.

Ejemplo:

{
  "id": "B01",
  "type": "hero"
}

---

17. ENABLED

Indica si el bloque debe utilizarse.

{
  "enabled": true
}

o:

{
  "enabled": false
}

Un bloque obligatorio no puede desactivarse.

---

18. DATA

Contiene exclusivamente los datos necesarios para renderizar el bloque.

Ejemplo:

{
  "id": "B01",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "Fontanero en Marbella",
    "subtitle": "Servicios de fontanería en Marbella.",
    "cta": {
      "label": "Solicitar servicio",
      "action": "contact"
    }
  }
}

---

19. HERO

El bloque Hero puede contener:

{
  "id": "B01",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "",
    "subtitle": "",
    "cta": {
      "label": "",
      "action": ""
    }
  }
}

El título debe ser coherente con el H1.

---

20. CONTENIDO DE SERVICIO

Puede contener:

{
  "id": "B02",
  "type": "service_intro",
  "enabled": true,
  "data": {
    "title": "",
    "content": ""
  }
}

El contenido debe explicar el servicio real.

---

21. SERVICIOS

Cuando esté autorizado:

{
  "id": "B03",
  "type": "services",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

Cada servicio debe corresponder a información válida.

---

22. INFORMACIÓN LOCAL

Cuando exista información local suficiente:

{
  "id": "B04",
  "type": "local_context",
  "enabled": true,
  "data": {
    "title": "",
    "content": ""
  }
}

Si no existen datos locales suficientes:

{
  "enabled": false
}

No se deben inventar datos locales para rellenar el bloque.

---

23. COBERTURA

Cuando exista cobertura confirmada:

{
  "id": "B05",
  "type": "coverage",
  "enabled": true,
  "data": {
    "title": "",
    "areas": []
  }
}

Las zonas deben proceder de datos autorizados.

---

24. PROCESO

Cuando corresponda:

{
  "id": "B06",
  "type": "process",
  "enabled": true,
  "data": {
    "title": "",
    "steps": []
  }
}

No se deben inventar procesos comerciales.

---

25. CONFIANZA

Cuando existan datos reales:

{
  "id": "B07",
  "type": "trust",
  "enabled": true,
  "data": {
    "title": "",
    "items": []
  }
}

Solo pueden utilizarse señales verificadas.

---

26. FAQ

Cuando exista justificación:

{
  "id": "B08",
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

Las preguntas deben guardar relación con la intención.

---

27. CTA

La llamada a la acción:

{
  "id": "B09",
  "type": "cta",
  "enabled": true,
  "data": {
    "title": "",
    "text": "",
    "action": {
      "type": "",
      "label": ""
    }
  }
}

No se debe afirmar:

- disponibilidad inmediata;
- atención 24 horas;
- respuesta en X minutos;

si esos datos no están confirmados.

---

28. IMÁGENES

La IA puede devolver necesidades de imagen:

{
  "images": [
    {
      "id": "",
      "location": "",
      "description": "",
      "alt": "",
      "source_required": true
    }
  ]
}

La IA no debe inventar URLs de imágenes.

---

29. ENLACES INTERNOS

{
  "internal_links": [
    {
      "url": "",
      "anchor": "",
      "type": ""
    }
  ]
}

Los enlaces deben proceder de URLs disponibles o autorizadas.

Si una URL no está confirmada:

no incluir

---

30. SCHEMA

Los datos estructurados se devolverán como:

{
  "schema": {
    "type": "",
    "data": {}
  }
}

Solo se utilizarán tipos y datos que sean realmente aplicables.

No se deben fabricar:

- reviews;
- ratings;
- precios;
- horarios;
- empresas;
- direcciones.

---

31. VALIDATION

La IA debe devolver información que permita a N8N comprobar problemas.

{
  "validation": {
    "result": "",
    "warnings": [],
    "required_review": false
  }
}

Valores de "result":

READY
REVIEW
ERROR

---

32. ISSUES

Las incidencias se devolverán así:

{
  "issues": {
    "items": []
  }
}

Cada incidencia:

{
  "code": "",
  "field": "",
  "description": "",
  "severity": ""
}

Severidad:

low
medium
high
critical

---

33. REGLA DE DATOS FALTANTES

Cuando un dato necesario no exista, la IA debe:

1. utilizar "null" cuando corresponda;
2. omitir el bloque si es opcional;
3. solicitar revisión si el dato es obligatorio;
4. registrar una incidencia cuando sea necesario.

Nunca debe inventar el dato.

---

34. REGLA DE BLOQUES OBLIGATORIOS

Si falta información para un bloque obligatorio:

required_review = true

y debe registrarse una incidencia.

La IA no debe rellenarlo con información inventada.

---

35. REGLA DE BLOQUES CONDICIONALES

Un bloque condicional solo debe aparecer cuando:

- existe la información necesaria;
- la intención lo justifica;
- las reglas del bloque lo permiten.

---

36. REGLA DE BLOQUES OPCIONALES

Los bloques opcionales deben utilizarse únicamente cuando aporten valor real.

No deben añadirse para aumentar artificialmente la longitud.

---

37. REGLA DE URL

La IA recibe:

url = /fontanero/marbella/

Debe devolver exactamente:

url = /fontanero/marbella/

Nunca:

/fontanero/desatascos/marbella/

si el "subservicio" recibido es "null".

---

38. REGLA DE IDENTIDAD

Si recibe:

servicio = fontanero
municipio = Marbella

debe mantener:

fontanero
Marbella

No puede sustituirlos por:

fontanería
Puerto Banús
Estepona

salvo que esos datos formen parte explícita de información autorizada.

---

39. REGLA DE NO INVENCIÓN

Está prohibido inventar:

teléfonos
WhatsApp
emails
direcciones
precios
horarios
empresas
técnicos
certificaciones
años de experiencia
garantías
reseñas
valoraciones
zonas de cobertura

---

40. REGLA DE CONTENIDO LOCAL

El nombre del municipio por sí solo no constituye contenido local suficiente.

La IA solo debe utilizar información local cuando exista evidencia disponible.

---

41. REGLA DE DIFERENCIACIÓN

El contenido debe ser específico para la oportunidad.

No se debe limitar a:

reemplazar "Marbella"

dentro de una plantilla genérica.

---

42. REGLA DE CONSISTENCIA

Debe comprobarse que:

identity.service

coincide con:

architecture
seo
blocks

y que:

architecture.url

coincide con:

seo.slug

cuando corresponda.

---

43. TRAZABILIDAD

La salida debe conservar:

{
  "traceability": {
    "schema_version": "1.0",
    "prompt_version": "",
    "source_opportunity_id": "",
    "generated_at": ""
  }
}

---

44. EJEMPLO COMPLETO

Entrada:

servicio = fontanero
subservicio = null
municipio = Marbella
provincia = Málaga
decision_seo = CREAR
url = /fontanero/marbella/

Salida conceptual:

{
  "schema_version": "1.0",
  "opportunity_id": "OPP-0001",
  "status": "READY",

  "identity": {
    "sector": "fontanería",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Marbella",
    "province": "Málaga"
  },

  "architecture": {
    "page_type": "servicio_localidad",
    "url": "/fontanero/marbella/",
    "canonical": "/fontanero/marbella/",
    "parent_url": "/fontanero/"
  },

  "seo": {
    "title": "Fontanero en Marbella | Servicios de fontanería",
    "meta_description": "Servicios de fontanería en Marbella para reparaciones, averías e instalaciones.",
    "h1": "Fontanero en Marbella",
    "slug": "fontanero/marbella"
  },

  "menu": {
    "items": [
      {
        "label": "Fontanería",
        "url": "/fontanero/marbella/",
        "type": "current"
      },
      {
        "label": "Servicios",
        "url": "#servicios",
        "type": "anchor"
      },
      {
        "label": "Preguntas frecuentes",
        "url": "#faq",
        "type": "anchor"
      },
      {
        "label": "Contacto",
        "url": "#contacto",
        "type": "anchor"
      }
    ]
  },

  "blocks": [
    {
      "id": "B01",
      "type": "hero",
      "enabled": true,
      "data": {
        "title": "Fontanero en Marbella",
        "subtitle": "Servicios de fontanería para necesidades de reparación, mantenimiento e instalación.",
        "cta": {
          "label": "Solicitar servicio",
          "action": "contact"
        }
      }
    },
    {
      "id": "B02",
      "type": "service_intro",
      "enabled": true,
      "data": {
        "title": "Servicios de fontanería en Marbella",
        "content": ""
      }
    },
    {
      "id": "B03",
      "type": "services",
      "enabled": true,
      "data": {
        "title": "Servicios de fontanería",
        "items": []
      }
    },
    {
      "id": "B04",
      "type": "local_context",
      "enabled": false,
      "data": {}
    },
    {
      "id": "B05",
      "type": "coverage",
      "enabled": false,
      "data": {}
    },
    {
      "id": "B06",
      "type": "process",
      "enabled": false,
      "data": {}
    },
    {
      "id": "B07",
      "type": "trust",
      "enabled": false,
      "data": {}
    },
    {
      "id": "B08",
      "type": "faq",
      "enabled": true,
      "data": {
        "title": "Preguntas frecuentes sobre fontanería",
        "items": []
      }
    },
    {
      "id": "B09",
      "type": "cta",
      "enabled": true,
      "data": {
        "title": "¿Necesitas un fontanero en Marbella?",
        "text": "Contacta para solicitar información sobre el servicio.",
        "action": {
          "type": "contact",
          "label": "Contactar"
        }
      }
    }
  ],

  "images": [],

  "internal_links": [],

  "schema": {
    "type": "",
    "data": {}
  },

  "validation": {
    "result": "READY",
    "warnings": [],
    "required_review": false
  },

  "issues": {
    "items": []
  },

  "traceability": {
    "schema_version": "1.0",
    "prompt_version": "",
    "source_opportunity_id": "OPP-0001",
    "generated_at": ""
  }
}

Este ejemplo es ilustrativo: los textos y datos definitivos deben generarse utilizando la información real disponible.

---

45. RESPONSABILIDAD DE N8N

N8N no debe asumir que la respuesta de la IA es válida simplemente porque tiene formato JSON.

Debe comprobar:

1. JSON válido.
2. "schema_version" compatible.
3. "opportunity_id" correcto.
4. URL correcta.
5. identidad correcta.
6. bloques autorizados.
7. campos obligatorios.
8. ausencia de errores críticos.
9. resultado de validación.
10. restricciones.

---

46. RESPUESTA INVÁLIDA

Si la IA devuelve:

JSON inválido

o modifica un campo protegido:

url
decision_seo
municipio
servicio

N8N debe detener el flujo.

No debe publicar.

Debe registrar una incidencia.

---

47. PUBLICACIÓN

La IA no publica.

La IA devuelve datos.

N8N decide si la salida supera las comprobaciones necesarias y, posteriormente, puede enviarla a WordPress.

---

48. WORDPRESS

La conversión:

JSON
↓
WordPress

será responsabilidad de N8N y de la lógica de integración definida posteriormente.

Este contrato no define todavía:

- endpoints;
- autenticación;
- IDs de WordPress;
- campos personalizados;
- Gutenberg;
- Elementor;
- plantillas concretas.

Eso pertenecerá al documento de integración N8N → WordPress.

---

49. REGLA DE VERSIONADO

Cuando se modifique este contrato deberá aumentar:

schema_version

Ejemplo:

1.0
↓
1.1

o:

1.0
↓
2.0

según la importancia del cambio.

N8N deberá conocer qué versiones acepta.

---

50. REGLA DE COMPATIBILIDAD

Los documentos:

esquema-datos.md
arquitectura-landing.md
sistema-bloques.md
especificacion-ia.md
contrato-salida-ia.md

deben mantenerse coherentes.

Si un campo se modifica en el contrato, debe comprobarse su correspondencia en el esquema de datos y en la especificación de IA.

---

51. REGLA DE ESCALABILIDAD

El contrato debe funcionar igual para:

1 landing
5 landings
100 landings
1.000 landings
10.000 landings

N8N debe poder procesar cada oportunidad de forma independiente utilizando el mismo contrato.

---

52. REGLA DE OPORTUNIDAD CON SUBSERVICIO

Si:

service = fontanero
subservice = desatascos
municipality = Marbella

la URL recibida podría ser:

/fontanero/desatascos/marbella/

y la landing debe representar específicamente esa intención.

---

53. REGLA DE OPORTUNIDAD SIN SUBSERVICIO

Si:

service = fontanero
subservice = null
municipality = Marbella

la URL será:

/fontanero/marbella/

La landing debe representar la intención general de fontanería/servicio de fontanero en Marbella.

La IA no puede convertirla por iniciativa propia en:

/fontanero/desatascos/marbella/

---

54. REGLA FINAL

La IA genera contenido.

N8N orquesta.

WordPress publica.

El motor decide.

La arquitectura determina la URL.

El sistema de bloques determina qué componentes pueden utilizarse.

La validación determina si la salida puede continuar.

Ningún componente debe asumir las funciones estratégicas de otro.

---

55. ESTADO DEL DOCUMENTO

DEFINIDO

Este documento constituye el contrato inicial de comunicación entre IA y N8N.

Antes de utilizarlo en producción deberá comprobarse conjuntamente con:

- esquema de datos;
- sistema de bloques;
- arquitectura de landing;
- especificación de IA;
- arquitectura de URLs;
- validación;
- integración N8N → WordPress.
