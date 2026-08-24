ARQUITECTURA WORDPRESS

Versión: 2.0
Estado: Preparado para implementación piloto
Proyecto: Plataforma de landings locales automatizadas

---

1. FUNCIÓN

Este documento define la arquitectura técnica de WordPress dentro del sistema.

No define:

- la estrategia SEO;
- el modelo de datos común;
- los bloques;
- el contrato de salida de IA;
- la lógica de N8N;
- el diseño visual concreto del tema.

Su función es definir cómo se organizará WordPress para recibir, almacenar, renderizar, actualizar y publicar las landings.

---

2. PAPEL DE WORDPRESS

WordPress será la capa de:

ALMACENAMIENTO
+
RENDERIZADO
+
PUBLICACIÓN

No será responsable de decidir:

qué páginas crear
qué localidades utilizar
qué contenidos generar
qué estrategia SEO seguir

Esas decisiones pertenecen a las capas superiores.

---

3. ARQUITECTURA GENERAL

USUARIO / LISTA DE OPORTUNIDADES
            ↓
       ARQUITECTURA SEO
            ↓
             IA
            ↓
        VALIDACIÓN
            ↓
            N8N
            ↓
       WORDPRESS API
            ↓
     MODELO WORDPRESS
            ↓
      RENDERIZADOR
            ↓
        PLANTILLAS
            ↓
       TEMA VISUAL
            ↓
       PÁGINA PUBLICADA

---

4. SEPARACIÓN DE CAPAS

Capa 1 — Datos

Contiene la información de la página.

Capa 2 — Bloques

Define qué componentes lógicos existen.

Capa 3 — Renderizador

Decide cómo convertir cada bloque en una representación WordPress.

Capa 4 — Plantillas

Define la estructura visual reutilizable.

Capa 5 — Tema

Aporta estilos, responsive y presentación.

---

5. INDEPENDENCIA DEL TEMA

La arquitectura no dependerá de un tema concreto.

Durante el piloto podrá utilizarse:

Kadence

pero Kadence no será parte del contrato lógico.

La arquitectura debe permitir:

Kadence
↓
otro tema
↓
otro sistema visual

sin modificar:

- "page_id";
- "block_id";
- "block_instance_id";
- estructura SEO;
- interlinking;
- modelo de datos.

---

6. ESTRUCTURA PRINCIPAL

WordPress deberá poder representar:

SITE
 └── PAGES
      └── PAGE
           ├── SEO
           ├── BLOCKS
           ├── LINKS
           ├── MENU
           ├── IMAGES
           └── SCHEMA

---

7. IDENTIDAD DE LA PÁGINA

Cada landing tendrá una identidad lógica estable:

site_id
opportunity_id
page_id

Ejemplo:

site_id: malaga
opportunity_id: fontanero-estepona
page_id: FON-EST-HOME

El ID interno de WordPress será secundario.

---

8. CUSTOM POST TYPE

La implementación podrá utilizar un Custom Post Type específico:

landing

La decisión definitiva sobre el CPT y su implementación técnica se realizará durante el piloto.

El CPT no debe convertirse en una dependencia del modelo lógico.

---

9. API DE WORDPRESS

N8N se comunicará con WordPress mediante una interfaz API.

La interfaz deberá permitir como mínimo:

CREATE PAGE
UPDATE PAGE
GET PAGE
CREATE/UPDATE BLOCK
UPDATE LINKS
UPDATE MENU
PUBLISH
UNPUBLISH

La implementación concreta podrá utilizar:

- REST API;
- endpoints personalizados;
- combinación de REST API y funciones internas.

---

10. PRINCIPIO API

N8N no debería manipular directamente la base de datos de WordPress.

Flujo recomendado:

N8N
 ↓
API
 ↓
WordPress
 ↓
validación interna
 ↓
almacenamiento

Esto reduce dependencias y facilita mantenimiento.

---

11. AUTENTICACIÓN

La conexión N8N → WordPress deberá utilizar credenciales seguras.

No se almacenarán:

- contraseñas;
- tokens;
- claves;
- credenciales

dentro de los documentos del proyecto ni dentro del contenido generado por IA.

---

12. RENDERIZADOR

El renderizador será responsable de convertir:

BLOCK_ID + DATA

en:

COMPONENTE WORDPRESS

Ejemplo:

B03
↓
Renderer Hero
↓
Plantilla Hero
↓
datos del Hero

---

13. REGISTRO DE COMPONENTES

Debe existir una correspondencia lógica:

B01 → Header
B02 → Navigation
B03 → Hero
B04 → Main Content
B05 → CTA
B06 → Footer
B07 → Subservice
B08 → Problems
B09 → Local Context
B10 → Coverage
B11 → Process
B12 → Trust
B13 → Differentiation
B14 → FAQ
B15 → Related Services
B16 → Related Locations
B17 → Structured Data
B18 → Testimonials
B19 → Cases
B20 → Gallery
B21 → Pricing
B22 → Opening Hours
B23 → Map

La implementación visual puede variar.

Los identificadores lógicos no.

---

14. PLANTILLAS

Las plantillas serán componentes reutilizables.

Una plantilla podrá utilizarse en cientos o miles de páginas.

Ejemplo:

PLANTILLA HERO
       ↓
Fontanero Estepona
Fontanero Manilva
Fontanero Ronda
Fontanero Cártama
Fontanero Marbella

Solo cambian los datos.

---

15. PLANTILLAS Y TEMA

La plantilla define:

- estructura;
- posiciones;
- componentes;
- jerarquía visual.

El tema proporciona:

- CSS;
- responsive;
- tipografías;
- estilos globales;
- elementos visuales.

La IA no debe controlar directamente estos elementos.

---

16. BLOQUES REUTILIZABLES

Los bloques deberán construirse inicialmente en WordPress como componentes o plantillas reutilizables.

No se debe diseñar manualmente cada landing.

La construcción inicial será:

B03 Hero
↓
crear plantilla

B04 Main Content
↓
crear plantilla

B14 FAQ
↓
crear plantilla

...

No necesariamente habrá una plantilla visual independiente para cada B01–B23.

---

17. MULTIPLICIDAD

Una página puede utilizar varias veces el mismo bloque.

Ejemplo:

B07-01
B07-02
B07-03

Por ello cada instancia deberá disponer de:

block_instance_id

---

18. IDENTIFICACIÓN DE INSTANCIAS

La combinación lógica será:

page_id
+
block_instance_id

Ejemplo:

FON-EST-HOME
+
FON-EST-HOME-B14-01

Esto permite actualizar una instancia concreta.

---

19. ACTUALIZACIÓN PARCIAL

WordPress debe permitir actualizar:

un bloque

sin reconstruir necesariamente:

toda la página

Ejemplo:

UPDATE_BLOCK
page_id = FON-EST-HOME
block_instance_id = FON-EST-HOME-B14-01

---

20. ACTUALIZACIÓN DE ENLACES

El interlinking será independiente del contenido principal.

WordPress debe poder recibir:

UPDATE_LINKS

y modificar únicamente los enlaces correspondientes.

---

21. MENÚ

La arquitectura debe permitir que N8N actualice menús sin regenerar las páginas.

El menú será una estructura independiente.

Ejemplo:

Servicios
 ├── Fontaneros
 ├── Electricistas
 ├── Pintores
 └── Carpinteros

---

22. MEDIA

Las imágenes se gestionarán mediante WordPress Media Library cuando corresponda.

El sistema deberá poder asociar:

imagen
alt
title
tipo

a la instancia correspondiente.

No se deberán inventar recursos.

---

23. SEO

WordPress recibirá los datos SEO validados.

La arquitectura no obliga a utilizar un plugin SEO concreto.

Podrá utilizarse el sistema SEO elegido durante la implementación.

Debe soportar como mínimo:

title
meta description
canonical
robots

---

24. DATOS ESTRUCTURADOS

WordPress deberá poder renderizar el schema validado.

El sistema no debe permitir que se introduzcan automáticamente datos estructurados ficticios.

---

25. DRAFT COMO ESTADO INICIAL

Durante el piloto:

CREATE
 ↓
DRAFT
 ↓
VERIFICACIÓN
 ↓
PUBLICACIÓN

La publicación automática solo se habilitará después de superar las pruebas.

---

26. PUBLICACIÓN

Una publicación deberá producir:

URL válida
+
HTML correcto
+
SEO correcto
+
interlinking correcto
+
schema correcto

---

27. VERIFICACIÓN POST-ESCRITURA

Después de cada creación o actualización:

N8N
 ↓
WordPress
 ↓
GET
 ↓
comprobar resultado

Debe verificarse que los datos realmente han sido almacenados.

---

28. VERSIONADO

WordPress deberá poder conservar la versión lógica de la página y de los bloques.

Ejemplo:

page_version = 4

y:

block_version = 2

No depende del sistema de revisiones visuales de WordPress.

Es un control lógico del sistema.

---

29. IDEMPOTENCIA

La arquitectura debe permitir que una misma operación no produzca duplicados.

Regla:

page_id inexistente
↓
CREATE

page_id existente
↓
UPDATE

Nunca:

CREATE
CREATE
CREATE

para la misma identidad.

---

30. ERRORES

WordPress deberá devolver errores identificables para que N8N pueda actuar.

Ejemplos:

PAGE_NOT_FOUND
BLOCK_NOT_FOUND
BLOCK_INSTANCE_NOT_FOUND
TEMPLATE_NOT_FOUND
INVALID_DATA
INVALID_URL
WORDPRESS_ERROR
AUTHENTICATION_ERROR

---

31. COMPATIBILIDAD

El sistema deberá ser compatible con:

N8N
IA
REST API
WordPress
plantillas
tema visual

sin acoplar innecesariamente una capa a otra.

---

32. ESCALABILIDAD

La arquitectura debe soportar progresivamente:

1 página
↓
3 páginas
↓
10 páginas
↓
50 páginas
↓
100 páginas
↓
1.000+

La escalabilidad dependerá también de:

- servidor;
- API;
- IA;
- límites de WordPress;
- concurrencia de N8N.

---

33. CAMBIO DE TEMA

Si se cambia el tema:

DATOS
+
BLOCK_ID
+
BLOCK_INSTANCE_ID

deben permanecer intactos.

Solo se sustituyen las plantillas/renderizadores visuales.

---

34. CAMBIO DE DISEÑO GLOBAL

Una modificación de una plantilla deberá poder afectar a todas las páginas que la utilizan.

Conceptualmente:

PLANTILLA B03
       ↓
páginas que utilizan B03
       ↓
nuevo diseño

Sin regenerar el contenido semántico.

---

35. SEGURIDAD DE DATOS

No deben almacenarse como contenido público:

- fuentes internas;
- razonamientos;
- logs;
- credenciales;
- información privada;
- datos de auditoría innecesarios.

La información pública debe limitarse a los datos autorizados.

---

36. RESPONSABILIDAD DE WORDPRESS

WordPress:

RECIBE
ALMACENA
RENDERIZA
PUBLICA

No:

INVESTIGA
DECIDE LA ESTRATEGIA
INVENTA CONTENIDO
INVENTA DATOS

---

37. RESPONSABILIDAD DE N8N

N8N:

ORQUESTA
TRANSFORMA
SINCRONIZA
ACTUALIZA
VERIFICA
REGISTRA

No debe convertirse en el propietario del diseño visual.

---

38. RESPONSABILIDAD DE LA IA

La IA:

GENERA CONTENIDO
GENERA DATOS ESTRUCTURADOS
PROPONE BLOQUES AUTORIZADOS
PROPONE RELACIONES AUTORIZADAS

No controla directamente:

HTML
CSS
TEMA
PLANTILLAS

---

39. RESPONSABILIDAD DE LAS PLANTILLAS

Las plantillas controlan:

estructura visual
diseño
espaciado
jerarquía
componentes
responsive

Los datos proceden del modelo validado.

---

40. RESPONSABILIDAD DEL TEMA

El tema proporciona la capa visual general.

El sistema debe poder sustituirlo sin alterar la arquitectura lógica.

---

41. PILOTO

La implementación inicial se realizará con:

WordPress
+
tema elegido
+
primer conjunto de plantillas
+
API
+
N8N

Primero se probará una landing.

Después:

1
→ 3
→ 10

Antes de escalar.

---

42. PRIMERA LANDING DE PRUEBA

Se utilizará una landing real de prueba, por ejemplo:

Fontanero Estepona

El objetivo será comprobar:

IA
↓
SITE_PACKAGE
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
PLANTILLAS
↓
PÁGINA

---

43. PRUEBAS OBLIGATORIAS

Antes de generación masiva:

Prueba 1

Crear landing.

Prueba 2

Actualizar landing completa.

Prueba 3

Actualizar un único bloque.

Prueba 4

Añadir un bloque.

Prueba 5

Desactivar un bloque.

Prueba 6

Actualizar interlinking.

Prueba 7

Actualizar menú.

Prueba 8

Cambiar una plantilla.

Prueba 9

Ejecutar dos veces la misma operación.

Resultado esperado:

sin duplicados

---

44. FASE DE IMPLEMENTACIÓN REAL

Cuando se disponga de PC:

1. Instalar/configurar WordPress.
2. Elegir tema.
3. Crear plantillas.
4. Crear estructura de bloques.
5. Configurar API.
6. Crear credenciales.
7. Crear workflow N8N.
8. Conectar IA.
9. Ejecutar primera landing.
10. Verificar.
11. Probar actualización.
12. Escalar.

---

45. FUENTES DE VERDAD

modelo-datos.md
→ modelo común

sistema-bloques.md
→ bloques B01–B23

contrato-salida-ia.md
→ salida de IA

modelo-datos-wordpress.md
→ datos almacenados en WordPress

modelo-renderizado-wordpress.md
→ renderizado

integracion-n8n-wordpress.md
→ comunicación N8N/WordPress

arquitectura-wordpress.md
→ arquitectura técnica WordPress

Cada documento debe mantener una responsabilidad única.

---

46. REGLA FINAL

La arquitectura WordPress debe permanecer:

SIMPLE
MODULAR
INDEPENDIENTE DEL TEMA
IDEMPOTENTE
ESCALABLE
ACTUALIZABLE

El objetivo no es construir cientos de páginas manualmente.

El objetivo es construir un sistema capaz de producir y mantener cientos o miles de páginas mediante datos y plantillas reutilizables.

---

47. ESTADO

Versión: 2.0
Estado: Preparado para implementación piloto.

Siguiente fase:

VALIDACIÓN DOCUMENTAL
↓
MODELO WORDPRESS
↓
PLANTILLAS
↓
API
↓
N8N
↓
PRIMERA LANDING

FIN
