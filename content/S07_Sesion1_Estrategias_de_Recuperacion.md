---
tags: [clase, continuidad-del-negocio, semana7, estrategias]
fuente: SEM 7/SESION 1 (PDF S07_s13 completo, texto + diapositivas gráficas)
---
# S07-1 · Estrategias de recuperación acordes con las necesidades reales del negocio
Ejercicios: [[EJ_S07_Estrategias_de_Recuperacion]]

## Logro y gancho
Formular estrategias de recuperación alineadas a las necesidades reales de la empresa, considerando la criticidad de los procesos y los recursos disponibles.
Pregunta: antes de definir una estrategia de recuperación, ¿qué información de la organización necesitamos conocer? → procesos prioritarios y sus requisitos (RTO/RPO/MTPD), recursos y dependencias, capacidad real de recuperación y riesgos que podrían provocar la interrupción.
**Importancia**: estrategias alineadas con las necesidades reales permiten responder ante una interrupción y recuperar las actividades prioritarias dentro de los requisitos establecidos, reducir el impacto, usar eficientemente los recursos y contribuir a la continuidad.
Contenido: estrategias de recuperación · información necesaria para definirlas · alineamiento con las necesidades del negocio · alternativas y estrategias de recuperación · selección · ejemplos aplicados · actividad en clase.

## 1. ¿Qué es una estrategia de recuperación?
- **Definición**: conjunto de **acciones y soluciones planificadas previamente** que una organización establece para **recuperar o reanudar sus actividades prioritarias y los recursos que las soportan**, dentro de los requisitos de recuperación definidos por el negocio, ante una interrupción.
- **Las estrategias de recuperación buscan**: (1) restablecer las actividades y procesos prioritarios dentro de los tiempos establecidos; (2) cumplir los requisitos de recuperación definidos (RTO, RPO); (3) reducir el impacto de la interrupción y favorecer la continuidad de las operaciones.
- Son la **base para desarrollar los planes y procedimientos de continuidad y recuperación**: BCP (Plan de Continuidad del Negocio) y DRP (Plan de Recuperación ante Desastres). **Propósito**: que las actividades prioritarias sean recuperadas dentro de los requisitos del negocio (RTO y RPO) usando alternativas y recursos adecuados.
- **Secuencia**: ① **Alternativas de recuperación** (se identifican y evalúan diferentes opciones) → ② **Selección de la estrategia** (se elige la más adecuada según las necesidades del negocio) → ③ **Procedimientos para ejecutarla** (se definen las acciones detalladas para su implementación). Una estrategia bien definida permite una recuperación efectiva y alineada con el negocio.

## 2. ¿Qué debemos considerar para definir las estrategias? (4 elementos)
1. **Procesos y actividades prioritarias y sus requisitos de recuperación (RTO/RPO)**: identificar las actividades críticas del negocio y definir el tiempo máximo de interrupción aceptable (RTO) y la pérdida de información tolerable (RPO).
2. **Recursos y dependencias necesarias para su operación**: determinar qué recursos (personas, tecnología, instalaciones, proveedores, entre otros) y qué dependencias son necesarios para que los procesos y actividades funcionen.
3. **Capacidad real de recuperación de esos recursos**: evaluar qué tan rápido y en qué condiciones se pueden recuperar o restablecer los recursos identificados, considerando las opciones disponibles (backup, redundancia, sitio alterno, nube, etc.).
4. **Riesgos que podrían provocar la interrupción**: analizar los riesgos (naturales, tecnológicos, humanos, entre otros) que podrían afectar la disponibilidad de los procesos y recursos, para definir estrategias de recuperación adecuadas.
Considerar estos elementos permite seleccionar y diseñar estrategias **realistas y alineadas** con los objetivos del negocio.

### Procesos críticos y tiempos (RTO y RPO)
Primero se identifican los procesos y actividades críticas y se establecen sus requisitos de recuperación, principalmente RTO y RPO. **RTO** (objetivo de tiempo de recuperación): tiempo establecido para recuperar y reanudar una actividad o proceso después de una interrupción. **RPO** (objetivo de punto de recuperación): máxima pérdida de datos que la organización puede tolerar, expresada en tiempo. Ejemplo: el negocio establece como objetivo recuperar el sistema de pedidos online en un máximo de 2 horas (RTO = 2 horas) y que la pérdida de datos no debe ser mayor a 15 minutos (RPO = 15 minutos).
| Proceso / actividad | RTO | RPO |
|---|---|---|
| Pedidos online | 2 h | 15 min |
| Facturación | 4 h | 1 hora |
| Gestión de clientes | 8 h | 4 horas |
| Reportes gerenciales | 24 h | 24 horas |
El RTO y el RPO se definen a partir de las necesidades del negocio y los resultados del **BIA**.

### Recursos implicados en los procesos críticos (5 grupos)
Para que un proceso crítico pueda recuperarse es necesario identificar todos los recursos que intervienen en su operación y sus dependencias: **1 Infraestructura tecnológica** (servidores, redes, almacenamiento, equipos de comunicaciones, software) · **2 Personas** (personal clave para la operación y recuperación del proceso: usuarios, operadores, especialistas, equipos de soporte) · **3 Recursos físicos e instalaciones** (oficinas, centros de datos, instalaciones, energía eléctrica, climatización, seguridad física) · **4 Información y datos** (bases de datos, archivos, configuraciones, documentación, propiedad intelectual y demás información necesaria) · **5 Proveedores y servicios externos** (proveedores de tecnología, servicios en la nube, telecomunicaciones, servicios logísticos, tercerización de procesos). La recuperación efectiva requiere asegurar la disponibilidad de todos los recursos y la gestión de sus dependencias.

### Capacidad real de recuperación de los recursos
Evaluar **qué tan rápido y en qué condiciones** se pueden recuperar o restablecer los recursos, y si la capacidad actual puede satisfacer los requisitos (RTO y RPO). Se evalúa: tiempos de recuperación actuales, recursos y medios disponibles, dependencias con otros recursos, restricciones (técnicas, operativas, contractuales). *Ejemplo*: el negocio requiere recuperar el sistema de pedidos online en 2 horas (RTO = 2 h), pero la capacidad actual de restauración es de 5 horas.
| Recurso | RTO requerido | Capacidad actual de recuperación | ¿Satisface? |
|---|---|---|---|
| Servidores de aplicaciones | 2 h | 5 h | No |
| Base de datos | 2 h | 4 h | No |
| Red y comunicaciones | 2 h | 2 h | Sí |
| Personal clave | 2 h | 1 h | Sí |
**Brecha de recuperación = 3 horas (5 h – 2 h).** Si la capacidad actual no satisface los requisitos, se deben implementar estrategias de recuperación para cerrar la brecha.

### Riesgos que pueden provocar la interrupción
Se consideran los riesgos previamente identificados y evaluados que podrían afectar las actividades prioritarias y sus recursos (internos y externos): fallas eléctricas, ciberataques, fallas de hardware, indisponibilidad de personal, incendios, inundaciones, fallas de proveedores, otros eventos (naturales, tecnológicos, sociales). Conocer estos escenarios permite seleccionar estrategias adecuadas frente a las posibles causas de interrupción.

### Brecha entre necesidad y capacidad
La **brecha de recuperación** se determina comparando **lo que el negocio necesita (RTO/RPO)** con la **capacidad actual de recuperación** de los recursos. Ejemplo: necesidad del negocio (RTO) 2 horas **−** capacidad actual 5 horas **=** brecha de recuperación 3 horas (la capacidad actual es 3 horas mayor al requisito del negocio). ¿La capacidad actual permite cumplir el RTO? **No**: necesitamos evaluar alternativas que reduzcan esta brecha. La identificación de la brecha permite definir y seleccionar estrategias adecuadas.

## 3. Alternativas de recuperación para cerrar la brecha
Dependen del **análisis de factibilidad, costos y riesgos**:
| Alternativa | Descripción | Beneficio potencial | Consideraciones |
|---|---|---|---|
| **Backup en la nube** (AWS S3, Azure, etc.) | Disponer de respaldos externos para restaurar la información según la capacidad de recuperación implementada | Protege la información y facilita su recuperación | El tiempo de recuperación depende del volumen de datos, la configuración y los procedimientos de restauración |
| **Sitio alterno (Hot Site)** | Infraestructura totalmente operativa y sincronizada (en otra ubicación) | Puede reducir significativamente el tiempo de recuperación, dependiendo de la configuración del ambiente alterno | Mayor costo de implementación y mantenimiento |
| **Sitio alterno (Warm Site)** | Infraestructura parcial; requiere algunos procesos de activación y configuración | Reduce el tiempo de recuperación en comparación con un sitio frío | Costo medio; requiere tareas de habilitación y pruebas periódicas |
| **Sitio alterno (Cold Site)** | Infraestructura básica (espacio físico, energía y conectividad); se instala y configura cuando se requiere | Permite la recuperación del servicio con un menor costo, pero con mayor tiempo de recuperación | Menor costo pero mayor tiempo; requiere instalación y configuración de equipos y software |
| **Replicación de datos** (en tiempo real o programada) | Copia de datos a un sitio alterno de forma continua o periódica | Disminuye la pérdida de información (RPO) y facilita la recuperación | Requiere enlaces de comunicación y almacenamiento en el sitio alterno |
| **Recursos alternos** (personal, proveedores, etc.) | Disponibilidad de personal clave, proveedores alternos o servicios de continuidad | Permite continuar o reanudar la operación | Requiere acuerdos, contratos, capacitación y pruebas periódicas |
La selección de la alternativa más adecuada debe estar alineada con los requisitos del negocio, el análisis de costos, riesgos y la factibilidad de implementación.

## 4. ¿Por qué deben alinearse con las necesidades reales del negocio?
Las estrategias deben estar alineadas con los objetivos del negocio, **evitando sobrecostos y priorizando lo verdaderamente crítico**. Cuatro razones:
1. **Evitar sobrecostos innecesarios**: no todos los procesos requieren el mismo nivel de recuperación; implementar soluciones con una capacidad superior a la necesaria puede generar costos innecesarios y un uso ineficiente de recursos.
2. **Priorizar lo verdaderamente crítico**: enfocar en las actividades prioritarias (mayor valor e impacto significativo por interrupción), concentrando esfuerzos y recursos en lo que realmente importa para la continuidad.
3. **Cumplir los requisitos de recuperación**: la estrategia debe permitir alcanzar el **RTO** establecido, evitando que la interrupción se prolongue hasta superar el **MTPD**. El servicio debe restablecerse dentro del RTO y siempre antes de alcanzar el MTPD (línea: interrupción → RTO (objetivo de recuperación, margen de recuperación) → MTPD (límite de tolerancia)).
4. **Optimizar el uso de recursos**: conociendo las necesidades de recuperación, los recursos tecnológicos, humanos, físicos y financieros pueden asignarse de manera más eficiente, priorizando lo que realmente aporta valor para la continuidad.
Alinear la estrategia significa proporcionar a cada proceso la capacidad que realmente necesita.

### Ejemplo: estrategia alineada y no alineada
Empresa de desarrollo de software; proceso: plataforma de soporte técnico para clientes; **MTPD = 2 horas** (el negocio no puede tolerar una interrupción mayor); **RTO = 1 hora**.
- **Estrategia alineada**: servidor redundante con datos replicados y mecanismo de **failover** que permite recuperar el servicio dentro del RTO de 1 hora → **cumple el RTO (1 h)**, **no supera el MTPD (2 h)** y permite continuar la atención a los clientes.
- **Estrategia no alineada**: depender únicamente de una restauración manual desde una copia de respaldo que requiere ~5 horas → **no cumple el RTO (1 h)**, **supera el MTPD (2 h)**; el cliente queda sin atención, se afecta el contrato y la confianza en la empresa.

## 5. Características de una estrategia efectiva (5)
Permite alcanzar los objetivos de continuidad de manera realista, eficiente y sostenible: **1 Alineada con las necesidades del negocio** (basada en los requisitos de recuperación (RTO, RPO y MTPD) determinados a partir del BIA y complementados con el análisis de riesgos y la capacidad de recuperación de la organización) · **2 Considera los recursos** (realista y viable: disponibilidad de recursos tecnológicos, humanos, físicos y financieros) · **3 Prioriza procesos críticos** (concentra esfuerzos e inversión en los procesos con mayor impacto en la continuidad, asegurando las actividades esenciales) · **4 Escalable y adaptable** (puede ajustarse ante cambios en el negocio, nuevos riesgos, avances tecnológicos o variaciones en los requisitos de recuperación) · **5 Se prueba y se actualiza** (se valida mediante pruebas de continuidad —p. ej. *tabletop*, técnica, simulación— y se revisa y actualiza periódicamente para asegurar su efectividad). Una estrategia efectiva combina **lo que el negocio necesita, lo que la organización puede hacer y lo que debe proteger**.

## 6. Clasificación de las estrategias de recuperación (dos criterios complementarios)
- **A. Según los requisitos de recuperación del proceso (RTO/RPO)**: relaciona las alternativas con la rapidez y capacidad de recuperación que requiere el negocio; permite determinar de inmediato el nivel de exigencia de la estrategia, asegurar que se cumplan los objetivos de recuperación y evitar que la interrupción supere el MTPD.
- **B. Según el tipo de recurso involucrado**: organiza las estrategias según los recursos que deben recuperarse o mantenerse disponibles para restablecer el proceso; facilita la identificación de los recursos críticos, ayuda a definir alternativas de recuperación por cada tipo de recurso y permite una asignación más eficiente de los recursos.

### A. Según RTO/RPO
| Nivel de recuperación | Características del proceso | Ejemplos de procesos | Alternativas |
|---|---|---|---|
| **RTO muy corto** (minutos – pocas horas); **RPO muy bajo** | Procesos críticos para la operación y generación de ingresos; su interrupción afecta significativamente el negocio; requieren alta disponibilidad y mínima pérdida de datos | Plataforma web de atención a clientes, sistema de pagos online, servidores de base de datos, servicios médicos | Redundancia de infraestructura, replicación en tiempo real, failover automático, sitio alterno activo (hot site) |
| **RTO medio** (horas – 1 a 2 días); **RPO moderado** | Procesos importantes pero no críticos; su interrupción genera impacto moderado y puede ser asumido temporalmente; se tolera una recuperación en un plazo razonable | Herramientas de gestión de proyectos (JIRA, Trello), sistema de control de calidad, aplicaciones de recursos humanos | Alternativas intermedias (sitio tibio / warm site, respaldos frecuentes, restauración desde backups con mayor rapidez) |
| **RTO amplio** (varios días); **RPO alto** | Procesos de baja criticidad; su interrupción tiene un impacto limitado; pueden recuperarse en un plazo más amplio | Sistema de reportes históricos, ambientes de desarrollo y pruebas, archivos y documentación interna | Restauración desde backups, sitio alterno pasivo (cold site), recuperación manual, uso de recursos compartidos |
Regla: **a menor RTO/RPO se requieren alternativas con mayor capacidad de recuperación; a mayor RTO/RPO pueden utilizarse alternativas menos inmediatas.**
- *Ejemplo 1 (proceso crítico)*: plataforma de atención a clientes, RTO 30 minutos, RPO 5 minutos → sitio espejo (mirror site), failover automático, replicación en tiempo real, infraestructura redundante.
- *Ejemplo 2 (proceso no crítico)*: sistema de gestión de recursos humanos, RTO 24 horas, RPO 4 horas → restauración desde backups, sitio alterno pasivo (cold site), recuperación manual, uso temporal de recursos compartidos.

### B. Según el tipo de recurso involucrado
Recursos: **Tecnología (TIC)** (equipos, redes, sistemas y plataformas tecnológicas) · **Personas** (personal clave que opera y da soporte a procesos críticos) · **Instalaciones** (sedes, oficinas, centros de datos u otras infraestructuras físicas) · **Información** (datos y documentos necesarios para continuar con las operaciones) · **Procesos** (procedimientos y actividades clave para la operación del negocio) · **Proveedores y terceros** (proveedores de servicios, tecnología o insumos críticos). Ejemplos de alternativas: TIC: sitio alterno (hot/warm/cold), replicación de servidores, failover en la nube, restauración desde backups · Personas: plan de relevo de personal, trabajo remoto, personal externo o *cross-training* · Instalaciones: sitio alterno, espacios temporales, recuperación gradual de instalaciones, acuerdos de alquiler de espacios · Información: backups periódicos, replicación de datos, almacenamiento en la nube, uso de medios inmutables · Procesos: procedimientos manuales, procesos alternos o simplificados, priorización de procesos, automatización temporal · Proveedores: proveedores alternos, acuerdos de nivel de servicio (SLA) con continuidad, inventario de proveedores críticos, estrategia de multi-sourcing.
- **Estrategias tecnológicas** (se apoyan directamente en recursos tecnológicos; recuperan o mantienen disponibles sistemas, redes, aplicaciones y bases de datos; **recurso principal: tecnología e infraestructura digital**). Incluyen:
  1. **Backups automáticos y verificados**: copias de seguridad realizadas sin intervención humana y validadas automáticamente para asegurar que se pueden restaurar correctamente; permiten recuperar la información ante su pérdida o corrupción. *Ejemplo*: un sistema que cada día guarda automáticamente los datos en una ubicación segura en la nube y verifica la integridad del backup.
  2. **Servidores redundantes (clustering)**: varios servidores funcionando en paralelo, preparados para asumir el servicio ante la falla del servidor principal; con mecanismos de **failover** reducen significativamente el tiempo de interrupción. *Ejemplo*: en un clúster de base de datos, si un nodo falla, otro nodo disponible puede asumir el servicio mediante el failover configurado.
  3. **Replicación en tiempo real en nubes alternas**: mantiene copias sincronizadas de datos (según la solución implementada, de otros componentes necesarios para operar); puede ser continua o periódica, en una infraestructura alternativa (otra nube o centro de datos); permite reducir la pérdida de datos (RPO bajo) y facilita una recuperación más rápida (RTO bajo). *Ejemplo*: los datos de una aplicación se replican en tiempo real hacia una infraestructura alternativa para disponer de información actualizada ante una falla.
  4. **Virtualización y recuperación de máquinas virtuales**: permite disponer de máquinas virtuales preconfiguradas que pueden facilitar una recuperación más rápida ante una falla; se pueden mantener imágenes de máquinas virtuales en repositorios seguros para su despliegue en la infraestructura alternativa; reduce el tiempo de recuperación de servidores y aplicaciones al contar con entornos previamente preparados. *Ejemplo*: ante la falla de una máquina virtual, se inicia una VM alternativa previamente preparada, permitiendo restablecer el servicio en menor tiempo.
- **Estrategias organizativas** (alternativas basadas en la organización del personal, los roles y los procedimientos que permiten continuar o recuperar una actividad mediante formas alternativas de operación; **recurso principal: personas, roles y procedimientos**):
  - **Reasignación de personal y roles**: definir personal alterno o reasignar funciones críticas ante la ausencia de personal clave; se apoya en la identificación de personal multifuncional y en planes de sucesión. *Ejemplo*: ante la indisponibilidad del administrador de TI, un técnico alterno asumirá temporalmente los servicios operativos.
  - **Procedimientos alternativos (manuales)**: definir y documentar procedimientos simplificados o alternativos para realizar actividades esenciales hasta que los sistemas estén disponibles; permite operaciones esenciales del negocio hasta la recuperación de los sistemas. *Ejemplo*: si el sistema de registro no está disponible, se utiliza un formato manual para registrar las transacciones y luego se cargan al sistema.
  - **Equipos de respuesta y coordinación**: establecer y capacitar equipos responsables de coordinar la recuperación de los procesos críticos (p. ej. equipo de gestión de continuidad, comité de crisis); permite una respuesta organizada y oportuna ante una interrupción. *Ejemplo*: el Equipo de Gestión de Continuidad coordina las acciones de recuperación, la comunicación interna y la ejecución de los planes.
- **Estrategias logísticas** (se enfocan en la disponibilidad de instalaciones, espacios físicos y el apoyo de proveedores externos para mantener o recuperar las operaciones del negocio; **recurso principal: instalaciones, ubicación y proveedores externos**):
  - **Uso de sitio alterno**: disponer de un lugar alternativo para operar la organización en caso de que las instalaciones críticas no estén disponibles; puede ser un sitio propio o contratado, con la infraestructura y servicios necesarios para continuar las operaciones críticas. *Ejemplo*: ante un desastre natural que inhabilita la sede principal, la empresa traslada sus operaciones críticas a un sitio alterno previamente equipado.
  - **Teletrabajo planificado**: habilitar al personal para que pueda continuar trabajando de forma remota durante una interrupción; requiere contar con herramientas tecnológicas, accesos seguros, políticas y procedimientos previamente definidos. *Ejemplo*: durante una emergencia que impide el acceso a la oficina, los colaboradores trabajan de forma remota utilizando herramientas y VPN habilitadas por la empresa.
  - **Acuerdos con proveedores y terceros**: establecer con proveedores alternativos o terceros estratégicos para asegurar el suministro de bienes o servicios críticos; permite mantener las operaciones cuando el proveedor principal no puede cumplir debido a una interrupción. *Ejemplo*: la empresa cuenta con un proveedor alternativo de servicios de Internet que puede activar el servicio ante una falla del proveedor principal.
- **Ejemplo integrado** (plataforma de ventas de una empresa de e-commerce fuera de servicio por una falla en el centro de datos principal; objetivo: restablecer el servicio de ventas en el menor tiempo posible minimizando el impacto en los clientes): *Tecnológicas* — activación de la réplica de la aplicación en línea en una nube alternativa; restauración de la BD desde copias de seguridad verificadas; uso de balanceador de carga para redirigir el tráfico al entorno alterno. *Organizativas* — activación del equipo de continuidad del negocio y asignación de responsabilidades; ejecución de procedimientos alternos de atención al cliente (canales manuales o telefónicos); comunicación interna y externa sobre la situación y las acciones de recuperación. *Logísticas* — habilitación de un sitio alterno de trabajo para el personal crítico (si es necesario); ejecución del plan de teletrabajo para las áreas que pueden operar de forma remota; coordinación con proveedores (p. ej. proveedor de nube o de conectividad) para asegurar recursos adicionales. **La combinación de estrategias tecnológicas, organizativas y logísticas permite una recuperación más efectiva y alineada con las necesidades del negocio.**
- **Ejemplos de estrategias**: *Backup y recuperación de datos* (empresa de desarrollo de software; objetivo: recuperar información ante pérdida de datos o ransomware; **RTO = 4 horas | RPO = 24 horas**; estrategia: respaldos automáticos diarios en la nube y mantener una copia offline periódica). *Alta disponibilidad / redundancia de servidores* (plataforma web de comercio electrónico; objetivo: mantener o recuperar rápidamente el servicio ante la falla de un servidor; estrategia: servidores redundantes en distintas ubicaciones, con mecanismos de distribución de carga o conmutación; beneficio: reduce significativamente la indisponibilidad ante la falla de un componente). *Teletrabajo como estrategia de continuidad* (un terremoto impide utilizar las oficinas; objetivo: continuar actividades sin depender de la sede física; estrategia: activar el trabajo remoto con equipos preparados, herramientas colaborativas y acceso seguro a sistemas críticos). **La elección depende de la criticidad del proceso, los objetivos de continuidad (RTO y RPO) y los recursos disponibles.**

## 7. Alternativas de sitio de recuperación (cold / warm / hot)
El sitio de recuperación es una ubicación física o virtual donde se restablecen los sistemas y las operaciones críticas después de una interrupción.
| | **Cold Site (sitio frío)** | **Warm Site (sitio tibio)** | **Hot Site (sitio caliente)** |
|---|---|---|---|
| Infraestructura | básica (espacio físico, energía, conectividad) | cuenta con infraestructura y algunos equipos preinstalados | infraestructura, equipos, software y datos replicados y listos para operar |
| Equipamiento | no cuenta con equipos ni software instalados; requiere adquisición, instalación y configuración | requiere completar la instalación, configuración y recuperación de datos | permite una recuperación casi inmediata |
| Tiempo de recuperación | el más largo | más rápida que un cold site | muy corto (cumple RTO bajos) |
| Costo | menor costo de implementación y mantenimiento | costo medio de implementación y mantenimiento | mayor costo de implementación y mantenimiento |
| Cuándo | procesos con RTO amplio | RTO medio | se utiliza para procesos críticos del negocio |
| Ejemplo | oficina alterna contratada sin equipamiento, que se habilita cuando ocurre la interrupción | centro de cómputo alterno con servidores listos para ser configurados y donde se restauran los datos de respaldo | centro de datos alterno en otra ubicación geográfica, con replicación en tiempo real y listo para asumir la operación |
**La elección del tipo de sitio depende de la criticidad de los procesos, los requisitos de tiempo de recuperación (RTO y RPO) y el presupuesto disponible.**

## 8. Resumen de alternativas y estrategias de recuperación
Pueden combinarse según las necesidades del negocio, la criticidad de los procesos y los recursos disponibles: **Sitio de recuperación** (uso de un sitio físico alterno —hot, warm o cold— para restablecer las operaciones; permite recuperar servicios críticos según los requisitos de tiempo de recuperación) · **Trabajo remoto (teletrabajo)** (habilitación del trabajo remoto para el personal crítico; permite mantener actividades desde ubicaciones alternas) · **Backup y restauración de datos** (respaldos periódicos de la información; permite recuperar datos ante pérdidas, fallas o ataques como ransomware) · **Alta disponibilidad y redundancia** (servidores redundantes y balanceo de carga; reduce significativamente la indisponibilidad ante la falla de un componente) · **Uso de soluciones en la nube** (infraestructura o servicios cloud para la recuperación o continuidad de las operaciones; escalabilidad, flexibilidad y acceso remoto) · **Tercerización temporal de funciones** (contratación temporal de un proveedor externo para mantener actividades del negocio mientras se restablece el entorno principal) · **Equipos de emergencia y reasignación de recursos** (activación de equipos de respuesta y gestión de crisis; reasignación de personal y recursos para atender actividades críticas).

## 9. Actividad de clase: ransomware en una empresa de desarrollo de software (Soluciones SAC)
Resuelto en [[EJ_S07_Estrategias_de_Recuperacion]].

## Preguntas de cierre
- ¿Qué es una estrategia de recuperación? → ver sección 1.
- ¿Qué elementos hay que conocer antes de establecerlas? → los 4 elementos de la sección 2 (procesos prioritarios y requisitos RTO/RPO; recursos y dependencias; capacidad real de recuperación; riesgos).

## Conclusiones del docente
- Las estrategias deben alinearse con las necesidades reales del negocio y los requisitos de recuperación de sus actividades prioritarias.
- La selección considera RTO, RPO, recursos y dependencias, riesgos y la capacidad real de recuperación.
- No todos los procesos requieren la misma estrategia; las alternativas se evalúan y seleccionan según sus requisitos.
- Una estrategia debe definirse previamente y desarrollarse mediante planes y procedimientos para su implementación y ejecución.

## Ojo en el examen
- Los 4 elementos previos a definir una estrategia; brecha = necesidad − capacidad (ej. 5 h − 2 h = 3 h).
- Clasificar alternativas por RTO/RPO (muy corto → hot/replicación/failover; medio → warm/backups frecuentes; amplio → cold/backups/manual) y por recurso (tecnológicas, organizativas, logísticas).
- Hot/warm/cold: infraestructura, tiempo y costo.
- Estrategia alineada: cumple el RTO y no supera el MTPD.
