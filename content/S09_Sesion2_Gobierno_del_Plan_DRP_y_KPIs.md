---
tags: [clase, continuidad-del-negocio, semana9, DRP, KPI]
fuente: SEM 9/SESION 2 (PDF S09_s18 completo, texto + diapositivas gráficas + caso Fintech Express)
---
# S09-2 · Gobierno del plan en el DRP e indicadores de gestión (KPIs)
Ejercicios: [[EJ_S09_DRP_y_Gobierno]] · Sesión previa: [[S09_Sesion1_DRP_Fundamentos_y_Elementos]]

## Logro y gancho
Identificar los componentes del Gobierno del DRP, su esquema de operación, equipos y actores, roles y responsabilidades y mecanismos de seguimiento y mejora, mediante casos prácticos.
Gancho: ¿cuál es el propósito principal de un DRP dentro de una organización? → recuperar los servicios tecnológicos (sistemas, datos, infraestructura) tras una interrupción significativa, según las prioridades y objetivos de recuperación del negocio.
**Importancia**: el Gobierno del DRP establece cómo se **dirige, supervisa y controla** el plan, definiendo responsabilidades, niveles de autoridad y mecanismos de seguimiento. Contribuye a mantener el DRP **actualizado, alineado con las necesidades del negocio y preparado para su aplicación**.
Contenido: gobierno del plan en el DRP · componentes del gobierno del plan.

## 1. ¿Qué es el Gobierno del Plan en el DRP?
**Definición**: conjunto de **políticas, roles, responsabilidades, niveles de autoridad y mecanismos de control** que permiten **dirigir, supervisar y mantener** el DRP alineado con las necesidades del negocio.
**¿Qué hace?** Establece cómo se dirige, supervisa y controla el plan para: definir quién toma decisiones y quién supervisa; asignar responsabilidades y niveles de autoridad; establecer reglas y mecanismos de control; supervisar las pruebas, revisiones y actualizaciones; mantener el DRP alineado con las necesidades del negocio. En síntesis: establece **quién decide, quién supervisa, quién ejecuta, qué autoridad posee cada responsable y bajo qué reglas se gestiona el DRP**. Cuatro preguntas: **¿Quién decide?** (define los niveles de autoridad para la toma de decisiones relacionadas con el DRP) · **¿Quién supervisa?** (determina quién verifica que el DRP se mantenga preparado, actualizado y alineado con las necesidades del negocio) · **¿Quién ejecuta?** (define los responsables de realizar las acciones de recuperación establecidas en el DRP) · **¿Bajo qué reglas?** (establece las políticas, procedimientos y mecanismos de control que deben seguirse para gestionar el DRP).

### Ejemplo: con y sin Gobierno del Plan
Una empresa de ventas en línea desarrolló su DRP y al cabo de 2 años decide migrar únicamente su **Base de Datos de Ventas a la nube de AWS**, pero mantiene sus **Servidores de Autenticación de Usuarios e internet de forma local** en su Data Center.
- **Escenario SIN gobierno**: la BD se migra a AWS; el cambio tecnológico **no genera una revisión del DRP**; posteriormente un incidente provoca la indisponibilidad de la BD; el equipo activa el DRP pero descubre que los procedimientos documentados corresponden a la **arquitectura anterior**; debe determinar durante el incidente cómo recuperar la BD en la nueva arquitectura. **Resultado: el DRP está desactualizado y se retrasa la recuperación.**
- **Escenario CON gobierno**: el equipo de TI propone migrar la BD a AWS; el cambio se **revisa considerando su impacto sobre el DRP**; se verifica que la nueva solución permita **cumplir los RTO y RPO establecidos**; se actualizan las estrategias y procedimientos de recuperación del DRP; se definen o actualizan los responsables involucrados; la **Alta Dirección aprueba los recursos** necesarios, cuando corresponda; se realiza una **prueba técnica** para validar la recuperación en la nueva arquitectura **antes de retirar la solución anterior**.

## 2. ¿Cómo se organizan las responsabilidades en el gobierno?
La estructura puede variar según el tamaño, complejidad y organización de la empresa. Durante la normalidad operativa permite distribuir responsabilidades para mantener el DRP preparado, actualizado y probado; ante una interrupción que requiera su aplicación, estas responsabilidades orientan la toma de decisiones, la coordinación y la ejecución de la recuperación.
| Nivel | Función |
|---|---|
| **Estratégico** | **Orienta y decide**: define la dirección, establece prioridades y toma decisiones de mayor nivel |
| **Táctico** | **Coordina, supervisa y prepara**: articula la gestión del DRP, supervisa su mantenimiento y prepara su aplicación |
| **Operativo** | **Ejecuta y responde**: realiza las acciones técnicas de recuperación y da soporte operativo |
En cada nivel deben definirse claramente los **roles, responsabilidades, niveles de autoridad y mecanismos de escalamiento**, tanto para la normalidad operativa como para la recuperación.
- **Nivel estratégico – Alta Dirección** (establece la dirección y toma las decisiones estratégicas relacionadas con el DRP; puede participar la Alta Dirección y responsables con autoridad sobre decisiones estratégicas relacionadas con continuidad y recuperación): establecer dirección y prioridades; aprobar políticas relacionadas con continuidad; asignar o aprobar los recursos necesarios; revisar información relevante sobre desempeño, pruebas y auditorías; tomar decisiones que excedan la autoridad de los niveles inferiores. **ORIENTA Y DECIDE.**
- **Nivel táctico – Coordinación del DRP** (articula la gestión del DRP y asegura que se mantenga preparado para su aplicación; lo asume el responsable o coordinador designado): coordinar la revisión y actualización del DRP; organizar y dar seguimiento a las pruebas y ejercicios; coordinar actividades de capacitación relacionadas con el plan; dar seguimiento a indicadores y resultados; coordinar con los equipos técnicos y escalar las decisiones cuando corresponda. **COORDINA, SUPERVISA Y PREPARA.**
- **Nivel operativo – Equipos técnicos de recuperación** (ejecutan las acciones técnicas de recuperación establecidas en el DRP; personal de infraestructura, redes, BD, aplicaciones, seguridad, soporte u otros especialistas): ejecutar los procedimientos técnicos establecidos; recuperar los sistemas, datos e infraestructura asignados; verificar técnicamente el funcionamiento de los servicios recuperados; informar el avance y las incidencias al nivel de coordinación; escalar las situaciones que excedan su autoridad. **EJECUTA Y RESPONDE.**
- **Auditoría interna – equipo de apoyo y soporte (nivel táctico)**: brinda apoyo al Gobierno del Plan mediante la evaluación y verificación del cumplimiento de los controles y disposiciones establecidos para el DRP; verificar el cumplimiento de políticas y procedimientos relacionados con el DRP; revisar evidencias de pruebas, revisiones y actualizaciones del plan; identificar hallazgos y oportunidades de mejora; informar los resultados a los responsables correspondientes; dar seguimiento a las acciones derivadas de los hallazgos. **Auditoría evalúa y verifica; no ejecuta la recuperación.**
- **Roles en la normalidad y durante la recuperación**:
  | Actor / nivel | Durante la normalidad operativa | Durante una interrupción |
  |---|---|---|
  | Alta Dirección (estratégico) | Establece dirección, aprueba políticas y recursos; revisa resultados relevantes | Toma decisiones estratégicas; autoriza acciones que exceden otros niveles |
  | Coordinación del DRP (táctico) | Coordina revisiones, actualizaciones, pruebas y capacitación del DRP; realiza seguimiento a su implementación | Coordina la ejecución del plan; consolida información; gestiona el escalamiento |
  | Equipos técnicos (operativo) | Mantienen su preparación; participan en pruebas; mantienen actualizados los procedimientos técnicos que les corresponden | Ejecutan los procedimientos de recuperación; reportan avances e incidencias |
  | Auditoría (independiente) | Evalúa periódicamente la gestión del DRP y sus evidencias | Su participación dependerá de los mecanismos de evaluación definidos; **no ejecuta la recuperación** |

## 3. Los 3 componentes del Gobierno del DRP (relacionados con ISO 22301)
1. **Componente 1: Política de continuidad y compromiso de la Alta Dirección (Cláusula 5 – ISO 22301)**. *Qué representa*: la orientación y el compromiso de la organización con la continuidad del negocio; la Alta Dirección demuestra liderazgo y compromiso con el SGCN. *Concepto clave*: liderazgo, rendición de cuentas y provisión de los recursos necesarios. *Aplicación al DRP*: facilita la asignación de recursos para las capacidades de recuperación tecnológica; respalda la participación de las áreas involucradas en pruebas, ejercicios, capacitación y mantenimiento del DRP. **Idea clave: el Gobierno del DRP requiere respaldo y dirección desde la Alta Dirección para mantenerse actualizado y preparado para su aplicación.**
2. **Componente 2: Gestión del cambio y actualización del DRP**. *Qué representa*: permite mantener el DRP alineado con los cambios tecnológicos, organizacionales y operativos que puedan afectar su capacidad de recuperación. *Concepto clave*: evitar que las estrategias, procedimientos y recursos de recuperación queden desactualizados. *Cómo se aplica*: evaluar el impacto de cambios relevantes sobre el DRP; actualizar estrategias, procedimientos, responsables y documentación cuando corresponda; verificar mediante pruebas que las capacidades de recuperación continúan siendo efectivas. *Riesgo*: un DRP desactualizado puede contener procedimientos que ya no corresponden con la infraestructura tecnológica existente. **Idea clave: todo cambio relevante debe evaluarse para determinar su impacto sobre el DRP y actualizar aquello que resulte afectado.**
3. **Componente 3: Estructura organizacional, roles, responsabilidades y autoridades (Cláusula 5.3 – ISO 22301)**. *Qué representa*: la definición formal de quién participa en la gestión del DRP, qué responsabilidades posee y qué autoridad tiene. *Concepto clave*: roles de gestión durante la normalidad operativa y roles de respuesta y recuperación durante una interrupción. *Durante la normalidad operativa*: coordinar la revisión y actualización del DRP; dar seguimiento a pruebas y ejercicios; verificar que responsables y datos de contacto permanezcan actualizados; coordinar las actividades de capacitación relacionadas con el plan. *Durante la recuperación*: los equipos designados ejecutan las acciones establecidas en el DRP; las decisiones que excedan su autoridad se escalan al nivel correspondiente. **Objetivo: reducir la improvisación y facilitar una respuesta coordinada durante la recuperación.**

## 4. Indicadores de gestión (KPIs) en continuidad
- En la GCN y en el Gobierno del DRP **no basta con tener un plan documentado**: la organización necesita saber **si realmente el plan funciona**, si está preparada y si puede responder ante una interrupción. **ISO 22301** requiere realizar **seguimiento, medición, análisis y evaluación del desempeño y la eficacia del BCMS**, y usar los resultados para apoyar su mejora continua. **La continuidad debe gestionarse con evidencia y datos, no solo con percepciones.** Los KPIs son una herramienta para apoyar esta evaluación.
- **¿Por qué son importantes?** Permiten: evaluar si el DRP es efectivo; demostrar resultados a la gerencia; detectar debilidades; tomar decisiones de mejora; y controlar el nivel de preparación organizacional.
- **Dos tipos**: **Indicadores de cumplimiento** (verifican si las actividades planificadas se realizan) e **Indicadores de efectividad** (evalúan si las capacidades de recuperación logran los resultados esperados).

### 1. Indicadores de cumplimiento — "¿Se hizo?"
Verifican si la organización está ejecutando correctamente las actividades de continuidad. Miden: avance, control, seguimiento, cumplimiento de tareas, mantenimiento del sistema. Responden: ¿se realizaron las pruebas programadas? ¿el DRP fue actualizado? ¿el personal fue capacitado? ¿se revisaron los respaldos? ¿se ejecutaron simulacros? **Característica: no demuestran por sí solos que la capacidad de recuperación sea efectiva; solo verifican si las actividades de gestión se están realizando.**
| KPI | Fórmula / medición |
|---|---|
| % de pruebas ejecutadas | (Pruebas realizadas / pruebas programadas) × 100 |
| % de personal capacitado | (Personal capacitado / total personal crítico) × 100 |
| % de planes revisados | (Planes revisados / planes programados para revisión) × 100 |
| Número de simulacros realizados | Cantidad por periodo |
| % de respaldos verificados | (Respaldos validados / respaldos programados) × 100 |
*Ejemplo*: se programaron 4 simulacros al año y solo se ejecutaron 2 → 2/4 × 100 = **50%** de cumplimiento; evidencia un incumplimiento del 50% y requiere analizar las causas.

### 2. Indicadores de efectividad — "¿Funcionó?"
Evalúan si las capacidades de recuperación logran los resultados esperados **durante una prueba, ejercicio o interrupción**. Responden: ¿la recuperación se logró dentro del tiempo objetivo? ¿los sistemas críticos fueron recuperados? ¿se cumplió el RTO? ¿la pérdida de datos estuvo dentro del RPO? ¿los servicios recuperados funcionaron al nivel esperado? **Característica: estos indicadores sí evalúan la capacidad real de recuperación.**
| KPI | ¿Qué evalúa? |
|---|---|
| **Tiempo real de recuperación (RTA)** | Tiempo realmente empleado para recuperar el servicio |
| **Cumplimiento del RTO** | Si la recuperación se logró dentro del tiempo objetivo |
| **Cumplimiento del RPO** | Si la pérdida de datos se mantuvo dentro del objetivo establecido |
| **% de recuperaciones exitosas** | Proporción de recuperaciones que alcanzaron los criterios definidos |
| **% de servicios críticos recuperados** | Servicios críticos recuperados respecto de los previstos en la prueba o evento |
**Relación con RTO y RPO**: RTO (¿en cuánto tiempo debemos recuperar el servicio?) → resultado real: ¿cuánto tardamos realmente en recuperar el servicio? RPO (¿cuánta pérdida de datos, expresada en tiempo, podemos tolerar?) → resultado real: ¿qué pérdida de datos se produjo realmente? **La efectividad se evalúa comparando el resultado real con el objetivo establecido (RTO y RPO).**
*Ejemplo*: RTO = 2 horas; durante el simulacro la recuperación tomó 4 horas → 4 h > 2 h → **en esta prueba, la recuperación no cumplió el RTO establecido**.

### Diferencia entre indicadores de cumplimiento y efectividad
| | **Cumplimiento ("¿Se hizo?")** | **Efectividad ("¿Funcionó?")** |
|---|---|---|
| Qué miden | Verifican si las actividades planificadas se realizan | Evalúan si las capacidades de recuperación logran los resultados esperados |
| Ejemplos | % de pruebas ejecutadas, % de personal capacitado, % de planes revisados, nº de simulacros, % de respaldos verificados | Tiempo real de recuperación (RTA), cumplimiento del RTO, cumplimiento del RPO, % de recuperaciones exitosas, % de servicios críticos recuperados |
| Tipo de resultado | Muestran el grado de ejecución de lo planificado | Muestran el resultado real de la recuperación |
| Cuándo se utilizan | Durante la preparación y mantenimiento del DRP | Durante una prueba, ejercicio o interrupción |
| Qué muestran | Si se están realizando las actividades definidas | Si la recuperación alcanzó los objetivos establecidos |
| Limitación | No demuestran por sí solos que la capacidad de recuperación sea efectiva | Valor: permiten evaluar si el DRP logra los resultados esperados (RTO y RPO) |
**Son complementarios**: el cumplimiento muestra si se hizo lo planificado y la efectividad muestra si realmente funcionó.
**Ejemplo integrador**: (1) *Cumplimiento alto*: la empresa realiza todos sus simulacros y capacitaciones; sus KPIs de cumplimiento son altos (simulacros, capacitaciones, planes actualizados, respaldos verificados). (2) *Resultados de la prueba de recuperación*: el sistema demora demasiado en recuperarse y se pierde información crítica → efectividad baja (tiempo de recuperación demasiado alto; pérdida de información crítica). (3) *Conclusión*: las actividades planificadas se cumplieron, **pero la capacidad de recuperación no alcanzó los resultados esperados**. **Cumplir actividades no garantiza por sí solo una capacidad efectiva de recuperación.**
**Cierre**: los KPIs transforman el DRP en un sistema medible y gestionable; permiten convertir los resultados de la gestión del DRP en información medible para apoyar la toma de decisiones y la mejora. ISO 22301 requiere evaluar el desempeño y la eficacia del SGCN; estos indicadores pueden utilizarse como herramientas para apoyar dicha evaluación.

## 5. Caso de estudio: El colapso de Fintech Express
Resuelto en [[EJ_S09_DRP_y_Gobierno]].

## Pregunta de cierre
¿Por qué una organización puede cumplir con todas las actividades programadas de su DRP y aun así no alcanzar sus objetivos de recuperación? → porque los indicadores de **cumplimiento** solo verifican que se ejecutan las actividades; la **efectividad** depende de que las capacidades de recuperación logren los resultados (RTO/RPO). Pueden existir actividades mal diseñadas, procedimientos desactualizados, recursos insuficientes o pruebas que no reflejan la realidad.

## Conclusiones del docente
- El Gobierno del DRP permite dirigir, supervisar y mantener la preparación mediante políticas, responsabilidades y niveles de autoridad definidos.
- Una gestión eficaz requiere compromiso de la Alta Dirección, coordinación entre niveles y actualización permanente ante cambios relevantes.
- El seguimiento con indicadores de cumplimiento y efectividad evalúa tanto la ejecución como los resultados de recuperación y facilita la mejora continua.

## Ojo en el examen
- Definición de gobierno del DRP y sus 4 preguntas (¿quién decide, supervisa, ejecuta y bajo qué reglas?).
- Los **3 componentes** con su cláusula ISO 22301 (5 y 5.3 para los componentes 1 y 3).
- Funciones por nivel (orienta y decide / coordina, supervisa y prepara / ejecuta y responde) y que **auditoría evalúa, no ejecuta**.
- **KPIs**: cumplimiento ("¿se hizo?") vs efectividad ("¿funcionó?"); fórmulas; RTA vs RTO; ejemplos 2/4 = 50% y 4 h > 2 h.
- Con y sin gobierno (migración de BD a AWS).
