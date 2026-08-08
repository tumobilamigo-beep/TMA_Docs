\# Documento 40 — DevOps

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial DevOps para construir, desplegar, operar y evolucionar Tu Mobil Amigo de forma segura, escalable, automatizada y controlada.

Este documento establece las reglas para la gestión de infraestructura, despliegues, entornos y automatización operativa.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo despliegue deberá ser:

\- repetible;  
\- automatizable;  
\- auditable;  
\- reversible.

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
\- Edge Functions;  
\- Realtime;  
\- Integraciones;  
\- Infraestructura.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- velocidad de despliegue;  
\- estabilidad;  
\- trazabilidad;  
\- seguridad;  
\- recuperación.

\--------------------------------------------------  
5\. FILOSOFÍA DEVOPS  
\--------------------------------------------------

La operación deberá minimizar:

\- tareas manuales;  
\- errores humanos;  
\- configuraciones inconsistentes.

\--------------------------------------------------  
6\. INFRAESTRUCTURA COMO CÓDIGO  
\--------------------------------------------------

Toda infraestructura futura deberá ser gestionable mediante código.

\--------------------------------------------------  
7\. ENTORNOS OFICIALES  
\--------------------------------------------------

La plataforma tendrá como mínimo:

\`\`\`text  
LOCAL

DESARROLLO

STAGING

PRODUCCIÓN  
\`\`\`

\--------------------------------------------------  
8\. ENTORNO LOCAL  
\--------------------------------------------------

Uso exclusivo de desarrolladores.

\--------------------------------------------------  
9\. ENTORNO DESARROLLO  
\--------------------------------------------------

Validación continua de funcionalidades.

\--------------------------------------------------  
10\. ENTORNO STAGING  
\--------------------------------------------------

Réplica funcional de producción.

\--------------------------------------------------  
11\. ENTORNO PRODUCCIÓN  
\--------------------------------------------------

Uso exclusivo de usuarios finales.

\--------------------------------------------------  
12\. AISLAMIENTO DE ENTORNOS  
\--------------------------------------------------

Los entornos deberán permanecer completamente separados.

\--------------------------------------------------  
13\. CONFIGURACIÓN POR ENTORNO  
\--------------------------------------------------

Toda configuración deberá depender de variables externas.

Nunca de código hardcodeado.

\--------------------------------------------------  
14\. GESTIÓN DE VARIABLES  
\--------------------------------------------------

Toda configuración sensible deberá almacenarse fuera del código fuente.

\--------------------------------------------------  
15\. CREDENCIALES  
\--------------------------------------------------

Prohibido almacenar:

\- API Keys;  
\- Secrets;  
\- Tokens;  
\- Contraseñas;

dentro del repositorio.

\--------------------------------------------------  
16\. CONTROL DE VERSIONES  
\--------------------------------------------------

Todo desarrollo deberá gestionarse mediante Git.

\--------------------------------------------------  
17\. ESTRATEGIA DE RAMAS  
\--------------------------------------------------

Como mínimo:

\`\`\`text  
main

develop

feature/\*  
\`\`\`

\--------------------------------------------------  
18\. REPOSITORIOS  
\--------------------------------------------------

El código deberá mantenerse versionado y trazable.

\--------------------------------------------------  
19\. REVISIÓN DE CÓDIGO  
\--------------------------------------------------

Todo cambio relevante deberá pasar revisión.

\--------------------------------------------------  
20\. AUTOMATIZACIÓN  
\--------------------------------------------------

Las tareas repetitivas deberán automatizarse.

\--------------------------------------------------  
21\. DOCKER  
\--------------------------------------------------

Docker será estándar oficial del proyecto.

\--------------------------------------------------  
22\. OBJETIVOS DE DOCKER  
\--------------------------------------------------

Garantizar:

\- consistencia;  
\- portabilidad;  
\- reproducibilidad.

\--------------------------------------------------  
23\. CONTENEDORES OFICIALES  
\--------------------------------------------------

Inicialmente:

\`\`\`text  
Flutter Build

React Admin

React SuperAdmin

Herramientas Operativas  
\`\`\`

\--------------------------------------------------  
24\. BASE DE DATOS  
\--------------------------------------------------

La Base de Datos oficial será Supabase PostgreSQL.

\--------------------------------------------------  
25\. MIGRACIONES  
\--------------------------------------------------

Toda modificación estructural deberá ejecutarse mediante migraciones.

\--------------------------------------------------  
26\. CONTROL DE MIGRACIONES  
\--------------------------------------------------

Prohibido modificar producción manualmente.

\--------------------------------------------------  
27\. VERSIONAMIENTO DE BASE DE DATOS  
\--------------------------------------------------

Toda migración deberá estar versionada.

\--------------------------------------------------  
28\. EDGE FUNCTIONS  
\--------------------------------------------------

Toda Edge Function deberá desplegarse mediante pipeline controlado.

\--------------------------------------------------  
29\. DESPLIEGUES  
\--------------------------------------------------

Los despliegues deberán ser:

\- trazables;  
\- reversibles;  
\- automatizados.

\--------------------------------------------------  
30\. ROLLBACK  
\--------------------------------------------------

Todo despliegue deberá permitir reversión.

\--------------------------------------------------  
31\. CRITERIOS DE ROLLBACK  
\--------------------------------------------------

Como mínimo:

\- error crítico;  
\- degradación severa;  
\- vulnerabilidad crítica.

\--------------------------------------------------  
32\. BACKUPS PREVIOS  
\--------------------------------------------------

Antes de cambios críticos deberá existir respaldo verificable.

\--------------------------------------------------  
33\. VALIDACIONES PRE-DESPLIEGUE  
\--------------------------------------------------

Obligatorias:

\- testing;  
\- seguridad;  
\- integridad.

\--------------------------------------------------  
34\. VALIDACIONES POST-DESPLIEGUE  
\--------------------------------------------------

Obligatorias:

\- disponibilidad;  
\- rendimiento;  
\- auditoría.

\--------------------------------------------------  
35\. OBSERVABILIDAD  
\--------------------------------------------------

Todo servicio deberá generar métricas.

\--------------------------------------------------  
36\. LOGGING  
\--------------------------------------------------

Todo componente deberá generar logs útiles.

\--------------------------------------------------  
37\. TRAZABILIDAD  
\--------------------------------------------------

Todo despliegue deberá registrar:

\- responsable;  
\- fecha;  
\- versión;  
\- resultado.

\--------------------------------------------------  
38\. SEGURIDAD OPERATIVA  
\--------------------------------------------------

Toda operación deberá ejecutarse bajo mínimo privilegio.

\--------------------------------------------------  
39\. ACCESO A PRODUCCIÓN  
\--------------------------------------------------

Restringido únicamente a personal autorizado.

\--------------------------------------------------  
40\. MFA OPERATIVO  
\--------------------------------------------------

Obligatorio para accesos privilegiados.

\--------------------------------------------------  
41\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

Desarrollo, aprobación y despliegue deberán mantenerse separados cuando sea posible.

\--------------------------------------------------  
42\. DESPLIEGUES DE EMERGENCIA  
\--------------------------------------------------

Deberán quedar auditados.

\--------------------------------------------------  
43\. GESTIÓN DE DEPENDENCIAS  
\--------------------------------------------------

Las dependencias deberán mantenerse actualizadas y verificadas.

\--------------------------------------------------  
44\. OPENSTREETMAP  
\--------------------------------------------------

La arquitectura inicial utilizará:

\`\`\`text  
OpenStreetMap  
\+  
MapTiler  
\+  
GraphHopper  
\`\`\`

como estrategia oficial de mapas para etapas tempranas.

\--------------------------------------------------  
45\. EVOLUCIÓN DE MAPAS  
\--------------------------------------------------

La arquitectura deberá permitir migrar posteriormente hacia:

\`\`\`text  
Infraestructura GIS propia  
\`\`\`

sin rediseños estructurales.

\--------------------------------------------------  
46\. ERP FUTURO  
\--------------------------------------------------

La arquitectura deberá soportar integración futura con:

\`\`\`text  
ERP

Contabilidad

Facturación  
\`\`\`

sin rediseños mayores.

\--------------------------------------------------  
47\. PSE FUTURO  
\--------------------------------------------------

La arquitectura deberá soportar integración futura con:

\`\`\`text  
PSE

Pasarelas de pago

Pagos empresariales  
\`\`\`

sin rediseños estructurales.

\--------------------------------------------------  
48\. RECUPERACIÓN OPERATIVA  
\--------------------------------------------------

Todo entorno deberá poder reconstruirse.

\--------------------------------------------------  
49\. TIEMPOS DE RECUPERACIÓN  
\--------------------------------------------------

Los procedimientos deberán minimizar:

\- indisponibilidad;  
\- pérdida de datos.

\--------------------------------------------------  
50\. ESCALABILIDAD  
\--------------------------------------------------

La infraestructura deberá soportar:

\- nuevas ciudades;  
\- nuevos países;  
\- nuevos servicios;  
\- crecimiento masivo.

\--------------------------------------------------  
51\. COSTOS OPERATIVOS  
\--------------------------------------------------

Las decisiones DevOps deberán balancear:

\- costo;  
\- rendimiento;  
\- escalabilidad.

\--------------------------------------------------  
52\. OPTIMIZACIÓN INICIAL  
\--------------------------------------------------

Durante etapas tempranas se priorizará:

\`\`\`text  
Simplicidad

Bajo costo

Alta mantenibilidad  
\`\`\`

sobre arquitecturas complejas prematuras.

\--------------------------------------------------  
53\. AUDITORÍA  
\--------------------------------------------------

Toda actividad operativa deberá ser auditable.

\--------------------------------------------------  
54\. CUMPLIMIENTO  
\--------------------------------------------------

Los procesos deberán respetar:

\- seguridad;  
\- protección financiera;  
\- trazabilidad.

\--------------------------------------------------  
55\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia DevOps deberá evolucionar junto con el crecimiento de la plataforma.

\--------------------------------------------------  
56\. Resumen de Componentes Desplegables  
\--------------------------------------------------
La infraestructura debe soportar el despliegue independiente de:
Flutter Cliente.
Flutter Asesor.
React Administrador.
React Superadministrador.
Backend (Supabase / Edge Functions).
El detalle completo de ambientes, versionamiento y pipelines por componente se encuentra en el Documento 40A (Infraestructura) y Documento 41A (Releases), los cuales deben considerarse la fuente autoritativa y prevalecer sobre este resumen en caso de conflicto.

\--------------------------------------------------  
57\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La operación tecnológica de Tu Mobil Amigo deberá ser automatizable, segura, escalable, auditable y recuperable, permitiendo que la plataforma evolucione durante años sin depender de procesos manuales o conocimientos individuales.  
