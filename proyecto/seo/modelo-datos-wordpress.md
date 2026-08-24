Ha pensado durante 16s

MODELO DE DATOS WORDPRESS

Versión: 2.0
Estado: Preparado para implementación piloto
Proyecto: Plataforma de landings locales automatizadas

---

1. FUNCIÓN

Este documento define cómo se representa en WordPress la información de una landing ya validada.

No define:

- estrategia SEO;
- generación de contenido;
- bloques;
- arquitectura general de WordPress;
- comunicación N8N;
- diseño visual.

WordPress recibe datos estructurados y los almacena para que el sistema de renderizado pueda convertirlos en una página.

---

2. FLUJO DE DATOS

MODELO DE DATOS COMÚN
        ↓
CONTRATO IA
        ↓
VALIDACIÓN
        ↓
N8N
        ↓
MODELO WORDPRESS
        ↓
RENDERIZADOR
        ↓
PLANTILLAS
        ↓
PÁGINA

---

3. ENTIDAD PRINCIPAL

Entidad conceptual:

Landing

Implementación prevista inicialmente:

Custom Post Type: landing

Cada registro representa una landing lógica.

El ID interno de WordPress no será la identidad principal del sistema.

---

4. IDENTIDAD LÓGICA

Cada landing deberá conservar:

site_id
opportunity_id
page_id

Ejemplo:

site_id: malaga
opportunity_id: fontanero-estepona
page_id: FON-EST-HOME

Regla

"page_id" debe ser estable e idempotente.

No debe cambiar porque WordPress cambie su ID interno.

---

5. IDENTIDAD WORDPRESS

WordPress puede tener:

wordpress_post_id

Este valor es únicamente técnico.

Ejemplo:

page_id:
FON-EST-HOME

wordpress_post_id:
1847

La relación será:

page_id
    ↓
wordpress_post_id

---

6. IDENTIDAD GEOGRÁFICA Y DE SERVICIO

Campos:

sector
servicio
subservicio
pais
comunidad_autonoma
provincia
municipio
localidad
intencion

Ejemplo:

{
  "sector": "servicios",
  "servicio": "fontanero",
  "subservicio": null,
  "pais": "España",
  "comunidad_autonoma": "Andalucía",
  "provincia": "Málaga",
  "municipio": "Estepona",
  "localidad": "Estepona",
  "intencion": "local_service"
}

La IA no puede alterar la identidad estratégica definida por la arquitectura.

---

7. URL

Campos:

slug
url
canonical
url_tipo

Ejemplo:

slug:
fontanero-estepona

url:
https://dominio.com/fontanero/estepona/

canonical:
https://dominio.com/fontanero/estepona/

La URL estratégica procede de la arquitectura y no debe ser modificada arbitrariamente por WordPress.

---

8. VERSIONADO

Cada landing tendrá:

page_version

Cada instancia de bloque tendrá:

block_version

Ejemplo:

page_version: 4

block_version: 2

El versionado lógico es independiente del sistema de revisiones visuales de WordPress.

---

9. ESTADO

Estado lógico de la landing:

draft
published
unpublished
archived

Durante el piloto:

CREATE
 ↓
draft
 ↓
verificación
 ↓
published

---

10. SEO

Campos conceptuales:

seo.title
seo.meta_description
seo.canonical
seo.robots

Ejemplo:

{
  "title": "Fontanero en Estepona | Servicio profesional",
  "meta_description": "Servicio de fontanería en Estepona...",
  "canonical": "https://dominio.com/fontanero/estepona/",
  "robots": "index,follow"
}

La implementación concreta dependerá del sistema SEO utilizado en WordPress.

---

11. BLOQUES

La landing tendrá:

blocks[]

Cada instancia deberá conservar:

block_id
block_instance_id
block_version
position
enabled
data

Ejemplo:

{
  "block_id": "B03",
  "block_instance_id": "FON-EST-HOME-B03-01",
  "block_version": 1,
  "position": 3,
  "enabled": true,
  "data": {
    "h1": "Fontanero en Estepona",
    "subtitle": "Servicio de fontanería en Estepona",
    "cta": {}
  }
}

---

12. BLOCK_ID

Los identificadores autorizados son:

B01
B02
B03
B04
B05
B06
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

Su definición funcional pertenece exclusivamente a:

sistema-bloques.md

La IA no puede crear nuevos "block_id".

---

13. BLOCK_INSTANCE_ID

"block_instance_id" identifica una instancia concreta de un bloque.

Ejemplo:

FON-EST-HOME-B14-01

Si la misma página contiene tres FAQ independientes:

FON-EST-HOME-B14-01
FON-EST-HOME-B14-02
FON-EST-HOME-B14-03

Esto permite actualizar una instancia concreta sin reconstruir toda la página.

---

14. POSICIÓN

Cada bloque tendrá:

position

Ejemplo:

B03 → position 3
B04 → position 4
B05 → position 5

La posición define el orden lógico de renderizado.

---

15. ENABLED

Cada instancia podrá tener:

enabled: true

o:

enabled: false

Cuando sea "false", el renderizador no debe mostrar el bloque.

La instancia no se elimina.

Esto permite desactivación temporal.

---

16. DATOS DEL BLOQUE

Cada bloque tendrá un objeto:

data

Su estructura dependerá de "block_id".

Ejemplo:

{
  "block_id": "B14",
  "data": {
    "items": [
      {
        "question": "¿Trabajáis en Estepona?",
        "answer": "Sí, ofrecemos servicio en Estepona."
      }
    ]
  }
}

No todos los bloques tendrán los mismos campos.

---

17. FAQ

Estructura:

faq[]

Cada elemento:

question
answer

Las respuestas deben proceder de información validada.

No se deben inventar datos comerciales.

---

18. CTA

Estructura:

cta:
  type
  text
  destination

Tipos posibles:

whatsapp
phone
contact
quote
appointment

El destino debe estar validado.

No se deben inventar teléfonos, WhatsApp, emails ni URLs.

---

19. INTERLINKING

La landing tendrá:

internal_links[]

Cada enlace podrá contener:

source_block_instance_id
target_page_id
url
anchor
type
reason
enabled

Ejemplo:

{
  "source_block_instance_id": "FON-EST-HOME-B16-01",
  "target_page_id": "FON-MAN-HOME",
  "url": "/fontanero/manilva/",
  "anchor": "Fontanero en Manilva",
  "type": "related_location",
  "reason": "localidad relacionada",
  "enabled": true
}

Solo se deben utilizar destinos existentes o validados.

---

20. IMÁGENES

Estructura:

images[]

Campos:

id
url
alt
title
type
source
license
wordpress_media_id

"wordpress_media_id" puede añadirse cuando el recurso haya sido incorporado a la Media Library.

No se deben inventar recursos.

---

21. DATOS ESTRUCTURADOS

Campo:

schema

Debe contener únicamente datos estructurados válidos y autorizados.

El renderizador podrá convertirlos en JSON-LD.

No se deben fabricar datos para completar campos obligatorios.

---

22. DATOS COMERCIALES

Cuando existan datos reales:

empresa
marca
telefono
whatsapp
email
direccion
horarios
precio
garantia
experiencia
certificaciones

Regla:

dato no disponible
       ↓
null / omitido

Nunca:

dato no disponible
       ↓
inventar

---

23. DATOS INTERNOS

Podrán almacenarse para trazabilidad:

sources
evidence
confidence
restrictions
validation_errors
validation_warnings
generation_date
validation_date

Estos datos no deben aparecer en la página pública salvo que exista una regla explícita.

---

24. METADATOS DE CONTROL

El sistema podrá conservar:

schema_version
validator_version
model_version
generated_at
validated_at
last_updated_at

Sirven para auditoría y control técnico.

---

25. ESTRUCTURA CONCEPTUAL COMPLETA

{
  "site_id": "malaga",
  "opportunity_id": "fontanero-estepona",
  "page_id": "FON-EST-HOME",
  "wordpress_post_id": 1847,

  "identity": {
    "sector": "servicios",
    "servicio": "fontanero",
    "subservicio": null,
    "pais": "España",
    "comunidad_autonoma": "Andalucía",
    "provincia": "Málaga",
    "municipio": "Estepona",
    "localidad": "Estepona",
    "intencion": "local_service"
  },

  "url": {
    "slug": "fontanero-estepona",
    "url": "https://dominio.com/fontanero/estepona/",
    "canonical": "https://dominio.com/fontanero/estepona/",
    "url_tipo": "service_location"
  },

  "page_version": 1,

  "status": "draft",

  "seo": {
    "title": "",
    "meta_description": "",
    "canonical": "",
    "robots": "index,follow"
  },

  "blocks": [],

  "internal_links": [],

  "images": [],

  "schema": {},

  "control": {
    "schema_version": "4.0",
    "validator_version": "",
    "model_version": "",
    "generated_at": "",
    "validated_at": "",
    "last_updated_at": ""
  }
}

---

26. CREATE

Cuando una página no existe:

page_id inexistente
        ↓
CREATE
        ↓
wordpress_post_id
        ↓
guardar relación

El "page_id" no cambia.

---

27. UPDATE

Cuando ya existe:

page_id existente
        ↓
UPDATE

No se crea una segunda landing.

---

28. ACTUALIZACIÓN PARCIAL

Debe ser posible modificar únicamente:

un bloque

o:

interlinking

o:

SEO

o:

menú

sin reconstruir innecesariamente toda la página.

---

29. IDEMPOTENCIA

Una ejecución repetida con el mismo:

site_id
+
opportunity_id
+
page_id

no debe crear duplicados.

Regla:

NO EXISTE
 ↓
CREATE

EXISTE
 ↓
UPDATE

---

30. VALIDACIÓN

Antes de almacenar:

page_id
identity
url
seo
blocks
block_id
block_instance_id
links
schema
commercial_data

deben haber superado el validador.

WordPress no sustituye al validador de N8N.

---

31. RENDERIZADO

El renderizador utilizará:

page
 ↓
blocks[]
 ↓
block_id
 ↓
resolver plantilla/componente
 ↓
data
 ↓
HTML WordPress

La información de este documento representa datos.

No contiene el diseño visual.

---

32. INDEPENDENCIA DEL TEMA

No se almacenarán referencias obligatorias a:

Kadence
Astra
GeneratePress
Divi
Elementor

El modelo debe funcionar aunque se cambie el tema.

---

33. RELACIÓN CON LAS PLANTILLAS

La relación conceptual es:

block_id
    ↓
renderer
    ↓
template
    ↓
data

Los datos permanecen estables.

La plantilla puede cambiar.

---

34. FONTANERO ESTEpona — FIXTURE

{
  "site_id": "malaga",
  "opportunity_id": "fontanero-estepona",
  "page_id": "FON-EST-HOME",

  "identity": {
    "sector": "servicios",
    "servicio": "fontanero",
    "subservicio": null,
    "pais": "España",
    "comunidad_autonoma": "Andalucía",
    "provincia": "Málaga",
    "municipio": "Estepona",
    "localidad": "Estepona",
    "intencion": "local_service"
  },

  "url": {
    "slug": "fontanero-estepona",
    "url": "/fontanero/estepona/",
    "canonical": "/fontanero/estepona/",
    "url_tipo": "service_location"
  },

  "page_version": 1,
  "status": "draft",

  "seo": {
    "title": "",
    "meta_description": "",
    "canonical": "/fontanero/estepona/",
    "robots": "index,follow"
  },

  "blocks": [],

  "internal_links": [],

  "images": [],

  "schema": {}
}

Los datos comerciales ausentes permanecen vacíos.

---

35. REGLAS DE INTEGRIDAD

Nunca debe existir:

block_instance_id

sin:

page_id

Nunca debe existir:

internal_link

con un destino no validado.

Nunca debe existir:

wordpress_post_id

sin su correspondiente:

page_id

Nunca se debe utilizar un "block_id" que no esté definido en "sistema-bloques.md".

---

36. FUENTES DE VERDAD

modelo-datos.md
→ modelo común

contrato-salida-ia.md
→ contrato de salida

sistema-bloques.md
→ B01–B23

arquitectura-wordpress.md
→ arquitectura técnica

integracion-n8n-wordpress.md
→ integración

modelo-renderizado-wordpress.md
→ renderizado

modelo-datos-wordpress.md
→ datos almacenados/proyectados en WordPress

Cada decisión debe tener un único documento propietario.

---

37. ESTADO

Versión: 2.0
Estado: Preparado para implementación piloto.

Siguiente fase:

VALIDACIÓN DOCUMENTAL
        ↓
PLANTILLAS WORDPRESS
        ↓
API
        ↓
N8N
        ↓
PRIMERA LANDING
        ↓
PRUEBAS DE ACTUALIZACIÓN

FIN
