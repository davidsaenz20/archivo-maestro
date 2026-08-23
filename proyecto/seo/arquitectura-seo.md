# Arquitectura SEO del proyecto

## 1. Objetivo

Crear una plataforma de servicios profesionales capaz de generar de forma controlada páginas específicas combinando:

- Servicio
- Especialidad
- Localidad
- Intención de búsqueda
- Tipo de cliente
- Cobertura territorial

El objetivo no es generar miles de páginas idénticas, sino construir páginas útiles, diferenciadas y con información real sobre cada servicio y localidad.

---

## 2. Modelo principal

La estructura parte de un servicio profesional y lo combina con una localidad cuando existe una oportunidad real.

Ejemplos:

- Fontanero Marbella
- Fontanero Málaga
- Fontanero Sevilla
- Fontanero Bilbao

Pero también pueden existir combinaciones más específicas:

- Desatascos Marbella
- Reparación de fugas Marbella
- Instalación de termos Marbella
- Fontanero urgente Marbella

No todas las combinaciones deben convertirse automáticamente en páginas.

---

## 3. Principio fundamental

La generación de páginas debe estar controlada por un motor de decisión.

El sistema debe valorar como mínimo:

- Existencia del servicio.
- Demanda o intención de búsqueda.
- Relevancia de la localidad.
- Especialización del servicio.
- Diferenciación respecto a otras páginas.
- Posibilidad de aportar información local real.
- Tipo de cliente.
- Competencia.
- Potencial comercial.

Si una combinación no aporta suficiente valor, no se genera como página independiente.

---

## 4. Estructura territorial

El sistema debe poder trabajar con diferentes niveles:

- País
- Comunidad autónoma
- Provincia
- Ciudad
- Municipio
- Localidad o zona
- Barrios o zonas relevantes cuando exista suficiente información

La profundidad territorial no será idéntica para todos los servicios ni para todas las localidades.

---

## 5. Tipos de páginas

### Servicio general

Ejemplo:

Fontanería

### Servicio + localidad

Ejemplo:

Fontanero Marbella

### Especialidad + localidad

Ejemplo:

Desatascos Marbella

### Servicio urgente + localidad

Ejemplo:

Fontanero urgente Marbella

### Servicio especializado + localidad

Ejemplo:

Instalación de termos Marbella

La existencia de cada tipo de página dependerá del motor de decisión.

---

## 6. Diferenciación local

Una página local debe poder incorporar información específica de la localidad.

Puede incluir:

- Zonas atendidas.
- Características del municipio.
- Tipos de viviendas.
- Problemas habituales.
- Servicios especialmente relevantes.
- Contexto turístico cuando sea relevante.
- Tipo de cliente predominante.
- Horarios o urgencias.
- Información comercial.
- Preguntas frecuentes específicas.
- Datos propios del servicio.

No se debe limitar a sustituir automáticamente el nombre de una ciudad dentro de una plantilla.

---

## 7. Fontanería como primer pilar

Fontanería será el primer pilar utilizado para desarrollar y validar el sistema.

Servicios y especialidades identificados inicialmente:

- Fontanería general.
- Reparación de fugas.
- Desatascos.
- Tuberías.
- Agua caliente.
- Termos.
- Urgencias.
- Instalaciones.
- Mantenimiento.
- Otros servicios relacionados que superen el filtro del motor de decisión.

Esta lista no se considera definitiva hasta completar el motor de decisión.

---

## 8. Motor de decisión

El motor deberá determinar:

1. Si existe una combinación servicio + localidad válida.
2. Si merece una página independiente.
3. Qué tipo de página corresponde.
4. Qué información local debe incorporarse.
5. Qué nivel de profundidad territorial debe utilizarse.
6. Qué contenidos deben evitarse por ser duplicados o poco útiles.

El motor será posteriormente trasladado a la automatización con N8N + IA.

---

## 9. Principio de escalabilidad

La arquitectura debe poder reutilizarse para otros pilares profesionales:

- Electricidad
- Carpintería
- Pintura
- Jardinería
- Reformas
- Abogados
- Climatización
- Cerrajería
- Otros servicios profesionales

Cada pilar tendrá su propia investigación y matriz, pero utilizará una arquitectura común.

---

## 10. Estado

Fontanería:
- Investigación: avanzada.
- Matriz: avanzada.
- Arquitectura SEO: definida.
- Motor de decisión: pendiente de formalización definitiva.
- Automatización N8N + IA: pendiente.
- Implementación web: pendiente.

Este documento debe evolucionar conforme se validen las reglas del sistema.
