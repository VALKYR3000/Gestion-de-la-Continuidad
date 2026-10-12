---
tags: [clase, continuidad-del-negocio, semana3]
fuente: SEM 3/SESION 1 (PDF S03_s5 completo, texto + diapositivas gráficas, + caso MediCloud)
---
# S03-1 · Estructura organizacional para la continuidad: roles, responsabilidades y autoridad
Ejercicios de esta semana: [[EJ_S03_Estructura_y_Procedimientos]]

## Logro y gancho
Analizar la estructura organizacional de la GCN identificando roles y responsabilidades en preparación, respuesta y recuperación.
Pregunta de entrada: último día de matrícula, 10 min para el cierre, cae el servidor principal. ¿Revisas el servidor/BD/logs de inmediato o llamas al Rector a pedir permiso? → Si el procedimiento ya te autoriza, **actúas** (autoridad previamente definida).

## 1. ¿Qué es la estructura organizacional para la continuidad?
- Marco que define **roles, responsabilidades y equipos** que la organización establece para **gestionar y responder** eficazmente ante una interrupción o crisis.
- **Complementa** la estructura jerárquica regular, con un enfoque específico en respuesta, recuperación y continuidad.
- Una estructura clara permite que cada persona sepa **qué hacer, a quién reportar y cuándo escalar**.
- Responde a 3 preguntas:
  - **¿Quién DECIDE?** instancias con autoridad para tomar decisiones estratégicas.
  - **¿Quién COORDINA?** quién articula, coordina y asegura la respuesta integrada.
  - **¿Quién EJECUTA?** equipos operativos que ejecutan las acciones de recuperación.
- Base para responder con rapidez, coordinación y efectividad.

## 2. Rol, responsabilidad y autoridad
| Concepto | Pregunta | Definición | Ejemplo |
|---|---|---|---|
| **Rol** | ¿Quién participa? | Función o posición que una persona/equipo ocupa dentro de la estructura de continuidad | Coordinador de Gestión de Continuidad del Negocio (BCM) |
| **Responsabilidad** | ¿Qué le corresponde hacer? | Funciones y acciones esperadas del rol para contribuir a preparación, respuesta y recuperación | Coordinar la respuesta ante incidentes y consolidar la información de los equipos de recuperación |
| **Autoridad** | ¿Qué puede decidir o activar? | Decisiones y acciones que el rol puede realizar dentro de límites previamente definidos, sin necesidad de solicitar autorización cada vez | Un responsable de TI puede ejecutar un *failover* cuando se cumplen criterios y procedimientos establecidos |
- Resumen: **rol = quién; responsabilidad = qué hace; autoridad = hasta dónde puede decidir o actuar.**
- Una estructura clara evita la improvisación y asegura que todos sepan QUÉ HACER, A QUIÉN INFORMAR y CUÁNDO ESCALAR.

**¿Cómo se organiza la actuación?** (3 bloques)
1. *Roles y responsabilidades*: define quién participa y qué función cumple cada persona/equipo; sin claridad se generan duplicidades, vacíos y confusión.
2. *Autoridad y escalamiento*: qué decisiones o acciones puede tomar cada rol dentro de límites definidos; cuándo debe escalar a un nivel superior. Actuar dentro de la autoridad definida da rapidez y seguridad.
3. *Coordinación y comunicación*: cómo fluye la información entre niveles, áreas y equipos; todos los actores informados y alineados.
- **Flujo de actuación ante una interrupción: ACTUAR → INFORMAR → COORDINAR → ESCALAR.**
  - Actuar: cada rol actúa dentro de su autoridad establecida.
  - Informar: se comunica lo realizado y el estado de la situación a los niveles correspondientes.
  - Coordinar: se coordinan acciones entre áreas y equipos para una respuesta integrada.
  - Escalar: cuando la situación excede la autoridad, se escala al nivel superior.

## 3. Distribución de roles por nivel de actuación (visión general)
| Nivel | Instancia | Enfoque |
|---|---|---|
| **Estratégico** | Comité de Gestión de Crisis / Alta Dirección: dirección y decisiones para proteger la organización y asegurar la continuidad del negocio. Define prioridades estratégicas, toma decisiones de alto impacto, asigna recursos críticos, autoriza o respalda decisiones que exceden los niveles de autoridad delegados | visión, impacto y sostenibilidad del negocio |
| **Táctico y de apoyo** | **Coordinador BCM** (articula y coordina entre los diferentes equipos y áreas) + equipos de soporte: Comunicaciones, Legal y Cumplimiento, Logística, Auditoría | articular, coordinar y dar soporte a la respuesta |
| **Operativo** | Equipos de recuperación: TI (sistemas, aplicaciones, datos), Operaciones (restablece procesos y servicios críticos), Finanzas (impactos financieros y recursos), RR.HH. (apoyo al personal, gestión de equipos), otros equipos según naturaleza del incidente | ejecución operativa y recuperación de actividades priorizadas |
Mensaje: una estructura clara asegura que cada nivel conozca su rol, responsabilidades y autoridad, permitiendo actuar con rapidez, coordinación y control ante cualquier interrupción.

## 4. NIVEL ESTRATÉGICO: Comité de Gestión de Crisis (CGC)
- Órgano estratégico que **dirige y toma decisiones de alto impacto** cuando una interrupción o crisis supera los niveles de autoridad delegados.
- **Integrantes principales (ejemplo)**: CEO/Gerente General · COO/Gerente de Operaciones · CFO/Gerente Financiero · CISO/Gerente de TI o Seguridad · Gerente de RR.HH. La composición **varía según tamaño, sector y complejidad**; no todos los cargos son obligatorios, se integran las áreas según la naturaleza y alcance del incidente.
- **Responsabilidades y autoridad (4 funciones)**:
  1. Establece **prioridades estratégicas**: qué debe protegerse y priorizarse (personas, servicios críticos, clientes, obligaciones, reputación, cumplimiento y sostenibilidad).
  2. Toma **decisiones de alto impacto**: decide ante situaciones que superan los niveles de autoridad delegados, incluyendo cambios en la operación, aceptación de riesgos y estrategias de respuesta y continuidad.
  3. **Asigna o reasigna recursos extraordinarios**: autoriza y asigna recursos financieros, humanos, tecnológicos y otros críticos adicionales.
  4. **Dirige y da seguimiento** a la gestión de la crisis: evalúa información consolidada sobre impactos, evolución, recuperación y comunicaciones para orientar decisiones estratégicas y asegurar el logro de objetivos de continuidad.
- **¿Cuándo interviene?** Cuando la interrupción supera los umbrales o niveles de autoridad establecidos, compromete múltiples áreas o servicios críticos, o genera consecuencias significativas para personas, clientes, reputación, cumplimiento o sostenibilidad. Actúa cuando la situación supera los niveles delegados y requiere decisiones estratégicas.
- **Qué aporta cada rol principal** (por qué están en el comité: información crítica, visión experta, capacidad de decisión):
  - **CEO/Gerente General**: visión global y objetivos estratégicos; define prioridades estratégicas ante la crisis; toma decisiones que protegen sostenibilidad, reputación y servicios clave; alinea las decisiones con la estrategia y el propósito institucional.
  - **COO/Gerente de Operaciones**: informa del impacto operativo en servicios, procesos, proveedores y clientes; propone alternativas para mantener o restablecer operaciones críticas; asegura decisiones que permitan mantener o recuperar lo esencial.
  - **CFO/Gerente Financiero**: informa del impacto financiero estimado; evalúa disponibilidad de recursos y presupuesto para opciones de respuesta; analiza viabilidad económica y retorno de alternativas; asegura decisiones financieramente sostenibles.
  - **CISO/Gerente de TI o Seguridad**: perspectiva tecnológica y de ciberseguridad; informa del estado de sistemas, aplicaciones, datos e infraestructura crítica; evalúa riesgos de ciberseguridad, vulnerabilidades y probabilidad de nuevas amenazas; presenta alternativas técnicas; estima tiempos de recuperación (RTO/RPO); asesora medidas para proteger datos. Ej.: "Tenemos un ataque de ransomware, sistemas afectados, cuánto tarda la recuperación…".
  - **Gerente de RR.HH.**: perspectiva de personas; impacto en personal, equipos y lugares de trabajo; disponibilidad de personal y planes de relevo; necesidades de seguridad, bienestar y soporte emocional; comunicación interna; cumplimiento de políticas laborales. Ej.: "El 30% del personal clave no puede desplazarse al centro de trabajo…".
  - Combinación: visión estratégica, operativa y financiera + tecnología y personas → calidad y oportunidad de las decisiones.

## 5. NIVEL TÁCTICO Y DE APOYO: Coordinador BCM y equipos de soporte
- Coordina y da soporte especializado a la respuesta ante la crisis; trabaja articulado siguiendo las decisiones estratégicas del Comité.
- **Quiénes participan** (figura central: Coordinador BCM, articula y coordina la respuesta entre las áreas involucradas):
  - **Comunicaciones**: apoya la gestión coordinada de la información y comunicación interna y externa durante la crisis; comunica con claridad, oportunidad y coherencia.
  - **Legal y Cumplimiento**: asesora sobre obligaciones legales, regulatorias y contractuales derivadas; reduce riesgos legales y asegura el cumplimiento.
  - **Logística**: facilita recursos, instalaciones, proveedores y servicios necesarios para sostener la respuesta y la recuperación; asegura recursos y condiciones para operar.
  - **Auditoría**: aporta evaluación independiente sobre controles, cumplimiento y oportunidades de mejora según el modelo de la organización; promueve transparencia y mejora continua.
- **Coordinador de Gestión de Continuidad del Negocio (BCM)**: enlace entre el nivel estratégico y los equipos operativos; asegura una respuesta organizada, oportuna y alineada. Responsabilidades:
  1. **Activación y evaluación**: evalúa la situación y activa o coordina la activación de los planes de continuidad cuando se encuentra dentro de los criterios y niveles de autoridad previamente establecidos. Cuando el impacto supera su autoridad, determina si se escala al Comité.
  2. **Coordinación de la respuesta**: coordina a los equipos involucrados y facilita la ejecución integrada de las estrategias de continuidad.
  3. **Monitoreo y consolidación**: recopila información sobre el incidente, avance de la recuperación y cumplimiento de requisitos (RTO, RPO, impacto, etc.).
  4. **Escalamiento y comunicación**: mantiene informado al nivel estratégico y escala asuntos o decisiones que exceden los umbrales o criterios definidos.
  - Mensaje clave: la autoridad para actuar está definida antes de la interrupción. Actuar dentro de la autoridad · Informar oportunamente · Escalar cuando corresponda.
- **Niveles de autoridad para actuar (según el incidente)**:
  1. **Incidente menor** (autoridad operativa): acciones acotadas y de bajo impacto con procedimientos autorizados; se informa al Coordinador BCM. Ej.: falla de un servidor con redundancia disponible → TI ejecuta *failover*.
  2. **Incidente significativo** (autoridad del Coordinador BCM): impacta servicios críticos o a varias áreas; el Coordinador BCM activa/coordina el plan; monitorea y puede requerir apoyo adicional. Ej.: indisponibilidad de múltiples servicios críticos.
  3. **Incidente grave / crisis** (autoridad estratégica): impacto alto, múltiple o sostenido; se escala al Comité de Gestión de Crisis; decisiones estratégicas/extraordinarias. Ej.: afectación externa, clientes, reputación o implicancias legales.
  - Ejemplo (empresa con sistema crítico con redundancia): (1) falla un servidor, hay redundancia y el impacto es limitado → TI tiene autoridad operativa, ejecuta failover inmediato e informa al Coordinador BCM. (2) Se afectan varios servicios priorizados (ventas, facturación, portal de clientes) → el Coordinador BCM evalúa, activa y coordina el plan, moviliza y coordina áreas (autoridad táctica). (3) La interrupción se prolonga y afecta múltiples servicios críticos y clientes (consecuencias reputacionales, financieras o regulatorias, incumplimiento contractual, necesidad de recursos que exceden la autoridad delegada) → el Coordinador escala, interviene el Comité, que toma decisiones estratégicas y autoriza recursos extraordinarios. **Cuanto mayor el impacto, mayor el nivel de autoridad.**
  - ¿Por qué es importante? Permite una respuesta rápida y ordenada, evitando demoras innecesarias y garantizando la coordinación.
- **¿Cómo articula y coordina la respuesta?** El Coordinador BCM conecta a las personas adecuadas, en el momento adecuado, para recuperar el negocio. Flujo de información en doble vía:
  - Con **Alta Dirección y Comité de Gestión de Crisis**: reporta/escala, recibe decisiones estratégicas.
  - Con **equipos operativos**: coordina acciones; recibe avance y recursos.
  - Con **equipos de apoyo**: coordina servicios; solicita soporte.
  - Con **proveedores y terceros clave**: coordina recursos; recibe soporte o información.
  - Qué hace: evalúa la situación (impacto, alcance, evolución) · activa o coordina el plan · articula y moviliza equipos (convoca equipos operativos y de apoyo) · comunica e informa (información clave a equipos, dirección y partes interesadas) · monitorea y consolida · escala cuando corresponde · documenta y reporta (registra pasos, acciones y lecciones).
  - Autoridad del Coordinador BCM: puede tomar decisiones y activar acciones dentro de los límites y criterios previamente aprobados. Ej.: activar planes/procedimientos aprobados, movilizar equipos internos y recursos previstos, solicitar soporte a equipos de apoyo o proveedores, aprobar acciones de recuperación dentro de su nivel de autoridad, tomar decisiones tácticas para minimizar el impacto.
  - **Limitaciones: debe escalar cuando…** el impacto supera los límites definidos; se requieren decisiones que exceden los criterios previamente aprobados; existen riesgos de recuperación fuera de los parámetros definidos; se requiere un gasto de recursos de alto costo; existe impacto regulatorio/reputacional/significativo; la interrupción afecta a toda la organización.
  - Principios que guían su actuar: liderazgo y calma · objetivos claros · comunicación clara y oportuna · decisiones basadas en información · enfoque en la recuperación.
  - Resultado esperado: una respuesta organizada, oportuna y alineada que reduce el impacto, acelera la recuperación y protege la reputación y sostenibilidad del negocio.
  - **Recuerda: el Coordinador BCM no ejecuta todas las acciones, pero orquesta la respuesta para que cada equipo haga lo que le corresponde, en el momento oportuno.**
- **Equipos de soporte a la crisis** (actúan coordinadamente con el Coordinador BCM; aportan especialización, no reemplazan a los equipos operativos):
  | Equipo | Qué aporta | Acciones clave | Cómo se coordina con el Coordinador BCM |
  |---|---|---|---|
  | **Comunicaciones y RR.PP.** | Gestiona información interna y externa; informa de manera oportuna, clara y consistente a colaboradores, clientes y partes interesadas; gestiona mensajes clave y canales de comunicación; reduce la incertidumbre y protege la reputación | preparar y difundir comunicados, gestionar medios y redes, alinear mensajes con el Coordinador BCM | recibe información verificada del BCM y retroalimenta el impacto en la comunicación |
  | **Asesoría Legal y Cumplimiento** | Asegura el cumplimiento legal, normativo y contractual; evalúa implicancias legales, regulatorias y contractuales; apoya notificaciones obligatorias y responsabilidades | evaluar obligaciones legales, definir requisitos regulatorios, revisar contratos con clientes y proveedores | recibe información del incidente y asesora sobre obligaciones y riesgos legales aplicables |
  | **Equipo de apoyo logístico** | Provee recursos, equipos, instalaciones y servicios contratados; asegura recursos, equipos, instalaciones y suministros; gestiona transporte, alojamiento u otros servicios de apoyo; facilita espacios alternos y condiciones operativas | habilitar sitios, transporte, equipos | recibe requerimientos del BCM y confirma disponibilidad/informa la comunicación |
  | **Auditoría** | Proporciona evaluación independiente y objetiva del proceso; evalúa efectividad de controles y cumplimiento de políticas; aporta una visión independiente para la mejora continua; apoya en la documentación y lecciones aprendidas | observar y registrar controles, analizar procesos, elaborar recomendaciones | recibe información y acceso según se requiera; comparte hallazgos y recomendaciones para la mejora |
  - Trabajo coordinado, respuesta efectiva. El Coordinador BCM integra los aportes de cada equipo, consolida la información y prioriza acciones para asegurar la continuidad del negocio.

## 6. NIVEL OPERATIVO: Equipos de respuesta y recuperación
- Ejecutan las acciones previstas para responder y recuperar los procesos, servicios y recursos afectados.
- **Quiénes participan**: equipo de TI/recuperación tecnológica; responsables de recuperación de las áreas de negocio; infraestructura y servicios; otros equipos operativos según la naturaleza e impacto de la interrupción (se movilizan los necesarios).
- **Rol principal: EJECUTAR** las acciones y procedimientos de respuesta y recuperación previamente establecidos, dentro de la autoridad asignada. Convierten los planes y procedimientos en acciones concretas, informando su avance al Coordinador BCM.
- **Ciclo**: DETECTAR (identifican la afectación en su área) → EJECUTAR (aplican los procedimientos autorizados para responder y recuperar) → RECUPERAR (restablecen servicios/procesos según objetivos definidos RTO/RPO) → VERIFICAR (validan el funcionamiento del recuperado y la calidad del servicio) → INFORMAR (comunican estado, avances, tiempos estimados y necesidades de apoyo al Coordinador BCM).
- **Si la acción está autorizada**: actúan de inmediato y reportan según lo establecido. **Si la situación excede su autoridad, afecta otras áreas o requiere coordinación mayor**: informan y escalan al Coordinador BCM.
- **Responsabilidades y autoridad** (tabla):
  1. Detectar y reportar — monitorean y detectan incidentes o interrupciones; reportan de forma inmediata la situación y su impacto.
  2. Ejecutar — aplican los procedimientos y acciones autorizadas para responder y recuperar; ejecutan acciones indicadas dentro de los límites de autoridad; utilizan recursos y herramientas autorizadas.
  3. Recuperar — restablecen servicios, procesos o recursos según los objetivos definidos (RTO/RPO); implementan estrategias de recuperación (tecnológicas, organizativas o logísticas); buscan cumplir los tiempos y niveles de servicio definidos.
  4. Verificar — validan el funcionamiento y la calidad del servicio; realizan pruebas o verificaciones para asegurar que los datos son íntegros y los servicios funcionan correctamente; confirman que la recuperación cumple los criterios de aceptación.
  5. Informar — comunican estado, avances, tiempos estimados y necesidades de apoyo; informan el estado actual y los hitos alcanzados; comunican riesgos, impedimentos y recursos adicionales requeridos.
  - **Nivel de autoridad**: *actúan directamente* cuando la acción está dentro de la autoridad previamente asignada (ej. reiniciar servicios, ejecutar failover, restaurar backups, activar sitio alterno, etc.); *escalan al Coordinador BCM* cuando la situación excede su autoridad, requiere recursos adicionales o decisiones de mayor impacto.
- Información que proporcionan: servicios o procesos afectados · acciones ejecutadas y resultados · estado de recuperación y tiempos estimados · recursos adicionales requeridos · riesgos o impedimentos identificados.
- **Idea clave**: el nivel operativo convierte los planes en acciones concretas; DETECTA, EJECUTA, RECUPERA E INFORMA para asegurar la continuidad del negocio. Ejecutan, verifican e informan; su actuar oportuno y coordinado es esencial para una recuperación efectiva.

## 7. Articulación y escalamiento entre niveles
- Los equipos operativos reportan el avance y las necesidades; el Coordinador BCM integra y coordina la respuesta; el Comité interviene cuando se requieren decisiones estratégicas o de alto impacto.
- La información fluye de abajo hacia arriba (reportes, estado, necesidades) y las decisiones de arriba hacia abajo.

## Caso MediCloud Perú (SaaS para 35 clínicas)
Resuelto en [[EJ_S03_Estructura_y_Procedimientos]].

## Preguntas de cierre de la clase
- Ante una interrupción en un servicio crítico, ¿cómo determinarían quién debe actuar, quién coordinar y cuándo escalar al estratégico? (criterios de autoridad predefinidos, magnitud del impacto, alcance, tiempo vs RTO, recursos extraordinarios).
- ¿Por qué definir antes quién decide/coordina/ejecuta? Para actuar con rapidez, evitar improvisación, duplicidades y vacíos, y dar trazabilidad.

## Conclusiones del docente
1. La estructura define quién decide, quién coordina y quién ejecuta.
2. Cada nivel cumple una función diferente pero complementaria: estratégico decide y orienta; táctico articula y coordina; operativo ejecuta y recupera.
3. La autoridad debe estar definida **antes** de la interrupción; los equipos ejecutan acciones previamente autorizadas, informan y escalan cuando excede su autoridad.
4. Respuesta eficaz = articulación entre todos los niveles.

## Ojo en el examen
- Rol / responsabilidad / autoridad con ejemplo de cada uno.
- Los 3 niveles de incidente (menor / significativo / grave-crisis) y quién tiene la autoridad en cada uno.
- Lista de cuándo debe escalar el Coordinador BCM.
- El Coordinador BCM **orquesta**, no ejecuta todo.
- Flujo ACTUAR → INFORMAR → COORDINAR → ESCALAR; ciclo operativo DETECTAR → EJECUTAR → RECUPERAR → VERIFICAR → INFORMAR.
