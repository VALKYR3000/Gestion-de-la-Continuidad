---
tags: [clase, continuidad-del-negocio, semana9, DRP]
fuente: SEM 9/SESION 1 (PDF S09_s17 completo, texto + diapositivas gráficas)
---
# S09-1 · Plan de Recuperación ante Desastres (DRP): fundamentos y elementos clave
Ejercicios: [[EJ_S09_DRP_y_Gobierno]]

## Logro y gancho
Comprender la importancia del DRP dentro de la gestión de la continuidad, identificar sus elementos clave y analizar un caso práctico.
Gancho: ¿qué aspectos debe tener preparados una organización para gestionar una crisis? / si una empresa pierde el acceso a sus servidores, aplicaciones y datos críticos por un evento disruptivo, ¿qué debería tener preparado para recuperarlos y restablecer sus servicios tecnológicos? → estrategias, recursos y procedimientos previamente definidos (DRP).
**Importancia**: la recuperación ante desastres permite prepararse para recuperar los sistemas, datos y servicios tecnológicos afectados por una interrupción grave; el DRP reduce el impacto y mantiene la continuidad de las actividades prioritarias que dependen de la tecnología.
Contenido: introducción · recuperación ante desastres · Plan de Recuperación ante Desastres (DRP) · elementos clave del DRP.

## 1. Introducción
Las organizaciones dependen cada vez más de la **tecnología** para sus operaciones diarias (gestión administrativa, atención a clientes, producción de bienes y servicios). Esta dependencia hace que cualquier interrupción significativa de los sistemas tecnológicos pueda afectar la continuidad del negocio, causando: **pérdidas económicas, daños a la reputación, incumplimiento de normativas, insatisfacción de clientes y usuarios**.

## 2. ¿Qué es un desastre en continuidad del negocio?
En el contexto del DRP, un **desastre** es un evento que provoca una **afectación grave** a los **sistemas, datos, infraestructura o servicios tecnológicos**, generando una interrupción significativa que requiere aplicar estrategias y procedimientos de recuperación previamente establecidos. Eventos que pueden provocarlo: incendios, fallas eléctricas, inundaciones, ataques cibernéticos, errores humanos, fallos técnicos.
| Desastre | Cómo afecta a TI | Ejemplo práctico |
|---|---|---|
| **Incendios** | Destruye servidores, almacenamiento, centros de datos y equipos de red | Un incendio afecta el centro de datos, dejando fuera de servicio servidores críticos y respaldos almacenados localmente |
| **Fallas eléctricas** | Apagado abrupto de sistemas, pérdida de datos no guardados, daño a hardware | Corte de energía deja inoperativos servidores y aplicaciones, interrupción de ERP |
| **Inundaciones** | Daño a infraestructura física y equipos de red | Inundación del piso de servidores impide el acceso a bases de datos y aplicaciones |
| **Errores humanos** | Configuración incorrecta, borrado de datos, caída de sistemas | Administrador borra por error la BD de clientes, bloqueando transacciones |
| **Ataques cibernéticos** | Secuestro o corrupción de datos, interrupción de servicios | Ransomware encripta servidores y aplicaciones críticas, deteniendo la operación |
| **Fallos técnicos** | Falla de hardware o software crítico | El servidor principal de correo corporativo se cae, bloqueando la comunicación interna y externa |
Ante una interrupción tecnológica significativa la organización debe contar con estrategias, recursos y procedimientos previamente definidos para recuperar los servicios tecnológicos afectados según las necesidades del negocio. Estos mecanismos forman parte de la **Recuperación ante Desastres (DR)**.

## 3. ¿Qué es la Recuperación ante Desastres (DR)?
- **Definición**: conjunto de **estrategias, recursos, medidas técnicas y procedimientos** destinados a **recuperar los sistemas, datos, infraestructura y servicios tecnológicos** afectados por un evento disruptivo.
- **Propósito principal**: recuperar la **infraestructura tecnológica, los sistemas y los datos** necesarios para la operación, de acuerdo con las prioridades y objetivos de recuperación establecidos, **reduciendo el tiempo de indisponibilidad y la pérdida de datos**.

### ¿En qué momento se desarrolla dentro de la BCM? (5 fases)
| Fase | Descripción | ¿Incluye recuperación ante desastres? |
|---|---|---|
| 1. Análisis de Impacto del Negocio (BIA) | Se identifican las actividades prioritarias, sus impactos y requisitos de recuperación (MTPD, RTO, RPO) | No directamente, pero sirve de base |
| 2. Análisis de Riesgos | Se identifican amenazas y vulnerabilidades que podrían afectar los recursos y servicios tecnológicos | No, pero define el escenario para la recuperación |
| 3. Estrategias de Continuidad y Recuperación | Se definen estrategias para continuar las operaciones y recuperar sistemas | **Sí**, se diseña la estrategia de recuperación ante desastres |
| 4. Desarrollo de Planes | Se documentan planes como el BCP (continuidad del negocio) y el DRP (recuperación de TI) | **Se redacta el DRP** |
| 5. Pruebas, entrenamiento y mantenimiento | Se prueba el DRP, se capacita al personal y se actualizan los planes | **Sí, aquí se valida la eficacia del DRP** |

## 4. ¿Qué es el DRP?
- **Plan documentado** que establece las **estrategias, recursos, procedimientos, roles y responsabilidades** necesarios para recuperar los sistemas, datos, infraestructura y servicios tecnológicos afectados por una interrupción significativa.
- **DRP dentro del BCM**: la BCM proporciona el marco para gestionar la continuidad de la organización; el DRP es un **subconjunto especializado** dentro del BCM que se enfoca **exclusivamente en la recuperación tecnológica**. *BCM*: ¿cómo mantengo el negocio funcionando en general? *DRP*: ¿cómo recupero los sistemas de TI que soportan ese negocio?
- **¿El DRP es solo para TI?** Formalmente y por definición, el DRP se aplica a la recuperación de la **infraestructura tecnológica (TI)**. Objetivo: restaurar sistemas de TI (servidores, redes, bases de datos, aplicaciones, comunicaciones) y minimizar el impacto de fallas tecnológicas en la operación. Las otras áreas críticas (operaciones, RR.HH., atención al cliente, logística, etc.) **sí deben estar cubiertas, pero no por el DRP, sino por el plan general de Continuidad del Negocio (BCP o BCM)**. **BCP** = cómo mantener o recuperar las actividades prioritarias del negocio. **DRP** = cómo recuperar los recursos y servicios tecnológicos que las soportan.

## 5. Elementos clave del DRP (9 componentes esenciales)
Objetivo del plan → Alcance → Análisis de Impacto al Negocio (BIA) → Estrategias de recuperación → Roles y responsabilidades → Procedimientos de respuesta y recuperación → Plan de comunicaciones → Plan de pruebas → Mantenimiento y actualización del plan.

### 1. Objetivo del plan
Recuperar los sistemas, datos, infraestructura y servicios tecnológicos afectados por una **interrupción significativa**, de acuerdo con las **prioridades y objetivos de recuperación** establecidos por el negocio.

### 2. Alcance del plan
Delimita **qué se protege y recupera** dentro del DRP: servidores, bases de datos, redes, aplicaciones críticas.

### 3. Análisis de Impacto al Negocio (BIA)
Permite identificar las actividades prioritarias, analizar los impactos de su interrupción y establecer sus **requisitos de recuperación**, que a su vez determinan las necesidades de recuperación de los recursos tecnológicos que las soportan. **RTO**: objetivo de tiempo para reanudar una actividad o servicio a un nivel previamente definido. **RPO**: máxima pérdida de datos tolerable, expresada en tiempo.
**Ejercicio: 5 sistemas de la universidad UTP (resuelto)**
| Sistema | Prioridad | ¿Por qué? | RTO | RPO |
|---|---|---|---|---|
| Plataforma de matrícula | **Alta** | Su indisponibilidad impide realizar procesos académicos esenciales relacionados con la matrícula y el registro de estudiantes | **2 h** | **15 min** |
| Correo institucional | **Media** | Su indisponibilidad afecta la comunicación y coordinación institucional, aunque temporalmente pueden utilizarse canales alternativos | **8 h** | **4 h** |
| Página web institucional | **Media** | Limita el acceso a información y servicios institucionales, aunque varias actividades internas pueden continuar | **12 h** | **24 h** |
| Sistema de nóminas | **Alta** | Puede impedir el procesamiento oportuno de remuneraciones y generar impactos laborales y administrativos | **12 h** | **4 h** |
| Aplicación de biblioteca | **Baja** | Afecta servicios académicos de apoyo, pero permite un mayor tiempo de recuperación frente a los sistemas anteriores | **48 h** | **24 h** |
*¿Por qué es importante?* El BIA establece las prioridades y requisitos de recuperación de las actividades del negocio; a partir de ellos se determinan las necesidades de recuperación de los sistemas tecnológicos.

### 4. Estrategias de recuperación
Alternativas, recursos y mecanismos definidos para recuperar los sistemas, datos, infraestructura y servicios tecnológicos de acuerdo con los objetivos de recuperación.
- **4.1 Respaldos (backups)**: copias de seguridad de los datos y configuraciones necesarias para su recuperación. **Local**: se almacenan en infraestructura de respaldo de la propia organización (servidores o dispositivos de almacenamiento locales). **En la nube**: se almacenan en la infraestructura de un proveedor de servicios cloud, permitiendo copias fuera de la infraestructura física principal. *Ejemplo*: una universidad realiza respaldos automáticos de la BD de su sistema de matrícula con una frecuencia definida de acuerdo con su **RPO**.
- **4.2 Sitios alternos**: instalaciones preparadas para continuar las operaciones si la sede principal queda inoperativa. Se clasifican por su nivel de preparación:
  | Tipo | Preparación | Recuperación relativa | Costo relativo |
  |---|---|---|---|
  | **Hot site** | Equipado y preparado para asumir rápidamente la operación | Muy rápida | Alto |
  | **Warm site** | Infraestructura disponible, requiere configuración/restauración | Intermedia | Medio |
  | **Cold site** | Infraestructura básica; requiere mayor preparación | Más lenta | Bajo |
  *Ejemplo*: un banco dispone de un sitio caliente en otra ciudad, equipado con la infraestructura tecnológica necesaria y preparado para asumir rápidamente la operación si el sitio principal queda inoperativo.
- **4.3 Redundancia de servicios**: disponer de recursos tecnológicos adicionales o alternativos que puedan utilizarse cuando el recurso principal falla, reduciendo la interrupción del servicio. **Redundancia en servidores** (servidores adicionales que asuman el servicio si falla el principal) · **redundancia de red** (más de una línea de internet o proveedor) · **redundancia geográfica** (infraestructura duplicada en distintas ubicaciones físicas). *Ejemplo*: Amazon tiene data centers redundantes en distintas partes del mundo; si uno falla, otro toma su lugar sin que el usuario lo note.

### 5. Roles y responsabilidades
En un DRP deben definirse claramente los roles, responsabilidades y **niveles de autoridad** necesarios para coordinar y ejecutar la recuperación tecnológica. (Estructura: Nivel estratégico — Alta Dirección y Responsable de Seguridad de la Información; Nivel táctico y de apoyo — Coordinador del DRP y Responsable de Comunicaciones; Nivel operativo — Equipo de TI.)
- **Alta Dirección**: tomadores de decisiones estratégicas; aprueban recursos para la recuperación; evalúan impactos legales, financieros y de reputación; toman decisiones estratégicas y autorizan acciones de acuerdo con los niveles de autoridad establecidos.
- **Coordinador del DRP**: líder del proceso de recuperación; se encarga de **activar el plan y supervisar su ejecución**; evalúa la situación y gestiona la activación del DRP de acuerdo con los criterios y niveles de autoridad; coordina a los distintos equipos; informa avances a la alta dirección; verifica que los procedimientos del DRP se sigan correctamente.
- **Equipo de TI**: equipo técnico que ejecuta la recuperación de los sistemas; restaura servidores, bases de datos y redes; restaura datos a partir de los respaldos disponibles; configura sistemas y accesos; trabaja en el sitio alterno si es necesario.
- **Responsable de Comunicaciones**: encargado de la comunicación interna y externa durante y después del incidente; coordina y difunde la información autorizada a las partes interesadas; emite comunicados por canales oficiales (web, redes, email); contribuye a mantener información oportuna, clara y coherente durante la recuperación.
- **Responsable de Seguridad de la Información**: contribuye a proteger la confidencialidad, integridad y disponibilidad de la información durante la recuperación; verifica la integridad de la información restaurada; controla los accesos a los sistemas críticos; evalúa posibles incidentes o vulneraciones de seguridad y gestiona su reporte.

### 6. Procedimientos de respuesta y recuperación
Instrucciones documentadas que establecen las acciones que deben ejecutar los equipos responsables para responder a la interrupción y recuperar los sistemas, datos, infraestructura y servicios afectados. Secuencia: **Evaluar → Activar → Recuperar → Verificar → Restablecer**.

### 7. Plan de comunicaciones
Establece **quién comunica, qué información se comunica, a quién, por qué canales y en qué momento** durante la recuperación. Procedimientos formales para (1) informar internamente a colaboradores y equipos responsables sobre lo que ocurre y qué acciones tomar; (2) informar externamente a usuarios/clientes (p. ej. estudiantes), proveedores y autoridades regulatorias (si aplica).
| Elemento | Ejemplo / explicación |
|---|---|
| Responsables de comunicar | Área de comunicaciones institucionales o el Coordinador DRP |
| Audiencias internas | Personal de TI, gerentes, directivos, personal clave |
| Audiencias externas | Clientes, estudiantes, proveedores, medios, autoridades |
| Medios de comunicación | Correo institucional, mensajería SMS, intranet, redes sociales, llamadas telefónicas |
| Frecuencia de mensajes | Definida según la evolución y necesidades de información durante la recuperación |
| Mensajes predefinidos | Plantillas preparadas para emergencias: "Estamos trabajando para restablecer el servicio…" |
*Ejemplo*: la plataforma virtual de una universidad se cae por una falla eléctrica mayor justo antes de los exámenes finales. Responsable: área de comunicaciones. Mensaje inicial: "Por causas técnicas ajenas a nuestro control, el sistema estará inoperativo por las próximas horas. Estamos ejecutando el plan de recuperación. Se informará en breve el nuevo cronograma." Canales: página web, redes sociales, correo masivo. Actualizaciones: cada 4 horas hasta la normalización.

### 8. Plan de pruebas
Parte fundamental que permite **evaluar si el DRP puede ejecutarse eficazmente y detectar oportunidades de mejora**. Ejercicios y simulacros para: verificar que los procedimientos funcionan; evaluar si los responsables saben qué hacer; evaluar el cumplimiento de los objetivos de recuperación (RTO y RPO); identificar debilidades o aspectos a mejorar.
| Tipo de prueba | Descripción |
|---|---|
| **Tabletop o prueba de escritorio** | Solo se revisa el DRP con los equipos en una reunión; no se interrumpe nada real |
| **Prueba técnica** | Se prueba un componente específico (p. ej. restaurar un servidor de respaldo) |
| **Simulación parcial** | Se simula un desastre real y se siguen todos los pasos como si estuviera ocurriendo |
| **Simulación completa** | Se interrumpe intencionalmente un sistema o servicio real (usualmente fuera de horario) para ver si el DRP responde correctamente |
**Un buen plan de pruebas incluye**: objetivo de la prueba (p. ej. medir tiempos de recuperación) · sistemas y procesos que serán probados · fecha y frecuencia (cada 6 meses, anual, etc.) · responsables y equipos involucrados · criterios de éxito · formato para registrar hallazgos, tiempos y oportunidades de mejora · plan de acción posterior (para corregir errores detectados).
*Ejemplo*: la universidad hace una **prueba parcial**: se simula una caída del sistema de notas por 1 hora; el equipo TI ejecuta los pasos del DRP; se mide cuánto tarda en restaurarlo desde un respaldo; al final se evalúa el tiempo de recuperación alcanzado y la pérdida de datos producida, comparándolos con el RTO y RPO establecidos.

### 9. Mantenimiento y actualización del plan
El DRP **no debe ser un documento estático**: sistemas, procesos, tecnologías y personal cambian, por lo que debe revisarse y actualizarse periódicamente. Incluye: **1 Revisiones programadas** (frecuencia, p. ej. cada 6 meses o cada año; evaluar si cubre todos los sistemas críticos) · **2 Actualizaciones por cambios** (nuevos servidores, software, personal clave o cambios en procesos; también tras mejoras identificadas en pruebas o incidentes reales) · **3 Lecciones aprendidas** (después de cada prueba o incidente real) · **4 Control de versiones** (registro de qué versión está vigente, con fecha, responsables de la actualización y cambios realizados).
*Ejemplo*: una universidad implementa una nueva plataforma de clases virtuales (sistema crítico): debe actualizar el DRP incluyéndola, definir quién será responsable de su respaldo, incorporar los requisitos de recuperación (RTO y RPO) e incluirla en las pruebas futuras.

## 6. Caso práctico: Instituto ALFA
Resuelto en [[EJ_S09_DRP_y_Gobierno]].

## Pregunta de cierre
Si tuvieran que definir un DRP con TRES palabras clave: ejemplo → **plan, recuperación, tecnología** (o: documentado, TI, RTO/RPO).

## Conclusiones del docente
- El DRP es clave para que la organización se recupere rápidamente tras un desastre y mantenga sus servicios críticos, protegiendo operaciones y reputación.
- Tener un DRP no es opcional: es vital para garantizar la continuidad y la confianza ante cualquier crisis.

## Ojo en el examen
- DRP = solo **TI** (subconjunto del BCM); BCP cubre el negocio; fases del BCM y dónde entra el DRP (se diseña la estrategia en la fase 3, se redacta en la 4, se valida en la 5).
- **9 elementos**; ejemplo de los 5 sistemas UTP (RTO/RPO).
- Hot/warm/cold; backups local vs nube; 3 tipos de redundancia.
- Procedimiento: **Evaluar → Activar → Recuperar → Verificar → Restablecer**.
- 4 tipos de prueba (tabletop, técnica, parcial, completa) y qué incluye un buen plan de pruebas; 4 acciones de mantenimiento.
