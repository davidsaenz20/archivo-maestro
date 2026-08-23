# CONTRATO DE SALIDA IA → N8N

## 1. FUNCIÓN

Este documento define exactamente qué debe devolver la inteligencia artificial después de recibir una oportunidad previamente validada y autorizada para generación de landing.

La salida debe ser estructurada, predecible y validable.

N8N utilizará esta salida para:

1. recibir los datos;
2. validar la estructura;
3. comprobar restricciones;
4. transformar los bloques;
5. preparar la landing;
6. enviar los datos a WordPress;
7. registrar el resultado.

La IA no decide:

- si existe una oportunidad;
- si debe crearse una página;
- la estructura de la URL;
- los bloques que han sido autorizados;
- los datos comerciales que no hayan sido proporcionados.

La IA genera contenido y datos únicamente dentro de las reglas recibidas.

---

## 2. FLUJO

El flujo oficial es:

OPORTUNIDAD

↓

MOTOR DE DECISIÓN

↓

DECISIÓN = CREAR

↓

URL

↓

ARQUITECTURA DE LANDING

↓

BLOQUES AUTORIZADOS

↓

DATOS DE ENTRADA

↓

IA

↓

JSON

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS

↓

LANDING

---

## 3. FORMATO DE SALIDA

La salida oficial es:

JSON válido.

No puede existir ningún contenido fuera del JSON.

No se permite:

- Markdown fuera del JSON;
- explicaciones;
- comentarios;
- texto antes del JSON;
- texto después del JSON;
- campos arbitrarios no definidos por este contrato.

La salida debe poder ser procesada automáticamente.

---

## 4. AUTORIDAD DE LOS DATOS

La IA recibe datos que tienen autoridad superior.

La IA no puede modificarlos.

Campos protegidos:

- opportunity_id
- sector
- servicio
- subservicio
- municipio
- provincia
- decision_seo
- tipo_pagina
- url
- canonical
- bloques_autorizados
- restricciones

Si existe una contradicción:

1. la IA mantiene el dato recibido;
2. no lo sustituye;
3. registra una incidencia;
4. puede establecer el estado como REVIEW.

---

## 5. ESTRUCTURA GENERAL

La salida tendrá esta estructura:

{
  "schema_version": "1.1",
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

## 6. SCHEMA_VERSION

Identifica la versión del contrato.

Versión actual:

1.1

N8N debe comprobar esta versión antes de procesar la respuesta.

Si la versión no es compatible:

status = ERROR

---

## 7. STATUS

Valores permitidos:

READY

REVIEW

ERROR

### READY

La salida es válida y puede continuar hacia la siguiente fase.

### REVIEW

Existe una incidencia que requiere revisión antes de publicar.

### ERROR

No se ha podido generar una salida válida.

---

## 8. IDENTITY

Representa la identidad de la oportunidad.

Estructura:

{
  "identity": {
    "sector": "",
    "service": "",
    "subservice": null,
    "municipality": "",
    "province": ""
  }
}

Los valores deben coincidir con los datos recibidos.

La IA no puede sustituir una localidad por otra.

---

## 9. ARCHITECTURE

Representa la arquitectura previamente determinada.

Estructura:

{
  "architecture": {
    "page_type": "",
    "url": "",
    "canonical": "",
    "parent_url": null
  }
}

La IA no decide la arquitectura.

La URL recibida debe devolverse exactamente.

---

## 10. SEO

La IA genera los elementos SEO de la página dentro de las restricciones recibidas.

Estructura:

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": "",
    "slug": ""
  }
}

### TITLE

Debe representar la intención principal.

### META DESCRIPTION

Debe describir la página de forma natural.

No puede contener promesas no respaldadas.

### H1

Debe representar claramente:

- servicio;
- subservicio cuando corresponda;
- localidad.

### SLUG

Debe coincidir exactamente con la URL autorizada.

---

## 11. EJEMPLO SEO

Entrada:

servicio = fontanero

subservicio = null

municipio = Marbella

url = /fontanero/marbella/

Salida:

{
  "seo": {
    "title": "Fontanero en Marbella",
    "meta_description": "Información y servicios de fontanería en Marbella.",
    "h1": "Fontanero en Marbella",
    "slug": "fontanero/marbella"
  }
}

El ejemplo es ilustrativo.

Los textos definitivos dependerán de las evidencias y restricciones disponibles.

---

## 12. MENU

La IA puede devolver elementos de navegación únicamente cuando las URLs estén autorizadas.

Estructura:

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

Tipos permitidos:

- current
- internal
- anchor

No se deben crear enlaces hacia páginas inexistentes o no autorizadas.

---

# 13. BLOQUES

La respuesta contiene los bloques seleccionados previamente por el sistema.

Estructura:

{
  "blocks": [
    {
      "id": "",
      "type": "",
      "enabled": true,
      "data": {}
    }
  ]
}

Los identificadores deben corresponder exactamente a:

`proyecto/seo/sistema-bloques.md`

La IA no puede inventar nuevos identificadores.

---

# 14. MAPA OFICIAL DE BLOQUES

Los identificadores oficiales son:

B01 = HEADER

B02 = NAVEGACIÓN

B03 = HERO

B04 = CONTENIDO PRINCIPAL

B05 = CTA PRINCIPAL

B06 = FOOTER

B07 = SUBSERVICIO

B08 = PROBLEMAS / NECESIDADES

B09 = INFORMACIÓN LOCAL

B10 = ZONAS / COBERTURA

B11 = PROCESO

B12 = ELEMENTOS DE CONFIANZA

B13 = DIFERENCIACIÓN

B14 = FAQ

B15 = SERVICIOS RELACIONADOS

B16 = LOCALIDADES RELACIONADAS

B17 = DATOS ESTRUCTURADOS

B18 = TESTIMONIOS

B19 = CASOS / EJEMPLOS

B20 = GALERÍA

B21 = PRECIO / TARIFAS

B22 = HORARIOS

B23 = MAPA / UBICACIÓN

Este mapa es vinculante.

No se deben reutilizar identificadores para funciones diferentes.

---

# 15. TYPE DE LOS BLOQUES

El campo `type` debe utilizar valores estables.

Mapa oficial:

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

El `type` debe corresponder al `id`.

Ejemplo correcto:

{
  "id": "B03",
  "type": "hero"
}

Ejemplo incorrecto:

{
  "id": "B01",
  "type": "hero"
}

---

# 16. ENABLED

Cada bloque tendrá:

{
  "enabled": true
}

o:

{
  "enabled": false
}

Los bloques obligatorios no pueden desactivarse salvo que el sistema de validación determine que existe una imposibilidad técnica que requiere revisión.

Los bloques condicionales y opcionales pueden omitirse cuando no exista información suficiente.

---

# 17. DATA

El campo `data` contiene únicamente la información necesaria para representar el bloque.

Ejemplo:

{
  "id": "B03",
  "type": "hero",
  "enabled": true,
  "data": {
    "title": "Fontanero en Marbella",
    "subtitle": "Servicios de fontanería en Marbella.",
    "cta": {
      "label": "Contactar",
      "action": "contact"
    }
  }
}

---

# 18. B01 — HEADER

Estructura conceptual:

{
  "id": "B01",
  "type": "header",
  "enabled": true,
  "data": {
    "logo": "",
    "brand": "",
    "navigation": [],
    "cta": null
  }
}

El header es global.

No debe cambiar artificialmente por localidad.

---

# 19. B02 — NAVEGACIÓN

Estructura:

{
  "id": "B02",
  "type": "navigation",
  "enabled": true,
  "data": {
    "items": []
  }
}

Solo se utilizarán enlaces autorizados.

---

# 20. B03 — HERO

Estructura:

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

El hero debe identificar claramente la intención principal.

---

# 21. B04 — CONTENIDO PRINCIPAL

Estructura:

{
  "id": "B04",
  "type": "main_content",
  "enabled": true,
  "data": {
    "title": "",
    "content": ""
  }
}

Debe explicar el servicio o necesidad principal.

No debe convertirse en texto genérico repetido.

---

# 22. B05 — CTA PRINCIPAL

Estructura:

{
  "id": "B05",
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

No se pueden inventar:

- teléfonos;
- WhatsApp;
- disponibilidad;
- tiempos de respuesta;
- precios.

---

# 23. B06 — FOOTER

Estructura:

{
  "id": "B06",
  "type": "footer",
  "enabled": true,
  "data": {
    "links": [],
    "legal": []
  }
}

No debe utilizarse para generar una red artificial de enlaces.

---

# 24. B07 — SUBSERVICIO

Solo se utiliza cuando la oportunidad contiene un subservicio autorizado.

Ejemplo:

Fontanero + Desatascos + Marbella

No se utiliza para introducir keywords adicionales.

---

# 25. B08 — PROBLEMAS / NECESIDADES

Solo se utiliza cuando existen necesidades relevantes respaldadas por información.

Ejemplo:

- atascos;
- obstrucciones;
- problemas de desagüe.

No se deben inventar problemas.

---

# 26. B09 — INFORMACIÓN LOCAL

Solo se utiliza cuando existen datos locales útiles y verificables.

No basta con mencionar repetidamente el nombre de la localidad.

No se deben inventar:

- barrios;
- calles;
- características urbanas;
- tiempos de desplazamiento;
- zonas;
- particularidades locales.

---

# 27. B10 — ZONAS / COBERTURA

Solo se utiliza cuando existe información real de cobertura.

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

No se deben generar listas artificiales.

---

# 28. B11 — PROCESO

Solo se utiliza cuando existe información suficiente para explicar el proceso.

No se deben inventar procedimientos comerciales.

---

# 29. B12 — ELEMENTOS DE CONFIANZA

Solo se utiliza con información verificable.

No se deben inventar:

- años de experiencia;
- certificaciones;
- garantías;
- reseñas;
- valoraciones;
- número de trabajos;
- disponibilidad.

---

# 30. B13 — DIFERENCIACIÓN

Solo se utiliza cuando existe información realmente diferenciadora.

La diferenciación no puede consistir únicamente en cambiar:

"Marbella"

por:

"Estepona"

Tampoco puede consistir únicamente en cambiar sinónimos o reordenar párrafos.

---

# 31. B14 — FAQ

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

Las preguntas deben estar relacionadas con la intención real.

Las respuestas deben poder justificarse.

---

# 32. B15 — SERVICIOS RELACIONADOS

Solo se utiliza cuando existen servicios relacionados y URLs autorizadas.

No se deben crear enlaces hacia páginas inexistentes.

---

# 33. B16 — LOCALIDADES RELACIONADAS

Solo se utiliza cuando existen localidades relacionadas dentro de la arquitectura real.

No se deben generar cientos de localidades automáticamente.

---

# 34. B17 — DATOS ESTRUCTURADOS

Solo se genera cuando el tipo de página y los datos disponibles permiten utilizar datos estructurados válidos.

No se deben inventar:

- reviews;
- ratings;
- precios;
- horarios;
- direcciones;
- empresas.

---

# 35. B18 — TESTIMONIOS

Solo se utiliza con testimonios reales y autorizados.

Nunca generar testimonios ficticios.

---

# 36. B19 — CASOS / EJEMPLOS

Solo se utiliza cuando existen casos reales o ejemplos documentados.

Nunca inventar trabajos realizados.

---

# 37. B20 — GALERÍA

Solo se utiliza cuando existen imágenes reales y relevantes.

La IA no debe inventar URLs de imágenes.

---

# 38. B21 — PRECIO / TARIFAS

Solo se utiliza con precios reales y autorizados.

Nunca inventar tarifas.

---

# 39. B22 — HORARIOS

Solo se utiliza con horarios reales y autorizados.

Nunca inferir horarios.

---

# 40. B23 — MAPA / UBICACIÓN

Solo se utiliza con información de ubicación válida.

Nunca inventar direcciones.

---

# 41. IMÁGENES

La IA puede solicitar imágenes mediante:

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

# 42. ENLACES INTERNOS

Estructura:

{
  "internal_links": [
    {
      "url": "",
      "anchor": "",
      "type": ""
    }
  ]
}

Solo se incluyen URLs autorizadas.

---

# 43. SCHEMA

Estructura:

{
  "schema": {
    "type": "",
    "data": {}
  }
}

Solo se utilizarán datos estructurados válidos.

---

# 44. VALIDATION

Estructura:

{
  "validation": {
    "result": "",
    "warnings": [],
    "required_review": false
  }
}

Valores permitidos:

READY

REVIEW

ERROR

---

# 45. ISSUES

Estructura:

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

- low
- medium
- high
- critical

---

# 46. DATOS FALTANTES

Cuando falte información:

1. utilizar `null` cuando corresponda;
2. omitir bloques condicionales u opcionales;
3. generar REVIEW si la ausencia impide completar correctamente un bloque obligatorio;
4. registrar la incidencia.

Nunca inventar el dato.

---

# 47. REGLA DE NO INVENCIÓN

Está prohibido inventar:

- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- empresas;
- técnicos;
- certificaciones;
- años de experiencia;
- garantías;
- reseñas;
- valoraciones;
- zonas de cobertura;
- testimonios;
- casos reales;
- imágenes reales;
- datos comerciales.

---

# 48. REGLA DE IDENTIDAD

Si recibe:

servicio = fontanero

municipio = Marbella

debe mantener:

fontanero

Marbella

No puede sustituirlos por otra localidad o servicio.

---

# 49. REGLA DE URL

Si recibe:

url = /fontanero/marbella/

debe devolver:

/fontanero/marbella/

No puede crear:

/fontanero/desatascos/marbella/

salvo que esa sea exactamente la URL recibida y autorizada.

La IA nunca decide la URL.

---

# 50. REGLA DE CANONICAL

El canonical recibido debe mantenerse.

La IA no puede inventar un canonical alternativo.

---

# 51. REGLA DE DIFERENCIACIÓN

La página debe responder a la oportunidad concreta.

No es suficiente:

- cambiar el municipio;
- cambiar el título;
- cambiar sinónimos;
- cambiar el orden de los párrafos;
- generar texto diferente sin datos diferentes.

La diferenciación debe proceder de la información disponible y autorizada.

---

# 52. REGLA DE CONTENIDO LOCAL

El nombre de una localidad no constituye por sí mismo contenido local.

Si no existe información local suficiente:

- no inventar;
- no rellenar artificialmente;
- omitir el bloque local cuando sea condicional;
- registrar la ausencia cuando sea relevante.

---

# 53. REGLA DE BLOQUES AUTORIZADOS

La IA solo puede utilizar los bloques incluidos en:

`bloques_autorizados`

Si un bloque no está autorizado:

no debe aparecer.

---

# 54. REGLA DE BLOQUES OBLIGATORIOS

Los bloques obligatorios definidos por la arquitectura deben aparecer salvo imposibilidad que requiera revisión.

La ausencia de información no autoriza a inventar contenido.

---

# 55. REGLA DE BLOQUES CONDICIONALES

Un bloque condicional solo aparece cuando:

- está autorizado;
- existe información suficiente;
- la intención lo justifica;
- el bloque aporta valor.

---

# 56. REGLA DE BLOQUES OPCIONALES

Los bloques opcionales solo se utilizan cuando aportan valor real.

No deben utilizarse para aumentar:

- longitud;
- palabras;
- headings;
- keywords;
- enlaces.

---

# 57. REGLA DE ENLACES

No se deben crear enlaces a URLs inexistentes.

Las URLs deben proceder de:

- arquitectura;
- datos recibidos;
- URLs autorizadas.

---

# 58. REGLA DE CONTENIDO

El contenido debe:

- ser útil;
- ser comprensible;
- responder a la intención;
- respetar las evidencias;
- respetar las restricciones;
- evitar afirmaciones no verificadas;
- evitar contenido artificialmente repetitivo.

---

# 59. REGLA DE IA

La IA no sustituye:

- investigación;
- motor de decisión;
- arquitectura SEO;
- arquitectura de URL;
- selección de oportunidades.

La IA trabaja después de que estas capas hayan tomado sus decisiones.

---

# 60. TRAZABILIDAD

La salida debe conservar información suficiente para saber qué versión del sistema generó el contenido.

Estructura:

{
  "traceability": {
    "contract_version": "1.1",
    "engine_version": "",
    "source_date": "",
    "generated_at": ""
  }
}

---

# 61. VALIDACIÓN FINAL

Antes de considerar una salida como READY deben comprobarse como mínimo:

1. JSON válido.
2. `schema_version` válida.
3. `opportunity_id` correcto.
4. identidad correcta.
5. URL correcta.
6. canonical correcto.
7. bloques autorizados.
8. IDs de bloques válidos.
9. tipos de bloques correctos.
10. ausencia de datos inventados.
11. ausencia de URLs no autorizadas.
12. contenido coherente con la oportunidad.
13. restricciones respetadas.
14. incidencias correctamente registradas.

---

# 62. RESULTADO

Si todas las condiciones se cumplen:

status = READY

Si existe una incidencia que requiere revisión:

status = REVIEW

Si la salida no puede procesarse correctamente:

status = ERROR

---

# 63. PRINCIPIO FINAL

La IA no debe intentar completar información que el sistema no posee.

Es preferible:

OMITIR

o:

REVIEW

antes que:

INVENTAR.

El sistema debe priorizar:

VERACIDAD

↓

TRAZABILIDAD

↓

UTILIDAD

↓

ESCALABILIDAD

---

# 64. CONTROL DE VERSIONES

Versión actual:

1.1

Fecha:

2026-08-23

Motivo:

Alineación del contrato de salida IA → N8N con el identificador oficial de bloques definido en `sistema-bloques.md`.

Cambio principal:

Se establece un mapa único y vinculante entre:

ID DEL BLOQUE

TYPE

FUNCIÓN

La versión anterior utilizaba identificadores incompatibles con el sistema oficial de bloques.

Esta versión corrige dicha incompatibilidad.

---
