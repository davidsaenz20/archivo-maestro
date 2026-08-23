REGISTRO DE DECISIONES SEO

1. FUNCIÓN DEL DOCUMENTO

Este documento registra las decisiones concretas obtenidas al aplicar el motor de decisión a combinaciones reales de:

SERVICIO × LOCALIDAD

y, cuando corresponda:

SERVICIO × SUBSERVICIO × LOCALIDAD

Su función es conservar la trazabilidad de las decisiones.

Este documento NO contiene las reglas generales del motor.

Las reglas se encuentran en:

"proyecto/seo/motor-decision.md"

Este documento contiene los resultados de aplicar esas reglas.

---

2. PRINCIPIO DE TRAZABILIDAD

Cada decisión importante debe poder reconstruirse.

El flujo es:

EVIDENCIA

↓

DATOS

↓

MATRIZ

↓

MOTOR

↓

DECISIÓN

↓

URL

↓

LANDING

Una decisión no debe depender de la memoria de la conversación.

---

3. INFORMACIÓN MÍNIMA DE UNA DECISIÓN

Cada registro debe conservar, cuando exista:

- Fecha.
- Sector.
- Servicio.
- Subservicio.
- Localidad.
- Provincia.
- Datos de entrada.
- Puntuaciones.
- Decisión.
- Motivo.
- URL.
- Evidencia.
- Versión del motor.
- Observaciones.
- Resultado de validación.
- Cambios posteriores.

---

4. DECISIONES POSIBLES

El motor puede producir:

CREAR

La combinación justifica una página independiente.

AGRUPAR

La intención debe resolverse dentro de otra página existente.

INVESTIGAR

No existe información suficiente para decidir.

NO CREAR

La combinación no justifica una página independiente.

---

5. RELACIÓN CON LA URL

Cuando la decisión sea:

CREAR

se registrará la URL propuesta.

Ejemplo:

SERVICIO:
fontanero

SUBSERVICIO:
desatascos

LOCALIDAD:
Marbella

DECISIÓN:
CREAR

URL:
 /fontanero/desatascos/marbella/

La URL debe seguir las reglas de:

"proyecto/seo/arquitectura-urls.md"

La IA no decide la URL.

---

6. VERSIÓN DEL MOTOR

Cada decisión debe indicar qué versión del motor se utilizó.

Ejemplo:

"motor v1.0"

Si posteriormente cambia el motor, las decisiones antiguas no deben modificarse silenciosamente.

Debe registrarse la nueva decisión o revisión.

---

7. EVIDENCIA

Siempre que sea posible debe registrarse la evidencia que respalda la decisión.

Puede incluir:

- URL de fuente.
- Web analizada.
- SERP.
- Competidores.
- Observación.
- Dato de matriz.
- Investigación sectorial.
- Fecha de observación.

No es obligatorio duplicar toda la investigación aquí.

Debe existir una referencia suficiente para localizarla.

---

8. REGLA DE NO INVENTAR DATOS

Si un dato necesario para decidir no está disponible:

No debe inventarse.

La decisión puede ser:

INVESTIGAR

hasta disponer de información suficiente.

---

9. REGISTRO DE DECISIONES

DECISIÓN #001

Estado:

PENDIENTE DE VALIDACIÓN

Este registro se utilizará como primera prueba del sistema.

Identificación

Fecha:

"2026-08-23"

Sector:

"Fontanería"

Servicio:

"Pendiente"

Subservicio:

"Pendiente"

Localidad:

"Pendiente"

Provincia:

"Pendiente"

---

Datos de entrada

Demanda:

"Pendiente"

Intención:

"Pendiente"

Potencial comercial:

"Pendiente"

Relevancia territorial:

"Pendiente"

Competencia:

"Pendiente"

Diferenciación:

"Pendiente"

Información disponible:

"Pendiente"

Riesgo de duplicación:

"Pendiente"

---

Resultado del motor

Versión:

"Pendiente"

Puntuación:

"Pendiente"

Decisión:

"Pendiente"

Motivo:

"Pendiente"

---

Arquitectura URL

URL propuesta:

"Pendiente"

¿La URL sigue la arquitectura definida?:

"Pendiente"

---

Validación

¿Merece una landing independiente?:

"Pendiente"

¿Existe información suficiente para construirla?:

"Pendiente"

¿Existe riesgo de solapamiento?:

"Pendiente"

Resultado final:

"Pendiente"

---

Evidencias

Fuentes:

"Pendiente"

Observaciones:

"Pendiente"

---

10. FORMATO PARA FUTURAS DECISIONES

Cada nueva decisión seguirá esta estructura:

DECISIÓN #XXX

Fecha:
Sector:

Servicio:
Subservicio:
Localidad:
Provincia:

Datos de entrada:

Demanda:
Intención:
Potencial comercial:
Relevancia territorial:
Competencia:
Diferenciación:
Información disponible:
Riesgo de duplicación:

Versión del motor:

Puntuación:

Decisión:
CREAR / AGRUPAR / INVESTIGAR / NO CREAR

Motivo:

URL:

¿Landing independiente?:

Evidencias:

Observaciones:

Resultado de validación:

Cambios posteriores:

---

11. REVISIÓN DE DECISIONES

Una decisión puede revisarse posteriormente si:

- aparecen nuevos datos;
- cambia la demanda;
- cambia la competencia;
- cambia la arquitectura;
- cambia el motor;
- aparece nueva evidencia;
- se detecta un error.

La decisión anterior no debe desaparecer.

Debe conservarse el historial.

---

12. CAMBIO DE DECISIÓN

Ejemplo:

DECISIÓN ORIGINAL:
CREAR

DECISIÓN POSTERIOR:
AGRUPAR

FECHA DEL CAMBIO:
2026-XX-XX

MOTIVO:
Nueva evidencia demuestra que la intención se solapa con una página existente.

NUEVA URL:
No aplica.

DECISIÓN ANTERIOR:
Conservada para mantener trazabilidad.

---

13. RELACIÓN CON OTROS DOCUMENTOS

Este documento depende principalmente de:

"proyecto/seo/motor-decision.md"

"proyecto/seo/arquitectura-urls.md"

"proyecto/seo/matriz-servicios-fontaneria.md"

"proyecto/seo/matriz-localidades.md"

"proyecto/seo/investigacion-fontaneria.md"

Y posteriormente podrá relacionarse con:

- Arquitectura de landing.
- Sistema de bloques.
- Modelo de datos.
- IA.
- Validación.
- N8N.

---

14. REGLA FUNDAMENTAL

El motor define:

CÓMO DECIDIMOS

Este documento registra:

QUÉ DECIDIMOS

La arquitectura de URLs define:

CÓMO SE REPRESENTA LA DECISIÓN EN UNA URL

La arquitectura de landing definirá:

CÓMO SE CONSTRUYE LA PÁGINA

La IA definirá:

CÓMO SE GENERA EL CONTENIDO DENTRO DE LAS REGLAS

N8N definirá:

CÓMO SE AUTOMATIZA EL PROCESO

---

15. ESTADO DEL DOCUMENTO

Estado:

ACTIVO

El documento se encuentra preparado para comenzar la validación real del motor.

Todavía no contiene decisiones reales definitivas.

---

16. REGISTRO DE ACTUALIZACIONES

2026-08-23

Se crea el registro de decisiones.

Objetivo:

Separar las reglas generales del motor de los resultados concretos obtenidos al aplicar dichas reglas.

Se establece un sistema de trazabilidad entre:

EVIDENCIA → DATOS → MATRIZ → MOTOR → DECISIÓN → URL → LANDING

El primer registro queda preparado para la validación real del motor y la arquitectura de URLs.
