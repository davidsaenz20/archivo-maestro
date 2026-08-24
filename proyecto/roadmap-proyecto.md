ROADMAP DEL PROYECTO — FÁBRICA DE WEBS AUTOMÁTICAS

Versión: 1.0
Proyecto: Sistema de generación automática de webs
Estado: En construcción
Roadmap universal: "proyecto/roadmap-fabrica-webs.md"

---

1. PROPÓSITO

Este documento define el orden oficial de construcción del proyecto actual.

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

Se registra y se continúa.

SÍ

Se detiene temporalmente la ejecución, se resuelve y se vuelve al paso original.

---

4. ESTADO ACTUAL

FASE: Diseño y construcción de la fábrica.

PASO ACTUAL: Auditoría y consolidación del roadmap.

OBJETIVO DEL PASO: establecer una secuencia única y coherente de construcción utilizando toda la documentación existente.

ESTADO: EN EJECUCIÓN.

BLOQUEOS: Ninguno conocido.

---

5. ROADMAP OFICIAL

FASE 1 — CONSOLIDACIÓN DEL SISTEMA

1.1 Auditoría del repositorio

Revisar toda la documentación existente.

Objetivo:

- conocer qué está definido;
- detectar duplicidades;
- detectar contradicciones;
- identificar piezas incompletas;
- distinguir arquitectura de implementación.

Estado: EN EJECUCIÓN.

---

1.2 Consolidar documentación

Determinar qué documentos:

- permanecen;
- se actualizan;
- se fusionan;
- se convierten en referencia;
- quedan como documentación histórica.

Estado: PENDIENTE.

---

1.3 Definir autoridad documental

Establecer qué documento tiene autoridad sobre:

- metodología;
- roadmap;
- estado;
- arquitectura;
- contratos;
- validación;
- implementación.

Estado: PENDIENTE.

---

1.4 Establecer sistema de estado

Definir una única forma persistente de indicar:

- fase;
- paso;
- objetivo;
- entregable;
- estado;
- bloqueos;
- siguiente paso.

Estado: PENDIENTE.

---

FASE 2 — MODELO DE NEGOCIO Y OPORTUNIDADES

2.1 Investigación de mercado

Analizar:

- demanda;
- competencia;
- intención;
- monetización;
- viabilidad.

Estado: PARCIALMENTE COMPLETADO.

---

2.2 Modelo de oportunidades

Definir cómo se representan las oportunidades.

Estado: PARCIALMENTE COMPLETADO.

---

2.3 Motor de decisión

Definir cuándo una oportunidad:

CREAR
REVISAR
NO_CREAR

Estado: PARCIALMENTE COMPLETADO.

---

2.4 Matrices de decisión

Completar las matrices necesarias.

Estado: PARCIALMENTE COMPLETADO.

---

FASE 3 — ARQUITECTURA SEO Y DE INFORMACIÓN

3.1 Arquitectura de URLs

Definir:

- patrones;
- jerarquía;
- canonical;
- páginas objetivo;
- reglas de indexación.

Estado: COMPLETADO / DOCUMENTADO.

---

3.2 Arquitectura de landing

Definir:

- estructura;
- bloques;
- orden;
- reglas;
- contenido;
- enlazado.

Estado: DOCUMENTADO.

---

3.3 Sistema de bloques

Definir B01–B23.

Estado: DOCUMENTADO.

---

3.4 Interlinking

Definir reglas de enlazado interno.

Estado: DOCUMENTADO / PENDIENTE DE IMPLEMENTACIÓN.

---

FASE 4 — MODELO DE DATOS

4.1 Modelo de datos canónico

Definir entidades y relaciones.

Estado: DOCUMENTADO.

---

4.2 Modelo de datos WordPress

Definir cómo se almacenarán los datos en WordPress.

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
- reglas.

Estado: DOCUMENTADO.

---

5.2 Generación estructurada

Construir el generador que produzca la salida según el contrato IA.

Estado: PENDIENTE DE IMPLEMENTACIÓN REAL.

---

5.3 Selección de bloques

Implementar la selección B01–B23.

Estado: PENDIENTE DE IMPLEMENTACIÓN REAL.

---

FASE 6 — VALIDADOR

6.1 Validador estructural

Comprobar esquema y campos.

Estado: DOCUMENTADO.

---

6.2 Validador semántico

Comprobar:

- intención;
- identidad;
- evidencia;
- coherencia;
- invenciones;
- utilidad.

Estado: DOCUMENTADO / PENDIENTE DE IMPLEMENTACIÓN FINAL.

---

6.3 Validador de landing

Comprobar la landing completa.

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
- renderizado.

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
...
B23

Cada componente debe:

- recibir los datos correspondientes;
- validar entradas necesarias;
- renderizar correctamente;
- mantener consistencia visual;
- funcionar de forma reutilizable.

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
- bloqueo de publicación.

Estado: PENDIENTE.

---

FASE 9 — PRIMERA LANDING REAL

9.1 Fixture de referencia

Utilizar el caso:

Fontanero Marbella

como primera unidad controlada.

Estado: DISPONIBLE.

---

9.2 Generación real

Ejecutar el flujo completo.

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
- automatización.

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
- estabilidad.

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
- alertas.

Estado: PENDIENTE.

---

FASE 13 — REUTILIZACIÓN

Una vez validada la fábrica:

Crear nuevos verticales

Ejemplos:

FONTANERO
ELECTRICISTA
CARPINTERO
PINTOR
JARDINERO
ABOGADO
REFORMAS

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

El sistema reutilizará el método pero tendrá:

- entidades diferentes;
- fuentes diferentes;
- modelo de datos específico;
- reglas de decisión específicas;
- arquitectura específica.

Estado: FUTURO.

---

6. CRITERIO DE FINALIZACIÓN DEL PROYECTO

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

sin depender de intervención manual para cada paso.

---

7. REGLA DE AVANCE

Para avanzar de una fase a otra:

1. El paso actual debe estar completado.
2. El entregable debe existir.
3. Debe haberse verificado.
4. Los bloqueos deben estar resueltos.
5. El estado debe quedar registrado.

Solo entonces se activa el siguiente paso.

---

8. REGLA DE NO DESVIACIÓN

NO SE RETROCEDE SIN BLOQUEO REAL.

Durante una fase:

- las mejoras se registran;
- las ideas nuevas se registran;
- las optimizaciones se registran;
- los problemas no bloqueantes se registran.

Pero se continúa trabajando en el paso actual.

---

9. REGLA PARA SESIONES FUTURAS

Cuando el usuario diga:

«Sigue»

el asistente debe:

1. Leer "maestro.md".
2. Leer "proyecto/roadmap-fabrica-webs.md".
3. Leer este "proyecto/roadmap-proyecto.md".
4. Leer "proyecto/protocolo-ejecucion.md".
5. Leer "proyecto/checklist-arranque.md".
6. Determinar el paso actual.
7. Leer únicamente la documentación técnica necesaria.
8. Continuar exactamente desde ese paso.
9. No cambiar de fase sin completar el paso.
10. Registrar el nuevo estado al terminar.

---

10. PRINCIPIO FINAL

ROADMAP UNIVERSAL
        ↓
ROADMAP DEL PROYECTO
        ↓
PASO ACTUAL
        ↓
DOCUMENTACIÓN
        ↓
CONSTRUCCIÓN
        ↓
VERIFICACIÓN
        ↓
REGISTRO
        ↓
SIGUIENTE PASO

El roadmap determina qué hacer.

El protocolo determina cómo trabajar.

El estado determina dónde estamos.

La documentación técnica determina cómo construir cada pieza.

La memoria de conversación no determina el estado del proyecto.

---

FIN DEL ROADMAP DEL PROYECTO
