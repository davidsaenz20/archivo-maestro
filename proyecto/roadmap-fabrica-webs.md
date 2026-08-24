ROADMAP UNIVERSAL — FÁBRICA DE WEBS AUTOMÁTICAS

Versión: 2.0
Tipo: Metodología reutilizable
Ámbito: Sistemas de generación automática de webs y contenidos estructurados
Estado: ACTIVO

---

1. PROPÓSITO

Este documento define el método general y reutilizable para diseñar, construir, validar, automatizar, publicar y escalar sistemas capaces de generar webs de forma estructurada y repetible.

No define el estado concreto de ningún proyecto.

No define qué paso está ejecutándose actualmente.

No sustituye al roadmap específico de cada proyecto.

Debe poder reutilizarse para diferentes proyectos y verticales.

Ejemplos:

- webs de servicios profesionales;
- webs de empresas locales;
- webs de ayudas y subvenciones;
- directorios especializados;
- webs informativas;
- otros sistemas de generación automática.

---

2. JERARQUÍA DEL SISTEMA

La metodología universal ocupa esta posición:

MAESTRO
↓
ROADMAP UNIVERSAL
↓
ROADMAP DEL PROYECTO
↓
DOCUMENTACIÓN TÉCNICA
↓
IMPLEMENTACIÓN

Cada capa tiene una función distinta.

"maestro.md"

Define el contexto persistente y las reglas maestras.

"proyecto/roadmap-fabrica-webs.md"

Define el método general reutilizable.

"proyecto/roadmap-proyecto.md"

Define el orden, estado y ejecución del proyecto concreto.

Documentación técnica

Define cómo debe construirse cada componente.

Implementación

Ejecuta las decisiones anteriores.

Ninguna capa inferior debe modificar unilateralmente las decisiones de una capa superior.

---

3. PRINCIPIO FUNDAMENTAL

El trabajo se divide en fases y pasos ordenados.

No se avanza al siguiente paso hasta completar el paso actual, salvo que exista un bloqueo real que obligue a modificar temporalmente el plan.

Una mejora, idea, optimización o duda no constituye por sí misma un bloqueo.

El método debe favorecer:

- ejecución secuencial;
- progreso acumulativo;
- verificación;
- trazabilidad;
- reutilización;
- mínima intervención manual.

---

4. FLUJO GENERAL

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

Este flujo representa el método general.

Cada proyecto concreto puede adaptar las fases y pasos necesarios, siempre que mantenga los principios fundamentales de control y validación.

---

5. FASE 0 — DEFINICIÓN DEL PROYECTO

Objetivo

Definir qué se quiere construir, para quién y con qué finalidad.

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

6. FASE 1 — INVESTIGACIÓN

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

La investigación debe basarse en fuentes y datos verificables cuando sea posible.

---

7. FASE 2 — MODELO DE DATOS

Objetivo

Definir qué información necesita manejar el sistema.

Pasos

2.1 Identificar entidades

2.2 Definir campos

2.3 Definir relaciones

2.4 Definir estados

2.5 Definir fuentes

2.6 Definir datos obligatorios y opcionales

2.7 Definir datos desconocidos

2.8 Crear esquema canónico

Criterio de finalización

Existe un modelo de datos único y suficientemente definido.

No deben existir modelos paralelos para representar la misma información.

---

8. FASE 3 — OPORTUNIDADES

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

9. FASE 4 — DECISIÓN

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

La decisión debe poder justificarse mediante datos, reglas y evidencia.

---

10. FASE 5 — ARQUITECTURA

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

La IA no debe decidir por sí misma elementos estructurales que correspondan a esta fase.

---

11. FASE 6 — GENERACIÓN DE DATOS Y CONTENIDO

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

La IA genera contenido dentro de los límites definidos por el sistema.

La IA no debe modificar unilateralmente:

- decisiones;
- arquitectura;
- reglas;
- identidad;
- datos fuente;
- criterios de publicación.

Criterio de finalización

Existe una salida estructurada que puede ser validada automáticamente.

---

12. FASE 7 — VALIDACIÓN

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

El sistema puede determinar automáticamente si una salida es publicable o necesita revisión.

---

13. FASE 8 — INFRAESTRUCTURA WEB / CMS

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

14. FASE 9 — AUTOMATIZACIÓN

Objetivo

Conectar las etapas para eliminar trabajo manual innecesario.

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

15. FASE 10 — PRIMERA IMPLEMENTACIÓN REAL

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

16. FASE 11 — QA

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

17. FASE 12 — PRODUCCIÓN

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

18. FASE 13 — ESCALADO

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

19. FASE 14 — MONITORIZACIÓN

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

20. FASE 15 — MEJORA

Objetivo

Mejorar el sistema basándose en datos reales.

Regla

Las mejoras no interrumpen automáticamente el trabajo actual.

Se registran y se priorizan.

Solo se convierten en trabajo cuando corresponda según el roadmap específico del proyecto.

---

21. REGLA DE BLOQUEOS

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

Un bloqueo debe afectar materialmente a la posibilidad de completar el paso actual.

---

22. REGLA DE NO DESVIACIÓN

NO SE RETROCEDE SIN BLOQUEO REAL.

Una idea nueva no cambia el paso actual.

Una mejora no cambia el paso actual.

Una optimización no cambia el paso actual.

Una duda no cambia el paso actual.

Una contradicción secundaria no cambia el paso actual.

Solo un bloqueo real puede obligar a modificar temporalmente el camino.

---

23. DESCOMPOSICIÓN DE PASOS

Un paso puede dividirse en subpasos cuando sea necesario.

Ejemplo:

FASE 8 — INFRAESTRUCTURA WEB

8.1 Modelo de datos
8.2 API
8.3 Plugin
8.4 Componentes
8.5 Plantilla
8.6 Renderizado

La descomposición no constituye un cambio de fase.

Mientras se trabaja en una fase, se continúa dentro de ella hasta completarla.

---

24. REUTILIZACIÓN

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

25. PROYECTOS FUTUROS

Este método puede utilizarse para:

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

Cada nuevo proyecto debe tener:

- su propio roadmap;
- su propio estado;
- su propia configuración;
- sus propios datos;

pero puede reutilizar el mismo método universal.

---

26. RELACIÓN CON EL ROADMAP DEL PROYECTO

Este documento define:

EL MÉTODO GENERAL

Cada proyecto concreto deberá tener:

"proyecto/roadmap-proyecto.md"

Ese documento determina:

- qué fases son necesarias;
- qué pasos concretos se ejecutarán;
- qué partes se reutilizan;
- qué partes son específicas;
- en qué paso se encuentra actualmente el proyecto.

Por tanto:

este documento NO debe contener el estado actual del proyecto concreto.

Ese estado pertenece al roadmap específico.

---

27. REGLA DE ESTADO

El método universal no almacena el estado operativo de un proyecto concreto.

El estado debe mantenerse en:

"proyecto/roadmap-proyecto.md"

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

28. CRITERIO DE COMPLETITUD METODOLÓGICA

El método universal se considera suficientemente definido cuando establece:

QUÉ HACER
↓
EN QUÉ ORDEN
↓
CÓMO VALIDAR
↓
CÓMO AUTOMATIZAR
↓
CÓMO PUBLICAR
↓
CÓMO ESCALAR
↓
CÓMO MEDIR
↓
CÓMO MEJORAR

La implementación concreta pertenece al proyecto correspondiente.

---

29. PRINCIPIO FINAL

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

El estado pertenece al proyecto, no a la metodología universal.

La documentación técnica explica cómo construir.

La ejecución implementa las decisiones.

---

FIN DEL ROADMAP UNIVERSAL
