\# Documento 38A — Casos de Prueba Financieros

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir los casos de prueba especializados para validar la integridad financiera de Tu Mobil Amigo.

Este documento complementa:

\- Documento 09 — Modelo Financiero  
\- Documento 10 — Motor Tarifario  
\- Documento 12 — Sistema Multinivel  
\- Documento 14 — IMF  
\- Documento 33 — Protección Financiera  
\- Documento 38 — Casos de Prueba

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ningún cálculo financiero deberá llegar a producción sin evidencia verificable de funcionamiento correcto.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Tarifas  
\- Cashback  
\- Multinivel  
\- Incentivos  
\- IMF  
\- Liquidaciones  
\- Conciliaciones  
\- Fondo de Reserva  
\- Reportes Financieros

\--------------------------------------------------  
4\. CRITERIOS DE ÉXITO  
\--------------------------------------------------

Toda prueba financiera deberá validar:

\`\`\`text  
Exactitud

Trazabilidad

Repetibilidad

Auditabilidad

No duplicidad  
\`\`\`

\--------------------------------------------------  
5\. MOTOR TARIFARIO  
\--------------------------------------------------

\#\#\# CPF-TAR-001

Tarifa mínima válida.

Resultado esperado:

Cálculo correcto.

\---

\#\#\# CPF-TAR-002

Tarifa máxima válida.

Resultado esperado:

Cálculo correcto.

\---

\#\#\# CPF-TAR-003

Ciudad sin parámetros.

Resultado esperado:

Operación bloqueada.

\---

\#\#\# CPF-TAR-004

Cambio de parámetros desde BD.

Resultado esperado:

Sin cambios de código.

\---

\#\#\# CPF-TAR-005

Cambio de tarifa durante operación activa.

Resultado esperado:

No afecta servicio ya creado.

\--------------------------------------------------  
6\. NEGOCIACIÓN  
\--------------------------------------------------

\#\#\# CPF-NEG-001

Oferta dentro de límites.

\---

\#\#\# CPF-NEG-002

Oferta fuera de límites.

Resultado esperado:

Rechazada.

\---

\#\#\# CPF-NEG-003

Contraoferta válida.

\---

\#\#\# CPF-NEG-004

Expiración de negociación.

\--------------------------------------------------  
7\. CASHBACK  
\--------------------------------------------------

\#\#\# CPF-CASH-001

Servicio inmediato.

Resultado esperado:

30%.

\---

\#\#\# CPF-CASH-002

Servicio programado.

Resultado esperado:

35%.

\---

\#\#\# CPF-CASH-003

Cancelación antes de finalizar.

Resultado esperado:

No genera cashback.

\---

\#\#\# CPF-CASH-004

Servicio anulado.

Resultado esperado:

Reverso completo.

\---

\#\#\# CPF-CASH-005

Intento de doble generación.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-CASH-006

Reprocesamiento del evento.

Resultado esperado:

No duplica valores.

\--------------------------------------------------  
8\. MULTINIVEL  
\--------------------------------------------------

\#\#\# CPF-MLM-001

Patrocinador Nivel 1 válido.

Resultado esperado:

20%.

\---

\#\#\# CPF-MLM-002

Patrocinador Nivel 2 válido.

Resultado esperado:

10%.

\---

\#\#\# CPF-MLM-003

Sin patrocinador.

Resultado esperado:

No genera distribución.

\---

\#\#\# CPF-MLM-004

Patrocinador suspendido.

Resultado esperado:

No recibe beneficio.

\---

\#\#\# CPF-MLM-005

Auto-referido.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-MLM-006

Cadena circular.

Resultado esperado:

Bloqueada.

\--------------------------------------------------  
9\. FONDO DE RESERVA  
\--------------------------------------------------

\#\#\# CPF-RES-001

Generación correcta.

Resultado esperado:

10%.

\---

\#\#\# CPF-RES-002

Acumulación histórica.

\---

\#\#\# CPF-RES-003

Consulta histórica.

\--------------------------------------------------  
10\. INCENTIVOS  
\--------------------------------------------------

\#\#\# CPF-INC-001

Generación correcta.

\---

\#\#\# CPF-INC-002

Maduración correcta.

\---

\#\#\# CPF-INC-003

Liquidación correcta.

\---

\#\#\# CPF-INC-004

Reverso autorizado.

\--------------------------------------------------  
11\. IMF  
\--------------------------------------------------

\#\#\# CPF-IMF-001

Cambio de nivel.

\---

\#\#\# CPF-IMF-002

Maduración correcta.

\---

\#\#\# CPF-IMF-003

No pérdida de historial.

\---

\#\#\# CPF-IMF-004

Intento de manipulación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
12\. BILLETERAS  
\--------------------------------------------------

\#\#\# CPF-WAL-001

Abono válido.

\---

\#\#\# CPF-WAL-002

Débito válido.

\---

\#\#\# CPF-WAL-003

Saldo insuficiente.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-WAL-004

Concurrencia simultánea.

Resultado esperado:

Consistencia garantizada.

\--------------------------------------------------  
13\. MOVIMIENTOS FINANCIEROS  
\--------------------------------------------------

\#\#\# CPF-MOV-001

Movimiento único.

\---

\#\#\# CPF-MOV-002

Movimiento duplicado.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-MOV-003

Movimiento revertido.

\---

\#\#\# CPF-MOV-004

Movimiento auditado.

\--------------------------------------------------  
14\. LIQUIDACIONES MENSUALES  
\--------------------------------------------------

\#\#\# CPF-LIQ-001

Generación automática.

\---

\#\#\# CPF-LIQ-002

Corte:

\`\`\`text  
Último día del mes  
23:59:59  
\`\`\`

\---

\#\#\# CPF-LIQ-003

Reporte Excel generado.

\---

\#\#\# CPF-LIQ-004

Discriminación correcta:

\- Cashback  
\- Multinivel  
\- Incentivos  
\- Totales

\---

\#\#\# CPF-LIQ-005

Auditoría generada.

\--------------------------------------------------  
15\. LIQUIDACIONES EXTRAORDINARIAS  
\--------------------------------------------------

\#\#\# CPF-LIQ-006

Liquidación individual.

\---

\#\#\# CPF-LIQ-007

Liquidación por ciudad.

\---

\#\#\# CPF-LIQ-008

Liquidación por grupo.

\---

\#\#\# CPF-LIQ-009

Sin afectar liquidaciones futuras.

\--------------------------------------------------  
16\. PAGOS  
\--------------------------------------------------

\#\#\# CPF-PAG-001

Pago aprobado.

\---

\#\#\# CPF-PAG-002

Pago rechazado.

\---

\#\#\# CPF-PAG-003

Pago duplicado.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-PAG-004

Pago auditado.

\--------------------------------------------------  
17\. CONCILIACIÓN  
\--------------------------------------------------

\#\#\# CPF-CON-001

Conciliación completa.

\---

\#\#\# CPF-CON-002

Diferencia detectada.

\---

\#\#\# CPF-CON-003

Reconciliación exitosa.

\--------------------------------------------------  
18\. REPORTES  
\--------------------------------------------------

\#\#\# CPF-REP-001

Excel mensual.

\---

\#\#\# CPF-REP-002

Exportación CSV.

\---

\#\#\# CPF-REP-003

Exportación PDF.

\---

\#\#\# CPF-REP-004

Totales coinciden con Base de Datos.

\--------------------------------------------------  
19\. RECUPERACIÓN  
\--------------------------------------------------

\#\#\# CPF-REC-001

Recuperación desde backup.

\---

\#\#\# CPF-REC-002

No pérdida financiera.

\---

\#\#\# CPF-REC-003

No duplicidad.

\--------------------------------------------------  
20\. CONCURRENCIA  
\--------------------------------------------------

\#\#\# CPF-CC-001

100 liquidaciones simultáneas.

\---

\#\#\# CPF-CC-002

1000 movimientos simultáneos.

\---

\#\#\# CPF-CC-003

Múltiples procesos de cálculo.

Resultado esperado:

Consistencia total.

\--------------------------------------------------  
21\. FRAUDE FINANCIERO  
\--------------------------------------------------

\#\#\# CPF-FRD-001

Manipulación de cashback.

\---

\#\#\# CPF-FRD-002

Manipulación de multinivel.

\---

\#\#\# CPF-FRD-003

Manipulación de liquidación.

\---

\#\#\# CPF-FRD-004

Manipulación de billetera.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
22\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

\#\#\# CPF-SGF-001

Aprobador ≠ Ejecutor.

\---

\#\#\# CPF-SGF-002

Ejecutor ≠ Pagador.

\---

\#\#\# CPF-SGF-003

Intento de bypass.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
23\. AUDITORÍA FINANCIERA  
\--------------------------------------------------

\#\#\# CPF-AUD-001

Todo movimiento genera auditoría.

\---

\#\#\# CPF-AUD-002

Toda liquidación genera auditoría.

\---

\#\#\# CPF-AUD-003

Todo pago genera auditoría.

\--------------------------------------------------  
24\. ESCENARIOS DE BORDE  
\--------------------------------------------------

Validar:

\- valores mínimos;  
\- valores máximos;  
\- cero movimientos;  
\- millones de movimientos;  
\- usuarios suspendidos;  
\- usuarios eliminados lógicamente.

\--------------------------------------------------  
25\. MATRIZ DE COBERTURA  
\--------------------------------------------------

Toda regla financiera deberá vincularse con:

\- caso de prueba;  
\- evidencia;  
\- resultado.

\--------------------------------------------------  
26\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Todo flujo financiero de Tu Mobil Amigo deberá demostrar exactitud matemática, trazabilidad completa, resistencia al fraude y consistencia transaccional antes de ser liberado a producción.  
