ESPECIFICACIÓN DE IA

1. FUNCIÓN

La inteligencia artificial es el motor de generación de contenido del sistema.

Su función es transformar una oportunidad SEO previamente definida en una salida estructurada que pueda ser procesada automáticamente por N8N.

La IA:

- no decide la estrategia SEO;
- no decide qué URLs deben existir;
- no modifica la arquitectura recibida;
- no inventa datos;
- no publica directamente en WordPress;
- no sustituye al motor de decisión;
- no sustituye a N8N.

La IA genera contenido y estructura dentro de las reglas recibidas.

---

2. FLUJO

El flujo general es:

DATOS
↓
MOTOR DE DECISIÓN
↓
ARQUITECTURA SEO
↓
ARQUITECTURA DE LANDING
↓
SISTEMA DE BLOQUES
↓
IA
↓
CONTRATO DE SALIDA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

La IA entra después de que la oportunidad haya sido definida.

---

3. DOCUMENTOS DE REFERENCIA

La IA debe trabajar respetando los documentos maestros del sistema.

Documentos principales:

"proyecto/seo/esquema-datos.md"

"proyecto/seo/matriz-servicios.md"

"proyecto/seo/matriz-localidades.md"

"proyecto/seo/arquitectura-urls.md"

"proyecto/seo/arquitectura-landing.md"

"proyecto/seo/sistema-bloques.md"

"proyecto/seo/contrato-salida-ia.md"

Cuando exista una contradicción, prevalecen las reglas de autoridad establecidas en el sistema.

---

4. ENTRADA DE LA IA

La IA recibirá una oportunidad estructurada.

Como mínimo:

{
  "opportunity_id": "",
  "sector": "",
  "servicio": "",
  "subservicio": null,
  "municipio": "",
  "provincia": "",
  "decision_seo": "",
  "tipo_pagina": "",
  "url": "",
  "canonical": "",
  "bloques_autorizados": [],
  "restricciones": []
}

Estos datos no son una sugerencia.

Son la especificación que la IA debe respetar.

---

5. CAMPOS PROTEGIDOS

La IA no puede modificar:

- opportunity_id
- sector
- servicio
- subservicio
- municipio
- provincia
- decision_seo
- tipo_pagina
- url
- canonical
- bloques_autorizados
- restricciones

Si detecta una contradicción:

"status = REVIEW"

y debe registrar la incidencia.

"REVIEW" es un estado técnico del contrato IA → N8N.

No debe confundirse con "decision_seo".

---

6. VERSIÓN DEL CONTRATO

La versión vigente del contrato de salida IA → N8N es:

"schema_version = "1.1""

La especificación de IA debe mantenerse compatible con:

"proyecto/seo/contrato-salida-ia.md"

N8N debe validar que la salida recibida utiliza una versión de contrato compatible antes de procesarla.

Si la versión no es compatible:

"status = ERROR"

---

7. ESTADOS TÉCNICOS DE LA SALIDA IA

El campo "status" pertenece al contrato técnico IA → N8N.

Valores permitidos:

- "READY"
- "REVIEW"
- "ERROR"

READY

La salida es válida y puede continuar hacia la siguiente fase.

REVIEW

Existe una incidencia que requiere revisión antes de continuar.

ERROR

No se ha podido generar una salida válida.

Estos estados son independientes de "decision_seo".

---

8. DECISIÓN SEO

La IA no determina la decisión SEO.

Las decisiones SEO válidas son:

- "CREAR"
- "AGRUPAR"
- "INVESTIGAR"
- "NO CREAR"

La IA únicamente recibe "decision_seo" como dato protegido.

Si:

"decision_seo != CREAR"

la IA no debe generar una landing lista para publicación.

---

9. URL

La IA no decide la URL.

La URL procede de la arquitectura SEO.

Ejemplo:

servicio = fontanero

municipio = Marbella

subservicio = null

La arquitectura puede proporcionar:

"/fontanero/marbella/"

La IA debe utilizar exactamente esa URL.

---

10. EJEMPLO CON SUBSERVICIO

Si la oportunidad recibida es:

servicio = fontanero

subservicio = desatascos

municipio = Marbella

y la arquitectura determina:

"/fontanero/desatascos/marbella/"

la IA debe utilizar esa URL.

No puede cambiarla.

---

11. EJEMPLO SIN SUBSERVICIO

Si la oportunidad recibida es:

servicio = fontanero

subservicio = null

municipio = Marbella

y la arquitectura determina:

"/fontanero/marbella/"

la IA debe generar una landing de intención general de fontanero en Marbella.

No debe convertirla en una landing de desatascos.

---

12. OBJETIVO DE GENERACIÓN

La IA debe producir una landing:

- coherente;
- específica;
- útil;
- orientada a la intención de búsqueda;
- estructurada;
- diferenciada;
- compatible con el sistema de bloques;
- compatible con N8N;
- compatible con WordPress.

No debe limitarse a sustituir el nombre del municipio dentro de un texto genérico.

---

13. CONTENIDO ESPECÍFICO

La IA debe utilizar:

- sector;
- servicio;
- subservicio cuando exista;
- municipio;
- provincia;
- datos locales disponibles;
- datos comerciales disponibles;
- información de cobertura disponible;
- información de servicios;
- preguntas relevantes;
- información adicional autorizada.

Debe evitar contenido vacío o genérico.

---

14. INFORMACIÓN LOCAL

El municipio por sí solo no constituye información local suficiente.

La IA solo puede utilizar datos locales respaldados por información disponible.

No debe inventar:

- barrios;
- calles;
- zonas;
- lugares;
- características geográficas;
- tiempos de desplazamiento;
- demanda local;
- problemas habituales;
- estadísticas.

---

15. DATOS COMERCIALES

Cuando exista información de una empresa concreta, la IA puede utilizarla.

Cuando no exista, no puede inventarla.

No debe inventar:

- nombre de empresa;
- teléfono;
- WhatsApp;
- email;
- dirección;
- horario;
- precios;
- garantías;
- años de experiencia;
- certificaciones;
- equipo;
- reseñas;
- valoraciones.

---

16. REGLA DE NO INVENCIÓN

La ausencia de información no debe solucionarse mediante imaginación.

Si un dato no está disponible:

"null"

o:

"bloque desactivado"

o:

"status = REVIEW"

según el caso.

Nunca debe inventarse información para evitar una ausencia de datos.

---

17. ARQUITECTURA DE LANDING

La IA debe respetar la arquitectura de landing definida.

La landing puede incluir:

- Header
- Navegación
- Hero
- Contenido principal
- Bloques de servicio
- Información local
- Cobertura
- Proceso
- Confianza
- FAQ
- CTA
- Footer

No todos los bloques tienen que aparecer.

La selección depende de las reglas del sistema de bloques y de los datos disponibles.

---

18. SISTEMA DE BLOQUES

La IA solo puede utilizar bloques autorizados.

Los identificadores deben proceder de:

"proyecto/seo/sistema-bloques.md"

No puede inventar:

- B99
- B100
- B-LOCALES

si no existen en el sistema.

Los identificadores y tipos deben ser compatibles con la versión vigente del contrato de salida.

---

19. BLOQUES OBLIGATORIOS

Los bloques marcados como obligatorios deben aparecer.

Si falta información necesaria para completarlos:

"status = REVIEW"

La IA no debe inventar contenido para completar el bloque.

---

20. BLOQUES CONDICIONALES Y OPCIONALES

Los bloques condicionales solo deben aparecer cuando se cumplen sus condiciones.

Ejemplo:

información local disponible
→ bloque local

Si no:

"bloque local = disabled"

Los bloques opcionales deben utilizarse cuando aporten valor.

No se deben añadir bloques simplemente para hacer la página más larga.

---

21. HERO Y ELEMENTOS SEO

HERO

El Hero debe reflejar la intención principal.

Para:

fontanero + Marbella

el H1 puede ser:

"Fontanero en Marbella"

Para:

fontanero + desatascos + Marbella

el H1 puede ser:

"Desatascos en Marbella"

si esa es la intención definida por la arquitectura.

La IA debe respetar el tipo de página recibido.

TÍTULO SEO

El title debe:

- representar la intención;
- ser natural;
- incluir los elementos principales cuando corresponda;
- evitar sobreoptimización;
- evitar promesas no verificadas.

META DESCRIPTION

Debe:

- describir la página;
- ser específica;
- resultar útil para el usuario;
- evitar afirmaciones no verificadas.

---

22. COMPATIBILIDAD CON EL CONTRATO

Esta especificación describe el comportamiento de la IA.

La estructura exacta de salida JSON está definida por:

"proyecto/seo/contrato-salida-ia.md"

La versión vigente del contrato es:

"1.1"

Por tanto:

Especificación de IA → define el comportamiento.

Contrato de salida IA → define la interfaz técnica.

N8N → valida y procesa la interfaz.

WordPress → recibe los datos validados.

Ninguno de estos documentos puede utilizar una versión diferente del contrato sin una actualización explícita y coordinada.

---

REGLA FINAL

La IA genera.

El motor SEO decide.

La arquitectura determina.

El sistema de bloques autoriza.

El contrato estructura.

El validador comprueba.

N8N procesa.

WordPress publica.

La IA no puede asumir funciones pertenecientes a ninguna de las capas anteriores o posteriores.

---

FIN DE LA ESPECIFICACIÓN DE IA
