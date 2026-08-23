ARQUITECTURA WORDPRESS

Versión: 1.0
Estado: Diseño
Proyecto: Plataforma de landings locales automatizadas

---

1. OBJETIVO

WordPress será la capa de presentación y publicación del sistema.

No debe decidir:

- qué bloques utiliza una landing;
- qué contenido genera la IA;
- qué arquitectura SEO corresponde;
- qué enlaces internos deben existir;
- qué estructura debe tener cada localidad.

Esas decisiones pertenecen al motor de arquitectura, al contrato IA y a N8N.

WordPress debe recibir un modelo de landing validado y renderizarlo mediante una plantilla controlada.

---

2. FLUJO GENERAL

DATOS DEL NEGOCIO
        ↓
MOTOR DE ARQUITECTURA
        ↓
SELECCIÓN DE BLOQUES
        ↓
BLOQUES AUTORIZADOS
        ↓
IA
        ↓
CONTENIDO ESTRUCTURADO
        ↓
VALIDADOR
        ↓
N8N
        ↓
MODELO WORDPRESS
        ↓
WORDPRESS
        ↓
PLANTILLA LANDING
        ↓
HTML FINAL

La IA no decide libremente la estructura de la página.

La IA rellena los bloques autorizados por el sistema.

---

3. PRINCIPIO FUNDAMENTAL

Debe existir una separación estricta entre:

Arquitectura

Define:

- qué página se crea;
- slug;
- localidad;
- servicio;
- intención;
- bloques autorizados;
- interlinking;
- estructura SEO.

Contenido

Define:

- títulos;
- textos;
- listas;
- preguntas;
- respuestas;
- CTAs;
- elementos de cada bloque.

Presentación

Define:

- HTML;
- CSS;
- diseño;
- componentes;
- responsive;
- navegación.

WordPress pertenece principalmente a la tercera capa.

---

4. TIPO DE CONTENIDO

La implementación inicial utilizará un tipo de contenido específico para las landings locales.

Nombre conceptual:

Landing

Slug técnico recomendado:

landing

La implementación definitiva del CPT podrá concretarse durante la fase de desarrollo.

La plantilla deberá ser única y reutilizable.

No se creará una plantilla diferente para cada localidad.

---

5. MODELO DE UNA LANDING

Cada landing deberá poder representarse conceptualmente así:

LANDING
│
├── IDENTIDAD
│   ├── servicio
│   ├── localidad
│   ├── provincia
│   └── país
│
├── URL
│   ├── slug
│   └── canonical
│
├── SEO
│   ├── title
│   ├── meta description
│   ├── robots
│   └── schema
│
├── CONTENIDO
│   ├── bloques[]
│   ├── FAQs[]
│   └── CTA
│
├── INTERLINKING
│   ├── enlaces entrantes
│   └── enlaces salientes
│
└── PUBLICACIÓN
    ├── estado
    └── fecha

---

6. BLOQUES

Los bloques B01–B23 son bloques lógicos del sistema.

WordPress no debe interpretar arbitrariamente su significado.

Cada bloque autorizado llegará acompañado de sus datos correspondientes.

Conceptualmente:

bloques[] = [
    {
        id: "B01",
        data: {...}
    },
    {
        id: "B07",
        data: {...}
    }
]

La plantilla será responsable de transformar cada bloque lógico en su componente visual correspondiente.

---

7. SEPARACIÓN BLOQUE / COMPONENTE

Un bloque lógico no tiene por qué equivaler exactamente a un bloque Gutenberg.

Ejemplo:

B01
↓
Componente Hero

Otro bloque puede ser:

B17
↓
Información técnica
↓
No necesariamente componente visual

Por tanto:

BLOQUE LÓGICO
      ↓
REGLA DE RENDERIZADO
      ↓
COMPONENTE WORDPRESS

Esto permite mantener estable la arquitectura aunque posteriormente cambie el diseño visual.

---

8. PLANTILLA ÚNICA

La plantilla de landing será reutilizable.

Conceptualmente:

single-landing.php

o equivalente según la tecnología WordPress finalmente seleccionada.

La plantilla recibirá los datos de la landing y ejecutará el renderizado correspondiente.

Ejemplo:

Landing Fontanero Marbella
Landing Fontanero Estepona
Landing Fontanero Fuengirola
Landing Electricista Marbella

Todas pueden utilizar la misma plantilla.

Lo que cambia es el contenido y la configuración de cada landing.

---

9. DATOS DINÁMICOS

Los datos no deben estar escritos directamente en la plantilla.

La plantilla debe obtenerlos desde el modelo de datos.

Ejemplo:

hero.title
hero.subtitle
hero.cta

services[]
benefits[]
process[]
faq[]

internal_links[]
schema

Esto permite generar miles de páginas sin duplicar plantillas.

---

10. CAMPOS FRENTE A CONTENIDO LIBRE

Se priorizarán datos estructurados frente a grandes bloques de HTML generado por IA.

Preferido:

title
subtitle
items[]
questions[]
answers[]
cta

No preferido:

html_completo_generado_por_ia

La IA no debe controlar directamente el HTML final.

---

11. SEO

WordPress deberá recibir y almacenar los elementos SEO necesarios:

seo.title
seo.meta_description
seo.canonical
seo.robots

El sistema deberá impedir duplicidades accidentales.

El canonical deberá corresponder a la URL definitiva de la landing.

---

12. SCHEMA

El schema será tratado como información estructurada.

No debe depender de texto visible generado manualmente dentro de la página.

Conceptualmente:

schema[]

La implementación final deberá generar JSON-LD válido en el HTML.

WordPress no deberá modificar arbitrariamente el contenido del schema recibido.

---

13. INTERLINKING

Los enlaces internos forman parte de la arquitectura, no de la creatividad de la IA.

N8N podrá enviar:

internal_links[]

Cada enlace deberá contener como mínimo:

url
anchor
target

Ejemplo:

{
  "url": "/fontanero/estepona/",
  "anchor": "Fontanero en Estepona",
  "target": "localidad"
}

La plantilla podrá utilizar estos datos para generar los enlaces correspondientes.

---

14. MENÚS

Los menús deberán tratarse separadamente del contenido de cada landing.

No se debe crear un menú nuevo de WordPress para cada página.

El sistema deberá utilizar una estructura de navegación reutilizable.

Cuando corresponda, N8N podrá indicar los elementos que deben incorporarse a determinadas estructuras de navegación.

---

15. IMÁGENES

Las imágenes deberán tratarse como recursos independientes.

El modelo podrá contener:

images[]

con información como:

url
alt
title
type

La IA podrá proporcionar información descriptiva, pero WordPress/N8N será responsable de gestionar el recurso real.

---

16. ESTADOS DE PUBLICACIÓN

La primera publicación automatizada deberá utilizar:

draft

o equivalente seguro.

Flujo recomendado:

GENERAR
 ↓
VALIDAR
 ↓
CREAR DRAFT
 ↓
REVISAR
 ↓
PUBLICAR

La publicación automática definitiva se habilitará posteriormente cuando el sistema haya superado las pruebas.

---

17. CREACIÓN Y ACTUALIZACIÓN

N8N deberá poder distinguir entre:

CREATE
UPDATE

No se deberán crear duplicados si una landing ya existe.

La identificación deberá basarse en un identificador estable.

Conceptualmente:

landing_id

o equivalente derivado de:

servicio + localidad + variante

---

18. IDEMPOTENCIA

Ejecutar dos veces el mismo proceso no debe generar dos landings.

Ejemplo:

Fontanero + Marbella

debe corresponder siempre a una única entidad.

Si ya existe:

UPDATE

Si no existe:

CREATE

---

19. VALIDACIÓN ANTES DE WORDPRESS

WordPress no será el primer lugar donde se detecten errores.

Antes de enviar los datos:

IA
↓
VALIDADOR
↓
N8N
↓
WORDPRESS

El validador deberá comprobar:

- campos obligatorios;
- tipos;
- bloques autorizados;
- estructura;
- SEO;
- URLs;
- interlinking;
- schema;
- ausencia de campos prohibidos.

---

20. WORDPRESS COMO CAPA DE PRESENTACIÓN

Principio fundamental:

WORDPRESS NO PIENSA
WORDPRESS RENDERIZA

La lógica de negocio permanece fuera de WordPress siempre que sea posible.

Esto permitirá:

- cambiar de plantilla;
- cambiar de tema;
- cambiar componentes;
- modificar CSS;
- cambiar WordPress por otra plataforma en el futuro;

sin tener que reconstruir el motor de generación.

---

21. RESPONSABILIDADES DE N8N

N8N será responsable de:

- recibir el contenido validado;
- transformar el modelo;
- localizar la landing;
- crear o actualizar;
- enviar campos;
- gestionar imágenes;
- gestionar enlaces;
- establecer estado;
- registrar errores;
- devolver resultado.

---

22. RESPONSABILIDADES DE WORDPRESS

WordPress será responsable de:

- almacenar;
- renderizar;
- generar HTML;
- mostrar navegación;
- cargar estilos;
- cargar scripts;
- insertar metadata;
- insertar schema;
- servir la URL pública.

No será responsable de generar contenido mediante IA.

---

23. PRIMERA IMPLEMENTACIÓN

La primera landing de prueba será:

Servicio:
Fontanero

Localidad:
Marbella

Slug:
fontanero-marbella

El objetivo no será generar cientos de páginas.

Primero deberá funcionar correctamente:

1 landing
↓
validación
↓
N8N
↓
WordPress
↓
renderizado
↓
SEO
↓
interlinking
↓
schema
↓
revisión

Solo después se ampliará el sistema.

---

24. ESCALABILIDAD

La arquitectura debe permitir:

1 landing
↓
10 landings
↓
100 landings
↓
1.000 landings
↓
10.000+ landings

sin crear manualmente:

- nuevas plantillas;
- nuevas estructuras;
- nuevos diseños;
- nuevos workflows individuales.

La variación debe estar principalmente en los datos.

---

25. PRINCIPIO DE MANTENIMIENTO

Una modificación del diseño deberá realizarse una sola vez.

Ejemplo:

Cambiar diseño del Hero
↓
modificar componente Hero
↓
todas las landings utilizan el nuevo componente

No:

Modificar 1.000 páginas individualmente

---

26. RELACIÓN CON LOS DOCUMENTOS MAESTROS

Esta arquitectura depende de los siguientes documentos:

arquitectura-landing.md
        ↓
define arquitectura

sistema-bloques.md
        ↓
define B01–B23

contrato-salida-ia.md
        ↓
define salida IA

integracion-n8n-wordpress.md
        ↓
define comunicación

arquitectura-wordpress.md
        ↓
define implementación WordPress

Ninguno de estos documentos debe contradecir a los demás.

---

27. REGLA DE FUENTE DE VERDAD

Cuando exista una contradicción:

1. Se detecta.
2. Se analiza qué documento es el propietario de esa decisión.
3. Se modifica el documento correcto.
4. Se actualizan las referencias necesarias.
5. No se resuelve mediante memoria informal.

El repositorio debe actuar como fuente de verdad del proyecto.

---

28. ESTADO ACTUAL

Diseño

- Arquitectura general: definida.
- Sistema de bloques: definido.
- Contrato IA: definido.
- Integración N8N → WordPress: definida conceptualmente.
- Arquitectura WordPress: definida en este documento.
- Implementación WordPress: pendiente.
- Implementación N8N: pendiente.
- Validador: pendiente.
- Primera landing real: pendiente.

Próximo paso

El siguiente trabajo será diseñar el modelo exacto de datos WordPress:

campo
→ tipo
→ origen
→ almacenamiento
→ renderizado

y posteriormente utilizar "Fontanero Marbella" como fixture de prueba.

---

29. REGLA DE NO SOBREINGENIERÍA

No se implementará una arquitectura más compleja de la necesaria.

Se priorizará:

simple
→ estable
→ automatizable
→ mantenible
→ escalable

sobre:

complejo
→ sofisticado
→ difícil de mantener

La implementación concreta de CPT, campos, API, plugins y código se decidirá en la fase técnica, después de validar este modelo.
