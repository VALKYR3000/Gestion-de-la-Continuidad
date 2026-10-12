---
tags: [clase, continuidad-del-negocio, semana4, BIA]
fuente: SEM 4/SESION 2 (PDF S04_s8 completo, 82 diapositivas, texto + gráficos)
---
# S04-2 · BIA: fases, niveles de impacto, matrices de criticidad y requerimientos de recuperación
Ejercicios: [[EJ_S04_BIA]] · Sesión previa: [[S04_Sesion1_BIA_Impactos_y_Requerimientos]]

## Logro y gancho
Analizar la criticidad de los procesos a partir de la evolución de sus impactos en el tiempo y establecer sus requerimientos de recuperación (MTPD, RTO, WRT, RPO).
Gancho: una empresa con 50 procesos y presupuesto para proteger solo 5, ¿con qué criterios elegir los más importantes para la supervivencia? → impactos (financiero, operacional, legal, reputacional, salud), criticidad total, tiempo de tolerancia (MTPD/RTO), dependencias.
**Importancia**: el BIA permite identificar y priorizar procesos críticos, analizar cómo aumentan sus impactos al prolongarse una interrupción y establecer requerimientos de recuperación que orienten las estrategias de continuidad.

## FASES DEL BIA (7)
El BIA se desarrolla en fases que permiten recopilar, analizar y priorizar información clave para diseñar estrategias de continuidad:
1. Planificación y preparación · 2. Identificación de procesos · 3. Evaluación de impacto e identificación de procesos críticos · 4. Determinación de las métricas de recuperación · 5. Identificación de recursos · 6. Validación y aprobación de los resultados del BIA · 7. Documentación y comunicación.

### Fase 1 · Planificación y preparación
**Objetivo**: establecer las bases del BIA, definir el alcance y los objetivos y organizar el equipo. **Actividades**: **definir el alcance** (qué áreas, departamentos y procesos se incluirán); **seleccionar el equipo del BIA** (miembros de diferentes áreas: TI, operaciones, finanzas, etc.); **establecer objetivos y plazos** (qué se quiere lograr: identificación de procesos críticos, tiempos de recuperación, etc.; fechas de finalización).

### Fase 2 · Identificación de procesos
**Objetivo**: identificar todos los procesos clave dentro de la organización y los recursos necesarios para llevarlos a cabo. **Actividades**: **identificar procesos críticos** (listar todos los procesos y actividades que la empresa realiza para cumplir su misión); **clasificar los procesos por su importancia** (priorizar según su impacto en la empresa si se interrumpen); **identificar los recursos necesarios** (materiales, humanos, tecnológicos y financieros de cada proceso). Existen herramientas para identificar procesos y su criticidad: cuestionarios, matrices.

#### Niveles de impacto (cualitativo → cuantitativo)
| Nivel | Valor | Descripción | Ejemplo práctico |
|---|---|---|---|
| 🔴 **Crítico** | **4** | Interrupción total de un proceso crítico; el negocio se detiene y hay pérdidas graves. Muy seria, necesita ser resuelta lo más rápido posible; afecta de forma significativa la operación o imagen | Un ciberataque paraliza la red de un banco: clientes no pueden retirar dinero ni realizar pagos |
| 🟠 **Alto** | **3** | Interrupción grave de un proceso crítico, pero con alternativas limitadas (un poco más de tiempo para manejarla) | Un hospital sufre un corte eléctrico prolongado: los equipos de soporte vital dependen de generadores de respaldo |
| 🟡 **Medio** | **2** | Interrupción moderada en un proceso de apoyo; el negocio sigue pero con retrasos/costos | En una cadena de retail, la caída del sistema de facturación dura 3 horas: largas colas, algunos clientes abandonan compras, pérdidas moderadas |
| 🟢 **Bajo** | **1** | Interrupción menor, fácil de manejar, sin grandes consecuencias inmediatas | En una empresa de logística, una falla en un sistema secundario de reportes retrasa informes internos, pero no detiene las operaciones |

#### Tipo de impacto vs niveles (definición de cada nivel por categoría)
**1. Financiero** (pérdidas monetarias directas o indirectas; ej. pérdida de ventas, sanciones, penalidades, costos de recuperación): Crítico = pérdida financiera masiva por hora o día, puede comprometer la viabilidad del negocio · Alto = pérdidas significativas que afectan seriamente ingresos o presupuestos · Medio = pérdidas manejables pero que requieren reajustes o compensaciones · Bajo = pérdidas menores, sin impacto en la sostenibilidad. *Ejemplo Core bancario:* Crítico = caída total del sistema central bancario durante 24 h (pérdidas millonarias por transacciones no procesadas, penalidades y compensaciones); Alto = falla en el módulo de transferencias internacionales por 12 h (pérdidas altas por comisiones no cobradas y demandas de clientes corporativos); Medio = interrupción de pagos con tarjetas de crédito por 2 h (pérdidas moderadas en comisiones y ventas no concretadas en comercios); Bajo = retraso de 1 h en el cierre contable nocturno (retrasos administrativos sin pérdidas directas relevantes).
**2. Operacional** (capacidad para seguir operando o prestar servicios; ej. caída de sistemas críticos, imposibilidad de despachar pedidos): Crítico = la operación del negocio se detiene totalmente, imposible continuar sin este proceso · Alto = se afecta una parte importante de la operación, pero hay formas parciales de continuar · Medio = disminuye la eficiencia, pero se puede seguir trabajando con algunos retrasos · Bajo = el proceso puede detenerse sin gran afectación operativa, hay alternativas claras. *Ejemplo (Sistema Central bancario):* Crítico = caída total, no se pueden hacer transferencias, retiros ni pagos; Alto = falla en el módulo de transferencias internacionales, la operación sigue en el mercado local pero con gran afectación; Medio = caída del módulo de reportes (los clientes operan, hay retrasos administrativos); Bajo = caída temporal del chatbot de consultas.
**3. Legal/Regulatorio** (incumplimiento de leyes, regulaciones o contratos; ej. sanciones gubernamentales, multas tributarias, demandas, incumplimientos contractuales): Crítico = incumplimientos graves con consecuencias legales severas (demandas, clausura, multas altas) · Alto = infracciones relevantes con consecuencias legales moderadas (sanciones, advertencias formales) · Medio = riesgos legales menores, usualmente corregibles sin penalidad · Bajo = sin implicancias legales directas o fácilmente mitigables.
**4. Reputacional** (imagen pública y percepción del cliente; ej. quejas en redes, cobertura negativa en medios, pérdida de confianza de clientes o socios): Crítico = daño severo e inmediato a la imagen, viralización en medios, fuga masiva de clientes · Alto = impacto considerable en la percepción, afecta la fidelidad o reputación del servicio · Medio = algunos clientes afectados, impacto limitado y manejable · Bajo = impacto casi nulo en la reputación o solo interno.
**5. Salud y Seguridad** (riesgo de daño físico o psicológico a empleados, clientes, contratistas o terceros; ej. accidentes laborales, exposición a riesgos físicos, condiciones inseguras, incendios, estrés severo): Crítico = riesgo **inminente de muerte o lesiones graves**, afecta a varias personas, puede ser emergencia mayor · Alto = posibilidad de lesiones moderadas o graves en una o más personas, necesita respuesta inmediata · Medio = riesgos menores (resbalones, fatiga, molestias leves), mitigables con controles estándar · Bajo = no representa un riesgo significativo, situación controlada.

**Tabla resumen (categoría × nivel):**
| Categoría | Bajo 🟢 | Medio 🟡 | Alto 🟠 | Crítico 🔴 |
|---|---|---|---|---|
| Financiero | pérdidas menores sin efecto significativo | pérdidas moderadas, requieren ajustes | pérdidas importantes, afectan ingresos | pérdidas masivas, riesgo a la continuidad del negocio |
| Operacional | operación continúa con impacto mínimo | reducción de eficiencia, proceso lento | proceso clave afectado; interrupciones parciales | interrupción total de operación; no puede continuar |
| Legal/Regulatorio | sin riesgo legal directo | incumplimientos menores, corregibles | infracciones importantes; sanciones posibles | violaciones graves a leyes o contratos; multas, demandas o cierre |
| Reputacional | casi sin impacto en imagen | imagen afectada ligeramente ante algunos usuarios | percepción pública negativa; pérdida de confianza | daño grave e inmediato a la reputación; fuga masiva de clientes |
| Salud y Seguridad | sin riesgos físicos o mentales | riesgos leves o molestias menores | riesgo de lesiones moderadas o estrés severo | riesgo inmediato de lesiones graves o muertes |
**¿Cómo usar esta tabla?** (1) Evalúa cada proceso crítico de negocio. (2) Asigna un nivel de impacto (bajo, medio, alto, crítico) **en cada categoría**. (3) Usa colores o puntajes para facilitar la visualización. (4) Prioriza la recuperación de procesos con **mayor concentración de niveles altos o críticos**.

#### Matriz simplificada (general) de criticidad
- **Primera matriz que se aplica a todos los procesos**: *Matriz Simplificada de Evaluación General*; compara rápidamente los procesos según los impactos de su interrupción y determina su nivel de criticidad para establecer prioridades. **Objetivo**: identificar cuáles procesos son más críticos en conjunto para luego analizarlos a detalle. Es una tabla que cruza categorías de impacto con niveles de impacto por proceso; sirve para **filtrar procesos críticos**; no es aún muy detallada, es **orientativa**, punto de partida para definir prioridades.
- **Dos enfoques para determinar la criticidad general**:
  1. **Criterio más severo (conservador)**: se adopta el nivel más alto que aparece entre todas las categorías. Ej.: Alto financiero, Crítico operacional, Alto reputacional → **Crítico**. Ventaja: muy útil en entornos donde la continuidad es vital.
     | Proceso | Financiero | Operacional | Reputacional | Criticidad (más severo) |
     |---|---|---|---|---|
     | Gestión de pedidos | Alto | Crítico | Alto | **Crítico** |
     | Atención al cliente | Medio | Alto | Alto | **Alto** |
     | Facturación | Alto | Medio | Bajo | **Alto** |
     | Marketing digital | Bajo | Bajo | Medio | **Medio** |
     | RR. HH. | Bajo | Bajo | Bajo | **Bajo** |
     | Soporte TI interno | Medio | Alto | Medio | **Alto** |
  2. **Puntaje acumulado (cuantitativo)**: Bajo = 1, Medio = 2, Alto = 3, Crítico = 4; se **suman** los valores de todas las categorías y se usa la escala para determinar el nivel.
     - **Ejemplo "Gestión de pedidos" (5 categorías)**: Operacional Crítico 4 + Financiero Alto 3 + Legal Medio 2 + Reputacional Alto 3 + Salud y Seguridad Bajo 1 = **13 → Alto**. Con el método 1 (criterio más severo) sería **Crítico** (porque operacional es Crítico). Ambos métodos pueden dar resultados diferentes.
     - **Escalas según número de categorías** (el número de categorías varía con el contexto; la criticidad total posible depende de cuántas se evalúan):
       | N.º categorías | Rango criticidad total | Bajo | Medio | Alto | Crítico |
       |---|---|---|---|---|---|
       | 3 | 3–12 | 3–4 | 5–6 | 7–9 | 10–12 |
       | 4 | 4–16 | 4–6 | 7–9 | 10–12 | 13–16 |
       | 5 | 5–20 | 5–7 | 8–10 | 11–13 | 14–20 |

### Fase 3 · Evaluación de impacto
**Objetivo**: evaluar el impacto de la interrupción de cada proceso; se determina el impacto operativo, financiero, reputacional y legal en función de los posibles tiempos de interrupción. **Actividades**: **evaluar el impacto de la interrupción** (cómo afectaría a distintas áreas; considerar corto y largo plazo) y **clasificar los impactos** (asignar nivel de gravedad en base a la duración de la interrupción: crítico, alto, medio o bajo).
- **¿Qué es criticidad?** Qué tan grave es el impacto de una interrupción en un proceso, considerando el **tiempo de interrupción** y la **gravedad de las consecuencias** en las categorías evaluadas. En la matriz BIA detallada, cada proceso se evalúa en diferentes categorías y en distintos intervalos de tiempo; para cada categoría e intervalo se determina un nivel cualitativo (Bajo/Medio/Alto/Crítico) con valor cuantitativo (1–4).
- **¿Qué es criticidad total?** Suma de los valores de las categorías de impacto para **cada intervalo de tiempo**. Comparando entre intervalos se observa cómo **evoluciona la severidad** al prolongarse la interrupción. Ej.: Medio (2) + Alto (3) + Bajo (1) + Alto (3) = **9**.
- **Matriz de criticidad detallada**: permite analizar cómo evoluciona la criticidad a medida que aumenta el tiempo de interrupción y proporciona información para establecer las métricas de recuperación. Dos dimensiones: **Eje Y** = categorías de impacto (en qué dimensiones se manifiestan las consecuencias); **Eje X** = intervalos de tiempo (0–4 horas · 4–24 horas · 1–3 días · más de 3 días). **Estos intervalos no son universales ni obligatorios.**
  - ¿En base a qué se definen los intervalos? (1) **Naturaleza del negocio** (e-commerce: intervalos cortos, horas; universidad: días); (2) **tipo de procesos** (operativos clave: tiempos más cortos; soporte: pueden tolerar más); (3) **experiencia histórica** (incidentes pasados y cuánto tomó restaurar); (4) **entrevistas/cuestionarios a dueños de procesos** (cuánto tiempo es tolerable antes de impactos severos). *Los intervalos no son fijos; se definen según la rapidez con que un proceso impacta al negocio. 0–4 h, 4–24 h y 1–3 días son solo referencia estándar. **El tiempo no lo define la metodología, lo define el negocio.***
  - **¿Para qué sirve?** Visualizar rápidamente qué procesos son más urgentes de recuperar; definir prioridades en el plan de continuidad; asignar recursos según la importancia del proceso; **definir MTPD y RTO más realistas**.
  - **¿Cómo se utiliza?** (1) Asignar un nivel de impacto a cada categoría por intervalo; (2) convertir a valor (Bajo 1, Medio 2, Alto 3, Crítico 4); (3) sumar los valores de las categorías en cada intervalo → criticidad total; (4) comparar la criticidad total con la escala correspondiente para obtener el nivel de criticidad **en cada intervalo**; (5) analizar cómo evoluciona la criticidad al prolongarse la interrupción.
  - **Ejemplo de matriz detallada (4 categorías, escala 4–16)**: Operacional: Medio (2), Alto (3), Crítico (4), Crítico (4); Financiero: Bajo (1), Medio (2), Alto (3), Crítico (4); Legal/Regulatorio: Bajo (1), Medio (2), Alto (3), Crítico (4); Reputacional: Bajo (1), Medio (2), Alto (3), Crítico (4). **Criticidad total: 5 (Bajo), 9 (Medio), 13 (Crítico), 16 (Crítico).** (Escala 4 categorías: 4–6 Bajo; 7–9 Medio; 10–12 Alto; 13–16 Crítico).
  - **Cálculo con 5 categorías (intervalo 0–4 h)**: Operacional Crítico 4 + Financiero Alto 3 + Legal Bajo 1 + Reputacional Alto 3 + Salud Bajo 1 = **12** → rango 11–13 → **Alto**.
  - **Interpretación**: la criticidad total se compara con la escala. Ej.: criticidad 12 → rango 11–13 (5 categorías) → nivel Alto. En "Gestión de la Plataforma Web" es un proceso esencial que debe recuperarse rápidamente. Con 4 categorías, 4+3+1+2 = 10 → Alto; si continúa la interrupción, 4–24 h: 13 → **Crítico** (la criticidad aumenta).
  - **Ventajas de la matriz**: análisis **multidimensional** y más completo; ayuda a **justificar prioridades ante la alta dirección** (no solo en dinero); facilita definir métricas de recuperación, especialmente **MTPD/MTD y RTO**.

#### Caso SOLUCIONES SAC — plataforma de compras en línea
Empresa de comercio electrónico (plataforma web y app móvil); operaciones dependen de procesos tecnológicos y de negocio. Procesos: **1 Gestión de la Plataforma Web** (clientes consultan productos y realizan compras) · **2 Pasarela de Pagos** (procesa los pagos) · **3 Gestión de Inventarios** (controla disponibilidad de stock) · **4 Logística y Despacho** (preparación y entrega de pedidos) · **5 Atención al Cliente** (consultas, reclamos, incidencias) · **6 Facturación** (emisión de comprobantes de pago). Preguntas: ¿todos deberían tener la misma prioridad de recuperación? (No) ¿cuál tendría mayores consecuencias? (la pasarela de pagos).
**Ruta de evaluación**: (1) consecuencias de la interrupción → (2) nivel de impacto (Bajo, Medio, Alto, Crítico) → (3) valor cuantitativo (1–4) → (4) criticidad total (suma) → (5) nivel de criticidad y prioridad de recuperación. Escala de 4 categorías: 4–6 Bajo (impacto de bajo impacto, se puede gestionar), 7–9 Medio (moderada, requiere atención), 10–12 Alto (grave, debe priorizarse la recuperación), 13–16 Crítico (muy seria, prioridad máxima).
Evaluación por proceso (4 categorías: Operacional, Financiero, Legal/Regulatorio, Reputacional):
| Proceso | Operacional | Financiero | Legal/Reg. | Reputacional | Total | Nivel |
|---|---|---|---|---|---|---|
| Gestión de la Plataforma Web | Crítico 4 | Alto 3 | Medio 2 | Alto 3 | **12** | **Alto** |
| Pasarela de Pagos | Crítico 4 | Crítico 4 | Alto 3 | Alto 3 | **14** | **Crítico** |
| Logística y Envíos | Alto 3 | Alto 3 | Medio 2 | Alto 3 | **11** | **Alto** |
| Atención al Cliente | Medio 2 | Medio 2 | Medio 2 | Alto 3 | **9** | **Medio** |
| Gestión de Inventarios | Alto 3 | Medio 2 | Medio 2 | Alto 3 | **10** | **Alto** |
| Facturación y Contabilidad | Medio 2 | Alto 3 | Crítico 4 | Medio 2 | **11** | **Alto** |
Justificaciones clave: *Web*: sin plataforma los clientes no pueden comprar (operación principal se detiene); se pierden ventas e ingresos; incumplimientos contractuales sin consecuencia legal severa inmediata; indisponibilidad afecta la confianza. *Pasarela*: sin ella el cliente no puede completar la compra (se interrumpe el flujo de ingresos); se generan pérdidas de ventas, devoluciones o regularizaciones; problemas en pagos pueden derivar en reclamos o sanciones por incumplimientos financieros; errores de cobro generan desconfianza. *Logística*: impide o retrasa la entrega de pedidos; reenvíos, devoluciones, indemnizaciones; incumplir plazos puede infringir derechos del consumidor; entregas tardías destruyen la experiencia. *Atención al cliente*: falta de soporte reduce la resolución de incidencias; puede provocar ventas futuras perdidas; quejas sin atender pueden implicar sanciones; respuesta lenta genera mala imagen. *Inventarios*: sin control de stock se pueden vender productos no disponibles; mala gestión → sobrestock o desabastecimiento; falta de información sobre inventario puede generar incumplimientos; clientes pierden confianza al no encontrar stock. *Facturación*: no detiene la venta pero afecta emisión de comprobantes y cierre contable; retrasos en cobranzas y control financiero; demoras o errores en comprobantes pueden causar incumplimientos tributarios y sanciones (legal Crítico); clientes/proveedores pierden confianza en la formalidad.
**Priorización** (¿qué procesos requieren análisis detallado?): **1.º Pasarela de Pagos (14, Crítico) → Prioridad 1**: mayor criticidad total; su indisponibilidad detiene directamente las transacciones y ya afecta los ingresos. **2.º Gestión de la Plataforma Web (12, Alto) → Prioridad 2**: afecta directamente la operación principal del negocio; es el canal por el que se brindan todos los servicios. Luego (prioridad posterior): Logística y Envíos (11), Facturación y Contabilidad (11), Gestión de Inventarios (10); **Atención al Cliente (9, Medio) → menor prioridad relativa**. Criterio de selección: criticidad total y severidad del impacto sobre la operación principal. Los procesos priorizados pasan al análisis detallado con la Matriz de Criticidad Detallada (evolución en el tiempo).

#### Análisis detallado de los procesos priorizados
**Gestión de la Plataforma Web** — Matriz detallada (4 categorías; escala 4–6 Bajo, 7–9 Medio, 10–12 Alto, 13–16 Crítico):
| Categoría | 0–4 h | 4–24 h | 1–3 días | >3 días |
|---|---|---|---|---|
| Operacional | Crítico 4 | Crítico 4 | Crítico 4 | Crítico 4 |
| Financiero | Alto 3 | Crítico 4 | Crítico 4 | Crítico 4 |
| Legal/Regulatorio | Bajo 1 | Medio 2 | Alto 3 | Crítico 4 |
| Reputacional | Medio 2 | Alto 3 | Crítico 4 | Crítico 4 |
| **Criticidad total** | **10 (Alto)** | **13 (Crítico)** | **15 (Crítico)** | **16 (Crítico)** |
Observación: la criticidad pasa de **ALTA (10) en 0–4 h a CRÍTICA (13) en 4–24 h**. Interpretación del intervalo 0–4 h: 4+3+1+2 = 10 → Alto; las consecuencias ya son significativas en las primeras horas; si continúa, a 4–24 h = 13 → Crítico.
**Pasarela de Pagos**: Operacional Crítico 4 (todos los intervalos); Financiero Crítico 4 (todos); Legal/Regulatorio: Medio 2, Alto 3, Crítico 4, Crítico 4; Reputacional: Alto 3, Crítico 4, Crítico 4, Crítico 4. **Totales: 13, 15, 16, 16 → Crítico desde el primer intervalo** (cálculo 0–4 h: 4+4+2+3 = 13 → Crítico). Muestra mayor criticidad desde las primeras horas → necesita estrategias de recuperación inmediatas.
**Resultado de la Fase 3 (comparación)**:
| Proceso | 0–4 h | 4–24 h | 1–3 días | >3 días |
|---|---|---|---|---|
| Gestión de la Plataforma Web | 10 Alto | 13 Crítico | 15 Crítico | 16 Crítico |
| Pasarela de Pagos | 13 Crítico | 15 Crítico | 16 Crítico | 16 Crítico |
Conclusiones: la Pasarela alcanza criticidad **Crítica desde el primer intervalo (0–4 h)**; la Plataforma Web inicia en **Alto** y alcanza **Crítica a partir de 4–24 h**. Los procesos priorizados no necesariamente alcanzan el mismo nivel de criticidad en el mismo intervalo: la Matriz Detallada permite observar con qué rapidez se intensifican los impactos y diferenciar la urgencia de recuperación entre procesos. La información será la base para definir tiempos máximos tolerables y objetivos de recuperación (MTPD, RTO, RPO) → Fase 4.

### Fase 4 · Establecimiento de tiempos de recuperación (requerimientos de recuperación)
**Objetivo**: establecer los requerimientos de recuperación de los procesos priorizados, considerando los resultados del análisis de impactos y las necesidades del negocio.
**¿Cómo se establecen?** Combinando los resultados del análisis de impactos con la tolerancia y necesidades del negocio: (1) **resultados de la matriz detallada** (impactos por categoría y su evolución en el tiempo, por cada proceso priorizado) → (2) **tolerancia y necesidades del negocio** (¿cuándo las consecuencias de la interrupción se vuelven inaceptables? ¿cuánta pérdida de datos puede tolerar el negocio?) → (3) **requerimientos de recuperación** MTPD, RTO, WRT, RPO. Los valores finales se definen considerando la tolerancia y las necesidades del negocio.
**Actividades clave (4)**: **1 Establecer el MTPD** (período máximo durante el cual la organización puede tolerar la interrupción antes de que las consecuencias sean inaceptables) · **2 Definir el RTO** (tiempo objetivo para reanudar el proceso a un nivel de operación previamente definido) · **3 Estimar el WRT** (tiempo adicional necesario, después de alcanzar el RTO, para completar actividades pendientes y estabilizar la operación) · **4 Definir el RPO** (punto en el tiempo hasta el cual deben recuperarse los datos; pérdida de información que el negocio puede tolerar).

#### ¿Cómo se establece el MTPD?
Es el límite máximo de tiempo que la organización puede tolerar una interrupción antes de que los impactos se vuelvan **inaceptables**.
1. **Observar la evolución de los impactos por categoría**: analizar cómo cambia el nivel de impacto conforme aumenta el tiempo en los procesos priorizados.
2. **Identificar el límite de tolerancia → MTPD**: la organización define sus criterios de tolerancia al impacto; en este caso ha establecido que el nivel **CRÍTICO representa consecuencias INACEPTABLES**. Cuando una categoría alcanza el nivel crítico, el impacto es inaceptable para el negocio. **El inicio del primer intervalo en el que se alcanza ese umbral sirve como referencia para establecer el MTPD.**
- Ejemplo (matriz: Operacional Alto/Crítico/Crítico/Crítico; Financiero Medio/Alto/Crítico/Crítico; Reputacional Alto/Crítico/Crítico/Crítico; Legal Medio/Alto/Crítico/Crítico): la primera categoría que alcanza Crítico es **Operacional en 4–24 h**; por tanto el MTPD debe establecerse **antes de entrar en ese intervalo → MTPD ≤ 4 horas**.
- El MTPD es un **requerimiento estratégico** que define el límite máximo tolerable de interrupción para evitar impactos inaceptables que comprometan los objetivos del negocio.

#### ¿Cómo se establece el RTO?
Tiempo objetivo para reanudar el proceso a un nivel de operación definido **antes de que los impactos se intensifiquen**.
1. **Observar cuándo los impactos alcanzan nivel ALTO** (la organización usa el nivel Alto como referencia de consecuencias significativas que requieren recuperar el proceso antes de que continúen intensificándose).
2. **Establecer el objetivo de recuperación**: a) **si ALTO aparece después del primer intervalo (0–4 h)**: el inicio de ese intervalo sirve de referencia para un RTO anterior a ese punto. Ej.: si el nivel Alto comienza en 4–24 h → **RTO < 4 horas**. b) **si ALTO aparece en 0–4 h**: la matriz no indica la hora exacta; se debe profundizar el análisis dentro del intervalo para identificar cuándo se alcanza Alto y fijar el RTO anterior a ese momento. Ej.: se determina que Alto se alcanza aprox. a las 2 h → **RTO = 1 h**.
3. **¿Y si el MTPD también está en 0–4 h?** Se profundiza el mismo intervalo para identificar ambos momentos. Ejemplo: Alto aprox. a la 1 h; Crítico (umbral inaceptable) aprox. a las 3 h → **RTO < 1 h y MTPD = 3 h**.
- **Idea clave**: el RTO **no se calcula como un porcentaje del MTPD**; se establece a partir de la evolución de los impactos y debe permitir recuperar el proceso **antes de que las consecuencias alcancen el nivel ALTO**. Relación importante: **RTO + WRT ≤ MTPD**.

#### Ejemplo guiado: Gestión de pedidos (e-commerce)
Proceso: recibir, validar, preparar y despachar pedidos a través de la plataforma de e-commerce. La organización define: **ALTO** = consecuencias significativas que requieren recuperación; **CRÍTICO** = consecuencias inaceptables.
| Categoría | 0–4 h | 4–24 h | 1–3 días | >3 días |
|---|---|---|---|---|
| Operacional | Bajo (el área puede absorber la demanda pendiente) | Alto (retrasos en preparación y despacho) | Crítico (no se pueden cumplir los pedidos comprometidos; paralización) | Crítico (interrupción total del servicio y colapso de la operación) |
| Financiero | Bajo (costos operativos sin variación significativa) | Alto (pérdidas por penalidades con clientes y costos adicionales) | Crítico (pérdidas importantes; devoluciones y cancelaciones masivas) | Crítico (afectación severa del flujo de caja y rentabilidad) |
| Reputacional | Bajo (clientes informados y atendidos) | Alto (quejas, disminuye la satisfacción) | Crítico (pérdida de confianza, impacto en redes y reputación de marca) | Crítico (daño significativo y pérdida de clientes) |
| Legal/Regulatorio | Bajo (cumplimiento sin afectación) | Medio (riesgo de incumplimiento de tiempos en contratos) | Alto (incumplimiento contractual, posibles reclamos formales y sanciones) | Crítico (demandas, sanciones regulatorias y multas significativas) |
**Aplicación de la regla**: Alto aparece por primera vez en **4–24 h** → **RTO < 4 horas**; Crítico aparece por primera vez en **1–3 días** → **MTPD ≤ 1 día (24 h)** (antes de entrar a ese intervalo). WRT del ejemplo: ver abajo. ⚠️ REVISAR: la diapositiva solo muestra la matriz; los valores concretos (RTO < 4 h, MTPD ≤ 24 h) se derivan aplicando las reglas anteriores.

#### ¿Cómo se determina el WRT?
Tiempo adicional que necesita el proceso **después de haber sido recuperado en el RTO** para completar el trabajo pendiente y estabilizar la operación. Pasos: (1) identificar qué **trabajo quedará pendiente** una vez recuperado el proceso en el RTO; (2) estimar el tiempo necesario para procesar pendientes, conciliar información y normalizar la operación; (3) considerar recursos disponibles, procedimientos y experiencia histórica; (4) verificar que **RTO + WRT ≤ MTPD**.
*Ejemplo gestión de pedidos (e-commerce)*: el sistema se recupera en el RTO = 2 h; quedan pendientes: procesar pedidos en cola (30 min), verificar y conciliar información (20 min), ajustes y normalización de la operación (10 min) → **tiempo total de estabilización 60 min → WRT = 1 hora**.
**Idea clave**: el WRT asegura que, tras recuperar el proceso, la operación no solo se reanude sino que se completen los trabajos pendientes y se estabilice. **Relación entre requerimientos: MTPD ≥ RTO + WRT ≥ RPO** (RTO + WRT debe ser menor o igual que el MTPD).

#### ¿Cómo se determina el RPO?
El RPO define **cuánta información (en tiempo) puede perderse como máximo** sin que el negocio lo considere inaceptable. Pasos: (1) **datos utilizados** (identificar qué datos son críticos para el proceso: pedidos, inventario, pagos, datos de clientes, etc.); (2) **frecuencia de cambio** (determinar cada cuánto se registran o actualizan estos datos: cada minuto, 15 min, 4 horas, diario, etc.); (3) **consecuencias de pérdida** (analizar el impacto de perder datos durante un período determinado: reprocesos, errores en pedidos, afectación económica, afectación al cliente); (4) **pérdida tolerable de datos** (definir cuánto tiempo de información puede perderse sin que el negocio se vea afectado de forma inaceptable); (5) **determinación del RPO** (se establece igual o menor que la pérdida tolerable definida; RPO = pérdida tolerable de datos, expresada en tiempo).
**Idea clave**: el RPO **no depende de la frecuencia de los backups**, sino de la información máxima que el negocio puede tolerar perder. Siempre se cumple: **RPO ≤ RTO y RTO + WRT ≤ MTPD**. (Nota de la diapositiva: "RPO ≤ RTO y RTO + WRT ≤ MTPD".)
**Ejemplos de determinación del RPO:**
| Proceso | Frecuencia de cambio de los datos | Consecuencias de perder información | Pérdida tolerable | RPO |
|---|---|---|---|---|
| Plataforma web | Datos de sesiones, catálogos y registros se actualizan cada minuto | Si se pierde mucha información, se afecta la experiencia del usuario, se generan reprocesos y pérdida de ventas | últimos 5 min | **5 minutos** |
| Pasarela de pagos | Transacciones y confirmaciones de pago se registran cada minuto | Si se pierde información, puede haber inconsistencias en los pagos, reclamos y pérdidas económicas | último 1 min | **1 minuto** |
| Gestión de inventario | Movimientos de inventario se registran cada 15 minutos | Puede generarse sobreventa, errores en el stock y reprocesos en pedidos | últimos 15 min | **15 minutos** |
| Reportes gerenciales | Datos consolidados se actualizan cada 4 horas | La información no estaría actualizada para la toma de decisiones, pero no hay impacto crítico en la operación | últimas 4 horas | **4 horas** |

#### Resultado de la Fase 4
La organización establece los requerimientos de recuperación de los procesos priorizados: **MTPD (máximo tiempo tolerable de interrupción), RTO (objetivo de recuperación), WRT (tiempo para completar y estabilizar), RPO (pérdida máxima de datos tolerable)**, que sirven de base para definir posteriormente las **estrategias de recuperación**.

## Pregunta de cierre
¿Por qué no es suficiente identificar que un proceso es crítico para determinar cómo debe recuperarse? → porque la criticidad depende de cómo evolucionan los impactos en el tiempo; hay que definir cuánto se tolera (MTPD), en cuánto se recupera (RTO), qué falta estabilizar (WRT) y cuántos datos se pueden perder (RPO) para elegir estrategias adecuadas.

## Conclusiones del docente
- La criticidad no depende solo de la importancia del proceso sino de cómo evolucionan sus impactos en el tiempo.
- La Matriz de Criticidad Detallada analiza esa evolución y da información para establecer los requerimientos.
- MTPD, RTO, WRT y RPO orientan la definición de las estrategias de continuidad.

## Ojo en el examen
- **Calcular criticidad con ambos métodos** y usar la **escala correcta según N.º de categorías** (3: 3–12; 4: 4–16; 5: 5–20).
- **Reglas de derivación**: MTPD = antes del primer intervalo donde aparece **Crítico**; RTO = antes del primer intervalo donde aparece **Alto**; WRT = suma de pendientes tras el RTO; RPO = pérdida tolerable de datos (no depende de los backups).
- Relaciones: **RTO + WRT ≤ MTPD**; **MTPD ≥ RTO + WRT ≥ RPO**.
- Los intervalos de tiempo los define el negocio.
- Si ALTO aparece ya en 0–4 h hay que profundizar el intervalo.
- Caso SAC: Pasarela (14, Crítico, prioridad 1), Web (12, Alto, prioridad 2), Logística 11, Facturación 11, Inventarios 10, Atención 9.
