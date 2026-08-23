# VALIDADOR DE LANDING

## 1. FUNCIÓN

Este documento define las reglas de validación de una landing generada por IA.

Su función es comprobar que la salida:

- cumple el contrato;
- respeta la arquitectura;
- utiliza únicamente bloques autorizados;
- no contiene datos inventados;
- mantiene la coherencia con la oportunidad;
- puede continuar hacia N8N;
- o debe quedar bloqueada para revisión.

Flujo:

IA
↓
JSON
↓
VALIDADOR
↓
READY / REVIEW / ERROR
↓
N8N
↓
WORDPRESS

El validador no decide si una oportunidad debe existir.

---

# 2. PRINCIPIO FUNDAMENTAL

La validación debe ser determinista siempre que sea posible.

No debe depender de una interpretación subjetiva de la IA.

Las reglas deben poder convertirse posteriormente en:

- código;
- nodos N8N;
- validaciones JSON Schema;
- reglas de WordPress.

---

# 3. RESULTADOS

El validador puede producir:

READY

REVIEW

ERROR

---

## READY

La salida:

- es estructuralmente válida;
- cumple el contrato;
- respeta la arquitectura;
- utiliza bloques autorizados;
- no presenta incidencias críticas;
- contiene todos los datos necesarios para continuar.

READY no significa:

"publicar inmediatamente".

Significa:

"puede continuar hacia la siguiente fase del proceso".

---

## REVIEW

Existe una incidencia que requiere revisión humana.

Ejemplos:

- información insuficiente;
- bloque condicional sin evidencia suficiente;
- posible duplicación;
- dato que necesita comprobación;
- contenido potencialmente ambiguo;
- información comercial incompleta.

Una salida REVIEW no puede publicarse automáticamente.

---

## ERROR

Existe un incumplimiento técnico o estructural.

Ejemplos:

- JSON inválido;
- schema_version incorrecta;
- opportunity_id inexistente;
- URL modificada;
- canonical incorrecto;
- bloque no autorizado;
- estructura inválida;
- campo obligatorio ausente;
- contradicción con datos protegidos.

Una salida ERROR queda bloqueada.

---

# 4. NIVELES DE VALIDACIÓN

La validación se divide en:

1. ESTRUCTURA
2. IDENTIDAD
3. ARQUITECTURA
4. BLOQUES
5. CONTENIDO
6. DATOS
7. ENLACES
8. SEO
9. PUBLICACIÓN
10. TRAZABILIDAD

---

# 5. VALIDACIÓN ESTRUCTURAL

## V001 — JSON válido

La salida debe ser JSON válido.

Si no:

ERROR

---

## V002 — schema_version

Debe existir:

schema_version

Debe ser compatible con la versión aceptada.

Actualmente:

1.1

Si no:

ERROR

---

## V003 — opportunity_id

Debe existir:

opportunity_id

Debe corresponder con la oportunidad utilizada como entrada.

Si no:

ERROR

---

## V004 — campos principales

Deben existir:

- schema_version;
- opportunity_id;
- status;
- identity;
- architecture;
- seo;
- blocks;
- validation;
- issues;
- traceability.

Si falta alguno:

ERROR

---

# 6. VALIDACIÓN DE IDENTIDAD

La identidad debe coincidir exactamente con los datos recibidos.

Campos:

- sector;
- service;
- subservice;
- municipality;
- province.

No se permite que la IA modifique:

- servicio;
- subservicio;
- municipio;
- provincia.

Ejemplo:

Entrada:

Marbella

Salida:

Estepona

Resultado:

ERROR

---

# 7. VALIDACIÓN DE ARQUITECTURA

La arquitectura es un dato protegido.

Debe coincidir exactamente con la entrada.

Campos:

- page_type;
- url;
- canonical;
- parent_url.

La IA no puede:

- crear una URL;
- cambiar una URL;
- cambiar canonical;
- cambiar parent_url;
- cambiar page_type.

Si lo hace:

ERROR

---

# 8. VALIDACIÓN DE URL

La URL debe:

- coincidir con la arquitectura;
- utilizar una estructura autorizada;
- no contener URLs inventadas;
- no contener parámetros no autorizados;
- no apuntar a otra localidad;
- no apuntar a otro servicio.

Ejemplo válido:

/fontanero/marbella/

Ejemplo inválido:

/fontanero/estepona/

Resultado:

ERROR

---

# 9. VALIDACIÓN DE CANONICAL

La canonical debe existir cuando la página sea indexable.

Debe coincidir con la arquitectura recibida.

Si falta cuando es obligatoria:

ERROR

Si existe pero es diferente:

ERROR

La IA nunca calcula la canonical.

La recibe como dato protegido.

---

# 10. VALIDACIÓN DE SEO

Debe existir:

- title;
- meta_description;
- h1;
- slug.

## TITLE

Debe corresponder con la intención.

No debe introducir:

- servicios inexistentes;
- localidades distintas;
- promesas no respaldadas.

## META DESCRIPTION

No debe contener:

- datos inventados;
- precios inventados;
- garantías inventadas;
- disponibilidad inventada.

## H1

Debe corresponder con:

- servicio;
- subservicio cuando corresponda;
- localidad.

## SLUG

Debe corresponder exactamente con la URL autorizada.

---

# 11. VALIDACIÓN DE BLOQUES

Todos los bloques deben pertenecer al conjunto autorizado:

B01-B23.

No se permiten IDs nuevos.

Ejemplo:

B99

Resultado:

ERROR

---

# 12. ID Y TYPE

Cada bloque debe mantener correspondencia:

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

Si:

id = B03

pero:

type = faq

resultado:

ERROR

---

# 13. BLOQUES NO AUTORIZADOS

La IA no puede generar un bloque que no haya sido autorizado.

Ejemplo:

Entrada:

authorized_blocks:

B01
B02
B03
B04
B05
B06
B08
B14

Salida:

B10

Resultado:

ERROR

---

# 14. BLOQUES OBLIGATORIOS

La validación debe comprobar que los bloques definidos como obligatorios por la arquitectura estén presentes.

No se puede eliminar silenciosamente un bloque obligatorio.

Si falta:

ERROR

o:

REVIEW

cuando la arquitectura permita una excepción explícita.

---

# 15. BLOQUES CONDICIONALES

Los bloques condicionales pueden estar ausentes.

Ejemplo:

B10 — cobertura

Si no existe información de cobertura:

puede omitirse.

No debe inventarse información para rellenarlo.

---

# 16. REGLA DE NO INVENCIÓN

La IA no puede inventar:

- empresas;
- nombres comerciales;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- experiencia;
- certificaciones;
- garantías;
- reseñas;
- testimonios;
- cobertura;
- zonas;
- casos;
- imágenes;
- disponibilidad.

Si un dato es necesario pero no existe:

REVIEW

o:

ERROR

según su importancia.

---

# 17. DATOS COMERCIALES

Los datos comerciales requieren especial control.

Ejemplos:

- teléfono;
- WhatsApp;
- email;
- precio;
- horario;
- garantía;
- disponibilidad.

Si aparecen sin haber sido proporcionados:

ERROR

La IA no puede rellenar estos campos con valores plausibles.

---

# 18. DATOS LOCALES

Los datos locales deben estar respaldados.

Ejemplos:

- barrios;
- urbanizaciones;
- zonas;
- cobertura;
- características locales;
- tiempos de desplazamiento.

Si aparecen sin evidencia:

REVIEW

Si son claramente inventados:

ERROR

---

# 19. COBERTURA

El bloque B10 requiere información real.

Si:

coverage_confirmed = false

entonces:

B10 no puede contener zonas inventadas.

Puede:

- omitirse;
- aparecer desactivado;
- generar REVIEW si se intentó utilizar.

---

# 20. CONFIANZA

B12 no puede contener afirmaciones no verificadas.

No se permiten:

"más de 20 años de experiencia"

"profesionales certificados"

"servicio 24 horas"

"garantía de 2 años"

si no existen como datos de entrada.

Resultado:

ERROR

---

# 21. TESTIMONIOS

B18 requiere testimonios reales.

No se permite que la IA genere testimonios ficticios.

Si aparecen testimonios sin fuente:

ERROR

---

# 22. CASOS

B19 requiere casos reales.

No se pueden inventar:

- clientes;
- trabajos;
- resultados;
- ubicaciones;
- fechas.

Si aparecen sin fuente:

ERROR

---

# 23. PRECIOS

B21 requiere datos de precios reales.

No se permiten precios estimados generados por IA.

Ejemplo prohibido:

"Desde 50 €"

si no existe ese dato.

Resultado:

ERROR

---

# 24. HORARIOS

B22 requiere horarios reales.

No se permite:

"24 horas"

"abierto todos los días"

si no existe evidencia.

Resultado:

ERROR

---

# 25. MAPA

B23 requiere ubicación real.

No se debe inventar:

- dirección;
- coordenadas;
- ubicación comercial.

Si no existe:

omitir.

---

# 26. IMÁGENES

No se deben inventar imágenes.

Cada imagen debe poder identificarse mediante:

- fuente;
- referencia;
- URL;
- archivo autorizado.

Si la imagen no está disponible:

puede omitirse.

No se debe crear una imagen como si representara una empresa real cuando no existe evidencia.

---

# 27. ENLACES INTERNOS

Todos los enlaces deben apuntar a URLs autorizadas.

No se permite:

- URL inexistente;
- URL inventada;
- URL fuera de arquitectura;
- URL hacia una página no aprobada.

Si aparece:

ERROR

---

# 28. MENU

Los elementos del menú deben utilizar URLs autorizadas.

No se pueden crear páginas nuevas únicamente para completar el menú.

---

# 29. SEO DUPLICADO

El validador debe detectar señales básicas de contenido potencialmente duplicado.

Debe comparar, cuando existan:

- title;
- H1;
- contenido;
- bloques;
- estructura.

Una similitud alta no implica automáticamente ERROR.

Resultado:

REVIEW

para evaluación.

---

# 30. DIFERENCIACIÓN

Si B13 está activado:

debe existir información que justifique la diferenciación.

Si B13 solo contiene:

- cambio de localidad;
- sinónimos;
- reordenación;
- texto genérico;

resultado:

REVIEW

---

# 31. FAQ

Las FAQ deben:

- estar relacionadas con la intención;
- responder preguntas reales;
- no inventar datos;
- no utilizarse únicamente para introducir keywords.

Si contienen datos no respaldados:

REVIEW

o:

ERROR

según el caso.

---

# 32. CTA

El CTA debe utilizar únicamente acciones autorizadas.

Permitido:

- contactar;
- solicitar información;
- solicitar presupuesto;
- pedir cita.

No permitido:

- teléfono inexistente;
- WhatsApp inexistente;
- disponibilidad inventada;
- precio inventado.

---

# 33. STATUS DE LA IA

El status proporcionado por la IA no es suficiente por sí mismo.

El validador debe calcular su propio resultado.

Ejemplo:

IA:

READY

Validador:

ERROR

Resultado final:

ERROR

El validador tiene autoridad sobre el estado técnico.

---

# 34. REGLAS DE READY

Solo puede producirse:

READY

si:

- JSON válido;
- schema_version correcta;
- opportunity_id correcto;
- identidad correcta;
- arquitectura correcta;
- URL correcta;
- canonical correcta;
- bloques válidos;
- bloques autorizados;
- SEO válido;
- enlaces válidos;
- no existen incidencias críticas;
- no existen datos comerciales inventados;
- no existen datos locales inventados;
- no existen testimonios inventados;
- no existen casos inventados;
- no existen precios inventados;
- no existen horarios inventados.

---

# 35. REGLAS DE REVIEW

Debe producirse:

REVIEW

cuando exista:

- información insuficiente;
- posible duplicación;
- diferenciación insuficiente;
- dato ambiguo;
- bloque condicional dudoso;
- evidencia insuficiente;
- necesidad de comprobación humana.

---

# 36. REGLAS DE ERROR

Debe producirse:

ERROR

cuando exista:

- JSON inválido;
- schema_version incompatible;
- opportunity_id incorrecto;
- identidad modificada;
- URL modificada;
- canonical modificada;
- bloque no autorizado;
- id/type incorrecto;
- dato comercial inventado;
- testimonio inventado;
- caso inventado;
- precio inventado;
- horario inventado;
- enlace no autorizado;
- estructura incompatible.

---

# 37. PUBLICACIÓN

El validador debe separar:

VALIDADA

de:

PUBLICABLE

Una página puede estar:

READY

y aun así no tener autorización para publicación.

La publicación requiere además:

- decisión SEO = CREAR;
- arquitectura aprobada;
- datos comerciales disponibles cuando sean necesarios;
- validación completa;
- autorización de publicación.

---

# 38. REGLA DE BLOQUEO

Si:

decision_seo != CREAR

entonces:

publication_allowed = false

Aunque la IA devuelva:

READY

Ejemplo:

decision_seo = INVESTIGAR

IA status = READY

Resultado:

publication_allowed = false

---

# 39. MODO TEST

El sistema puede ejecutar pruebas técnicas sin modificar la decisión real.

Una prueba debe utilizar:

test = true

y un:

opportunity_id

de prueba separado.

Ejemplo:

TEST-FONTANERO-MARBELLA

El modo TEST:

- no modifica OPP-001;
- no autoriza publicación;
- no modifica WordPress;
- no modifica la decisión SEO.

---

# 40. TRAZABILIDAD

Toda validación debe registrar:

- opportunity_id;
- schema_version;
- fecha;
- resultado;
- errores;
- advertencias;
- versión del validador;
- origen de la entrada.

---

# 41. RESULTADO DE VALIDACIÓN

Estructura prevista:

{
  "status": "READY",
  "publication_allowed": false,
  "errors": [],
  "warnings": [],
  "checks": {}
}

---

# 42. CHECKS

Ejemplo:

{
  "json_valid": true,
  "schema_version_valid": true,
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

# 43. ORDEN DE VALIDACIÓN

El validador ejecutará:

1. JSON
2. schema_version
3. opportunity_id
4. identidad
5. arquitectura
6. URL
7. canonical
8. bloques
9. id/type
10. SEO
11. datos
12. enlaces
13. no invención
14. duplicación
15. trazabilidad
16. publicación

Si falla una validación estructural crítica:

se puede detener el proceso.

---

# 44. RELACIÓN CON N8N

N8N recibirá:

INPUT IA

+

RESULTADO VALIDADOR

N8N decidirá el siguiente paso técnico según el resultado.

Ejemplo:

READY
↓
continuar

REVIEW
↓
detener / revisión

ERROR
↓
detener / registrar incidencia

---

# 45. RELACIÓN CON WORDPRESS

WordPress no debe recibir directamente la salida de IA.

Flujo obligatorio:

IA

↓

VALIDADOR

↓

N8N

↓

WORDPRESS

Si el validador devuelve:

ERROR

WordPress no recibe la página.

Si devuelve:

REVIEW

WordPress no publica automáticamente.

---

# 46. REGLA DE SEGURIDAD

Nunca confiar únicamente en:

- la IA;
- el prompt;
- N8N;
- WordPress.

La validación debe actuar como barrera independiente.

---

# 47. PRUEBA FONTANERO MARBELLA

Fixture:

TEST-FONTANERO-MARBELLA

Debe comprobar:

- identidad;
- arquitectura;
- bloques;
- SEO;
- ausencia de datos comerciales;
- ausencia de datos locales inventados;
- ausencia de testimonios;
- ausencia de precios;
- bloqueo de publicación.

Resultado esperado:

READY o REVIEW

pero:

publication_allowed = false

---

# 48. PRINCIPIO FINAL

La IA genera.

El validador comprueba.

N8N orquesta.

WordPress publica.

Ninguna capa debe asumir las responsabilidades de otra.

---

# 49. ESTADO DEL DOCUMENTO

Estado:

ACTIVO

Versión:

1.0

Fecha:

2026-08-23

Motivo:

Creación del sistema formal de validación de landings.

Siguiente evolución:

convertir estas reglas en validaciones ejecutables mediante código/N8N.
