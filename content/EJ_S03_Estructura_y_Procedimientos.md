---
tags: [ejercicios, continuidad-del-negocio, semana3]
fuente: SEM 3 (casos MediCloud y FINANCIERA resueltos + ejercicios propuestos)
---
# Ejercicios · Semana 3 (estructura, roles, autoridad, procedimientos)
Teoría: [[S03_Sesion1_Estructura_Organizacional_Roles]] · [[S03_Sesion2_Procedimientos_Respuesta_Recuperacion]]

# A. Casos del curso (resueltos)

## A1. Caso MediCloud Perú (S03-S5)
**Enunciado:** SaaS para ~35 clínicas (citas, admisión, historias clínicas, laboratorio, facturación), infraestructura en la nube; SGCN, procedimientos y estructura con niveles de autoridad. 9:15 a. m. degradación; TI hace *failover* (tiene autoridad). 9:35: 12 clínicas sin historias clínicas, laboratorio intermitente, facturación caída, reclamos, proveedor de nube investigando → TI informa al Coordinador BCM. 10:30: 28/35 clínicas afectadas, clínicas con procedimientos alternativos, proveedor sin tiempo de recuperación, riesgo de superar objetivos de recuperación, Comunicaciones necesita definir información a clientes, Legal advierte compromisos contractuales, TI propone infraestructura adicional con costo que supera la autoridad presupuestal del Coordinador.

**1. 9:15 a. m., ¿quién actúa y por qué no necesita esperar autorización?**
Actúa el **equipo de TI (nivel operativo)**. Es un *incidente menor*: falla de un componente con redundancia y el procedimiento establece que TI tiene **autoridad previamente definida** para hacer failover sin pedir autorización superior. La autoridad se define antes de la interrupción, así se actúa con rapidez dentro del límite establecido y luego se informa.

**2. ¿Cuándo deja de ser solo operativo y entra el nivel táctico?**
A las **9:35 a. m.**: el failover no resolvió; ya no es un solo componente. Evidencia: 12 clínicas sin acceso a historias clínicas, laboratorio con intermitencias, **facturación indisponible** (varios servicios críticos y áreas), reclamos masivos en Atención al Cliente y proveedor de nube con degradación propia. Es un *incidente significativo*: afecta varios servicios y áreas, requiere coordinación → TI informa al Coordinador BCM (autoridad táctica).

**3. ¿Qué articula y coordina el Coordinador BCM? (≥3 actores)**
- **TI/equipos operativos**: estado técnico, avance de la recuperación, tiempos estimados, recursos necesarios.
- **Proveedor de nube**: estado de la degradación, tiempo estimado de recuperación, soporte/escalamiento contractual (SLA).
- **Comunicaciones**: mensaje oportuno y consistente a clínicas y clientes (qué se informa, canales, frecuencia).
- **Legal y Cumplimiento**: obligaciones contractuales/regulatorias por la indisponibilidad (datos de salud, SLA).
- **Atención al Cliente**: volumen y tipo de reclamos, guion de respuesta, procedimientos alternativos para clínicas.
- **Logística/Finanzas**: recursos adicionales y costos.
- Además consolida información (RTO/RPO, impacto) y evalúa si escala.

**4. ¿Qué siguen ejecutando los equipos operativos?** Acciones técnicas de contención y recuperación dentro de su autoridad: análisis y corrección técnica, monitoreo, pruebas de funcionamiento, restauración/failover adicional autorizado, registro de acciones y reporte periódico al Coordinador. El Coordinador no los reemplaza: **orquesta**.

**5. Equipos de apoyo y qué aportan:** Comunicaciones/RR.PP. (mensajes a clientes y medios); Legal y Cumplimiento (compromisos contractuales, notificaciones); Apoyo logístico (recursos/infraestructura adicional, proveedores); Auditoría (evaluación independiente, evidencias y lecciones aprendidas); también Atención al Cliente como área afectada.

**6. Elementos de las 10:30 que justifican escalar al CGC:** 28 de 35 clínicas afectadas (impacto masivo, múltiples servicios críticos y clientes); proveedor sin tiempo definitivo de recuperación (incertidumbre); riesgo de **superar los objetivos de recuperación** (RTO/MTPD); implicancias **contractuales y legales**; reputación y comunicación a clientes de alto impacto; **gasto extraordinario que supera la autoridad presupuestal del Coordinador**. Es *incidente grave/crisis* → autoridad estratégica.

**7. Decisiones del Comité vs. las que NO deben ir al Comité**
- **Comité (estratégicas):** autorizar la infraestructura adicional de costo extraordinario; posición ante clientes/compensaciones y compromisos contractuales; declarar la crisis; priorizar servicios/clientes a proteger; aprobar el mensaje y estrategia de comunicación de alto impacto; aceptar riesgos residuales.
- **No al Comité:** acciones técnicas de recuperación (nivel operativo); coordinación entre áreas, seguimiento y consolidación de estado, solicitar apoyo a proveedor (táctico); activar procedimientos alternativos ya aprobados.

**8. Esquema**
| ¿Quién DECIDE? | ¿Quién COORDINA? | ¿Quién EJECUTA? | ¿Qué ESCALA? |
|---|---|---|---|
| Comité de Gestión de Crisis (gasto extraordinario, comunicación/contratos, prioridades) | Coordinador BCM con Comunicaciones, Legal, Logística, Atención al Cliente, proveedor | TI y equipos de recuperación (failover, restauración, pruebas, registro) | Impacto (28/35 clínicas), servicios críticos afectados, tiempo transcurrido vs RTO, estado del proveedor, riesgos legales/reputacionales, recursos extra solicitados, opciones recomendadas |
Flujo: Operativo detecta y ejecuta → informa → Coordinador evalúa/coordina → escala → Comité decide → Coordinador comunica y coordina → Operativo ejecuta.

## A2. Caso FINANCIERA S.A.C. (S03-S6)
**Datos:** plataforma de pagos 24/7, ~18 000 transacciones/día, BIA: servicio crítico, **RTO 2 h, RPO 30 min**. 10:15 degradación; 10:25 ~40% de transacciones con problemas; 10:35 TI comunica al Coordinador; 10:50 se decide usar infraestructura alterna; 11:20 componentes recuperados, verificaciones; 11:40 habilitación progresiva; 12:30 estable; revisión: notificaciones internas demoraron y un procedimiento técnico estaba desactualizado.

**1. Las cuatro fases en el caso**
1. **Activación y evaluación (10:15–10:35):** detección por monitoreo, notificación a TI, evaluación (40% de transacciones, un servidor anómalo, riesgo de propagación, clientes corporativos), aplicación de criterios (criticidad, afectación, tiempo, riesgo), comunicación al Coordinador y decisión de escalar (algunas acciones exceden la autoridad técnica).
2. **Respuesta y contención (10:35–10:50):** TI ejecuta acciones dentro de su autoridad para que la afectación no se extienda; se coordinan áreas; seguimiento de la plataforma; se activa la infraestructura alterna previamente preparada siguiendo procedimientos y niveles de autoridad (medida de continuidad inmediata).
3. **Recuperación y reanudación (10:50–12:30):** parte del servicio vuelve; 11:20 componentes recuperados y verificaciones técnicas y funcionales (disponibilidad, integridad/consistencia de datos, transacciones, operaciones pendientes, estabilidad); 11:40 habilitación progresiva; monitoreo de estabilidad.
4. **Cierre y mejora (desde 12:30):** confirmación de estabilidad, conservación de registros (alertas, tiempos, decisiones, comunicaciones, procedimientos y resultados), reunión de revisión, hallazgos (notificaciones lentas, procedimiento desactualizado) → acciones de mejora y actualización de documentos.
- Métrica: la interrupción desde 10:15 hasta 11:40 (habilitación) son ~85 min **< RTO 2 h** (se cumple si se toma 11:40 como recuperación del servicio).

**2. Procedimiento durante la interrupción (ej.: recuperación tecnológica en infraestructura alterna)**
Secuencia: (1) verificar condición del servicio (confirmar afectación) → (2) ejecutar acción técnica autorizada (conmutación/failover a infraestructura alterna) → (3) comprobar funcionamiento (conectividad, transacciones, integridad de datos) → (4) registrar resultado (acciones, tiempos, observaciones) → (5) reportar al coordinador.
- **Nivel:** operativo ejecuta; el táctico (Coordinador) coordina y decide dentro de su autoridad; el estratégico interviene solo si se exceden umbrales (impacto sobre clientes corporativos, recursos extraordinarios, riesgo de superar el RTO).
- **Hasta dónde llega la autoridad operativa:** acciones técnicas previamente autorizadas (aislar, reiniciar, failover). Usar la infraestructura alterna requiere seguir los procedimientos y niveles de autoridad de FINANCIERA (el caso lo indica); si requiere decisión fuera de su autoridad, escala.

**3. ¿Cuándo escalar y qué comunicar?**
- Escalar de operativo a táctico a las **10:35** (acciones exceden autoridad técnica y riesgo de propagación; 40% de transacciones; clientes corporativos reclaman). Escalar al estratégico si: se acerca el RTO de 2 h (vence 12:15), hay afectación de clientes corporativos/regulatoria o se requieren recursos extraordinarios.
- **Información a comunicar:** qué ocurrió y servicios afectados, alcance (% de transacciones, clientes), tiempo transcurrido vs RTO/RPO, acciones realizadas, estado de recuperación y tiempos estimados, riesgos, recursos requeridos y decisiones solicitadas. Hacia clientes: mensaje claro, oportuno, confiable y coordinado.

**4. ¿Usar la infraestructura alterna significa que la recuperación finalizó?**
**No.** Es una medida de continuidad inmediata/parte de la recuperación. Aún faltan: operaciones pendientes, verificar integridad y consistencia de datos (RPO 30 min), validar transacciones, reanudación gradual y monitoreo de estabilidad (Fase 3), y luego normalización, cierre y mejora (Fase 4). La recuperación no es volver de inmediato a la normalidad.

# B. Ejercicios propuestos (con solución)

**B1. Clasificación de incidentes.** Indica nivel de incidente (menor / significativo / grave-crisis), quién tiene la autoridad y si se escala: (a) falla un servidor con redundancia; (b) caen ventas, facturación y portal de clientes; (c) caída prolongada con riesgo legal, reputacional y necesidad de presupuesto extraordinario.
*Solución:* (a) Menor — autoridad operativa (TI ejecuta failover, informa al Coordinador); (b) Significativo — Coordinador BCM activa/coordina el plan; (c) Grave/crisis — Comité de Gestión de Crisis decide y autoriza recursos extraordinarios.

**B2. Rol / responsabilidad / autoridad.** Completa para "Responsable de TI": rol, responsabilidad y autoridad.
*Solución:* Rol: equipo operativo de recuperación tecnológica. Responsabilidad: recuperar el servicio afectado y verificar su restablecimiento. Autoridad: ejecutar acciones técnicas previamente autorizadas (p. ej., failover) dentro de criterios y procedimientos; escalar lo que excede.

**B3. Identifica el nivel.** ¿Qué nivel realiza cada acción? (1) Declarar la crisis. (2) Activar el plan de continuidad dentro de los criterios aprobados. (3) Restaurar un backup. (4) Aprobar un gasto extraordinario. (5) Consolidar información del incidente. (6) Redactar el comunicado a clientes.
*Solución:* (1) Estratégico; (2) Táctico (Coordinador BCM); (3) Operativo; (4) Estratégico; (5) Táctico; (6) Apoyo/Comunicaciones (táctico) con aprobación según el nivel.

**B4. Ordena las fases.** Ordena: cierre formal, detección, contención del impacto, reanudación, notificación, decisión de escalamiento, lecciones aprendidas, verificación y validación.
*Solución:* Fase 1: detección → notificación → decisión de escalamiento; Fase 2: contención del impacto; Fase 3: verificación y validación → reanudación; Fase 4: cierre formal → lecciones aprendidas.

**B5. Verdadero/Falso justificado.**
1. La Fase 2 busca recuperar todos los servicios. (F: busca contener el impacto y proteger lo crítico.)
2. La evaluación y la respuesta pueden superponerse. (V: si hay acción inmediata autorizada.)
3. El Coordinador BCM ejecuta todas las acciones técnicas. (F: orquesta la respuesta.)
4. La autoridad se define durante la crisis. (F: antes de la interrupción.)
5. Cerrar la respuesta es el final del ciclo. (F: inicio de un nuevo ciclo de mejora.)

**B6. Escalamiento.** Una e-commerce pierde su pasarela de pagos a las 9:00; RTO 1 h; el proveedor dice 4 h. TI hizo todo lo permitido. ¿Qué hacer?
*Solución:* TI informa al Coordinador (impacto > RTO); el Coordinador evalúa, coordina con proveedor alterno/Comunicaciones/Legal y **escala al Comité** porque se superará el RTO, hay impacto financiero/reputacional y puede requerirse un proveedor alterno (recursos extraordinarios). Comité decide; Coordinador comunica; TI ejecuta la conmutación.

**B7. Redacta un procedimiento operativo** para "caída de la base de datos con réplica disponible".
*Solución modelo:* 1 Verificar indisponibilidad de BD principal. 2 Verificar disponibilidad de la réplica y su consistencia (RPO). 3 Ejecutar failover autorizado. 4 Comprobar conectividad y funcionamiento de la aplicación. 5 Registrar acciones, tiempos y observaciones. 6 Reportar al Coordinador BCM (y escalar si no se cumple RTO).
