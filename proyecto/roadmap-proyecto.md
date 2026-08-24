ROADMAP DEL PROYECTO — FÁBRICA DE WEBS AUTOMÁTICAS

Versión: 2.0
Proyecto: Sistema de generación automática de webs
Estado: EN CONSTRUCCIÓN
Roadmap universal: "proyecto/roadmap-fabrica-webs.md"

---

1. PROPÓSITO

Este documento define el orden oficial de construcción y el estado operativo del proyecto actual.

El objetivo es construir una fábrica de webs capaz de generar páginas estructuradas, validadas y publicables de forma automática.

El sistema debe poder utilizarse inicialmente para servicios profesionales/locales y posteriormente reutilizarse para otros verticales.

Ejemplos:

- Fontaneros.
- Electricistas.
- Carpinteros.
- Pintores.
- Jardineros.
- Abogados.
- Reformas.
- Ayudas y subvenciones.
- Otros proyectos de generación automática.

---

2. OBJETIVO FINAL

Construir un sistema en el que:

DATOS / FUENTES
↓
INVESTIGACIÓN
↓
OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
↓
GENERACIÓN IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
LANDING REAL
↓
QA
↓
PUBLICACIÓN
↓
ESCALADO

pueda ejecutarse de forma repetible y con mínima intervención manual.

---

3. PRINCIPIO DE CONSTRUCCIÓN

Este roadmap es secuencial.

No se abandona un paso antes de completarlo.

Si aparece un problema:

¿BLOQUEA EL PASO?

NO
→ se registra y se continúa.

SÍ
→ se detiene temporalmente la ejecución, se resuelve el bloqueo y se vuelve al paso original.

Una mejora, idea u optimización que no bloquee el paso actual no modifica el orden del roadmap.

---

4. FUENTE DE VERDAD DEL ESTADO

La fuente única de verdad del estado operativo del proyecto es este documento:

"proyecto/roadmap-proyecto.md"

Aquí deben quedar registrados:

- fase actual;
- paso actual;
- objetivo;
- entregable;
- estado;
- bloqueos;
- decisiones relevantes;
- siguiente paso.

El protocolo de ejecución establece cómo trabajar, pero no determina el paso actual.

El roadmap universal establece el método general reutilizable, pero no sustituye al roadmap específico.

La documentación técnica define cómo construir cada componente, pero no puede modificar por sí misma el orden de ejecución.

---

5. ESTADO ACTUAL

FASE ACTUAL: Fase 2 — Modelo de negocio y oportunidades.

PASO ACTUAL: 2.1 — Investigación de mercado.

OBJETIVO: analizar y consolidar la demanda, competencia, intención, monetización y viabilidad de las oportunidades iniciales.

ESTADO: EN EJECUCIÓN.

BLOQUEOS: Ninguno conocido.

ÚLTIMO HITO COMPLETADO: Fase 1 — Consolidación del sistema.

SIGUIENTE PASO: 2.2 — Modelo de oportunidades.

---

6. ROADMAP OFICIAL

FASE 1 — CONSOLIDACIÓN DEL SISTEMA

1.1 Auditoría del repositorio

Revisar la documentación existente para:

- conocer qué está definido;
- detectar duplicidades;
- detectar contradicciones;
- identificar piezas incompletas;
- distinguir arquitectura de implementación;
- determinar la función de cada documento.

Estado: COMPLETADO.

---

1.2 Consolidar documentación

Determinar qué documentos:

- permanecen;
- se actualizan;
- se fusionan;
- actúan como referencia;
- quedan como documentación histórica.

Estado: COMPLETADO.

---

1.3 Definir autoridad documental

Establecer la autoridad de cada capa:

- "maestro.md" → contexto persistente y reglas maestras;
- "proyecto/roadmap-fabrica-webs.md" → metodología universal;
- "proyecto/roadmap-proyecto.md" → estado y orden del proyecto;
- documentación técnica → especificaciones de construcción;
- implementación → ejecución de las especificaciones.

Estado: COMPLETADO.

---

1.4 Establecer sistema de estado

El estado operativo debe contener como mínimo:

- fase;
- paso;
- objetivo;
- entregable;
- estado;
- bloqueos;
- decisiones relevantes;
- siguiente paso.

Estado: COMPLETADO.

---

FASE 2 — MODELO DE NEGOCIO Y OPORTUNIDADES

2.1 Investigación de mercado

Analizar:

- demanda;
- competencia;
- intención;
- monetización;
- viabilidad;
- dificultad;
- potencial de escalado.

Estado: EN EJECUCIÓN.

Entregable: modelo consolidado de investigación de oportunidades.

---

2.2 Modelo de oportunidades

Definir cómo se representan las oportunidades.

Cada oportunidad deberá poder contener, como mínimo:

- vertical;
- servicio;
- localidad;
- demanda;
- competencia;
- intención;
- potencial económico;
- dificultad;
- evidencia;
- estado;
- decisión.

Estados posibles:

CREAR
REVISAR
NO_CREAR

Estado: PARCIALMENTE COMPLETADO.

---

2.3 Motor de decisión

Definir las reglas que determinan cuándo una oportunidad debe:

CREAR

REVISAR

NO_CREAR

Las decisiones deberán basarse en criterios objetivos y datos disponibles.

Estado: PARCIALMENTE COMPLETADO.

---

2.4 Matrices de decisión

Completar las matrices necesarias para evaluar oportunidades de forma repetible.

Estado: PARCIALMENTE COMPLETADO.

---

FASE 3 — ARQUITECTURA SEO Y DE INFORMACIÓN

3.1 Arquitectura de URLs

Definir:

- patrones;
- jerarquía;
- canonical;
- páginas objetivo;
- reglas de indexación;
- relación servicio/localidad;
- estructura escalable.

Estado: COMPLETADO / DOCUMENTADO.

---

3.2 Arquitectura de landing

Definir:

- estructura;
- bloques;
- orden;
- reglas;
- contenido;
- enlazado;
- elementos obligatorios;
- elementos opcionales.

Estado: DOCUMENTADO.

---

3.3 Sistema de bloques

Definir y documentar los bloques:

B01–B23

Cada bloque debe tener:

- función;
- datos de entrada;
- reglas;
- condiciones;
- salida;
- comportamiento cuando falten datos.

Estado: DOCUMENTADO.

---

3.4 Interlinking

Definir reglas de enlazado interno:

- páginas relacionadas;
- jerarquía;
- contexto;
- anchors;
- límites;
- reglas de automatización.

Estado: DOCUMENTADO / PENDIENTE DE IMPLEMENTACIÓN.

---

FASE 4 — MODELO DE DATOS

4.1 Modelo de datos canónico

Definir las entidades y relaciones principales del sistema.

Estado: DOCUMENTADO.

---

4.2 Modelo de datos WordPress

Definir cómo se almacenarán los datos en WordPress.

Debe existir correspondencia clara entre:

DATOS CANÓNICOS
↓
DATOS WORDPRESS
↓
RENDERIZADO

Estado: DOCUMENTADO / PENDIENTE DE IMPLEMENTACIÓN.

---

4.3 Contrato de salida IA

Definir la salida estructurada de la IA.

Estado: DOCUMENTADO — CONTRATO IA 1.1.

---

4.4 Compatibilidad entre contratos

Comprobar:

MODELO CANÓNICO
↕
CONTRATO IA
↕
MODELO WORDPRESS

Debe garantizarse que los datos generados puedan almacenarse y renderizarse sin pérdida de información relevante.

Estado: PENDIENTE DE VERIFICACIÓN FINAL.

---

FASE 5 — GENERADOR DE CONTENIDO

5.1 Preparación de contexto

Definir cómo se suministra a la IA:

- identidad;
- intención;
- evidencia;
- datos;
- arquitectura;
- reglas;
- restricciones;
- contexto de localidad;
- contexto del servicio.

Estado: DOCUMENTADO.

---

5.2 Generación estructurada

Construir el generador que produzca la salida conforme al contrato IA.

Estado: PENDIENTE DE IMPLEMENTACIÓN REAL.

---

5.3 Selección de bloques

Implementar la selección de:

B01–B23

La selección debe depender de los datos disponibles, intención y reglas definidas.

Estado: PENDIENTE DE IMPLEMENTACIÓN REAL.

---

FASE 6 — VALIDADOR

6.1 Validador estructural

Comprobar:

- esquema;
- campos obligatorios;
- tipos;
- formato;
- valores permitidos;
- integridad de la salida.

Estado: DOCUMENTADO.

---

6.2 Validador semántico

Comprobar:

- intención;
- identidad;
- evidencia;
- coherencia;
- ausencia de invenciones;
- utilidad;
- adecuación al usuario;
- consistencia con los datos de entrada.

Estado: DOCUMENTADO / PENDIENTE DE IMPLEMENTACIÓN FINAL.

---

6.3 Validador de landing

Comprobar la landing completa:

- estructura;
- contenido;
- datos;
- enlaces;
- SEO;
- consistencia;
- renderizado.

Estado: DOCUMENTADO.

---

6.4 Estados de validación

Implementar:

VALID
REVIEW
INVALID

Estado: PENDIENTE DE IMPLEMENTACIÓN REAL.

---

FASE 7 — WORDPRESS

7.1 Arquitectura WordPress

Definir:

- plugin;
- plantilla;
- componentes;
- almacenamiento;
- renderizado;
- endpoints necesarios.

Estado: DOCUMENTADO.

---

7.2 Modelo WordPress

Implementar el almacenamiento de datos.

Estado: PENDIENTE.

---

7.3 Componentes B01–B23

Construir los componentes reales.

Orden inicial:

B01
B02
B03
…
B23

Cada componente debe:

- recibir los datos correspondientes;
- validar las entradas necesarias;
- renderizar correctamente;
- mantener consistencia visual;
- funcionar de forma reutilizable;
- poder ser utilizado automáticamente.

Estado: PENDIENTE.

---

7.4 Plantilla de landing

Construir una plantilla reutilizable.

Estado: PENDIENTE.

---

7.5 Renderizado completo

Conectar:

DATOS
↓
BLOQUES
↓
PLANTILLA
↓
LANDING

Estado: PENDIENTE.

---

FASE 8 — INTEGRACIÓN N8N → WORDPRESS

8.1 API

Definir y probar comunicación segura.

Estado: DOCUMENTADO.

---

8.2 Flujo N8N V1

Construir:

INPUT
↓
PREPARACIÓN
↓
IA
↓
VALIDADOR
↓
WORDPRESS

Estado: PENDIENTE.

---

8.3 Manejo de errores

Implementar:

- retry;
- logs;
- estados;
- revisión manual;
- bloqueo de publicación;
- recuperación ante errores.

Estado: PENDIENTE.

---

FASE 9 — PRIMERA LANDING REAL

9.1 Fixture de referencia

Utilizar:

Fontanero Marbella

como primera unidad controlada.

Estado: DISPONIBLE.

---

9.2 Generación real

Ejecutar el flujo completo utilizando el fixture.

Estado: PENDIENTE.

---

9.3 Publicación real

Crear la primera landing mediante el sistema.

Estado: PENDIENTE.

---

FASE 10 — QA

Comprobar:

- contenido;
- diseño;
- responsive;
- enlaces;
- SEO;
- canonical;
- datos estructurados;
- rendimiento;
- errores;
- validación;
- automatización;
- consistencia de datos;
- estabilidad del flujo.

Estado: PENDIENTE.

---

FASE 11 — ESCALADO CONTROLADO

No comenzar con miles de páginas.

Escalar progresivamente:

1
↓
10
↓
100
↓
1.000

En cada nivel comprobar:

- calidad;
- errores;
- costes;
- tiempo;
- duplicación;
- indexación;
- estabilidad;
- capacidad de recuperación;
- consumo de recursos.

No avanzar al siguiente nivel si aparecen errores estructurales no resueltos.

Estado: PENDIENTE.

---

FASE 12 — PRODUCCIÓN

Preparar:

- seguridad;
- backups;
- monitorización;
- logs;
- recuperación;
- control de publicaciones;
- alertas;
- gestión de errores;
- mantenimiento.

Estado: PENDIENTE.

---

FASE 13 — REUTILIZACIÓN

Una vez validada la fábrica:

crear nuevos verticales.

Ejemplos:

- FONTANERO;
- ELECTRICISTA;
- CARPINTERO;
- PINTOR;
- JARDINERO;
- ABOGADO;
- REFORMAS.

Cada vertical reutiliza:

- infraestructura;
- componentes;
- contratos;
- validadores;
- automatizaciones;
- metodología.

Solo cambia la configuración y los datos específicos.

Estado: FUTURO.

---

FASE 14 — NUEVOS TIPOS DE WEBS AUTOMÁTICAS

Aplicar la misma fábrica a proyectos diferentes.

Ejemplo:

Ayudas y subvenciones

El sistema reutilizará el método, pero tendrá:

- entidades diferentes;
- fuentes diferentes;
- modelo de datos específico;
- reglas de decisión específicas;
- arquitectura específica.

Estado: FUTURO.

---

7. CRITERIO DE FINALIZACIÓN DEL PROYECTO

La fábrica se considera operativa cuando puede realizar:

DATOS
↓
OPORTUNIDAD
↓
DECISIÓN
↓
ARQUITECTURA
↓
IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
LANDING
↓
QA
↓
PUBLICACIÓN

de forma repetible y sin depender de intervención manual para cada unidad.

---

8. REGLA DE AVANCE

Para avanzar de un paso:

1. el paso actual debe estar completado;
2. el entregable debe existir;
3. el resultado debe haberse verificado;
4. los bloqueos deben estar resueltos;
5. el estado debe quedar registrado.

Solo entonces se activa el siguiente paso.

---

9. REGLA DE NO DESVIACIÓN

NO SE RETROCEDE SIN BLOQUEO REAL.

Durante una fase:

- las mejoras se registran;
- las ideas nuevas se registran;
- las optimizaciones se registran;
- los problemas no bloqueantes se registran.

Pero se continúa trabajando en el paso actual.

---

10. REGLA PARA SESIONES FUTURAS

Cuando el usuario diga:

«Sigue»

el asistente debe:

1. recuperar "maestro.md";
2. recuperar "proyecto/roadmap-fabrica-webs.md";
3. recuperar este "proyecto/roadmap-proyecto.md";
4. recuperar "proyecto/protocolo-ejecucion.md";
5. recuperar "proyecto/checklist-arranque.md";
6. determinar el paso actual;
7. revisar únicamente la documentación técnica necesaria;
8. comprobar dependencias;
9. continuar exactamente desde el paso actual;
10. no cambiar de fase sin completar el paso;
11. actualizar el estado al completar el trabajo.

---

11. PRINCIPIO FINAL

ROADMAP UNIVERSAL
↓
ROADMAP DEL PROYECTO
↓
PASO ACTUAL
↓
DOCUMENTACIÓN NECESARIA
↓
CONSTRUCCIÓN
↓
VERIFICACIÓN
↓
REGISTRO DEL ESTADO
↓
SIGUIENTE PASO

El roadmap universal determina el método general.

El roadmap del proyecto determina el orden y estado del proyecto.

El protocolo de ejecución determina cómo trabajar.

La documentación técnica determina cómo construir cada pieza.

La ejecución implementa lo definido.

La memoria de conversación no sustituye al estado persistente del proyecto.

---

FIN DEL ROADMAP DEL PROYECTO
