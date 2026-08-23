Arquitectura SEO del Proyecto

1. Objetivo

Crear una plataforma de servicios profesionales capaz de generar de forma controlada páginas específicas combinando:

- Servicio.
- Especialidad.
- Localidad.
- Intención de búsqueda.
- Tipo de cliente.
- Cobertura territorial.
- Información local.

El objetivo no es generar miles de páginas idénticas.

El objetivo es construir páginas útiles, diferenciadas y justificadas por una oportunidad real.

---

2. Modelo principal

La estructura principal parte de:

SERVICIO + LOCALIDAD

Ejemplos:

- Fontanero Marbella.
- Fontanero Málaga.
- Fontanero Sevilla.
- Fontanero Bilbao.

Pero también pueden existir combinaciones más específicas:

- Desatascos Marbella.
- Reparación de fugas Marbella.
- Instalación de termos Marbella.
- Fontanero urgente Marbella.

No todas las combinaciones deben convertirse automáticamente en páginas.

La existencia de una combinación solo constituye una oportunidad que debe ser evaluada por el motor de decisión.

---

3. Principio fundamental

La generación de páginas debe estar controlada por un sistema de decisión.

El sistema debe valorar como mínimo:

- Existencia del servicio.
- Demanda o intención de búsqueda.
- Relevancia territorial.
- Especialización.
- Tipo de cliente.
- Competencia.
- Potencial comercial.
- Diferenciación.
- Información local disponible.
- Riesgo de contenido duplicado.
- Utilidad real para el usuario.

Si una combinación no aporta suficiente valor, no se genera como página independiente.

---

4. Unidad de análisis

La unidad principal del sistema es:

SERVICIO × LOCALIDAD

La decisión no debe basarse únicamente en que exista un servicio ni únicamente en que exista una localidad.

Debe analizarse la combinación concreta.

---

5. Estructura territorial

El sistema puede trabajar con diferentes niveles:

- País.
- Comunidad autónoma.
- Provincia.
- Ciudad.
- Municipio.
- Localidad.
- Zona.
- Barrio.
- Urbanización.

La profundidad territorial no será idéntica para todos los servicios ni para todas las localidades.

Dependerá de:

- Demanda.
- Relevancia territorial.
- Competencia.
- Potencial comercial.
- Información local disponible.
- Características del mercado.
- Posibilidad de diferenciación.

No se deben crear niveles territoriales artificialmente.

---

6. Tipos de páginas

Servicio general

Ejemplo:

Fontanería

Servicio + localidad

Ejemplo:

Fontanero Marbella

Especialidad + localidad

Ejemplo:

Desatascos Marbella

Urgencia + localidad

Ejemplo:

Fontanero urgente Marbella

Servicio especializado + localidad

Ejemplo:

Reparación de termos Marbella

La existencia de cada tipo de página debe estar justificada por el sistema de decisión.

---

7. Diferenciación local

Una página local debe poder incorporar información específica y real de la localidad.

Puede incluir:

- Zonas atendidas.
- Barrios.
- Urbanizaciones.
- Características del municipio.
- Tipos de viviendas.
- Problemas habituales.
- Servicios especialmente relevantes.
- Contexto turístico.
- Segundas residencias.
- Perfil de cliente.
- Horarios.
- Urgencias.
- Información comercial.
- Preguntas frecuentes específicas.

No se debe limitar a cambiar automáticamente el nombre de una localidad dentro de una plantilla.

---

8. Fontanería como primer caso de aplicación

Fontanería es el primer sector utilizado para investigar y validar el sistema.

La clasificación específica del sector puede incluir:

- Fontanería general.
- Reparación de fugas.
- Detección de fugas.
- Desatascos.
- Tuberías.
- Agua caliente.
- Termos.
- Calentadores.
- Urgencias.
- Instalaciones.
- Mantenimiento.
- Otros servicios que sean identificados mediante investigación.

Esta clasificación es específica del sector y no debe copiarse automáticamente a otros servicios.

---

9. Motor de decisión

El motor de decisión se encuentra documentado en:

"proyecto/seo/motor-decision.md"

El motor determina, para cada combinación relevante:

- Si existe una oportunidad.
- Si merece una página independiente.
- Qué tipo de página corresponde.
- Qué profundidad territorial utilizar.
- Qué información local debe incorporarse.
- Qué contenidos deben evitarse.
- Si la combinación debe CREARSE, AGRUPARSE, INVESTIGARSE o NO CREARSE.

---

10. Decisiones posibles

CREAR

Crear una página independiente.

AGRUPAR

Integrar el servicio o intención dentro de otra página.

INVESTIGAR

Existe una oportunidad potencial pero falta información crítica.

NO CREAR

No existe suficiente justificación para una página independiente.

---

11. Principio de diferenciación

No es suficiente:

- cambiar el nombre de la ciudad;
- cambiar algunas palabras;
- duplicar una plantilla;
- generar contenido artificial.

Cada página debe tener una función clara y aportar información útil.

---

12. Riesgo de contenido programático

La generación masiva puede producir:

- Contenido repetitivo.
- Páginas de poco valor.
- Canibalización.
- Problemas de indexación.
- Costes innecesarios.
- Mala experiencia de usuario.

Por ello:

la automatización debe estar subordinada al sistema de decisión.

---

13. Arquitectura reutilizable

La arquitectura general está diseñada para poder aplicarse a:

- Fontanería.
- Electricidad.
- Carpintería.
- Pintura.
- Jardinería.
- Reformas.
- Abogados.
- Climatización.
- Cerrajería.
- Otros servicios profesionales.

La estructura general se reutiliza.

La investigación y las reglas específicas de cada sector deben desarrollarse por separado.

---

14. Capa general y capa sectorial

El sistema tendrá conceptualmente dos niveles.

Capa general

Reglas comunes de:

- Investigación.
- Clasificación.
- Evaluación.
- Decisión.
- Validación.
- Medición.
- Escalado.

Capa sectorial

Características específicas de cada servicio:

- Servicios.
- Intenciones.
- Clientes.
- Particularidades territoriales.
- Potencial comercial.
- Excepciones.
- Parámetros específicos.

Esto permite escalar sin convertir cada sector en un sistema completamente diferente.

---

15. Relación con la metodología

La arquitectura se integra dentro de la metodología general:

INVESTIGAR

↓

CONSERVAR

↓

ESTRUCTURAR

↓

DECIDIR

↓

VALIDAR

↓

PROBAR

↓

MEDIR

↓

CORREGIR

↓

AUTOMATIZAR

↓

ESCALAR

La arquitectura no debe adelantarse a una fase que todavía no haya sido validada.

---

16. Automatización

La automatización con herramientas como N8N e IA se desarrollará posteriormente.

La automatización debe utilizar únicamente reglas, estructuras y decisiones previamente definidas y validadas.

La tecnología no debe utilizarse para automatizar una lógica todavía incorrecta.

---

17. Regla de calidad arquitectónica

Toda nueva capa de páginas debe responder a una necesidad real.

Antes de crear una nueva combinación de:

SERVICIO × LOCALIDAD

debe poder explicarse:

- Qué intención satisface.
- Qué valor aporta.
- Por qué merece existir como página independiente.
- Qué información específica puede contener.
- Cómo se diferencia de páginas similares.

Si estas preguntas no pueden responderse satisfactoriamente, la combinación debe pasar por el motor de decisión antes de generarse.

---

18. Regla de escalabilidad

La arquitectura debe permitir aumentar:

- número de servicios;
- número de localidades;
- número de especialidades;
- número de páginas;

sin perder:

- utilidad;
- diferenciación;
- calidad;
- trazabilidad;
- control;
- capacidad de validación.

El crecimiento debe producirse mediante reglas y datos, no mediante duplicación indiscriminada.

---

19. Regla de independencia sectorial

Cada nuevo servicio debe investigarse de forma independiente.

La arquitectura general puede reutilizarse, pero no deben heredarse automáticamente:

- servicios;
- pesos;
- umbrales;
- intenciones;
- niveles territoriales;
- excepciones;
- decisiones;

de otro sector.

Cada sector debe generar su propia evidencia y, cuando sea necesario, sus propias reglas sectoriales.
