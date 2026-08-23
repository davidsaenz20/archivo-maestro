# MATRIZ DE OPORTUNIDADES — FONTANERÍA

## 1. FUNCIÓN

Esta matriz identifica y estructura oportunidades SEO potenciales de fontanería.

Actúa entre:

EVIDENCIAS
↓
MATRIZ DE OPORTUNIDADES
↓
MOTOR DE DECISIÓN

No decide por sí misma si debe crearse una landing.

La decisión corresponde al motor.

---

## 2. ESTRUCTURA DE OPORTUNIDAD

Cada oportunidad representa una combinación potencial de:

SERVICIO × LOCALIDAD

o:

SERVICIO × SUBSERVICIO × LOCALIDAD

Cada oportunidad debe disponer de un identificador único.

Formato:

OPP-001
OPP-002
OPP-003

Los identificadores no se reutilizan.

---

## 3. CAMPOS

Cada oportunidad debe contener, cuando corresponda:

- opportunity_id
- sector
- servicio
- subservicio
- tipo_pagina
- país
- comunidad_autonoma
- provincia
- municipio
- localidad
- evidencias
- intención
- demanda
- potencial_comercial
- relevancia_territorial
- competencia
- diferenciación
- información_disponible
- riesgo_duplicacion
- estado_investigacion
- decision_seo
- url
- observaciones
- historial

Los datos desconocidos no se inventan.

---

## 4. ESTADOS DE INVESTIGACIÓN

Valores:

DETECTADA

EN_INVESTIGACION

EVIDENCIA_SUFICIENTE

EVIDENCIA_INSUFICIENTE

VALIDADA

---

## 5. DECISIÓN SEO

Valores oficiales:

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

Mientras no exista una decisión:

PENDIENTE

---

## 6. REGLA FUNDAMENTAL

La existencia de:

servicio + localidad

no implica automáticamente:

CREAR

La decisión debe considerar:

- intención;
- demanda;
- potencial comercial;
- relevancia territorial;
- competencia;
- diferenciación;
- información disponible;
- riesgo de duplicación.

---

# 7. OPORTUNIDAD OPP-001

## Identificación

ID:

OPP-001

Sector:

Fontanería

Servicio:

Fontanero

Subservicio:

null

Tipo:

servicio_localidad

---

## Localización

País:

España

Comunidad autónoma:

Andalucía

Provincia:

Málaga

Municipio:

Marbella

Localidad:

null

---

## Evaluación

Intención:

ALTA

Demanda:

DESCONOCIDA

Potencial comercial:

ALTO

Relevancia territorial:

ALTA

Competencia:

ALTA

Diferenciación:

INSUFICIENTEMENTE DOCUMENTADA

Información disponible:

MEDIA

Riesgo de duplicación:

MEDIO_ALTO

---

## Estado

Estado de investigación:

EVIDENCIA_INSUFICIENTE

Decisión SEO:

INVESTIGAR

---

## URL

URL propuesta:

`/fontanero/marbella/`

Estado:

PENDIENTE_DE_APROBACION

La URL no debe considerarse definitiva hasta que la decisión sea:

CREAR

---

## Motivo de INVESTIGAR

Existe una intención local comercial clara y una oferta local confirmada.

Sin embargo, todavía no existe suficiente evidencia sobre:

- demanda cuantitativa;
- diferenciación real;
- información local propia;
- capacidad de crear una landing suficientemente específica;
- riesgo real de duplicación frente a otras localidades.

Por tanto, no se autoriza todavía la creación de una landing publicable.

---

# 8. PRUEBA TÉCNICA

OPP-001 puede utilizarse como caso de prueba técnica del sistema de generación.

Esta prueba debe estar marcada como:

TEST

y no debe modificar:

decision_seo = INVESTIGAR

La generación técnica no constituye aprobación SEO.

No debe publicarse en WordPress.

No debe enviarse a producción.

---

# 9. FLUJO DE OPP-001

Actualmente:

INVESTIGACIÓN
↓
EVIDENCIA
↓
OPP-001
↓
INVESTIGAR

Pendiente:

nueva evidencia
↓
reevaluación
↓
CREAR / AGRUPAR / INVESTIGAR / NO CREAR

Si finalmente:

CREAR

entonces:

ARQUITECTURA
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

---

# 10. RELACIÓN CON EL ESQUEMA DE DATOS

El modelo canónico está definido en:

`proyecto/seo/esquema-datos.md`

Esta matriz representa únicamente la capa de oportunidades.

No debe crear estructuras paralelas incompatibles con el esquema canónico.

---

# 11. RELACIÓN CON EL MOTOR

El motor utiliza esta matriz como entrada.

Archivo:

`proyecto/seo/motor-decision.md`

La matriz proporciona datos.

El motor proporciona:

CREAR

AGRUPAR

INVESTIGAR

NO CREAR

---

# 12. RELACIÓN CON ARQUITECTURA

Solo después de:

decision_seo = CREAR

se consolida:

- tipo_pagina;
- URL;
- canonical;
- parent_url;
- profundidad.

La matriz puede contener una URL propuesta, pero nunca constituye por sí misma una autorización para crearla.

---

# 13. RELACIÓN CON LANDING

CREAR:

puede generar landing.

AGRUPAR:

se integra en otra página.

INVESTIGAR:

queda pendiente.

NO CREAR:

no genera landing.

---

# 14. REGLA DE NO INVENCIÓN

No se deben inventar:

- demanda;
- competencia;
- empresas;
- teléfonos;
- WhatsApp;
- emails;
- direcciones;
- precios;
- horarios;
- cobertura;
- zonas;
- reseñas;
- testimonios;
- experiencia;
- certificaciones;
- garantías.

Cuando no exista evidencia:

DESCONOCIDA

o:

null

según el campo.

---

# 15. CONTROL DE DUPLICADOS

Antes de crear una oportunidad nueva se comprobará:

- mismo servicio;
- mismo subservicio;
- mismo municipio;
- misma localidad;
- misma intención.

Si ya existe:

se conserva el opportunity_id existente.

---

# 16. HISTORIAL OPP-001

### 2026-08-23

Estado inicial:

DETECTADA

Posteriormente evaluada mediante el motor.

Resultado:

INVESTIGAR

Motivos principales:

- intención local comercial;
- relevancia territorial;
- oferta local;
- competencia alta;
- demanda cuantitativa desconocida;
- diferenciación insuficientemente documentada;
- información local parcial;
- riesgo de duplicación medio/alto.

Estado actual:

INVESTIGAR

---

# 17. SIGUIENTE ACCIÓN

Para modificar la decisión de OPP-001 se necesita nueva evidencia.

Prioridades:

1. demanda;
2. diferenciación;
3. información local;
4. competencia;
5. riesgo de duplicación.

Hasta entonces:

decision_seo = INVESTIGAR

---

# 18. ESCALABILIDAD

La estructura se podrá reutilizar para:

- electricistas;
- abogados;
- carpinteros;
- pintores;
- jardineros;
- reformas;
- otros servicios profesionales.

Ejemplo futuro:

`matriz-oportunidades-electricistas.md`

La estructura debe permanecer estable.

---

# 19. PRINCIPIO DE CALIDAD

No se crearán oportunidades únicamente mediante:

servicios × localidades

La combinación automática sirve para detectar candidatos.

La evidencia determina cuáles merecen ser evaluados.

El motor determina qué hacer.

---

# 20. ESTADO DEL DOCUMENTO

Estado:

ACTIVO

Versión:

1.1

Fecha:

2026-08-23

Cambios:

- incorporación de OPP-001;
- actualización de su decisión a INVESTIGAR;
- alineación con esquema-datos.md;
- separación entre oportunidad y landing;
- incorporación de prueba técnica;
- incorporación de historial;
- eliminación del estado obsoleto PENDIENTE DE CARGA.

---

# 21. REGLA FINAL

La matriz responde:

¿QUÉ OPORTUNIDADES DEBEMOS EVALUAR?

El motor responde:

¿QUÉ HACEMOS CON CADA OPORTUNIDAD?

La arquitectura responde:

¿QUÉ ESTRUCTURA TENDRÁ?

La IA responde:

¿CÓMO GENERAMOS EL CONTENIDO?

N8N responde:

¿CÓMO AUTOMATIZAMOS EL PROCESO?

WordPress responde:

¿DÓNDE SE PUBLICA?
