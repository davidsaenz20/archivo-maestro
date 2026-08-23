MAESTRO DEL PROYECTO

1. FUNCIÓN

Este archivo es el documento maestro de control del proyecto.

Su función es mantener una visión general y actualizada de:

- Qué es el proyecto.
- Qué principios lo gobiernan.
- Cómo está organizado.
- Qué documentos existen.
- En qué fase estamos.
- Qué está completado.
- Qué está en validación.
- Qué está pendiente.
- Qué decisiones importantes se han tomado.
- Qué información prevalece cuando existen contradicciones.
- Cuál es el siguiente paso oficial.

El maestro NO sustituye a los documentos especializados.

Los documentos especializados contienen el detalle.

---

2. FUENTE DE VERDAD

El repositorio es la memoria persistente del proyecto.

La memoria de la conversación de ChatGPT no sustituye a la documentación.

Todo trabajo importante debe terminar documentado.

Esto incluye:

- Investigación.
- Evidencias.
- Matrices.
- Oportunidades.
- Reglas.
- Decisiones.
- URLs.
- Arquitectura de landings.
- Bloques.
- Modelo de datos.
- Prompts.
- Validaciones.
- Automatizaciones.
- Publicación.
- Resultados.
- Aprendizajes.

Si una información importante solo existe en una conversación, todavía no está correctamente documentada.

---

3. REGLA DE PRIORIDAD

Cuando exista una contradicción:

1. Comprobar la fecha.
2. Identificar la versión del documento.
3. Comprobar la evidencia.
4. Determinar qué información está mejor fundamentada.
5. Dar prioridad a la información posterior y mejor fundamentada.
6. Actualizar los documentos afectados.
7. Registrar el cambio.

El maestro NO tiene prioridad automática sobre un documento especializado simplemente por ser el maestro.

El maestro refleja el estado consolidado del proyecto.

---

4. ACTUALIZACIONES

Las actualizaciones importantes deben conservar historial.

Toda actualización relevante debe poder identificar:

- Fecha.
- Documento.
- Información anterior.
- Nueva información.
- Motivo.
- Evidencia.
- Consecuencia.

Una actualización posterior y suficientemente fundamentada puede sustituir una decisión anterior.

La información anterior no debe desaparecer cuando tenga valor histórico.

---

5. OBJETIVO DEL PROYECTO

Construir un sistema escalable para investigar y generar páginas SEO locales de servicios profesionales.

La unidad principal puede ser:

SERVICIO × LOCALIDAD

o, cuando exista una intención suficientemente específica:

SERVICIO × SUBSERVICIO × LOCALIDAD

El objetivo NO es generar miles de páginas automáticamente.

El objetivo es identificar únicamente combinaciones que puedan justificar una página útil, diferenciada y comercialmente válida.

---

6. ARQUITECTURA GENERAL

El flujo oficial es:

INVESTIGACIÓN

↓

EVIDENCIAS

↓

MATRICES

↓

MATRIZ DE OPORTUNIDADES

↓

MOTOR DE DECISIÓN

↓

DECISIÓN

↓

ARQUITECTURA DE URL

↓

ARQUITECTURA DE LANDING

↓

SISTEMA DE BLOQUES

↓

MODELO DE DATOS

↓

IA / CONTENIDO

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS / PUBLICACIÓN

↓

MEDICIÓN

↓

APRENDIZAJE

Este es el flujo oficial.

No debe saltarse una fase sin justificación.

---

7. ARQUITECTURA DOCUMENTAL

CONTROL

"maestro.md"

Control general.

---

METODOLOGÍA

"proyecto/metodologia.md"

Define cómo se trabaja.

---

SEO

"proyecto/seo/"

Arquitectura SEO

"proyecto/seo/arquitectura-seo.md"

Define los principios SEO.

Arquitectura de URLs

"proyecto/seo/arquitectura-urls.md"

Define las estructuras de URL permitidas.

Actualmente:

"/{servicio}/{localidad}/"

"/{servicio}/{subservicio}/{localidad}/"

Motor de decisión

"proyecto/seo/motor-decision.md"

Define las reglas de decisión:

- CREAR.
- AGRUPAR.
- INVESTIGAR.
- NO CREAR.

Investigación

"proyecto/seo/investigacion-fontaneria.md"

Conserva el análisis y conclusiones de la investigación sectorial.

Evidencias

"proyecto/seo/evidencias-fontaneria.md"

Conserva las fuentes y observaciones concretas.

Matriz de servicios

"proyecto/seo/matriz-servicios-fontaneria.md"

Define servicios y subservicios.

Matriz de localidades

"proyecto/seo/matriz-localidades.md"

Define la estructura territorial.

Matriz de oportunidades

"proyecto/seo/matriz-oportunidades-fontaneria.md"

Cruza servicios, subservicios, localidades y evidencias para crear oportunidades evaluables.

Registro de decisiones

"proyecto/seo/registro-decisiones.md"

Conserva las decisiones obtenidas al aplicar el motor.

---

8. DOCUMENTOS DE CONSTRUCCIÓN

Después de validar la parte de decisión se crearán:

"proyecto/seo/arquitectura-landing.md"

"proyecto/seo/sistema-bloques.md"

"proyecto/seo/modelo-datos.md"

"proyecto/seo/sistema-contenido-ia.md"

"proyecto/seo/validacion.md"

"proyecto/seo/automatizacion-n8n.md"

"proyecto/seo/publicacion-wordpress.md"

"proyecto/seo/medicion-aprendizaje.md"

Estos documentos NO sustituyen a los anteriores.

Representan las siguientes capas del sistema.

---

9. METODOLOGÍA

La metodología oficial está en:

"proyecto/metodologia.md"

El orden es:

1. Investigación.
2. Evidencias.
3. Matrices.
4. Oportunidades.
5. Motor.
6. Decisiones.
7. URLs.
8. Landing.
9. Bloques.
10. Modelo de datos.
11. IA.
12. Validación.
13. N8N.
14. Publicación.
15. Medición.
16. Aprendizaje.

---

10. MOTOR DE DECISIÓN

El motor actual es:

v1.0

Estado:

DEFINIDO — PENDIENTE DE VALIDACIÓN REAL

Variables principales:

- Intención.
- Demanda.
- Potencial comercial.
- Relevancia territorial.
- Competencia.
- Diferenciación.
- Información disponible.
- Riesgo de duplicación.

Resultados:

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

El motor v1.0 utiliza reglas y evidencia.

No deben inventarse puntuaciones numéricas.

Si falta evidencia:

DESCONOCIDO

o:

INVESTIGAR

El motor solo se considerará validado después de probarlo con casos reales.

---

11. ARQUITECTURA DE URL

La arquitectura está definida.

Estructura principal:

"/{servicio}/{localidad}/"

Estructura específica:

"/{servicio}/{subservicio}/{localidad}/"

Ejemplos:

"/fontanero/marbella/"

"/fontanero/desatascos/marbella/"

La existencia de una combinación no implica automáticamente crear una URL.

Primero:

MOTOR → DECISIÓN

Después:

DECISIÓN → URL

La IA no decide libremente la URL.

---

12. TRAZABILIDAD

Cada decisión importante debe poder reconstruirse:

EVIDENCIA

↓

DATO

↓

MATRIZ

↓

OPORTUNIDAD

↓

MOTOR

↓

DECISIÓN

↓

URL

↓

LANDING

Esto permite saber por qué se creó, agrupó, investigó o descartó una combinación.

---

13. INVESTIGACIÓN DE FONTANERÍA

La investigación de fontanería constituye el primer caso de estudio del sistema.

Contiene:

- Servicios.
- Subservicios.
- Localidades.
- Competencia.
- SERP.
- Patrones.
- Conclusiones.
- Hipótesis.

No debe tratarse como una verdad universal para otros sectores.

Cuando se investigue otro servicio se repetirá la metodología.

---

14. MATRICES

Las matrices actuales son:

- Servicios.
- Localidades.
- Oportunidades.

Las evidencias proporcionan el soporte documental.

Las matrices no sustituyen a las evidencias.

Las oportunidades no sustituyen al motor.

---

15. REGISTRO DE DECISIONES

"proyecto/seo/registro-decisiones.md"

contiene los resultados concretos del motor.

El motor contiene:

REGLAS

El registro contiene:

DECISIONES

Nunca deben mezclarse ambas funciones.

---

16. IA

La IA no decide estratégicamente por su cuenta.

La IA recibe:

- Datos.
- Reglas.
- URL.
- Bloques.
- Evidencias.
- Restricciones.

Y genera contenido dentro de esos límites.

No debe inventar:

- Empresas.
- Precios.
- Direcciones.
- Teléfonos.
- Certificaciones.
- Testimonios.
- Disponibilidad.
- Cobertura.
- Datos locales no verificados.

---

17. N8N

N8N será la capa de orquestación.

No debe sustituir al motor.

No debe decidir estratégicamente qué páginas existen.

Su función será ejecutar el proceso previamente definido.

---

18. REGLA PARA NUEVOS SERVICIOS

La metodología y arquitectura general son reutilizables.

Las conclusiones sectoriales NO.

Ejemplo:

ABOGADOS

↓

Investigación específica.

↓

Evidencias.

↓

Matriz de servicios jurídicos.

↓

Matriz territorial.

↓

Oportunidades.

↓

Motor adaptado.

↓

Validación.

↓

URLs.

↓

Landings.

↓

IA.

↓

Automatización.

Por tanto, el sistema será reutilizable sin copiar hipótesis de fontanería a otros sectores.

---

19. AUDITORÍA ANTES DE AVANZAR

Antes de cambiar de fase debe comprobarse:

- Coherencia entre documentos.
- Evidencias disponibles.
- Matrices actualizadas.
- Reglas identificadas.
- Decisiones documentadas.
- Ausencia de contradicciones importantes.
- Siguiente fase definida.

Si existe una pérdida documental importante:

SE DETIENE EL AVANCE Y SE DOCUMENTA PRIMERO.

---

20. ESTADO ACTUAL

COMPLETADO

- Arquitectura general del proyecto.
- Metodología.
- Arquitectura SEO.
- Arquitectura de URLs.
- Investigación inicial de fontanería.
- Matriz de servicios.
- Matriz de localidades.
- Sistema de evidencias.
- Matriz de oportunidades.
- Motor de decisión v1.0.
- Registro de decisiones.

EN VALIDACIÓN

- Evidencias de la investigación inicial.
- Oportunidades reales.
- Motor de decisión.
- Arquitectura de URLs.

SIGUIENTE BLOQUE

Construcción de:

- Arquitectura de landing.
- Sistema de bloques.
- Modelo de datos.
- Sistema de contenido/IA.
- Validación.

DESPUÉS

- N8N.
- WordPress.
- Publicación.
- Medición.
- Aprendizaje.
- Escalado.

---

21. SIGUIENTE PASO OFICIAL

El siguiente paso inmediato es:

VALIDAR OPORTUNIDADES REALES DE FONTANERÍA

Para cada oportunidad:

1. Identificar datos.
2. Identificar evidencias.
3. Aplicar motor.
4. Registrar decisión.
5. Determinar URL si procede.
6. Comprobar si existe suficiente información para construir una landing.

Cuando exista un conjunto suficiente de decisiones reales, se pasará a:

ARQUITECTURA DE LANDING

---

22. REGLA CONTRA LA DERIVA DEL PROYECTO

Antes de crear o modificar cualquier documento se debe responder:

- ¿Qué función cumple?
- ¿Qué información contiene?
- ¿De qué documentos depende?
- ¿Qué documentos dependen de él?
- ¿Existe ya esa información?
- ¿En qué fase estamos?
- ¿Es necesario modificarlo ahora?

No se crearán documentos simplemente porque parezcan útiles en ese momento.

---

23. REGLA CONTRA LA PÉRDIDA DE INFORMACIÓN

Si durante una conversación se realiza:

- investigación;
- análisis;
- descubrimiento;
- decisión;
- modificación de una regla;
- creación de una matriz;
- definición de una arquitectura;

esa información deberá incorporarse al repositorio antes de considerarse cerrada.

La memoria conversacional nunca se considera almacenamiento definitivo.

---

24. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se consolida la arquitectura documental del proyecto.

Se incorporan explícitamente:

EVIDENCIAS

y:

MATRIZ DE OPORTUNIDADES

al flujo oficial.

Se consolida la separación entre:

- investigación;
- evidencia;
- matrices;
- oportunidades;
- reglas;
- decisiones;
- URLs;
- construcción de landings.

Se establece el motor v1.0 como sistema basado en reglas y evidencia, sin puntuaciones numéricas arbitrarias.

Se incorpora el registro de decisiones como documento ya existente.

Se establece como siguiente fase la validación real del motor con oportunidades de fontanería.

A partir de esta actualización, la arquitectura documental queda considerada ESTABLE salvo que una prueba real demuestre la necesidad de modificarla.
