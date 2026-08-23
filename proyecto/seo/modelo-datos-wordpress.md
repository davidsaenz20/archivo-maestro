MODELO DE DATOS WORDPRESS

Versión: 1.0
Estado: Diseño
Proyecto: Plataforma de landings locales automatizadas

---

1. FUNCIÓN

Este documento define la proyección del modelo de datos común hacia WordPress.

No sustituye a:

- "proyecto/seo/modelo-datos.md"
- "proyecto/seo/sistema-bloques.md"
- "proyecto/seo/contrato-salida-ia.md"
- "proyecto/seo/arquitectura-wordpress.md"

WordPress almacena y renderiza una landing ya decidida y validada.

No decide la estrategia SEO ni genera contenido.

Flujo

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
PLANTILLA

---

2. PRINCIPIO DE PROYECCIÓN

No todo el modelo común debe almacenarse como campo público de WordPress.

Se separan tres grupos:

1. Datos necesarios para renderizar.
2. Datos necesarios para SEO/publicación.
3. Datos de trazabilidad o control interno.

Los datos de investigación, evidencias y razonamiento del motor no deben exponerse innecesariamente en la página pública.

---

3. ENTIDAD PRINCIPAL

Tipo conceptual:

Landing

Implementación prevista:

Custom Post Type: landing

La decisión definitiva del CPT y del sistema de campos se realizará durante la implementación técnica.

Cada registro representa una única landing.

---

4. IDENTIFICACIÓN

Campo| Tipo| Origen| Almacenamiento| Renderizado
"landing_id"| string| motor/N8N| meta| no
"opportunity_id"| string| investigación/motor| meta| no
"version"| string| sistema| meta| no
"estado_landing"| enum| workflow| meta| no

"landing_id" debe ser estable e idempotente.

---

5. IDENTIDAD

Campo| Tipo| Origen| Almacenamiento| Renderizado
"sector"| string| modelo común| campo estructurado| indirecto
"servicio"| string| motor| campo estructurado| sí
"subservicio"| string/null| motor| campo estructurado| condicional
"pais"| string| modelo común| campo estructurado| no necesariamente
"comunidad_autonoma"| string| modelo común| campo estructurado| condicional
"provincia"| string| modelo común| campo estructurado| condicional
"municipio"| string| motor| campo estructurado| sí
"localidad"| string| motor| campo estructurado| sí
"intencion"| enum| motor| meta/control| indirecto

La identidad no puede ser modificada por la IA.

---

6. URL

Campo| Tipo| Origen| Almacenamiento| Renderizado
"slug"| string| arquitectura URL| post slug| URL
"url"| string| arquitectura URL| derivada/validada| URL
"canonical"| URL| arquitectura SEO| meta/SEO| head
"url_tipo"| enum| arquitectura URL| meta| no

WordPress no debe recalcular una URL estratégica de forma autónoma.

---

7. SEO

Campo| Tipo| Origen| Almacenamiento| Renderizado
"seo_title"| string| IA dentro de reglas| meta SEO| "<title>"
"meta_description"| string| IA dentro de reglas| meta SEO| "<meta>"
"robots"| enum/string| sistema| meta SEO| head
"canonical"| URL| arquitectura| meta SEO| head

El mecanismo concreto de almacenamiento SEO dependerá de la solución WordPress elegida.

---

8. BLOQUES

Campo principal:

bloques[]

Cada elemento debe conservar como mínimo:

id
position
data

Ejemplo:

{
  "id": "B03",
  "position": 3,
  "data": {
    "h1": "Fontanero en Marbella",
    "subtitulo": "...",
    "cta": {}
  }
}

Los identificadores B01–B23 son los definidos por "sistema-bloques.md".

La IA no puede introducir identificadores no autorizados.

---

9. MAPA B01–B23 → DATOS

Bloque| Datos principales
B01 Header| marca, logo, navegación, CTA global
B02 Navegación| URLs globales y estratégicas validadas
B03 Hero| h1, subtítulo, CTA, confianza disponible
B04 Contenido principal| títulos, textos, problemas, alcance
B05 CTA principal| tipo, texto, canal/destino validado
B06 Footer| navegación, contacto, legal, enlaces globales
B07 Subservicio| servicio, subservicio, contenido específico
B08 Problemas/necesidades| elementos respaldados
B09 Información local| datos locales verificados
B10 Zonas/cobertura| zonas y cobertura confirmada
B11 Proceso| pasos reales del servicio
B12 Confianza| experiencia, certificaciones, garantías, reseñas válidas
B13 Diferenciación| información específica y verificable
B14 FAQ| preguntas y respuestas
B15 Servicios relacionados| URL, anchor, relación
B16 Localidades relacionadas| localidad, URL, relación
B17 Datos estructurados| schema válido
B18 Testimonios| testimonios reales/autorizados
B19 Casos/ejemplos| casos reales/documentados
B20 Galería| recursos de imagen reales
B21 Precio/tarifas| precio autorizado
B22 Horarios| horarios reales
B23 Mapa/ubicación| ubicación válida

---

10. FAQ

Campo:

faq[]

Estructura:

question
answer

Las FAQ deben proceder del contenido validado y no pueden inventar datos comerciales.

---

11. CTA

Estructura conceptual:

cta:
  type
  text
  destination

El destino debe ser real y previamente validado.

Ejemplos de "type":

whatsapp
phone
contact
quote
appointment

No se almacenará un teléfono o WhatsApp inventado.

---

12. INTERLINKING

Campo:

internal_links[]

Cada enlace:

url
anchor
target
reason

Ejemplo:

{
  "url": "/fontanero/estepona/",
  "anchor": "Fontanero en Estepona",
  "target": "localidad",
  "reason": "localidad relacionada"
}

Solo se almacenarán URLs existentes o validadas.

La plantilla utilizará estos datos para renderizar los enlaces donde corresponda.

---

13. IMÁGENES

Campo:

images[]

Estructura conceptual:

id
url
alt
title
type
source
license

WordPress podrá convertir los recursos válidos en IDs de Media Library durante la implementación.

La URL no debe ser inventada.

---

14. SCHEMA

Campo:

schema

Debe contener únicamente datos estructurados válidos y derivados de información autorizada.

La salida final será JSON-LD en el HTML.

No se permitirá que un editor o proceso posterior introduzca datos ficticios para completar el schema.

---

15. DATOS COMERCIALES

Los datos comerciales que puedan aparecer públicamente deberán estar separados y validados:

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

ausencia de dato
        ↓
null / omitido

Nunca se debe inferir o inventar un dato comercial.

---

16. DATOS INTERNOS

No deben formar parte del contenido público salvo que una regla lo determine expresamente:

fuentes
evidencias
confianza
decision
restricciones
errores internos
logs
fecha_generacion
fecha_validacion

Pueden almacenarse para trazabilidad si resulta útil para administración, auditoría o automatización.

---

17. VALIDACIÓN

Antes de crear o actualizar una landing, N8N debe comprobar al menos:

- "landing_id" válido;
- identidad coherente;
- URL y slug válidos;
- bloques autorizados;
- datos obligatorios presentes;
- ausencia de datos prohibidos;
- URLs internas válidas;
- schema válido;
- CTA y datos comerciales autorizados;
- idempotencia.

WordPress no sustituye al validador previo.

---

18. RENDERIZADO

La plantilla seguirá esta lógica conceptual:

Landing
   ↓
leer identidad / SEO
   ↓
recorrer bloques[]
   ↓
resolver componente por ID
   ↓
pasar data del bloque
   ↓
renderizar HTML
   ↓
insertar interlinking
   ↓
insertar schema

No se debe generar HTML directamente desde el contenido de la IA sin pasar por el componente correspondiente.

---

19. REGLA DE COMPONENTES

Existirá un registro interno de correspondencia:

B01 → Header
B02 → Navigation
B03 → Hero
...
B23 → Map

La implementación podrá utilizar PHP, bloques dinámicos, componentes o una combinación, pero la interfaz lógica será el ID del bloque.

---

20. CREAR / ACTUALIZAR

N8N utilizará "landing_id" para determinar la operación.

no existe landing_id
        ↓
CREATE

existe landing_id
        ↓
UPDATE

La operación debe ser idempotente.

La primera publicación automática se mantendrá en "draft" hasta completar las pruebas.

---

21. FONTANERO MARBELLA — FIXTURE

Identidad mínima de prueba:

landing_id: LANDING-fontanero-marbella
servicio: fontanero
subservicio: null
pais: España
comunidad_autonoma: Andalucía
provincia: Málaga
municipio: Marbella
localidad: Marbella
slug: fontanero-marbella

Los campos comerciales no incluidos deberán permanecer vacíos/null.

No se deben inventar:

- teléfono;
- WhatsApp;
- dirección;
- precio;
- horarios;
- certificaciones;
- experiencia;
- reseñas.

El fixture servirá para probar:

modelo
   ↓
validación
   ↓
transformación N8N
   ↓
creación WordPress
   ↓
renderizado

---

22. DECISIONES PENDIENTES DE IMPLEMENTACIÓN

Todavía NO se fija:

- plugin de campos;
- ACF u otra solución;
- estructura exacta de tablas/meta;
- implementación definitiva del CPT;
- endpoints REST definitivos;
- autenticación;
- tema;
- constructor visual;
- implementación concreta de componentes.

Estas decisiones se tomarán después de validar el modelo.

---

23. FUENTES DE VERDAD

"modelo-datos.md" → modelo común.

"sistema-bloques.md" → definición B01–B23.

"contrato-salida-ia.md" → salida IA.

"arquitectura-wordpress.md" → arquitectura WordPress.

"integracion-n8n-wordpress.md" → comunicación N8N/WordPress.

Este documento → proyección del modelo común dentro de WordPress.

Si aparece una contradicción:

1. Se identifica el documento propietario de la decisión.
2. Se corrige ese documento.
3. Se actualizan las dependencias necesarias.
4. Se evita resolver la contradicción mediante memoria informal.

El repositorio debe actuar como fuente de verdad del proyecto.
