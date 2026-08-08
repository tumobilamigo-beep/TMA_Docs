\# Documento 42A — Catálogo de Alertas e Incidentes

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el catálogo oficial de alertas, incidentes, niveles de severidad, responsables, tiempos de respuesta y procedimientos de escalamiento para Tu Mobil Amigo.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo evento crítico deberá ser detectado, clasificado, notificado, atendido y auditado.

Ningún incidente crítico podrá quedar sin seguimiento.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Infraestructura;  
\- Base de Datos;  
\- APIs;  
\- Edge Functions;  
\- Realtime;  
\- Flutter;  
\- React;  
\- Seguridad;  
\- Antifraude;  
\- Liquidaciones;  
\- Integraciones.

\--------------------------------------------------  
4\. DEFINICIONES  
\--------------------------------------------------

Evento:

\`\`\`text  
Situación detectada por el sistema.  
\`\`\`

Alerta:

\`\`\`text  
Notificación generada por un evento.  
\`\`\`

Incidente:

\`\`\`text  
Evento que afecta  
la operación normal.  
\`\`\`

\--------------------------------------------------  
5\. CLASIFICACIÓN DE SEVERIDAD  
\--------------------------------------------------

Niveles oficiales:

\`\`\`text  
SEV-1

SEV-2

SEV-3

SEV-4  
\`\`\`

\--------------------------------------------------  
6\. SEV-1  
\--------------------------------------------------

Impacto crítico.

Características:

\- plataforma caída;  
\- pérdida financiera;  
\- fuga de datos;  
\- indisponibilidad total.

\--------------------------------------------------  
7\. SEV-2  
\--------------------------------------------------

Impacto alto.

Características:

\- funcionalidad crítica degradada;  
\- errores masivos;  
\- fallos operativos importantes.

\--------------------------------------------------  
8\. SEV-3  
\--------------------------------------------------

Impacto moderado.

Características:

\- afectación parcial;  
\- errores controlados.

\--------------------------------------------------  
9\. SEV-4  
\--------------------------------------------------

Impacto menor.

Características:

\- advertencias;  
\- comportamiento anómalo sin impacto inmediato.

\--------------------------------------------------  
10\. TIEMPOS OBJETIVO  
\--------------------------------------------------

\`\`\`text  
SEV-1 → inmediato

SEV-2 → \< 30 minutos

SEV-3 → \< 4 horas

SEV-4 → \< 24 horas  
\`\`\`

\--------------------------------------------------  
11\. RESPONSABLES  
\--------------------------------------------------

Podrán intervenir:

\`\`\`text  
Administrador

Superadministrador

Equipo Técnico

Equipo Financiero  
\`\`\`

\--------------------------------------------------  
12\. CANALES DE NOTIFICACIÓN  
\--------------------------------------------------

Inicialmente:

\`\`\`text  
Telegram

Correo electrónico

Dashboard Operativo  
\`\`\`

\--------------------------------------------------  
13\. REGISTRO OBLIGATORIO  
\--------------------------------------------------

Toda alerta deberá registrar:

\- fecha;  
\- origen;  
\- severidad;  
\- estado.

\--------------------------------------------------  
14\. ESTADOS DE INCIDENTE  
\--------------------------------------------------

\`\`\`text  
Abierto

En Investigación

Mitigado

Resuelto

Cerrado  
\`\`\`

\--------------------------------------------------  
15\. ALERTAS DE INFRAESTRUCTURA  
\--------------------------------------------------

\--------------------------------------------------  
16\. SERVICIO CAÍDO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

Acción:

Notificación inmediata.

\--------------------------------------------------  
17\. ALTO CONSUMO DE RECURSOS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
18\. FALLO DE RESPALDO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
19\. FALLA DE RESTAURACIÓN  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
20\. ALERTAS DE BASE DE DATOS  
\--------------------------------------------------

\--------------------------------------------------  
21\. CONEXIONES AGOTADAS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
22\. CONSULTAS LENTAS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
23\. BLOQUEOS ANÓMALOS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
24\. ERROR DE MIGRACIÓN  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
25\. ALERTAS DE EDGE FUNCTIONS  
\--------------------------------------------------

\--------------------------------------------------  
26\. ERROR REPETITIVO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
27\. FALLA DE EJECUCIÓN  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
28\. TIMEOUT EXCESIVO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
29\. ALERTAS DE REALTIME  
\--------------------------------------------------

\--------------------------------------------------  
30\. CANAL DESCONECTADO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
31\. RECONEXIONES MASIVAS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
32\. PÉRDIDA DE EVENTOS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
33\. ALERTAS DE SEGURIDAD  
\--------------------------------------------------

\--------------------------------------------------  
34\. INTENTOS DE FUERZA BRUTA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
35\. ACCESO NO AUTORIZADO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
36\. EXPOSICIÓN DE SECRETOS  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
37\. API KEY COMPROMETIDA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
38\. MODIFICACIÓN NO AUTORIZADA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
39\. ALERTAS ANTIFRAUDE  
\--------------------------------------------------

\--------------------------------------------------  
40\. MULTICUENTA SOSPECHOSA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
41\. ABUSO DE CASHBACK  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
42\. ABUSO MULTINIVEL  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
43\. MANIPULACIÓN DE DISPOSITIVO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
44\. ALERTAS FINANCIERAS  
\--------------------------------------------------

\--------------------------------------------------  
45\. DIFERENCIA EN CONCILIACIÓN  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
46\. LIQUIDACIÓN FALLIDA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
47\. REPORTE FINANCIERO NO GENERADO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
48\. PAGO DUPLICADO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
49\. PAGO SIN APROBACIÓN  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
50\. ALERTAS OPERATIVAS  
\--------------------------------------------------

\--------------------------------------------------  
51\. INTEGRACIÓN TELEGRAM FALLIDA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
52\. INTEGRACIÓN ERP FALLIDA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
53\. INTEGRACIÓN PSE FALLIDA  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
54\. ALERTAS GEOGRÁFICAS  
\--------------------------------------------------

\--------------------------------------------------  
55\. MAPTILER NO DISPONIBLE  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
56\. GRAPHHOPPER NO DISPONIBLE  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-2  
\`\`\`

\--------------------------------------------------  
57\. OPENSTREETMAP DEGRADADO  
\--------------------------------------------------

Severidad:

\`\`\`text  
SEV-3  
\`\`\`

\--------------------------------------------------  
58\. ESCALAMIENTO  
\--------------------------------------------------

Regla oficial:

\`\`\`text  
SEV-1

↓

Superadministrador  
\+  
Equipo Técnico  
\`\`\`

\--------------------------------------------------  
59\. ESCALAMIENTO FINANCIERO  
\--------------------------------------------------

Toda alerta financiera crítica deberá notificarse además al responsable financiero.

\--------------------------------------------------  
60\. ESCALAMIENTO DE SEGURIDAD  
\--------------------------------------------------

Toda alerta crítica de seguridad deberá notificarse inmediatamente.

\--------------------------------------------------  
61\. CIERRE DE INCIDENTES  
\--------------------------------------------------

Todo incidente deberá contener:

\- causa;  
\- solución;  
\- responsable.

\--------------------------------------------------  
62\. POSTMORTEM  
\--------------------------------------------------

Obligatorio para:

\`\`\`text  
SEV-1  
\`\`\`

\--------------------------------------------------  
63\. CONTENIDO DEL POSTMORTEM  
\--------------------------------------------------

Registrar:

\- qué ocurrió;  
\- impacto;  
\- causa raíz;  
\- corrección;  
\- prevención.

\--------------------------------------------------  
64\. HISTORIAL  
\--------------------------------------------------

Todas las alertas deberán conservarse.

\--------------------------------------------------  
65\. AUDITORÍA  
\--------------------------------------------------

Todo incidente deberá ser auditable.

\--------------------------------------------------  
66\. MÉTRICAS  
\--------------------------------------------------

Medir:

\- incidentes;  
\- severidad;  
\- frecuencia;  
\- resolución.

\--------------------------------------------------  
67\. KPI OPERATIVOS  
\--------------------------------------------------

Medir:

\- MTTR;  
\- tiempo de respuesta;  
\- incidentes recurrentes.

\--------------------------------------------------  
68\. MEJORA CONTINUA  
\--------------------------------------------------

Toda alerta recurrente deberá generar acción correctiva.

\--------------------------------------------------  
69\. EVOLUCIÓN  
\--------------------------------------------------

El catálogo deberá crecer junto con la plataforma.

\--------------------------------------------------  
70\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Todo evento crítico dentro de Tu Mobil Amigo deberá generar una respuesta controlada, auditable y escalable, garantizando que ningún riesgo operativo, financiero o de seguridad permanezca sin atención.  
