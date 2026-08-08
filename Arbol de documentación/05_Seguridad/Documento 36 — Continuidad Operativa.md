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
