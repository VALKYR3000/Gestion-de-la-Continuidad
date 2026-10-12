---
tags: [resumen, examen, continuidad-del-negocio]
---
# Resumen Express · Continuidad del Negocio
Índice: [[index]] · Preguntas: [[02_BANCO_DE_PREGUNTAS]]

## 1. Fundamentos (S1)
- **BC** = capacidad de mantener operaciones esenciales durante y después de un incidente disruptivo. Estratégica (dirección) + operativa (procedimientos).
- Incidente: **externo/interno**. Medidas: **preventivas** (antes) / **reactivas** (después). **Resiliencia** = anticiparse, responder y adaptarse.
- **DRII**: 10 prácticas (PPBCM, CBCP): programa · riesgos · **BIA** · estrategia · respuesta a incidentes · desarrollo del plan · capacitación · pruebas/mantenimiento · crisis y comunicación · coordinación externa.
- **BCI**: 6 buenas prácticas (GPG 7.0, CBCI): BCMS · adopción · análisis · diseño · habilitación · validación. **ISO 22301** = requisitos del BCMS (DRII/BCI no la sustituyen).
- El BCP nunca debe ser más viejo que el último cambio importante de la empresa.

## 2. Estrategia y estructura (S2–S3)
- Planeación estratégica: misión → visión → valores → análisis del entorno (FODA, PESTEL, 5 fuerzas) → objetivos **SMART** → estrategias → implementación → evaluación/KPIs. BCM protege las actividades que permiten cumplir la estrategia.
- Niveles: **estratégico decide** (Comité de Crisis) · **táctico coordina/prepara** (Coordinador BCM) · **operativo ejecuta** (equipos de respuesta). La autoridad se define **antes**; se escala cuando se excede autoridad, alcance, tiempo/RTO o presupuesto.
- Fases de actuación: detección/evaluación → respuesta → recuperación (verificar integridad) → post-incidente/mejora. Usar la infraestructura alterna ≠ recuperación terminada.

## 3. BIA (S4–S5)
- Identifica procesos críticos, impactos, tiempos tolerables y recursos. **Categorías**: financiero, operacional, legal/regulatorio, reputacional, salud y seguridad.
- **Niveles**: Crítico 4 · Alto 3 · Medio 2 · Bajo 1. **Criticidad**: criterio más severo o puntaje acumulado (escalas: 3 cat. 3–12, 4 cat. 4–16, 5 cat. 5–20; para 5 categorías Bajo 5–7, Medio 8–10, Alto 11–13, Crítico 14–20).
- Matriz detallada: categorías × intervalos de tiempo (los define el negocio).
- **Métricas**: **MTPD/MTD** (límite máximo), **RTO** (tiempo objetivo), **WRT** (trabajo para estabilizar), **RPO** (pérdida de datos tolerable en tiempo).
- **7 fases**: planificación · identificación de procesos · evaluación de impacto · métricas de recuperación · recursos · validación y aprobación · documentación y comunicación.
- **8 recursos**: humanos, tecnológicos, infraestructura, información/datos, financieros, equipos, terceros, documentación. RR.HH.: roles, polifuncionalidad (conocimiento explícito/tácito + potestad), **SPOF** (job shadowing, documentación, rotación).

## 4. Riesgos (S6)
- **Amenaza** (potencial) vs **incidente** (ocurrido). Riesgo = amenaza × vulnerabilidad sobre activo crítico → **Nivel = P × I**.
- Vulnerabilidades: tecnológicas, organizacionales, físicas.
- **BIA** (impacto/tiempo → MTPD, RTO, RPO) vs **análisis de riesgo** (amenazas, probabilidad, impacto).
- Proceso: identificar → analizar → evaluar (vs tolerancia) → tratar → monitorear. **VME = P × I($)**.
- Tratamiento: **evitar, mitigar, transferir, aceptar** (activa = con plan de contingencia; pasiva = sin acciones). Riesgo residual.

## 5. Estrategias y crisis (S7–S8)
- Estrategia de recuperación: alineada a RTO/RPO. Criterios de selección: cumple RTO/RPO, recursos/capacidad, viabilidad técnica y operativa, costo-beneficio.
- **Crisis** = incidente que escala por gravedad, incertidumbre y necesidad de dirección estratégica. **CGC**: CEO, CFO, CISO, Operaciones, RR.HH., Coordinador BCM + soporte (Comunicaciones, Legal, Auditoría).
- **5 etapas**: preparación → detección/alerta → contención/respuesta → recuperación → evaluación/aprendizaje. Comunicación: clara, oportuna, coherente, transparente.

## 6. DRP (S9)
- **DRP** = recuperación de **TI** (subconjunto del BCM); BCP cubre el negocio.
- **9 elementos**: objetivo · alcance · BIA (RTO/RPO) · estrategias (backups, **hot/warm/cold site**, redundancia) · roles · procedimientos (Evaluar→Activar→Recuperar→Verificar→Restablecer) · comunicaciones · pruebas (tabletop, técnica, parcial, completa) · mantenimiento.
- **Gobierno del DRP** (3 componentes): política y compromiso de la alta dirección · gestión del cambio · estructura/roles. 
- **KPIs**: cumplimiento (hacer lo planificado, p.ej. pruebas ejecutadas/programadas ×100) vs efectividad (RTA vs RTO, RPO, % recuperaciones exitosas).

## Ojo máximo en el examen
Definiciones RTO/RPO/WRT/MTPD · cálculo de criticidad · amenaza vs incidente · 4 tratamientos · 5 etapas de crisis · hot/warm/cold · KPI cumplimiento vs efectividad · quién decide/coordina/ejecuta.
