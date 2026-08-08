Documento 34 — Gestión de Dispositivos

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el modelo oficial de identificación, control, monitoreo y protección de dispositivos utilizados dentro del ecosistema Tu Mobil Amigo.

La gestión de dispositivos constituye una capa fundamental para:

\- Seguridad.  
\- Trust Score.  
\- Antifraude.  
\- Protección financiera.  
\- Control de cuentas.  
\- Prevención de abuso del sistema.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

La confianza no se otorgará únicamente al usuario.

También deberá evaluarse el dispositivo desde el cual opera.

\--------------------------------------------------  
3\. IDENTIDAD DIGITAL DEL DISPOSITIVO  
\--------------------------------------------------

Cada dispositivo deberá poseer una identidad única dentro del sistema.

Dicha identidad será utilizada para:

\- análisis de riesgo;  
\- prevención de fraude;  
\- auditoría;  
\- monitoreo.

\--------------------------------------------------  
4\. DEVICE FINGERPRINT  
\--------------------------------------------------

El sistema generará un Device Fingerprint utilizando múltiples atributos.

Ejemplos:

\- modelo;  
\- fabricante;  
\- sistema operativo;  
\- versión;  
\- resolución;  
\- zona horaria;  
\- idioma;  
\- identificadores permitidos por plataforma.

\--------------------------------------------------  
5\. PRINCIPIO DE PRIVACIDAD  
\--------------------------------------------------

La recolección de información deberá respetar:

\- legislación vigente;  
\- protección de datos;  
\- privacidad del usuario.

No se recopilará información prohibida por la plataforma o la ley.

\--------------------------------------------------  
6\. REGISTRO DE DISPOSITIVOS  
\--------------------------------------------------

Todo acceso autenticado deberá asociarse a un dispositivo registrado.

\--------------------------------------------------  
7\. TABLA OFICIAL  
\--------------------------------------------------

La entidad oficial será:

\`\`\`text  
device\_registry  
\`\`\`

Definida en la Base de Datos.

\--------------------------------------------------  
8\. ESTADO DEL DISPOSITIVO  
\--------------------------------------------------

Todo dispositivo tendrá un estado.

Estados permitidos:

\`\`\`text  
ACTIVO

SUSPENDIDO

BLOQUEADO

OBSERVACION  
\`\`\`

\--------------------------------------------------  
9\. HISTORIAL DE ACCESO  
\--------------------------------------------------

El sistema deberá registrar:

\- fecha;  
\- hora;  
\- IP;  
\- ubicación aproximada;  
\- resultado del acceso.

\--------------------------------------------------  
10\. NUEVO DISPOSITIVO  
\--------------------------------------------------

Cuando un usuario acceda desde un dispositivo desconocido:

\- deberá registrarse;  
\- deberá auditarse;  
\- podrá incrementar el riesgo antifraude.

\--------------------------------------------------  
11\. DISPOSITIVOS MÚLTIPLES  
\--------------------------------------------------

Un usuario podrá utilizar múltiples dispositivos.

La cantidad máxima deberá ser configurable desde Base de Datos.

\--------------------------------------------------  
12\. LÍMITES OPERATIVOS  
\--------------------------------------------------

Parámetros configurables:

\- dispositivos por usuario;  
\- dispositivos nuevos por día;  
\- cambios por período.

\--------------------------------------------------  
13\. CAMBIO FRECUENTE DE DISPOSITIVO  
\--------------------------------------------------

Cambios excesivos podrán generar:

\- alertas;  
\- disminución temporal de Trust;  
\- revisión antifraude.

\--------------------------------------------------  
14\. CUENTAS MÚLTIPLES  
\--------------------------------------------------

El sistema deberá detectar patrones compatibles con:

\- multicuentas;  
\- abuso de incentivos;  
\- fraude de referidos.

\--------------------------------------------------  
15\. RELACIÓN CON TRUST SCORE  
\--------------------------------------------------

El historial del dispositivo podrá afectar positivamente o negativamente el Trust Score.

\--------------------------------------------------  
16\. RELACIÓN CON IMF  
\--------------------------------------------------

La gestión de dispositivos no alterará directamente el IMF.

Sin embargo podrá generar restricciones operativas cuando existan riesgos elevados.

\--------------------------------------------------  
17\. RELACIÓN CON ANTIFRAUDE  
\--------------------------------------------------

Todo evento relevante deberá ser enviado al Motor Antifraude.

\--------------------------------------------------  
18\. DETECCIÓN DE PATRONES ANÓMALOS  
\--------------------------------------------------

Ejemplos:

\- múltiples usuarios en un mismo dispositivo;  
\- múltiples dispositivos en corto tiempo;  
\- actividad automatizada;  
\- actividad inconsistente.

\--------------------------------------------------  
19\. CONTROL DE IP  
\--------------------------------------------------

El sistema deberá registrar IP histórica.

La IP no será utilizada como único criterio de bloqueo.

\--------------------------------------------------  
20\. GEOLOCALIZACIÓN APROXIMADA  
\--------------------------------------------------

Se podrá registrar:

\- ciudad;  
\- región;  
\- país.

Con fines:

\- operativos;  
\- estadísticos;  
\- antifraude.

\--------------------------------------------------  
21\. VPN Y PROXYS  
\--------------------------------------------------

El sistema podrá detectar:

\- VPN;  
\- Proxy;  
\- Datacenter IP;  
\- Tor.

Como variables de riesgo.

\--------------------------------------------------  
22\. REPUTACIÓN DEL DISPOSITIVO  
\--------------------------------------------------

Cada dispositivo podrá poseer un indicador interno de reputación.

\--------------------------------------------------  
23\. SCORE DEL DISPOSITIVO  
\--------------------------------------------------

El sistema podrá calcular:

\`\`\`text  
Device Trust Score  
\`\`\`

para uso interno del Motor Antifraude.

\--------------------------------------------------  
24\. BLOQUEO PREVENTIVO  
\--------------------------------------------------

Dispositivos de alto riesgo podrán:

\- restringirse;  
\- suspenderse;  
\- requerir validación adicional.

\--------------------------------------------------  
25\. DISPOSITIVOS COMPROMETIDOS  
\--------------------------------------------------

Ante sospecha de compromiso:

\- invalidar sesiones;  
\- solicitar reautenticación;  
\- registrar auditoría.

\--------------------------------------------------  
26\. CONTROL DE SESIONES  
\--------------------------------------------------

Toda sesión deberá asociarse a:

\- usuario;  
\- dispositivo;  
\- fecha de inicio.

\--------------------------------------------------  
27\. SESIONES CONCURRENTES  
\--------------------------------------------------

El número máximo de sesiones concurrentes deberá ser configurable.

\--------------------------------------------------  
28\. CIERRE REMOTO  
\--------------------------------------------------

El usuario podrá cerrar sesiones activas desde otros dispositivos.

\--------------------------------------------------  
29\. MFA ADAPTATIVO  
\--------------------------------------------------

El sistema podrá requerir autenticación adicional cuando:

\- cambie el dispositivo;  
\- cambie la ubicación;  
\- aumente el riesgo.

\--------------------------------------------------  
30\. AUDITORÍA  
\--------------------------------------------------

Todo evento relevante deberá registrarse.

\--------------------------------------------------  
31\. EVENTOS AUDITABLES  
\--------------------------------------------------

Como mínimo:

\- registro;  
\- activación;  
\- suspensión;  
\- bloqueo;  
\- desbloqueo;  
\- acceso.

\--------------------------------------------------  
32\. NOTIFICACIONES DE SEGURIDAD  
\--------------------------------------------------

El sistema podrá notificar:

\- nuevo dispositivo;  
\- inicio sospechoso;  
\- bloqueo preventivo.

\--------------------------------------------------  
33\. PROTECCIÓN DE INCENTIVOS  
\--------------------------------------------------

La gestión de dispositivos deberá contribuir a prevenir:

\- fraude de cashback;  
\- fraude multinivel;  
\- abuso de incentivos.

\--------------------------------------------------  
34\. PROTECCIÓN DE REFERIDOS  
\--------------------------------------------------

No podrá utilizarse un mismo dispositivo para generar artificialmente estructuras de referidos.

\--------------------------------------------------  
35\. PROTECCIÓN DE LIQUIDACIONES  
\--------------------------------------------------

Eventos de alto riesgo podrán impedir temporalmente liquidaciones extraordinarias hasta revisión administrativa.

\--------------------------------------------------  
36\. MONITOREO  
\--------------------------------------------------

Los dispositivos deberán monitorearse continuamente.

\--------------------------------------------------  
37\. CONFIGURABILIDAD  
\--------------------------------------------------

Todos los umbrales deberán almacenarse en Base de Datos.

Nunca hardcodeados.

\--------------------------------------------------  
38\. INTEGRACIÓN CON SEGURIDAD  
\--------------------------------------------------

Este documento complementa:

Documento 32 — Ciberseguridad.

\--------------------------------------------------  
39\. INTEGRACIÓN CON ANTIFRAUDE  
\--------------------------------------------------

Este documento complementa:

Documento 15 — Motor Antifraude.

\--------------------------------------------------  
40\. INTEGRACIÓN CON TRUST  
\--------------------------------------------------

Este documento complementa:

Documento 13 — Trust Score.

\--------------------------------------------------  
41\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura deberá soportar:

\- millones de dispositivos;  
\- múltiples ciudades;  
\- múltiples países.

sin rediseño estructural.

\--------------------------------------------------  
42\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La gestión de dispositivos deberá proporcionar una capa adicional de confianza operativa que permita identificar comportamientos legítimos, detectar patrones sospechosos y proteger el ecosistema financiero y operativo de Tu Mobil Amigo frente a fraude, abuso y accesos no autorizados.  
