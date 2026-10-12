---
tags: [clase, continuidad-del-negocio, semana4, BIA]
fuente: SEM 4/SESION 1 (PDF S04_s7 completo, texto + diapositivas gráficas + caso Control Migratorio)
---
# S04-1 · Análisis de Impacto al Negocio (BIA): impactos y métricas de recuperación
Ejercicios: [[EJ_S04_BIA]]

## Logro y gancho
Identificar los tipos de impacto que puede generar la interrupción de los procesos de negocio y analizar los principales requerimientos de recuperación del BIA.
Gancho: gerente de un hospital privado; apagón masivo de 24 h; los generadores solo sostienen luces y soporte vital básico. ¿Cuáles son las 2 áreas más críticas que necesitan solución de continuidad inmediata y qué consecuencias tendría su interrupción? (Respuesta típica: **UCI/soporte vital y quirófanos/emergencias**; también laboratorio/banco de sangre, farmacia con cadena de frío y sistemas de historia clínica; consecuencias: riesgo de muerte, demandas, pérdida de confianza.)
**Importancia**: el BIA permite conocer qué procesos son esenciales, qué consecuencias tendría su interrupción, cuánto tiempo se tolera, qué recuperar primero y qué recursos se necesitan; las decisiones de continuidad se toman en función de necesidades reales, no por intuición.
Contenido: BIA · objetivos principales · tipos de impacto · métricas de recuperación · actividad en clase.

## 1. ¿Qué es el BIA?
- Proceso fundamental dentro de la GCN. Su propósito: **identificar los procesos y funciones del negocio y evaluar las consecuencias que tendría su interrupción** ante diferentes eventos disruptivos.
- Permite **identificar qué procesos requieren mayor prioridad**, analizar **cuánto tiempo puede tolerarse su interrupción** antes de generar consecuencias inaceptables y determinar **los recursos necesarios** para su continuidad y recuperación.

### 5 objetivos principales del BIA
| # | Objetivo | Explicación |
|---|---|---|
| 1 | Identificar los procesos del negocio y determinar su prioridad | No todos los procesos son igual de importantes; el BIA ayuda a reconocer cuáles son esenciales. Ej.: en un hospital, los sistemas médicos son más críticos que la cafetería |
| 2 | Evaluar los impactos de una interrupción | ¿Qué pasa si el proceso falla? ¿Se pierden ventas, se incumple una ley, se afecta la imagen? El BIA evalúa y clasifica esos impactos (financieros, operacionales, legales, reputacionales, etc.) |
| 3 | Establecer prioridades de recuperación | Define qué procesos deben recuperarse primero (priorización) y establece los **tiempos objetivo y límites tolerables de interrupción (RTO y MTD)** para enfocar los recursos de forma estratégica |
| 4 | Identificar los recursos necesarios del negocio | Determina qué recursos (tecnológicos, humanos, físicos, etc.) son necesarios para que un proceso funcione o pueda reactivarse rápidamente |
| 5 | Fundamentar decisiones en planes de continuidad y recuperación | Toda estrategia de recuperación debe basarse en los resultados del BIA, no en suposiciones; es la base para diseñar respuestas realistas y efectivas |

## 2. ¿Qué es un impacto al negocio?
Cualquier **efecto negativo** que sufre una organización cuando uno o varios de sus procesos, servicios o recursos se **interrumpen total o parcialmente** debido a una situación **no planificada** (evento disruptivo).

### 5 categorías de impacto
| Categoría | Ejemplo |
|---|---|
| **Financiero** | Pérdida de ingresos, costos adicionales por recuperación, multas, sanciones, penalidades por contrato |
| **Operacional** | Procesos detenidos, demoras en entregas, congestión de tareas |
| **Legal / Regulatorio** | Incumplimiento de contratos o leyes, pérdida de licencias, demandas |
| **Reputacional** | Clientes pierden la confianza, redes sociales con quejas, daño de imagen |
| **Salud y Seguridad** | Peligro físico para empleados o usuarios (ej. en fábricas u hospitales) |

## 3. Métricas de tiempos de recuperación
Línea de tiempo: **último backup → (RPO) → incidente → activación del plan de contingencia → (RTO) → servicio recuperado (al nivel objetivo) → (WRT) → operación plenamente estable y normal**. **MTPD** abarca desde el incidente hasta el límite máximo de interrupción, tras el cual los efectos de no reanudar serían inaceptables.

### RPO – Recovery Point Objective (punto objetivo de recuperación)
- **¿Qué es?** El **punto en el tiempo** hasta el cual la organización necesita poder **recuperar los datos** después de una interrupción. Determina la **pérdida máxima de información tolerable**, expresada en tiempo.
- **Objetivo**: limitar la pérdida de información a un punto máximo aceptable en el tiempo.
- **Responde**: *¿Cuántos datos, expresados en tiempo, podemos tolerar perder?*
- **Ejemplo**: si ocurre un incidente a las 12:00 y el RPO es de **1 hora**, la organización debe poder recuperar los datos al menos hasta las 11:00; la pérdida máxima tolerada sería aproximadamente 1 hora de información.
- **Importante**: el RPO **no indica cuánto tiempo demora recuperar** el sistema o servicio (eso es el RTO); se refiere únicamente al punto máximo de pérdida de datos tolerable.

### RTO – Recovery Time Objective (tiempo objetivo de recuperación)
- **¿Qué es?** Tiempo objetivo establecido para **reanudar un proceso, producto o servicio** después de una interrupción, **a un nivel de operación previamente definido**. Indica qué tan rápido necesita la organización recuperar dicho proceso o servicio para cumplir sus objetivos de continuidad.
- **Objetivo**: recuperar el servicio al nivel definido dentro del tiempo establecido.
- **Responde**: *¿En cuánto tiempo necesitamos recuperar este proceso o servicio?*
- **Ejemplo**: si el RTO de un sistema de ventas online es de **4 horas**, significa que debe reanudar el servicio al nivel de operación definido dentro de las 4 horas posteriores a la interrupción.
- **Importante**: recuperar al nivel objetivo no necesariamente significa haber regresado a la infraestructura original ni estar al 100% de la operación; puede lograrse mediante soluciones o recursos alternativos.

### WRT – Work Recovery Time (tiempo de recuperación del trabajo)
- **¿Qué es?** El **tiempo adicional** que necesita el proceso **después de alcanzar el RTO** para **completar actividades pendientes, estabilizar la operación** y llevar el proceso al nivel de funcionamiento esperado.
- **Objetivo**: completar pendientes y estabilizar la operación después de recuperar el servicio al nivel objetivo.
- **Responde**: *¿Cuánto tiempo adicional necesitamos, después de recuperar, para estabilizar completamente la operación?*
- **Ejemplo**: un sistema de ventas con RTO de 2 horas; al cumplirse las 2 h ya está disponible (nivel objetivo) y los clientes pueden realizar compras, pero se necesita **1 hora adicional** para procesar operaciones acumuladas, conciliar transacciones pendientes y restablecer funciones secundarias. **WRT = 1 hora.**
- **Importante**: durante el WRT el proceso ya ha sido recuperado al nivel objetivo; las verificaciones indispensables para habilitarlo de forma segura deben haberse realizado dentro del RTO. El WRT se usa para completar pendientes y estabilizar; no significa necesariamente retornar a la infraestructura original.

### MTPD – Maximum Tolerable Period of Disruption (período máximo tolerable de interrupción)
- **¿Qué es?** El **período máximo** durante el cual la organización puede tolerar la interrupción de un proceso o actividad **antes de que los impactos lleguen a ser inaceptables** para el negocio. (Algunas bibliografías usan **MTD – Maximum Tolerable Downtime**; es equivalente.)
- **Objetivo**: definir el límite de tolerancia del negocio, es decir, el tiempo que la organización puede tolerar la interrupción antes de que los impactos sean inaceptables.
- **Responde**: *¿Hasta cuánto tiempo puede tolerar el negocio la interrupción antes de llegar a consecuencias inaceptables?*
- **Ejemplo**: sistema de ventas online con **MTPD de 8 horas**: puede estar interrumpido hasta un máximo de 8 horas; después, los efectos para el negocio serían inaceptables. En el ejemplo: **RTO 2 h + WRT 1 h = 3 horas ≤ MTPD 8 horas** (5 horas de margen).
- **Importante**: el MTPD es un **límite de tolerancia** del negocio, no un objetivo de recuperación. El RTO debe establecerse antes del MTPD, dejando tiempo suficiente para la recuperación. El WRT se usa para completar pendientes y estabilizar la operación después de alcanzar el RTO.

### Diferencia RTO vs MTPD
| Concepto | Qué representa | Idea clave | Ejemplo |
|---|---|---|---|
| **RTO** | Tiempo **objetivo** para reanudar un proceso/servicio después de una interrupción, a un nivel de operación definido | Objetivo de recuperación | 2 horas |
| **MTPD** | Período **máximo** durante el cual la interrupción puede tolerarse antes de que sus impactos sean inaceptables | Límite de tolerancia | 8 horas |
- **Relación**: **RTO + WRT ≤ MTPD** (en el ejemplo: 2 h + 1 h = 3 h ≤ 8 h; margen de 5 h). Más completa: **MTPD ≥ RTO + WRT ≥ RPO**. Nota: los valores de RTO, WRT y MTPD se determinan para cada proceso crítico según su importancia y los impactos identificados en el BIA.

### Consecuencias de superar el RTO
Superar el RTO significa que la organización **no cumplió su objetivo de recuperación**: (1) no se cumple el objetivo de recuperación establecido; (2) los impactos pueden continuar aumentando (operacionales, financieros, reputacionales, legales); (3) se acumula trabajo pendiente y aumenta la dificultad de estabilizar la operación; (4) pueden verse afectados compromisos contractuales (clientes, proveedores, reguladores); (5) aumenta la presión sobre los equipos de recuperación (estrés, sobrecarga, riesgo de errores). **Mensaje clave**: superar el RTO no significa que el negocio haya alcanzado todavía su límite máximo tolerable; significa que no logró recuperarse dentro del tiempo objetivo establecido.

### Consecuencias de superar el MTPD
Superar el MTPD significa que la interrupción **ha sobrepasado el período máximo que la organización considera tolerable**; a partir de ese punto los impactos alcanzan niveles considerados **inaceptables**: impactos operacionales severos (procesos críticos dejan de estar disponibles por un período inaceptable; paralización de funciones esenciales) · consecuencias económicas significativas (se intensifican pérdidas financieras, multas y penalidades, costos adicionales de recuperación y posibles reclamos) · riesgos legales y regulatorios (incumplimiento de leyes, contratos o regulaciones; sanciones, demandas o pérdida de licencias) · daño reputacional crítico (se pierde la confianza de clientes, proveedores, socios y público; daño difícil y costoso de revertir) · impacto en salud, seguridad y vida (en sectores críticos como salud o energía, una interrupción prolongada puede poner en riesgo la seguridad y la vida de las personas). El MTPD marca el límite máximo tolerable; superarlo significa que se alcanzan impactos que la organización considera inaceptables. **Meta: recuperarse y estabilizarse antes de llegar al MTPD (RTO + WRT ≤ MTPD).**

### Resumen de métricas
| Métrica | ¿Qué indica? | Pregunta que responde | Se asocia a |
|---|---|---|---|
| **RPO** | Punto en el tiempo hasta el cual deben poder recuperarse los datos; pérdida máxima tolerable de datos expresada en tiempo | ¿Cuántos datos podemos tolerar perder? | DATOS |
| **RTO** | Tiempo objetivo para reanudar el proceso, producto o servicio al nivel de operación definido | ¿En cuánto tiempo necesitamos recuperarlo? | RECUPERAR |
| **WRT** | Tiempo adicional tras el RTO para completar pendientes y estabilizar la operación | ¿Cuánto tiempo adicional necesitamos para estabilizar la operación? | ESTABILIZAR |
| **MTPD** | Período máximo que puede tolerarse la interrupción antes de que los impactos sean inaceptables | ¿Hasta cuándo podemos tolerar la interrupción? | LÍMITE |
Se definen en el BIA y son la base para las estrategias y planes de continuidad y recuperación.

### Ejemplo de requerimientos de recuperación (distribuidora de medicamentos; valores académicos ilustrativos)
| Proceso | Consecuencia de la interrupción | RTO | RPO | MTPD |
|---|---|---|---|---|
| Sistema de pedidos | Clientes no pueden realizar pedidos; se afectan ventas y satisfacción del cliente | 2 h | 30 min | 8 h |
| Control de inventarios | No se conoce disponibilidad actual de productos; pueden generar quiebres de stock o demoras en entregas | 4 h | 1 h | 12 h |
| Reportes administrativos | Se retrasa la generación de informes y toma de decisiones internas | 8 h | 4 h | 24 h |
- Clave: los procesos con **menor RTO/RPO y menor MTPD** requieren **mayor prioridad de recuperación y más recursos**. En un BIA real, los valores se determinan a partir del análisis de impactos, necesidades del negocio y tolerancia.

## 4. Ejemplo: empresa distribuidora de medicamentos
Distribuye medicamentos a nivel nacional; plataforma web de pedidos, centros de almacenamiento en Lima y Arequipa, red logística propia y convenios con clínicas y hospitales para entregas urgentes. **Escenario:** un corte de energía daña el servidor central de datos y deja fuera de línea el sistema de pedidos y control de inventario durante **10 horas**.
**Análisis de impactos: consecuencias y categorías**
| Proceso | Consecuencias | Categorías |
|---|---|---|
| Sistema de pedidos | No se procesan pedidos; se pierden ventas y se generan reclamos; afecta confianza y satisfacción | Operacional, Financiero, Reputacional |
| Control de inventarios | No se conoce el stock; riesgo de errores en la preparación (productos vencidos o equivocados); posibles incumplimientos normativos | Operacional, Legal/Regulatorio, Salud y Seguridad |
| Envíos urgentes a clínicas y hospitales | Se retrasan entregas críticas de medicamentos; puede comprometer la atención o tratamiento de pacientes; pérdida de confianza de instituciones de salud | Operacional, Salud y Seguridad, Reputacional |
| Call center (atención al cliente) | No puede consultar información ni atender consultas; aumentan quejas y malestar | Operacional, Reputacional |
| Facturación | No se emiten comprobantes de pago; se retrasan obligaciones tributarias y contables; posibles multas y sanciones | Operacional, Financiero, Legal/Regulatorio |
**Recuerda:** un mismo proceso puede generar varios tipos de impacto al mismo tiempo. Identificar que existe un impacto no significa todavía determinar su severidad; en la siguiente sesión se evalúa cómo evolucionan los impactos con el tiempo y se determina la criticidad.

## 5. Caso de estudio: caída del sistema de Control Migratorio (LAP)
Resuelto en [[EJ_S04_BIA]].

## Pregunta de cierre
¿Por qué es importante realizar un BIA antes de establecer las prioridades y requerimientos de recuperación? → porque permite fundamentar con información objetiva qué procesos son críticos, qué impactos generan y en cuánto tiempo (RTO, RPO, WRT, MTPD); evita decidir por intuición o suposición y asigna recursos de forma estratégica.

## Conclusiones del docente
1. El BIA analiza las consecuencias de la interrupción y da información para priorizar la continuidad y recuperación.
2. Una interrupción puede generar varios tipos de impacto a la vez (operacional, financiero, legal/regulatorio, reputacional, salud y seguridad).
3. RTO, RPO, WRT y MTPD son requerimientos distintos: RTO = tiempo objetivo para recuperar; RPO = pérdida tolerable de datos en tiempo; WRT = tiempo adicional para completar y estabilizar; MTPD = límite máximo tolerable.
4. Los impactos no permanecen constantes: pueden aumentar con el tiempo; analizar su evolución permite evaluar la criticidad.

## Ojo en el examen
- Fórmulas: **RTO + WRT ≤ MTPD**; **MTPD ≥ RTO + WRT ≥ RPO**.
- RPO se refiere a datos (no al tiempo de recuperación); WRT ocurre **después** del RTO; MTPD = MTD.
- RTO ≠ volver a la infraestructura original; puede ser una solución alterna.
- Superar el RTO ≠ superar el MTPD.
- Ejemplo numérico del curso: RTO 2 h + WRT 1 h = 3 h ≤ MTPD 8 h.
