---
tags: [clase, continuidad-del-negocio, semana5, BIA]
fuente: SEM 5/SESION 1 (PDF S05_s9)
---
# S05-1 · BIA: identificación de recursos mínimos, validación y documentación
Ejercicios: [[EJ_S05_Recursos_BIA]]

**Gancho de la clase:** Facturación es proceso crítico; tras la interrupción hay sitio alterno, computadoras e Internet, pero Facturación no puede reanudarse. ¿Qué otros recursos faltan? → personal con conocimiento (tácito) y **potestad** (firmas/certificaciones/credenciales), datos actualizados (RPO), servicios de terceros (pasarela, SUNAT/proveedor de comprobantes), documentación/procedimientos, tokens/accesos, presupuesto.

## Resumen
Para cada proceso crítico se identifican los recursos indispensables para recuperarlo y mantenerlo operativo (no basta tener sitio alterno, PCs e Internet: puede faltar personal con conocimiento/potestad, datos, terceros, etc.). Luego se validan, aprueban, documentan y comunican los resultados del BIA (fases 5, 6 y 7).

## Conceptos clave
- **8 tipos de recursos**: 1 humanos · 2 tecnológicos · 3 infraestructura física · 4 información y datos · 5 financieros · 6 equipos y herramientas · 7 servicios de terceros · 8 documentación.
- **Recursos humanos** (no toda la planilla: roles indispensables). 3 pilares:
  1. **Estructura de roles** (comité de crisis, personal operativo crítico, sustitutos/backups).
  2. **Mapa de competencias (polifuncionalidad)**: dimensión del **conocimiento** (explícito = manuales/procedimientos; **tácito** = saber hacer/experiencia no escrita) y dimensión de la **potestad** (facultad legal/administrativa: certificaciones, firmas y autorizaciones).
  3. **Riesgo de persona única** (SPOF: Single Point of Failure).
- **Matriz de polifuncionalidad**: herramienta visual de quién puede ejecutar tareas críticas y con qué dominio. Sirve para: identificar SPOF, gestionar redundancia humana, planificar transferencia de conocimiento, facilitar decisiones en crisis.
- **RPO** se relaciona con los recursos de información: debe haber copia actualizada de transacciones, datos de clientes y configuraciones.
- **SLA**: acuerdo de nivel de servicio con terceros (si fallan, se requiere plan alterno).
- **DRaaS**: Disaster Recovery as a Service.

## Desarrollo
- **Conocimiento explícito vs tácito** (ransomware): el plan (explícito) dice revisar logs, apagar y desconectar del switch, informar al Coordinador BCM; el experto (tácito) reconoce el patrón (ventiladores al máximo, íconos que cambian), usa el atajo (desconectar el cable principal del servidor central) y cuida lo crítico (ejecutar un comando antes de desconectar la BD para no corromper respaldos). El backup que solo lee el plan puede tardar 15 min.
- **Potestad**: ej. CISSP exigido para validar cambios en producción → si el titular falta, el programador no puede intervenir (viola normas, cancela seguros). Acción del BIA: financiar la certificación del backup. Ej. pagos: sin Firma A del Gerente de Finanzas y sin flujos alternos registrados en el banco, los fondos quedan congelados → política de **delegación de autoridad financiera en cascada**.
- **Estrategias contra el riesgo de persona única**: *Job shadowing* (acompañamiento), documentación de pasos críticos (puntos de decisión/excepciones, p. ej. qué hacer ante Error 404 a fin de mes), *rotación de puestos* (la más agresiva y efectiva; el backup ejecuta y el titular observa).
- **Recursos tecnológicos**: sistemas principales (ERP/SAP, CRM), bases de datos en producción y sus respaldos, servidores (físicos, VM, nube, hot standby), respaldos/infraestructura alterna (backups, centro de datos alterno, DRaaS), redes seguras (internet, VPN, firewalls/IDS). Incluir también los recursos de **contingencia**.
- **Infraestructura física**: oficinas, centro de datos, almacenes; alternos: oficina alterna, centro de datos secundario, acceso remoto seguro.
- **Equipos y herramientas**: laptops, módems, impresoras, tokens, teléfonos corporativos/líneas de emergencia.
- **Terceros**: pasarela de pagos, ISP, correo/almacenamiento en la nube. **Documentación**: guías, manuales, checklists, BCP, DRP (impresos o accesibles). **Financieros**: presupuesto de emergencia, proveedores alternativos, DRaaS, equipos temporales, logística, seguros.
- Importancia de identificar recursos: priorizar su restauración, planificar contingencias, asignar responsabilidades.
- **Fase 6 – Validación y aprobación**: asegurar que los procesos críticos y sus impactos (financiero, operacional, reputacional, legal), RTO/RPO y dependencias están correctos; aprueban: gerencia de alto nivel, responsables de operaciones/departamentos críticos (TI, producción), equipos de continuidad/gestión de riesgos.
- **Fase 7 – Documentación y comunicación**: informe detallado del BIA (procesos críticos, impacto, RTO/RPO, recursos) y comunicar a stakeholders las prioridades y planes.
- Ejemplo de matriz de polifuncionalidad (servicio en la nube): reacción ante ciberataques (riesgo tácito del backup 2), restauración de BD (brecha de potestad: solo el DBA tiene la clave maestra), atención de incidencias (concentración de riesgo), despliegue de parches (dependencia tecnológica: VPN solo del titular y backup 1).

## Ojo en el examen
- Diferenciar **conocimiento explícito/tácito** y **potestad**; saber dar ejemplo de cada uno.
- SPOF = dependencia de una sola persona; soluciones: job shadowing, documentación, rotación.
- Los recursos incluyen los de **respaldo/contingencia**, no solo los de operación diaria.
- Quién aprueba el BIA (alta gerencia + responsables de áreas críticas + equipo de continuidad).
- ⚠️ SEM 5 sesión 2 solo tiene video (sin PDF) y no se transcribió: este tema queda sin cubrir.
