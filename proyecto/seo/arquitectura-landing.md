ARQUITECTURA DE LANDING / MINIWEB SEO LOCAL

Versión: 3.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: definir la arquitectura funcional de una landing o miniweb SEO local después de que el Motor de Decisión haya autorizado su creación.

---

1. FUNCIÓN

Este documento define cómo transformar una oportunidad SEO aprobada en una arquitectura web concreta.

Determina:

- qué páginas forman parte del activo;
- qué URL tiene cada página;
- qué relación existe entre páginas;
- qué página es principal;
- qué páginas son subpáginas;
- qué profundidad tiene cada página;
- qué páginas aparecen en la navegación;
- qué bloques están autorizados en cada página;
- qué enlaces internos pueden existir;
- qué páginas deben omitirse.

Este documento no decide si una oportunidad debe existir.

La decisión corresponde a:

"proyecto/seo/motor-decision.md"

La arquitectura tampoco genera contenido.

El contenido será generado posteriormente por la IA mediante:

"proyecto/seo/contrato-salida-ia.md"

---

2. FLUJO OFICIAL

INVESTIGACIÓN
↓
MOTOR DE DECISIÓN
↓
DECISIÓN = CREAR
↓
ARQUITECTURA SEO
↓
ARQUITECTURA MINIWEB
↓
SISTEMA DE BLOQUES
↓
MODELO DE DATOS
↓
CONTRATO IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS
↓
MINIWEB

---

3. PRINCIPIO FUNDAMENTAL

Una oportunidad aprobada no implica que haya que crear muchas páginas.

La arquitectura debe crear el mínimo conjunto de páginas necesario para resolver las intenciones autorizadas.

Por tanto:

«La arquitectura no maximiza el número de URLs.»

Maximiza:

- utilidad;
- cobertura de intención;
- diferenciación;
- navegación;
- coherencia;
- capacidad comercial;
- posibilidad de posicionamiento;
- capacidad de alquiler del activo.

---

4. LANDING VS MINIWEB

El sistema permite dos tipos principales de activo:

LANDING

Una única página que resuelve una intención.

Ejemplo:

/fontanero/manilva/

MINIWEB

Conjunto pequeño y coherente de páginas relacionadas.

Ejemplo:

/fontanero/marbella/
├── desatascos/
├── 24-horas/
└── contacto/

Una miniweb no debe convertirse en un conjunto arbitrario de páginas.

Cada subpágina debe tener una función.

---

5. REGLA DE MÍNIMO VIABLE

La arquitectura debe comenzar siempre con:

PÁGINA PRINCIPAL

Después debe preguntarse:

«¿Existe alguna intención adicional suficientemente justificada para crear otra página?»

Si la respuesta es no:

MINIWEB = 1 PÁGINA

Si existen intenciones adicionales válidas:

MINIWEB = PÁGINA PRINCIPAL + SUBPÁGINAS JUSTIFICADAS

---

6. PÁGINA PRINCIPAL

La página principal representa la intención principal de la oportunidad.

Ejemplo:

/fontanero/marbella/

Debe responder principalmente a:

Fontanero en Marbella

La página puede cubrir:

- servicio principal;
- necesidades principales;
- contexto local;
- cobertura;
- proceso;
- confianza;
- servicios relacionados;
- FAQ;
- conversión.

No debe convertirse en una página genérica que intente posicionar todas las intenciones secundarias.

---

7. SUBPÁGINA

Una subpágina solo puede crearse cuando exista una intención propia.

Debe cumplir simultáneamente:

- intención diferenciable;
- utilidad para el usuario;
- relevancia comercial;
- información suficiente;
- posibilidad de diferenciación;
- coherencia con la arquitectura;
- riesgo de duplicación aceptable.

Ejemplo:

/fontanero/marbella/desatascos/

Tiene una intención distinta de:

/fontanero/marbella/

Por tanto puede justificarse como subpágina.

---

8. REGLA DE NO CREACIÓN DE SUBPÁGINAS

No crear una subpágina simplemente porque exista una combinación:

servicio + localidad + keyword

Tampoco crearla porque:

- parezca interesante;
- la IA pueda escribir contenido;
- exista un sinónimo;
- exista una variación gramatical;
- queramos aumentar URLs;
- queramos aumentar palabras;
- queramos aumentar enlaces.

La pregunta es:

«¿El usuario tiene una intención suficientemente diferente que justifique otra página?»

Si no:

AGRUPAR

---

9. EVALUACIÓN INDIVIDUAL DE CADA SUBPÁGINA

Cada posible subpágina debe evaluarse antes de incorporarse a la arquitectura.

Debe poder responderse:

¿Qué busca el usuario?
¿Qué problema quiere resolver?
¿Por qué necesita una página específica?
¿Qué información diferente necesita?
¿Existe suficiente información?
¿Existe potencial comercial?
¿Podemos aportar valor?
¿Podemos diferenciarla?

Si las respuestas son débiles:

NO CREAR SUBPÁGINA

---

10. TIPOS DE PÁGINA AUTORIZADOS

La arquitectura puede utilizar, entre otros, los siguientes tipos:

service_locality
subservice_locality
service_variant
problem_intent
contact

La lista puede ampliarse mediante versionado documental.

La IA no puede inventar nuevos tipos.

---

11. SERVICE_LOCALITY

Representa el servicio principal asociado a una localidad.

Ejemplo:

/fontanero/marbella/

Datos conceptuales:

service = fontanero
municipality = Marbella
page_type = service_locality
depth = 1

Normalmente constituye la página principal de la miniweb.

---

12. SUBSERVICE_LOCALITY

Representa un subservicio con intención propia.

Ejemplo:

/fontanero/marbella/desatascos/

Datos:

service = fontanero
subservice = desatascos
municipality = Marbella
page_type = subservice_locality
depth = 2

Debe existir evidencia suficiente para justificarla.

---

13. SERVICE_VARIANT

Representa una variante del servicio con intención diferenciada.

Ejemplo:

/fontanero/marbella/24-horas/

Pero solo se autoriza cuando:

- existe intención propia;
- el servicio realmente existe;
- la disponibilidad está respaldada;
- la página aporta información específica.

No se puede crear una página "24 horas" si no existe realmente ese servicio.

---

14. PROBLEM_INTENT

Puede utilizarse cuando una necesidad concreta tenga suficiente entidad para constituir una página independiente.

Ejemplo conceptual:

/fontanero/marbella/atasco-fregadero/

Solo debe crearse cuando la intención y la información disponible lo justifiquen.

No crear páginas para cada pequeño problema.

---

15. CONTACT

La página de contacto puede formar parte de la miniweb cuando resulte útil para:

- conversión;
- navegación;
- confianza;
- información comercial.

Ejemplo:

/fontanero/marbella/contacto/

No necesita competir necesariamente por una keyword.

Su función principal es facilitar el contacto.

---

16. REGLA SOBRE CONTACTO

La existencia de una página de contacto no debe interpretarse como una obligación SEO.

Puede existir porque mejora el activo.

Puede omitirse cuando:

- no aporta utilidad;
- no existe información de contacto válida;
- la plantilla ya resuelve correctamente el contacto.

---

17. ARQUITECTURA BASE DE UNA MINIWEB

La arquitectura mínima posible es:

/fontanero/marbella/

Una arquitectura ampliada podría ser:

/fontanero/marbella/
├── desatascos/
├── 24-horas/
└── contacto/

Otra podría ser:

/fontanero/manilva/
├── desatascos/
└── contacto/

La diferencia entre ambas debe proceder de la investigación.

---

18. NO EXISTE UNA ESTRUCTURA FIJA

No todas las localidades deben tener exactamente las mismas páginas.

Esto es fundamental para evitar:

MARBELLA
↓
copiar estructura
↓
MANILVA
↓
copiar estructura
↓
ESTEPONA
↓
copiar estructura

La arquitectura debe adaptarse a cada oportunidad.

---

19. EJEMPLO

Marbella podría justificar:

/fontanero/marbella/
/fontanero/marbella/desatascos/
/fontanero/marbella/24-horas/
/fontanero/marbella/contacto/

Mientras que Manilva podría justificar:

/fontanero/manilva/
/fontanero/manilva/desatascos/
/fontanero/manilva/contacto/

Y otra localidad podría justificar solamente:

/fontanero/localidad/

Esto es correcto.

---

20. REGLA DE DIFERENCIACIÓN

Dos arquitecturas no tienen que ser iguales.

Incluso si utilizan el mismo servicio y sector.

La arquitectura puede cambiar según:

- intención;
- demanda;
- competencia;
- SERP;
- subservicios;
- necesidades;
- información local;
- potencial comercial;
- diferenciación.

---

21. PROFUNDIDAD

Cada página debe tener una profundidad definida.

Ejemplo:

Página principal
depth = 1

Subpágina
depth = 2

Se recomienda evitar estructuras innecesariamente profundas.

Ejemplo no recomendado:

/fontanero/marbella/servicios/desatascos/urgentes/24-horas/

salvo que exista una justificación excepcional.

---

22. PARENT_URL

Cada subpágina debe identificar su página padre.

Ejemplo:

{
  "url": "/fontanero/marbella/desatascos/",
  "parent_url": "/fontanero/marbella/"
}

Esto permite construir correctamente:

- breadcrumbs;
- navegación;
- jerarquía;
- enlazado interno.

---

23. PAGE_ID

Cada página debe tener un identificador estable.

Ejemplo:

FON-MARB-P01
FON-MARB-P02
FON-MARB-P03

No deben reutilizarse IDs para páginas diferentes.

---

24. URL

Las URLs deben proceder exclusivamente de la arquitectura autorizada.

Ejemplo:

/fontanero/marbella/
/fontanero/marbella/desatascos/
/fontanero/marbella/contacto/

No se permiten:

- URLs improvisadas;
- URLs creadas por la IA;
- URLs creadas por N8N;
- URLs creadas solamente por keywords.

---

25. CANONICAL

Cada página debe tener canonical definido.

Por defecto:

canonical = URL propia

Ejemplo:

URL:
/fontanero/marbella/desatascos/

Canonical:
/fontanero/marbella/desatascos/

La IA no puede modificar el canonical autorizado.

---

26. NAVEGACIÓN GLOBAL

La miniweb debe poder disponer de un menú coherente.

Ejemplo:

Inicio
Desatascos
24 horas
Contacto

Pero solo se muestran páginas autorizadas.

No se debe llenar el menú con todas las URLs existentes del proyecto.

---

27. MENÚ COMO ELEMENTO DE UX

El menú no debe diseñarse únicamente para SEO.

Debe responder:

«¿Qué necesita encontrar rápidamente un usuario que entra en esta miniweb?»

Por tanto:

- pocos elementos;
- claros;
- útiles;
- jerarquizados.

---

28. FOOTER

El footer puede incluir:

- contacto;
- navegación;
- servicios relevantes;
- información legal;
- localidades estratégicas.

No debe utilizarse para crear una red masiva de enlaces SEO.

---

29. ENLAZADO INTERNO

Las páginas de una miniweb deben estar conectadas de forma lógica.

Ejemplo:

Principal
   ↓
Desatascos
   ↓
Contacto

Y:

Principal → 24 horas
Desatascos → Principal
24 horas → Principal

Los enlaces deben existir por utilidad.

---

30. REGLA DE ENLACES

Un enlace interno debe responder:

«¿Por qué este enlace ayuda al usuario?»

Si la respuesta es:

"porque queremos pasar autoridad"

no es suficiente como justificación única.

---

31. BLOQUES POR PÁGINA

Cada página debe tener una lista de bloques autorizados.

Ejemplo:

{
  "page_id": "FON-MARB-P01",
  "authorized_blocks": [
    "B01",
    "B02",
    "B03",
    "B04",
    "B08",
    "B09",
    "B10",
    "B11",
    "B12",
    "B13",
    "B14",
    "B05",
    "B06"
  ]
}

La selección final de bloques se realizará según:

"proyecto/seo/sistema-bloques.md"

---

32. BLOQUES DE SUBPÁGINAS

Una subpágina no debe recibir automáticamente todos los bloques de la principal.

Ejemplo:

Desatascos podría utilizar:

B03
B04
B07
B08
B11
B12
B14
B05

Contacto podría utilizar:

B03
B04
B05
B06

La estructura depende de la intención.

---

33. REGLA DE OMISIÓN

Una página puede tener menos bloques que otra.

Esto es correcto.

No se debe añadir contenido únicamente para igualar el número de bloques.

---

34. MINIWEB Y DIFERENCIACIÓN

La miniweb debe funcionar como un sistema.

Cada página tiene una función distinta.

Ejemplo:

INICIO
↓
intención general

DESATASCOS
↓
intención específica

24 HORAS
↓
intención urgente

CONTACTO
↓
conversión

No:

INICIO
↓
misma información

DESATASCOS
↓
misma información

24 HORAS
↓
misma información

CONTACTO
↓
misma información

---

35. REGLA DE CONTENIDO COMPARTIDO

Puede compartirse información global cuando sea necesario.

Ejemplos:

- marca;
- navegación;
- datos de contacto;
- footer;
- información legal.

Pero el contenido principal debe responder a la intención específica de cada página.

---

36. REGLA DE INFORMACIÓN LOCAL

La información local debe utilizarse cuando realmente aporte valor.

Puede variar entre localidades:

Marbella
Manilva
Estepona
Málaga

No se debe crear automáticamente un bloque B09 para cada municipio.

---

37. REGLA DE COBERTURA

Una página de cobertura solo debe existir o mostrar zonas cuando existan datos reales.

No crear:

Todos los barrios de Marbella

si no existe evidencia de que el servicio los atienda.

---

38. REGLA DE SERVICIOS

Los servicios relacionados pueden formar parte de la navegación cuando estén autorizados.

Ejemplo:

Fontanero
Desatascos
Fontanero 24 horas

Pero cada servicio adicional debe tener justificación propia si se convierte en página.

---

39. REGLA DE ESCALABILIDAD

El sistema está diseñado para poder generar muchas miniwebs.

Pero:

ESCALABILIDAD ≠ CLONACIÓN

La estructura técnica puede repetirse.

La arquitectura funcional debe adaptarse a cada oportunidad.

---

40. REGLA DE COMPETENCIA

La arquitectura debe considerar la competencia detectada por el Motor de Decisión.

Si la página principal es muy competitiva pero existe una intención secundaria abordable:

puede ser razonable construir:

principal
+
subpágina específica

Pero nunca se debe crear una subpágina únicamente para intentar esquivar la competencia.

Debe existir una intención real.

---

41. REGLA DE MINIWEB COMPETITIVA

Una miniweb competitiva no significa tener muchas páginas.

Puede ser:

1 página excelente

o:

1 página principal
+
2 subpáginas excelentes

o:

1 página principal
+
4 subpáginas útiles

La cantidad dependerá de la oportunidad.

---

42. REGLA DE CALIDAD

Antes de autorizar una página debe poder responderse:

«¿Esta página mejora el activo?»

Si la respuesta es no:

NO CREAR

---

43. ESTRUCTURA DE DATOS

Cada página debe poder representarse conceptualmente como:

{
  "page_id": "",
  "page_type": "",
  "url": "",
  "canonical": "",
  "parent_url": null,
  "depth": 1,
  "identity": {},
  "seo": {},
  "authorized_blocks": [],
  "blocks": [],
  "internal_links": []
}

---

44. ESTRUCTURA DE LA MINIWEB

La arquitectura completa debe poder representarse como:

{
  "site_type": "local_service_site",
  "root_url": "/fontanero/marbella/",
  "pages": []
}

---

45. EJEMPLO COMPLETO

SITE
│
├── P01
│   └── /fontanero/marbella/
│
├── P02
│   └── /fontanero/marbella/desatascos/
│
├── P03
│   └── /fontanero/marbella/24-horas/
│
└── P04
    └── /fontanero/marbella/contacto/

Relaciones:

P01
├── P02
├── P03
└── P04

---

46. EJEMPLO MANILVA

Después de analizar una oportunidad como:

Fontanero + Manilva

podría determinarse:

P01
/fontanero/manilva/

P02
/fontanero/manilva/desatascos/

P03
/fontanero/manilva/contacto/

Si la investigación no justifica una página "24 horas":

no se crea.

Esto es correcto aunque Marbella sí tenga una página equivalente.

---

47. EJEMPLO MARBELLA

Para:

Fontanero + Marbella

podría determinarse:

P01
/fontanero/marbella/

P02
/fontanero/marbella/desatascos/

P03
/fontanero/marbella/24-horas/

P04
/fontanero/marbella/contacto/

Pero únicamente si cada página supera la evaluación correspondiente.

La arquitectura no debe asumir automáticamente que estas cuatro páginas son válidas.

---

48. PÁGINAS AUTORIZADAS

La arquitectura debe generar explícitamente:

authorized_pages[]

Ejemplo:

{
  "authorized_pages": [
    {
      "page_id": "FON-MARB-P01",
      "url": "/fontanero/marbella/",
      "page_type": "service_locality",
      "parent_url": null,
      "depth": 1
    },
    {
      "page_id": "FON-MARB-P02",
      "url": "/fontanero/marbella/desatascos/",
      "page_type": "subservice_locality",
      "parent_url": "/fontanero/marbella/",
      "depth": 2
    }
  ]
}

La IA solo podrá trabajar con estas páginas.

---

49. ESTADO DE LAS PÁGINAS

Cada página puede tener:

AUTHORIZED
REVIEW
OMITTED

AUTHORIZED

Puede pasar a generación.

REVIEW

Existe una duda que debe resolverse antes de generar.

OMITTED

La oportunidad fue analizada pero no justifica una página independiente.

---

50. REGLA DE SEGURIDAD

Si existe una contradicción entre:

- motor;
- arquitectura;
- datos;
- bloques;

debe prevalecer la capa superior.

Orden:

MOTOR
↓
ARQUITECTURA
↓
DATOS
↓
BLOQUES
↓
IA

La IA nunca puede resolver unilateralmente una contradicción modificando la arquitectura.

---

51. RELACIÓN CON EL CONTRATO IA

La arquitectura proporciona al contrato IA:

- páginas autorizadas;
- IDs;
- URLs;
- canonicals;
- parent_url;
- depth;
- tipos de página;
- bloques autorizados;
- relaciones.

La IA proporciona:

- contenido;
- datos de bloques;
- SEO;
- navegación concreta dentro de los límites;
- enlaces internos autorizados.

---

52. RELACIÓN CON N8N

N8N debe recibir una arquitectura ya validada.

Debe utilizarla para:

- crear páginas;
- actualizar páginas;
- mantener URLs;
- construir relaciones;
- construir menús;
- evitar duplicados.

N8N no debe crear páginas que no estén en:

authorized_pages[]

---

53. IDEMPOTENCIA

Cada página debe tener un identificador estable.

Ejemplo:

FON-MARB-P01

Si N8N procesa nuevamente la misma arquitectura:

PÁGINA EXISTE
↓
ACTUALIZAR

Si no existe:

CREAR

Nunca:

CREAR DUPLICADO

---

54. VALIDACIÓN

Antes de pasar la arquitectura al contrato IA se debe comprobar:

- decisión = CREAR;
- site_type válido;
- root_url válida;
- páginas autorizadas;
- page_id único;
- URLs únicas;
- canonical válido;
- parent_url válido;
- depth coherente;
- page_type válido;
- bloques autorizados;
- enlaces autorizados;
- ausencia de páginas innecesarias;
- ausencia de duplicación evidente.

Si falla una condición crítica:

REVIEW

---

55. PRINCIPIO DE NO INVENCIÓN

La arquitectura nunca debe inventar:

- servicios;
- subservicios;
- cobertura;
- páginas;
- URLs;
- empresas;
- profesionales;
- teléfonos;
- precios;
- horarios;
- datos comerciales.

La arquitectura trabaja con oportunidades y evidencias ya investigadas.

---

56. PRINCIPIO DE APRENDIZAJE

La arquitectura debe poder evolucionar cuando las pruebas reales demuestren que una estructura:

- no aporta valor;
- genera contenido repetitivo;
- dificulta la conversión;
- no responde a la intención;
- produce miniwebs demasiado grandes;
- produce miniwebs demasiado pobres;
- genera problemas técnicos.

Cuando se detecte:

1. registrar el caso;
2. analizarlo;
3. modificar la regla;
4. aumentar versión;
5. repetir las pruebas afectadas.

---

57. PRINCIPIO DE NEGOCIO

La arquitectura debe tener en cuenta que el producto final no es únicamente una página SEO.

El activo puede convertirse en:

- landing alquilable;
- miniweb alquilable;
- fuente de leads;
- activo digital;
- página comercial para un profesional.

Por tanto, una arquitectura útil debe permitir:

SEO
+
UX
+
CONVERSIÓN
+
ALQUILER

sin sacrificar la calidad SEO.

---

58. REGLA DE MINIWEB ALQUILABLE

Una miniweb destinada potencialmente a alquiler debe parecer y funcionar como un activo web real.

Debe poder disponer de:

- navegación;
- página principal;
- páginas de servicios relevantes;
- contacto;
- estructura coherente;
- enlazado interno;
- identidad visual;
- CTA.

No debe parecer:

una colección de páginas SEO independientes.

Debe parecer:

un pequeño sitio profesional especializado.

---

59. SEPARACIÓN ENTRE SEO Y PRODUCTO

Una página puede existir por SEO.

Pero la miniweb debe además funcionar como producto.

Por tanto:

SEO
↓
determina oportunidades e intenciones

ARQUITECTURA
↓
organiza el activo

UX
↓
organiza la experiencia

CONVERSIÓN
↓
facilita el contacto

ALQUILER
↓
convierte el activo en producto comercial

---

60. PRINCIPIO FINAL

El Motor de Decisión responde:

«¿Merece la pena construir?»

La Arquitectura responde:

«¿Qué páginas necesita realmente este activo?»

El Sistema de Bloques responde:

«¿Qué componentes lógicos necesita cada página?»

El Contrato IA responde:

«¿Cómo devuelve la IA la información?»

N8N responde:

«¿Cómo se crea y sincroniza?»

WordPress responde:

«¿Cómo se renderiza?»

La arquitectura debe impedir que:

KEYWORD
↓
PÁGINAS MASIVAS
↓
CONTENIDO CLÓNICO

sustituya a:

INTENCIÓN
↓
EVIDENCIA
↓
ARQUITECTURA
↓
PÁGINAS ÚTILES
↓
MINIWEB COHERENTE

---

61. ESTADO DEL DOCUMENTO

Versión: 3.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha: 2026-08-24

Cambios principales:

- adaptación completa de landing individual a miniweb;
- incorporación formal de subpáginas;
- evaluación individual de subpáginas;
- arquitectura variable según oportunidad;
- separación entre página principal y páginas secundarias;
- incorporación de page_id;
- incorporación de parent_url;
- incorporación de depth;
- incorporación de page_type;
- incorporación de authorized_pages;
- incorporación de estados de página;
- refuerzo de navegación;
- refuerzo de enlazado interno;
- protección contra creación masiva de subpáginas;
- adaptación a activos potencialmente alquilables;
- separación entre SEO y producto;
- refuerzo de diferenciación entre localidades;
- integración con Sistema de Bloques;
- integración con Contrato IA;
- integración con N8N;
- refuerzo de idempotencia;
- refuerzo de validación.

---

FIN DE ARQUITECTURA DE LANDING / MINIWEB SEO LOCAL
