---
tags: [ejercicios, continuidad-del-negocio, semana6, riesgos]
fuente: SEM 6 (casos clínica, FarmaRuta, tabla VME, EduControl resueltos + ejercicios propuestos)
---
# Ejercicios · Semana 6 (amenazas, análisis, evaluación y tratamiento de riesgos)
Teoría: [[S06_Sesion1_Amenazas_y_Analisis_de_Riesgo]] · [[S06_Sesion2_Gestion_de_Riesgos]]
**Fórmulas:** Nivel de riesgo = P × I (1–5 cada uno; 1–4 Muy bajo, 5–8 Bajo, 9–12 Medio, 13–16 Alto, 17–25 Muy alto) · VME = P(%) × Impacto($) · Redacción: "Existe el riesgo de que [amenaza], debido a [vulnerabilidad], afecte [activo], generando [impacto]".

# A. Casos del curso (resueltos)

## A1. App web de clínica privada (S06-S11)
Activos críticos, amenazas, vulnerabilidades e impactos:
| Activo crítico | Amenaza | Vulnerabilidad | Posible impacto |
|---|---|---|---|
| Base de datos clínica | Ciberataque (ransomware) | Sistemas sin parches/controles de seguridad insuficientes | Cifrado o indisponibilidad de datos e interrupción del servicio |
| Servidor de producción | Error humano en producción | Cambios sin control ni revisiones; acceso sin control de autenticación | Caída del sistema, usuarios bloqueados o acceso indebido |
| Código fuente / plataforma | Sabotaje interno (ex-empleado) | Repositorio sin control de accesos ni auditoría | Fuga de propiedad intelectual o inyección de código malicioso |
| Credenciales / plataforma de pagos | Phishing | Personal sin capacitación y ausencia de MFA | Pérdida financiera, robo de datos bancarios |
| Datos de salud del paciente | Fuga por ingeniería social | Empleados sin capacitación en seguridad | Violación legal por datos sensibles, multas |
Otros activos: servicio cloud/hosting (amenaza: indisponibilidad del proveedor SaaS), personal desarrollador clave (renuncia), sistema de citas (DDoS).

## A2. Clasificación de amenazas por procedencia
Tabla resuelta en [[S06_Sesion1_Amenazas_y_Analisis_de_Riesgo]] (internas: 1, 2, 5, 8; externas: 3, 4, 6, 7, 9, 10, 11).

## A3. Ejercicio "Redacta un escenario de riesgo"
Elementos: DDoS (amenaza) · falta de mecanismos de protección y mitigación frente a DDoS (vulnerabilidad) · plataforma de comercio electrónico (activo) · interrupción del servicio de ventas y pérdidas económicas (impacto).
**Respuesta:** "Existe el riesgo de que un ataque DDoS, debido a la falta de mecanismos adecuados de protección y mitigación frente a DDoS, afecte la plataforma de comercio electrónico, generando interrupción del servicio de ventas y pérdidas económicas."

## A4. Tabla de análisis cuantitativo (VME)
| Riesgo | P | Impacto $ | VME |
|---|---|---|---|
| Caída del servidor crítico | 30% | $15 000 (5 días × $3 000) | **$4 500** |
| Pérdida de código fuente | 20% | $8 000 (200 h × $40) | **$1 600** |
| Fuga de información confidencial | 10% | $50 000 | **$5 000** |
| Fallo de autenticación (sin MFA) | 40% | $7 500 (3 días × $2 500) | **$3 000** |
| Rotación de personal | 25% | $12 000 | **$3 000** |
Orden por VME: Fuga ($5 000) > Caída ($4 500) > Autenticación = Rotación ($3 000) > Pérdida de código ($1 600).

## A5. Caso FarmaRuta (LogiTech S.A.) — matriz completa
Condiciones: 4 meses, equipo de 5 (líder, 2 devs, especialista GPS, soporte), sin presupuesto para contratar; servidores propios con suministro eléctrico inestable; Google Maps API; especialista GPS único; datos sensibles sin protocolos de cifrado; temporada de lluvias con riesgo de inundación para los servidores.
| # | Riesgo identificado | Causa – Consecuencia | Valor (P × I) | Nivel | Evaluación (tolerancia) | Tratamiento |
|---|---|---|---|---|---|---|
| 1 | Interrupción del servicio por fallas del suministro eléctrico (servidores locales) | Causa: servidores locales y suministro inestable. Consecuencia: indisponibilidad y posible afectación de datos/operaciones | P5 (Muy alta) × I4 (Alto) = **20** | Muy alto | No aceptable | **Mitigar**: UPS y respaldo eléctrico; migrar servicios críticos a infraestructura de mayor disponibilidad |
| 2 | Paralización del módulo de mapas por indisponibilidad del especialista GPS | Causa: una sola persona con el conocimiento y sin reemplazo. Consecuencia: paralización del módulo y retrasos | P4 (Alta) × I5 (Muy alto) = **20** | Muy alto | No aceptable | **Mitigar**: transferencia de conocimiento, documentar la configuración, capacitar a un respaldo |
| 3 | Incremento de costos por cambios en tarifas/condiciones de Google Maps API | Causa: dependencia de un servicio externo cuyas tarifas pueden cambiar. Consecuencia: incremento del costo y afectación al presupuesto | P3 (Media) × I4 (Alto) = **12** | Medio | Controlable/tolerable según criterios | **Mitigar**: monitorear cambios del proveedor, alertas de consumo y evaluar servicios alternativos de mapas |
| 4 | Exposición o fuga de datos sensibles por falta de controles de seguridad | Causa: sin cifrado ni responsabilidades de seguridad asignadas. Consecuencia: exposición de información, sanciones y daño reputacional | P3 (Media) × I5 (Muy alto) = **15** | Alto | No aceptable | **Mitigar**: cifrado, controles de acceso, gestión de privilegios y asignación de responsables de seguridad |
| 5 | Daño o indisponibilidad de servidores físicos por inundaciones | Causa: servidores en instalación expuesta en temporada de lluvias. Consecuencia: daño del hardware, interrupción y posible pérdida de información | P4 (Alta) × I4 (Alto) = **16** | Alto | No aceptable | **Mitigar** (podría combinarse con *evitar*): reubicar fuera del área expuesta, protección física y respaldos externos |
| 6 | Retrasos en atención de incidencias por depender de una única persona de soporte | Causa: un solo responsable, sin reemplazo. Consecuencia: demora en atención y afectación a usuarios | P3 (Media) × I3 (Moderado) = **9** | Medio | Controlable/tolerable según criterios | **Mitigar**: documentar procedimientos, base de conocimiento y capacitar a un soporte de respaldo |
*Opciones válidas alternativas:* riesgo 3 → **transferir** (contrato/plan tarifario fijo con el proveedor) o **aceptar activamente** con plan de contingencia (proveedor alterno); riesgo 5 → **transferir** (seguro contra daños).

## A6. EduControl (Soluciones SAC)
Matriz de los 6 riesgos ya resuelta por el docente en [[S06_Sesion2_Gestion_de_Riesgos]] (valores 15, 20, 20, 12, 12, 12; todos tratados con *mitigar*).

# B. Ejercicios propuestos (con solución)

**B1. Amenaza, vulnerabilidad, activo, impacto.** Identifica cada elemento: "Un ataque de phishing aprovecha que el personal no tiene capacitación y compromete las credenciales de la plataforma de pagos, causando pérdida financiera".
*Solución:* Amenaza = phishing; Vulnerabilidad = personal sin capacitación (y ausencia de MFA); Activo = credenciales/plataforma de pagos; Impacto = pérdida financiera.

**B2. ¿Amenaza o incidente disruptivo?** (a) Posible inundación en la zona. (b) Corte eléctrico que apagó el centro de datos y detuvo las operaciones. (c) Corte eléctrico pero el UPS y el generador mantuvieron todo operativo. (d) Ransomware que cifró el servidor.
*Solución:* (a) amenaza; (b) incidente disruptivo; (c) amenaza materializada **sin** incidente disruptivo; (d) incidente disruptivo.

**B3. Clasifica por fuente y por procedencia:** huelga de trabajadores; falla de disco duro; terremoto; error humano de configuración; pandemia.
*Solución:* huelga = humana/social (interna si es de la propia empresa, externa si es de proveedores); falla de disco = tecnológica/interna; terremoto = natural/externa; error de configuración = humana (o tecnológica)/interna; pandemia = social-sanitaria/externa.

**B4. Calcula el nivel de riesgo y clasifica:** (a) P=4, I=5; (b) P=2, I=3; (c) P=5, I=5; (d) P=1, I=2; (e) P=3, I=3.
*Solución:* (a) 20 Muy alto – no aceptable; (b) 6 Bajo – aceptable; (c) 25 Muy alto; (d) 2 Muy bajo – aceptable; (e) 9 Medio (moderado) – controlable.

**B5. VME y decisión.** Riesgo: caída del servidor en un despliegue; P = 25%, impacto $40 000; un servidor redundante cuesta $8 000. ¿Conviene?
*Solución:* VME = 0,25 × 40 000 = **$10 000** > costo del control $8 000 → económicamente conveniente **mitigar** (servidor redundante). Si el control costase $15 000, el criterio económico podría inclinar a aceptar/transferir.

**B6. Compara dos riesgos.** A: P 40%, impacto $10 000. B: P 20%, 15 días × $1 500/día. ¿Cuál tiene mayor VME?
*Solución:* A = $4 000. B = 0,20 × 22 500 = **$4 500** → B tiene mayor pérdida esperada aunque su probabilidad sea menor.

**B7. Identifica el tratamiento.** (a) Cancelar un módulo que depende de una tecnología insegura. (b) Contratar un seguro cibernético. (c) Implementar UPS y generador. (d) Aceptar una caída del hosting de hasta 2 h/mes con plan alterno. (e) Aceptar el retraso de 1 día en tareas no críticas, solo con seguimiento. (f) Mudar el centro de datos fuera de zona inundable.
*Solución:* (a) evitar; (b) transferir; (c) mitigar; (d) aceptar **activa**; (e) aceptar **pasiva**; (f) evitar.

**B8. Evaluación con tolerancia.** Un riesgo tiene P=3, I=4. ¿Aceptable? ¿Qué acción?
*Solución:* 12 → Medio → **Controlable/condicional**: requiere seguimiento y evaluar si necesita tratamiento según criterios (mitigar si el costo-beneficio lo justifica).

**B9. Apetito de riesgo.** ¿Por qué una startup y un banco pueden evaluar distinto el mismo riesgo de caída de 2 horas?
*Solución:* distinto apetito/tolerancia: la startup lo acepta por velocidad de lanzamiento; el banco tiene obligaciones regulatorias, operativas y de impacto a clientes, por lo que no lo acepta.

**B10. Redacta tres escenarios de riesgo** para una tienda online (uno de cada tipo de vulnerabilidad: tecnológica, organizacional, física).
*Solución modelo:* (1) Existe el riesgo de que un ataque de inyección SQL, debido a software desactualizado, afecte la BD de clientes, generando fuga de datos y multas. (2) Existe el riesgo de que la renuncia del único administrador, por dependencia de una sola persona, afecte el despliegue de la plataforma, generando retrasos y pérdida de ventas. (3) Existe el riesgo de que una inundación, debido a la ubicación de los servidores en el sótano, afecte el centro de datos, generando interrupción del servicio.

**B11. Matriz y prioridad.** Riesgos: R1 P3 I4; R2 P5 I3; R3 P2 I5; R4 P4 I4; R5 P1 I3. Calcula y ordena.
*Solución:* R1 = 12 (Medio); R2 = 15 (Alto); R3 = 10 (Medio); R4 = 16 (Alto); R5 = 3 (Muy bajo). Orden: R4 (16) > R2 (15) > R1 (12) > R3 (10) > R5 (3). Tratamiento prioritario: R4 y R2 (no aceptables).

**B12. Riesgo residual.** Tras mitigar un riesgo muy alto con backup en la nube y servidor nuevo, ¿qué se debe hacer?
*Solución:* volver a analizar el riesgo para determinar el **nivel residual** y verificar si ahora es aceptable; luego monitorear y revisar.

**B13. Cualitativo vs cuantitativo.** Clasifica: (a) "Alta (4) × Media (3) = 12"; (b) "25% × $40 000 = $10 000".
*Solución:* (a) cualitativo (escala ordinal, matriz); (b) cuantitativo (VME).

**B14. Verdadero/Falso.** (1) Transferir elimina el riesgo. (2) Un riesgo bajo hoy puede ser crítico mañana. (3) La aceptación activa no tiene plan de contingencia. (4) Los valores 1–5 son mediciones exactas. (5) La gestión de riesgos busca eliminar todos los riesgos.
*Solución:* (1) F; (2) V (riesgo dinámico); (3) F (sí lo tiene); (4) F (categorías ordinales); (5) F (se decide cómo enfrentarlos).
