---
tags: [clase, continuidad-del-negocio, semana6, riesgos]
fuente: SEM 6/SESION 1 (PDF S06_s11 completo, texto + diapositivas gráficas)
---
# S06-1 · Evaluación de amenazas y análisis de riesgo
Ejercicios: [[EJ_S06_Riesgos]]

## Logro y gancho
Identificar amenazas y vulnerabilidades asociadas a los activos críticos y analizar su nivel de riesgo considerando probabilidad e impacto, en el contexto de la continuidad.
Gancho: ya sabemos las actividades críticas y cuánto tiempo podemos estar detenidos antes de un impacto inaceptable; ¿qué situaciones o eventos, externos o internos, podrían provocar la interrupción de esas actividades?
**Importancia**: tras el BIA conviene analizar las amenazas y vulnerabilidades que podrían afectar los procesos y recursos críticos, para anticipar interrupciones, determinar qué riesgos requieren mayor atención y decidir cómo proteger la continuidad.
Contenido: introducción · concepto de amenaza · clasificación de amenaza · análisis de riesgo y elementos clave.

## 1. Introducción
Una vez identificadas las funciones/procesos críticos y evaluado el impacto de su interrupción (BIA), toca preguntarse **¿qué puede poner en peligro esos procesos y activos?** La **evaluación de amenazas** es una actividad fundamental dentro del **análisis de riesgo**. Objetivos de la sesión: (1) identificar las amenazas internas y externas; (2) comprender la relación entre amenaza, vulnerabilidad, activo crítico e impacto; (3) analizar la probabilidad y el impacto para determinar el nivel de riesgo.

## 2. Amenaza e incidente disruptivo
- **Amenaza**: cualquier evento o condición **potencial** que podría causar un impacto negativo en la organización (dañar los activos, interrumpir operaciones o afectar negativamente la reputación). **Características**: es **posible**, puede ocurrir; se **identifica y analiza antes** de que provoque una interrupción; puede tener origen natural, tecnológico, humano o externo. *Ejemplos*: corte prolongado de energía eléctrica en la ciudad; ataque cibernético contra la red corporativa; terremoto en la zona donde está la empresa.
- **Incidente disruptivo**: evento **que se ha materializado** y provoca una interrupción o alteración significativa de las operaciones normales. **Características**: es un evento ocurrido; afecta las operaciones; puede requerir la activación de procedimientos o planes de respuesta y recuperación. *Ejemplos*: el apagón eléctrico que efectivamente detuvo los servidores; el ataque de ransomware que encriptó la información; el terremoto ocurrido que dañó las oficinas principales.
- **Amenaza vs incidente disruptivo**: Amenaza = *puede ocurrir; es potencial; se analiza anticipadamente*. → si se materializa y provoca una interrupción significativa → Incidente disruptivo = *ha ocurrido; afecta las operaciones; requiere respuesta y, según su gravedad, recuperación*.
- **Ejemplo: apagón en el centro de datos**: (1) *Antes del evento*: existe la posibilidad de un apagón prolongado que afecte el centro de datos → **amenaza** (evento potencial). (2) *El evento ocurre pero no hay interrupción significativa*: se produce el apagón pero el UPS y el generador funcionan, los servidores siguen operativos → la amenaza se materializa pero **no hay incidente disruptivo de continuidad**. (3) *El evento genera una interrupción*: ocurre el apagón, falla el generador, los servidores se detienen y el procesamiento de pagos queda indisponible → **incidente disruptivo**. **No toda amenaza que ocurre genera necesariamente un incidente disruptivo**: solo si provoca una interrupción significativa de las operaciones.

## 3. Tipos de amenazas (dos criterios)
**1. Según la fuente o causa que las origina**
| Tipo | Descripción | Ejemplos |
|---|---|---|
| **Naturales** | Fenómenos de la naturaleza | terremotos, inundaciones, tormentas, incendios forestales, erupciones volcánicas |
| **Humanas** | Acciones o errores de las personas (intencionales o no) | sabotaje, terrorismo, fraude, errores humanos, huelgas |
| **Tecnológicas** | Fallas o eventos de tecnología e infraestructura | malware/ransomware, denegación de servicio (DDoS), fallas de hardware (servidor, disco duro), phishing y robo de credenciales, fallas en sistemas o aplicaciones, interrupciones de servicios tecnológicos |
| **Sociales o sanitarias** | Eventos del entorno social o de salud pública | pandemias, conflictos sociales, inestabilidad política, paros o protestas, emergencias de salud pública |
**2. Según su procedencia respecto de la organización**
- **Internas**: se originan **dentro** de la organización (error humano, configuración incorrecta, falla de infraestructura interna: servidores, equipos, red; sabotaje de un empleado; uso inadecuado de recursos).
- **Externas**: provienen del **entorno externo** (sismo; inundaciones o tormentas; ataque de un ciberdelincuente externo; corte del suministro eléctrico por parte del proveedor; indisponibilidad de un proveedor Cloud/SaaS; conflictos sociales y huelgas externas).
- **Una misma amenaza puede clasificarse simultáneamente según la fuente/causa y según su procedencia.**
**Ejercicio de clase: clasificar según procedencia**
| # | Amenaza | Tipo |
|---|---|---|
| 1 | Falla del servidor o de un componente de hardware crítico de la organización | **Interna** |
| 2 | Error en la configuración de un firewall o de un sistema de red | **Interna** |
| 3 | Ataque de inyección SQL dirigido contra la aplicación web pública que compromete la BD de clientes | **Externa** |
| 4 | Robo de un equipo corporativo con información confidencial | **Externa** |
| 5 | Sabotaje realizado por un empleado descontento | **Interna** |
| 6 | Corte prolongado del suministro eléctrico que afecta el centro de datos | **Externa** |
| 7 | Indisponibilidad de un servicio crítico de nube/SaaS contratado por la organización | **Externa** |
| 8 | Renuncia masiva o pérdida de personal clave | **Interna** |
| 9 | Malware que ingresa mediante un correo de phishing | **Externa** |
| 10 | Ataque de denegación de servicio (DDoS) contra los servicios web de la organización | **Externa** |
| 11 | Fraude mediante deepfake para suplantar a un directivo y solicitar una transferencia bancaria | **Externa** |
(Las marcadas 4, 6 y 7 en la diapositiva se resaltaron en rojo; la clasificación de las filas 7, 10 y 11 no figuraba en el texto original: ⚠️ REVISAR con el docente si se pide justificar casos límite, p. ej. el robo de equipo o el phishing que explotan una vulnerabilidad interna.)

## 4. Riesgo y análisis de riesgo
- **Riesgo**: la **posibilidad** de que ocurra un evento no deseado (**amenaza**) que afecte negativamente (**impacto**) a un **activo crítico**, debido a una **vulnerabilidad** existente. *Mini-ejercicio:* "La empresa no tiene un sistema potente de seguridad" = vulnerabilidad; "¿qué va a ocasionar un malware o ransomware?" = amenaza; "va a impactar negativamente sobre el activo crítico" = impacto.
- **Elementos de un escenario de riesgo**: **Amenaza** —(puede aprovechar)→ **Vulnerabilidad** —(afecta a)→ **Activo o proceso crítico** —(genera)→ **Impacto**. *No es una fórmula matemática, sino una relación lógica que ayuda a analizar el riesgo.*
  1. **Amenaza**: evento o condición potencial que puede afectar negativamente activos, procesos u operaciones. Características: es potencial; puede tener diferentes fuentes o causas; puede afectar activos o procesos críticos; se identifica anticipadamente. Ejemplos: sismo, ataque de ransomware, error humano, corte prolongado del suministro eléctrico. *Identificar las amenazas permite anticipar posibles interrupciones y tomar medidas para proteger la continuidad.*
  2. **Vulnerabilidad**: **debilidad o condición** presente en un activo, proceso, sistema o entorno que puede **facilitar que una amenaza cause daño** o aumente sus consecuencias. Características: representa una debilidad o condición de exposición; puede facilitar que una amenaza afecte a la organización; puede aumentar las consecuencias del evento; puede ser tecnológica, organizacional o física. Ejemplos: servidor sin parches de seguridad; edificio sin adecuada protección antisísmica; personal sin capacitación para responder ante incidentes. *Identificar y gestionar las vulnerabilidades permite reducir la probabilidad de afectación y fortalece la resiliencia.*
     - **Tipos**: **Tecnológicas** (hardware y software): software desactualizado, falta de redundancia, configuraciones inseguras o por defecto. **Organizacionales** (procesos, gestión, personas): falta de políticas de respaldo, ausencia de capacitación, dependencia de una sola persona para una actividad crítica. **Físicas** (instalaciones y entorno): ubicación expuesta a amenazas naturales, falta de controles de acceso físico, ausencia de sistemas de detección o protección contra incendios.
  3. **Activo crítico**: recurso, información, sistema, instalación o capacidad **necesaria para la operación de procesos importantes del negocio**, cuya pérdida, indisponibilidad o afectación podría generar consecuencias significativas. *Tipos*: **Físicos** (edificios e instalaciones, servidores y equipos de cómputo, equipos de red y telecomunicaciones, mobiliario y equipamiento, documentos físicos) · **Tecnológicos o digitales** (aplicaciones ERP/CRM/sistemas de negocio, sistemas operativos, plataformas en la nube, software de seguridad, herramientas de gestión) · **De información** (bases de datos de clientes, información financiera, información de operaciones, registros y expedientes digitales, propiedad intelectual documentada) · **Humanos y conocimiento** (personal clave y especializado, conocimiento técnico crítico/know-how, experiencia institucional, capacidades críticas para la operación) · **Otros intangibles** (reputación e imagen corporativa, relaciones con clientes y proveedores, marca, licencias/patentes/derechos, contratos clave). **Un activo puede ser crítico aunque no sea el más costoso: lo importante es su función y su impacto en la continuidad.**
     - *Ejemplos por sector*: **Empresa de software**: BD de clientes, servidores de aplicaciones, código fuente, personal especializado con conocimiento crítico del producto. **Hospital**: sistema de historias clínicas, personal médico especializado, equipos de soporte vital. **Banco**: sistema de transacciones electrónicas, red de cajeros automáticos, BD de clientes y transacciones.
  4. **Impacto**: **consecuencia** que podría generar para la organización la ocurrencia de una amenaza al afectar un activo, recurso o proceso crítico. Dimensiones: **Económico/Financiero** (pérdidas económicas, costos adicionales), **Operativo** (interrupción o degradación de procesos y servicios), **Legal/Regulatorio** (multas, sanciones o incumplimientos), **Reputacional** (pérdida de confianza, deterioro de la imagen institucional). Ejemplos: pérdida de ingresos por la interrupción del servicio; paralización del proceso de pagos; multas por incumplimiento de normativas de protección de datos; pérdida de confianza de clientes y daño a la imagen. En el análisis de riesgos se pregunta: "Si ocurre esta amenaza, ¿qué impacto ocasionaría?" → luego se valora probabilidad e impacto para obtener el nivel de riesgo.
- **Cómo redactar un riesgo (integrando los 4 elementos)**. Estructura recomendada: **"Existe el riesgo de que [AMENAZA], debido a [VULNERABILIDAD], afecte [ACTIVO O PROCESO CRÍTICO], generando [IMPACTO]."** Consideraciones: incluir los 4 elementos; usar lenguaje claro y específico; indicar la debilidad o condición (vulnerabilidad) que puede facilitar que la amenaza cause daño o aumente sus consecuencias; describir el impacto principal para el negocio; el riesgo se redacta como un **evento posible** (no como un incidente ocurrido). *Ejemplo*: "Existe el riesgo de que un **ataque de ransomware**, aprovechando la **falta de actualización de parches de seguridad**, afecte la **base de datos de clientes**, generando **indisponibilidad de la información, interrupción del servicio y pérdidas económicas**." *Ejercicio de la diapositiva*: elementos desordenados (interrupción del servicio de ventas y pérdidas económicas = impacto; plataforma de comercio electrónico = activo; ataque DDoS = amenaza; falta de mecanismos adecuados de protección y mitigación frente a DDoS = vulnerabilidad) → "Existe el riesgo de que un ataque DDoS, debido a la falta de mecanismos adecuados de protección y mitigación frente a DDoS, afecte la plataforma de comercio electrónico, generando interrupción del servicio de ventas y pérdidas económicas."
- **Análisis de riesgo**: proceso que permite **analizar las amenazas** que podrían afectar a la organización y **estimar su probabilidad de ocurrencia y el impacto** que ocasionarían, con el fin de **determinar el nivel de riesgo y establecer prioridades para su tratamiento**. **Probabilidad**: ¿qué tan probable es que ocurra la amenaza? **Impacto**: si ocurre, ¿qué tan graves serían sus consecuencias?
- **Fórmula (valoración cualitativa mediante matriz de riesgos)**: **Nivel de Riesgo = Probabilidad × Impacto**.
  | Elemento | ¿Qué significa? |
  |---|---|
  | Probabilidad | Qué tan probable es que ocurra una amenaza; se valora mediante una escala previamente definida |
  | Impacto | Qué tan graves serían las consecuencias si la amenaza ocurre; escala previamente definida |
  | Nivel de riesgo | Resultado de combinar probabilidad e impacto; se utiliza para establecer la prioridad del riesgo |
- **Ejemplo**: empresa de software; falla del disco duro del servidor (amenaza) y no se realizan backups automáticos (vulnerabilidad). Activo crítico: base de datos de la empresa. Impacto principal: pérdida total de la BD, afectando la continuidad de los servicios y generando interrupción de servicios. Valoración cualitativa: **Probabilidad 3 (Media)** (se considera media según estadísticas de fallas de hardware en la organización o en el sector); **Impacto 4 (Alto)** (se perdería toda la BD, afectando la continuidad de los servicios y generando pérdidas significativas); **Nivel de riesgo = 3 × 4 = 12** → según la matriz de riesgos, nivel **Alto** (en la diapositiva); *con la tabla de la sesión 12 un valor de 12 corresponde a Medio: los rangos y colores pueden variar según la metodología de la organización* (⚠️ REVISAR cuál usar en el examen: la Sesión 12 usa 9–12 = Medio).

### Diferencia entre un BIA y el análisis de riesgo
| Concepto | BIA (Análisis de Impacto en el Negocio) | Evaluación de amenazas a través del análisis de riesgo |
|---|---|---|
| ¿Qué es? | Proceso que identifica las funciones críticas del negocio y evalúa el impacto de su interrupción | Proceso que identifica y analiza amenazas potenciales, su probabilidad y su impacto |
| Objetivo principal | Evaluar las consecuencias de la interrupción y cómo evolucionan en el tiempo | Determinar qué tan expuesto está el negocio frente a eventos adversos |
| Enfoque | Centrado en los **procesos** del negocio y el **tiempo de recuperación** necesario | Centrado en las **amenazas, vulnerabilidades y activos críticos** |
| Preguntas clave | Si el proceso se interrumpe, ¿qué impacto tendría y cómo evolucionaría con el tiempo? | ¿Qué amenazas podrían afectarlo, qué tan probable es que ocurran y qué impacto ocasionarían? |
| Resultado | Priorización de procesos y establecimiento de requisitos de recuperación: **MTPD, RTO, RPO y WRT** | Mapa de riesgos con niveles de prioridad según riesgo (probabilidad × impacto) |
| Ejemplo en desarrollo de software | Si el repositorio de código queda inaccesible, ¿cuánto afecta al negocio? ¿en cuánto tiempo debe estar nuevamente disponible? | ¿Qué tan probable es que un ataque DDoS afecte el servidor del repositorio? ¿Qué tan preparado estoy para responder? |

## 5. Caso de estudio (actividad de clase)
Desarrollan una aplicación web para una clínica privada: agendar citas, almacenar historias clínicas, pagos online; equipo híbrido; servicios cloud. Resuelto en [[EJ_S06_Riesgos]].

## Preguntas de cierre
¿Qué es una amenaza? ¿una vulnerabilidad? ¿un activo crítico? → ver definiciones arriba.

## Conclusiones del docente
1. Las amenazas son eventos o condiciones potenciales que pueden afectar los activos, recursos o procesos críticos.
2. Analizar la relación amenaza–vulnerabilidad–activo crítico–impacto permite comprender los escenarios de riesgo que podrían afectar la continuidad.
3. Valorar la **probabilidad** y el **impacto** permite determinar el nivel de riesgo y establecer prioridades para su tratamiento.

## Ojo en el examen
- Definir con precisión los 4 elementos + incidente disruptivo; distinguir amenaza (potencial) de incidente (ocurrido), y "no toda amenaza genera un incidente".
- Clasificar amenazas por **fuente/causa** (naturales, humanas, tecnológicas, sociales/sanitarias) y por **procedencia** (internas/externas); una amenaza puede clasificarse con ambos criterios.
- Redactar un riesgo con la estructura "Existe el riesgo de que… debido a… afecte… generando…".
- BIA vs análisis de riesgo (tabla).
- Nivel de riesgo = P × I.
