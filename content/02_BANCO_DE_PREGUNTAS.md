---
tags: [examen, preguntas, continuidad-del-negocio]
---
# Banco de preguntas (30) · Continuidad del Negocio
Volver: [[index]] · [[01_RESUMEN_EXPRESS]]

> [!question]- 1. ¿Qué es la continuidad del negocio y por qué tiene enfoque estratégico y operativo?
> Capacidad de mantener las operaciones esenciales durante y después de un incidente disruptivo. Estratégico: se planifica a nivel directivo y forma parte de la visión a largo plazo. Operativo: se concreta en procedimientos, herramientas y acciones para responder y recuperarse. [[S01_Sesion1_Introduccion_Continuidad_DRII_BCI]]

> [!question]- 2. Diferencie medidas preventivas y reactivas con un ejemplo de ciberataque.
> Preventivas (antes): firewalls, antivirus, políticas de seguridad. Reactivas (durante/después): restaurar datos, bloquear al atacante, informar a clientes. [[S01_Sesion1_Introduccion_Continuidad_DRII_BCI]]

> [!question]- 3. ¿Cuántas prácticas profesionales tiene el DRII y cuántas el BCI? ¿Qué norma no sustituyen?
> DRII: 10 (PPBCM, certificación CBCP). BCI: 6 buenas prácticas (GPG 7.0, certificación CBCI). No sustituyen a la ISO 22301, que establece los requisitos de un BCMS. [[S01_Sesion2_Marco_Profesional_DRII_BCI]]

> [!question]- 4. Nombre las 6 buenas prácticas del BCI.
> Establecimiento de un BCMS; adopción de la continuidad; análisis (BIA + riesgos); diseño de soluciones; habilitación de soluciones; validación. [[S01_Sesion2_Marco_Profesional_DRII_BCI]]

> [!question]- 5. Una empresa migró su BD a la nube pero el DRP sigue enviando al técnico al centro de datos físico. ¿Qué práctica falló y qué principio se violó?
> Desarrollo/implementación del plan y ejercicios/mantenimiento/pruebas. Se violó la sincronización operativa: el plan nunca debe ser más viejo que el último cambio importante de la empresa. [[S01_Sesion2_Marco_Profesional_DRII_BCI]]

> [!question]- 6. ¿Qué significa SMART y cómo se valida "Incrementar 25% la captación de pymes en 6 meses con marketing digital"?
> Specific, Measurable, Achievable, Relevant, Time-bound. S: captar nuevas pymes; M: 25%; A: marketing digital y demos; R: rentabilidad y posicionamiento; T: 6 meses. [[S02_Sesion1_Planeacion_Estrategica_y_BCM]]

> [!question]- 7. ¿Qué herramientas analizan el entorno y qué componentes tiene el FODA?
> FODA, PESTEL y 5 fuerzas de Porter. FODA: Fortalezas y Debilidades (internas), Oportunidades y Amenazas (externas). [[S02_Sesion1_Planeacion_Estrategica_y_BCM]]

> [!question]- 8. ¿Qué función cumple cada nivel (estratégico, táctico, operativo) en la continuidad?
> Estratégico: orienta y decide (prioridades, presupuesto, política). Táctico: analiza (BIA, riesgos), articula, coordina y prepara. Operativo: ejecuta y responde. [[S02_Sesion2_Integracion_PE_y_BCM_Niveles]]

> [!question]- 9. En el caso MediCloud, ¿por qué TI hace el failover sin pedir autorización y cuándo se escala al Comité?
> La autoridad de TI para failover está definida previamente en el procedimiento. Se escala al Comité cuando la afectación es masiva (28 de 35 clínicas), hay riesgo de superar los objetivos de recuperación, hay implicancias contractuales/de comunicación y el gasto extraordinario excede la autoridad del Coordinador BCM. [[S03_Sesion1_Estructura_Organizacional_Roles]]

> [!question]- 10. Si se activa la infraestructura alterna, ¿terminó la recuperación?
> No. Falta verificar disponibilidad, integridad y consistencia de datos, procesar operaciones pendientes, estabilizar, volver a la operación normal y documentar lecciones/mejoras. [[S03_Sesion2_Procedimientos_Respuesta_Recuperacion]]

> [!question]- 11. ¿Qué es el BIA y cuáles son sus 5 objetivos?
> Proceso que identifica procesos/funciones y evalúa las consecuencias de su interrupción. Objetivos: identificar procesos y prioridad; evaluar impactos; establecer prioridades y tiempos (RTO, MTD); identificar recursos; fundamentar planes de continuidad en datos. [[S04_Sesion1_BIA_Impactos_y_Requerimientos]]

> [!question]- 12. Liste las 5 categorías de impacto del BIA.
> Financiero, operacional, legal/regulatorio, reputacional, salud y seguridad. [[S04_Sesion1_BIA_Impactos_y_Requerimientos]]

> [!question]- 13. Defina RTO, RPO, WRT y MTPD.
> RTO: tiempo objetivo para recuperar el proceso. RPO: pérdida tolerable de datos expresada en tiempo. WRT: tiempo adicional para completar y estabilizar la operación. MTPD: límite máximo tolerable de interrupción. [[S04_Sesion1_BIA_Impactos_y_Requerimientos]]

> [!question]- 14. Calcule la criticidad: Operacional Crítico, Financiero Alto, Legal Medio, Reputacional Alto, Salud Bajo.
> 4+3+2+3+1 = 13 → con 5 categorías (11–13) es **Alto** por puntaje acumulado; por el criterio más severo sería **Crítico**. [[S04_Sesion2_BIA_Criticidad_y_Fases]]

> [!question]- 15. Nombre las 7 fases del BIA.
> Planificación y preparación; identificación de procesos; evaluación de impacto y procesos críticos; métricas de recuperación; identificación de recursos; validación y aprobación; documentación y comunicación. [[S04_Sesion2_BIA_Criticidad_y_Fases]]

> [!question]- 16. ¿Quién define los intervalos de tiempo de la matriz detallada y en qué se basa?
> El negocio, no la metodología. Se basa en la naturaleza del negocio, el tipo de procesos, la experiencia histórica y entrevistas con dueños de procesos (0–4 h, 4–24 h, 1–3 días son solo referencia). [[S04_Sesion2_BIA_Criticidad_y_Fases]]

> [!question]- 17. Diferencie conocimiento explícito, tácito y potestad en los recursos humanos del BIA.
> Explícito: está en manuales y procedimientos. Tácito: experiencia o saber hacer no escrito. Potestad: facultad legal/administrativa (certificaciones, firmas) para ejecutar o autorizar. Un backup puede saber hacer la tarea y no tener potestad. [[S05_Sesion1_BIA_Recursos_Necesarios_y_Aprobacion]]

> [!question]- 18. ¿Qué es un SPOF humano y qué estrategias lo reducen?
> Dependencia crítica de una sola persona. Estrategias: job shadowing, documentación de pasos críticos (decisiones y excepciones), rotación de puestos, capacitar backups. [[S05_Sesion1_BIA_Recursos_Necesarios_y_Aprobacion]]

> [!question]- 19. Mencione los 8 tipos de recursos que se identifican para un proceso crítico.
> Humanos, tecnológicos, infraestructura física, información y datos, financieros, equipos y herramientas, servicios de terceros, documentación. [[S05_Sesion1_BIA_Recursos_Necesarios_y_Aprobacion]]

> [!question]- 20. Diferencie amenaza, vulnerabilidad, activo crítico, riesgo e incidente disruptivo.
> Amenaza: evento potencial que puede causar daño. Vulnerabilidad: debilidad que la amenaza aprovecha. Activo crítico: recurso esencial. Riesgo: posibilidad de que una amenaza afecte un activo por una vulnerabilidad. Incidente: evento ya materializado que interrumpe. [[S06_Sesion1_Amenazas_y_Analisis_de_Riesgo]]

> [!question]- 21. ¿En qué se diferencian el BIA y el análisis de riesgo?
> BIA: centrado en procesos y tiempos; mide el impacto de la interrupción y produce MTPD, RTO, RPO, WRT. Análisis de riesgo: centrado en amenazas, vulnerabilidades y activos; estima probabilidad × impacto y produce el mapa de riesgos. [[S06_Sesion1_Amenazas_y_Analisis_de_Riesgo]]

> [!question]- 22. Calcule el VME: probabilidad 25% y pérdida $40 000; un servidor redundante cuesta $8 000.
> VME = 0,25 × 40 000 = $10 000. Como el control cuesta $8 000 (< $10 000), conviene implementarlo. [[S06_Sesion2_Gestion_de_Riesgos]]

> [!question]- 23. Nombre las cuatro opciones de tratamiento del riesgo con un ejemplo cada una.
> Evitar (dejar de operar el data center en zona inundable); mitigar (UPS, MFA, redundancia); transferir (seguro o backup en la nube con SLA); aceptar (pasiva sin acciones o activa con plan de contingencia). [[S06_Sesion2_Gestion_de_Riesgos]]

> [!question]- 24. ¿Transferir un riesgo lo elimina? ¿Y qué diferencia hay entre aceptación activa y pasiva?
> No: traslada o comparte determinadas consecuencias con un tercero, pero el riesgo y parte de la responsabilidad permanecen. Activa: se acepta y se prepara un plan de contingencia; pasiva: se acepta solo con seguimiento. [[S06_Sesion2_Gestion_de_Riesgos]]

> [!question]- 25. ¿Qué criterios se usan para seleccionar una estrategia de recuperación?
> Cumplimiento de RTO/RPO, recursos y capacidades requeridos, viabilidad técnica y operativa, y relación costo-beneficio. La opción más barata o más rápida no es necesariamente la elegida. [[S07_Sesion2_Seleccion_y_Justificacion_de_Estrategias]]

> [!question]- 26. ¿Cuándo un incidente disruptivo se convierte en crisis y quién asume la dirección?
> Cuando por gravedad, alcance, incertidumbre y necesidad de decisiones estratégicas excede la capacidad de respuesta operativa. Lo dirige el Comité de Gestión de Crisis. [[S08_Sesion1_Gestion_de_Crisis]]

> [!question]- 27. Nombre las 5 etapas de la gestión de crisis y los miembros del CGC.
> Prevención/preparación; detección y alerta; contención y respuesta inmediata; recuperación; evaluación post-crisis y aprendizaje. CGC: CEO (presidente), CFO, CISO, Director de Operaciones, Director de RR.HH., Coordinador BCM; soporte: Comunicaciones/RR.PP., Legal y Cumplimiento, Auditoría. [[S08_Sesion1_Gestion_de_Crisis]]

> [!question]- 28. ¿Qué diferencia hay entre BCP y DRP y entre hot, warm y cold site?
> BCP: mantiene o recupera actividades prioritarias del negocio. DRP: recupera los recursos y servicios tecnológicos que las soportan. Hot: equipado, recuperación muy rápida, costo alto. Warm: infraestructura disponible, requiere configuración, intermedio. Cold: básico, más lento, bajo costo. [[S09_Sesion1_DRP_Fundamentos_y_Elementos]]

> [!question]- 29. Enumere los elementos clave del DRP y los tipos de prueba.
> Objetivo, alcance, BIA, estrategias, roles y responsabilidades, procedimientos, plan de comunicaciones, plan de pruebas, mantenimiento y actualización. Pruebas: tabletop, técnica, simulación parcial, simulación completa. [[S09_Sesion1_DRP_Fundamentos_y_Elementos]]

> [!question]- 30. Fintech Express: RTO 1 h y RPO 15 min; RTA 7 h y pérdida de 4 h. ¿Se cumplieron? ¿Qué fallas de gobierno hubo? Distinga KPI de cumplimiento y efectividad.
> No: RTO excedido en 6 h; RPO excedido en 3 h 45 min. Fallas: la alta dirección no exigió evaluar el cambio (AWS) sobre el DRP, no hubo gestión del cambio (DRP y contactos desactualizados) y roles sin capacitar (reemplazo sin formación ni accesos). KPI de cumplimiento: verifican que se hagan las actividades planificadas (ej. 2/4 simulacros = 50%). KPI de efectividad: verifican si la recuperación logra RTO/RPO. Se puede cumplir todo lo programado y aun así no alcanzar los objetivos. [[S09_Sesion2_Gobierno_del_Plan_DRP_y_KPIs]]
