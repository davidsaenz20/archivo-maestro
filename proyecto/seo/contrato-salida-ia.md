CONTRATO DE SALIDA IA → N8N

Versión: 2.0
Estado: ACTIVO
Función: definir el contrato estructural que debe cumplir toda salida de IA destinada a N8N.

---

1. FUNCIÓN

Este documento define exactamente qué debe devolver la IA después de recibir una oportunidad previamente validada y autorizada para generación de una landing.

La salida debe ser:

- estructurada;
- predecible;
- validable;
- trazable;
- compatible con N8N;
- compatible con el modelo de datos;
- independiente de la presentación WordPress.

La IA genera contenido.

La IA no decide la arquitectura del sistema.

---

2. FLUJO OFICIAL

OPORTUNIDAD
↓
MOTOR DE DECISIÓN
↓
DECISIÓN = CREAR
↓
ARQUITECTURA URL
↓
ARQUITECTURA LANDING
↓
DATOS
↓
BLOQUES AUTORIZADOS
↓
IA
↓
JSON
↓
VALIDADOR
↓
N8N
↓
WORDPRESS

---

3. REGLA DE AUTORIDAD

La IA recibe determinados datos como información protegida.

No puede modificarlos.

Campos protegidos:

- "opportunity_id"
- "sector"
- "service"
- "subservice"
- "municipality"
- "province"
- "country"
- "decision_seo"
- "page_type"
- "url"
- "canonical"
- "authorized_blocks"
- "restrictions"

Si existe una contradicción:

1. conservar el dato recibido;
2. no sustituirlo;
3. registrar la incidencia;
4. establecer "REVIEW" cuando corresponda.

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
- estructuras no definidas.

La respuesta debe poder ser procesada automáticamente.

---

5. ESTRUCTURA PRINCIPAL

{
  "schema_version": "2.0",
  "opportunity_id": "",
  "status": "READY",
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

6. SCHEMA VERSION

Versión actual:

"2.0"

N8N debe comprobar la versión antes de procesar la respuesta.

Si no es compatible:

"ERROR"

---

7. STATUS

Valores permitidos:

"READY"

"REVIEW"

"ERROR"

READY

La salida cumple el contrato y puede pasar al siguiente proceso.

REVIEW

Existe una incidencia que requiere revisión.

ERROR

No existe una salida válida para procesar.

---

8. IDENTITY

Representa la identidad de la oportunidad.

{
  "identity": {
    "sector": "",
    "service": "",
    "subservice": null,
    "municipality": "",
    "province": "",
    "country": ""
  }
}

Los valores deben coincidir con la entrada.

La IA no puede sustituir una localidad, servicio o sector.

---

9. ARCHITECTURE

Representa la arquitectura previamente determinada.

{
  "architecture": {
    "page_type": "",
    "url": "",
    "canonical": "",
    "parent_url": null,
    "depth": 1,
    "authorized_blocks": []
  }
}

La IA no decide la arquitectura.

La URL recibida debe devolverse exactamente.

---

10. SEO

La IA genera únicamente los elementos SEO permitidos.

{
  "seo": {
    "title": "",
    "meta_description": "",
    "h1": ""
  }
}

TITLE

Debe representar la intención principal.

META DESCRIPTION

Debe describir la página de forma natural.

No puede contener promesas no respaldadas.

H1

Debe representar claramente:

- servicio;
- subservicio cuando corresponda;
- localidad.

El "slug" no se genera libremente.

La URL ya está determinada por la arquitectura.

---

11. MENU

La navegación solo puede utilizar URLs autorizadas.

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

- "current"
- "internal"
- "anchor"

No se crean enlaces hacia páginas inexistentes.

---

12. BLOQUES

La salida contiene únicamente los bloques autorizados.

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

Los identificadores deben corresponder exactamente con:

"proyecto/seo/sistema-bloques.md"

La IA no puede inventar nuevos bloques.

---

13. MAPA OFICIAL DE BLOQUES

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

El "type" debe corresponder al "id".

---

14. ENABLED

Cada bloque contiene:

"enabled": true

o:

"enabled": false

Los bloques autorizados obligatorios no deben desactivarse arbitrariamente.

Los bloques condicionales pueden omitirse cuando no exista información suficiente.

---

15. DATA

"data" contiene únicamente la información necesaria para representar el bloque.

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

16. REGLA DE BLOQUES

La IA debe respetar:

"authorized_blocks"

No puede:

- añadir bloques;
- eliminar bloques obligatorios;
- cambiar IDs;
- cambiar tipos;
- modificar la arquitectura;
- crear estructuras paralelas.

---

17. CONTENIDO

El contenido debe ser:

- específico;
- útil;
- coherente con la intención;
- basado en los datos recibidos;
- compatible con las restricciones.

No debe generarse contenido únicamente para aumentar longitud.

---

18. NO INVENCIÓN

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

si el dato es imprescindible.

---

19. CTA

La IA puede generar el texto del CTA.

No puede inventar el canal de contacto.

Ejemplo:

{
  "label": "Solicitar presupuesto",
  "action": "contact"
}

Los datos reales de contacto deben proceder del modelo de datos.

---

20. FAQ

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

21. INFORMACIÓN LOCAL

Cuando exista B09:

la información debe estar respaldada.

No se deben inventar:

- barrios;
- calles;
- urbanizaciones;
- tiempos;
- características;
- cobertura;
- necesidades locales.

Repetir el nombre del municipio no constituye información local.

---

22. COBERTURA

Cuando exista B10:

{
  "areas": []
}

Solo deben incluirse zonas realmente respaldadas.

No se generan listas masivas artificiales.

---

23. CONFIANZA

Cuando exista B12, solo se utilizan señales verificables:

- certificaciones;
- experiencia;
- garantías;
- reseñas;
- datos comerciales;
- otros elementos proporcionados.

Nunca se inventan señales de confianza.

---

24. DIFERENCIACIÓN

Cuando exista B13, debe existir una razón real para la diferenciación.

No es suficiente:

- cambiar localidad;
- cambiar sinónimos;
- reordenar párrafos;
- sustituir palabras;
- duplicar una plantilla.

---

25. SERVICIOS RELACIONADOS

B15 solo puede contener servicios existentes y autorizados.

No se crean URLs nuevas desde la IA.

---

26. LOCALIDADES RELACIONADAS

B16 solo puede utilizar localidades existentes en la arquitectura.

No se genera una red masiva de enlaces únicamente para SEO.

---

27. DATOS ESTRUCTURADOS

B17 y el campo "schema" solo pueden utilizar datos verificables.

No se inventan:

- reviews;
- ratings;
- precios;
- horarios;
- direcciones;
- empresas;
- personas.

El JSON-LD final será responsabilidad del sistema de renderizado.

---

28. TESTIMONIOS

B18 solo se utiliza cuando existen testimonios reales y autorizados.

Nunca generar testimonios ficticios.

---

29. CASOS / EJEMPLOS

B19 solo se utiliza con casos reales o ejemplos expresamente autorizados.

No se inventan trabajos realizados.

---

30. GALERÍA

B20 solo puede utilizar recursos reales disponibles.

La IA no crea URLs de imágenes inexistentes.

---

31. PRECIO

B21 solo puede utilizar precios proporcionados por la fuente de datos.

Si no existe precio:

"null"

No se inventan tarifas.

---

32. HORARIOS

B22 solo puede utilizar horarios proporcionados.

No se inventa disponibilidad.

---

33. MAPA

B23 solo se utiliza cuando existen datos válidos de ubicación.

No se inventan coordenadas, direcciones ni establecimientos.

---

34. IMAGES

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

La URL debe existir.

La IA puede describir una imagen proporcionada, pero no inventar el recurso.

---

35. INTERNAL LINKS

Formato:

{
  "internal_links": [
    {
      "url": "",
      "anchor": "",
      "target": ""
    }
  ]
}

Las URLs deben proceder de la arquitectura autorizada.

La IA no puede crear URLs arbitrarias.

---

36. VALIDATION

La IA puede devolver información de validación:

{
  "validation": {
    "valid": true,
    "checks": []
  }
}

Pero la validación definitiva corresponde al validador externo.

La IA no puede autovalidarse como autoridad final.

---

37. ISSUES

Formato:

{
  "issues": {
    "items": []
  }
}

Cada incidencia puede contener:

{
  "code": "",
  "severity": "",
  "field": "",
  "message": ""
}

La IA debe registrar problemas detectados en lugar de ocultarlos.

---

38. TRACEABILITY

La salida debe permitir rastrear su origen.

Formato conceptual:

{
  "traceability": {
    "opportunity_id": "",
    "source_version": "",
    "contract_version": "2.0"
  }
}

La trazabilidad permite identificar qué oportunidad y qué contrato generaron la salida.

---

39. REGLAS DE INTEGRIDAD

N8N debe rechazar la salida cuando:

- no sea JSON válido;
- falte "schema_version";
- falte "opportunity_id";
- falte "status";
- existan bloques no autorizados;
- existan IDs desconocidos;
- el "type" no corresponda al ID;
- la URL no coincida con la arquitectura;
- existan campos protegidos modificados;
- existan estructuras incompatibles.

Resultado:

"ERROR"

o:

"REVIEW"

según la naturaleza del problema.

---

40. IDEMPOTENCIA

El contrato debe permitir que N8N procese la misma salida sin crear duplicados.

El identificador estable es:

"opportunity_id"

La landing correspondiente debe poder localizarse mediante ese identificador o mediante el identificador estable definido por el sistema.

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

WordPress renderiza los datos estructurados.

---

42. N8N

N8N será responsable de:

- recibir JSON;
- validar;
- transformar;
- comprobar existencia;
- crear o actualizar;
- enviar a WordPress;
- registrar errores;
- registrar resultados.

N8N no debe reinterpretar arbitrariamente las decisiones SEO.

---

43. EJEMPLO MÍNIMO

Para:

Fontanero + Marbella

{
  "schema_version": "2.0",
  "opportunity_id": "FON-MARB-001",
  "status": "READY",
  "identity": {
    "sector": "fontaneria",
    "service": "fontanero",
    "subservice": null,
    "municipality": "Marbella",
    "province": "Málaga",
    "country": "España"
  },
  "architecture": {
    "page_type": "servicio_localidad",
    "url": "/fontanero/marbella/",
    "canonical": "/fontanero/marbella/",
    "parent_url": null,
    "depth": 1,
    "authorized_blocks": [
      "B01",
      "B02",
      "B03",
      "B04",
      "B05",
      "B06"
    ]
  },
  "seo": {
    "title": "Fontanero en Marbella",
    "meta_description": "Servicios de fontanería en Marbella.",
    "h1": "Fontanero en Marbella"
  },
  "menu": {
    "items": []
  },
  "blocks": [],
  "images": [],
  "internal_links": [],
  "schema": {},
  "validation": {
    "valid": true,
    "checks": []
  },
  "issues": {
    "items": []
  },
  "traceability": {
    "opportunity_id": "FON-MARB-001",
    "source_version": "",
    "contract_version": "2.0"
  }
}

El ejemplo es ilustrativo.

Los valores definitivos dependen de los datos y evidencias reales.

---

44. REGLA DE NO DECISIÓN

La IA NO DECIDE:

- si crear una página;
- qué servicio investigar;
- qué localidad crear;
- qué URL utilizar;
- qué canonical utilizar;
- qué bloques están autorizados;
- qué arquitectura aplicar;
- qué datos comerciales existen.

La IA SÍ GENERA:

- contenido;
- títulos;
- descripciones;
- preguntas;
- respuestas;
- textos de bloques;
- contenido SEO permitido;
- información derivada de datos recibidos.

---

45. RELACIÓN CON DOCUMENTOS

Este contrato debe mantenerse alineado con:

"proyecto/seo/arquitectura-seo.md"

→ arquitectura SEO.

"proyecto/seo/arquitectura-urls.md"

→ URLs.

"proyecto/seo/arquitectura-landing.md"

→ estructura funcional.

"proyecto/seo/esquema-datos.md"

→ modelo de datos.

"proyecto/seo/sistema-bloques.md"

→ B01–B23.

"proyecto/seo/integracion-n8n-wordpress.md"

→ comunicación.

La fuente de verdad de cada decisión pertenece al documento correspondiente.

No se deben crear definiciones paralelas.

---

46. RELACIÓN CON ESPECIFICACIÓN IA

"especificacion-ia.md" define el comportamiento, instrucciones y contexto de generación.

Este documento define exclusivamente:

la salida estructurada que debe cumplir la IA.

Por tanto:

ESPECIFICACIÓN IA
→ cómo debe trabajar la IA.

CONTRATO SALIDA IA
→ qué debe devolver.

No deben duplicarse sus responsabilidades.

---

47. VALIDACIÓN EXTERNA

El contrato no sustituye al validador.

La secuencia correcta es:

GENERAR
↓
VALIDAR ESTRUCTURA
↓
VALIDAR DATOS
↓
VALIDAR ARQUITECTURA
↓
VALIDAR SEO
↓
VALIDAR RESTRICCIONES
↓
N8N

Una salida "READY" de la IA no implica publicación automática.

---

48. VERSIONADO

Los cambios incompatibles deben aumentar la versión del contrato.

N8N debe poder rechazar versiones incompatibles.

No se debe modificar silenciosamente la estructura esperando que N8N la interprete.

---

49. PRINCIPIO DE ESCALABILIDAD

El mismo contrato debe poder utilizarse para:

- 1 landing;
- 10 landings;
- 100 landings;
- 1.000 landings;
- 10.000+ landings.

La estructura del contrato permanece estable.

Lo que cambia son:

- oportunidades;
- datos;
- arquitectura;
- bloques autorizados;
- contenido.

---

50. REGLA FINAL

La IA no es la fuente de verdad.

La arquitectura no es la IA.

N8N no decide el SEO.

WordPress no decide el contenido.

Cada capa ejecuta exclusivamente su responsabilidad.

El flujo definitivo es:

EVIDENCIA
↓
DECISIÓN
↓
ARQUITECTURA
↓
DATOS
↓
IA
↓
CONTRATO JSON
↓
VALIDADOR
↓
N8N
↓
WORDPRESS

---

51. CONTROL DE VERSIONES

Versión: 2.0

Fecha: 2026-08-24

Motivo: consolidación posterior a auditoría.

Cambios principales:

- separación entre especificación IA y contrato de salida;
- alineación con arquitectura SEO;
- alineación con arquitectura URL;
- alineación con arquitectura Landing;
- alineación con B01–B23;
- versión de contrato actualizada;
- refuerzo de campos protegidos;
- refuerzo de validación externa;
- refuerzo de trazabilidad;
- eliminación de decisiones autónomas de la IA;
- preparación para N8N → WordPress;
- eliminación de estructuras paralelas.

---

FIN DEL CONTRATO DE SALIDA IA → N8N
