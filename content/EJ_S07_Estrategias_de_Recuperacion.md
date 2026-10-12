---
tags: [ejercicios, continuidad-del-negocio, semana7, estrategias]
fuente: SEM 7 (caso ransomware y 4 ejercicios de costo-beneficio de clase, resueltos + ejercicios propuestos)
---
# Ejercicios · Semana 7 (estrategias de recuperación y análisis costo-beneficio)
Teoría: [[S07_Sesion1_Estrategias_de_Recuperacion]] · [[S07_Sesion2_Seleccion_y_Justificacion_de_Estrategias]]
**Fórmulas:**
- Pérdida esperada anual (PEA) = ingresos por hora × horas de interrupción × probabilidad anual (o × nº de eventos/año si es frecuencia).
- Costo total anual (con alternativa) = PEA con alternativa + costo anual de la estrategia.
- **Ahorro anual = PEA sin estrategia − costo total anual.** (Positivo = conviene económicamente; negativo = costo adicional esperado.)
- Brecha de recuperación = capacidad actual − RTO requerido.

# A. Caso de clase (resuelto)

## A1. Ransomware en Soluciones SAC (empresa de desarrollo de software)
**Enunciado:** servidores locales con repositorio de código, BD de clientes, herramientas de integración y pruebas, correo corporativo sincronizado con servidores internos; ransomware cifra los servidores principales y los equipos de los empleados; rescate en criptomonedas; nadie puede acceder; riesgo de penalidades graves si no se recupera en menos de 48 horas.

**1. Incidente disruptivo y activos/procesos prioritarios afectados**
Incidente: **ataque de ransomware** que cifra servidores y equipos. Activos: repositorio de código fuente, BD de clientes, herramientas de integración/pruebas (alojadas localmente), correo corporativo, equipos de los empleados, servidores locales. Procesos prioritarios: desarrollo de software, pruebas y entrega de versiones, atención y comunicación con clientes, gestión de proyectos, cumplimiento contractual.

**2. Necesidades de recuperación del negocio**
Recuperar acceso al **código fuente, BD de clientes y herramientas** de desarrollo/pruebas y al correo, **en menos de 48 h (RTO/MTPD ≈ 48 h; para operar con seguridad un RTO menor, p. ej. 24 h)** para evitar penalidades; pérdida mínima de información (RPO bajo: p. ej. 4–24 h de código/datos); restablecer equipos de trabajo y comunicación con clientes; asegurar que lo restaurado esté libre de malware (integridad y seguridad).

**3. Alternativas (≥ 3)**
1. **Restauración desde backups limpios/offline o en la nube** (inmutables), tras erradicar el malware.
2. **Migrar a servicios en la nube** (repositorio Git alojado, CI/CD y correo SaaS, escritorios virtuales) con acceso remoto desde equipos alternos.
3. **Sitio alterno / infraestructura alterna** (warm/hot site o VMs preconfiguradas) para levantar el entorno de desarrollo.
4. **Equipos de reemplazo y teletrabajo** (laptops limpias, VPN) para que el equipo siga trabajando.
5. **Proveedor/servicio externo de respuesta a incidentes y recuperación (DRaaS)** y comunicación proactiva a clientes (tercerización temporal).
6. (Descartada) Pagar el rescate: no garantiza recuperación, financia al atacante y no resuelve la brecha.

**4. Estrategia seleccionada y por qué**
Combinar: **restauración desde backups inmutables/offline (alternativa 1)** + **servicios en la nube y teletrabajo (2 y 4)** + apoyo de proveedor de respuesta a incidentes. Justificación: cumple el límite de 48 h (los servicios cloud se pueden habilitar en horas), minimiza pérdida de datos (RPO con backups frecuentes), es viable técnica y operativamente con recursos adicionales contratables, tiene razonable costo-beneficio frente a penalidades graves, y reduce la dependencia de servidores locales. Complementar con comunicación a clientes y aislamiento/erradicación del malware antes de reconectar.

# B. Ejercicios de costo-beneficio de clase (resueltos)

## B1. Ejercicio 1 — El servidor de pagos
Datos: ingresos $2 000/h; frecuencia **1 interrupción/año**; sin estrategia 24 h; alternativa: replicación en la nube con costo anual **$10 000** que reduce la interrupción a **6 h**.
1. PEA sin estrategia = 2 000 × 24 × 1 = **$48 000**.
2. PEA con replicación = 2 000 × 6 × 1 = **$12 000**.
3. Costo total anual = 12 000 + 10 000 = **$22 000**.
4. Ahorro anual = 48 000 − 22 000 = **$26 000**.
5. **Interpretación:** el ahorro es positivo: la inversión está justificada económicamente (reduce significativamente la pérdida). Aun así, la decisión final también considera RTO/RPO, recursos y viabilidad.

## B2. Ejercicio 2 — El almacén logístico (baja probabilidad)
Datos: pérdida $5 000/h; **probabilidad anual 5% (0,05)** de incendio/desastre mayor; sin estrategia 120 h; sitio alterno con costo anual **$40 000** que reduce a **24 h**.
1. PEA sin estrategia = 5 000 × 120 × 0,05 = **$30 000**.
2. PEA con sitio alterno = 5 000 × 24 × 0,05 = **$6 000**.
3. Costo total anual = 6 000 + 40 000 = **$46 000**.
4. Ahorro anual = 30 000 − 46 000 = **−$16 000**.
5. **Interpretación:** ahorro negativo (costo adicional esperado de $16 000 al año) pero **no significa descartar automáticamente** la alternativa: la probabilidad es baja pero el impacto, si ocurre, es enorme (un solo evento = 5 000 × 120 = $600 000 de pérdida sin estrategia vs $120 000 con ella); también importan el RTO/RPO, la criticidad del proceso, la viabilidad y los requisitos del negocio (y legales/contractuales). Se evalúan otras opciones más baratas (warm/cold site, seguro) y la aversión al riesgo de la empresa.

## B3. Ejercicio 3 — Call center (alta frecuencia)
Datos: ingresos $500/h; **4 interrupciones de Internet al año**; sin estrategia 10 h cada una; línea redundante con costo anual **$2 000** que reduce cada interrupción a **1 h**.
1. PEA sin estrategia = 500 × 10 × 4 = **$20 000**.
2. PEA con línea redundante = 500 × 1 × 4 = **$2 000**.
3. Costo total anual = 2 000 + 2 000 = **$4 000**.
4. Ahorro anual = 20 000 − 4 000 = **$16 000**.
5. **Interpretación:** la alta frecuencia multiplica la pérdida esperada anual, por lo que incluso una alternativa barata se justifica ampliamente (la frecuencia aumenta el beneficio de reducir cada interrupción). Se usa la **frecuencia** (4 eventos/año), no probabilidad.

## B4. Ejercicio 4 — Selección de la estrategia (consultoría)
Datos: ingresos $3 500/h; **2 interrupciones/año**; sin estrategia 48 h cada una; **RTO de 4 h**. Alternativa A (Backup remoto): costo anual $15 000, recuperación 12 h, se implementa con recursos actuales, viabilidad alta, presupuesto disponible. Alternativa B (Hot site): costo $100 000, recuperación 2 h, requiere proveedor especializado, viabilidad alta mediante proveedor, la empresa dispone del presupuesto necesario.
1. PEA sin estrategia = 3 500 × 48 × 2 = **$336 000**.
2. **Alternativa A:** PEA = 3 500 × 12 × 2 = **$84 000**; costo total = 84 000 + 15 000 = **$99 000**; ahorro = 336 000 − 99 000 = **$237 000**. **Alternativa B:** PEA = 3 500 × 2 × 2 = **$14 000**; costo total = 14 000 + 100 000 = **$114 000**; ahorro = 336 000 − 114 000 = **$222 000**.
3. **RTO 4 h:** A (12 h) **no cumple**; B (2 h) **sí cumple**.
4. **Comparación:**
   | Criterio | A (Backup remoto) | B (Hot site) |
   |---|---|---|
   | RTO (4 h) | No (12 h) | Sí (2 h) |
   | Recursos y capacidades | Con recursos actuales | Requiere proveedor especializado |
   | Viabilidad técnica-operativa | Alta | Alta (mediante proveedor) |
   | Costo-beneficio | Mayor ahorro ($237 000) | Menor ahorro ($222 000) pero cumple el requisito |
5. **Selección: Alternativa B (Hot site).** Aunque A tiene mayor ahorro económico y menor costo, **no cumple el RTO de 4 h** exigido por el BIA; B lo cumple (2 h), es viable (proveedor especializado) y el presupuesto está disponible, y su ahorro sigue siendo muy alto ($222 000). El RTO es un requisito del negocio, no negociable por costo.

## B5. Caso Soluciones SAC (comparación de sitios) — recordatorio
Warm site: mayor ahorro ($51 000) pero no cumple RTO 4 h (6 h) → se selecciona **Hot site** (único que cumple, ahorro $25 500, presupuesto disponible). Ver [[S07_Sesion2_Seleccion_y_Justificacion_de_Estrategias]].

# C. Ejercicios propuestos (con solución)

**C1. Brecha.** RTO requerido de la BD: 3 h; capacidad actual de restauración: 7 h. ¿Brecha? ¿Qué alternativa propones?
*Solución:* 7 − 3 = **4 h**. Cerrarla con replicación a sitio alterno/nube + failover (RTO bajo), o warm site si el presupuesto es limitado y la brecha restante es aceptable.

**C2. Clasifica por RTO/RPO.** (a) Plataforma de pagos RTO 15 min, RPO 1 min; (b) herramienta de proyectos RTO 1 día; (c) ambiente de pruebas RTO 5 días. Asigna alternativa.
*Solución:* (a) hot site/replicación en tiempo real/failover; (b) warm site o backups frecuentes con restauración rápida; (c) cold site, restauración desde backups o recuperación manual.

**C3. Tipo de estrategia.** (a) Servidores en clúster con failover; (b) procedimiento manual en papel mientras cae el sistema; (c) teletrabajo con VPN; (d) reasignar funciones al técnico alterno; (e) acuerdo con proveedor alterno de internet; (f) VM preconfigurada.
*Solución:* (a) tecnológica; (b) organizativa; (c) logística; (d) organizativa; (e) logística (acuerdos con terceros); (f) tecnológica.

**C4. Calcula.** Tienda online: $4 000/h; probabilidad anual 20%; sin estrategia 30 h; con warm site (costo $15 000/año) 5 h. ¿Ahorro?
*Solución:* PEA sin = 4 000 × 30 × 0,20 = **$24 000**; PEA con = 4 000 × 5 × 0,20 = **$4 000**; costo total = 4 000 + 15 000 = **$19 000**; ahorro = 24 000 − 19 000 = **$5 000** (conviene económicamente).

**C5. Frecuencia vs probabilidad.** Un banco tiene 3 caídas al año de 4 h; $10 000/h. Sin estrategia; con failover automático cada caída dura 0,5 h, costo $20 000/año.
*Solución:* PEA sin = 10 000 × 4 × 3 = **$120 000**; con = 10 000 × 0,5 × 3 = **$15 000**; costo total = **$35 000**; ahorro = **$85 000**.

**C6. Selección.** Alternativas para RTO 2 h: X (cold, 20 h, ahorro $60 000), Y (warm, 5 h, ahorro $80 000), Z (hot, 1 h, ahorro $50 000). ¿Cuál y por qué?
*Solución:* **Z**: única que cumple el RTO (1 h ≤ 2 h), aunque tenga el menor ahorro; X e Y incumplen el RTO.

**C7. Argumenta.** Si el hot site no entra en el presupuesto y el RTO es 4 h, ¿qué haces?
*Solución:* no relajar el RTO por falta de presupuesto: evaluar alternativas híbridas (warm site mejorado, nube con VMs preconfiguradas/DRaaS, financiamiento/contratación del servicio) que cumplan o se acerquen al RTO y escalar la decisión al nivel estratégico si hay brecha.

**C8. Criterios.** Enumera los 4 criterios de evaluación y un ejemplo de pregunta de cada uno.
*Solución:* RTO/RPO (¿cumple el tiempo objetivo?); capacidades y recursos (¿tenemos o podemos adquirir lo necesario?); viabilidad técnica y operativa (¿se puede implementar y mantener?); costo-beneficio (¿la inversión se justifica frente a las pérdidas evitadas?).

**C9. Verdadero/Falso.** (1) La alternativa más barata siempre es la mejor. (2) Una estrategia puede requerir recursos que hoy no se tienen. (3) Un ahorro negativo implica descartar automáticamente. (4) 4 eventos/año equivalen a 400% de probabilidad. (5) El RTO se puede modificar por límite presupuestario.
*Solución:* (1) F; (2) V; (3) F; (4) F; (5) F.
