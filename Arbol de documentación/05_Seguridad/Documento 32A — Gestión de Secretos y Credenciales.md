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
