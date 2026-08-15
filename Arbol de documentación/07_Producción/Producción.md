Producción

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

Fin de Documento 40 — DevOps

\# Documento 40A — Gestión de Infraestructura y Ambientes

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la arquitectura de infraestructura, ambientes, dependencias tecnológicas y procedimientos de reconstrucción operativa de Tu Mobil Amigo.

Este documento establece la visión completa de los componentes tecnológicos necesarios para ejecutar la plataforma.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Toda infraestructura deberá poder reconstruirse completamente a partir de documentación, configuraciones versionadas y procedimientos controlados.

La operación nunca deberá depender del conocimiento exclusivo de una persona.

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
\- Realtime;  
\- OpenStreetMap;  
\- GraphHopper;  
\- Telegram;  
\- Integraciones futuras;  
\- Infraestructura futura.

\--------------------------------------------------  
4\. ARQUITECTURA GENERAL  
\--------------------------------------------------

La plataforma estará compuesta por:

\`\`\`text  
Frontend

Backend

Base de Datos

Realtime

Servicios Geográficos

Servicios Externos

Infraestructura Operativa  
\`\`\`

\--------------------------------------------------  
5\. CAPAS DE INFRAESTRUCTURA  
\--------------------------------------------------

\`\`\`text  
Capa Cliente

Capa Aplicación

Capa Datos

Capa Integración

Capa Observabilidad  
\`\`\`

\--------------------------------------------------  
6\. CAPA CLIENTE  
\--------------------------------------------------

Componentes:

\`\`\`text  
Flutter Cliente

Flutter Asesor

React Administrador

React Superadministrador  
\`\`\`

\--------------------------------------------------  
7\. CAPA DE APLICACIÓN  
\--------------------------------------------------

Componentes:

\`\`\`text  
Edge Functions

Servicios de negocio

Procesos programados  
\`\`\`

\--------------------------------------------------  
8\. CAPA DE DATOS  
\--------------------------------------------------

Componentes:

\`\`\`text  
PostgreSQL

Storage

Backups

Auditoría  
\`\`\`

\--------------------------------------------------  
9\. CAPA DE INTEGRACIÓN  
\--------------------------------------------------

Componentes:

\`\`\`text  
Telegram

GraphHopper

MapTiler

ERP Futuro

PSE Futuro  
\`\`\`

\--------------------------------------------------  
10\. CAPA DE OBSERVABILIDAD  
\--------------------------------------------------

Componentes:

\`\`\`text  
Logs

Métricas

Alertas

Dashboards  
\`\`\`

\--------------------------------------------------  
11\. AMBIENTES OFICIALES  
\--------------------------------------------------

La plataforma tendrá:

\`\`\`text  
Local

Desarrollo

Staging

Producción  
\`\`\`

\--------------------------------------------------  
12\. AMBIENTE LOCAL  
\--------------------------------------------------

Uso exclusivo de desarrollo.

\--------------------------------------------------  
13\. AMBIENTE DESARROLLO  
\--------------------------------------------------

Uso para construcción continua.

\--------------------------------------------------  
14\. AMBIENTE STAGING  
\--------------------------------------------------

Répllica funcional de producción.

\--------------------------------------------------  
15\. AMBIENTE PRODUCCIÓN  
\--------------------------------------------------

Uso exclusivo de usuarios finales.

\--------------------------------------------------  
16\. AISLAMIENTO  
\--------------------------------------------------

Los ambientes deberán mantenerse completamente separados.

\--------------------------------------------------  
17\. CONFIGURACIÓN  
\--------------------------------------------------

Cada ambiente tendrá:

\- variables independientes;  
\- secretos independientes;  
\- configuraciones independientes.

\--------------------------------------------------  
18\. FRONTENDS OFICIALES  
\--------------------------------------------------

Se autorizan:

\`\`\`text  
Flutter Cliente

Flutter Asesor

React Administrador

React Superadministrador  
\`\`\`

\--------------------------------------------------  
19\. FLUTTER CLIENTE  
\--------------------------------------------------

Responsabilidades:

\- solicitud de servicios;  
\- pagos futuros;  
\- cashback;  
\- multinivel.

\--------------------------------------------------  
20\. FLUTTER ASESOR  
\--------------------------------------------------

Responsabilidades:

\- recepción de ofertas;  
\- negociación;  
\- operación.

\--------------------------------------------------  
21\. REACT ADMINISTRADOR  
\--------------------------------------------------

Responsabilidades:

\- gestión operativa;  
\- monitoreo;  
\- soporte.

\--------------------------------------------------  
22\. REACT SUPERADMINISTRADOR  
\--------------------------------------------------

Responsabilidades:

\- gobierno;  
\- auditoría;  
\- configuración global;  
\- seguridad.

\--------------------------------------------------  
23\. BASE DE DATOS OFICIAL  
\--------------------------------------------------

La plataforma utilizará:

\`\`\`text  
Supabase PostgreSQL  
\`\`\`

\--------------------------------------------------  
24\. SERVICIOS DE DATOS  
\--------------------------------------------------

Componentes:

\- PostgreSQL;  
\- Storage;  
\- Realtime;  
\- Auth.

\--------------------------------------------------  
25\. REALTIME  
\--------------------------------------------------

Utilizará infraestructura oficial de Supabase.

\--------------------------------------------------  
26\. EDGE FUNCTIONS  
\--------------------------------------------------

Centralizarán lógica crítica de negocio.

\--------------------------------------------------  
27\. SERVICIOS GEOGRÁFICOS  
\--------------------------------------------------

Arquitectura inicial:

\`\`\`text  
OpenStreetMap

MapTiler

GraphHopper  
\`\`\`

\--------------------------------------------------  
28\. OPENSTREETMAP  
\--------------------------------------------------

Proveedor principal de datos cartográficos.

\--------------------------------------------------  
29\. MAPTILER  
\--------------------------------------------------

Proveedor principal de tiles.

\--------------------------------------------------  
30\. GRAPHHOPPER  
\--------------------------------------------------

Proveedor principal de rutas.

\--------------------------------------------------  
31\. EVOLUCIÓN GIS  
\--------------------------------------------------

La arquitectura deberá permitir migración futura hacia:

\`\`\`text  
Infraestructura GIS propia  
\`\`\`

sin rediseño estructural.

\--------------------------------------------------  
32\. TELEGRAM  
\--------------------------------------------------

Canal secundario autorizado.

\--------------------------------------------------  
33\. ERP FUTURO  
\--------------------------------------------------

Integración prevista.

\--------------------------------------------------  
34\. PSE FUTURO  
\--------------------------------------------------

Integración prevista.

\--------------------------------------------------  
35\. TOPOLOGÍA LÓGICA  
\--------------------------------------------------

\`\`\`text  
Cliente  
      ↓  
Flutter  
      ↓  
API / Edge Functions  
      ↓  
PostgreSQL  
      ↓  
Realtime  
      ↓  
Aplicaciones  
\`\`\`

\--------------------------------------------------  
36\. SEGMENTACIÓN  
\--------------------------------------------------

Separar:

\- usuarios;  
\- administración;  
\- infraestructura.

\--------------------------------------------------  
37\. DISPONIBILIDAD  
\--------------------------------------------------

Toda infraestructura crítica deberá ser monitoreada.

\--------------------------------------------------  
38\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura deberá soportar:

\- nuevas ciudades;  
\- nuevos países;  
\- nuevos servicios.

\--------------------------------------------------  
39\. CAPACIDAD  
\--------------------------------------------------

La infraestructura deberá escalar horizontalmente cuando sea posible.

\--------------------------------------------------  
40\. BACKUPS  
\--------------------------------------------------

Todos los componentes críticos deberán poseer estrategia de respaldo.

\--------------------------------------------------  
41\. RESTAURACIÓN  
\--------------------------------------------------

Las restauraciones deberán probarse periódicamente.

\--------------------------------------------------  
42\. RECUPERACIÓN ANTE DESASTRES  
\--------------------------------------------------

Deberán existir procedimientos documentados.

\--------------------------------------------------  
43\. RTO  
\--------------------------------------------------

Objetivo inicial:

\`\`\`text  
Menor a 8 horas  
\`\`\`

\--------------------------------------------------  
44\. RPO  
\--------------------------------------------------

Objetivo inicial:

\`\`\`text  
Menor a 1 hora  
\`\`\`

\--------------------------------------------------  
45\. DOCUMENTACIÓN DE ACTIVOS  
\--------------------------------------------------

Todo activo deberá estar documentado.

\--------------------------------------------------  
46\. INVENTARIO DE ACTIVOS  
\--------------------------------------------------

Registrar:

\- nombre;  
\- función;  
\- responsable;  
\- criticidad.

\--------------------------------------------------  
47\. DEPENDENCIAS  
\--------------------------------------------------

Todas las dependencias deberán documentarse.

\--------------------------------------------------  
48\. OBSERVABILIDAD  
\--------------------------------------------------

Toda infraestructura deberá ser observable.

\--------------------------------------------------  
49\. SEGURIDAD  
\--------------------------------------------------

Aplicar principio de mínimo privilegio.

\--------------------------------------------------  
50\. GESTIÓN DE SECRETOS  
\--------------------------------------------------

Regida por:

\`\`\`text  
Documento 32A  
\`\`\`

\--------------------------------------------------  
51\. AUDITORÍA  
\--------------------------------------------------

Toda modificación deberá quedar registrada.

\--------------------------------------------------  
52\. PROCEDIMIENTO DE RECONSTRUCCIÓN  
\--------------------------------------------------

La infraestructura deberá poder reconstruirse completamente.

\--------------------------------------------------  
53\. PROCEDIMIENTO DE REEMPLAZO  
\--------------------------------------------------

Todo componente deberá poder sustituirse.

\--------------------------------------------------  
54\. INDEPENDENCIA TECNOLÓGICA  
\--------------------------------------------------

Evitar dependencias que impidan evolución futura.

\--------------------------------------------------  
55\. EVOLUCIÓN  
\--------------------------------------------------

La infraestructura deberá crecer sin requerir rediseños completos.

\--------------------------------------------------  
56\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La infraestructura de Tu Mobil Amigo deberá ser escalable, auditable, recuperable y documentada, permitiendo operar la plataforma durante años sin depender de configuraciones ocultas o conocimiento individual.  

Fin de Documento 40A — Gestión de Infraestructura y Ambientes

\# Documento 41 — CI/CD

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial de Integración Continua (CI) y Despliegue Continuo (CD) para Tu Mobil Amigo.

El objetivo es garantizar entregas frecuentes, seguras, auditables y reproducibles.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ningún cambio deberá llegar a producción sin pasar por un proceso automatizado de validación.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Flutter Cliente;  
\- Flutter Asesor;  
\- React Administrador;  
\- React Superadministrador;  
\- Base de Datos;  
\- Edge Functions;  
\- Infraestructura;  
\- Configuración.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- calidad;  
\- velocidad;  
\- trazabilidad;  
\- seguridad;  
\- recuperación.

\--------------------------------------------------  
5\. DEFINICIONES  
\--------------------------------------------------

CI:

\`\`\`text  
Continuous Integration  
\`\`\`

CD:

\`\`\`text  
Continuous Delivery  
o  
Continuous Deployment  
\`\`\`

\--------------------------------------------------  
6\. MODELO OFICIAL  
\--------------------------------------------------

La estrategia oficial será:

\`\`\`text  
Desarrollo  
      ↓

Pull Request  
      ↓

Pipeline CI  
      ↓

Staging  
      ↓

Aprobación  
      ↓

Producción  
\`\`\`

\--------------------------------------------------  
7\. REPOSITORIO OFICIAL  
\--------------------------------------------------

Todo código deberá residir en Git.

\--------------------------------------------------  
8\. ESTRATEGIA DE RAMAS  
\--------------------------------------------------

\`\`\`text  
main

develop

feature/\*  
\`\`\`

\--------------------------------------------------  
9\. FEATURE BRANCHES  
\--------------------------------------------------

Toda funcionalidad nueva deberá desarrollarse en ramas independientes.

\--------------------------------------------------  
10\. PULL REQUESTS  
\--------------------------------------------------

Todo cambio deberá ingresar mediante Pull Request.

\--------------------------------------------------  
11\. REVISIÓN OBLIGATORIA  
\--------------------------------------------------

Los cambios críticos requerirán revisión previa.

\--------------------------------------------------  
12\. PROHIBICIONES  
\--------------------------------------------------

Prohibido:

\`\`\`text  
Push directo a main  
\`\`\`

\--------------------------------------------------  
13\. INTEGRACIÓN CONTINUA  
\--------------------------------------------------

Cada Pull Request deberá ejecutar automáticamente:

\- compilación;  
\- validaciones;  
\- pruebas.

\--------------------------------------------------  
14\. ETAPA DE BUILD  
\--------------------------------------------------

Validar:

\- compilación correcta;  
\- dependencias;  
\- configuración.

\--------------------------------------------------  
15\. ETAPA DE LINTING  
\--------------------------------------------------

Validar:

\- estándares de código;  
\- consistencia.

\--------------------------------------------------  
16\. ETAPA DE TESTING  
\--------------------------------------------------

Ejecutar:

\- unit tests;  
\- integration tests;  
\- pruebas críticas.

\--------------------------------------------------  
17\. COBERTURA MÍNIMA  
\--------------------------------------------------

Objetivo mínimo:

\`\`\`text  
80%  
\`\`\`

para componentes críticos.

\--------------------------------------------------  
18\. ANÁLISIS DE SEGURIDAD  
\--------------------------------------------------

Ejecutar automáticamente:

\`\`\`text  
SAST  
\`\`\`

\--------------------------------------------------  
19\. ESCANEO DE DEPENDENCIAS  
\--------------------------------------------------

Detectar:

\- vulnerabilidades;  
\- paquetes inseguros.

\--------------------------------------------------  
20\. VALIDACIÓN DE SECRETOS  
\--------------------------------------------------

Detectar:

\- API Keys;  
\- Tokens;  
\- Secrets;  
\- Contraseñas.

\--------------------------------------------------  
21\. BLOQUEO DE PIPELINE  
\--------------------------------------------------

El pipeline deberá fallar automáticamente si detecta credenciales expuestas.

\--------------------------------------------------  
22\. VALIDACIÓN DE MIGRACIONES  
\--------------------------------------------------

Toda migración deberá verificarse antes del despliegue.

\--------------------------------------------------  
23\. VALIDACIÓN DE BASE DE DATOS  
\--------------------------------------------------

Verificar:

\- estructura;  
\- compatibilidad;  
\- integridad.

\--------------------------------------------------  
24\. VALIDACIÓN DE EDGE FUNCTIONS  
\--------------------------------------------------

Verificar:

\- compilación;  
\- despliegue;  
\- dependencias.

\--------------------------------------------------  
25\. VALIDACIÓN FLUTTER  
\--------------------------------------------------

Verificar:

\- compilación Android;  
\- compilación Web.

\--------------------------------------------------  
26\. VALIDACIÓN REACT  
\--------------------------------------------------

Verificar:

\- build exitoso;  
\- rutas válidas.

\--------------------------------------------------  
27\. VALIDACIÓN DE CONFIGURACIÓN  
\--------------------------------------------------

Verificar:

\- variables requeridas;  
\- consistencia.

\--------------------------------------------------  
28\. ENTORNO DE STAGING  
\--------------------------------------------------

Todo cambio aprobado deberá desplegarse primero en Staging.

\--------------------------------------------------  
29\. OBJETIVO DE STAGING  
\--------------------------------------------------

Simular producción.

\--------------------------------------------------  
30\. APROBACIÓN DE DESPLIEGUE  
\--------------------------------------------------

La liberación a producción requerirá aprobación formal.

\--------------------------------------------------  
31\. DESPLIEGUE CONTROLADO  
\--------------------------------------------------

Toda liberación deberá quedar registrada.

\--------------------------------------------------  
32\. DESPLIEGUE A PRODUCCIÓN  
\--------------------------------------------------

Deberá ser:

\- automatizado;  
\- trazable;  
\- reversible.

\--------------------------------------------------  
33\. ROLLBACK AUTOMÁTICO  
\--------------------------------------------------

El proceso deberá permitir reversión rápida.

\--------------------------------------------------  
34\. CRITERIOS DE ROLLBACK  
\--------------------------------------------------

Como mínimo:

\- fallo crítico;  
\- degradación severa;  
\- vulnerabilidad crítica.

\--------------------------------------------------  
35\. VERSIONAMIENTO  
\--------------------------------------------------

Toda liberación deberá generar versión identificable.

\--------------------------------------------------  
36\. VERSIONADO SEMÁNTICO  
\--------------------------------------------------

Formato oficial:

\`\`\`text  
MAJOR.MINOR.PATCH  
\`\`\`

Ejemplo:

\`\`\`text  
1.0.0  
1.1.0  
1.1.1  
\`\`\`

\--------------------------------------------------  
37\. REGISTRO DE RELEASES  
\--------------------------------------------------

Toda versión deberá documentarse.

\--------------------------------------------------  
38\. TRAZABILIDAD  
\--------------------------------------------------

Registrar:

\- versión;  
\- responsable;  
\- fecha;  
\- resultado.

\--------------------------------------------------  
39\. PIPELINE FLUTTER  
\--------------------------------------------------

Secuencia mínima:

\`\`\`text  
Build

Lint

Testing

Package

Deploy  
\`\`\`

\--------------------------------------------------  
40\. PIPELINE REACT  
\--------------------------------------------------

Secuencia mínima:

\`\`\`text  
Build

Lint

Testing

Deploy  
\`\`\`

\--------------------------------------------------  
41\. PIPELINE BASE DE DATOS  
\--------------------------------------------------

Secuencia mínima:

\`\`\`text  
Migración

Validación

Backup

Aplicación  
\`\`\`

\--------------------------------------------------  
42\. PIPELINE EDGE FUNCTIONS  
\--------------------------------------------------

Secuencia mínima:

\`\`\`text  
Build

Testing

Deploy  
\`\`\`

\--------------------------------------------------  
43\. CONTROL DE CAMBIOS  
\--------------------------------------------------

Todo cambio deberá quedar asociado a:

\- ticket;  
\- incidencia;  
\- mejora.

\--------------------------------------------------  
44\. AUDITORÍA  
\--------------------------------------------------

Toda ejecución deberá conservar evidencia.

\--------------------------------------------------  
45\. MÉTRICAS CI/CD  
\--------------------------------------------------

Monitorear:

\- éxito;  
\- fallos;  
\- duración;  
\- frecuencia.

\--------------------------------------------------  
46\. SEGURIDAD OPERATIVA  
\--------------------------------------------------

Los pipelines deberán ejecutarse con mínimo privilegio.

\--------------------------------------------------  
47\. SEPARACIÓN DE FUNCIONES  
\--------------------------------------------------

Cuando sea posible:

\`\`\`text  
Desarrollador

Revisor

Aprobador

Operador  
\`\`\`

deberán ser distintos.

\--------------------------------------------------  
48\. DESPLIEGUES DE EMERGENCIA  
\--------------------------------------------------

Permitidos únicamente bajo procedimiento especial.

\--------------------------------------------------  
49\. HOTFIXES  
\--------------------------------------------------

Deberán seguir pipeline reducido pero auditado.

\--------------------------------------------------  
50\. RECUPERACIÓN  
\--------------------------------------------------

Todo pipeline deberá permitir reconstruir una versión anterior.

\--------------------------------------------------  
51\. ESCALABILIDAD  
\--------------------------------------------------

La estrategia deberá soportar crecimiento del equipo.

\--------------------------------------------------  
52\. EVOLUCIÓN  
\--------------------------------------------------

El pipeline deberá evolucionar junto con la plataforma.

\--------------------------------------------------  
53\. Resumen de Componentes Desplegables  
\--------------------------------------------------

La infraestructura debe soportar el despliegue independiente de:
Flutter Cliente.
Flutter Asesor.
React Administrador.
React Superadministrador.
Backend (Supabase / Edge Functions).
El detalle completo de ambientes, versionamiento y pipelines por componente se encuentra en el Documento 40A (Infraestructura) y Documento 41A (Releases), los cuales deben considerarse la fuente autoritativa y prevalecer sobre este resumen en caso de conflicto.

\--------------------------------------------------  
54\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Todo cambio en Tu Mobil Amigo deberá atravesar un proceso automatizado de validación, seguridad, trazabilidad y despliegue controlado antes de impactar usuarios o procesos financieros.  

Fin de Documento 41 — CI/CD

\# Documento 41A — Gestión de Releases y Versionamiento

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el modelo oficial de releases, versionamiento, trazabilidad y control de cambios de Tu Mobil Amigo.

Este documento garantiza que cualquier cambio desplegado en la plataforma pueda ser identificado, auditado, reconstruido y revertido.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo cambio deberá estar asociado a una versión identificable y trazable.

Ningún despliegue podrá existir sin versión oficial.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Flutter Cliente;  
\- Flutter Asesor;  
\- React Administrador;  
\- React Superadministrador;  
\- Base de Datos;  
\- Edge Functions;  
\- APIs;  
\- Integraciones;  
\- Infraestructura.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- trazabilidad;  
\- auditoría;  
\- compatibilidad;  
\- recuperación;  
\- evolución controlada.

\--------------------------------------------------  
5\. CONCEPTO DE RELEASE  
\--------------------------------------------------

Un Release representa un conjunto aprobado de cambios desplegados en un ambiente específico.

\--------------------------------------------------  
6\. COMPONENTES VERSIONABLES  
\--------------------------------------------------

Todo componente deberá poseer versión independiente.

\--------------------------------------------------  
7\. COMPONENTES OFICIALES  
\--------------------------------------------------

\`\`\`text  
Flutter Cliente

Flutter Asesor

React Administrador

React Superadministrador

Base de Datos

Edge Functions

Infraestructura  
\`\`\`

\--------------------------------------------------  
8\. VERSIONAMIENTO OFICIAL  
\--------------------------------------------------

Se utilizará:

\`\`\`text  
Semantic Versioning  
\`\`\`

\--------------------------------------------------  
9\. FORMATO OFICIAL  
\--------------------------------------------------

\`\`\`text  
MAJOR.MINOR.PATCH  
\`\`\`

Ejemplos:

\`\`\`text  
1.0.0

1.1.0

1.1.1

2.0.0  
\`\`\`

\--------------------------------------------------  
10\. MAJOR  
\--------------------------------------------------

Cambios incompatibles o estructurales.

\--------------------------------------------------  
11\. MINOR  
\--------------------------------------------------

Nuevas funcionalidades compatibles.

\--------------------------------------------------  
12\. PATCH  
\--------------------------------------------------

Correcciones y mejoras menores.

\--------------------------------------------------  
13\. VERSIONAMIENTO DE FLUTTER  
\--------------------------------------------------

Cliente y Asesor tendrán control independiente.

\--------------------------------------------------  
14\. VERSIONAMIENTO REACT  
\--------------------------------------------------

Administrador y Superadministrador tendrán control independiente.

\--------------------------------------------------  
15\. VERSIONAMIENTO BASE DE DATOS  
\--------------------------------------------------

Las migraciones tendrán numeración propia.

\--------------------------------------------------  
16\. VERSIONAMIENTO EDGE FUNCTIONS  
\--------------------------------------------------

Las funciones críticas podrán evolucionar independientemente.

\--------------------------------------------------  
17\. MATRIZ DE COMPATIBILIDAD  
\--------------------------------------------------

Deberá mantenerse una matriz oficial entre componentes.

\--------------------------------------------------  
18\. EJEMPLO DE COMPATIBILIDAD  
\--------------------------------------------------

\`\`\`text  
Flutter Cliente 1.3.0

Compatible con

Base de Datos 1.2.0  
\`\`\`

\--------------------------------------------------  
19\. RELEASE CANDIDATE  
\--------------------------------------------------

Podrán existir versiones:

\`\`\`text  
RC  
\`\`\`

para validación previa.

\--------------------------------------------------  
20\. RELEASE OFICIAL  
\--------------------------------------------------

Solo versiones aprobadas podrán desplegarse a producción.

\--------------------------------------------------  
21\. IDENTIFICADOR DE RELEASE  
\--------------------------------------------------

Todo release tendrá:

\- código;  
\- fecha;  
\- responsable.

\--------------------------------------------------  
22\. CHANGELOG  
\--------------------------------------------------

Todo release deberá generar historial de cambios.

\--------------------------------------------------  
23\. CONTENIDO DEL CHANGELOG  
\--------------------------------------------------

Registrar:

\- funcionalidades;  
\- correcciones;  
\- riesgos;  
\- dependencias.

\--------------------------------------------------  
24\. CLASIFICACIÓN DE CAMBIOS  
\--------------------------------------------------

\`\`\`text  
Funcional

Técnico

Seguridad

Financiero

Infraestructura  
\`\`\`

\--------------------------------------------------  
25\. CAMBIOS FINANCIEROS  
\--------------------------------------------------

Deberán quedar especialmente identificados.

\--------------------------------------------------  
26\. CAMBIOS DE SEGURIDAD  
\--------------------------------------------------

Deberán quedar especialmente identificados.

\--------------------------------------------------  
27\. APROBACIÓN  
\--------------------------------------------------

Todo release requerirá aprobación formal.

\--------------------------------------------------  
28\. STAGING  
\--------------------------------------------------

Todo release deberá pasar previamente por Staging.

\--------------------------------------------------  
29\. VALIDACIÓN  
\--------------------------------------------------

Deberán ejecutarse:

\- pruebas;  
\- auditorías;  
\- verificaciones.

\--------------------------------------------------  
30\. DESPLIEGUE  
\--------------------------------------------------

Todo despliegue deberá quedar registrado.

\--------------------------------------------------  
31\. REGISTRO DE RELEASES  
\--------------------------------------------------

Registrar:

\- versión;  
\- fecha;  
\- responsable;  
\- resultado.

\--------------------------------------------------  
32\. ESTADOS DE RELEASE  
\--------------------------------------------------

\`\`\`text  
Planificado

En Desarrollo

En Validación

Aprobado

Desplegado

Retirado  
\`\`\`

\--------------------------------------------------  
33\. HOTFIX  
\--------------------------------------------------

Los Hotfix tendrán numeración oficial.

\--------------------------------------------------  
34\. HOTFIX CRÍTICO  
\--------------------------------------------------

Podrá utilizar procedimiento acelerado.

\--------------------------------------------------  
35\. ROLLBACK  
\--------------------------------------------------

Todo release deberá permitir reversión.

\--------------------------------------------------  
36\. REGISTRO DE ROLLBACK  
\--------------------------------------------------

Toda reversión deberá documentarse.

\--------------------------------------------------  
37\. TRAZABILIDAD  
\--------------------------------------------------

Toda modificación deberá poder rastrearse.

\--------------------------------------------------  
38\. AUDITORÍA  
\--------------------------------------------------

Toda versión deberá ser auditable.

\--------------------------------------------------  
39\. HISTÓRICO  
\--------------------------------------------------

Las versiones deberán conservarse.

\--------------------------------------------------  
40\. OBSOLESCENCIA  
\--------------------------------------------------

Las versiones retiradas deberán registrarse.

\--------------------------------------------------  
41\. SOPORTE  
\--------------------------------------------------

Se deberá definir qué versiones poseen soporte activo.

\--------------------------------------------------  
42\. SOPORTE EXTENDIDO  
\--------------------------------------------------

Podrán existir versiones LTS.

\--------------------------------------------------  
43\. VERSIONES MÍNIMAS  
\--------------------------------------------------

La plataforma podrá exigir versiones mínimas.

\--------------------------------------------------  
44\. CONTROL DE APPS  
\--------------------------------------------------

Flutter Cliente y Asesor podrán forzar actualización obligatoria.

\--------------------------------------------------  
45\. MIGRACIONES  
\--------------------------------------------------

Toda migración deberá asociarse a un release.

\--------------------------------------------------  
46\. INCIDENTES  
\--------------------------------------------------

Todo incidente crítico deberá asociarse a una versión.

\--------------------------------------------------  
47\. MÉTRICAS  
\--------------------------------------------------

Medir:

\- frecuencia;  
\- fallos;  
\- reversión.

\--------------------------------------------------  
48\. KPI OPERATIVOS  
\--------------------------------------------------

Medir:

\- releases exitosos;  
\- releases fallidos;  
\- tiempo promedio.

\--------------------------------------------------  
49\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia de releases deberá crecer junto con la plataforma.

\--------------------------------------------------  
50\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda modificación realizada en Tu Mobil Amigo deberá estar identificada, versionada, auditada y asociada a un release oficial que permita conocer qué cambió, cuándo cambió, quién lo aprobó y cómo revertirlo.  

Fin de Documento 41A — Gestión de Releases y Versionamiento

\# Documento 42 — Monitoreo

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial de monitoreo, observabilidad y gestión proactiva de eventos operativos para garantizar la disponibilidad, estabilidad, seguridad y continuidad de Tu Mobil Amigo.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

No se puede administrar aquello que no se puede medir.

Todo componente crítico deberá ser monitoreado.

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
\- Realtime;  
\- OpenStreetMap;  
\- GraphHopper;  
\- Integraciones futuras;  
\- Infraestructura.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- disponibilidad;  
\- rendimiento;  
\- estabilidad;  
\- seguridad;  
\- recuperación temprana.

\--------------------------------------------------  
5\. PILARES DE OBSERVABILIDAD  
\--------------------------------------------------

La observabilidad oficial se basará en:

\`\`\`text  
Logs

Métricas

Trazas  
\`\`\`

\--------------------------------------------------  
6\. LOGS  
\--------------------------------------------------

Todo componente deberá generar logs útiles para:

\- diagnóstico;  
\- auditoría;  
\- investigación.

\--------------------------------------------------  
7\. MÉTRICAS  
\--------------------------------------------------

Todo componente crítico deberá generar métricas operativas.

\--------------------------------------------------  
8\. TRAZAS  
\--------------------------------------------------

Los procesos críticos deberán poder rastrearse de extremo a extremo.

\--------------------------------------------------  
9\. COMPONENTES MONITOREADOS  
\--------------------------------------------------

Como mínimo:

\`\`\`text  
Frontend

Backend

Base de Datos

Realtime

Integraciones

Infraestructura  
\`\`\`

\--------------------------------------------------  
10\. DISPONIBILIDAD  
\--------------------------------------------------

Se deberá monitorear:

\- uptime;  
\- interrupciones;  
\- degradaciones.

\--------------------------------------------------  
11\. SLA OBJETIVO  
\--------------------------------------------------

Objetivo inicial:

\`\`\`text  
99.5%  
\`\`\`

\--------------------------------------------------  
12\. EVOLUCIÓN DEL SLA  
\--------------------------------------------------

A medida que crezca la plataforma:

\`\`\`text  
99.9%  
\`\`\`

\--------------------------------------------------  
13\. LATENCIA  
\--------------------------------------------------

Monitorear:

\- APIs;  
\- consultas;  
\- integraciones.

\--------------------------------------------------  
14\. TIEMPO DE RESPUESTA  
\--------------------------------------------------

Medir:

\- promedio;  
\- máximo;  
\- percentiles.

\--------------------------------------------------  
15\. BASE DE DATOS  
\--------------------------------------------------

Monitorear:

\- conexiones;  
\- consultas;  
\- bloqueos;  
\- consumo.

\--------------------------------------------------  
16\. CONSULTAS LENTAS  
\--------------------------------------------------

Detectar automáticamente:

\`\`\`text  
Slow Queries  
\`\`\`

\--------------------------------------------------  
17\. CONCURRENCIA  
\--------------------------------------------------

Monitorear:

\- usuarios simultáneos;  
\- sesiones activas.

\--------------------------------------------------  
18\. REALTIME  
\--------------------------------------------------

Monitorear:

\- canales activos;  
\- desconexiones;  
\- reconexiones.

\--------------------------------------------------  
19\. EDGE FUNCTIONS  
\--------------------------------------------------

Monitorear:

\- ejecuciones;  
\- errores;  
\- duración.

\--------------------------------------------------  
20\. APIs  
\--------------------------------------------------

Monitorear:

\- volumen;  
\- errores;  
\- latencia.

\--------------------------------------------------  
21\. RATE LIMIT  
\--------------------------------------------------

Monitorear:

\- abusos;  
\- bloqueos;  
\- intentos sospechosos.

\--------------------------------------------------  
22\. ERRORES  
\--------------------------------------------------

Clasificar:

\`\`\`text  
Crítico

Alto

Medio

Bajo  
\`\`\`

\--------------------------------------------------  
23\. ALERTAS  
\--------------------------------------------------

Toda condición crítica deberá generar alerta.

\--------------------------------------------------  
24\. CANALES DE ALERTA  
\--------------------------------------------------

Inicialmente:

\`\`\`text  
Telegram

Correo electrónico  
\`\`\`

\--------------------------------------------------  
25\. INCIDENTES CRÍTICOS  
\--------------------------------------------------

Generar alerta inmediata.

\--------------------------------------------------  
26\. SEGURIDAD  
\--------------------------------------------------

Monitorear:

\- intentos fallidos;  
\- accesos sospechosos;  
\- anomalías.

\--------------------------------------------------  
27\. ANTIFRAUDE  
\--------------------------------------------------

Monitorear:

\- patrones sospechosos;  
\- abuso de beneficios;  
\- multicuentas.

\--------------------------------------------------  
28\. DEVICE REGISTRY  
\--------------------------------------------------

Monitorear:

\- dispositivos bloqueados;  
\- dispositivos sospechosos;  
\- cambios frecuentes.

\--------------------------------------------------  
29\. CASHBACK  
\--------------------------------------------------

Monitorear:

\- generación;  
\- reversos;  
\- anomalías.

\--------------------------------------------------  
30\. MULTINIVEL  
\--------------------------------------------------

Monitorear:

\- crecimiento;  
\- patrones anómalos.

\--------------------------------------------------  
31\. LIQUIDACIONES  
\--------------------------------------------------

Monitorear:

\- ejecución;  
\- tiempos;  
\- errores.

\--------------------------------------------------  
32\. REPORTES MENSUALES  
\--------------------------------------------------

Monitorear:

\- generación;  
\- exportación;  
\- entrega.

\--------------------------------------------------  
33\. OPENSTREETMAP  
\--------------------------------------------------

Monitorear:

\- disponibilidad;  
\- tiempos de respuesta.

\--------------------------------------------------  
34\. GRAPHHOPPER  
\--------------------------------------------------

Monitorear:

\- disponibilidad;  
\- latencia;  
\- errores.

\--------------------------------------------------  
35\. TELEGRAM  
\--------------------------------------------------

Monitorear:

\- conectividad;  
\- errores;  
\- tiempos.

\--------------------------------------------------  
36\. ERP FUTURO  
\--------------------------------------------------

Monitorear:

\- sincronización;  
\- errores.

\--------------------------------------------------  
37\. PSE FUTURO  
\--------------------------------------------------

Monitorear:

\- pagos;  
\- conciliaciones;  
\- errores.

\--------------------------------------------------  
38\. BACKUPS  
\--------------------------------------------------

Monitorear:

\- ejecución;  
\- éxito;  
\- recuperación.

\--------------------------------------------------  
39\. RECUPERACIÓN  
\--------------------------------------------------

Monitorear:

\- restauraciones;  
\- tiempos.

\--------------------------------------------------  
40\. DASHBOARDS  
\--------------------------------------------------

La operación deberá disponer de paneles visuales.

\--------------------------------------------------  
41\. DASHBOARD EJECUTIVO  
\--------------------------------------------------

Visualizar:

\- usuarios;  
\- servicios;  
\- ingresos;  
\- disponibilidad.

\--------------------------------------------------  
42\. DASHBOARD OPERATIVO  
\--------------------------------------------------

Visualizar:

\- errores;  
\- alertas;  
\- incidentes.

\--------------------------------------------------  
43\. DASHBOARD FINANCIERO  
\--------------------------------------------------

Visualizar:

\- cashback;  
\- multinivel;  
\- liquidaciones;  
\- pagos.

\--------------------------------------------------  
44\. DASHBOARD SEGURIDAD  
\--------------------------------------------------

Visualizar:

\- ataques;  
\- bloqueos;  
\- eventos sospechosos.

\--------------------------------------------------  
45\. RETENCIÓN DE DATOS  
\--------------------------------------------------

Los datos de monitoreo deberán conservarse según política operativa.

\--------------------------------------------------  
46\. AUDITORÍA  
\--------------------------------------------------

Toda alerta deberá ser trazable.

\--------------------------------------------------  
47\. SLO  
\--------------------------------------------------

Definir objetivos internos de rendimiento.

\--------------------------------------------------  
48\. ERROR BUDGET  
\--------------------------------------------------

La plataforma podrá operar con márgenes de error controlados.

\--------------------------------------------------  
49\. CAPACIDAD  
\--------------------------------------------------

Monitorear crecimiento de:

\- usuarios;  
\- servicios;  
\- almacenamiento.

\--------------------------------------------------  
50\. ESCALABILIDAD  
\--------------------------------------------------

Detectar anticipadamente necesidades de ampliación.

\--------------------------------------------------  
51\. MANTENIMIENTO PREVENTIVO  
\--------------------------------------------------

El monitoreo deberá permitir actuar antes de una falla.

\--------------------------------------------------  
52\. POSTMORTEM  
\--------------------------------------------------

Todo incidente crítico deberá generar análisis posterior.

\--------------------------------------------------  
53\. MEJORA CONTINUA  
\--------------------------------------------------

Las métricas deberán utilizarse para optimizar la plataforma.

\--------------------------------------------------  
54\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia de monitoreo deberá crecer junto con el sistema.

\--------------------------------------------------  
54\. KPIs de Portales Administrativos
\--------------------------------------------------
Disponibilidad de React Administrador / Superadministrador.
Tiempo de respuesta de endpoints exclusivos de Superadministrador (reapertura, liquidación extraordinaria).
Intentos de acceso no autorizado a rutas administrativas (correlacionar con Documento 32 y Documento 42A).

\--------------------------------------------------  
55\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Todo componente crítico de Tu Mobil Amigo deberá ser observable, medible y auditable, permitiendo detectar riesgos operativos, financieros y de seguridad antes de que impacten al negocio o a los usuarios.  

Fin de Documento 42 — Monitoreo

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

Fin de Documento 42A — Catálogo de Alertas e Incidentes

\# Documento 43 — Operación

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el modelo operativo oficial para la administración, supervisión, soporte, mantenimiento y continuidad de Tu Mobil Amigo.

Este documento establece cómo deberá operarse la plataforma diariamente, mensualmente y anualmente.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

La operación deberá ser repetible, auditable, escalable y depender de procesos documentados, no de personas específicas.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Clientes;  
\- Asesores;  
\- Administradores;  
\- Superadministradores;  
\- Backend;  
\- Base de Datos;  
\- Infraestructura;  
\- Integraciones;  
\- Seguridad;  
\- Finanzas.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- continuidad operativa;  
\- estabilidad;  
\- soporte eficiente;  
\- crecimiento sostenible.

\--------------------------------------------------  
5\. MODELO OPERATIVO  
\--------------------------------------------------

La operación se divide en:

\`\`\`text  
Operación Diaria

Operación Semanal

Operación Mensual

Operación Anual  
\`\`\`

\--------------------------------------------------  
6\. OPERACIÓN DIARIA  
\--------------------------------------------------

Actividades obligatorias:

\- monitoreo;  
\- revisión de alertas;  
\- revisión de incidentes;  
\- validación de servicios críticos.

\--------------------------------------------------  
7\. VERIFICACIÓN DIARIA  
\--------------------------------------------------

Validar:

\- disponibilidad;  
\- APIs;  
\- Realtime;  
\- Base de Datos.

\--------------------------------------------------  
8\. INCIDENTES  
\--------------------------------------------------

Todo incidente deberá registrarse.

\--------------------------------------------------  
9\. CLASIFICACIÓN DE INCIDENTES  
\--------------------------------------------------

\`\`\`text  
Crítico

Alto

Medio

Bajo  
\`\`\`

\--------------------------------------------------  
10\. GESTIÓN DE INCIDENTES  
\--------------------------------------------------

Registrar:

\- fecha;  
\- responsable;  
\- impacto;  
\- resolución.

\--------------------------------------------------  
11\. OPERACIÓN SEMANAL  
\--------------------------------------------------

Actividades obligatorias:

\- revisión de métricas;  
\- revisión de seguridad;  
\- revisión financiera.

\--------------------------------------------------  
12\. CAPACIDAD  
\--------------------------------------------------

Analizar:

\- crecimiento;  
\- consumo;  
\- tendencias.

\--------------------------------------------------  
13\. AUDITORÍA OPERATIVA  
\--------------------------------------------------

Verificar:

\- accesos;  
\- cambios;  
\- eventos críticos.

\--------------------------------------------------  
14\. OPERACIÓN MENSUAL  
\--------------------------------------------------

Actividades obligatorias:

\- cierre operativo;  
\- conciliación;  
\- revisión financiera.

\--------------------------------------------------  
15\. CIERRE FINANCIERO  
\--------------------------------------------------

Validar:

\- liquidaciones;  
\- pagos;  
\- reportes.

\--------------------------------------------------  
16\. CORTE OFICIAL  
\--------------------------------------------------

El corte financiero oficial será:

\`\`\`text  
Último día del mes  
23:59:59  
\`\`\`

\--------------------------------------------------  
17\. GENERACIÓN DE LIQUIDACIONES  
\--------------------------------------------------

El sistema deberá ejecutar automáticamente:

\`\`\`text  
Liquidación Mensual  
\`\`\`

al cierre oficial.

\--------------------------------------------------  
18\. REPORTE DE LIQUIDACIÓN  
\--------------------------------------------------

El sistema deberá generar automáticamente:

\`\`\`text  
Excel Oficial de Liquidación  
\`\`\`

\--------------------------------------------------  
19\. CONTENIDO DEL REPORTE  
\--------------------------------------------------

Como mínimo:

\- usuario;  
\- cashback;  
\- multinivel nivel 1;  
\- multinivel nivel 2;  
\- incentivos;  
\- total a pagar.

\--------------------------------------------------  
20\. ESTADO DE LIQUIDACIÓN  
\--------------------------------------------------

Estados oficiales:

\`\`\`text  
Pendiente

Aprobada

Pagada

Rechazada

Anulada  
\`\`\`

\--------------------------------------------------  
21\. PLAZO DE PAGO  
\--------------------------------------------------

La empresa dispondrá de:

\`\`\`text  
5 días calendario  
\`\`\`

para ejecutar pagos posteriores al cierre.

\--------------------------------------------------  
22\. PAGOS  
\--------------------------------------------------

Todo pago deberá quedar auditado.

\--------------------------------------------------  
23\. LIQUIDACIÓN EXTRAORDINARIA  
\--------------------------------------------------

El sistema deberá permitir:

\- usuario individual;  
\- grupo específico;  
\- ciudad específica.

\--------------------------------------------------  
24\. REPROCESAMIENTO  
\--------------------------------------------------

Las liquidaciones deberán poder recalcularse de forma controlada.

\--------------------------------------------------  
25\. APROBACIÓN OPERATIVA  
\--------------------------------------------------

Toda liquidación extraordinaria requerirá autorización.

\--------------------------------------------------  
26\. SOPORTE  
\--------------------------------------------------

Todo caso deberá registrarse.

\--------------------------------------------------  
27\. NIVELES DE SOPORTE  
\--------------------------------------------------

\`\`\`text  
Nivel 1

Nivel 2

Nivel 3  
\`\`\`

\--------------------------------------------------  
28\. SOPORTE NIVEL 1  
\--------------------------------------------------

Atención operativa básica.

\--------------------------------------------------  
29\. SOPORTE NIVEL 2  
\--------------------------------------------------

Incidentes funcionales.

\--------------------------------------------------  
30\. SOPORTE NIVEL 3  
\--------------------------------------------------

Incidentes técnicos complejos.

\--------------------------------------------------  
31\. SEGURIDAD OPERATIVA  
\--------------------------------------------------

Verificar diariamente:

\- accesos;  
\- bloqueos;  
\- eventos sospechosos.

\--------------------------------------------------  
32\. ANTIFRAUDE  
\--------------------------------------------------

Revisar:

\- multicuentas;  
\- anomalías;  
\- alertas.

\--------------------------------------------------  
33\. DEVICE REGISTRY  
\--------------------------------------------------

Monitorear:

\- nuevos dispositivos;  
\- dispositivos bloqueados;  
\- cambios sospechosos.

\--------------------------------------------------  
34\. OPENSTREETMAP  
\--------------------------------------------------

Verificar:

\- disponibilidad;  
\- rendimiento.

\--------------------------------------------------  
35\. GRAPHHOPPER  
\--------------------------------------------------

Verificar:

\- disponibilidad;  
\- latencia.

\--------------------------------------------------  
36\. TELEGRAM  
\--------------------------------------------------

Verificar:

\- conectividad;  
\- errores;  
\- disponibilidad.

\--------------------------------------------------  
37\. BACKUPS  
\--------------------------------------------------

Verificar ejecución correcta.

\--------------------------------------------------  
38\. RECUPERACIÓN  
\--------------------------------------------------

Realizar pruebas periódicas de restauración.

\--------------------------------------------------  
39\. GESTIÓN DE CAMBIOS  
\--------------------------------------------------

Todo cambio deberá seguir proceso formal.

\--------------------------------------------------  
40\. DESPLIEGUES  
\--------------------------------------------------

Solo mediante procesos aprobados.

\--------------------------------------------------  
41\. POSTMORTEM  
\--------------------------------------------------

Todo incidente crítico deberá generar análisis posterior.

\--------------------------------------------------  
42\. DOCUMENTACIÓN  
\--------------------------------------------------

Toda modificación relevante deberá actualizar documentación.

\--------------------------------------------------  
43\. MÉTRICAS OPERATIVAS  
\--------------------------------------------------

Medir:

\- disponibilidad;  
\- incidentes;  
\- recuperación.

\--------------------------------------------------  
44\. INDICADORES FINANCIEROS  
\--------------------------------------------------

Medir:

\- liquidaciones;  
\- pagos;  
\- diferencias;  
\- conciliaciones.

\--------------------------------------------------  
45\. INDICADORES DE SEGURIDAD  
\--------------------------------------------------

Medir:

\- ataques;  
\- bloqueos;  
\- eventos críticos.

\--------------------------------------------------  
46\. INDICADORES DE CRECIMIENTO  
\--------------------------------------------------

Medir:

\- usuarios;  
\- asesores;  
\- servicios;  
\- ciudades.

\--------------------------------------------------  
47\. PLAN DE CONTINUIDAD  
\--------------------------------------------------

Mantener procedimientos actualizados.

\--------------------------------------------------  
48\. PLAN DE CONTINGENCIA  
\--------------------------------------------------

Mantener procedimientos alternos documentados.

\--------------------------------------------------  
49\. ERP FUTURO  
\--------------------------------------------------

La operación deberá contemplar integración futura con sistemas ERP.

\--------------------------------------------------  
50\. PSE FUTURO  
\--------------------------------------------------

La operación deberá contemplar integración futura con pasarelas de pago y PSE.

\--------------------------------------------------  
51\. GESTIÓN DE PROVEEDORES  
\--------------------------------------------------

Registrar y monitorear proveedores tecnológicos críticos.

\--------------------------------------------------  
52\. CUMPLIMIENTO  
\--------------------------------------------------

Toda operación deberá cumplir políticas internas y requisitos regulatorios.

\--------------------------------------------------  
53\. MEJORA CONTINUA  
\--------------------------------------------------

La operación deberá revisarse periódicamente para identificar mejoras.

\--------------------------------------------------  
54\. EVOLUCIÓN  
\--------------------------------------------------

Los procesos operativos deberán evolucionar junto con la plataforma.

\--------------------------------------------------  
54\. Procedimiento Operativo: Reapertura de Período  
\--------------------------------------------------
1. El Superadministrador identifica la necesidad de reapertura y documenta la justificación.
2. El sistema valida rol y bloquea si el usuario no es Superadministrador (ver Documento 39, CP-SA-003).
3. El sistema registra evento de auditoría con justificación, período afectado y usuario ejecutor (ver Documento 35, Sección 34).
4. Se ejecuta el recálculo (ver Documento 33A, Secciones 34-37).
5. Se conserva evidencia del cierre anterior y del nuevo cierre, ambos accesibles desde el Centro de Liquidaciones (Documento 28, Sección 39).
6. Se notifica a los administradores afectados por el recálculo.

\--------------------------------------------------  
55\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La operación de Tu Mobil Amigo deberá garantizar continuidad, seguridad, estabilidad financiera, trazabilidad y capacidad de crecimiento, permitiendo administrar la plataforma durante años de forma controlada y sostenible.  

Fin de Documento 43 — Operación
