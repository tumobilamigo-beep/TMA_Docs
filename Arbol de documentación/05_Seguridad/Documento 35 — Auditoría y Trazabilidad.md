\# Documento 35 — Auditoría y Trazabilidad

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el sistema oficial de auditoría y trazabilidad de Tu Mobil Amigo.

Toda acción relevante ejecutada dentro del ecosistema deberá poder:

\- identificarse;  
\- reconstruirse;  
\- verificarse;  
\- auditarse.

La auditoría constituye la fuente oficial de evidencia operativa, financiera y de seguridad.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Toda acción relevante deberá dejar evidencia.  
Si una acción no puede auditarse:  
No debe existir.

\--------------------------------------------------  
3\. INMUTABILIDAD  
\--------------------------------------------------

Los registros de auditoría nunca deberán eliminarse.

Las correcciones deberán registrarse mediante nuevos eventos.

\--------------------------------------------------  
4\. TRAZABILIDAD COMPLETA  
\--------------------------------------------------

Toda operación deberá permitir identificar:

\- quién;  
\- cuándo;  
\- desde dónde;  
\- qué hizo;  
\- resultado obtenido.

\--------------------------------------------------  
5\. ALCANCE  
\--------------------------------------------------

La auditoría cubrirá:

\- Flutter;  
\- React;  
\- Backend;  
\- Base de Datos;  
\- APIs;  
\- Integraciones;  
\- Procesos automáticos.

\--------------------------------------------------  
6\. TABLA OFICIAL  
\--------------------------------------------------

La entidad principal será:

\`\`\`text  
audit\_logs  
\`\`\`

\--------------------------------------------------  
7\. ESTRUCTURA GENERAL  
\--------------------------------------------------

La tabla deberá registrar como mínimo:

\`\`\`sql  
id uuid

evento varchar(100)

categoria varchar(50)

usuario\_id uuid

dispositivo\_id uuid

ip inet

entidad varchar(100)

entidad\_id uuid

resultado varchar(30)

detalle jsonb

created\_at timestamp  
\`\`\`

\--------------------------------------------------  
8\. CATEGORÍAS OFICIALES  
\--------------------------------------------------

\`\`\`text  
AUTENTICACION

AUTORIZACION

FINANCIERO

SERVICIO

SEGURIDAD

ANTIFRAUDE

LIQUIDACION

ADMINISTRACION

CONFIGURACION

SISTEMA  
\`\`\`

\--------------------------------------------------  
9\. NIVELES DE SEVERIDAD  
\--------------------------------------------------

\`\`\`text  
INFO

WARNING

ERROR

CRITICO  
\`\`\`

\--------------------------------------------------  
10\. AUDITORÍA DE AUTENTICACIÓN  
\--------------------------------------------------

Registrar:

\- login;  
\- logout;  
\- recuperación;  
\- MFA;  
\- bloqueo.

\--------------------------------------------------  
11\. AUDITORÍA DE USUARIOS  
\--------------------------------------------------

Registrar:

\- creación;  
\- modificación;  
\- suspensión;  
\- eliminación lógica.

\--------------------------------------------------  
12\. AUDITORÍA DE ROLES  
\--------------------------------------------------

Registrar cambios de:

\- Cliente;  
\- Asesor;  
\- Administrador;  
\- Superadministrador.

\--------------------------------------------------  
13\. AUDITORÍA DE SERVICIOS  
\--------------------------------------------------

Registrar:

\- creación;  
\- aceptación;  
\- cancelación;  
\- finalización.

\--------------------------------------------------  
14\. AUDITORÍA DE NEGOCIACIÓN  
\--------------------------------------------------

Registrar:

\- ofertas;  
\- contraofertas;  
\- aceptación.

\--------------------------------------------------  
15\. AUDITORÍA DE TRUST  
\--------------------------------------------------

Registrar:

\- aumentos;  
\- disminuciones;  
\- recalculos.

\--------------------------------------------------  
16\. AUDITORÍA DE IMF  
\--------------------------------------------------

Registrar:

\- cambios de nivel;  
\- validaciones;  
\- bloqueos.

\--------------------------------------------------  
17\. AUDITORÍA DE CASHBACK  
\--------------------------------------------------

Registrar:

\- generación;  
\- reversos;  
\- ajustes.

\--------------------------------------------------  
18\. AUDITORÍA MULTINIVEL  
\--------------------------------------------------

Registrar:

\- generación;  
\- distribución;  
\- ajustes.

\--------------------------------------------------  
19\. AUDITORÍA DE INCENTIVOS  
\--------------------------------------------------

Registrar:

\- generación;  
\- aprobación;  
\- reverso.

\--------------------------------------------------  
20\. AUDITORÍA DE LIQUIDACIONES  
\--------------------------------------------------

Registrar:

\- simulación;  
\- aprobación;  
\- ejecución;  
\- pago;  
\- anulación.

\--------------------------------------------------  
21\. EVENTOS DE LIQUIDACIÓN  
\--------------------------------------------------

\`\`\`text  
LIQUIDACION\_SIMULADA

LIQUIDACION\_APROBADA

LIQUIDACION\_EJECUTADA

LIQUIDACION\_PAGADA

LIQUIDACION\_ANULADA  
\`\`\`

\--------------------------------------------------  
22\. AUDITORÍA DE PAGOS  
\--------------------------------------------------

Registrar:

\- pagos realizados;  
\- pagos rechazados;  
\- pagos revertidos.

\--------------------------------------------------  
23\. AUDITORÍA DE DISPOSITIVOS  
\--------------------------------------------------

Registrar:

\- registro;  
\- bloqueo;  
\- desbloqueo;  
\- cambios relevantes.

\--------------------------------------------------  
24\. AUDITORÍA DE SEGURIDAD  
\--------------------------------------------------

Registrar:

\- intentos fallidos;  
\- accesos sospechosos;  
\- VPN;  
\- Proxy;  
\- TOR.

\--------------------------------------------------  
25\. AUDITORÍA DE CONFIGURACIÓN  
\--------------------------------------------------

Toda modificación de parámetros deberá registrarse.

\--------------------------------------------------  
26\. AUDITORÍA DE TARIFAS  
\--------------------------------------------------

Registrar:

\- creación;  
\- modificación;  
\- activación;  
\- desactivación.

\--------------------------------------------------  
27\. AUDITORÍA DE CIUDADES  
\--------------------------------------------------

Registrar:

\- creación;  
\- activación;  
\- suspensión.

\--------------------------------------------------  
28\. AUDITORÍA DE INTEGRACIONES  
\--------------------------------------------------

Registrar:

\- consumo;  
\- error;  
\- timeout;  
\- reconexión.

\--------------------------------------------------  
29\. AUDITORÍA DE API  
\--------------------------------------------------

Registrar:

\- acceso;  
\- error;  
\- rechazo.

\--------------------------------------------------  
30\. AUDITORÍA DE EDGE FUNCTIONS  
\--------------------------------------------------

Toda Edge Function deberá generar trazabilidad.

\--------------------------------------------------  
31\. AUDITORÍA DE PROCESOS AUTOMÁTICOS  
\--------------------------------------------------

Registrar:

\- jobs;  
\- schedulers;  
\- liquidaciones automáticas;  
\- conciliaciones.

\--------------------------------------------------  
32\. AUDITORÍA DE EXPORTACIONES  
\--------------------------------------------------

Registrar:

\- Excel;  
\- CSV;  
\- PDF.

\--------------------------------------------------  
33\. AUDITORÍA DE ADMINISTRADORES  
\--------------------------------------------------

Toda acción administrativa deberá registrarse.

\--------------------------------------------------  
34\. AUDITORÍA DE SUPERADMINISTRADOR  
\--------------------------------------------------

Toda acción deberá considerarse crítica.

No existirán excepciones.

\--------------------------------------------------  
35\. AUDITORÍA DE CAMBIOS MASIVOS  
\--------------------------------------------------

Toda operación masiva deberá registrar:

\- alcance;  
\- cantidad de registros;  
\- operador.

\--------------------------------------------------  
36\. AUDITORÍA DE ERRORES  
\--------------------------------------------------

Registrar:

\- excepciones;  
\- errores de integración;  
\- errores financieros.

\--------------------------------------------------  
37\. AUDITORÍA DE BASE DE DATOS  
\--------------------------------------------------

Registrar eventos críticos sobre:

\- tablas;  
\- funciones;  
\- triggers;  
\- configuraciones.

\--------------------------------------------------  
38\. RETENCIÓN  
\--------------------------------------------------

Los registros deberán conservarse según políticas definidas por la empresa y la normativa aplicable.

\--------------------------------------------------  
39\. CONSULTA DE AUDITORÍA  
\--------------------------------------------------

La información deberá ser:

\- filtrable;  
\- exportable;  
\- trazable.

\--------------------------------------------------  
40\. BÚSQUEDA AVANZADA  
\--------------------------------------------------

Permitir filtros por:

\- usuario;  
\- fecha;  
\- evento;  
\- categoría;  
\- entidad.

\--------------------------------------------------  
41\. EXPORTACIÓN  
\--------------------------------------------------

La auditoría deberá soportar:

\- Excel;  
\- CSV;  
\- PDF.

\--------------------------------------------------  
42\. PROTECCIÓN  
\--------------------------------------------------

Los registros de auditoría no podrán modificarse desde Flutter o React.

\--------------------------------------------------  
43\. CONTROL DE ACCESO  
\--------------------------------------------------

Solo usuarios autorizados podrán consultar auditoría.

\--------------------------------------------------  
44\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

La consulta de auditoría no implica permiso de modificación.

\--------------------------------------------------  
45\. RELACIÓN CON SEGURIDAD  
\--------------------------------------------------

Complementa:

Documento 32 — Ciberseguridad.

\--------------------------------------------------  
46\. RELACIÓN CON ANTIFRAUDE  
\--------------------------------------------------

Complementa:

Documento 15 — Motor Antifraude.

\--------------------------------------------------  
47\. RELACIÓN CON PROTECCIÓN FINANCIERA  
\--------------------------------------------------

Complementa:

Documento 33 — Protección Financiera.

\--------------------------------------------------  
48\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura deberá soportar:

\- cientos de millones de eventos;  
\- múltiples países;  
\- múltiples años de operación.

\--------------------------------------------------  
49\. OBSERVABILIDAD  
\--------------------------------------------------

La auditoría será uno de los pilares de monitoreo y análisis operativo.

\--------------------------------------------------  
50\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda acción relevante dentro de Tu Mobil Amigo deberá poder reconstruirse completa y cronológicamente mediante evidencia auditable, garantizando trazabilidad operativa, financiera, legal y de seguridad durante todo el ciclo de vida del sistema.  
