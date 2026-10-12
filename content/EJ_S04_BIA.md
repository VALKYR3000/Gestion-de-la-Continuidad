---
tags: [ejercicios, continuidad-del-negocio, semana4, BIA]
fuente: SEM 4 (caso Control Migratorio y Soluciones SAC resueltos + ejercicios propuestos con cálculos)
---
# Ejercicios · Semana 4 (BIA: impactos, criticidad, MTPD/RTO/WRT/RPO)
Teoría: [[S04_Sesion1_BIA_Impactos_y_Requerimientos]] · [[S04_Sesion2_BIA_Criticidad_y_Fases]]
**Fórmulas a memorizar:** criticidad total = Σ valores (Bajo 1, Medio 2, Alto 3, Crítico 4) · escalas: 3 cat. (3–4 B, 5–6 M, 7–9 A, 10–12 C) · 4 cat. (4–6 B, 7–9 M, 10–12 A, 13–16 C) · 5 cat. (5–7 B, 8–10 M, 11–13 A, 14–20 C) · **RTO + WRT ≤ MTPD** · **MTPD ≥ RTO + WRT ≥ RPO** · MTPD = antes del primer intervalo con **Crítico** · RTO = antes del primer intervalo con **Alto**.

# A. Casos del curso (resueltos)

## A1. Caída del Sistema de Control Migratorio (S4-S7)
**Enunciado:** 07:00 a. m., Aeropuerto Jorge Chávez, hora pico. El sistema informático de Migraciones (software del Estado, no de LAP) cae a nivel nacional: no se pueden escanear pasaportes, verificar antecedentes ni validar alertas; las E-Gates inoperativas. Nadie ingresa a salas de embarque; en <30 min la cola va del 2.º piso a la puerta principal; aviones en pista listos, pasajeros atrapados. LAP debe mantener seguras y fluidas las instalaciones.

**1. Identificación y análisis de impactos (≥3 procesos)**
| Proceso/actividad afectada | Consecuencia de la interrupción | Categoría(s) | Justificación |
|---|---|---|---|
| Control migratorio de salidas / acceso a salas de embarque | Pasajeros no pueden pasar a embarque; colas que llegan a la puerta principal; vuelos retrasados/cancelados | Operacional, Financiero, Reputacional | Detiene el flujo principal del aeropuerto; las aerolíneas no despachan; retrasos generan costos y penalidades; quejas y mala imagen |
| Operación de aerolíneas (check-in, embarque, salida de aviones) | Aviones en pista no pueden salir; reprogramaciones, compensaciones | Operacional, Financiero, Legal/Regulatorio (derechos del pasajero, contratos con aerolíneas) | Afecta contratos y obligaciones con aerolíneas y pasajeros |
| Seguridad y fluidez dentro de instalaciones (gestión de multitudes) | Aglomeración, desorden, estrés, riesgo de incidentes, necesidades básicas | Salud y Seguridad, Operacional, Reputacional | Riesgo físico (aglomeración, personas vulnerables, calor, desmayos) en un área que LAP debe mantener segura |
| Servicios comerciales (tiendas, restaurantes, estacionamiento) | Baja de ventas y de ingresos por concesiones | Financiero | Los pasajeros no llegan a la zona comercial |
| Atención al pasajero / comunicación | Reclamos, desinformación | Reputacional, Legal | LAP es el rostro visible aunque el software no sea suyo |

**2. Priorización**
Mayor prioridad: **el control migratorio / acceso a salas de embarque (flujo de pasajeros)**, y en lo que compete a LAP: la **seguridad y gestión de multitudes** (salud y seguridad es la categoría de mayor severidad potencial: riesgo para personas). Justificación: sin este proceso se detiene la operación principal, cada minuto agrava colas, retrasos de vuelos, costos y riesgo físico; los demás impactos (comerciales, atención) se derivan de este. Como el software es del Estado, LAP prioriza lo que controla: contingencia de flujo (puntos de contacto, información, habilitar procedimientos manuales con Migraciones) y seguridad de la multitud.

**3. Impacto a través del tiempo**
No. **30 min**: colas, molestia, retrasos en salidas, riesgo bajo/moderado. **4 horas**: múltiples vuelos retrasados/cancelados, costos y penalidades con aerolíneas, congestión grave, riesgo a la salud (calor, estrés, personas vulnerables), reclamos y viralización en redes. **12 horas**: cancelaciones masivas, pérdida de conexiones, compensaciones legales a pasajeros, daño reputacional severo, riesgo de seguridad y orden público, impacto económico muy alto. La criticidad **crece** al prolongarse la interrupción (de Medio/Alto a Crítico), por lo que se justifican RTO y MTPD cortos para este proceso.

## A2. Soluciones SAC (matrices de criticidad)
Resuelto de principio a fin (matriz general de 6 procesos, priorización y matrices detalladas de Plataforma Web y Pasarela de Pagos) en [[S04_Sesion2_BIA_Criticidad_y_Fases]].
Resumen: Pasarela 14 (Crítico, prioridad 1) · Plataforma Web 12 (Alto, prioridad 2) · Logística 11 · Facturación 11 · Inventarios 10 · Atención al Cliente 9 (Medio).

## A3. Ejemplo guiado: Gestión de pedidos
Matriz (4 categorías) en [[S04_Sesion2_BIA_Criticidad_y_Fases]]; resultado: **RTO < 4 h** (Alto aparece en 4–24 h) y **MTPD ≤ 24 h** (Crítico aparece en 1–3 días); con WRT = 1 h se cumple RTO + WRT ≤ MTPD.

# B. Ejercicios propuestos (con solución)

**B1. Criticidad por puntaje (5 categorías).** Proceso "Atención de emergencias": Operacional Crítico, Financiero Medio, Legal Alto, Reputacional Alto, Salud y Seguridad Crítico. Calcula criticidad total y nivel por ambos métodos.
*Solución:* 4+2+3+3+4 = **16** → 5 categorías: 14–20 = **Crítico**. Criterio más severo: Crítico. Coinciden.

**B2. Criticidad por puntaje (4 categorías).** Proceso "Reportes internos": Operacional Bajo, Financiero Bajo, Legal Bajo, Reputacional Medio.
*Solución:* 1+1+1+2 = **5** → 4 categorías: 4–6 = **Bajo**. Criterio más severo: Medio. **Difieren** (Medio vs Bajo): se explica porque el puntaje acumulado suaviza un único valor medio.

**B3. Escala.** ¿Qué nivel es una criticidad total de 9 con (a) 3 categorías, (b) 4 categorías, (c) 5 categorías?
*Solución:* (a) 7–9 = Alto; (b) 7–9 = Medio; (c) 8–10 = Medio.

**B4. Matriz detallada.** Proceso "Facturación electrónica" (4 categorías):
| | 0–4 h | 4–24 h | 1–3 d | >3 d |
|---|---|---|---|---|
| Operacional | Medio | Alto | Crítico | Crítico |
| Financiero | Bajo | Medio | Alto | Crítico |
| Legal | Bajo | Medio | Alto | Crítico |
| Reputacional | Bajo | Bajo | Medio | Alto |
Calcula la criticidad total e identifica MTPD y RTO si Crítico = inaceptable y Alto = significativo.
*Solución:* 0–4 h: 2+1+1+1 = **5 (Bajo)**; 4–24 h: 3+2+2+1 = **8 (Medio)**; 1–3 d: 4+3+3+2 = **12 (Alto)**; >3 d: 4+4+4+3 = **15 (Crítico)**. Primer **Crítico** (operacional) aparece en 1–3 días → **MTPD ≤ 24 h**. Primer **Alto** (operacional) aparece en 4–24 h → **RTO < 4 h**.

**B5. Derivar MTPD y RTO.** Matriz: Operacional Alto (0–4), Crítico (4–24), Crítico, Crítico; Financiero Medio, Alto, Crítico, Crítico. Alto se alcanza en 0–4 h aproximadamente a 1 h; Crítico aprox. a las 3 h.
*Solución:* como Alto y Crítico caen en 0–4 h se profundiza el intervalo: **RTO < 1 h** y **MTPD = 3 h**. Verifica RTO + WRT ≤ MTPD → WRT ≤ 2 h.

**B6. WRT.** RTO = 3 h. Tras recuperar quedan: reprocesar cola de 45 min, conciliar 25 min, validación y ajustes 20 min. MTPD = 6 h. ¿WRT? ¿Se cumple la relación?
*Solución:* WRT = 45+25+20 = **90 min = 1,5 h**. RTO + WRT = 4,5 h ≤ 6 h → **sí cumple** (margen 1,5 h).

**B7. Relaciones.** MTPD = 8 h, RTO = 6 h, WRT = 3 h. ¿Es consistente?
*Solución:* No: 6 + 3 = 9 h > 8 h. Hay que reducir el RTO (≤ 5 h con WRT 3 h), reducir el WRT o revisar el MTPD con el negocio.

**B8. RPO.** Una tienda registra pedidos cada minuto; perder más de 5 minutos de pedidos genera reprocesos y pérdida de ventas inaceptable. ¿RPO? ¿Basta con backups diarios?
*Solución:* **RPO = 5 min** (pérdida tolerable). No: el RPO depende de la información máxima tolerable, no de la frecuencia de backups; para cumplirlo hay que **replicar/respaldar cada ≤5 min** (replicación continua o logs de transacciones).

**B9. Distingue RTO, RPO, WRT y MTPD** (qué responde cada una).
*Solución:* RTO: ¿en cuánto tiempo recuperamos? RPO: ¿cuántos datos podemos perder (en tiempo)? WRT: ¿cuánto tiempo adicional para estabilizar tras el RTO? MTPD: ¿hasta cuándo se tolera la interrupción?

**B10. Impactos del caso hospital.** Apagón de 24 h en un hospital: clasifica impactos de UCI, quirófano, laboratorio y cafetería con nivel y categoría.
*Solución modelo:* UCI/soporte vital: Salud y Seguridad **Crítico** (riesgo inminente de muerte), Reputacional/Legal Alto-Crítico. Quirófano: Salud **Crítico**, Operacional Crítico. Laboratorio: Operacional Alto (retrasa diagnósticos), Salud Alto. Cafetería: Bajo en todas. Prioridad de recuperación: UCI > quirófano > laboratorio > cafetería.

**B11. Orden de prioridades.** Procesos con criticidad total (4 cat.): Nómina 8, Ventas online 15, Soporte interno 6, Facturación 11. Ordena y clasifica.
*Solución:* Ventas online 15 (**Crítico**, prioridad 1) > Facturación 11 (**Alto**) > Nómina 8 (**Medio**) > Soporte interno 6 (**Bajo**).

**B12. Verdadero/Falso.** (1) El MTPD se calcula como un % del RTO. (2) El RTO obliga a volver a la infraestructura original. (3) Los intervalos 0–4/4–24/1–3/>3 son obligatorios. (4) La matriz general sirve para filtrar procesos. (5) El WRT se cuenta antes del RTO.
*Solución:* (1) F (el RTO se establece por la evolución de impactos y no es % del MTPD). (2) F. (3) F (los define el negocio). (4) V. (5) F (después del RTO).
