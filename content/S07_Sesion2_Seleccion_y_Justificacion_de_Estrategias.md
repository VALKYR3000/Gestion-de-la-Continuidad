---
tags: [clase, continuidad-del-negocio, semana7, estrategias]
fuente: SEM 7/SESION 2 (PDF S07_s14 completo, texto + diapositivas gráficas)
---
# S07-2 · Selección y justificación de estrategias de recuperación (análisis costo-beneficio)
Ejercicios: [[EJ_S07_Estrategias_de_Recuperacion]] · Sesión previa: [[S07_Sesion1_Estrategias_de_Recuperacion]]

## Logro y gancho
Seleccionar y justificar estrategias de recuperación alineadas con los requisitos de recuperación del negocio, considerando su **viabilidad, capacidad de recuperación y relación costo-beneficio**.
Repaso: ¿la estrategia debe limitarse a los recursos que la empresa tiene actualmente? → **No**; puede requerir recursos adicionales a los actualmente disponibles.
Gancho: una empresa tiene varias alternativas para recuperar un proceso crítico; ¿cómo decidir cuál es la más adecuada?
**Importancia**: alinear las estrategias con las necesidades reales permite seleccionar soluciones capaces de responder a los requisitos de recuperación de los procesos prioritarios, reduciendo el impacto de una interrupción y **evitando inversiones innecesarias o insuficientes**.
Contenido: retroalimentación · criterios para seleccionar estrategias · evaluación y justificación de alternativas · aplicación práctica.

## 1. Retroalimentación: cómo se conectan BIA, riesgos y estrategia
- **BIA** (punto de partida): permite conocer qué necesita el negocio y qué consecuencias tendría una interrupción en sus procesos. Responde: ¿qué procesos y actividades son prioritarios, cuál es el impacto de su interrupción? *El BIA no identifica riesgos, pero proporciona*: procesos y actividades prioritarias (críticas); recursos que los soportan (tecnológicos, humanos, físicos, terceros); impacto de su interrupción (financiero, legal, reputacional, operativo, etc.); requisitos de recuperación del negocio expresados en **MTPD, RTO, RPO y WRT**. Resultado: una lista de procesos prioritarios con sus impactos y requisitos de recuperación → **necesidades del negocio para la recuperación**.
- **Gestión de riesgos**: identifica y analiza las amenazas que podrían afectar los procesos críticos y sus recursos, para determinar el nivel de riesgo y priorizar acciones. Responde: ¿qué amenazas podrían afectar nuestros procesos o recursos? ¿qué vulnerabilidades podrían facilitarlas? ¿qué tan probable es que ocurran? ¿qué impacto tendrían? ¿cuál es el nivel de riesgo? Resultado: riesgos identificados y evaluados para los procesos críticos y sus recursos, que sirven de insumo para definir y seleccionar estrategias. Importante: los riesgos analizados están relacionados con los procesos críticos y los recursos que los hacen funcionar, no son riesgos generales de toda la empresa.
- **Selección de la estrategia de recuperación**: se seleccionan considerando los **resultados del BIA, el análisis de riesgos y la realidad de la organización**, buscando la mejor relación beneficio–costo y la capacidad de responder ante una interrupción. ¿Qué debemos considerar? **Requisitos de recuperación** (RTO, RPO y otros requisitos definidos en el BIA) · **Riesgos** (amenazas y escenarios que podrían provocar la interrupción) · **Capacidad real de recuperación** (capacidades actuales de la organización) · **Recursos y brechas** (qué recursos se requieren y qué falta; pueden adquirirse o contratarse) · **Viabilidad técnica y operativa** (que la alternativa sea factible de implementar y sostener en el tiempo) · **Relación costo-beneficio** (costo de implementación y mantenimiento frente al beneficio para el negocio). Resultado: la alternativa de recuperación más adecuada para cada proceso crítico. *Importante: la estrategia puede requerir recursos adicionales a los actualmente disponibles; no debe limitarse solo a lo que la empresa tiene.*
- **Ejemplo integrador** (empresa de comercio electrónico, plataforma web de ventas como proceso crítico; contexto: alta demanda en campañas (Black Friday), genera el mayor porcentaje de ingresos, su interrupción afecta ventas, clientes y reputación): *Resultado del BIA*: proceso crítico = plataforma web; **RTO 2 horas; RPO 15 minutos; MTPD 8 horas**; recursos críticos: servidores, base de datos, equipo de TI. *Resultado del análisis de riesgos*: amenaza principal = sobrecarga por incremento de tráfico; vulnerabilidad = infraestructura sin escalabilidad suficiente; probabilidad Alta (en campañas); impacto Alto (pérdida de ventas y daño reputacional); nivel de riesgo Alto. *Estrategia de recuperación seleccionada*: implementar alta disponibilidad con escalabilidad automática en la nube; replicación de la BD en sitio alterno; pruebas periódicas de conmutación. La estrategia seleccionada cumple con los requisitos de recuperación, reduce el riesgo identificado y es viable para la organización. **Conclusión: la combinación del BIA y la gestión de riesgos permite seleccionar una estrategia alineada con las necesidades reales del negocio.**

## 2. ¿Cómo seleccionar entre varias alternativas?
Una organización puede disponer de múltiples alternativas capaces de recuperar un mismo proceso, pero **no todas son igualmente convenientes**. Antes de definir la estrategia hay que evaluarlas y compararlas con criterios objetivos. Pasos: ① **Alternativas de recuperación** (identificar las opciones que podrían responder a la necesidad del negocio) → ② **Evaluar criterios** (analizar cada alternativa según los criterios de selección) → ③ **Comparar alternativas** (contrastar ventajas y limitaciones) → ④ **Seleccionar** (elegir la alternativa más adecuada) → ⑤ **Justificar la decisión** (fundamentar por qué la opción elegida es la adecuada para el negocio).
**Idea clave: la alternativa más rápida o más económica no necesariamente es la mejor opción. Debe responder a las necesidades del negocio y ser viable para la organización.**

### 4 criterios para evaluar alternativas
1. **Cumplimiento de los requisitos de recuperación**: ¿la alternativa permite cumplir con los RTO o RPO definidos para el proceso o servicio? Se analiza: tiempo de recuperación (RTO), pérdida de información tolerable (RPO).
2. **Capacidad y recursos requeridos**: ¿la organización puede implementarla con su capacidad actual? Si no, ¿qué recursos adicionales tendría que adquirir? Se analiza: recursos (personas, tecnología, infraestructura, proveedores) y la brecha de capacidades.
3. **Viabilidad técnica y operativa**: ¿es técnicamente factible de implementar? ¿puede operarse, mantenerse y sostenerse en el tiempo dentro de la organización? Se analiza: factibilidad técnica, compatibilidad con el entorno, facilidad de implementación y operación, disponibilidad de soporte.
   - **Viabilidad técnica**: ¿es posible implementarla con la tecnología disponible o que la organización pueda adquirir o contratar? (compatibilidad con la infraestructura actual o con el entorno, disponibilidad de la tecnología en el mercado, requerimientos de hardware y software, integración con los sistemas y procesos existentes, nivel de complejidad de implementación, tiempo de puesta en servicio). Preguntas: ¿la tecnología está disponible en el mercado o se puede adquirir/contratar? ¿contamos con personal capacitado para implementarla y operarla? ¿se puede integrar con los sistemas y procesos actuales? ¿podemos operarla y mantenerla de manera continua? ¿qué dependencias externas existen (proveedores, servicios en la nube) y son viables?
   - **Viabilidad operativa**: ¿puede operarse y mantenerse en la organización? (disponibilidad de personal con habilidades necesarias o posibilidad de capacitarlo/contratarlo, procesos y procedimientos requeridos, tiempo de puesta en operación, soporte y mantenimiento continuo, dependencia de terceros/proveedores, costos operativos y sostenibilidad en el tiempo).
   - **Idea clave**: no tener actualmente la infraestructura, tecnología o personal no implica descartar la alternativa; se debe evaluar si la organización puede adquirir, contratar o desarrollar las capacidades necesarias en un plazo y costo razonables. **Una alternativa puede cumplir con el RTO/RPO, pero también debe ser técnicamente viable y operable. Si la organización no puede hacer viable su implementación u operación, no será una opción adecuada.**
4. **Relación costo-beneficio**: ¿el costo de implementar y mantener la alternativa se justifica frente a los impactos y pérdidas que permitiría reducir? Se analiza: costos de implementación, costos de operación y mantenimiento, beneficios esperados, reducción de pérdidas e impactos.
   - **Costos**: inversión inicial (equipos, software, licencias, servicios), costos de operación y mantenimiento, costos de personal y capacitación. **Beneficios**: reducción de pérdidas financieras, menor tiempo de inactividad, menor impacto reputacional, cumplimiento de requisitos legales y contractuales, mayor resiliencia del negocio.
   - Preguntas clave: ¿cuál es el costo total de la alternativa? ¿qué pérdidas e impactos permitiría reducir? ¿el beneficio esperado justifica la inversión? ¿es la alternativa sostenible en el tiempo?
   - **La decisión busca el equilibrio** entre costos y beneficios. **No siempre la alternativa más económica es la mejor, ni la más costosa garantiza la continuidad del negocio.** Se selecciona la alternativa que ofrece el mayor valor para el negocio, considerando los costos y los beneficios esperados en función de sus necesidades y objetivos.

## 3. Análisis costo-beneficio (cálculo)
### Ejemplo práctico: pérdida con y sin alternativa
Negocio online (comercio electrónico); pérdida estimada por hora de interrupción: **$2 000**; sin estrategia la interrupción se estima en **24 horas**; con la alternativa evaluada se reduce a **6 horas**; costo de implementar la alternativa: **$10 000**. Objetivo: determinar si la inversión en la estrategia de recuperación está justificada frente a las pérdidas que permite reducir.
- **Sin estrategia**: pérdida por interrupción = 24 h × $2 000 = **$48 000** → pérdida total $48 000.
- **Con la alternativa**: pérdida por interrupción = 6 h × $2 000 = **$12 000**; costo de implementación $10 000; **costo total con alternativa = $12 000 + $10 000 = $22 000**.
- **Beneficio económico (ahorro)**: $48 000 − $22 000 = **$26 000**. La alternativa genera un beneficio económico de $26 000 en este escenario. **Conclusión**: en este escenario, la inversión en la estrategia se justifica porque reduce significativamente las pérdidas (nota: este análisis considera un solo evento de interrupción; en la siguiente diapositiva se incorpora la probabilidad anual).

### Cálculo paso a paso (pérdida esperada anual)
Se utiliza la **pérdida esperada anual** para comparar alternativas en un horizonte anual.
1. **Pérdida esperada anual = Ingresos_por_hora × Horas_de_interrupción × Probabilidad_anual** (representa la pérdida económica promedio en un año, considerando la probabilidad de que ocurra la interrupción).
2. **Costo total anual de la alternativa = Pérdida_esperada_con_alternativa + Costo_de_la_estrategia** (incluye la pérdida económica con la alternativa y el costo anual de la alternativa: implementación y mantenimiento).
3. **Ahorro anual frente a no implementar la estrategia = Pérdida_sin_plan − Costo_total** (si es positivo, la alternativa genera un ahorro económico esperado; si es negativo, implica un costo adicional esperado).
*Datos del ejemplo*: negocio online; pérdida por hora $2 000; probabilidad anual de interrupción **10%**; sin estrategia: interrupción de **24 horas**; con la alternativa: interrupción de **6 horas**; costo anual de la alternativa **$10 000**.
- Pérdida esperada anual sin estrategia: $2 000 × 24 h × 0,10 = **$4 800**.
- Pérdida esperada anual con alternativa: $2 000 × 6 h × 0,10 = **$1 200**.
- Costo total anual de la alternativa: $1 200 + $10 000 = **$11 200**.
- Ahorro anual frente a no implementar: $4 800 − $11 200 = **−$6 400**.
- **Conclusión**: en este escenario la alternativa tiene un **costo adicional esperado de $6 400** (el ahorro es negativo). Sin embargo, la decisión final debe considerar también otros criterios (RTO/RPO, criticidad del servicio, requisitos legales, viabilidad técnica, entre otros).

### Comparación costo-beneficio de alternativas de sitio (Caso Soluciones SAC)
Tienda online de productos electrónicos; plataforma de ventas genera **$3 000 por hora** en promedio; probabilidad anual de interrupción importante **50% (0,5)**. Datos comunes: pérdida por hora (ingresos no generados) $3 000; probabilidad anual 50%.
**Paso 1 – Pérdida esperada anual = pérdida por hora × downtime × probabilidad anual**
| Alternativa | Downtime promedio por incidente | Pérdida esperada anual |
|---|---|---|
| Sin estrategia (manual) | 48 h | 3 000 × 48 × 0,5 = **$72 000** |
| Cold site (sitio frío) | 24 h | 3 000 × 24 × 0,5 = **$36 000** |
| Warm site (sitio tibio) | 6 h | 3 000 × 6 × 0,5 = **$9 000** |
| Hot site (sitio caliente) | 1 h | 3 000 × 1 × 0,5 = **$1 500** |
Idea: a menor tiempo de interrupción, menor la pérdida económica esperada; pero falta incorporar el costo de cada alternativa.
**Paso 2 – Costo total anual = pérdida esperada + costo anual de la estrategia; Paso 3 – Ahorro = pérdida sin estrategia − costo total**
| Concepto | Sin estrategia | Cold site | Warm site | Hot site |
|---|---|---|---|---|
| Pérdida esperada anual | $72 000 | $36 000 | $9 000 | $1 500 |
| Costo anual de la estrategia | $0 | $4 000 | $12 000 | $45 000 |
| **Costo total anual** | **$72 000** | **$40 000** | **$21 000** | **$46 500** |
| **Ahorro anual frente a no implementar** | — | **$32 000** | **$51 000** | **$25 500** |
Resultados: todas las alternativas reducen la pérdida esperada anual frente a no hacer nada; **la alternativa Warm site presenta el mayor ahorro económico esperado ($51 000)**; el Hot site ofrece la menor interrupción pero tiene un costo anual alto. Desde el punto de vista **económico** la mejor es Warm site, pero esto no significa que sea la que se seleccionará: se debe evaluar también RTO/RPO, capacidad, viabilidad, entre otros. **La alternativa con mejor resultado económico no necesariamente será la seleccionada.**

### Comparación de alternativas con el requisito del negocio (RTO)
Requisito del negocio: **RTO de los servicios críticos = 4 horas** (proviene del BIA y no se modifica por limitaciones presupuestarias).
| Criterio | Cold site | Warm site | Hot site |
|---|---|---|---|
| Tiempo estimado de recuperación (downtime) | 24 h | 6 h | 1 h |
| ¿Cumple el RTO = 4 h? | **No** | **No** | **Sí** |
| Capacidad y recursos requeridos | Menores | Intermedios | Altos |
| Viabilidad técnica-operativa | Alta | Alta | Requiere mayores capacidades |
| Costo anual de la estrategia | $4 000 | $12 000 | $45 000 |
| Ahorro económico esperado | $32 000 | **$51 000** | $25 500 |
Principales hallazgos: Warm site presenta el mayor ahorro económico esperado ($51 000) **pero no cumple el RTO de 4 horas (requiere 6 horas)**; **Hot site es la única alternativa que cumple el RTO de 4 horas**, aunque su ahorro económico ($25 500) es menor y requiere mayores capacidades; Cold site no cumple el RTO y genera el ahorro más bajo entre las opciones de sitio. **Idea clave: la alternativa con mayor beneficio económico no necesariamente es la más adecuada; la decisión final considera todos los criterios (RTO/RPO, viabilidad, capacidades, costos).**

### Selección y justificación de la estrategia
Caso Soluciones SAC; la organización cuenta con capacidad presupuestaria para contratar el servicio de Hot Site; requisito de negocio RTO = 4 horas.
**Estrategia recomendada: Hot site (sitio caliente).** Justificación: (1) cumple con el requisito del negocio (RTO = 4 horas); (2) permite la recuperación más rápida (1 hora); (3) es técnica y operativamente viable mediante servicios críticos en la nube (proveedor externo); (4) la organización cuenta con el presupuesto y los recursos necesarios; (5) aunque tiene un costo mayor y un ahorro menor que Warm site, la continuidad del negocio y el cumplimiento del RTO tienen mayor prioridad. **No se selecciona por el costo o el ahorro únicamente, sino por el cumplimiento del RTO y su viabilidad para la organización.**
¿Qué pasa si no se cuenta con el presupuesto? El Hot site, aunque cumple con el RTO, podría no ser viable si la organización no dispone del presupuesto necesario (contratación, financiamiento, etc.); se deben evaluar alternativas (p. ej. mejorar el Warm site, soluciones híbridas) que permitan cumplir o acercarse al RTO de 4 horas; **no se debe aumentar el RTO solo por limitaciones presupuestarias, ya que proviene de la criticidad de las necesidades del negocio.**

### Proceso para seleccionar una estrategia de recuperación (6 pasos)
1. **Necesidades del negocio (BIA)**: determinar los requisitos de recuperación (RTO, RPO, procesos críticos y priorizados, impacto de la interrupción). 2. **Identificar alternativas**: definir las opciones posibles de recuperación (cold site, warm site, hot site, nube, redundancia, otras). 3. **Evaluar alternativas**: analizar cada alternativa con los criterios (tiempo de recuperación, recursos y capacidades requeridos, viabilidad técnica y operativa, costo y ahorro económico esperado). 4. **Comparar alternativas**: contrastar los resultados y analizar las diferencias (cumplimiento del RTO, fortalezas y debilidades, brechas de recuperación, relación costo-beneficio, riesgos asociados). 5. **Seleccionar la estrategia**: elegir la alternativa que mejor responde a las necesidades del negocio y es viable para la organización (cumple RTO/RPO, es viable técnica y operativamente, se alinea con los objetivos de continuidad). 6. **Justificar la decisión**: explicar por qué la alternativa seleccionada es la adecuada (cómo satisface los requisitos, qué beneficios aporta, qué riesgos mitiga, por qué es viable). **Idea clave: la estrategia seleccionada no necesariamente es la más económica ni la más rápida; es aquella que, considerando los criterios definidos, responde de manera viable a las necesidades de recuperación del negocio.**

## 4. Probabilidad anual vs frecuencia anual esperada (antes de calcular)
- **Probabilidad anual**: posibilidad de que un evento ocurra durante un año; se expresa entre 0 y 1 o entre 0% y 100% (ej. 5% = 0,05). Ejemplo: incendio en un centro de datos, probabilidad anual 5% (0,05).
- **Frecuencia anual esperada**: número esperado de veces que ocurre un evento durante un año; se expresa en eventos/año (ej. 4 interrupciones/año). Ejemplo: fallos de Internet en un call center, frecuencia anual 4 veces al año.
- **Importante: 4 eventos/año NO significa 400% de probabilidad; es una frecuencia anual esperada.** Si el dato está expresado en porcentaje o decimal entre 0 y 1, es probabilidad; si dice 2, 3 o 4 eventos por año, es frecuencia anual. En la fórmula de pérdida esperada: con probabilidad se multiplica por la probabilidad; con frecuencia se multiplica por el número de eventos.

## 5. Actividad de clase: 4 ejercicios de análisis costo-beneficio
Enunciados y soluciones en [[EJ_S07_Estrategias_de_Recuperacion]].

## Pregunta de cierre
¿Qué criterios debería considerar una organización para seleccionar y justificar una estrategia de recuperación? → cumplimiento de RTO/RPO, recursos y capacidades requeridos, viabilidad técnica y operativa, relación costo-beneficio.

## Conclusiones del docente
- Las estrategias deben responder a las necesidades reales del negocio, considerando procesos prioritarios y requisitos (RTO, RPO).
- Antes de seleccionar, se deben identificar, evaluar y comparar diferentes alternativas.
- La selección considera en conjunto RTO/RPO, recursos y capacidades, viabilidad técnica y operativa y costo-beneficio.
- La alternativa con **menor costo, mayor ahorro o recuperación más rápida no necesariamente será la seleccionada**; la decisión debe justificarse con los criterios definidos y las necesidades del negocio.

## Ojo en el examen
- **Fórmulas**: Pérdida esperada anual = ingresos/h × horas de interrupción × probabilidad (o × nº de eventos); Costo total = pérdida con estrategia + costo de la estrategia; **Ahorro = pérdida sin estrategia − costo total**.
- Un ahorro negativo no descarta automáticamente una alternativa (RTO/RPO, criticidad, requisitos legales, viabilidad).
- La estrategia ganadora económicamente puede no cumplir el RTO (caso Warm site vs Hot site).
- No subir el RTO por falta de presupuesto: buscar alternativas.
- Distinguir probabilidad (0–1) vs frecuencia (eventos/año).
