# MAESTRO DEL PROYECTO

## 1. FUNCIÓN

Este archivo es el documento maestro de control del proyecto.

Su función es mantener una visión general y actualizada de:

- objetivo;
- principios;
- arquitectura;
- documentos;
- fase actual;
- trabajo completado;
- trabajo en validación;
- trabajo pendiente;
- decisiones;
- contradicciones;
- siguiente paso.

El maestro no sustituye a los documentos especializados.

Los documentos especializados contienen el detalle.

---

# 2. FUENTE DE VERDAD

El repositorio es la memoria persistente del proyecto.

La conversación no sustituye al repositorio.

Todo trabajo importante debe terminar documentado.

Cuando exista contradicción:

1. comprobar fecha;
2. comprobar versión;
3. comprobar evidencia;
4. determinar qué información está mejor fundamentada;
5. actualizar los documentos afectados;
6. registrar el cambio.

El maestro refleja el estado consolidado.

No tiene prioridad automática sobre un documento especializado.

---

# 3. OBJETIVO

Construir un sistema escalable para detectar oportunidades SEO locales de servicios profesionales y, únicamente cuando exista justificación suficiente, generar landings útiles, diferenciadas y comercialmente válidas.

Unidad principal:

SERVICIO × LOCALIDAD

o:

SERVICIO × SUBSERVICIO × LOCALIDAD

El objetivo no es generar miles de páginas automáticamente.

El objetivo es generar únicamente páginas que puedan justificarse.

---

# 4. PRINCIPIO CENTRAL

El sistema debe diferenciar:

TECNOLOGÍA

de:

NEGOCIO

La automatización no justifica una página.

La IA no justifica una página.

Una keyword no justifica una página.

Una localidad no justifica una página.

Debe existir:

INTENCIÓN

+

EVIDENCIA

+

UTILIDAD

+

INFORMACIÓN SUFICIENTE

+

DIFERENCIACIÓN

+

RIESGO DE DUPLICACIÓN ACEPTABLE

---

# 5. FLUJO OFICIAL

INVESTIGACIÓN

↓

EVIDENCIAS

↓

MATRICES

↓

OPORTUNIDADES

↓

MOTOR DE DECISIÓN

↓

DECISIÓN

↓

ARQUITECTURA DE URL

↓

ARQUITECTURA DE LANDING

↓

DATOS

↓

BLOQUES

↓

IA

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS

↓

PUBLICACIÓN

↓

MEDICIÓN

↓

APRENDIZAJE

No se debe saltar una fase sin justificación.

---

# 6. ARQUITECTURA DOCUMENTAL

## CONTROL

`maestro.md`

Control general.

## METODOLOGÍA

`proyecto/metodologia.md`

Define cómo se trabaja.

## SEO

`proyecto/seo/`

Incluye:

- arquitectura SEO;
- arquitectura de URLs;
- investigación;
- evidencias;
- matrices;
- oportunidades;
- motor;
- decisiones;
- arquitectura de landing;
- sistema de bloques;
- esquema de datos;
- contrato IA.

---

# 7. DOCUMENTOS SEO PRINCIPALES

### Arquitectura SEO

`proyecto/seo/arquitectura-seo.md`

Define principios SEO.

### Arquitectura de URLs

`proyecto/seo/arquitectura-urls.md`

Define estructuras permitidas.

Actuales:

`/{servicio}/{localidad}/`

`/{servicio}/{subservicio}/{localidad}/`

### Investigación

`proyecto/seo/investigacion-fontaneria.md`

### Evidencias

`proyecto/seo/evidencias-fontaneria.md`

### Matriz de servicios

`proyecto/seo/matriz-servicios-fontaneria.md`

### Matriz de localidades

`proyecto/seo/matriz-localidades.md`

### Matriz de oportunidades

`proyecto/seo/matriz-oportunidades-fontaneria.md`

### Motor

`proyecto/seo/motor-decision.md`

### Registro

`proyecto/seo/registro-decisiones.md`

---

# 8. DOCUMENTOS DE CONSTRUCCIÓN ACTUALES

## Arquitectura de landing

`proyecto/seo/arquitectura-landing.md`

Estado:

DEFINIDA

## Sistema de bloques

`proyecto/seo/sistema-bloques.md`

Estado:

DEFINIDO

## Esquema de datos

`proyecto/seo/esquema-datos.md`

Estado:

DEFINIDO

Versión:

1.1

## Contrato IA → N8N

`proyecto/seo/contrato-salida-ia.md`

Estado:

DEFINIDO

Versión:

1.1

---

# 9. SISTEMA DE BLOQUES

Los identificadores oficiales son:

B01 HEADER

B02 NAVEGACIÓN

B03 HERO

B04 CONTENIDO PRINCIPAL

B05 CTA PRINCIPAL

B06 FOOTER

B07 SUBSERVICIO

B08 PROBLEMAS / NECESIDADES

B09 INFORMACIÓN LOCAL

B10 ZONAS / COBERTURA

B11 PROCESO

B12 ELEMENTOS DE CONFIANZA

B13 DIFERENCIACIÓN

B14 FAQ

B15 SERVICIOS RELACIONADOS

B16 LOCALIDADES RELACIONADAS

B17 DATOS ESTRUCTURADOS

B18 TESTIMONIOS

B19 CASOS / EJEMPLOS

B20 GALERÍA

B21 PRECIO / TARIFAS

B22 HORARIOS

B23 MAPA / UBICACIÓN

El mapa es vinculante.

La IA no puede inventar nuevos IDs.

---

# 10. ESQUEMA DE DATOS

El modelo canónico actual es:

OPORTUNIDAD

├── opportunity_id
├── identidad
├── localizacion
├── intencion
├── investigacion
├── decision_seo
├── agrupacion
├── arquitectura
├── datos_locales
├── cobertura
├── datos_comerciales
├── resenas
├── bloques
├── contenido
├── imagenes
├── enlazado
├── schema
├── estado_oportunidad
├── estado_landing
├── validacion
├── incidencias
└── trazabilidad

Este esquema es la estructura común entre investigación, decisión, IA, N8N y publicación.

---

# 11. MOTOR DE DECISIÓN

Versión:

v1.0

Estado:

DEFINIDO — EN VALIDACIÓN REAL

Resultados permitidos:

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

Variables:

- intención;
- demanda;
- potencial comercial;
- relevancia territorial;
- competencia;
- diferenciación;
- información disponible;
- riesgo de duplicación.

No utiliza puntuaciones arbitrarias.

Cuando falta evidencia:

DESCONOCIDO

o:

INVESTIGAR

---

# 12. PRIMERA OPORTUNIDAD REAL

ID:

OPP-001

Servicio:

fontanero

Subservicio:

ninguno

Municipio:

Marbella

Provincia:

Málaga

Fecha:

2026-08-23

---

# 13. ESTADO DE OPP-001

La primera decisión registrada es:

INVESTIGAR

Motivos:

- intención confirmada;
- potencial comercial probable;
- relevancia territorial confirmada;
- competencia alta;
- oferta local confirmada;
- demanda cuantitativa todavía desconocida;
- diferenciación insuficientemente documentada;
- riesgo de duplicación medio/alto;
- información local propia todavía parcial.

Por tanto:

NO ESTÁ APROBADA PARA PUBLICACIÓN.

---

# 14. URL PREVISTA

Si OPP-001 pasa a CREAR:

`/fontanero/marbella/`

Actualmente:

PENDIENTE DE APROBACIÓN

La URL no se activa antes de la decisión.

---

# 15. PRUEBA TÉCNICA DE LANDING

Existe una segunda línea de trabajo:

PROBAR EL SISTEMA DE GENERACIÓN

utilizando:

Fontanero Marbella

Esta prueba sirve para comprobar:

- estructura;
- bloques;
- datos;
- contrato IA;
- JSON;
- validación;
- posterior integración con N8N;
- posible generación WordPress.

IMPORTANTE:

Una prueba técnica de generación no equivale a aprobar OPP-001 para publicación.

---

# 16. REGLA DE LA PRUEBA

Si se genera contenido de prueba para Fontanero Marbella:

debe marcarse como:

TEST

y no:

PUBLICABLE

hasta que el motor real produzca:

CREAR

La prueba no puede utilizarse como evidencia para justificar la propia decisión.

---

# 17. IA

La IA trabaja después de:

1. investigación;
2. evidencias;
3. decisión;
4. arquitectura;
5. preparación de datos;
6. selección de bloques.

La IA genera contenido.

No decide:

- si existe la página;
- URL;
- canonical;
- localidad;
- servicio;
- arquitectura;
- bloques no autorizados.

---

# 18. CONTRATO IA

Archivo:

`proyecto/seo/contrato-salida-ia.md`

Versión:

1.1

La salida debe ser JSON válido.

La IA no puede devolver contenido fuera del JSON.

Debe respetar:

- identidad;
- arquitectura;
- URL;
- canonical;
- bloques;
- restricciones;
- datos disponibles.

No puede inventar información factual.

---

# 19. N8N

N8N será la capa de orquestación.

No decide estratégicamente.

Flujo previsto:

DATOS

↓

IA

↓

JSON

↓

VALIDACIÓN

↓

N8N

↓

WORDPRESS

N8N no debe decidir qué páginas existen.

---

# 20. WORDPRESS

Todavía no se considera cerrada la integración.

Pendiente:

- formato de entrada;
- endpoint;
- creación de páginas;
- asignación de plantilla;
- metadatos;
- imágenes;
- enlaces;
- publicación;
- actualización;
- control de errores.

---

# 21. VALIDACIÓN

Debe comprobar como mínimo:

- JSON válido;
- schema_version;
- opportunity_id;
- identidad;
- URL;
- canonical;
- bloques;
- tipos de bloques;
- ausencia de invenciones;
- enlaces autorizados;
- coherencia;
- restricciones;
- incidencias.

Resultado:

READY

REVIEW

ERROR

---

# 22. REGLA DE NO INVENCIÓN

Está prohibido inventar:

- empresas;
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
- URLs.

Si no existe información:

null

o:

REVIEW

según corresponda.

---

# 23. DIFERENCIACIÓN

Cambiar:

Marbella

por:

Estepona

no es suficiente.

Tampoco:

- cambiar título;
- cambiar sinónimos;
- cambiar orden;
- generar texto distinto mediante IA.

La diferenciación debe proceder de información real.

---

# 24. ESTADOS DEL SISTEMA

## Decisión SEO

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

## Estado de oportunidad

DETECTADA

INVESTIGADA

EVALUADA

DECIDIDA

CERRADA

## Estado de landing

NO_INICIADA

DATOS_PREPARADOS

ARQUITECTURA_PREPARADA

BLOQUES_SELECCIONADOS

CONTENIDO_GENERADO

VALIDACION_PENDIENTE

VALIDADA

PUBLICADA

RECHAZADA

REVISAR

---

# 25. QUÉ ESTÁ COMPLETADO

- arquitectura general;
- metodología;
- arquitectura SEO;
- arquitectura de URLs;
- investigación inicial de fontanería;
- evidencias iniciales;
- matriz de servicios;
- matriz de localidades;
- matriz de oportunidades;
- motor de decisión v1.0;
- registro de decisiones;
- arquitectura de landing;
- sistema de bloques;
- esquema de datos v1.1;
- contrato IA → N8N v1.1.

---

# 26. QUÉ ESTÁ EN VALIDACIÓN

- motor de decisión;
- oportunidades reales;
- diferenciación;
- arquitectura aplicada a casos reales;
- generación técnica de landing;
- contrato IA;
- validación del JSON.

---

# 27. QUÉ ESTÁ PENDIENTE

- completar pruebas IA;
- validar salida JSON;
- crear sistema de validación operativo;
- definir integración N8N;
- definir integración WordPress;
- probar publicación;
- medir resultados;
- aprender;
- escalar.

---

# 28. PRÓXIMO PASO OFICIAL

No crear más documentación estructural por ahora.

El siguiente trabajo es:

PRUEBA TÉCNICA DE GENERACIÓN

↓

OPP-001 / FONTANERO / MARBELLA

↓

PREPARAR INPUT

↓

SELECCIONAR BLOQUES

↓

GENERAR JSON

↓

VALIDAR JSON

↓

ANALIZAR RESULTADO

Después:

INTEGRACIÓN N8N

---

# 29. REGLA DE TRABAJO

Cuando un archivo necesite actualización:

1. identificarlo;
2. explicar brevemente por qué;
3. entregar contenido completo;
4. el usuario sustituye manualmente;
5. comprobar el archivo;
6. continuar.

No modificar archivos innecesariamente.

No crear documentos duplicados.

---

# 30. PRINCIPIO DE CONTROL

Antes de avanzar:

¿Está documentado?

¿Está justificado?

¿Está probado?

¿Es necesario?

Si no:

no avanzar.

---

# 31. REGISTRO DE ACTUALIZACIÓN

2026-08-23

Se actualiza el maestro para reflejar el estado real del proyecto.

Cambios:

- sustitución de referencias antiguas a `modelo-datos.md` por `esquema-datos.md`;
- incorporación de arquitectura de landing;
- incorporación del sistema de bloques B01-B23;
- incorporación del contrato IA → N8N;
- incorporación del modelo de datos canónico;
- incorporación del estado real de OPP-001;
- separación entre prueba técnica y publicación real;
- actualización de la fase actual;
- definición del siguiente paso como prueba técnica de generación.

Estado actual:

ARQUITECTURA DOCUMENTAL CONSOLIDADA

↓

VALIDACIÓN TÉCNICA

↓

PRUEBA FONTANERO MARBELLA

---

# 32. REGLA FINAL

El sistema debe demostrar primero que funciona correctamente con pocos casos.

Después:

automatizar.

Después:

escalar.

Nunca:

automatizar primero y descubrir después que el modelo era incorrecto.
