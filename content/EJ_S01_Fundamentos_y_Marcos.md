---
tags: [ejercicios, continuidad-del-negocio, semana1]
fuente: SEM 1 (actividades de clase resueltas + ejercicios propuestos)
---
# Ejercicios · Semana 1 (fundamentos, DRII y BCI)
Teoría: [[S01_Sesion1_Introduccion_Continuidad_DRII_BCI]] · [[S01_Sesion2_Marco_Profesional_DRII_BCI]]

# A. Actividades de clase (resueltas)

## A1. "Analicemos" (S1)
1. *Universidad sin internet 2 h: ¿operación esencial?* La que sostiene el servicio académico/administrativo crítico del momento: plataforma virtual/clases y evaluaciones en línea, matrícula y comunicación con estudiantes. Se mantiene con un enlace de respaldo, datos móviles, procedimientos manuales o contingencia.
2. *Sin planificación previa, ¿hay continuidad aunque sobrevivamos?* No. La BC es el resultado de planificación y preparación adecuadas; sobrevivir por improvisación no es continuidad.
3. *¿Por qué la resiliencia es estratégica?* Requiere decisiones de la alta dirección (presupuesto, prioridades), involucra a toda la organización y los objetivos estratégicos; no solo a TI.

## A2. Tres hallazgos de BCP desactualizado (S2)
| Caso | Práctica DRII que falló | Qué revisar |
|---|---|---|
| 1. Cambio tecnológico (SaaS; DRP manda al centro de datos físico) | Desarrollo e implementación del plan + Ejercicios, mantenimiento y pruebas | Procedimientos DRP para la nube, contactos y SLA del proveedor, accesos, respaldos cloud, RTO/RPO, pruebas |
| 2. Cambió la criticidad (matrícula 24/7, 80% ingresos; RTO 24 h) | BIA (3) → luego Estrategia (4) | Rehacer BIA (impactos), ajustar RTO (p. ej. < 1 h), revisar estrategia |
| 3. Modalidad de trabajo remota (BCP exige reunirse en campus) | Gestión de la crisis y comunicación / Preparación y respuesta | Canales (Teams/WhatsApp), contactos, accesos remotos, roles/suplentes |
**Común:** la organización cambió, el plan no → incumple la sincronización operativa.

# B. Ejercicios propuestos (con solución)

**B1. Clasifica y propón medidas.** Incidente: (a) ciberataque ransomware; (b) incendio en el almacén; (c) fraude de un empleado; (d) quiebra de un proveedor único. Indica externo/interno, tipo, una medida preventiva y una reactiva.
*Solución:* (a) Externo–tecnológico; prev.: firewall/antivirus/backup offline; react.: restaurar datos desde respaldo, bloquear acceso, informar a clientes. (b) Interno–accidente; prev.: detectores, extintores, mantenimiento eléctrico; react.: plan de emergencia, reubicar operaciones en otra sede. (c) Interno–económico/humano; prev.: auditorías y segregación de funciones; react.: investigación y refuerzo de controles. (d) Externo–económico/proveedor; prev.: diversificar y evaluar proveedores; react.: cambiar de proveedor/ajustar cadena de suministro, plan de contingencia logística.

**B2. DRII vs BCI.** Completa: marco de referencia, certificación, nº de prácticas, alineación normativa.
*Solución:* DRII: PPBCM, CBCP, 10 dominios, prácticas propias del sector; BCI: GPG (7.ª ed., 2023), CBCI, 6 buenas prácticas (PP1–PP6), alineado con ISO 22301.

**B3. Ordena la evolución.** Relaciona período–enfoque–foco: 1950–1970, 1980–1990, 2000–actualidad.
*Solución:* 1950–70 Disaster Recovery / tecnología; 1980–90 Business Continuity / operaciones (BIA, sitios alternos); 2000+ Resiliencia organizacional / organización (alta dirección, ISO 22301).

**B4. Asocia la práctica DRII.** ¿A qué práctica corresponde cada situación? (1) Se aprueba el presupuesto y el comité de crisis. (2) Se calcula RTO de 2 h para facturación. (3) Se hace un simulacro de caída del sistema para el personal. (4) Se prueba el plan y se descubre que menciona un servidor ya retirado. (5) Se coordina con bomberos y proveedores. (6) Se identifica que un sismo puede dañar el edificio.
*Solución:* (1) Gestión del programa; (2) BIA; (3) Concientización y capacitación; (4) Ejercicios, mantenimiento y pruebas; (5) Coordinación con entidades externas; (6) Evaluación de riesgos.

**B5. Asocia la buena práctica BCI.** (1) Se redacta política y gobernanza del BCMS. (2) Se realizan campañas para crear cultura de continuidad. (3) Se ejecutan BIA y evaluación de riesgos. (4) Se evalúan opciones de solución según RTO. (5) Se implementan las soluciones y se documentan planes. (6) Se hacen auditorías y pruebas periódicas.
*Solución:* PP1 BCMS; PP2 Adopción; PP3 Análisis; PP4 Diseño de soluciones; PP5 Habilitación; PP6 Validación.

**B6. Caso.** Un banco cambió su centro de contacto a teletrabajo y su plan de comunicación sigue indicando reunirse en la sede y llamar por la central telefónica física. ¿Qué principio se violó, qué práctica del DRII falló y qué corregir?
*Solución:* Sincronización operativa (plan más viejo que el último cambio). Fallaron Gestión de la crisis y la comunicación y Ejercicios/mantenimiento. Corregir: canales digitales, lista de contactos, procedimientos remotos, pruebas del plan actualizado.

**B7. Verdadero/Falso.** (1) DRII y BCI sustituyen a ISO 22301. (2) La resiliencia es solo tema de TI. (3) El BIA es el corazón del programa. (4) Las medidas reactivas se aplican antes del incidente. (5) PPBCM es el marco del DRII.
*Solución:* (1) F (la ISO 22301 define requisitos del BCMS; DRII/BCI son buenas prácticas). (2) F. (3) V. (4) F (después). (5) V.

**B8. Define con tus palabras** resiliencia organizacional y sus 4 factores.
*Solución:* capacidad de anticiparse, responder y adaptarse a eventos adversos asegurando la continuidad; factores: planificación proactiva, capacidad de respuesta rápida, adaptabilidad, aprendizaje continuo.
