Documento 03 — Seguridad Maestra

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Establecer el marco de seguridad integral de Tu Mobil Amigo V1.0.

Este documento define los principios, controles y mecanismos obligatorios destinados a proteger:

Usuarios.  
Asesores.  
Información.  
Recursos financieros.  
Infraestructura tecnológica.  
Ecosistema comercial futuro.

La seguridad tendrá prioridad sobre la comodidad operativa cuando exista conflicto entre ambas.

2\. Principio Rector de Seguridad

Toda funcionalidad deberá responder obligatoriamente las siguientes preguntas:

¿Qué valor protege?  
¿Cómo puede ser atacada?  
¿Cómo puede ser abusada?  
¿Cómo puede auditarse?  
¿Cómo puede recuperarse?

Si alguna respuesta no existe, la funcionalidad no podrá aprobarse.

3\. Modelo de Defensa

Tu Mobil Amigo utilizará una estrategia de:

Defensa en Capas  
(Defense in Depth)

Ningún mecanismo individual será considerado suficiente.

Cada control deberá complementarse con controles adicionales.

4\. Activos Críticos

Los activos críticos del proyecto son:

Nivel 1

Críticos absolutos.

Identidad de usuarios.  
Billeteras.  
Beneficios financieros.  
Comisiones multinivel.  
Trust Score.  
IMF.  
Historial de servicios.  
Motor Antifraude.  
Nivel 2

Críticos operativos.

Servicios.  
Negociaciones.  
Ubicaciones.  
Dispositivos registrados.  
Auditorías.  
Nivel 3

Críticos estratégicos.

Información comercial.  
Métricas.  
Inteligencia de negocio.  
Ecosistema comercial futuro.

5\. Principio de Trazabilidad Total

Toda acción deberá quedar registrada.

Ejemplos:

Registro.  
Inicio de sesión.  
Cambio de dispositivo.  
Cambio de teléfono.  
Recargas.  
Solicitud de servicio.  
Negociación.  
Contraofertas.  
Finalización.  
Liberación de beneficios.  
Retiros.

Nada crítico podrá ejecutarse sin trazabilidad.

6\. Device Fingerprint

Cada dispositivo generará una huella digital.

La huella podrá incluir:

Modelo.  
Sistema operativo.  
Versión.  
Idioma.  
Resolución.  
Zona horaria.  
Identificadores permitidos legalmente.  
Patrones de uso.

Objetivo:

Detectar multicuentas  
y comportamiento anómalo.  
7\. Control de Dispositivos

Cada usuario tendrá un historial de dispositivos.

El sistema deberá registrar:

Dispositivo actual.  
Dispositivos anteriores.  
Fecha de cambio.  
Frecuencia de cambios.  
8\. Protección Contra Multicuentas

El sistema deberá detectar:

Un dispositivo con múltiples cuentas.  
Múltiples cuentas operando coordinadamente.  
Redes artificiales.  
Servicios simulados.

La detección no bloqueará automáticamente.

Generará eventos de riesgo para análisis.

9\. Seguridad de Identidad

Todo usuario tendrá:

UUID interno.  
Identidad única.  
Historial permanente.

La identidad nunca podrá reciclarse.

10\. Validación de Servicios

Todo servicio deberá ser validable.

La plataforma deberá detectar:

Servicios inexistentes.  
Servicios duplicados.  
Servicios simulados.  
Servicios circulares.  
11\. Prevención de Autobeneficio

Está prohibido:

cliente\_uuid \= asesor\_uuid

La regla aplica para:

Servicios digitales.  
Servicios QR.  
Cashback.  
Comisiones.  
Beneficios.  
12\. Seguridad del Sistema QR

Cada QR deberá:

Ser único.  
Ser verificable.  
Estar asociado a un UUID.  
Permitir auditoría.

El QR no contendrá información sensible visible.

13\. Protección de Billeteras

Todas las billeteras serán cerradas.

No existirán:

Transferencias entre usuarios.  
Cesión de beneficios.  
Venta de saldo.  
Intercambio de cashback.

Objetivo:

Reducir riesgos  
de lavado de activos.  
14\. Separación de Billeteras  
Cliente

Billetera única de beneficios.

Asesor

Dos billeteras independientes.

Bolsa Operativa

Utilizada para:

Recargas.  
Operación.  
Descuentos.  
Bolsa de Beneficios

Utilizada para:

Cashback.  
Comisiones.  
Beneficios.

Nunca podrán mezclarse.

15\. Saldo Operativo Mínimo

Todo asesor deberá mantener un saldo mínimo operativo.

Valor inicial:

$5.000 COP

Si el saldo cae por debajo del mínimo:

No recibe servicios.  
No acepta servicios.  
No aparece disponible.  
16\. Seguridad del Cashback

El cashback no podrá liberarse inmediatamente.

Se utilizarán mecanismos de:

Maduración.  
Trust Score.  
Actividad.  
Participación.  
17\. Seguridad de Comisiones

Las comisiones multinivel deberán originarse únicamente de:

Actividad real validada.

No podrán generarse por:

Referidos falsos.  
Servicios simulados.  
Actividad artificial.  
18\. Trust Score

Todo usuario tendrá una puntuación dinámica de confianza.

El Trust Score analizará:

Comportamiento.  
Actividad.  
Historial.  
Riesgo.  
Consistencia.

Nunca influirá sobre el valor tarifario.

19\. Índice de Maduración Financiera (IMF)

El IMF controlará:

Liberación de beneficios.  
Velocidad de maduración.  
Riesgo financiero.

Objetivo:

Premiar comportamiento legítimo.  
20\. Motor Antifraude

El sistema utilizará análisis conductual.

Detectará:

Patrones anormales.  
Redes sospechosas.  
Servicios ficticios.  
Manipulación de beneficios.  
Manipulación de reputación.  
21\. Riesgo Financiero

La plataforma deberá asumir que todo mecanismo económico puede ser utilizado indebidamente.

Por ello:

Toda recompensa será auditable.  
Todo beneficio será rastreable.  
Todo retiro será verificable.  
22\. Prevención de Lavado de Activos

La plataforma deberá minimizar riesgos mediante:

Identidad persistente.  
Billeteras cerradas.  
Historial completo.  
Actividad verificable.  
Maduración financiera.  
Trust Score.  
Motor Antifraude.  

23. Seguridad Operativa
Las herramientas de seguridad operativa se distribuyen según el nivel de privilegio (ver Documento 06 — DA-005 y Documento 28):
Administrador podrá:
Suspender usuarios.
Suspender dispositivos.
Bloquear operaciones puntuales.
Auditar movimientos.
Superadministrador podrá adicionalmente:
Congelar beneficios a nivel de billetera o de red.
Ejecutar reapertura de períodos contables (con justificación obligatoria — ver Documento 33A).
Ejecutar liquidaciones extraordinarias.
Modificar parámetros globales de seguridad y motores del sistema.
Toda acción administrativa, de cualquier nivel, deberá quedar registrada y ser atribuible de forma inequívoca al rol y al usuario que la ejecutó (ver Documento 35 — Auditoría de Superadministrador).

24\. Seguridad de Infraestructura

Toda infraestructura deberá implementar:

Control de acceso.  
Gestión de secretos.  
Registro de eventos.  
Copias de seguridad.  
Recuperación ante desastres.  
25\. Principio de Confianza Cero

La plataforma operará bajo modelo:

Zero Trust

Ningún usuario.

Ningún dispositivo.

Ninguna solicitud.

Será considerada confiable por defecto.

Toda interacción deberá validarse.

26\. Objetivo Final

Construir una plataforma donde el fraude sea:

Difícil de ejecutar.  
Fácil de detectar.  
Rápida de auditar.  
Costosa de repetir.

Manteniendo simultáneamente:

Seguridad  
\+  
Escalabilidad  
\+  
Trazabilidad  
\+  
Sostenibilidad Financiera

La implementación técnica detallada de los controles de ciberseguridad se desarrolla en el Documento 32 — Ciberseguridad.

Fin del Documento 03 — Seguridad Maestra  
