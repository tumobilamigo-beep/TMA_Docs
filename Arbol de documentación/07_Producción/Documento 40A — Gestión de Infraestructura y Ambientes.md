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
