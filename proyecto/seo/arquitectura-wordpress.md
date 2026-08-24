ARQUITECTURA WORDPRESS

Versión: 2.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
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

Esas decisiones pertenecen al motor de arquitectura, al contrato de salida de IA y a N8N.

WordPress debe recibir un modelo de landing previamente validado y renderizarlo mediante una plantilla controlada y reutilizable.

---

2. FLUJO GENERAL

DATOS DEL NEGOCIO
        ↓
INVESTIGACIÓN
        ↓
MOTOR DE DECISIÓN
        ↓
DECISIÓN = CREAR
        ↓
ARQUITECTURA
        ↓
SELECCIÓN DE BLOQUES
        ↓
DATOS
        ↓
IA
        ↓
CONTENIDO ESTRUCTURADO
        ↓
VALIDACIÓN
        ↓
N8N
        ↓
WORDPRESS
        ↓
PLANTILLA LANDING
        ↓
HTML FINAL

La IA no decide libremente la estructura de la página.

La IA rellena únicamente los bloques y campos autorizados.

---

3. PRINCIPIO FUNDAMENTAL

Debe existir una separación estricta entre:

Arquitectura

Define:

- qué página se crea;
- servicio;
- subservicio;
- localidad;
- intención;
- URL;
- canonical;
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

La lógica de decisión y generación debe permanecer fuera de WordPress siempre que sea posible.

---

4. TIPO DE CONTENIDO

La implementación inicial utilizará un tipo de contenido específico para las landings locales.

Nombre conceptual:

"Landing"

Slug técnico recomendado:

"landing"

La implementación definitiva del CPT podrá concretarse durante la fase de desarrollo.

La plantilla será única y reutilizable.

No se creará una plantilla diferente para cada localidad.

Ejemplos:

- Fontanero Marbella.
- Fontanero Estepona.
- Fontanero Fuengirola.
- Electricista Marbella.

Todas podrán utilizar la misma plantilla.

---

5. MODELO DE UNA LANDING

Cada landing deberá poder representarse conceptualmente así:

LANDING
│
├── IDENTIDAD
│   ├── servicio
│   ├── subservicio
│   ├── localidad
│   ├── provincia
│   └── país
│
├── ARQUITECTURA
│   ├── page_type
│   ├── url
│   ├── canonical
│   ├── parent_url
│   └── depth
│
├── SEO
│   ├── title
│   ├── meta_description
│   ├── h1
│   ├── robots
│   └── schema
│
├── CONTENIDO
│   ├── bloques[]
│   ├── FAQ[]
│   └── CTA
│
├── INTERLINKING
│   ├── enlaces entrantes
│   └── enlaces salientes
│
├── IMÁGENES
│   └── images[]
│
└── PUBLICACIÓN
    ├── estado
    └── fecha

---

6. BLOQUES

Los bloques B01–B23 son bloques lógicos oficiales del sistema.

WordPress no debe interpretar arbitrariamente su significado.

Cada bloque autorizado llegará acompañado de sus datos correspondientes.

Conceptualmente:

{
  "blocks": [
    {
      "id": "B01",
      "data": {}
    },
    {
      "id": "B07",
      "data": {}
    }
  ]
}

La plantilla será responsable de transformar cada bloque lógico en su componente visual correspondiente.

La definición funcional de los bloques se encuentra en:

"proyecto/seo/sistema-bloques.md"

No se deben crear identificadores paralelos.

---

7. SEPARACIÓN BLOQUE / COMPONENTE

Un bloque lógico no tiene por qué equivaler exactamente a un bloque Gutenberg.

Ejemplo:

B03
↓
Componente Hero

Otro bloque puede ser:

B17
↓
Información estructurada
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

"single-landing.php"

o equivalente según la tecnología WordPress finalmente seleccionada.

La plantilla recibirá los datos de la landing y ejecutará el renderizado correspondiente.

No se debe crear código específico para cada localidad.

---

9. DATOS DINÁMICOS

Los datos no deben estar escritos directamente en la plantilla.

La plantilla debe obtenerlos desde el modelo de datos.

Ejemplos:

hero.title
hero.subtitle
hero.cta

services[]
benefits[]
problems[]
process[]
faq[]

internal_links[]
images[]
schema

Esto permite generar muchas páginas sin duplicar plantillas.

---

10. CAMPOS FRENTE A HTML LIBRE

Se priorizarán datos estructurados frente a grandes bloques de HTML generado por IA.

Preferido

title
subtitle
items[]
questions[]
answers[]
cta

No preferido

html_completo_generado_por_ia

La IA no debe controlar directamente el HTML final.

La presentación debe estar controlada por WordPress.

---

11. SEO

WordPress deberá recibir y almacenar los elementos SEO necesarios:

seo.title
seo.meta_description
seo.h1
seo.canonical
seo.robots

El sistema deberá impedir duplicidades accidentales.

El canonical deberá corresponder exactamente a la URL definitiva de la landing.

La URL no debe ser generada libremente por WordPress ni por la IA.

---

12. SCHEMA

El schema será tratado como información estructurada.

Conceptualmente:

schema[]

La implementación final deberá generar JSON-LD válido en el HTML.

WordPress no deberá modificar arbitrariamente el contenido estructurado recibido.

El tipo de schema deberá corresponder con la información realmente disponible y validada.

No se deben generar datos estructurados con información inventada.

---

13. INTERLINKING

Los enlaces internos forman parte de la arquitectura.

No deben depender de la creatividad de la IA.

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

No se crearán enlaces hacia páginas que no existan o no estén autorizadas.

---

14. MENÚS

Los menús deberán tratarse separadamente del contenido de cada landing.

No se debe crear un menú nuevo de WordPress para cada página.

El sistema utilizará una estructura de navegación reutilizable.

Cuando corresponda, N8N podrá indicar qué elementos deben incorporarse a determinadas estructuras de navegación.

La IA no podrá crear arbitrariamente URLs de navegación.

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

La IA podrá proporcionar información descriptiva.

N8N y WordPress serán responsables de gestionar el recurso real.

No se deben publicar imágenes inexistentes ni inventar atributos que no correspondan al recurso.

---

16. ESTADOS DE PUBLICACIÓN

La primera publicación automatizada deberá utilizar:

"draft"

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

La publicación automática definitiva se habilitará únicamente después de superar las pruebas del sistema.

---

17. CREACIÓN Y ACTUALIZACIÓN

N8N deberá poder distinguir entre:

CREATE
UPDATE

No se deberán crear duplicados si una landing ya existe.

La identificación deberá basarse en un identificador estable.

Conceptualmente:

landing_id

o equivalente derivado de la identidad estable de la oportunidad.

Por ejemplo:

servicio + subservicio + localidad + variante

La identidad exacta deberá quedar determinada por el modelo de datos definitivo.

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

Esta regla es obligatoria para permitir automatizaciones seguras.

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

El validador deberá comprobar como mínimo:

- campos obligatorios;
- tipos de datos;
- bloques autorizados;
- estructura;
- SEO;
- URLs;
- canonical;
- interlinking;
- schema;
- imágenes;
- ausencia de campos prohibidos;
- coherencia con la arquitectura.

Si la validación falla, WordPress no debe recibir la publicación como válida.

---

20. WORDPRESS COMO CAPA DE PRESENTACIÓN

Principio fundamental:

WORDPRESS NO PIENSA.
WORDPRESS RENDERIZA.

La lógica de negocio permanece fuera de WordPress siempre que sea posible.

Esto permitirá:

- cambiar de plantilla;
- cambiar de tema;
- cambiar componentes;
- modificar CSS;
- modificar el diseño;
- evolucionar la presentación;

sin tener que reconstruir el motor de generación.

---

21. RESPONSABILIDADES DE N8N

N8N será responsable de:

- recibir el contenido validado;
- transformar el modelo cuando sea necesario;
- localizar la landing correspondiente;
- determinar si debe crear o actualizar;
- enviar los campos;
- gestionar imágenes;
- gestionar enlaces;
- establecer el estado de publicación;
- registrar errores;
- devolver el resultado del proceso.

N8N no debe modificar arbitrariamente decisiones SEO protegidas.

---

22. RESPONSABILIDADES DE WORDPRESS

WordPress será responsable principalmente de:

- almacenar la landing;
- almacenar los datos recibidos;
- aplicar la plantilla;
- renderizar los bloques;
- generar el HTML final;
- aplicar CSS y diseño responsive;
- mostrar navegación;
- mostrar contenido;
- servir la página al usuario.

WordPress no será responsable de decidir si una oportunidad SEO debe existir.

---

23. RESPONSABILIDADES DE LA IA

La IA será responsable de generar contenido dentro de los límites definidos por:

- arquitectura;
- modelo de datos;
- bloques autorizados;
- restricciones;
- contrato de salida.

La IA no podrá:

- inventar URLs;
- inventar bloques;
- modificar la arquitectura;
- convertir hipótesis en hechos;
- inventar datos comerciales;
- crear información local no respaldada;
- modificar identificadores protegidos.

---

24. MODELO DE AUTORIDAD

Cuando existan contradicciones, se aplicará el siguiente orden:

REGLAS DEL PROYECTO
        ↓
DECISIÓN SEO
        ↓
ARQUITECTURA
        ↓
DATOS VALIDADOS
        ↓
CONTRATO IA
        ↓
IA
        ↓
N8N
        ↓
WORDPRESS

Las capas inferiores no pueden modificar unilateralmente las decisiones de las capas superiores.

---

25. PILOTO

Antes de construir el sistema completo se realizará una primera landing piloto.

Ejemplo:

Fontanero + Hispan

La landing piloto servirá para comprobar:

- creación del contenido;
- selección de bloques;
- funcionamiento de la plantilla;
- renderizado;
- SEO;
- enlaces;
- schema;
- imágenes;
- comunicación N8N → WordPress;
- creación y actualización;
- validación;
- experiencia visual.

No se debe escalar el sistema hasta comprobar que el piloto funciona correctamente.

---

26. ESCALABILIDAD

La arquitectura deberá permitir que una misma plantilla pueda utilizarse para múltiples combinaciones.

Ejemplos:

Fontanero Marbella
Fontanero Estepona
Fontanero Fuengirola
Electricista Marbella
Abogado Marbella

La plantilla no cambia.

Cambian:

- identidad;
- arquitectura;
- datos;
- bloques autorizados;
- contenido;
- enlaces;
- recursos.

---

27. MANTENIMIENTO Y ACTUALIZACIÓN

El sistema deberá permitir actualizar una landing existente sin crear otra.

Flujo:

NUEVA INFORMACIÓN
 ↓
INVESTIGACIÓN / DETECCIÓN
 ↓
IA
 ↓
VALIDACIÓN
 ↓
N8N
 ↓
UPDATE WORDPRESS

Las actualizaciones deberán conservar la identidad estable de la landing.

No se debe generar una nueva página cuando corresponda actualizar una existente.

---

28. SEGURIDAD DE PUBLICACIÓN

Durante la fase inicial:

IA
 ↓
VALIDADOR
 ↓
N8N
 ↓
WORDPRESS DRAFT
 ↓
REVISIÓN HUMANA
 ↓
PUBLICACIÓN

La publicación completamente automática será una fase posterior.

Solo podrá habilitarse cuando:

- el contrato esté validado;
- el validador sea fiable;
- la plantilla esté probada;
- la idempotencia funcione;
- los errores estén controlados;
- las pruebas reales sean satisfactorias.

---

29. RELACIÓN CON LA DOCUMENTACIÓN SEO

WordPress no sustituye los documentos de arquitectura.

Debe utilizar como referencia:

- "motor-decision.md"
- "arquitectura-seo.md"
- "arquitectura-urls.md"
- "arquitectura-landing.md"
- "sistema-bloques.md"
- "esquema-datos.md"
- "contrato-salida-ia.md"

Cada documento tiene una función diferente.

WordPress implementa la capa de presentación definida por esos documentos.

---

30. ESTADO ACTUAL

Versión: v2.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

La arquitectura conceptual de WordPress queda definida.

La implementación técnica concreta de:

- CPT;
- campos;
- plantilla;
- componentes;
- CSS;
- endpoints;
- autenticación;
- integración N8N;

se realizará durante la fase de construcción y podrá ajustarse tras las pruebas del piloto.

---

31. SIGUIENTE PASO

El siguiente paso es:

CONSTRUIR LA PRIMERA LANDING PILOTO EN WORDPRESS

Antes de automatizar múltiples páginas se deberá:

1. Crear la estructura WordPress.
2. Crear la plantilla.
3. Crear los componentes necesarios.
4. Conectar el modelo de datos.
5. Preparar una primera landing.
6. Validar el resultado visual y funcional.
7. Conectar posteriormente N8N.
8. Probar CREATE.
9. Probar UPDATE.
10. Corregir cualquier problema detectado.
11. Documentar las modificaciones.
12. Escalar.

La construcción definitiva no debe comenzar sobre cientos de páginas.

Primero debe funcionar correctamente una.

---

32. REGISTRO DE ACTUALIZACIÓN

2026-08-24

Se actualiza "arquitectura-wordpress.md" de la versión v1.0 — Diseño a v2.0 — Preparado para implementación piloto.

Se consolida la separación entre:

- arquitectura;
- contenido;
- presentación.

Se establece WordPress como capa de presentación y publicación.

Se refuerza que:

- WordPress no decide la arquitectura SEO;
- WordPress no decide los bloques;
- WordPress no genera la lógica de negocio;
- la IA no controla directamente el HTML;
- N8N gestiona la automatización;
- el validador precede a WordPress;
- las operaciones deben ser idempotentes;
- CREATE y UPDATE deben diferenciarse;
- la publicación inicial debe realizarse mediante DRAFT;
- la primera implementación debe validarse mediante un piloto.

La arquitectura queda preparada para comenzar la fase de construcción.
