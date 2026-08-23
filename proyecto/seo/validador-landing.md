# VALIDADOR DE LANDING

## 1. OBJETIVO

Este documento define las reglas del sistema que valida una landing generada por IA antes de permitir que continúe hacia N8N y, posteriormente, WordPress.

El validador comprueba que la salida de IA:

- respeta el contexto protegido;
- cumple el contrato de salida;
- mantiene la identidad de la oportunidad;
- respeta la arquitectura autorizada cuando exista;
- utiliza únicamente bloques permitidos;
- no inventa información;
- mantiene coherencia SEO;
- no introduce enlaces no autorizados;
- no presenta errores estructurales;
- puede continuar o debe quedar bloqueada.

Flujo:

MAESTRO
↓
OPORTUNIDAD
↓
CONTEXTO PROTEGIDO
↓
IA
↓
OUTPUT IA
↓
VALIDADOR
↓
READY / REVIEW / ERROR
↓
N8N
↓
WORDPRESS

---

# 2. PRINCIPIO FUNDAMENTAL

El modelo maestro es la fuente de verdad.

La IA genera contenido.

La IA NO tiene autoridad para modificar:

- la oportunidad;
- la decisión SEO;
- la identidad;
- la arquitectura;
- las URLs protegidas;
- los bloques autorizados;
- las reglas de publicación.

El validador compara la salida de IA contra el contexto protegido.

---

# 3. SEPARACIÓN DE MODELOS

El sistema utiliza tres capas:

## 3.1 MODELO MAESTRO

Representa los datos canónicos del proyecto.

Ejemplos:

- servicio;
- municipio;
- provincia;
- decisión SEO;
- arquitectura;
- URLs;
- profundidad;
- estado;
- relaciones.

---

## 3.2 CONTRATO IA

Define el formato que debe devolver la IA.

Puede utilizar nombres técnicos diferentes al modelo maestro.

Ejemplo:

Modelo maestro:

servicio

Contrato IA:

service

Modelo maestro:

municipio

Contrato IA:

municipality

Esta diferencia es válida siempre que exista una correspondencia definida.

---

## 3.3 CONTEXTO PROTEGIDO

Es la información que el validador recibe directamente del sistema y no de la IA.

La IA no puede modificarla.

Ejemplo conceptual:

{
  "opportunity_id": "TEST-FONTANERO-MARBELLA",
  "decision_seo": "CREAR",
  "identity": {},
  "architecture": {},
  "authorized_blocks": []
}

---

# 4. ENTRADA DEL VALIDADOR

El validador recibe:

{
  "protected_context": {},
  "ai_output": {}
}

## protected_context

Contiene la información de confianza.

## ai_output

Contiene exclusivamente la salida generada por la IA.

---

# 5. ARQUITECTURA Y DECISIÓN SEO

La arquitectura definitiva depende de la decisión SEO.

Si:

decision_seo = CREAR

puede existir una arquitectura definitiva que debe ser respetada.

Si:

decision_seo != CREAR

no se debe asumir que existe una arquitectura definitiva de publicación.

Por tanto, el validador debe distinguir entre:

- contexto de oportunidad;
- arquitectura definitiva;
- fixture de prueba.

---

# 6. RESULTADOS

El validador puede producir:

READY

REVIEW

ERROR

Además calcula:

publication_allowed

---

# 7. READY

READY significa:

"La salida de IA supera las validaciones automáticas y puede continuar hacia la siguiente fase."

READY NO significa necesariamente:

"publicar".

Una landing puede estar:

READY

y:

publication_allowed = false

---

# 8. REVIEW

REVIEW significa:

"La salida no presenta necesariamente un error técnico, pero existe una cuestión que requiere revisión humana."

Ejemplos:

- información insuficiente;
- posible duplicación;
- diferenciación insuficiente;
- evidencia local insuficiente;
- contenido ambiguo;
- afirmación que requiere comprobación.

REVIEW bloquea la publicación automática.

---

# 9. ERROR

ERROR significa:

"Existe un incumplimiento técnico, estructural o de integridad."

Ejemplos:

- JSON inválido;
- campo obligatorio ausente;
- identidad modificada;
- arquitectura modificada;
- URL modificada;
- bloque no autorizado;
- dato inventado;
- enlace no autorizado.

ERROR bloquea el proceso.

---

# 10. REGLA DE AUTORIDAD

El resultado de la IA nunca tiene prioridad sobre el validador.

Ejemplo:

IA:

status = READY

VALIDADOR:

ERROR

Resultado final:

ERROR

Otro ejemplo:

IA:

status = READY

VALIDADOR:

READY

decision_seo = INVESTIGAR

Resultado:

status = READY
publication_allowed = false

---

# 11. VALIDACIÓN ESTRUCTURAL

## V001 — JSON

La salida debe ser JSON válido.

Si no:

ERROR

---

## V002 — schema_version

Debe existir y ser compatible con la versión aceptada.

Si no:

ERROR

---

## V003 — opportunity_id

Debe existir.

Debe corresponder al contexto protegido.

Si no:

ERROR

---

## V004 — campos obligatorios

Deben existir los campos obligatorios definidos por el contrato IA.

Si falta un campo estructural obligatorio:

ERROR

---

# 12. CORRESPONDENCIA CON EL MODELO MAESTRO

El validador debe realizar explícitamente la correspondencia entre:

MODELO MAESTRO

y:

CONTRATO IA.

Ejemplo:

maestro.servicio
↕
ia.identity.service

maestro.municipio
↕
ia.identity.municipality

La traducción no debe depender de una interpretación de la IA.

---

# 13. IDENTIDAD

Cuando exista identidad protegida, debe coincidir:

- servicio;
- subservicio;
- municipio;
- provincia;
- sector cuando corresponda.

La IA no puede cambiar:

Marbella

por:

Estepona.

Resultado:

ERROR

---

# 14. ARQUITECTURA PROTEGIDA

Cuando exista arquitectura definitiva, el validador debe comprobar:

- tipo de página;
- URL;
- canonical;
- parent_url;
- profundidad;
- cualquier otro campo protegido definido por el maestro.

La IA no puede modificar estos valores.

---

# 15. URL

Cuando exista una URL protegida:

La URL generada debe coincidir exactamente con la autorizada.

No se permite:

- cambiar localidad;
- cambiar servicio;
- crear parámetros;
- modificar estructura;
- inventar URLs.

Ejemplo:

Autorizada:

/fontanero/marbella/

IA:

/fontanero/estepona/

Resultado:

ERROR

---

# 16. CANONICAL

Cuando exista canonical protegida:

Debe coincidir con la arquitectura.

La IA no puede calcular una canonical diferente.

Si existe una canonical incorrecta:

ERROR

---

# 17. BLOQUES

La IA solo puede utilizar bloques incluidos en:

authorized_blocks

Un bloque no autorizado produce:

ERROR

---

# 18. IDENTIDAD DEL BLOQUE

Cada bloque debe mantener correspondencia entre:

id

y:

type

Ejemplo:

B03 → hero

Si:

B03 → faq

resultado:

ERROR

---

# 19. BLOQUES OBLIGATORIOS

Cuando la arquitectura establezca bloques obligatorios, deben estar presentes.

Si falta un bloque obligatorio:

ERROR

salvo que exista una excepción explícitamente autorizada.

---

# 20. BLOQUES CONDICIONALES

Un bloque condicional puede omitirse cuando no exista información suficiente.

No se debe inventar información únicamente para completar el bloque.

Ejemplo:

B10 — coverage

Si no existe información real de cobertura:

puede omitirse.

---

# 21. NO INVENCIÓN

La IA no puede inventar:

- empresas;
- nombres comerciales;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- garantías;
- certificaciones;
- experiencia;
- testimonios;
- reseñas;
- casos;
- disponibilidad;
- cobertura;
- zonas;
- datos comerciales.

---

# 22. DATOS COMERCIALES

Los datos comerciales son especialmente sensibles.

Incluyen:

- teléfono;
- WhatsApp;
- email;
- precios;
- horarios;
- garantías;
- disponibilidad.

Si aparecen sin estar respaldados por el contexto:

ERROR

---

# 23. DATOS LOCALES

Los datos locales requieren evidencia.

Ejemplos:

- barrios;
- urbanizaciones;
- zonas;
- cobertura;
- tiempos de desplazamiento;
- características específicas de la localidad.

Si existe información insuficiente:

REVIEW

Si se detecta una invención clara:

ERROR

---

# 24. TESTIMONIOS

No se pueden generar testimonios ficticios.

Si un testimonio no tiene fuente o respaldo:

ERROR

---

# 25. CASOS

No se pueden inventar:

- clientes;
- trabajos;
- resultados;
- fechas;
- ubicaciones.

Si aparecen sin respaldo:

ERROR

---

# 26. PRECIOS

No se pueden inventar precios.

Ejemplo:

"Desde 50 €"

si el dato no existe en el contexto.

Resultado:

ERROR

---

# 27. HORARIOS

No se pueden inventar horarios.

Ejemplo:

"Servicio 24 horas"

sin respaldo.

Resultado:

ERROR

---

# 28. COBERTURA

La cobertura debe proceder de información disponible y autorizada.

Si no existe:

el bloque puede omitirse.

No se puede completar con barrios o zonas inventadas.

---

# 29. CONFIANZA

No se pueden generar afirmaciones como:

- más de 20 años de experiencia;
- profesionales certificados;
- servicio 24 horas;
- garantía de 2 años;
- cientos de clientes;

si no existe respaldo.

Resultado:

ERROR

---

# 30. IMÁGENES

No se deben presentar imágenes como representativas de una empresa real si no existe una fuente autorizada.

Las imágenes deben disponer, cuando corresponda, de:

- fuente;
- referencia;
- URL;
- archivo autorizado.

---

# 31. ENLACES INTERNOS

Los enlaces deben utilizar únicamente URLs autorizadas.

No se permite:

- URL inventada;
- URL inexistente;
- URL fuera de arquitectura;
- enlace a una página no aprobada.

Resultado:

ERROR

---

# 32. SEO

La salida debe mantener coherencia entre:

- title;
- meta description;
- H1;
- slug;
- intención;
- servicio;
- localidad.

No debe introducir:

- servicios inexistentes;
- localidades diferentes;
- promesas no respaldadas.

---

# 33. SLUG

Cuando exista arquitectura definitiva:

El slug debe corresponder con la URL autorizada.

Si no:

ERROR

---

# 34. FAQ

Las FAQ deben:

- estar relacionadas con la intención;
- responder preguntas útiles;
- no inventar datos;
- no utilizarse únicamente para introducir keywords.

Una FAQ con información dudosa:

REVIEW

Una FAQ con información inventada:

ERROR

---

# 35. CTA

El CTA debe utilizar acciones autorizadas.

Ejemplos:

- contactar;
- solicitar información;
- solicitar presupuesto;
- pedir cita.

No puede utilizar:

- teléfono inventado;
- WhatsApp inventado;
- precio inventado;
- disponibilidad inventada.

---

# 36. DUPLICACIÓN

El sistema puede detectar señales de contenido potencialmente duplicado.

Puede comparar:

- title;
- H1;
- contenido;
- estructura;
- bloques.

Una posible duplicación no implica automáticamente ERROR.

Resultado:

REVIEW

---

# 37. DIFERENCIACIÓN

Una landing local no debe limitarse a cambiar el nombre de la localidad.

Si el contenido resulta excesivamente genérico o intercambiable:

REVIEW

No se debe exigir una diferenciación artificial inventando datos locales.

---

# 38. DECISIÓN SEO

La decisión SEO pertenece al sistema maestro.

La IA no puede modificarla.

Ejemplo:

decision_seo = INVESTIGAR

La IA no puede convertirla en:

CREAR

---

# 39. PUBLICATION_ALLOWED

publication_allowed debe calcularlo el validador.

No debe aceptarse directamente desde la IA.

Regla mínima:

decision_seo != CREAR
→ publication_allowed = false

Además, debe ser false si:

- status = REVIEW;
- status = ERROR;
- existe una incidencia crítica;
- falta una autorización necesaria.

---

# 40. READY Y PUBLICACIÓN

Puede existir:

status = READY
publication_allowed = false

Esto es completamente válido.

Ejemplo:

decision_seo = INVESTIGAR
status = READY
publication_allowed = false

---

# 41. MODO TEST

Las pruebas deben utilizar un identificador independiente.

Ejemplo:

TEST-FONTANERO-MARBELLA

El modo TEST:

- no modifica oportunidades reales;
- no modifica el maestro;
- no publica;
- no modifica WordPress;
- no cambia decisiones SEO.

---

# 42. FIXTURE TEST-FONTANERO-MARBELLA

El fixture es una prueba técnica.

No debe interpretarse como una oportunidad real autorizada para publicación.

Su objetivo es probar:

- estructura;
- identidad;
- bloques;
- SEO;
- no invención;
- validación;
- bloqueo de publicación.

---

# 43. CASOS DE PRUEBA MÍNIMOS

## TEST 01 — correcto

Resultado:

READY

---

## TEST 02 — cambio de localidad

Marbella → Estepona.

Resultado:

ERROR

---

## TEST 03 — bloque no autorizado

IA añade B10 cuando no está autorizado.

Resultado:

ERROR

---

## TEST 04 — teléfono inventado

Resultado:

ERROR

---

## TEST 05 — precio inventado

Resultado:

ERROR

---

## TEST 06 — contenido genérico

Resultado:

REVIEW

---

## TEST 07 — posible duplicación

Resultado:

REVIEW

---

## TEST 08 — página técnicamente correcta + INVESTIGAR

Resultado:

READY

publication_allowed = false

---

# 44. SALIDA DEL VALIDADOR

Formato previsto:

{
  "status": "READY",
  "publication_allowed": false,
  "errors": [],
  "warnings": [],
  "checks": {},
  "traceability": {}
}

---

# 45. CHECKS

Ejemplo:

{
  "json_valid": true,
  "schema_version_valid": true,
  "opportunity_id_valid": true,
  "identity_valid": true,
  "architecture_valid": true,
  "url_valid": true,
  "canonical_valid": true,
  "blocks_valid": true,
  "blocks_authorized": true,
  "seo_valid": true,
  "links_valid": true,
  "no_invention": true,
  "publication_allowed": false
}

---

# 46. ERRORES Y WARNINGS

Los errores deben registrar:

- código;
- mensaje;
- gravedad;
- campo afectado cuando corresponda.

Ejemplo:

{
  "code": "V005",
  "severity": "ERROR",
  "field": "identity.municipality",
  "message": "La localidad generada no coincide con el contexto protegido."
}

Los warnings pueden utilizarse para incidencias no críticas.

---

# 47. TRAZABILIDAD

La validación debe registrar:

- opportunity_id;
- fecha;
- schema_version;
- versión del validador;
- resultado;
- errores;
- warnings;
- origen del input.

---

# 48. ORDEN DE VALIDACIÓN

El orden recomendado es:

1. JSON
2. schema_version
3. opportunity_id
4. correspondencia con modelo maestro
5. identidad
6. arquitectura
7. URL
8. canonical
9. bloques
10. id/type
11. SEO
12. datos
13. enlaces
14. no invención
15. duplicación
16. trazabilidad
17. publicación

---

# 49. INTEGRACIÓN CON N8N

El validador será implementado inicialmente como lógica ejecutable dentro de N8N.

Flujo:

IA
↓
Code Node / Validador
↓
IF status
├── READY
├── REVIEW
└── ERROR

No se necesita inicialmente:

- servidor independiente;
- API propia;
- aplicación externa;
- infraestructura adicional.

---

# 50. INTEGRACIÓN CON WORDPRESS

WordPress nunca debe recibir directamente la salida de IA.

Flujo obligatorio:

IA
↓
VALIDADOR
↓
N8N
↓
WORDPRESS

Si:

ERROR

no continúa.

Si:

REVIEW

no publica automáticamente.

Si:

READY

puede continuar siempre que:

publication_allowed = true

---

# 51. REGLA DE SEGURIDAD

Ninguna capa debe confiar ciegamente en otra.

La IA genera.

El contexto protegido define la verdad.

El validador comprueba.

N8N orquesta.

WordPress ejecuta la publicación autorizada.

---

# 52. PRINCIPIO FINAL

La arquitectura del sistema debe impedir que una IA pueda convertir por sí sola:

- INVESTIGAR → CREAR;
- una URL no autorizada → URL válida;
- un dato inventado → dato real;
- REVIEW → publicación;
- ERROR → publicación.

El validador constituye una barrera independiente entre generación y publicación.

---

# 53. ESTADO DEL DOCUMENTO

Estado:

ACTIVO

Versión:

2.0

Fecha:

2026-08-23

Motivo:

Consolidación del sistema de validación y alineación con el modelo maestro y el contrato IA.

Siguiente evolución:

Implementación del validador como Code Node de N8N y ejecución de los casos de prueba definidos.
