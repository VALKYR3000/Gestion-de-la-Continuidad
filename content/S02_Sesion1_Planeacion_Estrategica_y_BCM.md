---
tags: [clase, continuidad-del-negocio, semana2]
fuente: SEM 2/SESION 1 (PDF S02_s3 completo, texto + diapositivas gráficas)
---
# S02-1 · Planeación estratégica y Gestión de la continuidad del negocio (BCM/GCN)
Ejercicios: [[EJ_S02_Planeacion_Estrategica_y_Niveles]]

## Logro y gancho
Aplicar los principios de la planeación estratégica (PE) en la GCN, relacionando objetivos estratégicos con necesidades de continuidad y resiliencia.
Pregunta: si una organización tiene claros sus objetivos estratégicos, ¿qué podría impedir que los alcance cuando ocurre una interrupción grave?
**Importancia**: la PE define hacia dónde quiere dirigirse la organización; la GCN protege las actividades y recursos necesarios para mantener ese rumbo frente a interrupciones. Integrarlas fortalece la resiliencia y favorece el cumplimiento de objetivos.
Contenido: proceso de planeación estratégica · elementos de la PE · actividad en clase.

## 1. Relación PE ↔ GCN (analogía del barco)
- **Empresa = barco**. PE = el **mapa**: estado actual, destino (visión), ruta a seguir. **Preparación (antes)**: analizamos el entorno y los riesgos, definimos objetivos y estrategias, identificamos actividades y recursos críticos, preparamos capacidades y alternativas. **Interrupción (durante)**: el barco enfrenta un iceberg (interrupción disruptiva). **Respuesta y recuperación (después)**: gracias a las capacidades y procedimientos, el barco responde (activamos protocolos y recursos), se recupera (restablecemos actividades prioritarias), continúa (seguimos avanzando hacia el destino) y mejora (aprendemos y fortalecemos capacidades).
- La **PE define el destino y la ruta** de la organización; la **GCN prepara capacidades, alternativas y procedimientos** para que la empresa pueda seguir avanzando ante cualquier interrupción.
- **PE**: establece hacia dónde quiere ir la organización y qué estrategias utilizará; define visión, objetivos estratégicos y ruta. **GCN**: busca que una interrupción **no destruya la capacidad** de la organización para continuar desarrollando las **actividades prioritarias** que apoyan esos objetivos; protege procesos, recursos y capacidades para mantener o recuperar lo que realmente importa.
- **La GCN debe estar ALINEADA con los objetivos estratégicos**: sin alineación se puede invertir en proteger lo que no es prioritario y dejar expuesto lo esencial (no tendría sentido gastar enormes recursos recuperando rápidamente una actividad que no es importante para los objetivos, mientras se deja detenida durante días una actividad prioritaria crítica para la misión).
- **Ejemplo aplicado (empresa de servicios en la nube)**: Objetivo estratégico = alcanzar una cuota de mercado del 20% en el sector gubernamental en 3 años (diversificar cartera, ingresos más estables con contratos estatales). Necesidad de continuidad = mantener disponibles los servicios tecnológicos prioritarios que soportan la atención de clientes y el cumplimiento de contratos gubernamentales. Respuesta de la GCN = **BIA** (identifica actividades críticas y evalúa impactos), **necesidad de recuperación** (RTO de 2 horas para recuperar el servicio prioritario, ej. servicio de base de datos), **estrategia de continuidad** (infraestructura redundante en una ubicación geográficamente separada que permita recuperar el servicio dentro del tiempo establecido). Idea: la estrategia determina qué es importante; la GCN ayuda a proteger su continuidad.
- **Resumen**: la PE define el destino y la ruta; la GCN asegura que podamos seguir navegando y llegar a él incluso cuando aparezcan interrupciones. **La continuidad no empieza cuando ocurre la interrupción, empieza mucho antes: se planifica, se prepara y se alinea con la estrategia.**

### Cuadro comparativo PE vs GCN
| Característica | Planeación Estratégica | Gestión de Continuidad (GCN) |
|---|---|---|
| Pregunta | ¿A dónde queremos llegar? | ¿Cómo mantenemos y recuperamos las operaciones ante un incidente disruptivo? |
| Foco principal | Dirección estratégica, crecimiento y generación de valor | Continuidad de actividades prioritarias frente a interrupciones |
| Estado | Mira hacia el futuro (oportunidades) | Considera riesgos de interrupción y sus impactos |
| Contexto | Condiciones normales de operación | Preparación, respuesta y recuperación ante interrupciones |
| Pregunta clave | ¿Dónde queremos estar en 5 años? | ¿Cómo operamos si hoy perdemos el servidor? |
| Meta | Maximizar el valor y la rentabilidad | Minimizar el impacto de las interrupciones y recuperar las actividades prioritarias dentro de los tiempos establecidos |
| Instrumentos | Matriz FODA, PESTEL, Cuadro de Mando | BIA, Plan de Continuidad (BCP), Plan de Recuperación (DRP) |

## 2. Planeación estratégica
- **¿Qué ocurre si una empresa opera sin PE clara?** No tiene dirección clara · no puede adaptarse a cambios · pierde oportunidades de crecimiento · uso ineficiente de recursos · mayor vulnerabilidad ante crisis.
- **¿Qué ocurre cuando la estrategia no se adapta al entorno?** **Blockbuster** no logró adaptar oportunamente su estrategia ante el cambio en los hábitos de consumo y el crecimiento del *streaming*. **Kodak** desarrolló tempranamente la tecnología de fotografía digital pero no transformó oportunamente su modelo de negocio frente al avance del mercado digital.
- **Definición**: proceso mediante el cual una organización define su **dirección y objetivos a largo plazo**, analiza su **entorno** y establece las **estrategias** necesarias para alcanzarlos.
- **Ejemplo software contable** (cuota de mercado 5% en Perú): ¿Hacia dónde queremos ir? (dirección futura/visión) = convertirse en un proveedor referente de software de gestión financiera para PYMES en Latinoamérica al 2030. ¿Qué queremos lograr? (objetivos estratégicos) = expandir operaciones a países de Latinoamérica, aumentar participación de mercado, ampliar oferta de soluciones financieras, consolidar marca reconocida y confiable. ¿Cómo lo lograremos? (estrategias) = desarrollar plataforma financiera integrada y moderna; ingresar progresivamente a nuevos mercados; establecer alianzas estratégicas con empresas y asociaciones; fortalecer la innovación y la experiencia del cliente. ¿Qué haremos concretamente? (plan de acción/acciones) = lanzar campañas digitales, realizar webinars y eventos para PYMES, desarrollar nuevos módulos (contabilidad, inventarios, análisis de datos), programa de referidos, contratar y capacitar talento. **Idea clave**: la PE nos ayuda a definir una dirección clara, establecer objetivos, elegir estrategias y ejecutar acciones para construir el futuro deseado. La GCN se alinea con esta planificación para proteger las actividades críticas que permiten cumplir los objetivos estratégicos.
- **Proceso de PE (esquema de 5 etapas en la diapositiva)**: 1 **Dirección estratégica** (misión, visión, valores: ¿quiénes somos y hacia dónde queremos ir?) → 2 **Análisis estratégico** (entorno interno y externo, FODA, PESTEL: ¿dónde estamos y qué ocurre en nuestro entorno?) → 3 **Formulación estratégica** (objetivos estratégicos, estrategias: ¿qué queremos lograr y cómo lo lograremos?) → 4 **Implementación** (planes de acción, recursos, responsables: ¿cómo llevamos la estrategia a la práctica?) → 5 **Evaluación y control** (indicadores, seguimiento, ajustes: ¿estamos logrando los resultados esperados?). Objetivo del proceso: tomar decisiones informadas, alinear a toda la organización y utilizar eficientemente los recursos para alcanzar los objetivos y asegurar el crecimiento sostenible en el tiempo.
- En la numeración de la clase los elementos son 8: **1 Misión · 2 Visión · 3 Valores · 4 Análisis del entorno · 5 Objetivos estratégicos · 6 Desarrollo de estrategias · 7 Implementación · 8 Evaluación y control**.

### 1. Misión
- Expresa la **razón de ser** de la organización: qué hace, para quién lo hace y, según la formulación, cómo aporta valor. *¿Por qué existimos y qué hacemos?*
- **Perspectiva de continuidad**: la GCN contribuye a **proteger la capacidad de la organización para continuar cumpliendo su misión** cuando ocurre una interrupción. Ej.: hospital con misión de brindar servicios de salud → la BCM considera especialmente las **actividades prioritarias** necesarias para mantener la atención.

### 2. Visión
- Declaración **a largo plazo** que describe el **futuro deseado**; dirección futura hacia la cual la organización desea avanzar. *¿Qué queremos llegar a ser en el futuro?* Ej.: "Ser una plataforma líder de servicios financieros digitales en Latinoamérica, reconocida por su seguridad, confiabilidad e innovación para el año 2030."
- **Perspectiva de continuidad**: la BCM protege la capacidad para seguir avanzando hacia el futuro deseado, evitando que las interrupciones comprometan seriamente esa dirección. Ej.: si aspira a servicios financieros confiables y seguros, la BCM debe mantener y recuperar las actividades prioritarias que soportan esos servicios.

### 3. Valores
- Fundamento **ético y cultural**; **principios y creencias** que orientan el comportamiento, decisiones y forma de actuar. *¿Qué principios guían nuestro comportamiento y decisiones?* Empresa de software: innovación, calidad, compromiso con el cliente, responsabilidad, trabajo en equipo.
- Influyen en las decisiones y en cómo se implementan las estrategias. Ej. Innovación: **orienta decisiones y se refleja en acciones** (inversión en I+D, formación continua, mejora de productos y servicios).
- **Perspectiva de continuidad**: orientan cómo la organización toma decisiones y actúa frente a una interrupción. Ej. **compromiso con el cliente**: mantiene comunicación oportuna con clientes y prioriza la continuidad o recuperación de los servicios relevantes para ellos.

### 4. Análisis del entorno
- Evalúa **factores internos y externos** que pueden afectar a una empresa/organización/proyecto; objetivo: identificar **oportunidades y amenazas** del entorno que influyen en la toma de decisiones y el éxito del negocio. Herramientas: **Análisis FODA, PESTEL, 5 fuerzas de Porter**.
- **FODA**: análisis **interno** → Fortalezas, Debilidades; análisis **externo** → Oportunidades, Amenazas.
  - **Fortalezas**: aspectos internos positivos que dan ventaja sobre competidores (tecnología avanzada, talento humano calificado, buena reputación de marca).
  - **Oportunidades**: condiciones externas que se pueden aprovechar (crecimiento del mercado, cambios regulatorios favorables, avances tecnológicos que mejoran la eficiencia).
  - **Debilidades**: aspectos internos negativos que limitan competir o lograr objetivos (falta de recursos financieros, procesos ineficientes, poca presencia en mercados clave).
  - **Amenazas**: factores externos que podrían poner en peligro el éxito o dificultar el crecimiento (competencia creciente, crisis económicas, cambios en regulaciones del sector).
- **Análisis del entorno y BCM**: el análisis del entorno aporta contexto a la GCN: identifica amenazas y vulnerabilidades potenciales para la continuidad, aporta contexto para determinar actividades prioritarias, impactos, tiempos de recuperación (RTO/RPO) y requisitos de recursos, y facilita el diseño de estrategias y planes alineados al contexto real. Retroalimenta y mejora. **⚠️ FODA y PESTEL aportan información del contexto, pero NO reemplazan el análisis de riesgos ni el BIA.** El análisis del entorno brinda perspectiva y contexto; la BCM convierte ese contexto en decisiones para proteger la continuidad del negocio.
- **Caso SOLUCIONES TEC** (empresa de software para PYMES) — matriz FODA resuelta:
  - **Fortalezas**: especialización en pymes (aliado estratégico); plataformas low-code que reducen costos y tiempos; capacitación y soporte remoto que aseguran la adopción; flexibilidad de portafolio (web, móvil, gestión interna).
  - **Oportunidades**: mayor demanda de digitalización en pymes; creciente interés en IA y ciberseguridad; auge del trabajo remoto y servicios en la nube; potencial de alianzas estratégicas.
  - **Debilidades**: dependencia de talento especializado difícil de retener; portafolio limitado en IA y ciberseguridad; capacidad de inversión y escalamiento reducida; procesos comerciales y marketing poco robustos.
  - **Amenazas**: alta competencia de grandes tecnológicas y proveedores globales; rápida obsolescencia de herramientas y lenguajes; sustitución por soluciones low-cost/no-code autogestionadas; inestabilidad económica que recorta presupuestos de TI.

### 5. Objetivos estratégicos
- Resultados **específicos** que la organización busca alcanzar en un **periodo determinado**, contribuyen al cumplimiento de su dirección estratégica; se formulan con el enfoque **SMART**.
- **Perspectiva de continuidad**: los objetivos indican qué resultados son importantes; la BCM considera qué **actividades y recursos** son necesarios para sostener esos objetivos frente a interrupciones. Ejemplo: objetivo = incrementar 20% la cartera de clientes empresariales en 2 años → actividad prioritaria = prestación del servicio tecnológico en la nube a los clientes → interrupción = falla del centro de datos que deja la plataforma fuera de servicio → BCM: identifica la actividad prioritaria, BIA (determina necesidad de recuperación, RTO 2 horas), define estrategia (infraestructura redundante), establece procedimientos y realiza pruebas de recuperación → resultado: ante una interrupción, la organización está preparada para recuperar la actividad prioritaria y reducir el impacto sobre sus objetivos. La BCM alinea la continuidad de las actividades críticas con los objetivos estratégicos.
- **Criterios SMART**: **S**pecific (clara y precisa) · **M**easurable (cuantificable para medir el progreso) · **A**chievable (realista, según recursos y restricciones) · **R**elevant (importante y alineada con otros objetivos/prioridades) · **T**ime-bound (plazo determinado: urgencia y priorización).
- **Objetivo SMART 1 (Soluciones Tec)**: "Reducir en un 15% la dependencia de talento especializado en los próximos 9 meses mediante programas internos de capacitación continua, asegurando la sostenibilidad operativa del negocio." S: reducir dependencia de talento externo especializado · M: reducción del 15% · A: mediante programas internos de capacitación continua · R: asegurar la sostenibilidad operativa · T: 9 meses.
- **Objetivo SMART 2**: "Incrementar en un 25% la captación de nuevas pymes en los próximos 6 meses, mediante campañas de marketing digital y demostraciones de software, lo cual contribuirá a aumentar la rentabilidad y posicionamiento." S: incrementar la captación de nuevas pymes clientes · M: +25% en 6 meses · A: campañas de marketing digital y demostraciones · R: mejorar rentabilidad y posicionamiento · T: 6 meses.

### 6. Desarrollo de estrategias
- Las estrategias son los **enfoques o cursos de acción** que la organización define para alcanzar sus objetivos estratégicos. Objetivo = **¿qué queremos lograr?** · Estrategia = **¿cómo lo lograremos?** · Acciones = **¿qué haremos concretamente?** Se formulan considerando los recursos y capacidades, toman en cuenta el entorno interno y externo, y permiten aprovechar fortalezas y oportunidades y responder a debilidades y amenazas.
- **Perspectiva de continuidad**: las estrategias indican cómo se busca alcanzar los objetivos; la BCM alinea con ellas, identificando las actividades y recursos prioritarios que las soportan y preparando capacidades de continuidad para protegerlos frente a interrupciones.
- **Estrategias propuestas Soluciones Tec**: Objetivo 1 (reducir 15% dependencia del talento en 9 meses): programa de formación interna; plataforma de aprendizaje virtual (e-learning); mentoría interna; convenios educativos con universidades e institutos. Objetivo 2 (+25% pymes en 6 meses): campañas digitales (LinkedIn, Google Ads); alianzas estratégicas con cámaras de comercio y asociaciones; webinars y demostraciones; programa de referidos.
- **Relación estrategia–continuidad (paso a paso)**: objetivo estratégico (¿qué queremos lograr?) → estrategia (¿cómo lo lograremos?) → actividades y recursos necesarios para ejecutarla → BCM (¿qué protegemos y cómo nos recuperamos?) → continuidad de la estrategia. Ejemplo: objetivo = incrementar 25% la captación de PYMES en 6 meses; estrategia = fortalecer los canales digitales mediante campañas, webinars y demostraciones virtuales; recursos = plataforma web, CRM, canales digitales, BD de clientes, personal de marketing, conectividad/servicios tecnológicos; BCM = ante una interrupción tecnológica, establecer alternativas para mantener o recuperar esos servicios (plataforma alterna, sitio alterno, respaldos, procedimientos); resultado: la estrategia puede seguir ejecutándose y la organización continúa avanzando hacia su objetivo. **Una estrategia sin continuidad es vulnerable.**

### 7. Implementación de estrategias
- Poner en práctica las estrategias diseñadas. Implica: **1 Asignación de recursos** (talento humano, tecnología, infraestructura, recursos financieros, información) · **2 Roles y responsabilidades** (quién hace qué: responsables, equipos de trabajo, autoridad y toma de decisiones) · **3 Planes de acción** (acciones concretas con metas y plazos: actividades clave, cronograma, hitos y entregables, indicadores de avance) · **4 Comunicación** (interna, externa, reportes de avance, retroalimentación) · **5 Presupuesto** (estimación de costos, asignación, control y seguimiento del gasto).
- **Para que sea efectiva**: alinear todas las áreas · fomentar el compromiso y la cultura de colaboración · monitorear y dar seguimiento continuamente · ajustar y mejorar en función de los resultados. **Perspectiva BCM**: una implementación efectiva asegura que las estrategias se ejecuten incluso ante interrupciones, preparando a la organización para responder con resiliencia. "Implementar bien hoy garantiza resultados sostenibles mañana."

### 8. Evaluación y control
- **Monitorear el progreso** para asegurar que se cumplen los objetivos; mediante **recopilación de datos, medición de resultados y análisis de desempeño**; se usan **indicadores de desempeño (KPIs)** y otros sistemas de seguimiento.

## Preguntas de cierre (con respuesta)
- ¿Qué es la PE? → proceso por el cual la organización define su dirección y objetivos a largo plazo, analiza su entorno y establece estrategias.
- ¿Elementos clave? → misión, visión, valores, análisis del entorno, objetivos estratégicos, desarrollo de estrategias, implementación, evaluación y control.

## Conclusiones del docente
1. La PE establece la dirección (hacia dónde, qué objetivos, qué estrategias).
2. Misión, visión, valores y análisis del entorno orientan la formulación de objetivos y estrategias.
3. La BCM debe estar alineada con la estrategia para proteger las actividades prioritarias que permiten avanzar hacia los objetivos.
4. PE y BCM son **complementarias**: la primera orienta hacia dónde avanzar; la segunda fortalece la capacidad de continuar y recuperarse cuando una interrupción amenaza ese camino.

## Ojo en el examen
- Misión vs visión vs valores + perspectiva de continuidad de cada una.
- FODA: interno vs externo; FODA/PESTEL **no reemplazan** el BIA ni el análisis de riesgos.
- Validar/redactar objetivos SMART; objetivo (qué) vs estrategia (cómo) vs acciones (qué haremos).
- Tabla PE vs GCN; analogía del barco.
