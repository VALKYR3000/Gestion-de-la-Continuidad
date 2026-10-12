---
tags: [ejercicios, continuidad-del-negocio, semana5, BIA]
fuente: SEM 5 (actividades de clase resueltas + ejercicios propuestos; práctica calificada PC1 es en esta semana)
---
# Ejercicios · Semana 5 (recursos del BIA, polifuncionalidad, validación) — PC1 se rinde en la semana 5
Teoría: [[S05_Sesion1_BIA_Recursos_Necesarios_y_Aprobacion]] · Revisa también [[EJ_S04_BIA]] (cálculos de criticidad, MTPD/RTO/WRT/RPO), que suelen entrar en la PC1.

# A. Actividades de clase (resueltas)

## A1. Facturación crítica sin poder reanudarse
Tiene sitio alterno, computadoras e Internet. **Otros recursos que pueden impedir la recuperación:** (1) **humanos**: el titular no está y el backup no tiene el conocimiento tácito; (2) **potestad**: firma digital/certificado, token bancario o permiso para emitir comprobantes; (3) **datos**: no hay copia actualizada de clientes y facturación (RPO); (4) **terceros**: proveedor de facturación electrónica/SUNAT/pasarela fuera de servicio; (5) **documentación**: no existe el procedimiento ni los contactos; (6) **herramientas**: tokens, licencias; (7) **financieros**: no hay presupuesto de emergencia.

## A2. "Importancia de la Matriz de Polifuncionalidad" (pregunta de cierre)
Sirve para: identificar **SPOF** (puntos únicos de fallo), gestionar la **redundancia humana** (backups), planificar la **transferencia de conocimiento** y facilitar la **toma de decisiones en crisis** (saber quién puede hacer qué cuando el titular falta). Revela brechas de conocimiento tácito, de potestad, concentración de riesgo y dependencias tecnológicas.

## A3. Matriz de polifuncionalidad (proceso: mantener disponibilidad del servicio en la nube) — lectura
| Tarea crítica | Observación de continuidad | Tipo de brecha | Acción |
|---|---|---|---|
| Reacción ante ciberataques | Backup 1 conoce la red, backup 2 no tiene conocimiento tácito para ataques nuevos | **Conocimiento tácito** | Simulacro *tabletop*, formación del backup 2 |
| Restauración de BD | Solo el DBA tiene la clave maestra física; el backup 1 sabe pero no tiene la "llave" | **Potestad** | Delegar/custodiar clave de forma segura (doble custodia), autorizar al backup |
| Atención de incidencias nivel 3 | Jefe de Seguridad es backup en esta tarea crítica y titular en otra → **concentración de riesgo** | Sobrecarga | Asignar otro backup |
| Despliegue de parches de emergencia | Requiere VPN de administración que solo titular y backup 1 tienen activa | **Dependencia tecnológica** | Habilitar accesos al backup 2 |

## A4. Casos de potestad
- **CISSP:** el programador (backup) sabe restaurar la BD pero la política exige CISSP para cambios en producción → sin él no puede intervenir. **Acción del BIA:** financiar de inmediato la certificación del backup.
- **Pagos:** el Analista de Tesorería (conocimiento) puede preparar el lote pero sin Firma A del Gerente de Finanzas los fondos quedan congelados. **Solución:** política de **delegación de autoridad financiera en cascada** (tokens y facultades pre-configurados en el banco para el Contralor/Subgerente).

# B. Ejercicios propuestos (con solución)

**B1. Clasifica el recurso** (humano, tecnológico, infraestructura, información/datos, financiero, equipos, terceros, documentación): (a) BCP impreso; (b) centro de datos alterno; (c) pasarela de pagos; (d) backups cada hora; (e) token bancario; (f) presupuesto de emergencia; (g) DBA suplente; (h) laptop; (i) VPN; (j) oficina alterna.
*Solución:* (a) documentación; (b) tecnológico (infraestructura de contingencia; también físico); (c) servicios de terceros; (d) información y datos; (e) equipos y herramientas; (f) financiero; (g) humano; (h) equipos y herramientas; (i) tecnológico (redes seguras); (j) infraestructura física.

**B2. Conocimiento explícito, tácito o potestad.** (1) El manual dice reiniciar el servicio X. (2) El técnico sabe que ese error aparece solo a fin de mes y cómo evitarlo. (3) Solo quien tiene firma B puede autorizar transferencias de alta cuantía. (4) Solo un auditor certificado puede validar el cierre.
*Solución:* (1) explícito; (2) tácito; (3) potestad (firmas/autorizaciones); (4) potestad (certificación técnica).

**B3. Construye una matriz de polifuncionalidad** para el proceso "Cierre contable mensual": titular Contador Senior; backups: Analista (apto), Asistente (en formación). Hallazgo: solo el Contador tiene el certificado digital. Identifica brechas y estrategias.
*Solución:* Brecha de **potestad** (certificado digital único) y **SPOF** de conocimiento tácito. Estrategias: delegar/obtener certificado para el backup (política de delegación), job shadowing durante el cierre, documentar excepciones (p. ej., qué hacer si falla la conciliación), rotación (el analista ejecuta con el contador observando).

**B4. Job shadowing, documentación de pasos críticos y rotación** — di cuál es cuál: (1) el backup observa al titular un cierre completo y pregunta; (2) el experto escribe qué hacer ante el Error 404 a fin de mes; (3) el backup ejecuta el proceso crítico mientras el titular observa.
*Solución:* (1) job shadowing; (2) documentación de pasos críticos (solo decisiones/excepciones, no manual de uso); (3) rotación de puestos (la más agresiva y efectiva, convierte el conocimiento tácito en experiencia práctica).

**B5. Recursos del proceso "Gestión de pedidos online".** Lista un recurso de cada uno de los 8 tipos.
*Solución modelo:* humano: soporte técnico y suplente; tecnológico: plataforma web, BD, servidor cloud alterno, VPN; infraestructura física: oficina alterna/teletrabajo seguro; información: backup de órdenes, inventario y clientes (RPO); financieros: presupuesto de emergencia, pago a proveedor alterno; equipos: laptops, tokens, teléfonos; terceros: pasarela de pagos, courier alterno, ISP (con SLA); documentación: BCP/DRP, checklists, contactos.

**B6. Validación y aprobación.** ¿Quiénes aprueban los resultados del BIA y qué se aprueba? ¿Qué se hace luego?
*Solución:* Aprueban: gerencia de alto nivel; responsables de operaciones y departamentos críticos (TI, producción…); equipos de continuidad/gestión de riesgos. Se aprueba: procesos críticos, evaluación de impactos (financiero, operacional, reputacional, legal), RTO/RPO y dependencias de recursos. Luego: **documentar** (informe detallado) y **comunicar** a los stakeholders las prioridades de recuperación y planes.

**B7. SLA.** ¿Por qué debe haber SLA con terceros críticos?
*Solución:* porque muchas empresas no son autosuficientes; si el tercero falla se requiere un plan alterno o un acuerdo de nivel de servicio robusto que defina disponibilidad, tiempos de respuesta/recuperación y consecuencias por incumplimiento.

**B8. Verdadero/Falso.** (1) Se identifican todos los empleados como recursos humanos. (2) Los recursos de respaldo (backups, servidores alternos) también se identifican. (3) El RPO se relaciona con los recursos de información. (4) La documentación debe estar solo en la nube. (5) El BIA se archiva sin comunicar.
*Solución:* (1) F (roles indispensables/capacidades críticas); (2) V; (3) V; (4) F (impresa o accesible); (5) F (se comunica).

**B9. Caso integrador.** Una clínica tiene como proceso crítico "Admisión de pacientes" (RTO 1 h). Tras un ciberataque, el sitio alterno y los servidores están listos, pero el único administrador que tiene las credenciales del sistema está de viaje y el procedimiento de restauración no está documentado. ¿Qué recursos/brechas hay y qué haría el BIA?
*Solución:* Brechas: **potestad/credenciales** (SPOF humano), **documentación** inexistente, quizá **conocimiento tácito**. Acciones: delegar credenciales con custodia segura, backup capacitado, documentar procedimiento y puntos de decisión, job shadowing y simulacro; incorporar los hallazgos en el BIA, validar con la dirección y comunicarlos.
