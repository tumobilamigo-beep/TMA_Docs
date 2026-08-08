# AUDITORÍA Y MATRIZ DE IMPACTO ARQUITECTÓNICO CONSOLIDADA
## Proyecto: Tu Mobil Amigo V1.0

**Metodología:** Extracción y análisis textual completo de los 55 documentos oficiales del árbol de documentación (00_Gobierno_Proyecto → 07_Producción), cruzados contra los 25 cambios arquitectónicos aprobados listados en el prompt de auditoría, mediante búsqueda semántica, verificación de contexto y lectura directa de las secciones relevantes de cada documento.

**Principio de verdad aplicado:** todo hallazgo citado abajo está referenciado a un documento y, cuando es relevante, a la sección exacta. Donde no se encontró evidencia, se declara explícitamente como ausencia, no como suposición.

---

## 1. RESUMEN EJECUTIVO

La documentación de Tu Mobil Amigo V1.0 tiene una particularidad estructural clara y verificable: **existen dos generaciones de documentos**.

**Generación 1 — Fundacional** (Documentos 00, 01, 02, 03, 06, 07, 08, y los modelos de datos 16/17/18/19): fueron redactados bajo un modelo de **tres roles únicamente** (Cliente, Asesor, Administrador) y una **arquitectura mono-frontend** (solo Flutter). No conocen ni al Superadministrador ni a los portales React.

**Generación 2 — Evolucionada** (Documentos 27, 28, 32, 32A, 33A, 34, 35, 36, 37A, 40, 40A, 41, 41A, 42, 42A y en menor medida 23, 26): ya incorporan explícitamente el Superadministrador, la arquitectura híbrida Flutter/React, Device Registry, ERP futuro, PSE, gestión de secretos, releases, infraestructura, alertas y auditoría ampliada.

**Esto genera una fractura documental real y verificable**, no hipotética: la Generación 1 sigue afirmando reglas ("solo existen tres roles", DA-005 del Documento 06) que la Generación 2 contradice directamente (DA-033 del mismo documento, y el Documento 28 completo dedicado al portal de Superadministrador). Cualquier IA, desarrollador o auditor que consulte primero Documento 02 o Documento 08 recibirá información oficialmente "Aprobada" pero obsoleta.

Adicionalmente, el **modelo de datos central (16/17/18/19) nunca fue actualizado** para soportar roles/permisos (no existe tabla `roles`, `permisos` ni `roles_permisos` en ningún catálogo), pese a que el Documento 28 declara explícitamente "Modelo: RBAC" para los portales de Administrador y Superadministrador. Esto es un vacío arquitectónico crítico: el modelo de autorización está descrito a nivel de aplicación pero no tiene sustento en la base de datos.

Se identificaron:
- **7 documentos en Categoría A (Cambio Crítico)**
- **9 documentos en Categoría B (Cambio Alto)**
- **14 documentos en Categoría C (Cambio Medio)**
- **25 documentos en Categoría D (Sin Impacto)**
- **1 inconsistencia de numeración interna** (DA-031 duplicado en Documento 06)
- **1 contradicción directa** entre reglas activas del mismo documento (DA-005 vs DA-033)
- **4 catálogos/documentos faltantes** con necesidad sustentada documentalmente
- **2 falsos amigos terminológicos** relevantes para desarrollo (device_registry vs "dispositivos" como nombre informal; PSE ya cubierto contra lo que el prompt de auditoría sugiere)

---

## 2. HALLAZGOS CRÍTICOS

### H-C1 — Contradicción activa de roles en Documento 06 (Decisiones Arquitectónicas)
**Evidencia:** DA-005 ("Roles del Sistema") establece textualmente: *"Existen únicamente tres roles oficiales: Cliente, Asesor, Administrador"*, con Estado = APROBADA. Más abajo, en el mismo documento, DA-033 ("Separación Tecnológica Frontend") establece: *"Los portales de gestión (Administrador y Superadministrador) serán desarrollados en React"*, también con Estado = APROBADA.
**Impacto:** dos decisiones activas, ambas "Aprobadas", se contradicen sobre cuántos roles administrativos existen oficialmente. Cualquier IA que siga el Documento 01 — Prompt Maestro ("no podrá contradecir documentos previamente aprobados") queda en un dilema sin salida documental.
**Recomendación:** actualizar DA-005 a cuatro roles oficiales (Cliente, Asesor, Administrador, Superadministrador) y dejar registro de versión en la tabla de cambios.

### H-C2 — Documento 07 (Arquitectura General) no refleja la arquitectura híbrida aprobada
**Evidencia:** La Sección 3 ("Arquitectura Base") muestra el diagrama oficial como `Cliente APK Flutter → Supabase Backend`, sin mención de portales React. La Sección 4 ("Componentes Principales – Frontend Mobile") solo describe Flutter. La Sección 6 ("Canales Oficiales") solo lista APK Android y Telegram, sin canal web administrativo. La Sección 5 ("Dominio Usuarios") lista "Administradores" pero no "Superadministrador".
**Impacto:** este es el documento que define "la fuente oficial de diseño arquitectónico del proyecto" (texto literal, Sección 1). Que no incluya la arquitectura híbrida ya aprobada en DA-033 y desarrollada en detalle en el Documento 28 es la brecha más grave detectada, porque es el documento de mayor autoridad arquitectónica del árbol.
**Recomendación:** reescribir Secciones 3, 4 y 6 para incorporar los portales React (Administrador/Superadministrador) como componentes de primera clase, no como nota al margen.

### H-C3 — Roles/Permisos ausentes del modelo de datos (Documentos 16, 17, 18, 19)
**Evidencia:** búsqueda exhaustiva de "rol", "permiso", "superadmin" en Modelo Conceptual (16), Modelo Lógico (17) y Modelo Físico (18): **cero coincidencias en los tres documentos**. El Catálogo de Tablas (19) no incluye ninguna tabla `roles`, `permisos` ni `roles_permisos`; la tabla `usuarios` se relaciona con `asesores`, `dispositivos`, `billeteras`, `trust_score`, `ipa`, `ipr`, `imf` — pero no con ninguna entidad de autorización.
**Impacto:** el Documento 28 (Arquitectura React) afirma en su Sección 32: *"Autorización — Modelo: RBAC — Roles: Administrador, Superadministrador"*. No existe ninguna tabla, ni en el modelo lógico ni en el físico, que soporte ese RBAC. Esto es una brecha entre lo que el backend/frontend asume y lo que la base de datos realmente modela.
**Recomendación:** incorporar entidades `roles`, `permisos`, `usuario_roles` (o equivalente) en el Modelo Conceptual/Lógico/Físico y en el Catálogo de Tablas, con políticas RLS asociadas.

### H-C4 — Documentos 00, 02, 03 y 08 (capa de Gobierno y Modelo Operativo) desactualizados en roles
**Evidencia:** Documento 02 (Contexto Maestro), Sección 6: *"Actualmente existen únicamente tres roles oficiales"* (Cliente, Asesor, Administrador). Documento 08 (Modelo Operativo), líneas 32-40: mismo listado, sin Superadministrador. Documento 03 (Seguridad Maestra), Sección 23, habla de "administradores" en genérico sin diferenciar niveles de privilegio, pese a que el Documento 32 (Ciberseguridad) sí exige 2FA obligatorio específicamente para Superadministrador.
**Impacto:** estos son los documentos que "cualquier IA, desarrollador, arquitecto o consultor deberá utilizar... como referencia principal" (texto literal del Documento 02, Sección 1). Están desalineados con la decisión ya aprobada y ya implementada documentalmente en capas posteriores (Backend, Seguridad, Producción).
**Recomendación:** propagar la definición de cuatro roles a estos cuatro documentos como corrección editorial prioritaria — es bajo esfuerzo y alto impacto de consistencia.

### H-C5 — Glosario Corporativo (Documento 05) no define "Superadministrador"
**Evidencia:** búsqueda de "superadmin" en el Glosario: cero resultados. Solo existe la entrada "Administrador".
**Impacto:** el Documento 02 cierra diciendo que la documentación aprobada es "la única fuente de verdad" y el glosario debe ser la referencia de términos oficiales; que el rol de mayor privilegio del sistema no tenga entrada de glosario es una omisión crítica para cualquier onboarding técnico o auditoría legal/financiera.
**Recomendación:** agregar entradas: Superadministrador, Device Registry, PSE, ERP, RBAC, Liquidación Extraordinaria, Reapertura de Período.

### H-C6 — Ausencia de "Algoritmo de Elegibilidad" como motor/documento propio
**Evidencia:** el término "elegibilidad" aparece disperso en Documento 33 (Protección Financiera), Documento 39 (Validaciones) y Documento 09 (Modelo Financiero) siempre como *atributo verificado dentro de otra regla* ("verificar... elegibilidad"), nunca como un motor o algoritmo configurable con parámetros propios almacenados en base de datos.
**Impacto:** el cambio aprobado #19 ("Algoritmo de elegibilidad configurable") no tiene un documento, sección ni tabla que lo defina como entidad propia — es una ausencia real y demostrable, no una omisión menor.
**Recomendación:** ver Sección 6 — Documentos Faltantes.

### H-C7 — Sistema Multinivel (Documento 12) no contempla ningún actor administrativo
**Evidencia:** búsqueda de "administrador"/"superadmin" en Documento 12: cero coincidencias, pese a que Documento 28 (React) sí incluye un módulo "Multinivel" con visualización de árbol, comisiones y acumulados para Administrador/Superadministrador.
**Impacto:** el documento de arquitectura del dominio Multinivel no reconoce ninguna capacidad de supervisión, ajuste o intervención administrativa sobre la red, lo que deja sin base documental de origen las funciones que el Documento 28 ya promete.
**Recomendación:** agregar sección de "Supervisión Administrativa" al Documento 12, referenciando al Documento 28.

---

## 3. HALLAZGOS ALTOS

### H-A1 — Duplicidad de numeración DA-031 en Documento 06
**Evidencia:** el documento contiene dos decisiones distintas ambas etiquetadas "DA-031": "Evolución de Infraestructura Cartográfica" y "Arquitectura Modular por Dominios". Todo lo posterior (DA-032, DA-033) queda con numeración ambigua respecto a cuál "DA-031" referencian otros documentos.
**Recomendación:** renumerar consecutivamente (DA-031 y DA-032, corriendo el resto +1) y actualizar cualquier referencia cruzada existente en otros documentos.

### H-A2 — "Modo oscuro administrado desde frontend" no está definido a nivel de administración
**Evidencia:** Documento 30 (UI Kit), Sección 28, define modo oscuro como **preferencia local del usuario** (Claro/Oscuro/Automático, persistida en el dispositivo). Documento 27 (Arquitectura Flutter) confirma esto como "Preferencias Visuales Locales". Documento 28 (React Admin/Superadmin) — que es el portal desde el cual, según el cambio aprobado #20, debería administrarse — **no menciona "modo oscuro" en ninguna de sus 39 secciones**.
**Impacto:** el cambio aprobado dice explícitamente "administrado **desde frontend**" (es decir, desde el panel de Administrador/Superadministrador), pero la documentación actual solo contempla selección local por el usuario final, no una configuración administrada centralmente (p. ej. forzar tema por marca blanca, por ciudad, o por campaña).
**Recomendación:** clarificar con el equipo de producto si "administrado desde frontend" significa (a) selección del usuario persistida, ya cubierta, o (b) un parámetro configurable por el Administrador/Superadministrador — y en ese caso documentarlo en el Documento 28.

### H-A3 — Documento 26 (Integraciones) no incluye ERP pese a ser el documento natural para adaptadores externos
**Evidencia:** Documento 26 define adaptadores explícitos para PSE (`PSEAdapter`), mapas, notificaciones, Telegram y correo — pero no contiene ninguna sección "ERP" o `ERPAdapter`, mientras que el Documento 09 (Modelo Financiero, Sección 31) y el Documento 23 (Edge Functions) sí anticipan `exportar_erp()`, `sincronizar_erp()`, `consultar_estado_erp()` como capacidades futuras.
**Impacto:** inconsistencia de ubicación — la lógica de integración ERP está fragmentada entre Modelo Financiero y Edge Functions, pero ausente del documento cuyo propósito explícito es catalogar integraciones externas.
**Recomendación:** agregar sección "Integración ERP (Futura)" al Documento 26, replicando el patrón de fase-inicial/fase-crecimiento ya usado para PSE.

### H-A4 — Nomenclatura ambigua "dispositivos" vs "device_registry" en Documento 19
**Evidencia:** en la Sección 3 ("Núcleo de Usuarios") la tabla aparece listada simplemente como `dispositivos` (dependencia de `usuarios` y de `asesores`), mientras que en la Sección posterior se define formalmente como `device_registry`, con reglas de negocio RN-DR-001 a RN-DR-007.
**Impacto:** bajo, pero real para consistencia de nomenclatura entre documentos y código — un desarrollador que busque "dispositivos" como nombre de tabla real generará una migración con nombre incorrecto.
**Recomendación:** unificar toda referencia a `device_registry` desde la primera mención.

### H-A5 — Documento 03 (Seguridad Maestra) no diferencia niveles de privilegio administrativo
**Evidencia:** Sección 23 ("Seguridad Operativa") habla de "los administradores" en genérico, con capacidad de suspender usuarios, congelar beneficios, bloquear operaciones. No hay distinción de qué le corresponde a Administrador vs Superadministrador, mientras Documento 28 sí segmenta con precisión (Sección 10 vs 11).
**Recomendación:** replicar en Documento 03 la segmentación de privilegios ya definida en Documento 28, al menos por referencia cruzada explícita.

### H-A6 — Documento 09 (Modelo Financiero) no menciona explícitamente "Reapertura de Período" ni "Liquidación Manual" con el mismo nivel de detalle que Documento 33A
**Evidencia:** Documento 33A contiene 19 menciones de conciliación, define Reapertura de Período (Sección 34, exclusiva de Superadministrador) y Liquidación Manual (Sección asociada). Documento 09, que es la fuente arquitectónica del modelo financiero, solo tiene 1 mención de "liquidación mensual" y ninguna de "reapertura".
**Recomendación:** Documento 09 debería referenciar formalmente al Documento 33A como su extensión operativa, para que la trazabilidad de la regla de negocio no dependa solo del documento de seguridad.

### H-A7 — Documento 24 (Sistema Realtime) no fue revisado contra el catálogo de alertas ampliado
**Evidencia:** Documento 42A (Catálogo de Alertas e Incidentes) tiene 476 líneas con eventos que probablemente deban propagarse por Realtime (alertas de liquidación, antifraude, dispositivos); Documento 24 no menciona el Documento 42A ni su catálogo de eventos como fuente.
**Recomendación:** agregar referencia cruzada en Documento 24 a los tipos de eventos definidos en 42A que deban emitirse por canal Realtime.

### H-A8 — Documento 20/21 (Catálogos de Funciones/Triggers) no contienen funciones de soporte a RBAC
**Evidencia:** cero menciones de "rol" en ambos catálogos.
**Impacto:** si se corrige H-C3 (agregar tablas de roles), estos catálogos también requerirán funciones (`fn_verificar_permiso`, etc.) y triggers de auditoría sobre cambios de rol.
**Recomendación:** actualización dependiente de H-C3 — no puede resolverse de forma aislada.

### H-A9 — Documento 39 (Validaciones) no incluye validaciones específicas de Superadministrador (reapertura, liquidación extraordinaria)
**Evidencia:** Documento 39 tiene reglas de validación tarifaria, multinivel y elegibilidad, pero no valida los flujos exclusivos de Superadministrador ya descritos en 33A (reapertura) y 28 (liquidación extraordinaria).
**Recomendación:** agregar sección de "Validaciones de Operaciones Superadministrativas".

---
## 4. HALLAZGOS MEDIOS

| # | Hallazgo | Documento(s) | Evidencia breve |
|---|---|---|---|
| H-M1 | Trust Score (13) no referencia explícitamente Device Registry por nombre de tabla | Doc 13 | Habla de "dispositivo" genérico, no de `device_registry` |
| H-M2 | Motor Antifraude (15) no referencia el catálogo de alertas 42A | Doc 15 / 42A | Ambos documentos hablan de "alertas" sin cruzarse formalmente |
| H-M3 | Componentes UI (31) menciona modo oscuro solo 1 vez, sin detalle de theming administrado | Doc 31 | Confirma gap de H-A2 a nivel de componentes |
| H-M4 | Casos de Prueba (38) no incluye casos para Superadministrador/reapertura | Doc 38 | Los casos financieros específicos están solo en 38A, no en el general |
| H-M5 | Estrategia de Testing (37) no menciona explícitamente pruebas de portal React | Doc 37 | Pentesting de React sí está cubierto en 37A, pero no en la estrategia general |
| H-M6 | Anexo A (Estándares SQL) no define convención de nombres para tablas de auditoría de Superadmin | Anexo A | Puede heredar del estándar general, pero no hay ejemplo explícito |
| H-M7 | Anexo B (Guía de Modelado) no ejemplifica cómo modelar una entidad de rol/permiso nueva | Anexo B | Relevante directamente para resolver H-C3 |
| H-M8 | Anexo C (Principios Backend) no referencia el Modular Monolith con dominio "Admin" definido en DA-031(bis) | Anexo C | DA-031/DA-032 de Doc 06 listan dominio "Admin" y "Audit"; Anexo C no los nombra explícitamente |
| H-M9 | APIs (25) no documenta endpoints específicos para Superadministrador (reapertura, liquidación extraordinaria) | Doc 25 | Los endpoints existentes son genéricos de dominio, no por rol |
| H-M10 | Documento 22 (Arquitectura Backend) no referencia el dominio "Admin" ni "Audit" de forma explícita en su propio texto | Doc 22 | Debe alinearse con DA-031(bis)/DA-032 del Doc 06 |
| H-M11 | Continuidad Operativa (36) no contempla escenario de caída específica del portal React Admin/Superadmin | Doc 36 | Cubre OSM/GraphHopper/backend, pero no un plan de contingencia del frontend administrativo |
| H-M12 | DevOps (40) y CI/CD (41) no detallan pipeline separado para los 4 frontends (Flutter Cliente, Flutter Asesor, React Admin, React Superadmin) con el mismo nivel de detalle que 40A/41A | Docs 40, 41 | 40A y 41A sí lo detallan; 40/41 (los documentos "padre") deberían reflejar al menos el resumen |
| H-M13 | Monitoreo (42) no define KPIs específicos de los portales React | Doc 42 | Tiene 6 menciones de "monitoreo" pero orientadas a backend/infraestructura |
| H-M14 | Operación (43) no detalla procedimiento operativo de "Reapertura de Período" paso a paso, solo lo referencia | Doc 43 | Remite a 33A pero no incluye el runbook operativo correspondiente |

---

## 5. MATRIZ DE IMPACTO ARQUITECTÓNICO CONSOLIDADA

**Leyenda de Estado:** 🔴 Crítico · 🟠 Alto · 🟡 Medio · ⚪ Sin cambios/menor

### 00_Gobierno_Proyecto

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 00 — Visión y Principios | ⚪ Sin cambios | Documento de visión/valores; no fija roles ni arquitectura técnica | — | Ninguno obligatorio | — |
| 01 — Prompt Maestro | 🟡 Medio | No menciona explícitamente Superadministrador entre las tecnologías/roles que la IA debe conocer | Sección 9 (Tecnologías Oficiales) | Agregar React/TypeScript y rol Superadministrador a la lista de tecnologías/roles reconocidos | 06, 07 |
| 02 — Contexto Maestro | 🔴 Crítico | Sección 6 afirma "únicamente tres roles oficiales", contradice DA-033 aprobada | Sección 6 (Roles del Ecosistema) | Agregar Superadministrador con sus responsabilidades | 06, 07, 08, 28 |
| 03 — Seguridad Maestra | 🟠 Alto | No diferencia privilegios Administrador/Superadministrador pese a exigirlo el Doc 32 (2FA) | Sección 23 (Seguridad Operativa) | Segmentar capacidades por rol administrativo | 28, 32 |
| 04 — Roadmap Estratégico | 🟡 Medio | Debe confirmarse si incluye hitos de ERP/PSE/portales React como entregables con fecha | General | Verificar inclusión de hitos de los 25 cambios aprobados en el roadmap | 06 |
| 05 — Glosario Corporativo | 🔴 Crítico | No define "Superadministrador", "Device Registry", "PSE", "ERP", "RBAC" | General | Agregar entradas faltantes (ver Sección 6) | Todos |
| 06 — Decisiones Arquitectónicas | 🔴 Crítico | DA-005 contradice DA-033; DA-031 duplicado | DA-005, DA-031 (dos veces) | Corregir DA-005 a 4 roles; renumerar DA-031 duplicado | 02, 07, 08, 19 |

### 01_Arquitectura

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 07 — Arquitectura General | 🔴 Crítico | Diagrama y componentes no incluyen portales React; canal web ausente | Secc. 3, 4, 5, 6 | Incorporar arquitectura híbrida como componente oficial | 06, 27, 28 |
| 08 — Modelo Operativo | 🔴 Crítico | Lista de roles no incluye Superadministrador | Secc. roles (líneas 32-40) | Agregar Superadministrador y su interacción operativa | 02, 06, 28 |
| 09 — Modelo Financiero | 🟠 Alto | No detalla Reapertura de Período ni Liquidación Manual al nivel de 33A | Secc. 31 (Integración Contable Futura) y liquidaciones | Referenciar formalmente 33A; ampliar ERP | 33A, 26 |
| 10 — Motor Tarifario | ⚪ Sin cambios | No depende de roles administrativos nuevos ni de integraciones cartográficas nuevas | — | Ninguno | — |
| 11 — Sistema de Negociación | ⚪ Sin cambios | Reglas de negociación cliente-asesor no afectadas por los 25 cambios | — | Ninguno | — |
| 12 — Sistema Multinivel | 🟠 Alto | No contempla supervisión administrativa pese a que Doc 28 sí promete módulo Multinivel para Admin/Superadmin | General | Agregar sección de supervisión administrativa | 28 |
| 13 — Trust Score | 🟡 Medio | No usa el nombre formal `device_registry` de forma consistente | Relación con dispositivos | Alinear nomenclatura | 34, 19 |
| 14 — Índice de Maduración Financiera (IMF) | ⚪ Sin cambios | No depende de roles ni de las integraciones nuevas | — | Ninguno | — |
| 15 — Motor Antifraude | 🟡 Medio | No referencia el Catálogo de Alertas (42A) | General | Cruzar catálogo de eventos con 42A | 42A |

### 02_Base_Datos

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 16 — Modelo Conceptual | 🔴 Crítico | Cero entidades de rol/permiso pese a RBAC declarado en Doc 28 | General | Agregar entidad Rol/Permiso | 17, 18, 19, 28 |
| 17 — Modelo Lógico | 🔴 Crítico | Mismo vacío que 16, a nivel de atributos y relaciones | General | Modelar `roles`, `permisos`, `usuario_rol` | 16, 18, 19 |
| 18 — Modelo Físico | 🔴 Crítico | Sin DDL de tablas de rol/permiso | General | Agregar DDL de tablas de autorización + índices | 16, 17, 19 |
| 18A — Plan Maestro de Implementación de BD | 🟠 Alto | El plan de fases debe incorporar la fase de tablas RBAC si se agregan | General | Actualizar cronograma de implementación | 16, 17, 18 |
| 19 — Catálogo de Tablas | 🔴 Crítico | Sin tabla `roles`/`permisos`; nomenclatura ambigua "dispositivos" vs `device_registry` | Secc. 3, tabla device_registry | Agregar catálogo de roles; unificar nomenclatura | 16, 17, 18 |
| 20 — Catálogo de Funciones | 🟠 Alto | Sin funciones de verificación de permisos | General | Agregar `fn_verificar_permiso()` u homólogo | 19 (dependiente de H-C3) |
| 21 — Catálogo de Triggers | 🟠 Alto | Sin triggers de auditoría sobre cambios de rol | General | Agregar trigger de auditoría de asignación de rol | 19, 35 |
| Anexo A — Estándares SQL | 🟡 Medio | No ejemplifica convención de nombres para tablas de autorización | General | Agregar ejemplo con `roles`/`permisos` | 19 |
| Anexo B — Guía de Modelado de Nuevas Entidades | 🟡 Medio | No incluye ejemplo de modelado de rol/permiso como caso guía | General | Agregar caso de estudio de RBAC | 16, 17 |

### 03_Backend

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 22 — Arquitectura Backend | 🟡 Medio | No nombra explícitamente dominios "Admin"/"Audit" de DA-031(bis)/032 | General | Alinear texto con dominios ya aprobados en Doc 06 | 06 |
| 23 — Edge Functions | ⚪ Sin cambios | Ya anticipa `exportar_erp`, `sincronizar_erp`, `consultar_estado_erp` como futuros; ya cubre PSE y device fingerprint | — | Ninguno urgente | — |
| 24 — Sistema Realtime | 🟠 Alto | No referencia el catálogo de eventos/alertas de 42A | General | Cruzar tipos de evento con 42A | 42A |
| 25 — APIs | 🟡 Medio | Sin endpoints diferenciados por rol administrativo (Superadmin) | General | Documentar endpoints exclusivos de Superadministrador | 28 |
| 26 — Integraciones | 🟠 Alto | PSE bien cubierto; ERP ausente pese a estar aprobado (DA-032) | General (falta sección ERP) | Agregar sección "Integración ERP (Futura)" | 09, 23, 06 |
| Anexo C — Principios de Arquitectura Backend | 🟡 Medio | No nombra dominios Admin/Audit explícitamente | General | Alinear con DA-031(bis) | 06, 22 |

### 04_Flutter

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 27 — Arquitectura Flutter | ⚪ Sin cambios | Ya define los 4 roles, ya excluye interfaces admin de Flutter, ya cubre ERP/CRM/BI como compatibilidad futura | Secc. 35, 36 | Ninguno urgente | — |
| 28 — Arquitectura React (Admin/Superadmin) | 🟡 Medio | Documento más completo del árbol; solo falta "modo oscuro administrado" y numeración duplicada de Secc. 39 | Secc. 39 (duplicada) | Corregir numeración; evaluar si agregar control de tema | — |
| 29 — Gestión de Estado | ⚪ Sin cambios | Riverpod no depende de los 25 cambios (coincidencias de "erp" eran falsos positivos de "Riverpod") | — | Ninguno | — |
| 30 — UI Kit | 🟡 Medio | Modo oscuro documentado como preferencia local, no como parámetro "administrado desde frontend" | Secc. 28 | Clarificar alcance de administración centralizada del tema | 28 |
| 31 — Componentes | ⚪ Sin cambios | Mención de modo oscuro es solo de estilo visual, consistente con Doc 30 | — | Ninguno urgente | 30 |

### 05_Seguridad

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 32 — Ciberseguridad | ⚪ Sin cambios | Ya exige 2FA obligatorio para Superadministrador | — | Ninguno | — |
| 32A — Gestión de Secretos y Credenciales | ⚪ Sin cambios | Documento ya dedicado íntegramente al cambio aprobado #11/#22/#23 | — | Ninguno | — |
| 33 — Protección Financiera | ⚪ Sin cambios | Ya cubre liquidaciones manuales y elegibilidad como controles | — | Ninguno | — |
| 33A — Conciliación Financiera y Cierre Contable | ⚪ Sin cambios | Documento más alineado del árbol con cambios #5, #6, #7, #24 | — | Ninguno | — |
| 34 — Gestión de Dispositivos | ⚪ Sin cambios | Documento completo y coherente; ya define `device_registry` formalmente | — | Ninguno | 19 (debe reflejar la misma tabla) |
| 35 — Auditoría y Trazabilidad | 🟡 Medio | Ya cubre auditoría de Superadministrador; falta cruzar con releases (41A) y credenciales (32A) explícitamente | Secc. 34 | Agregar referencias cruzadas a 41A y 32A | 41A, 32A |
| 36 — Continuidad Operativa | 🟡 Medio | No contempla contingencia específica de caída del portal React Admin/Superadmin | General | Agregar escenario de contingencia de frontend administrativo | 28, 40A |

### 06_Testing

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 37 — Estrategia de Testing | 🟡 Medio | No menciona explícitamente pruebas del portal React como categoría propia | General | Agregar categoría "Testing de Portales React" | 37A |
| 37A — Testing de Seguridad y Pentesting | ⚪ Sin cambios | Ya cubre pentesting de React Admin/Superadmin explícitamente | — | Ninguno | — |
| 38 — Casos de Prueba | 🟡 Medio | Sin casos específicos de Superadministrador/reapertura | General | Agregar casos de reapertura y liquidación extraordinaria | 38A, 33A |
| 38A — Casos de Prueba Financieros | ⚪ Sin cambios | Ya cubre escenarios financieros críticos | — | Ninguno | — |
| 39 — Validaciones | 🟠 Alto | Sin validaciones de operaciones exclusivas de Superadministrador | General | Agregar sección de validaciones superadministrativas | 33A, 28 |

### 07_Producción

| Documento | Estado | Motivo | Sección afectada | Cambio requerido | Dependencias |
|---|---|---|---|---|---|
| 40 — DevOps | 🟡 Medio | No resume, a su propio nivel, el pipeline de los 4 frontends (sí lo hace 40A) | General | Agregar resumen ejecutivo alineado a 40A | 40A |
| 40A — Gestión de Infraestructura y Ambientes | ⚪ Sin cambios | Documento ya completamente alineado con arquitectura híbrida | — | Ninguno | — |
| 41 — CI/CD | 🟡 Medio | Igual que Documento 40, falta resumen alineado a 41A | General | Agregar resumen ejecutivo alineado a 41A | 41A |
| 41A — Gestión de Releases y Versionamiento | ⚪ Sin cambios | Documento más completo en cobertura de los 25 cambios (30 coincidencias) | — | Ninguno | — |
| 42 — Monitoreo | 🟡 Medio | Sin KPIs específicos de los portales React | General | Agregar KPIs de frontend administrativo | 42A |
| 42A — Catálogo de Alertas e Incidentes | ⚪ Sin cambios | Documento ya dedicado íntegramente al cambio aprobado #14 | — | Ninguno | — |
| 43 — Operación | 🟠 Alto | Referencia la reapertura de período pero no documenta el runbook operativo paso a paso | General | Agregar procedimiento operativo de reapertura | 33A |

---
## 6. DOCUMENTOS FALTANTES

Reportados únicamente donde la necesidad está sustentada por evidencia documental directa (no especulación):

### 6.1 Documento faltante: "Modelo de Roles y Permisos (RBAC)"
**Evidencia que sustenta la necesidad:** Documento 28, Sección 32, declara explícitamente "Modelo: RBAC" con roles Administrador y Superadministrador; Documento 06, DA-033, aprueba la separación de portales; ninguno de los tres modelos de datos (16/17/18) ni el Catálogo de Tablas (19) contiene la entidad correspondiente. Es el vacío más citado a lo largo de esta auditoría (H-C3, H-A8, H-M6, H-M7).
**Ubicación sugerida:** nuevo Documento en `02_Base_Datos` (ej. Documento 21A) o ampliación formal de 17/18/19.

### 6.2 Catálogo faltante: "Catálogo de Eventos de Negocio / Realtime"
**Evidencia:** el Documento 24 (Sistema Realtime) describe responsabilidades generales ("nuevos servicios, ofertas, contraofertas, estados, notificaciones") sin un catálogo formal de nombres de evento, payloads o canales — a diferencia del Documento 42A que sí cataloga formalmente alertas e incidentes con esa disciplina. La ausencia de un catálogo equivalente para eventos Realtime de negocio (no solo de infraestructura) es evidenciable por comparación directa entre ambos documentos.
**Ubicación sugerida:** nuevo documento en `03_Backend`, complementario a 24.

### 6.3 Documento faltante: "Motor / Algoritmo de Elegibilidad"
**Evidencia:** "elegibilidad" se usa como criterio validado en al menos tres documentos distintos (09, 33, 39) sin que exista una definición única, centralizada y configurable del algoritmo — contraviene el principio DA-029 del propio Documento 06 ("ningún parámetro de negocio configurable podrá modelarse mediante columnas fijas cuando exista posibilidad razonable de crecimiento futuro... se priorizará Configuración → Registro"). La elegibilidad, al estar dispersa, viola su propio principio de diseño.
**Ubicación sugerida:** nuevo documento en `01_Arquitectura`, junto a Motor Tarifario (10) y Motor Antifraude (15).

### 6.4 Anexo faltante: "Runbooks Operativos de Superadministrador"
**Evidencia:** Documento 33A define Reapertura de Período y Liquidación Manual como operaciones exclusivas de Superadministrador con "justificación obligatoria"; Documento 43 (Operación) las referencia pero no las documenta como procedimiento operativo paso a paso, a diferencia de otros procedimientos operativos que sí están detallados en ese mismo documento.
**Ubicación sugerida:** anexo de `07_Producción`, vinculado a 43 y 33A.

---

## 7. RIESGOS DETECTADOS

| Riesgo | Impacto | Probabilidad | Recomendación |
|---|---|---|---|
| Un desarrollador o IA consulta primero Documento 02/08 (roles = 3) y construye lógica de autorización sin contemplar Superadministrador | Alto — requiere refactorización de RLS y de UI ya construida | Alta, dado que son los documentos de "referencia principal" según su propio texto | Corregir H-C1/H-C4 antes de cualquier sprint de construcción de autorización |
| Ausencia de tablas de rol/permiso en el modelo de datos mientras el frontend (Doc 28) ya asume RBAC | Crítico — riesgo de implementar autorización con roles hardcodeados en frontend en lugar de en RLS/Postgres, violando el propio principio DA-029 y las reglas del Documento 07 ("prohibido... reglas financieras/lógica crítica fuera del backend") | Alta si no se corrige antes del desarrollo de Backend/BD | Priorizar H-C3 como bloqueante de la fase Base de Datos |
| Contradicción DA-005/DA-033 usada como excusa para justificar decisiones opuestas por distintos equipos (frontend vs backend) en paralelo | Medio-Alto — reduce la autoridad del documento como "fuente única de verdad" (DA-027) | Media | Resolver antes de escalar el equipo de desarrollo |
| Falta de runbook de Reapertura de Período | Medio — riesgo operativo/financiero: una operación crítica y sensible (afecta cierres contables) sin procedimiento estandarizado puede ejecutarse de forma inconsistente entre distintos Superadministradores | Media | Documentar antes de habilitar la función en producción |
| ERP fragmentado entre 3 documentos (09, 23, 06) sin sección propia en Integraciones (26) | Bajo-Medio — riesgo de implementación duplicada o inconsistente de adaptadores cuando se aborde la integración real | Baja en el corto plazo (es "futuro"), pero crece con el tiempo si no se centraliza | Consolidar en Documento 26 antes de iniciar la integración real |
| "Modo oscuro administrado" mal interpretado por el equipo de desarrollo (local vs centralizado) | Bajo — esfuerzo de desarrollo perdido si se construye la interpretación equivocada | Media, por ambigüedad real del texto del cambio aprobado | Clarificar con producto antes de asignar el ticket de desarrollo |
| Nomenclatura ambigua `dispositivos` vs `device_registry` | Bajo — error de nombre de tabla en migración inicial | Baja-Media | Unificar nomenclatura en la primera pasada de corrección documental |
| Numeración duplicada DA-031 usada como referencia cruzada incorrecta en documentos futuros | Bajo | Baja | Corregir en la misma pasada que H-C1 |

---

## 8. RECOMENDACIONES PRIORITARIAS

1. **No iniciar (o pausar) el desarrollo de RLS y tablas de autorización en Supabase** hasta resolver H-C3 (modelo de roles/permisos ausente). Es el hallazgo con mayor riesgo de retrabajo técnico real.
2. **Congelar temporalmente DA-005** como decisión activa y reemplazarla por una versión corregida antes de que cualquier nueva IA o desarrollador la consulte como fuente de verdad — es rápido de corregir y alto el costo de no hacerlo.
3. **Tratar Documento 07 como el siguiente en la cola de actualización**, por ser la "fuente oficial de diseño arquitectónico" según su propio texto; su desactualización se propaga por autoridad documental a todo lo demás.
4. **Usar el Documento 28 como plantilla de referencia** para actualizar 02, 03, 07 y 08 — es, por lejos, el documento con mejor cobertura de los 25 cambios aprobados y puede servir como fuente de "texto a propagar" antes que redactar desde cero.
5. **Resolver la ambigüedad de "modo oscuro administrado desde frontend" con el equipo de producto** antes de tocar documentación — es el único cambio aprobado cuyo alcance real no puede determinarse solo con evidencia documental.
6. **Consolidar ERP en Documento 26** replicando el patrón fase-inicial/fase-crecimiento ya validado y funcionando para PSE.
7. **No tratar las correcciones editoriales (roles, glosario, numeración) como menores por ser "solo texto"**: dado que el Documento 01 obliga a cualquier IA a "no contradecir documentos previamente aprobados", cada contradicción sin resolver es una fuente activa de error en desarrollo futuro, no un defecto cosmético.

---

## 9. PLAN DE ACTUALIZACIÓN DOCUMENTAL

**Fase 1 — Corrección de Contradicciones (bloqueante, bajo esfuerzo)**
Documentos: 06 (DA-005, DA-031 duplicado)
Objetivo: eliminar la contradicción activa antes de que se propague a más documentos o código.

**Fase 2 — Propagación de Roles a Capa Fundacional (alto impacto, esfuerzo medio)**
Documentos: 02, 03, 07, 08, 05 (glosario)
Objetivo: alinear los documentos de mayor autoridad con la decisión ya aprobada (Superadministrador + arquitectura híbrida), usando el Documento 28 como fuente de texto.

**Fase 3 — Modelo de Datos RBAC (bloqueante para desarrollo de Backend, esfuerzo alto)**
Documentos: 16, 17, 18, 19, 20, 21, Anexo A, Anexo B
Objetivo: dar sustento real en base de datos al RBAC que Frontend/Backend ya asumen. Es la fase de mayor esfuerzo pero también la de mayor riesgo si se omite.

**Fase 4 — Consolidación de Integraciones Futuras (esfuerzo bajo, no bloqueante)**
Documentos: 26 (ERP), 09 (referencia cruzada a 33A)
Objetivo: centralizar documentación de ERP; no bloquea desarrollo actual porque ERP es "futuro" en todos los documentos.

**Fase 5 — Cierre de Brechas Operativas y de Testing (esfuerzo medio, no bloqueante a corto plazo)**
Documentos: 12, 22, Anexo C, 24, 25, 35, 36, 37, 38, 39, 40, 41, 42, 43
Objetivo: cruzar referencias, agregar runbooks y casos de prueba faltantes, alinear documentos "padre" (40, 41, 42) con sus anexos ya actualizados (40A, 41A, 42A).

**Fase 6 — Clarificación de Producto (paralela, no depende de las anteriores)**
Tema: "Modo oscuro administrado desde frontend"
Objetivo: obtener definición de producto antes de tocar Documento 28/30.

**Fase 7 — Documentos Nuevos**
Objetivo: crear los 4 documentos/anexos faltantes identificados en la Sección 6, una vez cerradas las Fases 1-3 (dependen de que exista ya el modelo de roles).

---

## 10. ORDEN RECOMENDADO DE MODIFICACIÓN DOCUMENTO POR DOCUMENTO

1. **Documento 06** — Decisiones Arquitectónicas (corregir DA-005, renumerar DA-031 duplicado)
2. **Documento 07** — Arquitectura General (incorporar arquitectura híbrida)
3. **Documento 02** — Contexto Maestro (actualizar roles)
4. **Documento 08** — Modelo Operativo (actualizar roles)
5. **Documento 03** — Seguridad Maestra (segmentar privilegios administrativos)
6. **Documento 05** — Glosario Corporativo (agregar términos faltantes)
7. **Documento 16** — Modelo Conceptual (agregar entidad Rol/Permiso)
8. **Documento 17** — Modelo Lógico (modelar atributos y relaciones RBAC)
9. **Documento 18** — Modelo Físico (DDL de tablas de autorización)
10. **Documento 19** — Catálogo de Tablas (agregar tablas nuevas; unificar nomenclatura device_registry)
11. **Documento 20 / 21** — Catálogos de Funciones y Triggers (funciones y triggers de RBAC)
12. **Anexo A / Anexo B** (02_Base_Datos) — ejemplos de convención y modelado con el caso RBAC ya resuelto
13. **Documento 18A** — Plan Maestro de Implementación de BD (incorporar fase RBAC al cronograma)
14. **Documento 01** — Prompt Maestro (agregar React/Superadministrador a tecnologías/roles reconocidos)
15. **Documento 22 / Anexo C** (03_Backend) — alinear con dominios Admin/Audit
16. **Documento 26** — Integraciones (agregar sección ERP)
17. **Documento 09** — Modelo Financiero (referenciar formalmente 33A)
18. **Documento 12** — Sistema Multinivel (agregar supervisión administrativa)
19. **Documento 24 / 25** — Realtime / APIs (referenciar 42A; documentar endpoints de Superadmin)
20. **Documento 13 / 15** — Trust Score / Motor Antifraude (nomenclatura device_registry; cruce con 42A)
21. **Documento 35 / 36** — Auditoría / Continuidad Operativa (referencias cruzadas; contingencia de portal React)
22. **Documento 30 / 28** — UI Kit / React (una vez resuelta la Fase 6 de clarificación de producto)
23. **Documento 37 / 38 / 39** — Testing (casos y validaciones de Superadministrador)
24. **Documento 40 / 41 / 42** — DevOps / CI-CD / Monitoreo (alinear con sus anexos 40A/41A/42A)
25. **Documento 43** — Operación (runbook de reapertura de período)
26. **Documento 04** — Roadmap Estratégico (verificación final de hitos, al cierre de todo lo anterior)
27. **Creación de documentos/anexos nuevos** (Sección 6) — al final, una vez estabilizado el modelo de roles

---

## Nota metodológica de cierre

Esta auditoría no reescribió ningún documento, no propuso tecnologías fuera de las ya aprobadas, y no modificó ninguna decisión arquitectónica existente — solo señaló dónde el árbol documental está internamente inconsistente respecto a sus propias decisiones ya aprobadas. Los 25 cambios arquitectónicos, en su gran mayoría, **ya están bien documentados** en la "Generación 2" (32, 32A, 33A, 34, 35, 40A, 41A, 42A); el trabajo pendiente real es de **propagación y consistencia** hacia la "Generación 1" (00-08, 16-19), no de diseño desde cero.
