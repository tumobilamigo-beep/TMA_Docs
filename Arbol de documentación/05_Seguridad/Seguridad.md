Seguridad

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

Fin de Documento 32 — Ciberseguridad

\# Documento 32A — Gestión de Secretos y Credenciales

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir las políticas, procedimientos y controles para la gestión segura de secretos, credenciales, llaves, certificados y configuraciones sensibles utilizadas por Tu Mobil Amigo.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ningún secreto deberá estar expuesto en código fuente, repositorios, aplicaciones cliente o documentación pública.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Flutter Cliente;  
\- Flutter Asesor;  
\- React Administrador;  
\- React Superadministrador;  
\- Supabase;  
\- PostgreSQL;  
\- Edge Functions;  
\- APIs;  
\- Integraciones;  
\- Infraestructura.

\--------------------------------------------------  
4\. ACTIVOS PROTEGIDOS  
\--------------------------------------------------

Se consideran secretos:

\- contraseñas;  
\- API Keys;  
\- Tokens;  
\- JWT Secrets;  
\- Certificados;  
\- Llaves privadas;  
\- Credenciales de servicios;  
\- Webhooks protegidos;  
\- Claves de cifrado.

\--------------------------------------------------  
5\. CLASIFICACIÓN  
\--------------------------------------------------

Clasificación oficial:

\`\`\`text  
Crítico

Alto

Medio

Bajo  
\`\`\`

\--------------------------------------------------  
6\. SECRETOS CRÍTICOS  
\--------------------------------------------------

Incluyen:

\- claves maestras;  
\- llaves de cifrado;  
\- credenciales de producción;  
\- claves privadas.

\--------------------------------------------------  
7\. SECRETOS DE ALTO IMPACTO  
\--------------------------------------------------

Incluyen:

\- API Keys externas;  
\- Tokens administrativos;  
\- Integraciones financieras.

\--------------------------------------------------  
8\. ALMACENAMIENTO  
\--------------------------------------------------

Los secretos deberán almacenarse exclusivamente en mecanismos seguros.

\--------------------------------------------------  
9\. PROHIBICIONES  
\--------------------------------------------------

Prohibido almacenar secretos en:

\`\`\`text  
Código fuente

GitHub

GitLab

Bitbucket

Archivos públicos

Documentación pública  
\`\`\`

\--------------------------------------------------  
10\. HARDCODEO  
\--------------------------------------------------

Queda prohibido hardcodear:

\- contraseñas;  
\- API Keys;  
\- tokens;  
\- secretos.

\--------------------------------------------------  
11\. VARIABLES DE ENTORNO  
\--------------------------------------------------

Toda configuración sensible deberá utilizar variables de entorno.

\--------------------------------------------------  
12\. SEPARACIÓN POR ENTORNO  
\--------------------------------------------------

Cada entorno tendrá secretos independientes:

\`\`\`text  
Local

Desarrollo

Staging

Producción  
\`\`\`

\--------------------------------------------------  
13\. REUTILIZACIÓN  
\--------------------------------------------------

Prohibido reutilizar credenciales entre entornos.

\--------------------------------------------------  
14\. GESTIÓN DE SUPABASE  
\--------------------------------------------------

Las credenciales Supabase deberán gestionarse de forma independiente.

\--------------------------------------------------  
15\. SERVICE ROLE KEY  
\--------------------------------------------------

La Service Role Key nunca podrá exponerse al frontend.

\--------------------------------------------------  
16\. ANON KEY  
\--------------------------------------------------

La Anon Key podrá utilizarse únicamente según diseño oficial de Supabase.

\--------------------------------------------------  
17\. EDGE FUNCTIONS  
\--------------------------------------------------

Las Edge Functions accederán a secretos mediante almacenamiento seguro.

\--------------------------------------------------  
18\. FLUTTER  
\--------------------------------------------------

Flutter nunca deberá contener secretos críticos.

\--------------------------------------------------  
19\. REACT  
\--------------------------------------------------

React nunca deberá contener secretos críticos.

\--------------------------------------------------  
20\. OPENSTREETMAP  
\--------------------------------------------------

Las configuraciones deberán mantenerse separadas del código.

\--------------------------------------------------  
21\. MAPTILER  
\--------------------------------------------------

Las API Keys deberán mantenerse protegidas.

\--------------------------------------------------  
22\. GRAPHHOPPER  
\--------------------------------------------------

Las API Keys deberán mantenerse protegidas y rotables.

\--------------------------------------------------  
23\. TELEGRAM  
\--------------------------------------------------

Los tokens de bots deberán considerarse secretos críticos.

\--------------------------------------------------  
24\. ERP FUTURO  
\--------------------------------------------------

Las credenciales ERP deberán almacenarse de forma independiente.

\--------------------------------------------------  
25\. PSE FUTURO  
\--------------------------------------------------

Las credenciales financieras deberán clasificarse como críticas.

\--------------------------------------------------  
26\. CIFRADO  
\--------------------------------------------------

Los secretos almacenados deberán permanecer cifrados.

\--------------------------------------------------  
27\. ROTACIÓN  
\--------------------------------------------------

Todo secreto deberá poder rotarse.

\--------------------------------------------------  
28\. ROTACIÓN PROGRAMADA  
\--------------------------------------------------

Se recomienda rotación periódica.

\--------------------------------------------------  
29\. ROTACIÓN EXTRAORDINARIA  
\--------------------------------------------------

Será obligatoria ante:

\- sospecha de exposición;  
\- incidente;  
\- fuga.

\--------------------------------------------------  
30\. ACCESO  
\--------------------------------------------------

Aplicar principio de mínimo privilegio.

\--------------------------------------------------  
31\. CONTROL DE ACCESO  
\--------------------------------------------------

Solo personal autorizado podrá acceder a secretos.

\--------------------------------------------------  
32\. AUDITORÍA  
\--------------------------------------------------

Todo acceso deberá registrarse.

\--------------------------------------------------  
33\. TRAZABILIDAD  
\--------------------------------------------------

Registrar:

\- usuario;  
\- fecha;  
\- acción;  
\- resultado.

\--------------------------------------------------  
34\. PIPELINES CI/CD  
\--------------------------------------------------

Los pipelines nunca deberán exponer secretos en logs.

\--------------------------------------------------  
35\. LOGS  
\--------------------------------------------------

Prohibido registrar:

\- contraseñas;  
\- tokens;  
\- secretos;  
\- credenciales.

\--------------------------------------------------  
36\. EXPORTACIONES  
\--------------------------------------------------

Prohibido incluir secretos en:

\- Excel;  
\- PDF;  
\- CSV;  
\- reportes.

\--------------------------------------------------  
37\. BACKUPS  
\--------------------------------------------------

Los secretos deberán mantenerse protegidos en respaldos.

\--------------------------------------------------  
38\. RECUPERACIÓN  
\--------------------------------------------------

Los procedimientos de recuperación deberán proteger credenciales.

\--------------------------------------------------  
39\. DETECCIÓN DE EXPOSICIÓN  
\--------------------------------------------------

Los pipelines deberán buscar:

\- API Keys;  
\- Tokens;  
\- Contraseñas;  
\- Certificados.

\--------------------------------------------------  
40\. BLOQUEO AUTOMÁTICO  
\--------------------------------------------------

La detección de secretos deberá detener el despliegue.

\--------------------------------------------------  
41\. INCIDENTES  
\--------------------------------------------------

Toda exposición deberá generar incidente de seguridad.

\--------------------------------------------------  
42\. REVOCACIÓN  
\--------------------------------------------------

Los secretos comprometidos deberán revocarse inmediatamente.

\--------------------------------------------------  
43\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

El administrador de infraestructura no necesariamente deberá conocer todos los secretos.

\--------------------------------------------------  
44\. DOCUMENTACIÓN  
\--------------------------------------------------

La documentación nunca deberá contener credenciales reales.

\--------------------------------------------------  
45\. EJEMPLOS  
\--------------------------------------------------

Toda documentación utilizará:

\`\`\`text  
\<API\_KEY\>

\<SECRET\>

\<TOKEN\>

\<PASSWORD\>  
\`\`\`

\--------------------------------------------------  
46\. PRUEBAS  
\--------------------------------------------------

Las pruebas utilizarán credenciales no productivas.

\--------------------------------------------------  
47\. ENTORNOS TEMPORALES  
\--------------------------------------------------

Los entornos temporales deberán utilizar credenciales independientes.

\--------------------------------------------------  
48\. CUMPLIMIENTO  
\--------------------------------------------------

La gestión de secretos deberá cumplir políticas internas de seguridad.

\--------------------------------------------------  
49\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia deberá adaptarse a nuevas tecnologías e integraciones.

\--------------------------------------------------  
50\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda credencial, secreto o llave utilizada por Tu Mobil Amigo deberá permanecer protegida, auditada, rotable y aislada, evitando que una exposición individual comprometa la seguridad global de la plataforma.  

Fin de Documento 32A — Gestión de Secretos y Credenciales

Documento 33 — Protección Financiera

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir los controles de protección financiera que garantizarán la integridad económica del ecosistema Tu Mobil Amigo.

Este documento protege:

\- Empresa.  
\- Clientes.  
\- Asesores.  
\- Red Multinivel.  
\- Fondo de Reserva.  
\- Cashback.  
\- Liquidaciones.  
\- Trust.  
\- IMF.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo movimiento económico deberá ser:

\- Trazable.  
\- Auditable.  
\- Reproducible.  
\- Verificable.

No podrán existir movimientos financieros sin evidencia registrable.

\--------------------------------------------------  
3\. PRINCIPIO DE INMUTABILIDAD  
\--------------------------------------------------

Ninguna transacción financiera podrá eliminarse.

Las correcciones se realizarán mediante:

\- reversos;  
\- ajustes;  
\- compensaciones.

Siempre conservando historial.

\--------------------------------------------------  
4\. LIBRO MAYOR FINANCIERO  
\--------------------------------------------------

Toda operación económica deberá generar registros en un libro mayor financiero.  
El libro mayor será la fuente oficial de verdad financiera.

\--------------------------------------------------  
5\. DOBLE VALIDACIÓN  
\--------------------------------------------------

Toda operación crítica deberá validarse:

\- en Backend;  
\- en Base de Datos.

Nunca exclusivamente en Frontend.

\--------------------------------------------------  
6\. PROHIBICIÓN DE CÁLCULOS EN CLIENTE  
\--------------------------------------------------

Flutter y React no podrán calcular:

\- cashback;  
\- multinivel;  
\- IMF;  
\- liquidaciones;  
\- incentivos.

Todo cálculo deberá ejecutarse en Backend y Base de Datos.

\--------------------------------------------------  
7\. CONFIGURACIÓN DESDE BASE DE DATOS  
\--------------------------------------------------

Toda variable económica deberá residir en Base de Datos.

Prohibido hardcodear:

\- porcentajes;  
\- límites;  
\- comisiones;  
\- incentivos.

\--------------------------------------------------  
8\. MOTOR ECONÓMICO CENTRALIZADO  
\--------------------------------------------------

Las reglas económicas deberán ejecutarse desde:

\- funciones PostgreSQL;  
\- servicios Backend autorizados.

\--------------------------------------------------  
9\. SEGREGACIÓN DE FONDOS  
\--------------------------------------------------

El sistema deberá diferenciar conceptualmente:

\- ingresos empresa;  
\- cashback;  
\- multinivel;  
\- reserva;  
\- incentivos.

\--------------------------------------------------  
10\. DISTRIBUCIÓN OFICIAL  
\--------------------------------------------------

La distribución aprobada será:

Empresa:  
30%

Cashback Cliente:  
30%

Upline Nivel 1:  
20%

Upline Nivel 2:  
10%

Fondo Reserva:  
10%

\--------------------------------------------------  
11\. SERVICIOS PROGRAMADOS  
\--------------------------------------------------

Para servicios programados:

Empresa:  
25%

Cashback Cliente:  
35%

Upline Nivel 1:  
20%

Upline Nivel 2:  
10%

Reserva:  
10%

El incremento de cashback será financiado exclusivamente desde la participación de la empresa.

\--------------------------------------------------  
12\. INCENTIVO ASESOR CALLE  
\--------------------------------------------------

Los incentivos de captación en calle deberán:

\- configurarse desde Base de Datos;  
\- entrar al esquema IMF;  
\- ser auditables.

Nunca podrán afectar directamente:

\- cashback;  
\- multinivel;  
\- fondo de reserva.

\--------------------------------------------------  
13\. PROTECCIÓN DE COMISIONES  
\--------------------------------------------------

Las comisiones deberán generarse únicamente sobre:  
servicios finalizados válidos.

\--------------------------------------------------  
14\. VALIDACIÓN DE SERVICIO  
\--------------------------------------------------

Antes de cualquier liquidación deberán validarse:

\- estado finalizado;  
\- integridad de datos;  
\- elegibilidad financiera.

\--------------------------------------------------  
15\. PROHIBICIÓN DE DUPLICIDAD  
\--------------------------------------------------

Ningún evento económico podrá procesarse dos veces.

\--------------------------------------------------  
16\. IDEMPOTENCIA  
\--------------------------------------------------

Toda operación financiera deberá ser idempotente.  
La repetición accidental no podrá generar pagos duplicados.

\--------------------------------------------------  
17\. CONTROL DE CONCURRENCIA  
\--------------------------------------------------

Las operaciones financieras deberán protegerse contra:

\- doble ejecución;  
\- carreras de concurrencia;  
\- inconsistencias transaccionales.

\--------------------------------------------------  
18\. TRANSACCIONES ACID  
\--------------------------------------------------

Toda operación económica deberá ejecutarse mediante transacciones ACID.

\--------------------------------------------------  
19\. CONTROL DE SALDOS  
\--------------------------------------------------

Ningún saldo podrá quedar negativo salvo reglas explícitamente aprobadas.

\--------------------------------------------------  
20\. PROTECCIÓN DE WALLET  
\--------------------------------------------------

Toda modificación de wallet deberá:

\- registrarse;  
\- auditarse;  
\- versionarse.

\--------------------------------------------------  
21\. CONTROL DE RETIROS  
\--------------------------------------------------

Los retiros deberán validar:

\- identidad;  
\- Trust;  
\- IMF;  
\- elegibilidad.

\--------------------------------------------------  
22\. CONTROL DE RECARGAS  
\--------------------------------------------------

Toda recarga deberá:

\- verificarse;  
\- registrarse;  
\- conciliarse.

\--------------------------------------------------  
23\. CONCILIACIÓN FINANCIERA  
\--------------------------------------------------

El sistema deberá soportar conciliación entre:

\- transacciones;  
\- wallets;  
\- liquidaciones;  
\- pagos realizados.

\--------------------------------------------------  
24\. DETECCIÓN DE ANOMALÍAS  
\--------------------------------------------------

El sistema deberá detectar:

\- incrementos atípicos;  
\- acumulaciones anormales;  
\- patrones sospechosos.

\--------------------------------------------------  
25\. LÍMITES OPERATIVOS  
\--------------------------------------------------

Todos los límites económicos deberán ser configurables desde Base de Datos.

\--------------------------------------------------  
26\. CONTROL DE CASHBACK  
\--------------------------------------------------

El cashback deberá:

\- calcularse automáticamente;  
\- registrarse individualmente;  
\- mantenerse pendiente hasta liquidación.

\--------------------------------------------------  
27\. CONTROL MULTINIVEL  
\--------------------------------------------------

Las comisiones multinivel deberán:

\- ser trazables;  
\- ser explicables;  
\- poder reconstruirse.

\--------------------------------------------------  
28\. CUMPLIMIENTO LEGAL  
\--------------------------------------------------

El sistema multinivel deberá operar conforme a:

\- legislación vigente;  
\- regulación comercial;  
\- regulación tributaria;  
\- normativa de protección al consumidor.

\--------------------------------------------------  
29\. PROHIBICIÓN DE PIRÁMIDES  
\--------------------------------------------------

Las recompensas deberán originarse exclusivamente de actividad económica real.  
Nunca de aportes de afiliación.

\--------------------------------------------------  
30\. AUDITORÍA ECONÓMICA  
\--------------------------------------------------

Todo cálculo deberá poder auditarse posteriormente.

\--------------------------------------------------  
31\. HISTÓRICO FINANCIERO  
\--------------------------------------------------

El sistema conservará historial completo.  
No se eliminarán registros financieros.

\--------------------------------------------------  
32\. LIQUIDACIÓN MENSUAL  
\--------------------------------------------------

La liquidación oficial se realizará:  
Último día del mes  
23:59:59

## **32A. Liquidación Manual Extraordinaria**

El sistema deberá permitir liquidaciones manuales controladas por:

Superadministrador

o perfiles autorizados específicamente.

La liquidación manual podrá ejecutarse:

* por usuario;  
* por grupo de usuarios;  
* por ciudad;  
* por rango de fechas;  
* por concepto financiero.

---

## **32B. Casos Permitidos**

Ejemplos:

* retiro voluntario;  
* cierre de cuenta;  
* corrección operativa;  
* contingencia tecnológica;  
* incidente de producción;  
* orden judicial;  
* auditoría extraordinaria;  
* cierre de operación local.

---

## **32C. Auditoría Obligatoria**

Toda liquidación manual deberá registrar:

* operador;  
* fecha;  
* hora;  
* motivo;  
* usuario afectado;  
* evidencia.

---

## **32D. Prohibición**

No podrá modificarse una liquidación ya pagada.

Las correcciones deberán realizarse mediante:

Ajustes  
Compensaciones  
Reversos

\--------------------------------------------------  
33\. CORTE FINANCIERO  
\--------------------------------------------------

El sistema deberá congelar los valores correspondientes al periodo liquidado.

\--------------------------------------------------  
34\. REPORTE OFICIAL  
\--------------------------------------------------

Automáticamente deberá generarse:  
Liquidación Mensual Oficial  
en formato Excel.

\--------------------------------------------------  
35\. CONTENIDO DEL REPORTE  
\--------------------------------------------------

Como mínimo:

\- usuario;  
\- ciudad;  
\- cashback;  
\- nivel 1;  
\- nivel 2;  
\- incentivos;  
\- total a pagar.

\--------------------------------------------------  
36\. ESTADO DE PAGO  
\--------------------------------------------------

Los registros deberán diferenciar:

\- pendiente;  
\- procesado;  
\- pagado.

\--------------------------------------------------  
37\. VENTANA OPERATIVA DE PAGO  
\--------------------------------------------------

La empresa dispondrá de:

5 días calendario

para ejecutar pagos.

\--------------------------------------------------  
38\. TRAZABILIDAD DE PAGOS  
\--------------------------------------------------

Todo pago deberá registrar:

\- fecha;  
\- valor;  
\- operador;  
\- evidencia.

\--------------------------------------------------  
39\. REVERSOS  
\--------------------------------------------------

Todo reverso deberá:

\- justificarse;  
\- auditarse;  
\- registrarse.

\--------------------------------------------------  
40\. PROTECCIÓN DEL FONDO DE RESERVA  
\--------------------------------------------------

El fondo de reserva deberá mantenerse completamente separado de los demás conceptos financieros.

\--------------------------------------------------  
41\. ERP FUTURO  
\--------------------------------------------------

La arquitectura deberá permitir integración futura con:

\- Siigo;  
\- Alegra;  
\- Odoo;  
\- SAP Business One;  
\- World Office.

\--------------------------------------------------  
42\. EXPORTACIONES  
\--------------------------------------------------

El sistema deberá soportar:

\- Excel;  
\- CSV;  
\- PDF.

\--------------------------------------------------  
43\. SEGURIDAD FINANCIERA  
\--------------------------------------------------

Toda operación económica deberá cumplir:

Documento 32 — Ciberseguridad.

\--------------------------------------------------  
44\. AUDITORÍA  
\--------------------------------------------------

Toda operación económica deberá cumplir:

Documento 35 — Auditoría y Trazabilidad.

\--------------------------------------------------  
45\. MONITOREO  
\--------------------------------------------------

Las operaciones económicas deberán monitorearse continuamente.

\--------------------------------------------------  
46\. RECUPERACIÓN  
\--------------------------------------------------

Toda información financiera deberá poder recuperarse ante incidentes.

\--------------------------------------------------  
47\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura financiera deberá soportar:

\- nuevas ciudades;  
\- nuevos países;  
\- nuevas monedas;  
\- nuevos servicios.

sin rediseño estructural.

\--------------------------------------------------  
48\. Liquidaciones en Dos Fases  
\--------------------------------------------------

Toda liquidación deberá ejecutarse mediante:

Simulación  
\+  
Aprobación  
\+  
Ejecución

Nunca directamente.

La gestión de liquidaciones se soportará mediante las entidades:  
 \- liquidaciones   
\- liquidacion\_detalles   
\- liquidacion\_auditoria 

\--------------------------------------------------  
49\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La protección financiera de Tu Mobil Amigo deberá garantizar que cada peso procesado por el ecosistema sea trazable, auditable, verificable y legalmente sustentable, evitando pérdidas económicas, fraude interno, fraude externo y errores operativos que comprometan la sostenibilidad del negocio.  

Fin de Documento 33 — Protección Financiera

\# Documento 33A — Conciliación Financiera y Cierre Contable

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el proceso oficial de conciliación financiera, validación de liquidaciones, cierre mensual y control contable de Tu Mobil Amigo.

Este documento garantiza que los valores generados por cashback, multinivel, incentivos y demás obligaciones financieras sean consistentes, auditables y verificables antes de cualquier desembolso.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ningún pago deberá ejecutarse sin haber sido conciliado, validado y aprobado.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Cashback;  
\- Multinivel Nivel 1;  
\- Multinivel Nivel 2;  
\- Incentivos futuros;  
\- Bonificaciones futuras;  
\- Pagos extraordinarios;  
\- Liquidaciones manuales;  
\- Liquidaciones automáticas.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- exactitud financiera;  
\- trazabilidad;  
\- auditoría;  
\- prevención de fraude;  
\- consistencia contable.

\--------------------------------------------------  
5\. CICLO FINANCIERO OFICIAL  
\--------------------------------------------------

\`\`\`text  
Generación  
      ↓

Liquidación  
      ↓

Conciliación  
      ↓

Aprobación  
      ↓

Pago  
      ↓

Cierre  
\`\`\`

\--------------------------------------------------  
6\. PERÍODO CONTABLE  
\--------------------------------------------------

El período oficial será:

\`\`\`text  
Mensual  
\`\`\`

\--------------------------------------------------  
7\. FECHA DE CORTE  
\--------------------------------------------------

El sistema realizará corte oficial:

\`\`\`text  
Último día del mes  
23:59:59  
\`\`\`

\--------------------------------------------------  
8\. GENERACIÓN AUTOMÁTICA  
\--------------------------------------------------

El sistema deberá ejecutar automáticamente el cierre financiero mensual.

\--------------------------------------------------  
9\. BLOQUEO DEL PERÍODO  
\--------------------------------------------------

Una vez generado el cierre:

\`\`\`text  
No podrán modificarse  
movimientos del período cerrado.  
\`\`\`

salvo mediante procedimiento extraordinario autorizado.

\--------------------------------------------------  
10\. LIQUIDACIÓN  
\--------------------------------------------------

La liquidación consolidará:

\- cashback;  
\- multinivel;  
\- incentivos;  
\- ajustes autorizados.

\--------------------------------------------------  
11\. FUENTE DE VERDAD  
\--------------------------------------------------

La única fuente válida será la base de datos oficial.

\--------------------------------------------------  
12\. PROCESO DE CONCILIACIÓN  
\--------------------------------------------------

El sistema deberá verificar:

\- movimientos generados;  
\- movimientos liquidados;  
\- movimientos pendientes.

\--------------------------------------------------  
13\. VALIDACIÓN DE CONSISTENCIA  
\--------------------------------------------------

Deberá comprobar:

\`\`\`text  
Total generado

\=

Total liquidado

\+

Total pendiente  
\`\`\`

\--------------------------------------------------  
14\. DIFERENCIAS  
\--------------------------------------------------

Toda diferencia deberá generar alerta.

\--------------------------------------------------  
15\. TOLERANCIA  
\--------------------------------------------------

La tolerancia oficial será:

\`\`\`text  
0  
\`\`\`

No se permiten diferencias financieras.

\--------------------------------------------------  
16\. ALERTA DE DIFERENCIAS  
\--------------------------------------------------

Toda inconsistencia deberá registrarse como incidente financiero.

\--------------------------------------------------  
17\. CONCILIACIÓN AUTOMÁTICA  
\--------------------------------------------------

El sistema intentará conciliación automática.

\--------------------------------------------------  
18\. CONCILIACIÓN MANUAL  
\--------------------------------------------------

El Administrador autorizado podrá ejecutar conciliaciones manuales.

\--------------------------------------------------  
19\. CONCILIACIÓN INDIVIDUAL  
\--------------------------------------------------

Permitida para:

\- usuario específico;  
\- asesor específico;  
\- caso especial.

\--------------------------------------------------  
20\. CONCILIACIÓN MASIVA  
\--------------------------------------------------

Permitida para:

\- ciudad;  
\- campaña;  
\- período.

\--------------------------------------------------  
21\. LIQUIDACIÓN EXTRAORDINARIA  
\--------------------------------------------------

Permitida bajo autorización formal.

\--------------------------------------------------  
22\. RETIRO DE USUARIO  
\--------------------------------------------------

Si un usuario solicita retiro:

\`\`\`text  
El sistema podrá generar  
liquidación extraordinaria individual.  
\`\`\`

\--------------------------------------------------  
23\. SUSPENSIÓN DE USUARIO  
\--------------------------------------------------

La liquidación podrá quedar retenida.

\--------------------------------------------------  
24\. FRAUDE  
\--------------------------------------------------

Las liquidaciones sospechosas podrán bloquearse.

\--------------------------------------------------  
25\. APROBACIÓN  
\--------------------------------------------------

Toda liquidación deberá ser aprobada.

\--------------------------------------------------  
26\. DOBLE VALIDACIÓN  
\--------------------------------------------------

Para montos críticos podrá requerirse doble aprobación.

\--------------------------------------------------  
27\. REPORTE OFICIAL  
\--------------------------------------------------

El sistema deberá generar automáticamente:

\`\`\`text  
Excel Oficial de Liquidación  
\`\`\`

\--------------------------------------------------  
28\. CONTENIDO DEL REPORTE  
\--------------------------------------------------

Como mínimo:

\- usuario;  
\- identificación;  
\- ciudad;  
\- cashback;  
\- multinivel nivel 1;  
\- multinivel nivel 2;  
\- incentivos;  
\- ajustes;  
\- total.

\--------------------------------------------------  
29\. FORMATO DE EXPORTACIÓN  
\--------------------------------------------------

Inicialmente:

\`\`\`text  
XLSX  
\`\`\`

\--------------------------------------------------  
30\. VERSIONAMIENTO DEL REPORTE  
\--------------------------------------------------

Todo reporte deberá poseer:

\- fecha;  
\- período;  
\- versión.

\--------------------------------------------------  
31\. AUDITORÍA  
\--------------------------------------------------

Toda conciliación deberá registrarse.

\--------------------------------------------------  
32\. TRAZABILIDAD  
\--------------------------------------------------

Registrar:

\- usuario ejecutor;  
\- fecha;  
\- acción;  
\- resultado.

\--------------------------------------------------  
33\. HISTORIAL  
\--------------------------------------------------

Conservar histórico de cierres.

\--------------------------------------------------  
34\. REAPERTURA DE PERÍODO  
\--------------------------------------------------

Solo podrá ejecutarse por Superadministrador.

\--------------------------------------------------  
35\. JUSTIFICACIÓN  
\--------------------------------------------------

Toda reapertura requerirá justificación obligatoria.

\--------------------------------------------------  
36\. RECÁLCULO  
\--------------------------------------------------

Todo recálculo deberá quedar registrado.

\--------------------------------------------------  
37\. AJUSTES CONTABLES  
\--------------------------------------------------

Los ajustes deberán conservar evidencia.

\--------------------------------------------------  
38\. ESTADOS DEL CIERRE  
\--------------------------------------------------

\`\`\`text  
Abierto

En Conciliación

Conciliado

Aprobado

Pagado

Cerrado  
\`\`\`

\--------------------------------------------------  
39\. PLAZO DE PAGO  
\--------------------------------------------------

La empresa dispondrá de:

\`\`\`text  
5 días calendario  
\`\`\`

posteriores al cierre.

\--------------------------------------------------  
40\. CONTROL DE PAGOS  
\--------------------------------------------------

Todo pago deberá asociarse a:

\- liquidación;  
\- período;  
\- beneficiario.

\--------------------------------------------------  
41\. PAGOS PARCIALES  
\--------------------------------------------------

Podrán permitirse bajo autorización.

\--------------------------------------------------  
42\. PAGOS REVERSADOS  
\--------------------------------------------------

Deberán registrarse y auditarse.

\--------------------------------------------------  
43\. CONCILIACIÓN FUTURA ERP  
\--------------------------------------------------

La arquitectura deberá soportar integración ERP.

\--------------------------------------------------  
44\. CONCILIACIÓN FUTURA PSE  
\--------------------------------------------------

La arquitectura deberá soportar conciliación automática bancaria.

\--------------------------------------------------  
45\. INDICADORES  
\--------------------------------------------------

Medir:

\- diferencias;  
\- tiempos;  
\- errores;  
\- pagos pendientes.

\--------------------------------------------------  
46\. KPI FINANCIEROS  
\--------------------------------------------------

Medir:

\- porcentaje conciliado;  
\- tiempo promedio de pago;  
\- diferencias detectadas.

\--------------------------------------------------  
47\. INCIDENTES FINANCIEROS  
\--------------------------------------------------

Toda anomalía deberá generar incidente.

\--------------------------------------------------  
48\. SEGURIDAD  
\--------------------------------------------------

Toda operación deberá ser auditable.

\--------------------------------------------------  
49\. EVOLUCIÓN  
\--------------------------------------------------

El proceso deberá adaptarse a nuevos modelos financieros.

\--------------------------------------------------  
50\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda liquidación, conciliación y cierre financiero de Tu Mobil Amigo deberá ser exacto, verificable, auditable y reproducible, garantizando que ningún pago se ejecute sin validación previa y que toda obligación financiera pueda reconstruirse completamente en cualquier momento.  

Fin de Documento 33A — Conciliación Financiera y Cierre Contable

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

Fin de Documento 34 — Gestión de Dispositivos

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

Este registro debe correlacionarse con:
Documento 41A — Gestión de Releases y Versionamiento, para cambios desplegados por Superadministrador.
Documento 32A — Gestión de Secretos y Credenciales, cuando la acción auditada involucre rotación o acceso a secretos.

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

Fin de  Documento 35 — Auditoría y Trazabilidad

\# Documento 36 — Continuidad Operativa

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial de continuidad operativa para garantizar que Tu Mobil Amigo pueda mantener o recuperar su operación ante eventos que afecten parcial o totalmente la plataforma.

Este documento busca minimizar:

\- interrupciones;  
\- pérdida de información;  
\- impacto financiero;  
\- impacto reputacional;  
\- impacto operativo.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

El sistema deberá diseñarse asumiendo que los fallos ocurrirán.

La continuidad operativa no consiste en evitar fallos.

Consiste en continuar operando cuando ocurran.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Flutter Cliente;  
\- Flutter Asesor;  
\- React Administrador;  
\- React Superadministrador;  
\- Backend;  
\- Base de Datos;  
\- Realtime;  
\- Integraciones;  
\- Infraestructura.

\--------------------------------------------------  
4\. OBJETIVOS DE CONTINUIDAD  
\--------------------------------------------------

Garantizar:

\- disponibilidad;  
\- recuperación;  
\- integridad;  
\- trazabilidad.

\--------------------------------------------------  
5\. EVENTOS CONTEMPLADOS  
\--------------------------------------------------

Como mínimo:

\- caída de servidores;  
\- caída de Base de Datos;  
\- pérdida de conectividad;  
\- error humano;  
\- corrupción de datos;  
\- ciberataque;  
\- ransomware;  
\- falla de integraciones;  
\- error de despliegue.

\--------------------------------------------------  
6\. CLASIFICACIÓN DE INCIDENTES  
\--------------------------------------------------

Nivel 1

Impacto menor.

Nivel 2

Impacto moderado.

Nivel 3

Impacto alto.

Nivel 4

Impacto crítico.

\--------------------------------------------------  
7\. RECUPERACIÓN PRIORITARIA  
\--------------------------------------------------

Orden de prioridad:

1\. Información financiera.  
2\. Usuarios.  
3\. Servicios activos.  
4\. Liquidaciones.  
5\. Auditoría.  
6\. Configuración.  
7\. Estadísticas.

\--------------------------------------------------  
8\. DISPONIBILIDAD  
\--------------------------------------------------

La arquitectura deberá buscar alta disponibilidad desde su diseño.

\--------------------------------------------------  
9\. ELIMINACIÓN DE PUNTOS ÚNICOS DE FALLA  
\--------------------------------------------------

Siempre que sea viable técnicamente.

\--------------------------------------------------  
10\. BACKUPS  
\--------------------------------------------------

Toda información crítica deberá respaldarse periódicamente.

\--------------------------------------------------  
11\. COBERTURA DE BACKUP  
\--------------------------------------------------

Incluir:

\- Base de Datos;  
\- Storage;  
\- Configuración;  
\- Reportes críticos.

\--------------------------------------------------  
12\. BACKUP DE BASE DE DATOS  
\--------------------------------------------------

Deberán existir mecanismos de recuperación completos.

\--------------------------------------------------  
13\. BACKUP DE CONFIGURACIONES  
\--------------------------------------------------

Toda configuración operativa deberá poder reconstruirse.

\--------------------------------------------------  
14\. BACKUP DE DOCUMENTOS  
\--------------------------------------------------

Los documentos operativos deberán mantenerse protegidos.

\--------------------------------------------------  
15\. RECUPERACIÓN DE DATOS  
\--------------------------------------------------

Toda restauración deberá ser verificable.

\--------------------------------------------------  
16\. PRUEBAS DE RESTAURACIÓN  
\--------------------------------------------------

Los procedimientos de restauración deberán probarse periódicamente.

\--------------------------------------------------  
17\. RECUPERACIÓN FINANCIERA  
\--------------------------------------------------

Las siguientes entidades son críticas:

\- wallets;  
\- liquidaciones;  
\- cashback;  
\- multinivel;  
\- incentivos;  
\- auditoría financiera.

\--------------------------------------------------  
18\. RECUPERACIÓN DE AUDITORÍA  
\--------------------------------------------------

Los registros de auditoría deberán preservarse.

\--------------------------------------------------  
19\. RECUPERACIÓN DE SEGURIDAD  
\--------------------------------------------------

Los eventos de seguridad deberán mantenerse disponibles para análisis posterior.

\--------------------------------------------------  
20\. RECUPERACIÓN DE DISPOSITIVOS  
\--------------------------------------------------

La información de:

\`\`\`text  
device\_registry  
\`\`\`

deberá formar parte de la estrategia de recuperación.

\--------------------------------------------------  
21\. FALLA DE INTEGRACIONES  
\--------------------------------------------------

El sistema deberá tolerar fallas temporales de:

\- Telegram;  
\- OpenStreetMap;  
\- GraphHopper;  
\- ERP futuros;  
\- PSE futuros.

\--------------------------------------------------  
22\. DEGRADACIÓN CONTROLADA  
\--------------------------------------------------

Ante una falla parcial el sistema deberá continuar operando con funcionalidades reducidas.

\--------------------------------------------------  
23\. FALLA DEL SISTEMA DE MAPAS  
\--------------------------------------------------

Si OpenStreetMap o GraphHopper presentan indisponibilidad:

\- el sistema deberá registrar el incidente;  
\- los servicios podrán continuar cuando sea posible;  
\- la operación financiera no deberá verse afectada.

\--------------------------------------------------  
24\. FALLA DEL SISTEMA DE PAGOS  
\--------------------------------------------------

Las operaciones deberán quedar registradas para procesamiento posterior.

\--------------------------------------------------  
25\. FALLA DE REALTIME  
\--------------------------------------------------

La pérdida de Realtime no deberá provocar pérdida de información.

\--------------------------------------------------  
26\. REPROCESAMIENTO  
\--------------------------------------------------

Los eventos fallidos deberán poder reprocesarse.

\--------------------------------------------------  
27\. COLAS DE RECUPERACIÓN  
\--------------------------------------------------

Los procesos críticos deberán soportar reintentos controlados.

\--------------------------------------------------  
28\. ERRORES HUMANOS  
\--------------------------------------------------

La arquitectura deberá minimizar:

\- borrados accidentales;  
\- configuraciones erróneas;  
\- ejecuciones incorrectas.

\--------------------------------------------------  
29\. OPERACIONES CRÍTICAS  
\--------------------------------------------------

Toda operación crítica deberá ser:

\- auditable;  
\- reversible cuando aplique;  
\- trazable.

\--------------------------------------------------  
30\. LIQUIDACIONES  
\--------------------------------------------------

Las liquidaciones deberán soportar:

\- simulación;  
\- aprobación;  
\- ejecución;  
\- recuperación.

\--------------------------------------------------  
31\. CONTINGENCIA DE LIQUIDACIONES  
\--------------------------------------------------

El sistema deberá permitir:

\`\`\`text  
Liquidaciones Extraordinarias  
\`\`\`

cuando existan contingencias operativas.

\--------------------------------------------------  
32\. REPORTE DE CONTINGENCIA  
\--------------------------------------------------

Todo incidente relevante deberá generar evidencia auditable.

\--------------------------------------------------  
33\. MONITOREO  
\--------------------------------------------------

Los servicios críticos deberán monitorearse continuamente.

\--------------------------------------------------  
34\. ALERTAMIENTO  
\--------------------------------------------------

La plataforma deberá generar alertas ante eventos críticos.

\--------------------------------------------------  
35\. TRAZABILIDAD  
\--------------------------------------------------

Todo incidente deberá registrarse en auditoría.

\--------------------------------------------------  
36\. ESCALABILIDAD  
\--------------------------------------------------

La continuidad operativa deberá mantenerse conforme crezca:

\- número de usuarios;  
\- ciudades;  
\- países;  
\- servicios.

\--------------------------------------------------  
37\. RECUPERACIÓN OPERATIVA  
\--------------------------------------------------

La empresa deberá poder continuar operando incluso ante indisponibilidad parcial de componentes tecnológicos.

\--------------------------------------------------  
38\. PROCEDIMIENTOS OPERATIVOS  
\--------------------------------------------------

Deberán existir procedimientos documentados para:

\- recuperación;  
\- restauración;  
\- contingencias;  
\- escalamiento.

\--------------------------------------------------  
39\. RESPONSABILIDADES  
\--------------------------------------------------

Toda contingencia deberá tener responsables claramente definidos.

\--------------------------------------------------  
40\. PRUEBAS DE CONTINUIDAD  
\--------------------------------------------------

Los procedimientos de continuidad deberán validarse periódicamente.

\--------------------------------------------------  
41\. CONTINUIDAD FINANCIERA  
\--------------------------------------------------

La integridad financiera tendrá prioridad sobre la velocidad de recuperación.

\--------------------------------------------------  
42\. CONTINUIDAD DE SEGURIDAD  
\--------------------------------------------------

La recuperación nunca deberá comprometer controles de seguridad.

\--------------------------------------------------  
43\. CONTINUIDAD DE AUDITORÍA  
\--------------------------------------------------

La trazabilidad deberá mantenerse incluso durante incidentes.

\--------------------------------------------------  
44\. CUMPLIMIENTO  
\--------------------------------------------------

Toda recuperación deberá respetar:

\- requisitos legales;  
\- requisitos tributarios;  
\- requisitos financieros.

\--------------------------------------------------  
45\. EVOLUCIÓN FUTURA  
\--------------------------------------------------

La arquitectura deberá permitir incorporar nuevos mecanismos de recuperación sin rediseños estructurales.

\--------------------------------------------------  
46\. Contingencia del Portal Administrativo
\--------------------------------------------------

Ante indisponibilidad del portal React (Administrador/Superadministrador):
Las operaciones críticas irreversibles (reapertura de período, liquidación extraordinaria) deberán quedar bloqueadas hasta el restablecimiento del portal — no existirá vía alterna de ejecución (ver Documento 40A para el plan de infraestructura de contingencia del frontend administrativo).
Las operaciones de Cliente y Asesor (Flutter) no se ven afectadas por esta contingencia, al ser arquitecturas independientes.

\--------------------------------------------------  
47\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La continuidad operativa de Tu Mobil Amigo deberá garantizar que la plataforma pueda resistir, recuperarse y continuar operando frente a fallas tecnológicas, operativas o de seguridad, preservando siempre la integridad de la información, la estabilidad financiera y la confianza del ecosistema.  

Fin de Documento 36 — Continuidad Operativa
