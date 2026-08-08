\# Documento 38 — Casos de Prueba

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir los casos de prueba oficiales que permitirán validar funcionalmente, operativamente, financieramente y técnicamente el ecosistema Tu Mobil Amigo.

Este documento transforma las reglas de negocio aprobadas en escenarios verificables.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Toda regla de negocio deberá tener al menos un caso de prueba asociado.

Toda funcionalidad crítica deberá tener múltiples escenarios de validación.

\--------------------------------------------------  
3\. ESTRUCTURA ESTÁNDAR  
\--------------------------------------------------

Cada caso de prueba deberá contener:

\`\`\`text  
ID

Nombre

Objetivo

Precondiciones

Pasos

Resultado Esperado

Prioridad

Estado  
\`\`\`

\--------------------------------------------------  
4\. CLASIFICACIÓN  
\--------------------------------------------------

Los casos de prueba se clasifican en:

\`\`\`text  
FUNCIONAL

NEGOCIO

FINANCIERO

SEGURIDAD

INTEGRACIÓN

RENDIMIENTO

RECUPERACIÓN  
\`\`\`

\--------------------------------------------------  
5\. CASOS DE AUTENTICACIÓN  
\--------------------------------------------------

\#\#\# CP-AUT-001

Login válido.

Resultado esperado:

Acceso exitoso.

\---

\#\#\# CP-AUT-002

Contraseña incorrecta.

Resultado esperado:

Acceso denegado.

\---

\#\#\# CP-AUT-003

Usuario suspendido.

Resultado esperado:

Acceso bloqueado.

\---

\#\#\# CP-AUT-004

MFA exitoso.

Resultado esperado:

Acceso autorizado.

\---

\#\#\# CP-AUT-005

MFA inválido.

Resultado esperado:

Acceso denegado.

\--------------------------------------------------  
6\. CASOS DE ROLES  
\--------------------------------------------------

\#\#\# CP-ROL-001

Cliente accede únicamente a recursos de cliente.

\---

\#\#\# CP-ROL-002

Asesor accede únicamente a recursos de asesor.

\---

\#\#\# CP-ROL-003

Administrador accede únicamente a recursos administrativos.

\---

\#\#\# CP-ROL-004

Superadministrador posee acceso total autorizado.

\---

\#\#\# CP-ROL-005

Intento de escalamiento de privilegios.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
7\. CASOS DE SERVICIOS  
\--------------------------------------------------

\#\#\# CP-SRV-001

Crear servicio inmediato.

\---

\#\#\# CP-SRV-002

Crear servicio programado.

\---

\#\#\# CP-SRV-003

Cancelar servicio.

\---

\#\#\# CP-SRV-004

Finalizar servicio.

\---

\#\#\# CP-SRV-005

Servicio expirado.

\--------------------------------------------------  
8\. CASOS DE NEGOCIACIÓN  
\--------------------------------------------------

\#\#\# CP-NEG-001

Oferta válida.

\---

\#\#\# CP-NEG-002

Contraoferta válida.

\---

\#\#\# CP-NEG-003

Aceptación de oferta.

\---

\#\#\# CP-NEG-004

Expiración de oferta.

\---

\#\#\# CP-NEG-005

Oferta fuera de límites permitidos.

Resultado esperado:

Rechazada.

\--------------------------------------------------  
9\. CASOS DE MOTOR TARIFARIO  
\--------------------------------------------------

\#\#\# CP-TAR-001

Cálculo correcto de tarifa.

\---

\#\#\# CP-TAR-002

Aplicación correcta de variables por ciudad.

\---

\#\#\# CP-TAR-003

Cambio de parámetros sin modificación de código.

\---

\#\#\# CP-TAR-004

Validación de límites mínimos.

\---

\#\#\# CP-TAR-005

Validación de límites máximos.

\--------------------------------------------------  
10\. CASOS DE TRUST SCORE  
\--------------------------------------------------

\#\#\# CP-TRUST-001

Incremento por operación exitosa.

\---

\#\#\# CP-TRUST-002

Disminución por cancelación.

\---

\#\#\# CP-TRUST-003

Límite inferior.

\---

\#\#\# CP-TRUST-004

Límite superior.

\---

\#\#\# CP-TRUST-005

Recalculo completo.

\--------------------------------------------------  
11\. CASOS DE IMF  
\--------------------------------------------------

\#\#\# CP-IMF-001

Maduración correcta.

\---

\#\#\# CP-IMF-002

Cambio de nivel.

\---

\#\#\# CP-IMF-003

Validación de restricciones.

\---

\#\#\# CP-IMF-004

Liquidación anticipada.

Resultado esperado:

No altera IMF.

\--------------------------------------------------  
12\. CASOS DE CASHBACK  
\--------------------------------------------------

\#\#\# CP-CASH-001

Generación correcta.

\---

\#\#\# CP-CASH-002

Servicio programado.

Resultado esperado:

35%.

\---

\#\#\# CP-CASH-003

Servicio inmediato.

Resultado esperado:

30%.

\---

\#\#\# CP-CASH-004

Reverso.

\---

\#\#\# CP-CASH-005

Ajuste manual.

\--------------------------------------------------  
13\. CASOS MULTINIVEL  
\--------------------------------------------------

\#\#\# CP-MLM-001

Distribución Nivel 1\.

\---

\#\#\# CP-MLM-002

Distribución Nivel 2\.

\---

\#\#\# CP-MLM-003

Sin patrocinador elegible.

\---

\#\#\# CP-MLM-004

Patrocinador suspendido.

\---

\#\#\# CP-MLM-005

Validación legal del esquema.

\--------------------------------------------------  
14\. CASOS DE INCENTIVOS  
\--------------------------------------------------

\#\#\# CP-INC-001

Generación de incentivo.

\---

\#\#\# CP-INC-002

Maduración correcta.

\---

\#\#\# CP-INC-003

Liquidación.

\---

\#\#\# CP-INC-004

Reverso.

\--------------------------------------------------  
15\. CASOS DE LIQUIDACIONES  
\--------------------------------------------------

\#\#\# CP-LIQ-001

Generación de simulación.

\---

\#\#\# CP-LIQ-002

Aprobación.

\---

\#\#\# CP-LIQ-003

Ejecución.

\---

\#\#\# CP-LIQ-004

Pago.

\---

\#\#\# CP-LIQ-005

Anulación.

\---

\#\#\# CP-LIQ-006

Liquidación extraordinaria por usuario.

\---

\#\#\# CP-LIQ-007

Liquidación extraordinaria por ciudad.

\---

\#\#\# CP-LIQ-008

Intento de ejecutar sin aprobación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
16\. CASOS DE AUDITORÍA  
\--------------------------------------------------

\#\#\# CP-AUD-001

Registro de login.

\---

\#\#\# CP-AUD-002

Registro financiero.

\---

\#\#\# CP-AUD-003

Registro administrativo.

\---

\#\#\# CP-AUD-004

Registro de liquidación.

\--------------------------------------------------  
17\. CASOS DE DISPOSITIVOS  
\--------------------------------------------------

\#\#\# CP-DEV-001

Registro de nuevo dispositivo.

\---

\#\#\# CP-DEV-002

Cambio frecuente de dispositivo.

\---

\#\#\# CP-DEV-003

VPN detectada.

\---

\#\#\# CP-DEV-004

Proxy detectado.

\---

\#\#\# CP-DEV-005

Dispositivo bloqueado.

\--------------------------------------------------  
18\. CASOS ANTIFRAUDE  
\--------------------------------------------------

\#\#\# CP-AF-001

Multicuenta.

\---

\#\#\# CP-AF-002

Abuso de incentivos.

\---

\#\#\# CP-AF-003

Patrones sospechosos.

\---

\#\#\# CP-AF-004

Manipulación de ubicación.

\--------------------------------------------------  
19\. CASOS DE SEGURIDAD  
\--------------------------------------------------

\#\#\# CP-SEC-001

SQL Injection.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-002

XSS.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-003

CSRF.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-004

Acceso sin autenticación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
20\. CASOS DE APIs  
\--------------------------------------------------

\#\#\# CP-API-001

Solicitud válida.

\---

\#\#\# CP-API-002

Token inválido.

\---

\#\#\# CP-API-003

Permiso insuficiente.

\---

\#\#\# CP-API-004

Rate limit excedido.

\--------------------------------------------------  
21\. CASOS DE REALTIME  
\--------------------------------------------------

\#\#\# CP-RT-001

Recepción de evento.

\---

\#\#\# CP-RT-002

Reconexión automática.

\---

\#\#\# CP-RT-003

Recuperación tras desconexión.

\--------------------------------------------------  
22\. CASOS DE OPENSTREETMAP  
\--------------------------------------------------

\#\#\# CP-MAP-001

Obtención de coordenadas.

\---

\#\#\# CP-MAP-002

Ruta válida.

\---

\#\#\# CP-MAP-003

Falla temporal del proveedor.

Resultado esperado:

Degradación controlada.

\--------------------------------------------------  
23\. CASOS DE INTEGRACIONES  
\--------------------------------------------------

\#\#\# CP-INT-001

Telegram disponible.

\---

\#\#\# CP-INT-002

Telegram no disponible.

\---

\#\#\# CP-INT-003

ERP futuro disponible.

\--------------------------------------------------  
24\. CASOS DE REPORTES  
\--------------------------------------------------

\#\#\# CP-REP-001

Excel mensual generado.

\---

\#\#\# CP-REP-002

CSV generado.

\---

\#\#\# CP-REP-003

PDF generado.

\--------------------------------------------------  
25\. CASOS DE CONTINUIDAD OPERATIVA  
\--------------------------------------------------

\#\#\# CP-CO-001

Caída de integración.

\---

\#\#\# CP-CO-002

Caída de Realtime.

\---

\#\#\# CP-CO-003

Recuperación de Base de Datos.

\---

\#\#\# CP-CO-004

Restauración desde backup.

\--------------------------------------------------  
26\. CASOS DE CONCURRENCIA  
\--------------------------------------------------

\#\#\# CP-CON-001

100 usuarios simultáneos.

\---

\#\#\# CP-CON-002

500 usuarios simultáneos.

\---

\#\#\# CP-CON-003

Múltiples ofertas simultáneas.

\--------------------------------------------------  
27\. CASOS DE EXPORTACIÓN  
\--------------------------------------------------

\#\#\# CP-EXP-001

Excel correcto.

\---

\#\#\# CP-EXP-002

CSV correcto.

\---

\#\#\# CP-EXP-003

PDF correcto.

\--------------------------------------------------  
28\. MATRIZ DE COBERTURA  
\--------------------------------------------------

Todo requisito deberá vincularse con:

\- caso de prueba;  
\- resultado;  
\- evidencia.

\--------------------------------------------------  
29\. TRAZABILIDAD  
\--------------------------------------------------

Toda ejecución deberá generar evidencia auditable.

\--------------------------------------------------  
30\. CP-SA-001:  
\--------------------------------------------------
 Superadministrador ejecuta reapertura de período con justificación → período recalculado, evidencia conservada, evento auditado.
 
\--------------------------------------------------  
31\. CP-SA-002:  
\-------------------------------------------------- 
Superadministrador intenta reapertura sin justificación → operación rechazada.

\--------------------------------------------------  
32\. CP-SA-003:  
\--------------------------------------------------
Administrador intenta ejecutar reapertura de período → operación rechazada por falta de permiso (403).

\--------------------------------------------------  
33\. CP-SA-004:  
\--------------------------------------------------
Superadministrador ejecuta liquidación extraordinaria → visible solo para Superadministrador, registrada en Centro de Liquidaciones (ver Documento 28, Sección 39).

\--------------------------------------------------  
34\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Ninguna funcionalidad de Tu Mobil Amigo podrá considerarse aprobada hasta que los casos de prueba asociados hayan sido ejecutados, documentados y validados satisfactoriamente.  
