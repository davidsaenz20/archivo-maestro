SISTEMA DE INTERLINKING SEO

Versión: 1.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir cómo se crean y mantienen automáticamente las relaciones internas entre páginas, localidades, servicios, subservicios y pilares SEO.

---

1. FUNCIÓN

Este documento define el sistema oficial de enlazado interno del proyecto SEO local.

El sistema debe permitir conectar automáticamente:

- páginas del mismo servicio;
- páginas de diferentes localidades;
- subservicios con sus páginas padre;
- servicios relacionados;
- diferentes pilares SEO;
- páginas de una misma miniweb;
- miniwebs pertenecientes a localidades relacionadas.

El objetivo no es crear el mayor número posible de enlaces.

El objetivo es construir una arquitectura interna:

- lógica;
- útil;
- rastreable;
- escalable;
- coherente;
- autorizada;
- comprensible para usuarios y buscadores.

---

2. PRINCIPIO FUNDAMENTAL

Todo enlace interno debe responder a una relación real entre dos páginas.

No se deben crear enlaces únicamente porque:

- exista una URL;
- exista una keyword;
- queramos transmitir autoridad;
- queramos aumentar el número de enlaces;
- queramos conectar todas las páginas entre sí.

La pregunta principal será:

"¿Tiene sentido que un usuario que está en esta página visite la página de destino?"

Si la respuesta es no:

NO SE ENLAZA.

---

3. DEFINICIÓN

Un enlace interno es cualquier enlace entre dos URLs pertenecientes al mismo activo digital o dominio controlado por el proyecto.

Por tanto, son enlaces internos:

- Fontanero Estepona → Fontanero Casares.
- Fontanero Estepona → Electricista Estepona.
- Fontanero Estepona → Desatascos Estepona.
- Carpintero Estepona → Reformas Estepona.

Aunque pertenezcan a pilares diferentes, siguen siendo enlaces internos si están dentro del mismo dominio.

---

4. TIPOS DE RELACIÓN

El sistema reconoce inicialmente seis tipos:

R01 — PADRE → HIJA

Ejemplo:

Fontanero Estepona

↓

Desatascos Estepona

---

R02 — HIJA → PADRE

Ejemplo:

Desatascos Estepona

↓

Fontanero Estepona

---

R03 — MISMO SERVICIO / DIFERENTE LOCALIDAD

Ejemplo:

Fontanero Estepona

↓

Fontanero Casares

---

R04 — SERVICIOS RELACIONADOS

Ejemplo:

Fontanero Estepona

↓

Electricista Estepona

---

R05 — MISMO PILAR / SERVICIO RELACIONADO

Ejemplo:

Fontanero Estepona

↓

Fontanero 24 horas Estepona

---

R06 — RELACIÓN TERRITORIAL

Ejemplo:

Fontanero Estepona

↓

Fontanero San Pedro

cuando la relación territorial haya sido autorizada.

---

5. GRAFO SEO

El sistema debe poder representar el sitio como un grafo.

Ejemplo:

FONTANERÍA
│
├── Estepona
│   ├── Fontanero
│   ├── Desatascos
│   └── Fontanero 24 horas
│
├── Casares
│   ├── Fontanero
│   └── Desatascos
│
└── San Pedro
├── Fontanero
└── Desatascos

Y otros pilares:

SERVICIOS DEL HOGAR
│
├── Fontanería
├── Electricidad
├── Carpintería
└── Pintura

El enlazado debe utilizar las relaciones existentes en este grafo.

---

6. REGLA DE AUTORIDAD

La IA no puede inventar una URL de destino.

Una URL solo puede utilizarse cuando:

- existe;
- está autorizada;
- pertenece a la arquitectura;
- es compatible con la relación.

La arquitectura determina qué páginas existen.

El sistema de interlinking determina qué relaciones pueden establecerse.

La IA puede proponer el enlace.

N8N ejecuta el enlace.

---

7. LOCALIDAD → LOCALIDAD

Se permite enlazar páginas del mismo servicio entre localidades.

Ejemplo:

/fontaneros/estepona/

puede enlazar a:

/fontaneros/casares/

/fontaneros/san-pedro/

/fontaneros/manilva/

si dichas relaciones están autorizadas.

No se debe enlazar automáticamente con todas las localidades existentes.

---

8. RELACIÓN TERRITORIAL

La relación entre localidades debe poder clasificarse como:

- cercana;
- perteneciente a la misma zona;
- área de servicio relacionada;
- localidad estratégica;
- relación comercial;
- relación pendiente de validación.

No se debe inventar una relación territorial.

---

9. LÍMITE DE ENLACES ENTRE LOCALIDADES

No se establece un número fijo universal de enlaces.

El número dependerá de:

- número de localidades;
- proximidad;
- importancia;
- arquitectura;
- intención;
- utilidad para el usuario;
- densidad de enlaces;
- riesgo de sobreoptimización.

No se debe crear una red completa:

A → B → C → D → E → F → ...

solo para conectar todas las localidades.

---

10. SERVICIO → SERVICIO

Se permite enlazar diferentes servicios cuando exista una relación lógica.

Ejemplo:

Fontanero Estepona

→

Electricista Estepona

o:

Fontanero Estepona

→

Pintor Estepona

o:

Carpintero Estepona

→

Reformas Estepona

La relación debe estar justificada.

---

11. SERVICIOS RELACIONADOS

Los servicios relacionados deben registrarse explícitamente.

Ejemplo conceptual:

{
"source": "/fontaneros/estepona/",
"target": "/electricistas/estepona/",
"relation": "related_service"
}

La IA no puede crear automáticamente una relación no autorizada.

---

12. SUBSERVICIOS

Un subservicio debe enlazar normalmente con su página padre.

Ejemplo:

/fontaneros/estepona/desatascos/

→

/fontaneros/estepona/

La página padre puede enlazar de vuelta al subservicio.

---

13. BREADCRUMBS

Cuando corresponda, las relaciones padre/hija deben poder representarse también mediante breadcrumbs.

Ejemplo:

Inicio
→
Fontaneros
→
Fontaneros Estepona
→
Desatascos Estepona

Los breadcrumbs deben utilizar únicamente URLs existentes.

---

14. ENLACES DE NAVEGACIÓN

Los enlaces de navegación forman parte del sistema de interlinking.

Ejemplos:

- menú;
- navegación secundaria;
- breadcrumbs;
- footer;
- bloques de servicios relacionados;
- bloques de localidades relacionadas.

Todos deben utilizar URLs autorizadas.

---

15. ENLACES CONTEXTUALES

Además de la navegación, se permiten enlaces dentro del contenido cuando tengan sentido.

Ejemplo:

"También ofrecemos servicios de desatascos en Estepona."

→ enlace contextual a:

/fontaneros/estepona/desatascos/

El anchor debe ser natural.

No se deben introducir enlaces únicamente para colocar keywords.

---

16. ANCHORS

Los anchors deben ser:

- naturales;
- descriptivos;
- útiles;
- relacionados con la página destino.

No se debe utilizar siempre exactamente la keyword principal.

Ejemplo válido:

"servicio de desatascos en Estepona"

También puede utilizarse:

"desatascos"

"servicio de fontanería"

"fontanería urgente"

cuando corresponda.

---

17. DENSIDAD

No existe un número obligatorio de enlaces por página.

La cantidad debe depender de:

- contenido;
- número de páginas relacionadas;
- intención;
- arquitectura;
- utilidad.

Una página no debe llenarse de enlaces artificialmente.

---

18. REGLA DE RELEVANCIA

Antes de crear un enlace:

ORIGEN
↓
¿Existe DESTINO?
↓
¿Está autorizado?
↓
¿Existe relación?
↓
¿Es útil para el usuario?
↓
SÍ
↓
CREAR ENLACE

Si cualquiera de los criterios críticos falla:

NO CREAR.

---

19. REGLA DE NO SOBREOPTIMIZACIÓN

No se debe crear:

- bloques gigantes de enlaces;
- listas artificiales de localidades;
- cientos de enlaces desde una página;
- enlaces repetidos innecesariamente;
- anchors idénticos de forma sistemática.

El sistema debe priorizar calidad sobre cantidad.

---

20. PÁGINAS HUÉRFANAS

Una página no debería quedar aislada cuando existan relaciones autorizadas.

El validador debe detectar:

- páginas sin enlaces entrantes;
- páginas sin enlaces salientes cuando deberían tenerlos;
- páginas desconectadas de su padre;
- páginas desconectadas del pilar.

Resultado:

REVIEW

cuando la arquitectura esperaba conexiones.

---

21. RELACIONES ENTRANTES

El sistema debe poder calcular:

incoming_links

Número de enlaces internos que apuntan hacia una página.

Esto permitirá detectar páginas:

- aisladas;
- centrales;
- secundarias;
- estratégicas.

---

22. RELACIONES SALIENTES

El sistema debe poder calcular:

outgoing_links

Número de enlaces internos que salen de una página.

Debe utilizarse para detectar páginas con una densidad anormal de enlaces.

---

23. PÁGINAS ESTRATÉGICAS

La arquitectura podrá marcar determinadas páginas como estratégicas.

Ejemplo:

- página principal del servicio;
- página principal de localidad;
- página comercial;
- página de servicio con mayor valor.

Estas páginas pueden recibir mayor cantidad de enlaces internos, siempre de forma natural.

---

24. INTERLINKING ENTRE PILARES

Los pilares pueden conectarse.

Ejemplo:

FONTANERÍA
│
├── Estepona
├── Casares
└── Manilva

ELECTRICIDAD
│
├── Estepona
├── Casares
└── Manilva

Una página de Fontanería Estepona puede enlazar a Electricidad Estepona si ambas páginas están relacionadas y autorizadas.

Esto crea una arquitectura temática transversal.

---

25. REGLA DE SIMETRÍA

Los enlaces no tienen que ser siempre bidireccionales.

Ejemplo:

Fontanero Estepona

→

Electricista Estepona

puede ser válido sin que:

Electricista Estepona

→

Fontanero Estepona

sea obligatorio.

La relación debe decidirse por utilidad e intención.

---

26. RELACIÓN CON BLOQUES

Los siguientes bloques pueden utilizar el sistema de interlinking:

- B02 navigation;
- B06 footer;
- B15 related_services;
- B16 related_locations;
- B04 main_content;
- B07 subservice;
- B10 coverage.

No se crean bloques nuevos para resolver el interlinking si ya existe un bloque autorizado que cumple esa función.

---

27. RELACIÓN CON IA

La IA puede proponer:

- URL destino;
- anchor;
- tipo de relación;
- motivo.

Pero únicamente dentro de las relaciones y URLs autorizadas.

Ejemplo:

{
"source_url": "/fontaneros/estepona/",
"target_url": "/fontaneros/casares/",
"anchor": "fontaneros en Casares",
"relation": "related_location",
"reason": "Localidad relacionada autorizada"
}

---

28. RELACIÓN CON N8N

N8N será responsable de:

- leer las relaciones;
- comprobar que las URLs existen;
- comprobar autorización;
- generar los enlaces;
- actualizar enlaces cuando cambie la arquitectura;
- eliminar enlaces obsoletos;
- evitar duplicados;
- registrar incidencias.

N8N no debe inventar relaciones.

---

29. IDEMPOTENCIA

El procesamiento repetido no debe crear enlaces duplicados.

Cada relación debe tener un identificador estable.

Ejemplo:

LINK-FON-EST-CAS-001

Si ya existe:

actualizar.

Si no existe:

crear.

Nunca duplicar.

---

30. ACTUALIZACIÓN

Cuando se cree una nueva página:

el sistema debe comprobar qué páginas existentes deberían enlazar hacia ella.

Ejemplo:

Se crea:

/fontaneros/casares/desatascos/

El sistema puede actualizar:

/fontaneros/casares/

/fontaneros/casares/24-horas/

y otras páginas autorizadas.

---

31. ELIMINACIÓN

Si una página deja de estar autorizada:

- eliminar enlaces que apunten a ella;
- actualizar navegación;
- actualizar bloques relacionados;
- eliminar relaciones obsoletas.

No deben quedar enlaces rotos.

---

32. CAMBIOS DE ARQUITECTURA

Si cambia la arquitectura:

ARQUITECTURA
↓
NUEVAS RELACIONES AUTORIZADAS
↓
VALIDACIÓN
↓
N8N
↓
ACTUALIZACIÓN DEL INTERLINKING

La IA no puede modificar directamente la arquitectura.

---

33. VALIDACIÓN

El sistema debe comprobar:

- URL origen válida;
- URL destino válida;
- destino autorizado;
- relación autorizada;
- anchor válido;
- ausencia de duplicado;
- ausencia de enlace roto;
- coherencia con la arquitectura.

---

34. ERRORES

Ejemplos:

LINK_TARGET_NOT_AUTHORIZED

LINK_TARGET_NOT_FOUND

LINK_DUPLICATE

LINK_INVALID_RELATION

LINK_ORPHAN_PAGE

LINK_EXCESSIVE_DENSITY

LINK_ARCHITECTURE_CONFLICT

---

35. PRINCIPIO DE ESCALABILIDAD

El sistema debe funcionar igual con:

10 páginas

100 páginas

1.000 páginas

10.000 páginas

sin necesidad de construir manualmente el enlazado.

La arquitectura debe determinar las relaciones y N8N debe ejecutarlas.

---

36. EJEMPLO COMPLETO

Ejemplo:

/fontaneros/estepona/

puede tener:

→ /fontaneros/estepona/desatascos/
→ /fontaneros/estepona/24-horas/
→ /fontaneros/casares/
→ /electricistas/estepona/

Mientras que:

/fontaneros/casares/

puede tener:

→ /fontaneros/casares/desatascos/
→ /fontaneros/estepona/
→ /electricistas/casares/

No existe obligación de enlazar todas las páginas entre sí.

---

37. PRINCIPIO FINAL

El proyecto debe construir una red semántica.

No:

PÁGINAS AISLADAS

Ni:

TODAS LAS PÁGINAS CONECTADAS CON TODAS

Sino:

PÁGINAS
↓
RELACIONES REALES
↓
ENLACES AUTORIZADOS
↓
ARQUITECTURA COHERENTE

---

38. ESTADO

Versión:

1.0

Estado:

PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha:

2026-08-24

---

FIN DEL SISTEMA DE INTERLINKING SEO
