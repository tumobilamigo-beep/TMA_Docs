\# Documento 32 — Ciberseguridad

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el marco oficial de ciberseguridad para todo el ecosistema Tu Mobil Amigo.

Este documento establece los controles mínimos obligatorios para:

\- Flutter.  
\- React.  
\- Backend.  
\- PostgreSQL.  
\- Supabase.  
\- APIs.  
\- Integraciones.  
\- Infraestructura.

El objetivo es reducir la superficie de ataque y proteger:

\- Usuarios.  
\- Asesores.  
\- Empresa.  
\- Información financiera.  
\- Información operativa.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

La seguridad deberá implementarse por capas.

Ningún control individual será considerado suficiente.

Toda protección deberá asumir que otra capa podría fallar.

\--------------------------------------------------  
3\. SECURITY BY DESIGN  
\--------------------------------------------------

Toda funcionalidad deberá diseñarse considerando:

\- Confidencialidad.  
\- Integridad.  
\- Disponibilidad.  
\- Trazabilidad.  
\- No repudio.

Antes de desarrollar una funcionalidad deberá evaluarse su impacto en seguridad.

\--------------------------------------------------  
4\. ZERO TRUST  
\--------------------------------------------------

El sistema adoptará el principio:

Nunca confiar.  
Siempre verificar.

Toda solicitud deberá validarse independientemente.

\--------------------------------------------------  
5\. CAPAS DE SEGURIDAD  
\--------------------------------------------------

Se implementarán controles en:

\- Cliente Flutter.  
\- Portal React.  
\- API.  
\- Backend.  
\- Base de Datos.  
\- Infraestructura.  
\- Integraciones.

\--------------------------------------------------  
6\. PROTECCIÓN DE CREDENCIALES  
\--------------------------------------------------

Prohibido almacenar:

\- Passwords.  
\- Tokens.  
\- Secrets.  
\- API Keys.  
\- Service Keys.

en:

\- Flutter.  
\- React.  
\- Repositorios Git.

\--------------------------------------------------  
7\. GESTIÓN DE SECRETOS  
\--------------------------------------------------

Todos los secretos deberán almacenarse mediante:

\- Supabase Secrets.  
\- Variables de entorno.  
\- Secret Managers.

Nunca en código fuente.

\--------------------------------------------------  
8\. CONTROL DE ACCESO  
\--------------------------------------------------

Todo acceso deberá estar controlado mediante:

RBAC

Roles aprobados:

\- Cliente.  
\- Asesor.  
\- Administrador.  
\- Superadministrador.

\--------------------------------------------------  
9\. MENOR PRIVILEGIO  
\--------------------------------------------------

Todo usuario, proceso o servicio deberá operar con el mínimo privilegio necesario.

\--------------------------------------------------  
10\. AUTENTICACIÓN  
\--------------------------------------------------

Toda autenticación deberá realizarse mediante servicios oficiales aprobados.

Prohibido implementar mecanismos personalizados inseguros.

\--------------------------------------------------  
11\. CONTRASEÑAS  
\--------------------------------------------------

Las contraseñas nunca serán almacenadas en texto plano.

Deberán utilizar algoritmos modernos de hash administrados por el proveedor de identidad.

\--------------------------------------------------  
12\. MFA  
\--------------------------------------------------

Será obligatorio para:

\- Superadministrador.

Será configurable para:

\- Administrador.  
\- Asesor.

\--------------------------------------------------  
13\. PROTECCIÓN DE SESIONES  
\--------------------------------------------------

Las sesiones deberán contemplar:

\- expiración;  
\- renovación;  
\- invalidación;  
\- cierre remoto.

\--------------------------------------------------  
14\. PROTECCIÓN DE APIs  
\--------------------------------------------------

Toda API deberá validar:

\- autenticación;  
\- autorización;  
\- formato;  
\- origen;  
\- límites.

\--------------------------------------------------  
15\. RATE LIMITING  
\--------------------------------------------------

Se implementarán límites configurables para:

\- Login.  
\- Registro.  
\- Consultas.  
\- Operaciones financieras.

Todos los parámetros deberán almacenarse en Base de Datos.

\--------------------------------------------------  
16\. PROTECCIÓN CONTRA FUERZA BRUTA  
\--------------------------------------------------

El sistema deberá detectar:

\- intentos masivos;  
\- ataques automatizados;  
\- credenciales repetidas.

y aplicar bloqueos progresivos.

\--------------------------------------------------  
17\. PROTECCIÓN CONTRA ENUMERACIÓN  
\--------------------------------------------------

El sistema no deberá revelar:

\- existencia de usuarios;  
\- existencia de correos;  
\- existencia de teléfonos.

\--------------------------------------------------  
18\. PROTECCIÓN CONTRA BOTS  
\--------------------------------------------------

Se implementarán mecanismos de detección de automatización.

Incluyendo:

\- comportamiento anómalo;  
\- velocidad de solicitudes;  
\- reputación.

\--------------------------------------------------  
19\. PROTECCIÓN SQL  
\--------------------------------------------------

Queda prohibido:

\- SQL dinámico inseguro.  
\- Concatenación de consultas.  
\- Ejecución arbitraria.

\--------------------------------------------------  
20\. CONSULTAS PARAMETRIZADAS  
\--------------------------------------------------

Todas las consultas deberán utilizar:

\- parámetros;  
\- prepared statements;  
\- funciones controladas.

\--------------------------------------------------  
21\. ROW LEVEL SECURITY  
\--------------------------------------------------

RLS será obligatorio.

Ninguna tabla operativa podrá exponerse sin políticas explícitas.

\--------------------------------------------------  
22\. POLÍTICAS RLS  
\--------------------------------------------------

Toda política deberá documentar:

\- quién accede;  
\- qué accede;  
\- cuándo accede.

\--------------------------------------------------  
23\. PROTECCIÓN CONTRA INYECCIÓN  
\--------------------------------------------------

El sistema deberá proteger contra:

\- SQL Injection.  
\- Command Injection.  
\- NoSQL Injection.  
\- Template Injection.

\--------------------------------------------------  
24\. PROTECCIÓN XSS  
\--------------------------------------------------

Se deberán prevenir:

\- reflected XSS;  
\- stored XSS;  
\- DOM XSS.

\--------------------------------------------------  
25\. PROTECCIÓN CSRF  
\--------------------------------------------------

Toda operación sensible deberá protegerse contra CSRF cuando aplique.

\--------------------------------------------------  
26\. VALIDACIÓN DE ENTRADAS  
\--------------------------------------------------

Toda entrada deberá validarse:

\- Frontend.  
\- Backend.  
\- Base de Datos.

Nunca confiar en validaciones de cliente.

\--------------------------------------------------  
27\. VALIDACIÓN DE ARCHIVOS  
\--------------------------------------------------

Todo archivo deberá validar:

\- tipo;  
\- tamaño;  
\- contenido;  
\- extensión.

\--------------------------------------------------  
28\. PROTECCIÓN DE STORAGE  
\--------------------------------------------------

Todo acceso a Storage deberá realizarse mediante permisos controlados.

\--------------------------------------------------  
29\. CIFRADO EN TRÁNSITO  
\--------------------------------------------------

Todo tráfico deberá utilizar:

HTTPS

TLS

\--------------------------------------------------  
30\. CIFRADO EN REPOSO  
\--------------------------------------------------

Toda información sensible deberá utilizar los mecanismos de cifrado provistos por la plataforma.

\--------------------------------------------------  
31\. AUDITORÍA DE SEGURIDAD  
\--------------------------------------------------

Deberán registrarse:

\- logins;  
\- bloqueos;  
\- accesos;  
\- cambios críticos;  
\- operaciones financieras.

\--------------------------------------------------  
32\. DETECCIÓN DE ANOMALÍAS  
\--------------------------------------------------

El sistema deberá monitorear:

\- accesos inusuales;  
\- dispositivos nuevos;  
\- patrones sospechosos.

\--------------------------------------------------  
33\. SEGURIDAD DE DISPOSITIVOS  
\--------------------------------------------------

La gestión de dispositivos se complementará con:

Documento 34\.

\--------------------------------------------------  
34\. SEGURIDAD FINANCIERA  
\--------------------------------------------------

La protección financiera se complementará con:

Documento 33\.

\--------------------------------------------------  
35\. SEGURIDAD DE INTEGRACIONES  
\--------------------------------------------------

Toda integración deberá:

\- autenticarse;  
\- registrarse;  
\- auditarse.

\--------------------------------------------------  
36\. TELEGRAM  
\--------------------------------------------------

Las integraciones Telegram deberán validar:

\- origen;  
\- token;  
\- identidad.

\--------------------------------------------------  
37\. OPENSTREETMAP  
\--------------------------------------------------

No se almacenarán credenciales sensibles en cliente.

\--------------------------------------------------  
38\. GRAPHHOPPER  
\--------------------------------------------------

Las claves deberán gestionarse mediante Backend.

Nunca desde Flutter.

\--------------------------------------------------  
39\. GITHUB  
\--------------------------------------------------

Queda prohibido almacenar:

\- passwords;  
\- API Keys;  
\- tokens;  
\- secrets.

en repositorios.

\--------------------------------------------------  
40\. VERCEL  
\--------------------------------------------------

Toda configuración sensible deberá mantenerse mediante variables protegidas.

\--------------------------------------------------  
41\. SUPABASE  
\--------------------------------------------------

La Service Role Key nunca podrá exponerse públicamente.

\--------------------------------------------------  
42\. SEGURIDAD DE EDGE FUNCTIONS  
\--------------------------------------------------

Toda Edge Function deberá:

\- validar autenticación;  
\- validar autorización;  
\- registrar auditoría.

\--------------------------------------------------  
43\. SEGURIDAD DE REACT  
\--------------------------------------------------

React nunca contendrá:

\- lógica financiera;  
\- secretos;  
\- credenciales.

\--------------------------------------------------  
44\. SEGURIDAD DE FLUTTER  
\--------------------------------------------------

Flutter nunca contendrá:

\- claves privadas;  
\- secretos;  
\- reglas críticas de negocio.

\--------------------------------------------------  
45\. OWASP  
\--------------------------------------------------

Toda la plataforma deberá alinearse con:

OWASP Top 10

como estándar mínimo.

\--------------------------------------------------  
46\. PRUEBAS DE SEGURIDAD  
\--------------------------------------------------

Deberán realizarse:

\- revisión de código;  
\- análisis estático;  
\- análisis de dependencias;  
\- pruebas funcionales.

\--------------------------------------------------  
47\. DEPENDENCIAS  
\--------------------------------------------------

Toda dependencia deberá evaluarse antes de ser incorporada.

\--------------------------------------------------  
48\. VULNERABILIDADES  
\--------------------------------------------------

Las vulnerabilidades críticas deberán corregirse antes de despliegues productivos.

\--------------------------------------------------  
49\. RESPUESTA A INCIDENTES  
\--------------------------------------------------

Todo incidente deberá:

\- registrarse;  
\- clasificarse;  
\- investigarse;  
\- documentarse.

\--------------------------------------------------  
50\. MONITOREO  
\--------------------------------------------------

La seguridad deberá monitorearse continuamente.

\--------------------------------------------------  
51\. CONFIGURABILIDAD  
\--------------------------------------------------

Los umbrales de seguridad deberán almacenarse en Base de Datos.

Nunca hardcodeados.

\--------------------------------------------------  
52\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La seguridad no será una funcionalidad adicional del sistema.

Será una característica transversal obligatoria que deberá estar presente en todas las capas tecnológicas de Tu Mobil Amigo desde el diseño inicial hasta la operación en producción.  
