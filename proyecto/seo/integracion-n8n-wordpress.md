INTEGRACIÓN N8N → WORDPRESS

1. FUNCIÓN

Este documento define cómo N8N transforma la salida estructurada de la IA en una landing real dentro de WordPress.

Flujo:

OPORTUNIDAD
↓
MOTOR SEO
↓
ARQUITECTURA
↓
IA
↓
JSON
↓
N8N
↓
VALIDACIÓN
↓
TRANSFORMACIÓN
↓
WORDPRESS
↓
LANDING

N8N es el orquestador técnico.

No decide la estrategia SEO.

---

2. RESPONSABILIDADES

Motor SEO

Decide:

- oportunidad;
- creación;
- tipo de página;
- URL;
- canonical;
- arquitectura.

IA

Genera:

- contenido;
- SEO;
- datos de bloques;
- navegación;
- FAQ;
- enlaces;
- estructura JSON.

N8N

Realiza:

- recepción;
- validación;
- transformación;
- creación;
- actualización;
- registro;
- control de errores.

WordPress

Realiza:

- almacenamiento;
- renderizado;
- publicación.

---

3. ENTRADA

N8N recibe exclusivamente el JSON definido en:

proyecto/seo/contrato-salida-ia.md

Ejemplo:

{
  "schema_version": "1.0",
  "opportunity_id": "OPP-0001",
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

4. PRIMERA VALIDACIÓN

N8N debe comprobar:

1. JSON válido.
2. "schema_version".
3. "opportunity_id".
4. "status".
5. URL.
6. canonical.
7. identidad.
8. tipo de página.
9. bloques.
10. incidencias.
11. campos obligatorios.

Si falla una comprobación crítica:

DETENER
↓
NO PUBLICAR
↓
REGISTRAR ERROR

---

5. VALIDACIÓN DE URL

N8N debe comprobar que:

architecture.url

coincide con la arquitectura recibida.

Ejemplo:

/fontanero/marbella/

No debe transformarse en:

/fontanero/desatascos/marbella/

si la oportunidad no tiene subservicio.

La URL es un dato protegido.

---

6. VALIDACIÓN DE CANONICAL

Debe existir coherencia entre:

architecture.url
architecture.canonical

Ejemplo:

URL:
/fontanero/marbella/

Canonical:
/fontanero/marbella/

Si existe discrepancia:

REVIEW

y no se publica.

---

7. COMPROBACIÓN DE EXISTENCIA

Antes de crear una página, N8N debe comprobar si la URL ya existe.

Estados:

NO EXISTE
EXISTE
ERROR

---

8. SI LA URL NO EXISTE

Flujo:

NO EXISTE
↓
VALIDACIÓN
↓
CREAR PÁGINA

---

9. SI LA URL YA EXISTE

N8N no debe crear un duplicado.

Debe comprobar:

- si pertenece a la misma oportunidad;
- si puede actualizarse;
- si existe conflicto.

Estados:

ACTUALIZAR
REVISAR
NO TOCAR

---

10. MODO DE PUBLICACIÓN

El sistema debe permitir inicialmente:

DRAFT

y posteriormente:

PUBLISH

Durante la fase de desarrollo se recomienda:

IA
↓
N8N
↓
WORDPRESS
↓
DRAFT

para poder revisar las primeras generaciones.

---

11. CREACIÓN DE PÁGINA

N8N deberá enviar a WordPress como mínimo:

title
slug
content
status

La implementación concreta dependerá de la API y del sistema de plantillas elegido.

---

12. URL Y SLUG

La URL estratégica no debe generarse mediante un slug improvisado.

N8N debe utilizar la arquitectura recibida.

Ejemplo:

URL:
/fontanero/marbella/

Slug:
fontanero/marbella

Si WordPress requiere una estructura concreta de página padre/hija, N8N deberá traducirla respetando la URL final.

---

13. PÁGINA PADRE

Cuando sea necesario:

/fontanero/

puede actuar como página padre.

La landing:

/fontanero/marbella/

podrá quedar relacionada con ella.

La existencia de la página padre deberá estar validada antes de crear la hija.

---

14. LANDING DE SERVICIO + LOCALIDAD

Ejemplo:

/fontanero/marbella/

Datos:

Servicio:
Fontanero

Municipio:
Marbella

Tipo:
servicio_localidad

---

15. LANDING DE SERVICIO + SUBSERVICIO + LOCALIDAD

Ejemplo:

/fontanero/desatascos/marbella/

Datos:

Servicio:
Fontanero

Subservicio:
Desatascos

Municipio:
Marbella

Tipo:
servicio_subservicio_localidad

---

16. TRANSFORMACIÓN DE BLOQUES

La IA devuelve:

{
  "blocks": [
    {
      "id": "B01",
      "type": "hero",
      "enabled": true,
      "data": {}
    }
  ]
}

N8N transforma cada bloque en el formato que utilice WordPress.

Conceptualmente:

B01
↓
componente Hero

B02
↓
componente contenido

B03
↓
componente servicios

---

17. REGLA DE BLOQUES

N8N no debe aceptar bloques que no estén autorizados.

Debe comprobar:

block.id
block.type
block.enabled
block.data

contra:

proyecto/seo/sistema-bloques.md

---

18. BLOQUES DESACTIVADOS

Si:

{
  "enabled": false
}

N8N no debe renderizar ese bloque.

---

19. BLOQUES OBLIGATORIOS

Si falta un bloque obligatorio:

ERROR

o:

REVIEW

según la gravedad definida.

Nunca debe solucionarse inventando contenido.

---

20. ORDEN DE BLOQUES

El orden recibido por la IA debe conservarse.

Ejemplo:

B01
B02
B03
B08
B09

se renderiza en ese orden.

La IA no debe devolver bloques desordenados si el sistema exige una secuencia determinada.

---

21. HEADER

N8N debe utilizar la configuración global de WordPress para:

- logo;
- menú principal;
- navegación;
- elementos globales.

La IA no debe duplicar elementos globales innecesariamente.

---

22. MENÚ

La IA puede devolver elementos específicos de la landing.

N8N debe validar:

label
url
type

Los anchors deben existir realmente en la página.

Ejemplo:

#servicios
#faq
#contacto

Si el bloque correspondiente no existe, N8N debe eliminar el enlace o marcar la landing para revisión.

---

23. CONTENIDO

N8N debe insertar el contenido generado por la IA en los componentes correspondientes.

No debe alterar el contenido semántico salvo:

- sanitización;
- escape;
- conversión técnica;
- formato necesario para WordPress.

---

24. SEO

Los campos:

seo.title
seo.meta_description
seo.h1

deben llegar a WordPress o al plugin SEO utilizado.

La implementación exacta dependerá del sistema SEO instalado.

---

25. CANONICAL

N8N debe configurar la canonical según:

architecture.canonical

No debe calcular una canonical diferente.

---

26. SCHEMA

Si la IA devuelve:

schema.type
schema.data

N8N deberá enviarlo al mecanismo de datos estructurados correspondiente.

Solo se publicará si pasa la validación.

---

27. IMÁGENES

La IA puede indicar qué imágenes necesita.

N8N podrá:

1. buscar una imagen autorizada;
2. utilizar una biblioteca existente;
3. solicitar generación;
4. dejar placeholder;
5. enviar a revisión.

Nunca debe inventar una URL.

---

28. ALT

El texto ALT será tomado del campo:

images[].alt

Debe describir la imagen.

No debe utilizarse para keyword stuffing.

---

29. ENLACES INTERNOS

N8N debe comprobar que cada:

internal_links[].url

existe o está autorizada.

Si no:

NO PUBLICAR ENLACE

No se deben crear enlaces rotos.

---

30. SANITIZACIÓN

Antes de enviar contenido a WordPress, N8N debe aplicar las medidas técnicas necesarias para:

- evitar HTML peligroso;
- evitar scripts no autorizados;
- evitar contenido malformado;
- evitar inyección;
- mantener estructura válida.

---

31. DATOS COMERCIALES

N8N no debe completar automáticamente:

- teléfono;
- WhatsApp;
- email;
- dirección;
- horario;
- precio;

si no están presentes en los datos autorizados.

---

32. PUBLICACIÓN

El flujo inicial recomendado:

GENERAR
↓
VALIDAR
↓
CREAR DRAFT
↓
REVISIÓN
↓
PUBLISH

Cuando el sistema esté suficientemente validado podrá evolucionar hacia:

GENERAR
↓
VALIDAR
↓
PUBLICAR AUTOMÁTICAMENTE

---

33. CONTROL DE ERRORES

Cada ejecución debe registrar:

opportunity_id
url
fecha
estado
error
resultado

Estados posibles:

SUCCESS
REVIEW
ERROR
SKIPPED

---

34. IDEMPOTENCIA

La misma oportunidad no debe crear páginas duplicadas.

La combinación:

opportunity_id
url

debe permitir identificar la operación.

Si N8N recibe dos veces la misma oportunidad:

OPP-0001
/fontanero/marbella/

debe detectar que ya existe una operación relacionada.

---

35. ACTUALIZACIÓN

Si la landing ya existe y se determina que debe actualizarse:

VALIDAR
↓
ACTUALIZAR
↓
REGISTRAR

No se debe duplicar.

---

36. REGISTRO

N8N deberá registrar como mínimo:

{
  "opportunity_id": "",
  "url": "",
  "wordpress_id": "",
  "status": "",
  "timestamp": "",
  "schema_version": "",
  "prompt_version": ""
}

---

37. WORDPRESS_ID

Una vez creada la página, N8N debe guardar el identificador de WordPress.

Ejemplo:

wordpress_id = 1234

Esto permitirá futuras actualizaciones.

---

38. RELACIÓN OPPORTUNITY → WORDPRESS

Debe poder reconstruirse:

OPP-0001
↓
/fontanero/marbella/
↓
WordPress ID 1234

Esto permitirá controlar todo el ciclo de vida de la landing.

---

39. REINTENTOS

Si una llamada a WordPress falla por un error temporal:

RETRY

debe poder ejecutarse de forma controlada.

No deben generarse duplicados.

---

40. ERROR PERMANENTE

Si el error no es recuperable:

ERROR

La operación debe quedar registrada.

No debe continuar automáticamente hacia publicación.

---

41. RESPUESTA DE WORDPRESS

N8N debe registrar como mínimo:

wordpress_id
url
status
response
timestamp

---

42. VALIDACIÓN POSTERIOR

Después de crear la página, N8N debería comprobar:

1. página creada;
2. URL correcta;
3. estado correcto;
4. contenido presente;
5. SEO presente;
6. canonical presente;
7. bloques presentes;
8. enlaces válidos.

---

43. VALIDACIÓN DE URL FINAL

Debe comprobarse que WordPress realmente genera:

/fontanero/marbella/

y no una URL distinta.

Si WordPress genera una URL incorrecta:

ERROR

y la landing no se considera válida.

---

44. PUBLICACIÓN SEGURA

La publicación automática solo estará permitida cuando:

IA = READY
+
VALIDACIÓN = OK
+
WORDPRESS = OK

Si cualquiera falla:

NO PUBLICAR

---

45. FLUJO COMPLETO

El workflow final será conceptualmente:

TRIGGER
↓
RECIBIR OPORTUNIDAD
↓
OBTENER DATOS
↓
MOTOR SEO
↓
ARQUITECTURA
↓
GENERAR INPUT IA
↓
LLAMAR IA
↓
RECIBIR JSON
↓
VALIDAR JSON
↓
VALIDAR ARQUITECTURA
↓
VALIDAR BLOQUES
↓
VALIDAR CONTENIDO
↓
COMPROBAR URL
↓
COMPROBAR SI EXISTE
↓
CREAR / ACTUALIZAR WORDPRESS
↓
CONFIGURAR SEO
↓
CONFIGURAR CANONICAL
↓
CONFIGURAR SCHEMA
↓
CONFIGURAR ENLACES
↓
VALIDAR RESULTADO
↓
REGISTRAR
↓
DRAFT / PUBLISH

---

46. PRIMERA PRUEBA

La primera prueba del sistema será:

Servicio:
Fontanero

Municipio:
Marbella

Provincia:
Málaga

Subservicio:
null

Resultado esperado:

URL:
/fontanero/marbella/

La IA deberá generar:

- SEO;
- H1;
- menú;
- bloques;
- contenido;
- FAQ;
- CTA;
- enlaces;
- validación.

N8N deberá transformar esa salida en una página WordPress.

---

47. SEGUNDA PRUEBA

Posteriormente:

Servicio:
Fontanero

Subservicio:
Desatascos

Municipio:
Marbella

Provincia:
Málaga

Resultado esperado:

URL:
/fontanero/desatascos/marbella/

Debe generarse una landing diferente y específica.

---

48. PRUEBA MASIVA

Una vez superadas las pruebas individuales:

5 oportunidades
↓
5 generaciones
↓
5 validaciones
↓
5 páginas

Después:

100 oportunidades
↓
100 landings

El sistema debe mantener:

- URLs correctas;
- ausencia de duplicados;
- coherencia;
- trazabilidad;
- control de errores.

---

49. IMPLEMENTACIÓN TÉCNICA PENDIENTE

Este documento define la lógica de integración.

Todavía deben definirse los detalles concretos de:

- instalación de WordPress;
- API utilizada;
- autenticación;
- sistema de plantillas;
- constructor visual, si existe;
- campos personalizados;
- mecanismo exacto de bloques;
- plugin SEO;
- gestión de imágenes;
- base de datos o registro de oportunidades.

Estos elementos se concretarán cuando se configure el entorno real.

---

50. PRINCIPIO DE SEGURIDAD

N8N nunca debe publicar una landing únicamente porque la IA haya devuelto contenido.

Debe existir una cadena de validación.

IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
VALIDACIÓN
↓
PUBLICACIÓN

---

51. PRINCIPIO DE SEPARACIÓN

El sistema mantiene separadas:

ESTRATEGIA
→ Motor SEO

CONTENIDO
→ IA

AUTOMATIZACIÓN
→ N8N

RENDERIZADO
→ WordPress

Esto permite modificar una capa sin reconstruir todo el sistema.

---

52. ESTADO

DEFINIDO COMO ESPECIFICACIÓN FUNCIONAL.

Este documento establece cómo debe funcionar la integración.

Los datos concretos de API, WordPress y entorno se definirán durante la implementación técnica.

El siguiente objetivo es realizar una prueba completa con una oportunidad real de ejemplo antes de construir el workflow definitivo de N8N.
