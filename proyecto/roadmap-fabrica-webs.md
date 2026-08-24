ROADMAP UNIVERSAL — FÁBRICA DE WEBS AUTOMÁTICAS

Versión: 1.0
Tipo: Metodología reutilizable
Ámbito: Sistemas de generación automática de webs y contenidos estructurados
Estado: En construcción

---

1. PROPÓSITO

Este documento define el proceso general para diseñar, construir, validar, automatizar y escalar sistemas capaces de generar webs de forma estructurada y repetible.

Debe poder reutilizarse para diferentes proyectos y verticales.

Ejemplos:

- webs de servicios profesionales;
- webs de empresas locales;
- webs de ayudas y subvenciones;
- directorios especializados;
- webs informativas;
- otros sistemas de generación automática.

El método no depende de un sector concreto.

---

2. PRINCIPIO FUNDAMENTAL

El proyecto se divide en fases y pasos ordenados.

No se avanza al siguiente paso hasta completar el paso actual, salvo que exista un bloqueo real que obligue a modificar el plan.

Una mejora o una idea nueva no constituye un bloqueo.

---

3. FLUJO GENERAL

DEFINICIÓN
↓
INVESTIGACIÓN
↓
MODELO DE DATOS
↓
OPORTUNIDADES
↓
DECISIÓN
↓
ARQUITECTURA
↓
CONTENIDO
↓
VALIDACIÓN
↓
WORDPRESS / CMS
↓
AUTOMATIZACIÓN
↓
PRIMERA WEB REAL
↓
QA
↓
PRODUCCIÓN
↓
ESCALADO
↓
MONITORIZACIÓN
↓
MEJORA

---

FASE 0 — DEFINICIÓN DEL PROYECTO

Objetivo

Definir qué se quiere construir y para qué.

Pasos

0.1 Definir problema

Identificar el problema real que resolverá el sistema.

0.2 Definir usuario

Identificar quién utilizará o consumirá el sistema.

0.3 Definir modelo de negocio

Determinar cómo puede generar valor o ingresos.

0.4 Definir alcance

Determinar qué entra y qué queda fuera.

0.5 Definir criterios de éxito

Establecer cómo sabremos que el proyecto funciona.

Criterio de finalización

El proyecto tiene:

- problema definido;
- usuario definido;
- objetivo definido;
- alcance definido;
- criterios de éxito definidos.

---

FASE 1 — INVESTIGACIÓN

Objetivo

Obtener información suficiente para decidir si el proyecto es viable y cómo debe construirse.

Pasos

1.1 Identificar fuentes

1.2 Recopilar datos

1.3 Analizar demanda

1.4 Analizar competencia

1.5 Identificar restricciones

1.6 Identificar oportunidades

1.7 Evaluar calidad y fiabilidad de las fuentes

Criterio de finalización

Existe suficiente evidencia para continuar con el diseño.

---

FASE 2 — MODELO DE DATOS

Objetivo

Definir qué información necesita manejar el sistema.

Pasos

2.1 Identificar entidades

2.2 Definir campos

2.3 Definir relaciones

2.4 Definir estados

2.5 Definir fuentes

2.6 Definir datos obligatorios y opcionales

2.7 Definir valores desconocidos

2.8 Crear esquema canónico

Criterio de finalización

Existe un modelo de datos único y suficientemente definido.

No deben existir modelos paralelos para representar la misma información.

---

FASE 3 — OPORTUNIDADES

Objetivo

Convertir datos e investigación en oportunidades concretas que puedan ser evaluadas.

Pasos

3.1 Definir oportunidad

3.2 Definir identificador

3.3 Asociar entidades

3.4 Asociar intención

3.5 Asociar evidencia

3.6 Asociar datos disponibles

3.7 Asociar restricciones

Criterio de finalización

Las oportunidades pueden representarse mediante el modelo de datos definido.

---

FASE 4 — DECISIÓN

Objetivo

Determinar qué oportunidades deben convertirse en páginas o recursos.

Decisiones posibles

CREAR
REVISAR
NO_CREAR

Pasos

4.1 Evaluar intención

4.2 Evaluar demanda

4.3 Evaluar evidencia

4.4 Evaluar diferenciación

4.5 Evaluar utilidad

4.6 Evaluar riesgo

4.7 Emitir decisión

Criterio de finalización

Cada oportunidad relevante tiene una decisión trazable.

---

FASE 5 — ARQUITECTURA

Objetivo

Determinar cómo se organizará la información antes de generar contenido.

Pasos

5.1 Definir tipos de página

5.2 Definir URLs

5.3 Definir jerarquía

5.4 Definir canonical

5.5 Definir navegación

5.6 Definir enlazado interno

5.7 Definir bloques

5.8 Definir reglas de selección

Criterio de finalización

La arquitectura está definida y puede reutilizarse a escala.

---

FASE 6 — GENERACIÓN DE DATOS Y CONTENIDO

Objetivo

Generar contenido utilizando exclusivamente la información y arquitectura autorizadas.

Pasos

6.1 Preparar contexto

6.2 Preparar datos

6.3 Seleccionar bloques

6.4 Construir contrato de entrada

6.5 Generar contenido

6.6 Generar metadatos

6.7 Generar elementos auxiliares

6.8 Generar salida estructurada

Regla

La IA genera contenido.

La IA no modifica decisiones arquitectónicas que pertenecen al sistema.

Criterio de finalización

Existe una salida estructurada que puede ser validada automáticamente.

---

FASE 7 — VALIDACIÓN

Objetivo

Impedir que contenido incorrecto, incompleto o no autorizado llegue a producción.

Validaciones

- esquema;
- campos obligatorios;
- identidad;
- intención;
- arquitectura;
- URL;
- canonical;
- contenido;
- duplicación;
- evidencias;
- invenciones;
- enlaces;
- bloques;
- SEO;
- consistencia.

Estados

VALID
REVIEW
INVALID

Criterio de finalización

El sistema puede determinar automáticamente si una salida es publicable.

---

FASE 8 — INFRAESTRUCTURA WEB / CMS

Objetivo

Construir la infraestructura capaz de almacenar y representar los datos generados.

Pasos

8.1 Elegir CMS / infraestructura

8.2 Definir modelo de almacenamiento

8.3 Definir API

8.4 Definir plantilla

8.5 Definir componentes

8.6 Implementar renderizado

8.7 Implementar SEO técnico

8.8 Implementar navegación

Criterio de finalización

Una salida validada puede convertirse en una página real.

---

FASE 9 — AUTOMATIZACIÓN

Objetivo

Conectar todas las etapas para eliminar trabajo manual innecesario.

Flujo

FUENTE
↓
INVESTIGACIÓN
↓
OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
↓
DATOS
↓
IA
↓
VALIDADOR
↓
CMS
↓
PUBLICACIÓN

Pasos

9.1 Automatizar adquisición

9.2 Automatizar procesamiento

9.3 Automatizar generación

9.4 Automatizar validación

9.5 Automatizar publicación

9.6 Registrar errores

9.7 Registrar resultados

Criterio de finalización

El flujo puede ejecutarse de principio a fin con intervención humana mínima.

---

FASE 10 — PRIMERA IMPLEMENTACIÓN REAL

Objetivo

Demostrar el sistema completo con una unidad real.

No se debe comenzar con generación masiva.

Primero:

1 oportunidad
↓
1 página
↓
1 validación
↓
1 publicación

Criterio de finalización

Existe al menos una página real generada mediante el sistema completo.

---

FASE 11 — QA

Objetivo

Comprobar que la implementación real funciona correctamente.

Comprobar

- contenido;
- diseño;
- responsive;
- enlaces;
- SEO;
- canonical;
- datos estructurados;
- rendimiento;
- errores;
- automatización;
- consistencia.

Criterio de finalización

La primera implementación cumple los criterios definidos.

---

FASE 12 — PRODUCCIÓN

Objetivo

Preparar el sistema para funcionar de forma estable.

Pasos

12.1 Seguridad

12.2 Backup

12.3 Monitorización

12.4 Logs

12.5 Gestión de errores

12.6 Recuperación

12.7 Control de publicaciones

Criterio de finalización

El sistema puede funcionar de forma controlada en producción.

---

FASE 13 — ESCALADO

Objetivo

Aumentar el número de páginas sin degradar la calidad.

Principio

1
↓
10
↓
100
↓
1.000
↓
ESCALA MAYOR

Cada salto debe comprobar:

- calidad;
- costes;
- tiempo;
- errores;
- duplicación;
- indexabilidad;
- estabilidad.

Regla

No escalar un sistema que todavía no funciona correctamente con una unidad.

---

FASE 14 — MONITORIZACIÓN

Objetivo

Conocer qué ocurre después de publicar.

Medir

- páginas creadas;
- páginas publicadas;
- errores;
- tráfico;
- indexación;
- conversiones;
- costes;
- rendimiento;
- problemas de calidad.

Criterio de finalización

Existe un sistema que permite observar el comportamiento del proyecto.

---

FASE 15 — MEJORA

Objetivo

Mejorar el sistema basándose en datos reales.

Regla

Las mejoras no interrumpen automáticamente el trabajo actual.

Se registran y se priorizan.

Solo se convierten en trabajo cuando corresponde según el roadmap.

---

16. REGLA DE BLOQUEOS

Durante cualquier fase:

PROBLEMA
↓
¿BLOQUEA EL PASO ACTUAL?

NO

REGISTRAR
↓
CONTINUAR

SÍ

DETENER
↓
ANALIZAR
↓
RESOLVER
↓
VERIFICAR
↓
VOLVER AL PASO ORIGINAL

---

17. REGLA DE NO DESVIACIÓN

NO SE RETROCEDE SIN BLOQUEO REAL.

Una idea nueva no cambia el paso actual.

Una mejora no cambia el paso actual.

Una optimización no cambia el paso actual.

Una duda no cambia el paso actual.

Una contradicción secundaria no cambia el paso actual.

Solo un bloqueo real puede obligar a modificar temporalmente el camino.

---

18. DESCOMPOSICIÓN DE PASOS

Un paso puede dividirse en subpasos cuando sea necesario.

Ejemplo:

FASE 8
Infraestructura WordPress

8.1 Modelo de datos
8.2 API
8.3 Plugin
8.4 Componentes
8.5 Plantilla
8.6 Renderizado

La descomposición no constituye un cambio de fase.

Mientras se trabaja en la fase 8, se continúa dentro de ella hasta completarla.

---

19. REUTILIZACIÓN

El método debe distinguir entre:

Núcleo reutilizable

- metodología;
- protocolo;
- validación;
- arquitectura técnica;
- automatización;
- componentes;
- infraestructura;
- observabilidad.

Configuración específica

- sector;
- servicio;
- localidad;
- fuentes;
- entidades;
- contenido;
- reglas específicas;
- datos.

El objetivo es que crear un nuevo proyecto requiera principalmente configurar el sistema existente, no reconstruirlo desde cero.

---

20. PROYECTOS FUTUROS

Este roadmap puede utilizarse para:

- fontaneros;
- electricistas;
- carpinteros;
- pintores;
- jardineros;
- abogados;
- reformas;
- ayudas;
- subvenciones;
- directorios;
- otros proyectos de generación automática.

Cada nuevo proyecto debe tener su propio estado y configuración, pero puede utilizar el mismo método.

---

21. RELACIÓN CON LOS ROADMAPS DE PROYECTO

Este documento define:

«EL MÉTODO GENERAL»

Cada proyecto concreto deberá tener posteriormente:

ROADMAP DEL PROYECTO

Ese roadmap determinará:

- qué fases son necesarias;
- qué pasos concretos se ejecutarán;
- qué partes se reutilizan;
- qué partes son específicas;
- en qué paso se encuentra actualmente el proyecto.

---

22. REGLA DE ESTADO

En todo momento debe existir una única referencia persistente al estado actual del proyecto.

Como mínimo:

FASE ACTUAL:
PASO ACTUAL:
OBJETIVO:
ENTREGABLE:
ESTADO:
BLOQUEOS:
SIGUIENTE PASO:

No se debe determinar el paso actual únicamente mediante memoria de conversación.

---

23. FIN DEL MÉTODO

El proyecto se considera metodológicamente completo cuando:

MÉTODO
↓
ROADMAP
↓
IMPLEMENTACIÓN
↓
VALIDACIÓN
↓
PRODUCCIÓN
↓
ESCALA
↓
MONITORIZACIÓN

están definidos y controlados.

---

PRINCIPIO FINAL

SABER QUÉ CONSTRUIR
↓
SABER EN QUÉ ORDEN
↓
SABER QUÉ ESTAMOS HACIENDO AHORA
↓
NO ABANDONARLO SIN BLOQUEO
↓
TERMINAR
↓
VERIFICAR
↓
AVANZAR

El método es reutilizable.

El roadmap concreto cambia por proyecto.

El paso actual nunca se decide por memoria.

---

FIN DEL ROADMAP UNIVERSAL
