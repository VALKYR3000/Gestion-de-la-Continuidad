---
tags: [clase, continuidad-del-negocio, semana1]
fuente: SEM 1/SESION 1 (PDF S01_s1 completo, texto + diapositivas gráficas)
---
# S01-1 · Introducción a la contextualización en Continuidad del Negocio (DRII – BCI)
Ejercicios: [[EJ_S01_Fundamentos_y_Marcos]]

## Presentación del curso
- **Contenido de la sesión**: presentación del docente, fundamentación, desarrollo del curso, evaluación y pautas de trabajo.
- **Fundamentación**: los estudiantes aprenden el proceso de implementación de un **sistema de gestión de la continuidad del negocio**, con visión integral de la aplicación de las mejores prácticas; se revisan estándares internacionales con buenas prácticas para elaborar **estrategias de recuperación ante desastres**, y a usar una guía de buenas prácticas para diseñar planes y realizar pruebas de recuperación del negocio.
- **Logro general del curso**: al finalizar, el estudiante **propone estrategias para la continuidad del negocio mediante el uso de herramientas de diagnóstico y modelos de madurez**.
- **Desarrollo del curso**: Unidad 1 Continuidad del Negocio · Unidad 2 Estrategias de recuperación y gestión de crisis · Unidad 3 Gestión de la continuidad.
- **Evaluación**: Promedio Final = 20% PC1 + 20% PC2 + 30% PC3 + 30% EXFI.
  | Tipo | Descripción | Semana | Obs. |
  |---|---|---|---|
  | PC1 | Práctica calificada 1 | 5 | Individual |
  | PC2 | Práctica calificada 2 | 10 | Individual |
  | PC3 | Práctica calificada 3 | 15 | Individual |
  | EXFI | Examen final individual | 18 | Individual |
- **Pautas**: clase presencial según sílabo (UTP+ class tiene material y adicionales); participación activa; foros y actividades; celular en silencio; consultas levantando la mano. **Exámenes/PC: tolerancia de 15 minutos para ingresar; iniciado el examen nadie puede retirarse en los primeros 15 minutos.**

## Logro de la sesión
Comprender los conceptos básicos de Continuidad del Negocio según los enfoques del **DRII** (Instituto Internacional de Recuperación ante Desastres) y el **BCI** (Instituto de Continuidad del Negocio).
- **Importancia**: comprender la contextualización de BC basada en DRII–BCI es crucial para que las organizaciones adopten estándares internacionales que fortalezcan su resiliencia y capacidad de recuperación ante crisis.
- **Contenido**: introducción a la continuidad del negocio · DRII y BCI · BC desde una perspectiva histórica.

## 1. ¿Qué es la continuidad del negocio?
- Capacidad de una organización para **mantener sus operaciones esenciales durante y después de un incidente disruptivo**.
- Es el resultado de una **planificación y preparación adecuadas**.
- Es un **enfoque estratégico y operativo** que permite minimizar interrupciones y garantizar la **resiliencia organizacional**.
- **Enfoque estratégico**: la continuidad se **planifica a nivel directivo** y forma parte de la visión a largo plazo.
- **Enfoque operativo**: se concreta en **procedimientos, herramientas y acciones diarias** para responder a incidentes y recuperarse rápidamente.
- Actividad "Analicemos": (1) universidad pierde internet 2 h, ¿cuál es la operación esencial a mantener? (p. ej. matrícula/clases virtuales, plataforma académica, evaluaciones y comunicación con estudiantes); (2) sin planificación previa, ¿hay continuidad aunque se sobreviva? → **No**: sobrevivir sin planificación es suerte/improvisación; la BC es resultado de planificación y preparación; (3) ¿por qué la resiliencia es estratégica y no solo de sistemas? → porque implica decisiones de la alta dirección, toda la organización, visión de largo plazo y objetivos del negocio, no solo TI.

## 2. Incidentes disruptivos
- **Definición**: cualquier evento **inesperado** que **interrumpe significativamente** las operaciones normales de una organización.
- Para evaluar la continuidad hay que considerar el **contexto organizacional**: analizar incidentes **externos e internos** que afecten los objetivos estratégicos.
- **Externos** (eventos externos que pueden afectar la operación): **climáticos** (inundaciones, terremotos) · **sociales** (atentados, COVID-19/pandemias) · **tecnológicos** (fallas de hardware, ciberataques) · **económicos** (crisis económicas) · otros.
- **Internos** (afectan la continuidad operativa): **accidentes, incendios, explosiones, apagones, derrames** · **robos, huelgas, sabotajes, rotación, falta de competencia del personal** · **falta de material, agua, energéticos, falta de refacciones y servicios**.

## 3. Medidas de continuidad: preventivas y reactivas
- **Preventivas (antes del evento)**: acciones que se implementan para **evitar** que ocurra un incidente disruptivo. Ej.: firewall y antivirus (ciberataque); auditorías financieras (fraudes internos); proveedores alternativos (problemas de abastecimiento).
- **Reactivas (después del evento)**: acciones que se activan **después** de que ocurre un incidente para **minimizar el daño y restaurar la operación**. Ej.: ciberataque → restaurar datos desde respaldo; apagón → activar planta eléctrica de emergencia; fraude financiero → investigación interna.
- **Incidentes internos** (originados dentro de la organización: fraudes, errores humanos, problemas de infraestructura):
  | Preventiva (antes) | Reactiva (después) |
  |---|---|
  | Auditorías financieras: inspecciones periódicas para detectar irregularidades antes de que se conviertan en un problema grave | Activación del plan de recuperación: si ocurre un fraude, se activa un plan para recuperar la estabilidad económica |
  | Segregación de funciones: se asignan responsabilidades a diferentes empleados para evitar fraudes o abusos de poder | Investigación y mejora de controles: si se detecta un fraude, se investiga y se refuerzan los controles internos |
  | Control interno: políticas y procedimientos que supervisan el cumplimiento de normas | Respaldo de datos y restauración: en caso de fallos internos, se restauran los datos y procesos afectados |
  | Capacitación del personal: entrena para minimizar errores y sabotajes | Reubicación de operaciones en otra sede: si un error o sabotaje compromete una sede, se trasladan las operaciones |
  | Seguridad en las instalaciones: cámaras, accesos restringidos y sistemas de alarma | Comunicación de crisis interna: se informa al personal para evitar el pánico y tomar acciones rápidas |
  | Políticas contra robos y sabotajes: normas estrictas | Investigación y mejora de respuesta de seguridad |
- **Incidentes externos** (ciberataques, crisis política o económica, falla en proveedores):
  | Preventiva | Reactiva |
  |---|---|
  | Seguridad informática (firewalls, antivirus) | Respuesta ante ciberataques (mitigación y restauración): se restauran sistemas y se refuerza la seguridad |
  | Evaluaciones de proveedores antes de contratarlos | Gestión de reclamaciones y compensaciones si un proveedor falla |
  | Monitoreo del mercado y de riesgos políticos | Ajustes en la cadena de suministro (cambios de proveedores o rutas) |
  | Políticas de ciberseguridad y protección de datos | Comunicación de crisis externa (a clientes y socios) |
  | Estrategias de diversificación de proveedores | Activación del plan de contingencia logística |
- **Ejemplos resumidos**: *Fraude financiero interno (interno–económico)*: preventivas = auditorías y segregación de funciones; reactiva = se investiga el caso y se refuerzan los controles. *Ciberataque (externo–tecnológico)*: preventivas = firewalls, antivirus y políticas de seguridad; reactiva = se restauran datos, se bloquea la entrada del atacante y se informa a clientes.

## 4. Resiliencia organizacional
- **Definición**: capacidad de una empresa para **anticiparse, responder y adaptarse** ante cambios o eventos adversos, asegurando la continuidad de sus operaciones.
- **Factores clave**: **Planificación proactiva** (identificar riesgos y desarrollar planes de continuidad) · **Capacidad de respuesta rápida** (procedimientos y equipos entrenados) · **Adaptabilidad** (ajustar estrategias según la evolución de la crisis) · **Aprendizaje continuo** (evaluar incidentes pasados para mejorar respuestas futuras).
- **Relación**: un incidente disruptivo es un evento que interfiere en las operaciones normales; la resiliencia organizacional determina **qué tan bien la empresa afronta, resiste y se recupera** de estos eventos.

## 5. DRII y BCI
- Ambas organizaciones establecen **estándares, buenas prácticas y certificaciones** en gestión de la continuidad del negocio y recuperación ante desastres.
- **DRII (Disaster Recovery Institute International)**: organización con **sede en Estados Unidos** que establece estándares y certificaciones en continuidad del negocio y recuperación ante desastres. **Aportes**: define buenas prácticas con el **PPBCM (Professional Practices for Business Continuity Management)**; ofrece certificaciones reconocidas mundialmente como **CBCP (Certified Business Continuity Professional)** para profesionales con experiencia y conocimiento en continuidad, recuperación ante desastres y resiliencia; proporciona un marco estructurado con **10 dominios clave**.
- **BCI (Business Continuity Institute)**: organización **global** que promueve mejores prácticas en **BCM (Business Continuity Management)**; objetivo: ayudar a las empresas a prepararse, responder y recuperarse de incidentes (resiliencia organizacional). **Aportes**: desarrolla las **Good Practice Guidelines (GPG)**, alineadas con normas internacionales como **ISO 22301**; ofrece certificaciones como **CBCI (Certificate of the Business Continuity Institute)**; enfatiza un enfoque integral de la continuidad, incluyendo la gestión de crisis y la resiliencia organizacional.
- **Diferencia DRII vs BCI**
  | Característica | DRII | BCI |
  |---|---|---|
  | Enfoque principal | Recuperación ante desastres y continuidad del negocio | Continuidad del negocio y resiliencia organizacional |
  | Marco de referencia | PPBCM (Professional Practices for BCM) | GPG (Good Practice Guidelines) |
  | Certificación destacada | CBCP (Certified Business Continuity Professional) | CBCI (Certificate of the Business Continuity Institute) |
  | Alineación con normativas | Basado en prácticas propias y experiencia del sector | Alineado con ISO 22301 |

## Preguntas de cierre (con respuesta)
- ¿Qué es continuidad del negocio? → capacidad de mantener operaciones esenciales durante y después de un incidente disruptivo (planificación y preparación; enfoque estratégico y operativo).
- ¿Qué son incidentes disruptivos y cuántas clases hay? → eventos inesperados que interrumpen significativamente las operaciones; **2 clases: externos e internos**.
- ¿Qué son DRII y BCI? → organizaciones que establecen estándares, buenas prácticas y certificaciones en BCM (DRII: EE.UU., PPBCM, 10 dominios, CBCP; BCI: global, GPG, ISO 22301, CBCI).

## Conclusión del docente
Es necesario **identificar las amenazas potenciales de una organización y los impactos que pueden causar en las operaciones del negocio**.

## Ojo en el examen
- DRII = 10 dominios / PPBCM / CBCP / sede EE.UU.; BCI = GPG / CBCI / ISO 22301 / global.
- Incidentes **externos** (climáticos, sociales, tecnológicos, económicos) vs **internos** (accidentes/incendios, robos/sabotajes/rotación, falta de insumos); preventiva vs reactiva (dar ejemplo).
- Resiliencia: 4 factores. Evaluación: 20-20-30-30; PC1 sem 5, PC2 sem 10, PC3 sem 15, EXFI sem 18.
