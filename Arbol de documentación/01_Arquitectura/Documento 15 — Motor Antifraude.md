Documento 15 — Motor Antifraude

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

El Motor Antifraude es el sistema encargado de identificar, prevenir, contener y registrar comportamientos que representen riesgos para la operación, la seguridad, la estabilidad financiera o la legalidad del ecosistema Tu Mobil Amigo.  
Su función no es castigar usuarios.  
Su función es:  
Detectar riesgos.  
Proteger usuarios.  
Proteger asesores.  
Proteger la red multinivel.  
Proteger el cashback.  
Proteger las billeteras.  
Proteger la sostenibilidad financiera.

2\. Principios Fundamentales

AF-01 — Presunción de Buena Fe  
Todo usuario será considerado legítimo hasta que existan evidencias suficientes de comportamiento anómalo.

AF-02 — Riesgo Acumulativo  
Un único evento aislado no deberá provocar sanciones automáticas.  
El sistema evaluará patrones.

AF-03 — Evidencia Digital  
Toda alerta deberá estar sustentada por evidencia trazable.

AF-04 — Escalabilidad  
Las reglas deberán funcionar para:  
100 usuarios.  
10.000 usuarios.  
100.000 usuarios.  
1.000.000 usuarios.  
Múltiples ciudades.  
Sin modificaciones estructurales.

3\. Arquitectura General

El Motor Antifraude estará compuesto por:  
Módulo de Identidad  
Módulo de Dispositivos  
Módulo Operativo  
Módulo Financiero  
Módulo Multinivel  
Módulo QR  
Módulo de Auditoría

4\. Niveles de Riesgo

Nivel	Riesgo  
0	Sin riesgo  
1	Riesgo Bajo  
2	Riesgo Medio  
3	Riesgo Alto  
4	Riesgo Crítico

5\. Módulo de Identidad  
Evalúa:  
Documento de identidad.  
Coincidencia de datos.  
Duplicidad de registros.  
Inconsistencias de información.  
Alertas:  
Documento duplicado.  
Teléfono duplicado.  
Correo duplicado.  
Identidad sospechosa.

6\. Módulo de Dispositivos  
Evalúa:  
Dispositivo principal.  
Cambios frecuentes.  
Huella digital del dispositivo.  
Historial de acceso.  
Variables sugeridas:  
UUID dispositivo  
Modelo  
Sistema operativo  
Versión App  
IP histórica  
Zona horaria  
Patrones de conexión

7\. Módulo Dispositivo Confiable  
Todo usuario tendrá un dispositivo principal.  
Los cambios frecuentes aumentarán el riesgo.

8\. Módulo Operativo  
Evalúa:  
Servicios solicitados.  
Servicios completados.  
Cancelaciones.  
Negociaciones.  
Alertas:  
Cancelaciones masivas.  
Servicios simulados.  
Comportamiento coordinado.

9\. Módulo de Negociación  
Evalúa:  
Contraofertas repetitivas.  
Negociaciones artificiales.  
Patrones de manipulación.  
El sistema deberá identificar:  
Cliente A  
↓  
Asesor B  
↓  
Mismo patrón repetitivo

10\. Módulo Financiero  
Evalúa:  
Recargas.  
Retiros.  
Liberaciones IMF.  
Comisiones.  
Cashback.  
Alertas:  
Movimientos anormales.  
Crecimiento acelerado.  
Patrones incompatibles con la actividad.

11\. Módulo Multinivel  
Evalúa:  
Crecimiento de red.  
Calidad de referidos.  
Concentración de actividad.  
Alertas:  
Auto patrocinio.  
Redes artificiales.  
Estructuras coordinadas.

12\. Módulo QR  
Evalúa:  
Uso de QR.  
Servicios de calle.  
Frecuencia.  
Repetición de usuarios.  
Alertas:  
Servicios QR ficticios.  
Clientes repetitivos.  
Montos anormales.  
Incentivos QR artificiales.

13\. Servicios Espejo  
Se consideran de alto riesgo los patrones donde:  
Cliente A  
↓  
Asesor B

Cliente A  
↓  
Asesor B

Cliente A  
↓  
Asesor B

durante periodos prolongados sin variación operativa razonable.

14\. Módulo de Geolocalización  
Evalúa:  
Distancias recorridas.  
Ubicaciones frecuentes.  
Consistencia operacional.  
Alertas:  
Servicios físicamente imposibles.  
Cambios instantáneos de ubicación.  
Operación simultánea incompatible.

15\. Integración con Trust Score  
El Motor Antifraude alimentará el Trust Score.  
Podrá:  
Reducir puntajes.  
Limitar beneficios.  
Generar observaciones.  
No podrá:  
Modificar tarifas.  
Alterar negociaciones.

16\. Integración con IMF  
Las alertas podrán:  
Congelar beneficios.  
Suspender liberaciones.  
Requerir revisión.

17\. Eventos Críticos  
Se consideran críticos:  
Suplantación.  
Documentación falsa.  
Multiplicidad de cuentas.  
Fraude financiero.  
Manipulación deliberada.

18\. Sistema de Puntuación de Riesgo  
Cada evento generará una puntuación.

Ejemplo conceptual:  
Evento	Riesgo  
Cambio de dispositivo	\+5  
Teléfono duplicado	\+15  
Servicio sospechoso	\+20  
QR fraudulento		\+25  
Identidad falsa		\+50

19\. Acciones Automáticas  
Según el nivel de riesgo:

Riesgo Bajo  
Monitoreo.

Riesgo Medio  
Observación reforzada.

Riesgo Alto  
Restricción temporal.

Riesgo Crítico  
Congelamiento preventivo.  
Revisión manual.

20\. Auditoría Obligatoria  
Toda acción del motor deberá generar:  
Fecha  
Usuario  
Evento  
Origen  
Nivel de riesgo  
Acción aplicada

21\. Conservación de Evidencia  
La evidencia deberá conservarse para:  
Auditoría interna.  
Cumplimiento normativo.  
Investigación de fraude.

22\. Prevención de Lavado de Activos  
El motor deberá identificar:  
Actividad económica inconsistente.  
Redes financieras artificiales.  
Movimientos incompatibles con el perfil del usuario.  
Acumulaciones anormales de beneficios.

23\. Cumplimiento Normativo  
El Motor Antifraude deberá alinearse con:  
Legislación colombiana vigente.  
Protección de datos.  
Normativa financiera aplicable.  
Requisitos de prevención de fraude.  
Requisitos de prevención de lavado de activos.

24.Fuente de Señales

Device Fingerprint  
Device Trust Score  
VPN Detection  
Proxy Detection  
Device Reputation  
 

25\. Principio Rector Final  
La confianza se presume.  
El fraude se investiga.  
La evidencia decide.

Toda acción del Motor Antifraude deberá estar sustentada por información verificable, trazable y auditable.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 15 — Motor Antifraude  
