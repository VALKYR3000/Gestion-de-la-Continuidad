---
tags: [ejercicios, continuidad-del-negocio, semana9, DRP, KPI]
fuente: SEM 9 (casos Instituto ALFA y Fintech Express resueltos + ejercicios propuestos)
---
# Ejercicios · Semana 9 (DRP, gobierno del plan y KPIs)
Teoría: [[S09_Sesion1_DRP_Fundamentos_y_Elementos]] · [[S09_Sesion2_Gobierno_del_Plan_DRP_y_KPIs]]
**Fórmulas:** % cumplimiento = (realizado / programado) × 100 · Exceso del RTO = RTA − RTO · Exceso del RPO = pérdida real − RPO · RTO cumplido si RTA ≤ RTO; RPO cumplido si la pérdida real ≤ RPO.

# A. Casos del curso (resueltos)

## A1. Instituto ALFA (S9-S17)
**Enunciado:** institución educativa con plataforma digital (matrículas, pagos, clases virtuales, materiales) en un data center local en su sede. En marzo, al iniciar el ciclo, una falla eléctrica dañó los servidores: **caída de 2 días**; el respaldo más reciente tenía **6 días** de antigüedad. TI activó parcialmente el DRP; problemas: plan sin actualizar hace más de 1 año; responsables que ya no trabajaban allí; sin sitio alterno; comunicación confusa y tardía a los estudiantes; última prueba hace 18 meses, sin incluir el sistema de matrículas. Alta dirección pidió revisión y nuevo esquema de actualización, pruebas y documentación.

**1. Cuatro (o más) deficiencias y el elemento del DRP**
| Deficiencia | Elemento del DRP |
|---|---|
| Plan no actualizado desde hacía más de un año | **9. Mantenimiento y actualización del plan** |
| Responsables señalados ya no trabajaban en la institución | **5. Roles y responsabilidades** (y mantenimiento: directorio desactualizado) |
| No se contaba con sitio alterno habilitado | **4. Estrategias de recuperación** (sitios alternos/redundancia) |
| Comunicación confusa y tardía a los estudiantes | **7. Plan de comunicaciones** |
| Última prueba hace 18 meses, sin incluir matrículas | **8. Plan de pruebas** |
| Respaldo de 6 días de antigüedad (datos perdidos) | **4. Estrategias (backups) / 3. BIA (RPO)** |
| Plataforma local única, sin redundancia ante falla eléctrica | **4. Estrategias (redundancia)** |

**2. Estrategia de respaldo: ¿qué problema evidencia un respaldo de 6 días y qué mejora?**
Evidencia que **no se cumple (o no se definió) el RPO**: se perdieron hasta 6 días de datos de matrículas y pagos; la frecuencia de backup no estaba alineada con la criticidad del sistema; no hubo verificación de respaldos ni copias fuera del sitio. **Mejora:** definir el RPO del sistema de matrícula en el BIA (p. ej. 15 min–1 h) y ajustar la frecuencia: **respaldos automáticos frecuentes (incrementales/horarios) + replicación** de la BD a la nube o sitio alterno; copias **fuera del sitio principal** (nube/offsite) y **verificación periódica** de restauración; monitoreo de los respaldos (KPI: % de respaldos verificados).

**3. Estrategia de recuperación tecnológica para la plataforma académica (y justificación)**
Propuesta: **migrar o replicar la plataforma a la nube** (o contratar un **warm/hot site** según el RTO) con **backups automáticos en la nube**, **replicación de la BD** y **redundancia de energía** (UPS/generador) y de conectividad. Por criticidad (matrícula: RTO 2 h, RPO 15 min): hot/warm site o servicios cloud con failover. Justificación: cumple RTO/RPO, es viable técnica y operativamente (proveedor cloud), reduce la dependencia de un data center local único y tiene razonable costo-beneficio frente a la pérdida de matrículas y reputación. Complementar con redundancia de red y energía.

**4. Mejoras para las próximas pruebas del DRP**
Incluir **todos los sistemas críticos** (matrícula, pagos, clases virtuales); definir **objetivos y criterios de éxito** (RTO/RPO); programar **frecuencia** (cada 6 meses o anual) y escalonar los tipos de prueba (tabletop → técnica → simulación parcial → completa fuera de horario); definir **responsables**; registrar **hallazgos y tiempos** (RTA, pérdida de datos) y un **plan de acción** posterior; probar la restauración desde respaldos y la comunicación a estudiantes; medir con KPIs de efectividad.

**5. Acciones de mantenimiento y actualización**
- **Responsables:** designar un Coordinador del DRP y responsables por sistema; actualizar el directorio de contactos con RR.HH. cuando haya altas/bajas.
- **Revisiones programadas:** cada 6 meses o anual.
- **Actualizaciones por cambios:** ante nuevos sistemas, software, proveedores o personal clave, y tras pruebas o incidentes (gestión del cambio).
- **Lecciones aprendidas:** tras cada prueba o incidente.
- **Control de cambios/versiones:** registro de versión vigente, fecha, responsables y cambios.
- Seguimiento con KPIs (% de planes revisados, % de pruebas ejecutadas) y aprobación de la alta dirección.

## A2. Fintech Express (S9-S18)
**Enunciado:** plataforma de servicios financieros digitales; transferencias interbancarias 24/7. En enero de 2025 TI elaboró el DRP (servidores On-Premise) con **RTO 1 h y RPO 15 min**. En mayo de 2026 un ransomware interrumpió el servicio. Situaciones: (1) el DRP indicaba restaurar la BD desde respaldos en el centro de datos local, pero 6 meses antes la BD se migró a AWS y se retiró la infraestructura anterior, sin evaluar el impacto sobre el DRP ni verificar si cumplía RTO/RPO; (2) los teléfonos del proveedor de conectividad en el plan eran de una empresa cuyo contrato se canceló el año anterior; (3) el técnico designado renunció 3 meses antes y su reemplazo no recibió capacitación ni sabía acceder a la consola de AWS. Resultado: **RTA 7 h**, **pérdida de las últimas 4 h de transacciones**.

**1. Indicadores de efectividad**
- **RTO:** establecido 1 h; real (RTA) 7 h → exceso = 7 − 1 = **6 horas** (el tiempo real fue **7 veces** el objetivo) → **no se cumplió**.
- **RPO:** establecido 15 min; pérdida real 4 h (240 min) → exceso = 240 − 15 = **225 minutos = 3 h 45 min** (la pérdida fue **16 veces** el máximo tolerable) → **no se cumplió**.
- Ambos indicadores de efectividad están incumplidos: la capacidad real de recuperación no alcanzó los objetivos.

**2. Deficiencias de gobierno (3 componentes) con evidencias**
| Componente | Deficiencia / evidencia |
|---|---|
| **1. Política de continuidad y compromiso de la Alta Dirección** | La Alta Dirección no exigió ni respaldó la revisión del DRP ante cambios mayores: la migración a AWS se realizó sin aprobar recursos para actualizar/probar el plan; no se verificó que la nueva arquitectura cumpliera RTO 1 h / RPO 15 min; falta de rendición de cuentas |
| **2. Gestión del cambio y actualización** | La migración a AWS **no se evaluó ni actualizó** en el DRP (procedimientos apuntaban a la infraestructura retirada); contactos del proveedor de conectividad desactualizados (contrato cancelado); no hubo pruebas tras el cambio |
| **3. Estructura organizacional, roles, responsabilidades y autoridades** | El técnico designado ya no estaba y el reemplazo **no fue capacitado**, desconocía sus responsabilidades y no tenía preparación/acceso a la consola AWS; no se actualizaron los roles |

**3. Auditoría interna: dos hallazgos relevantes y evidencias a revisar**
- **Hallazgo 1: DRP desactualizado frente a la arquitectura real** (la migración a AWS no pasó por gestión del cambio). *Evidencias*: control de versiones del DRP y fecha de la última revisión; registros/tickets de la migración y aprobaciones de cambio; diagramas de arquitectura vigentes vs procedimientos del DRP; resultados de pruebas posteriores a la migración; evaluación de RTO/RPO de la nueva solución.
- **Hallazgo 2: roles y contactos no actualizados, personal sin capacitación**. *Evidencias*: organigrama y lista de responsables del DRP vs altas/bajas de RR.HH.; registros de capacitación y de pruebas con participación de los designados; directorio de contactos y contratos vigentes de proveedores; accesos y permisos a AWS.
- (Otros posibles: ausencia de pruebas de efectividad, falta de KPIs, incumplimiento del RTO/RPO.)

# B. Ejercicios propuestos (con solución)

**B1. Define y distingue** BCP vs DRP.
*Solución:* BCP = cómo mantener o recuperar las actividades prioritarias del negocio (todas las áreas); DRP = cómo recuperar los recursos y servicios tecnológicos que las soportan (TI). El DRP es un subconjunto especializado del BCM.

**B2. Relaciona el elemento del DRP:** (a) "servidores, BD, redes y aplicaciones críticas"; (b) "Evaluar → Activar → Recuperar → Verificar → Restablecer"; (c) "revisiones cada 6 meses y control de versiones"; (d) "tabletop, prueba técnica, simulación parcial y completa"; (e) "responsables, audiencias, canales, frecuencia y plantillas"; (f) "hot, warm, cold, backups y redundancia".
*Solución:* (a) alcance; (b) procedimientos de respuesta y recuperación; (c) mantenimiento y actualización; (d) plan de pruebas; (e) plan de comunicaciones; (f) estrategias de recuperación.

**B3. Hot/warm/cold.** Asigna: (1) RTO de minutos, banco; (2) RTO de 1–2 días, herramienta de proyectos; (3) RTO de varios días, entorno de pruebas.
*Solución:* (1) hot site (alto costo, recuperación muy rápida); (2) warm site (intermedio); (3) cold site (bajo costo, más lento).

**B4. Define RTO/RPO para sistemas.** Una universidad: plataforma de matrícula (alta), correo (media), web (media), nóminas (alta), biblioteca (baja). Asigna valores razonables.
*Solución modelo (clase):* matrícula 2 h/15 min; correo 8 h/4 h; web 12 h/24 h; nóminas 12 h/4 h; biblioteca 48 h/24 h. A mayor prioridad, menor RTO/RPO.

**B5. Tipos de prueba.** ¿Qué prueba usarías para: (a) revisar el DRP con los equipos sin tocar nada; (b) restaurar un servidor de respaldo; (c) simular una caída del sistema de notas por 1 hora y seguir todos los pasos; (d) apagar intencionalmente un sistema real fuera de horario?
*Solución:* (a) tabletop; (b) prueba técnica; (c) simulación parcial; (d) simulación completa.

**B6. KPIs de cumplimiento — calcula.** Se programaron 12 pruebas y se ejecutaron 9; 40 personas críticas, 30 capacitadas; 8 planes por revisar, 6 revisados; 20 respaldos programados, 18 validados.
*Solución:* pruebas = 9/12 × 100 = **75%**; capacitación = 30/40 × 100 = **75%**; planes = 6/8 × 100 = **75%**; respaldos = 18/20 × 100 = **90%**.

**B7. KPIs de efectividad — evalúa.** RTO 2 h, RPO 15 min. Prueba A: RTA 1 h 40 min, pérdida 10 min. Prueba B: RTA 3 h, pérdida 5 min. Prueba C: RTA 1 h 50 min, pérdida 45 min.
*Solución:* A: cumple RTO y RPO (exitosa); B: **no** cumple el RTO (exceso 1 h), sí el RPO; C: sí el RTO, **no** el RPO (exceso 30 min). % de recuperaciones exitosas = 1/3 ≈ **33%**.

**B8. Cumplimiento vs efectividad.** Clasifica: % de planes revisados; RTA; cumplimiento del RPO; nº de simulacros; % de servicios críticos recuperados; % de respaldos verificados.
*Solución:* cumplimiento: % planes revisados, nº simulacros, % respaldos verificados; efectividad: RTA, cumplimiento del RPO, % servicios críticos recuperados.

**B9. ¿Por qué se puede cumplir todo y fallar?** Argumenta con un ejemplo.
*Solución:* una empresa hace los 4 simulacros anuales y capacita a todos (cumplimiento 100%) pero sus pruebas no incluyen el nuevo sistema o el hardware de recuperación es insuficiente: en la prueba tarda 4 h con un RTO de 2 h. El cumplimiento no garantiza efectividad.

**B10. Gobierno del plan.** Asigna la función: (1) aprueba recursos y políticas; (2) coordina revisiones y pruebas, da seguimiento a indicadores; (3) restaura servidores y verifica servicios; (4) revisa evidencias y controles de forma independiente.
*Solución:* (1) Alta Dirección (estratégico: orienta y decide); (2) Coordinador del DRP (táctico: coordina, supervisa y prepara); (3) Equipos técnicos (operativo: ejecuta y responde); (4) Auditoría interna (evalúa y verifica; no ejecuta).

**B11. Componentes del gobierno.** Identifica el componente: (a) la dirección aprueba recursos y respalda las pruebas; (b) ante un cambio de proveedor se evalúa y actualiza el DRP; (c) se define quién activa el plan y quién ejecuta cada tarea; con cláusula ISO 22301 si aplica.
*Solución:* (a) Componente 1 (Cláusula 5); (b) Componente 2 (gestión del cambio); (c) Componente 3 (Cláusula 5.3).

**B12. Con/sin gobierno.** Una empresa migra su BD a AWS. Describe qué haría con gobierno del plan.
*Solución:* proponer el cambio → revisar su impacto en el DRP → verificar que cumpla RTO/RPO → actualizar estrategias y procedimientos → actualizar responsables → que la Alta Dirección apruebe recursos → prueba técnica en la nueva arquitectura antes de retirar la solución anterior.

**B13. Redacta un plan de comunicaciones** para la caída de la plataforma virtual antes de los exámenes finales.
*Solución modelo:* Responsable: Área de Comunicaciones; mensaje inicial: "Por causas técnicas, el sistema estará inoperativo las próximas horas. Estamos ejecutando el plan de recuperación; informaremos el nuevo cronograma"; canales: web, redes, correo masivo; frecuencia: cada 4 h hasta la normalización; audiencias: estudiantes, docentes, personal; mensajes predefinidos.

**B14. Calcula excesos.** RTO 3 h, RTA 5 h 30 min; RPO 30 min, pérdida real 2 h.
*Solución:* exceso RTO = 2 h 30 min (no cumple); exceso RPO = 1 h 30 min (no cumple).

**B15. Verdadero/Falso.** (1) El DRP cubre RR.HH. y logística. (2) Un DRP puede ser un documento estático. (3) Auditoría ejecuta la recuperación. (4) El Coordinador del DRP activa el plan y supervisa su ejecución. (5) Los KPIs de cumplimiento demuestran por sí solos que la recuperación es efectiva.
*Solución:* (1) F (BCP); (2) F; (3) F (evalúa y verifica); (4) V; (5) F.
