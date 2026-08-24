ARQUITECTURA DE LANDING SEO

Versión: 4.0
Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO
Función: determinar la arquitectura óptima de páginas, URLs, navegación y bloques para cada oportunidad SEO local.

---

1. FUNCIÓN

Este documento define cómo transformar una oportunidad SEO previamente investigada y aprobada en una arquitectura web coherente.

La arquitectura determina:

- qué páginas pueden existir;
- qué URLs pueden existir;
- qué páginas dependen de otras;
- qué profundidad tiene cada página;
- qué intenciones cubre cada página;
- qué subservicios merecen página propia;
- qué páginas deben agruparse;
- qué páginas deben descartarse;
- qué bloques puede utilizar cada página;
- cómo se relacionan las páginas entre sí;
- cómo se construye la navegación.

La arquitectura no genera contenido.

La arquitectura no publica páginas.

La arquitectura no inventa datos comerciales.

La arquitectura no decide libremente qué oportunidades existen.

---

2. CAMBIO FUNDAMENTAL DE LA VERSIÓN 4.0

La versión 4.0 elimina cualquier número predeterminado de páginas.

No existe:

- número mínimo de páginas;
- número máximo de páginas por defecto;
- plantilla fija de 5 páginas;
- plantilla fija de 3 subservicios;
- estructura obligatoria de servicios;
- obligación de crear una página de contacto;
- obligación de crear una página de presupuesto.

El número final de páginas será el resultado de la investigación y evaluación de las distintas intenciones.

Una miniweb puede tener:

- 1 página;
- 2 páginas;
- 5 páginas;
- 8 páginas;
- 12 páginas;
- 20 páginas;

o cualquier otro número que esté justificado.

---

3. NUEVO PRINCIPIO DE ARQUITECTURA

El sistema utilizará una estrategia de:

DESCUBRIMIENTO AMPLIO + PODA INTELIGENTE

Flujo:

INVESTIGACIÓN
↓
DESCUBRIR INTENCIONES
↓
DESCUBRIR SUBSERVICIOS
↓
DESCUBRIR VARIANTES
↓
DESCUBRIR NECESIDADES
↓
DESCUBRIR POSIBLES PÁGINAS
↓
EVALUAR CADA OPORTUNIDAD
↓
AGRUPAR CUANDO PROCEDA
↓
DESCARTAR CUANDO PROCEDA
↓
ARQUITECTURA FINAL
↓
SISTEMA DE BLOQUES
↓
CONTRATO IA
↓
VALIDACIÓN
↓
N8N
↓
WORDPRESS

La arquitectura final debe ser el resultado de la poda de un universo inicial de posibilidades.

---

4. REGLA DE DESCUBRIMIENTO AMPLIO

Durante la fase de investigación se deben descubrir tantas intenciones relevantes como sea razonablemente posible.

Pueden aparecer:

- servicio principal;
- subservicios;
- variantes del servicio;
- problemas;
- necesidades;
- urgencias;
- servicios específicos;
- servicios complementarios;
- tipos de cliente;
- contextos de uso;
- búsquedas relacionadas;
- intenciones transaccionales;
- intenciones informativas con valor comercial;
- páginas funcionales;
- oportunidades locales específicas.

El sistema no debe limitar artificialmente el descubrimiento para conseguir una web pequeña.

---

5. REGLA DE TODAS LAS POSIBILIDADES

Cuando la investigación identifique posibles páginas relevantes, inicialmente deben entrar en el conjunto de candidatos.

Ejemplo:

FONTANERO + FUENGIROLA

Puede descubrir:

- fontanero;
- desatascos;
- desatascos urgentes;
- fontanero urgente;
- fontanero 24 horas;
- fugas de agua;
- reparación de fugas;
- reparación de tuberías;
- instalación de termos;
- reparación de termos;
- reparación de cisternas;
- grifos;
- sanitarios;
- presupuestos;
- contacto;
- etc.

El descubrimiento de estas posibilidades no significa que todas vayan a convertirse en URLs finales.

Significa que todas deben poder ser evaluadas.

---

6. UNIVERSO DE CANDIDATOS

La arquitectura debe distinguir entre:

CANDIDATE_PAGES

y:

AUTHORIZED_PAGES

CANDIDATE_PAGES:

conjunto amplio de páginas potencialmente válidas detectadas durante la investigación.

AUTHORIZED_PAGES:

conjunto final de páginas que han superado la evaluación y pueden pasar a generación.

Flujo:

CANDIDATE_PAGES
↓
EVALUACIÓN
↓
AGRUPACIÓN
↓
DESCARTE
↓
AUTHORIZED_PAGES

---

7. NÚMERO DE PÁGINAS

El número de páginas no debe fijarse antes de la investigación.

Nunca debe existir una regla como:

"crear exactamente 5 páginas".

Tampoco:

"crear siempre 3 subservicios".

Tampoco:

"crear siempre una página de contacto".

Tampoco:

"crear siempre una página de presupuesto".

El sistema debe permitir que la investigación determine el tamaño real de la arquitectura.

---

8. EJEMPLO DE ARQUITECTURA PEQUEÑA

Una localidad con poca oportunidad puede terminar en:

/fontanero/pueblo/

Una sola página puede ser suficiente si no existen intenciones independientes suficientemente fuertes.

---

9. EJEMPLO DE ARQUITECTURA MEDIA

Otra localidad puede terminar en:

/fontanero/ciudad/

/fontanero/ciudad/desatascos/
/fontanero/ciudad/fugas-de-agua/
/fontanero/ciudad/24-horas/
/fontanero/ciudad/termos/
/fontanero/ciudad/contacto/

---

10. EJEMPLO DE ARQUITECTURA AMPLIA

Una localidad con muchas oportunidades puede terminar en:

/fontanero/ciudad/

/fontanero/ciudad/desatascos/
/fontanero/ciudad/desatascos-urgentes/
/fontanero/ciudad/fontanero-urgente/
/fontanero/ciudad/24-horas/
/fontanero/ciudad/fugas-de-agua/
/fontanero/ciudad/reparacion-de-tuberias/
/fontanero/ciudad/reparacion-de-termos/
/fontanero/ciudad/instalacion-de-termos/
/fontanero/ciudad/reparacion-de-cisternas/
/fontanero/ciudad/reparacion-de-grifos/
/fontanero/ciudad/presupuesto/
/fontanero/ciudad/contacto/

Solo se mantendrán aquellas que superen la evaluación.

---

11. DESCUBRIMIENTO NO EQUIVALE A CREACIÓN

La regla fundamental es:

DESCUBRIR TODO LO RAZONABLE

pero:

CREAR SOLO LO JUSTIFICADO

Por tanto:

CANDIDATO ≠ URL AUTORIZADA

y:

URL AUTORIZADA ≠ PUBLICACIÓN AUTOMÁTICA

La publicación requiere superar todas las capas posteriores.

---

12. EVALUACIÓN DE CADA CANDIDATO

Cada candidato debe evaluarse individualmente.

Como mínimo:

- intención;
- demanda;
- potencial comercial;
- relevancia local;
- competencia;
- calidad SERP;
- fortaleza de competidores;
- diferenciación;
- información disponible;
- riesgo de duplicación;
- utilidad para el usuario;
- relación con otras páginas;
- posibilidad de agrupación;
- coste/complejidad;
- coherencia con el modelo de negocio.

---

13. RESULTADOS DE LA EVALUACIÓN

Cada candidato puede terminar como:

KEEP

GROUP

DROP

RESEARCH

KEEP:

se mantiene como página independiente.

GROUP:

se agrupa con otra intención en una página existente.

DROP:

se descarta.

RESEARCH:

requiere más investigación antes de decidir.

---

14. REGLA DE AGRUPACIÓN

No todas las keywords o variaciones necesitan páginas independientes.

Ejemplo:

- fontanero Fuengirola;
- fontaneros Fuengirola;
- fontanería Fuengirola;
- servicio de fontanería Fuengirola.

Si representan la misma intención:

se agrupan.

Una página puede cubrir todas esas variantes.

---

15. REGLA DE NO AGRUPAR INTENCIONES DIFERENTES

No se deben agrupar automáticamente dos búsquedas diferentes.

Ejemplo:

"fontanero Fuengirola"

y:

"desatascos Fuengirola"

pueden requerir páginas diferentes si la investigación demuestra intenciones distintas.

La decisión debe basarse en la intención real, no solamente en similitud lingüística.

---

16. REGLA DE SUBSERVICIOS

Todo subservicio relevante descubierto durante la investigación debe entrar inicialmente en el conjunto de candidatos.

Ejemplo:

FONTANERO

Puede producir candidatos como:

- desatascos;
- fugas;
- termos;
- tuberías;
- cisternas;
- grifos;
- sanitarios;
- instalaciones;
- reparaciones.

Posteriormente se evaluará cada uno.

---

17. REGLA DE SUBSERVICIOS ESPECÍFICOS

También deben poder descubrirse niveles adicionales.

Ejemplo:

/desatascos/
    ↓
/desatascos-urgentes/

o:

/termos/
    ↓
/reparacion-de-termos/
/instalacion-de-termos/

No existe un límite artificial de profundidad.

La profundidad debe depender de:

- intención;
- arquitectura;
- utilidad;
- demanda;
- diferenciación;
- relación jerárquica.

---

18. REGLA DE PROFUNDIDAD

La profundidad no se determina por una plantilla.

Debe existir una relación lógica:

Página principal
↓
Servicio
↓
Subservicio
↓
Intención específica

Solo se profundiza cuando existe una razón real.

No crear profundidad únicamente para aumentar URLs.

---

19. REGLA DE PÁGINAS FUNCIONALES

Pueden existir páginas funcionales como:

- contacto;
- presupuesto;
- solicitud de servicio;
- cita;
- información comercial.

Pero no deben convertirse automáticamente en páginas SEO.

Debe distinguirse entre:

PÁGINA SEO

y:

PÁGINA FUNCIONAL

Una página de presupuesto puede existir por conversión aunque no tenga una intención SEO independiente.

---

20. CONTACTO

La página de contacto no debe ser obligatoria por sistema.

Puede crearse cuando:

- mejora la experiencia;
- forma parte de la arquitectura;
- existe información suficiente;
- es útil para la conversión;
- el modelo de negocio lo requiere.

No debe existir simplemente para completar un número predeterminado de páginas.

---

21. PRESUPUESTO

La página:

/presupuesto/

solo se crea cuando:

- existe una función comercial real;
- aporta valor;
- existe una razón para separarla;
- la arquitectura la contempla.

Si únicamente necesitamos un botón:

"Solicitar presupuesto"

no es necesario crear una página SEO independiente.

---

22. REGLA DE BLOQUES

La arquitectura debe comenzar con un conjunto amplio de bloques candidatos.

La IA y el sistema de bloques no deben estar condicionados a utilizar únicamente 5 o 6 bloques.

Para cada página se pueden considerar todos los bloques autorizados:

B01–B23.

Después se evalúa cuáles deben mantenerse.

---

23. DESCUBRIMIENTO AMPLIO DE BLOQUES

Por defecto, una página debe poder considerar todos los bloques compatibles con su tipo.

Ejemplo:

B01
B02
B03
B04
B05
B06
B07
B08
B09
B10
B11
B12
B13
B14
B15
B16
B17
B18
B19
B20
B21
B22
B23

Esto es un conjunto de candidatos, no una obligación de publicar los 23.

---

24. PODA DE BLOQUES

Cada bloque debe evaluarse.

Se conserva cuando:

- aporta valor;
- existen datos;
- corresponde a la intención;
- mejora la experiencia;
- existe información suficiente;
- no genera contenido artificial.

Se descarta cuando:

- no aporta valor;
- no existen datos;
- obligaría a inventar;
- produce contenido repetitivo;
- no corresponde a la página;
- no es necesario.

---

25. REGLA DE BLOQUES POR DEFECTO

El sistema no debe comenzar preguntando:

"¿Qué pocos bloques necesitamos?"

Debe comenzar preguntando:

"¿Qué bloques podrían aportar valor a esta página?"

Después:

"¿Cuáles deben eliminarse?"

La secuencia será:

TODOS LOS BLOQUES COMPATIBLES
↓
EVALUACIÓN
↓
DESCARTE
↓
BLOQUES FINALES

---

26. DIFERENCIACIÓN ENTRE PÁGINAS

Dos páginas pueden comenzar con los mismos bloques candidatos.

Pero después de la evaluación pueden terminar con estructuras diferentes.

Ejemplo:

Home:

B03 + B04 + B09 + B10 + B11 + B12 + B13 + B14 + B05

Desatascos:

B03 + B04 + B07 + B08 + B11 + B13 + B14 + B05

Presupuesto:

B03 + B04 + B05

Contacto:

B03 + B04 + B05

No existe obligación de que todas las páginas tengan la misma cantidad de bloques.

---

27. REGLA DE NO RELLENO

La estrategia de descubrimiento amplio no autoriza el relleno.

No se debe crear un bloque simplemente porque está disponible.

No se debe crear una página simplemente porque puede crearse.

No se debe crear una URL simplemente porque existe una keyword.

No se debe crear contenido simplemente porque existe un hueco.

---

28. REGLA DE CALIDAD

La arquitectura óptima no es:

"la que tiene más páginas".

Tampoco es:

"la que tiene menos páginas".

Es:

la que cubre el mayor número de intenciones relevantes con el menor nivel posible de duplicación y contenido artificial.

---

29. OBJETIVO DE COBERTURA

El sistema debe intentar maximizar:

COBERTURA DE INTENCIONES ÚTILES

y minimizar:

- duplicación;
- thin content;
- páginas innecesarias;
- canibalización;
- URLs artificiales;
- contenido inventado.

---

30. MODELO DE PODA

Conceptualmente:

UNIVERSO DE OPORTUNIDADES
        ↓
CANDIDATOS
        ↓
┌───────────────────────────┐
│ Evaluación individual     │
├───────────────────────────┤
│ KEEP                      │
│ GROUP                     │
│ RESEARCH                  │
│ DROP                      │
└───────────────────────────┘
        ↓
ARQUITECTURA FINAL

---

31. REGLA CONTRA EL MOLDE DE CINCO PÁGINAS

Queda expresamente prohibido utilizar como patrón:

HOME
+
3 SERVICIOS
+
CONTACTO

como arquitectura predeterminada.

Este patrón puede aparecer como resultado de una investigación.

Pero nunca puede ser impuesto por el sistema.

---

32. REGLA CONTRA EL MOLDE DE TRES SERVICIOS

No existe una cantidad predeterminada de servicios.

Puede haber:

- 0;
- 1;
- 2;
- 3;
- 5;
- 8;
- 15;

según las oportunidades descubiertas y validadas.

---

33. REGLA CONTRA EL MOLDE DE CONTACTO

Contacto no es una página obligatoria.

Puede existir:

CTA → formulario

sin:

/contacto/

O puede existir una página de contacto cuando aporte valor.

---

34. REGLA CONTRA EL MOLDE DE PRESUPUESTO

Presupuesto no es una página obligatoria.

Puede ser:

CTA → formulario

o:

CTA → WhatsApp

o:

/presupuesto/

según la arquitectura.

---

35. REGLA DE LOCALIDAD

Cada localidad debe tener una arquitectura propia.

No se debe copiar automáticamente:

Fuengirola
↓
misma arquitectura que Marbella

La investigación de Fuengirola determina su arquitectura.

La investigación de Marbella determina otra.

La investigación de Casares determina otra.

La arquitectura puede coincidir parcialmente, pero no se presupone que sea idéntica.

---

36. REGLA DE ESCALABILIDAD

El sistema debe poder procesar miles de localidades sin imponer una arquitectura uniforme.

Ejemplo:

Pueblo A → 1 página
Pueblo B → 4 páginas
Pueblo C → 9 páginas
Ciudad D → 18 páginas
Ciudad E → 27 páginas

Todos son resultados válidos.

---

37. REGLA DE APRENDIZAJE

Cuando una localidad demuestre que determinados tipos de páginas:

- funcionan;
- no aportan;
- generan duplicación;
- tienen buena demanda;
- tienen mala competencia;

esa información puede utilizarse para mejorar futuras investigaciones.

Pero nunca debe convertirse automáticamente en una regla rígida.

---

38. RELACIÓN CON MOTOR DE DECISIÓN

El motor de decisión determina si existe una oportunidad.

La arquitectura amplía el análisis para determinar:

qué páginas podrían cubrir esa oportunidad.

Flujo:

MOTOR
↓
CREAR
↓
DESCUBRIMIENTO AMPLIO
↓
CANDIDATOS
↓
EVALUACIÓN
↓
PODA
↓
ARQUITECTURA FINAL

---

39. RELACIÓN CON SISTEMA DE BLOQUES

El sistema de bloques define qué bloques existen.

La arquitectura determina qué bloques son candidatos para cada página.

Después se realiza la poda.

Flujo:

B01–B23
↓
BLOQUES COMPATIBLES
↓
EVALUACIÓN
↓
BLOQUES FINALES

---

40. RELACIÓN CON CONTRATO IA

La IA recibe únicamente:

- páginas autorizadas;
- URLs autorizadas;
- bloques autorizados;
- datos disponibles;
- restricciones.

La IA no puede volver a ampliar la arquitectura.

La ampliación ocurre antes de la IA.

---

41. RELACIÓN CON N8N

N8N procesa únicamente la arquitectura final autorizada.

No debe crear páginas adicionales.

No debe interpretar keywords para crear URLs.

No debe añadir subservicios por iniciativa propia.

Su función es ejecutar la arquitectura aprobada.

---

42. RELACIÓN CON WORDPRESS

WordPress recibe la arquitectura final y los datos correspondientes.

Debe poder:

- crear páginas;
- actualizar páginas;
- crear relaciones;
- construir navegación;
- renderizar bloques;
- activar/desactivar elementos comerciales.

No decide qué URLs existen.

---

43. PREALQUILER

Una web puede construirse antes de disponer de cliente.

En ese caso:

SITE_STATUS = PREALQUILER

La arquitectura SEO puede estar completamente construida.

Los datos comerciales inexistentes deben permanecer:

null

o:

unconfigured

No se deben inventar datos empresariales.

---

44. CAPA SEO Y CAPA NEGOCIO

La arquitectura debe distinguir:

CAPA SEO

- servicio;
- localidad;
- intención;
- subservicio;
- información útil;
- navegación;
- FAQ;
- contenido local respaldado.

CAPA NEGOCIO

- empresa;
- logo;
- teléfono;
- WhatsApp;
- email;
- horarios;
- precios;
- cobertura;
- reseñas;
- testimonios;
- imágenes propias;
- certificaciones;
- garantías.

La capa negocio puede estar vacía durante el prealquiler.

---

45. REGLA DE PREALQUILER

La ausencia de datos comerciales no debe impedir construir una arquitectura SEO válida.

Pero sí debe impedir afirmar datos comerciales inexistentes.

Ejemplo válido:

/fontanero/fuengirola/desatascos/

Ejemplo no válido:

"Desatascos realizados por Empresa X desde 2008"

si todavía no existe Empresa X.

---

46. VALIDACIÓN DE ARQUITECTURA

Antes de pasar a IA deben comprobarse:

- URLs únicas;
- intención definida;
- ausencia de duplicación innecesaria;
- parent_url correcto;
- profundidad correcta;
- páginas agrupadas correctamente;
- candidatos descartados correctamente;
- páginas funcionales diferenciadas de páginas SEO;
- bloques compatibles;
- navegación coherente;
- ausencia de páginas creadas por plantilla;
- ausencia de número predeterminado de páginas.

---

47. CRITERIO DE FINALIZACIÓN

La arquitectura está terminada cuando:

no existen candidatos relevantes sin evaluar

y:

no existen páginas autorizadas cuya existencia no esté justificada.

No se considera terminada simplemente porque tenga cinco páginas.

---

48. EJEMPLO DE RESULTADO VARIABLE

Para una oportunidad:

FONTANERO + FUENGIROLA

el sistema podría descubrir inicialmente:

20 candidatos

Después de evaluar:

8 KEEP
5 GROUP
4 DROP
3 RESEARCH

Tras resolver la investigación:

10 páginas autorizadas

Otra localidad podría terminar con:

3 páginas

Y otra:

15 páginas

---

49. PRINCIPIO DE OPTIMIZACIÓN

La arquitectura debe buscar un equilibrio entre:

COBERTURA

y:

CALIDAD

No se debe maximizar simplemente el número de URLs.

La función conceptual es:

VALOR ARQUITECTÓNICO
=
COBERTURA DE INTENCIONES
+
UTILIDAD
+
DIFERENCIACIÓN
+
POTENCIAL COMERCIAL
-
DUPLICACIÓN
-
THIN CONTENT
-
COMPLEJIDAD INNECESARIA

---

50. REGLA FINAL DE PODA

El sistema parte de una visión amplia.

Después elimina.

Nunca debe partir de una web pequeña y añadir páginas únicamente porque falten.

Por tanto:

MEJOR DESCUBRIR 20 POSIBILIDADES Y DESCARTAR 12

que:

CREAR 5 PÁGINAS POR DEFECTO Y NO DESCUBRIR 15 OPORTUNIDADES REALES.

---

51. PRINCIPIO FINAL

La pregunta de la arquitectura no es:

"¿Cuántas páginas debemos crear?"

Es:

"¿Qué conjunto de páginas cubre de forma óptima las intenciones relevantes de esta oportunidad?"

El resultado puede tener cualquier tamaño.

---

52. ESTADO DEL DOCUMENTO

Versión: 4.0

Estado: PREPARADO PARA IMPLEMENTACIÓN PILOTO

Fecha: 2026-08-24

Cambios principales:

- eliminación del patrón predeterminado de cinco páginas;
- eliminación del patrón predeterminado de tres subservicios;
- eliminación de la obligatoriedad de contacto;
- eliminación de la obligatoriedad de presupuesto;
- incorporación de descubrimiento amplio;
- incorporación de CANDIDATE_PAGES;
- incorporación de AUTHORIZED_PAGES;
- incorporación de KEEP / GROUP / DROP / RESEARCH;
- incorporación de poda arquitectónica;
- incorporación de descubrimiento amplio de subservicios;
- incorporación de descubrimiento amplio de bloques;
- separación entre descubrimiento y autorización;
- arquitectura variable por localidad;
- arquitectura variable por oportunidad;
- separación entre páginas SEO y páginas funcionales;
- incorporación formal del modelo PREALQUILER;
- separación entre capa SEO y capa negocio;
- refuerzo contra arquitecturas clónicas;
- refuerzo contra generación masiva artificial;
- mantenimiento de la diferenciación como criterio central.

---

FIN DE ARQUITECTURA DE LANDING SEO
