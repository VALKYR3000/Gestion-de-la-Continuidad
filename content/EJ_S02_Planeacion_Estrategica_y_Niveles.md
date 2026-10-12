---
tags: [ejercicios, continuidad-del-negocio, semana2]
fuente: SEM 2 (casos FinPay y TechNova resueltos + ejercicios propuestos)
---
# Ejercicios · Semana 2 (planeación estratégica, SMART, FODA, niveles)
Teoría: [[S02_Sesion1_Planeacion_Estrategica_y_BCM]] · [[S02_Sesion2_Integracion_PE_y_BCM_Niveles]]

# A. Casos del curso (resueltos)

## A1. FODA de SOLUCIONES TEC (clase)
Ver la matriz resuelta en [[S02_Sesion1_Planeacion_Estrategica_y_BCM]] (sección 4).

## A2. Caso TechNova Solutions (S02-S4)
**Enunciado:** SaaS de gestión administrativa para PYMES. Eje del semestre: *"Incrementar en un 25% la captación de nuevas pymes en los próximos 6 meses, mediante campañas de marketing digital y demostraciones de software, lo cual contribuirá a aumentar la rentabilidad y posicionamiento de la empresa en el mercado tecnológico."*

### Parte A — Descomposición SMART
1. **S (Específico):** el objetivo es claro y concreto: incrementar la **captación de nuevas pymes** como clientes (no "crecer" en general).
2. **M (Medible):** se cuantifica con **+25%** en el número de pymes captadas; se puede verificar con el CRM/registro de nuevos clientes.
3. **A (Alcanzable):** es realista con los medios previstos: **campañas de marketing digital y demostraciones de software**, respaldado por la oportunidad de mercado (digitalización creciente de las pymes) y los recursos de la empresa.
4. **R (Relevante):** contribuye a **aumentar la rentabilidad y el posicionamiento** de la empresa en el mercado tecnológico; alineado con la dirección estratégica (liderazgo ante la digitalización).
5. **T (Temporal):** plazo definido de **6 meses**.

### Parte B — Estrategias de crecimiento + salvaguardas de continuidad
**Estrategia 1 — Marketing digital**
- *Táctica de captación:* campañas segmentadas en LinkedIn/Google Ads/redes y email marketing hacia pymes, con una *landing page* de registro de demos; embudo con seguimiento en CRM; métricas (leads, conversión, CAC).
- *Riesgo:* denegación de servicio (DoS/DDoS) sobre la plataforma web durante la campaña.
- *Medidas de continuidad (preventivas):* WAF/anti-DDoS y CDN; balanceo de carga y autoescalado en la nube; redundancia (multi-zona); monitoreo y alertas; límites de tasa; pruebas de carga previas a la campaña; contrato SLA con el proveedor cloud/ISP; sitio estático/landing alterna.
- *Medidas reactivas:* activar el procedimiento de respuesta a incidentes (aislar tráfico malicioso, activar mitigación del proveedor), conmutar a la infraestructura/landing alterna, pausar temporalmente las campañas pagadas, comunicar a clientes/prospectos, registrar y evaluar lecciones aprendidas. Definir **RTO** de la landing (p. ej., 1 h) y responsables (táctico coordina, operativo ejecuta, estratégico decide si hay que suspender la campaña).

**Estrategia 2 — Demostraciones técnicas**
- *Protocolo para que las demos no se interrumpan ante fallos de conectividad o energía:*
  1. **Antes:** verificar conectividad y energía 24 h antes; checklist técnico; entorno demo (sandbox) alojado en la nube con respaldo; grabar demo de contingencia (video) y datos de prueba cargados offline.
  2. **Infraestructura de respaldo:** UPS y/o grupo electrógeno en la sede; internet redundante (dos ISP o enlace móvil 4G/5G de respaldo); laptop con batería y copia local del demo; acceso alterno desde otra sede o teletrabajo.
  3. **Roles:** presentador principal y suplente (backup), soporte técnico en línea.
  4. **Durante:** monitoreo; ante la falla, conmutar al enlace de respaldo/entorno alterno o a la demo grabada, informar al cliente con mensaje preparado y reprogramar si el corte supera el umbral (p. ej., 10 min).
  5. **Después:** registrar el incidente, medir impacto y actualizar el protocolo.

## A3. Caso FinPay Perú (S2-S3)
**Enunciado resumido:** plataforma de pagos con 3 800 clientes empresariales; objetivo estratégico: **incrementar en 30% el número de clientes manteniendo la confianza y disponibilidad**. Dependencias: proveedor externo de procesamiento, autenticación, BD de transacciones, personal de TI, conectividad y atención al cliente. Interrupciones breves recientes de un proveedor. BIA: procesamiento de pagos con impactos financieros y reputacionales importantes; **RTO 2 h, RPO 15 min**; fuerte dependencia del proveedor externo. Alternativas: redundancia, proveedor alterno, recuperación automática, procedimientos temporales. Lunes 10:15 falla grave del proveedor; 10:35 se confirma que no se resolverá pronto (varias horas).

**1. ¿Qué objetivo se afecta y cuál es la relación con la continuidad?**
El objetivo de **crecer 30% en clientes empresariales manteniendo confianza y disponibilidad**. Una interrupción prolongada genera pérdida de clientes, reclamos y daño reputacional, lo que impide captar y retener clientes. La BCM protege las actividades prioritarias (procesamiento de pagos) y sus recursos para que la organización siga avanzando hacia su objetivo aunque haya interrupciones: la estrategia define *qué* proteger; la continuidad asegura *poder seguir*.

**2. ¿Qué es BIA y qué es análisis de riesgos?**
- **BIA:** el procesamiento de pagos tiene impactos financieros y reputacionales importantes si permanece interrumpido; **RTO 2 h y RPO 15 min** (requisitos de recuperación); identificación de recursos/dependencias del servicio (proveedor externo, autenticación, BD, personal, conectividad, atención).
- **Análisis de riesgos:** las interrupciones breves recientes del proveedor tecnológico externo (amenaza/probabilidad), la **fuerte dependencia** del proveedor (vulnerabilidad) y la posibilidad de una falla mayor; las alternativas son opciones de tratamiento/estrategia.
- No confundir: el BIA mide el impacto y los tiempos tolerables; el análisis de riesgos identifica amenazas, vulnerabilidades, probabilidad e impacto.

**3. Decisiones del nivel estratégico (≥2)**
- **Definir/aprobar la política y prioridad de disponibilidad** del servicio de pagos como crítico para el objetivo (alinear con el 30% de crecimiento).
- **Aprobar presupuesto e inversión** para redundancia: contrato con un **proveedor alterno** de procesamiento y mecanismos de recuperación automática.
- **Asignar responsabilidades y autoridad** (designar Coordinador BCM, criterios de activación/escalamiento y autoridad presupuestal).
- Aceptar o no el riesgo residual (apetito de riesgo) y exigir SLA al proveedor actual.

**4. Nivel táctico: qué analizar y preparar + estrategia coherente con RTO/RPO**
- Analizar: BIA detallado, dependencias del proveedor, riesgos (fallas recurrentes), recursos necesarios, SLA/penalidades, alternativas y costos.
- Preparar: planes y procedimientos (BCP/DRP), contratos con proveedor alterno, pruebas de conmutación, capacitación, contactos y comunicación.
- **Estrategia coherente (RTO 2 h / RPO 15 min):** **proveedor alterno activo-pasivo con conmutación automática (failover)** + **replicación casi en tiempo real/backups cada ≤15 min** de la BD de transacciones (cumple RPO 15 min) + monitoreo y alertas; procedimiento temporal de contingencia (cola de transacciones/modo degradado, comunicación a comercios). El tiempo de conmutación debe ser inferior a 2 h (RTO).

**5. Nivel operativo cuando falla (10:15)**
Secuencia: (1) **Detectar y reportar** al Coordinador/táctico por los canales definidos; (2) verificar la condición del servicio y el alcance; (3) **ejecutar el procedimiento autorizado**: activar la conmutación al proveedor alterno/mecanismo automático o modo contingencia; (4) comprobar funcionamiento (transacciones, autenticación, integridad de datos; verificar RPO); (5) monitorear estabilidad; (6) apoyar a Atención al Cliente con información; (7) **registrar** acciones y tiempos y **informar** estado. El operativo no define la estrategia, sigue los procedimientos y escala lo que excede su autoridad.

**6. Articulación de los tres niveles y retroalimentación**
Estratégico orienta (objetivo, prioridad, presupuesto) → táctico analiza y prepara (BIA/riesgos, estrategia, planes) → operativo ejecuta y responde (10:15–10:35 en adelante). El táctico coordina durante el incidente y escala al estratégico si se excede el RTO/hay impacto contractual o necesidad de recursos extraordinarios. **Retroalimentan:** tiempos reales de recuperación vs RTO/RPO, decisiones tomadas, comunicación, fallas del proveedor, lecciones aprendidas y mejoras propuestas, que permiten ajustar estrategias, SLA, presupuesto y planes.

# B. Ejercicios propuestos (con solución)

**B1. Valida si es SMART:** "Mejorar el servicio al cliente pronto."
*Solución:* No: no es específico (¿qué aspecto?), ni medible, ni tiene plazo. Versión SMART: "Reducir en 20% el tiempo medio de respuesta de soporte (de 10 a 8 h) en los próximos 4 meses mediante un chatbot y capacitación del equipo, para elevar la satisfacción del cliente."

**B2. Clasifica en FODA** (interno/externo): (a) personal altamente calificado; (b) nueva regulación que obliga a digitalizar; (c) dependencia de un único proveedor; (d) llegada de un competidor global; (e) buena reputación de marca; (f) crecimiento del e-commerce.
*Solución:* (a) F; (b) O (si favorece) o A (si obliga costos) — se justifica según el caso; (c) D; (d) A; (e) F; (f) O.

**B3. Relaciona misión/visión/valores con la continuidad.** Hospital: misión "brindar servicios de salud". ¿Qué debe proteger la BCM?
*Solución:* las actividades prioritarias necesarias para mantener la atención (urgencias, UCI, historias clínicas, suministros, energía, personal clínico).

**B4. Asigna el nivel:** (1) aprobar un presupuesto de US$50 000 de ciberseguridad; (2) definir RTO 4 h/RPO 1 h; (3) verificar el backup cada mañana; (4) establecer que la disponibilidad de datos es prioridad #1; (5) proponer backups cada hora; (6) aislar equipos infectados.
*Solución:* (1) estratégico; (2) táctico; (3) operativo; (4) estratégico; (5) táctico; (6) operativo.

**B5. Horizontes:** ¿qué horizonte tiene cada nivel?
*Solución:* estratégico 3–10 años (largo); táctico 1–3 años (mediano); operativo días/semanas/meses (corto).

**B6. PE vs GCN.** Completa: pregunta que responde, meta, instrumentos.
*Solución:* PE = ¿a dónde queremos llegar? / maximizar valor y rentabilidad / FODA, PESTEL, cuadro de mando. GCN = ¿cómo mantenemos y recuperamos las operaciones ante un incidente? / minimizar impacto y recuperar actividades prioritarias en los tiempos establecidos / BIA, BCP, DRP.

**B7. Redacta** dos objetivos SMART y la estrategia de continuidad que los protege (empresa de comercio electrónico que quiere crecer 30% en 12 meses).
*Solución modelo:* Objetivo: "Incrementar 30% las ventas online en 12 meses mediante campañas en redes y un programa de fidelización." Continuidad: proteger la plataforma de e-commerce, pasarela de pagos e inventario con hosting redundante en dos zonas, backups cada hora (RPO 1 h), RTO 2 h, pasarela de pagos alterna y plan de comunicación a clientes.

**B8. Verdadero/Falso.** (1) FODA reemplaza el BIA. (2) La BCM debe alinearse con los objetivos estratégicos. (3) Misión = futuro deseado. (4) Una estrategia sin continuidad es vulnerable. (5) El nivel operativo define las políticas.
*Solución:* (1) F; (2) V; (3) F (misión = razón de ser; visión = futuro deseado); (4) V; (5) F.
