\# Documento 29 — Gestión de Estado

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial de gestión de estado para las aplicaciones Flutter del ecosistema Tu Mobil Amigo.

Este documento establece:

\- Flujo de datos.  
\- Estado local.  
\- Estado global.  
\- Estado remoto.  
\- Caché.  
\- Realtime.  
\- Invalidación.  
\- Rendimiento.  
\- Escalabilidad.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

La aplicación nunca será la fuente oficial de información.

La única fuente de verdad será:

PostgreSQL

Todo estado en Flutter será considerado temporal.

\--------------------------------------------------  
3\. TECNOLOGÍA OFICIAL  
\--------------------------------------------------

Se aprueba:

Riverpod

como solución oficial de gestión de estado.

\--------------------------------------------------  
4\. JUSTIFICACIÓN  
\--------------------------------------------------

Riverpod proporciona:

\- Bajo acoplamiento.  
\- Alta testabilidad.  
\- Modularidad.  
\- Escalabilidad.  
\- Compatibilidad con Clean Architecture.

\--------------------------------------------------  
5\. CLASIFICACIÓN DEL ESTADO  
\--------------------------------------------------

La aplicación manejará cuatro tipos de estado:

\- Estado Local.  
\- Estado Global.  
\- Estado Remoto.  
\- Estado de Sesión.

\--------------------------------------------------  
6\. ESTADO LOCAL  
\--------------------------------------------------

Responsable de:

\- Controles UI.  
\- Modales.  
\- Filtros.  
\- Inputs.  
\- Estados visuales.

Ejemplos:

\- Loading.  
\- Error.  
\- Modal abierto.  
\- Tab seleccionada.

Las preferencias visuales podrán persistirse localmente mediante SharedPreferences sin sincronización con Backend.

\--------------------------------------------------  
7\. ESTADO GLOBAL  
\--------------------------------------------------

Responsable de:

\- Usuario autenticado.  
\- Rol.  
\- Configuración.  
\- Permisos.  
\- Notificaciones.

\--------------------------------------------------  
8\. ESTADO REMOTO  
\--------------------------------------------------

Responsable de:

\- Servicios.  
\- Ofertas.  
\- Contraofertas.  
\- Wallet.  
\- Trust.  
\- IMF.  
\- Cashback.

Proviene exclusivamente del Backend.

\--------------------------------------------------  
9\. ESTADO DE SESIÓN  
\--------------------------------------------------

Contendrá:

\- Token.  
\- Usuario.  
\- Permisos.  
\- Configuración inicial.

\--------------------------------------------------  
10\. PRINCIPIO DE INMUTABILIDAD  
\--------------------------------------------------

Los estados deberán tratarse como inmutables.

Toda modificación generará una nueva instancia.

\--------------------------------------------------  
11\. PROVIDERS OFICIALES  
\--------------------------------------------------

Tipos permitidos:

Provider

StateProvider

FutureProvider

StreamProvider

NotifierProvider

AsyncNotifierProvider

\--------------------------------------------------  
12\. PROHIBICIONES  
\--------------------------------------------------

No se permitirá:

\- Variables globales.  
\- Singletons manuales.  
\- Estado compartido sin Provider.

\--------------------------------------------------  
13\. FLUJO OFICIAL  
\--------------------------------------------------

UI

↓

Provider

↓

Repository

↓

Datasource

↓

API

↓

Backend

\--------------------------------------------------  
14\. REPOSITORIOS  
\--------------------------------------------------

Los Providers nunca accederán directamente a APIs.

Siempre utilizarán:

Repositories

\--------------------------------------------------  
15\. CACHE  
\--------------------------------------------------

La aplicación podrá almacenar temporalmente:

\- Configuración.  
\- Catálogos.  
\- Datos de consulta.

Nunca información crítica.

\--------------------------------------------------  
16\. DATOS PROHIBIDOS EN CACHE  
\--------------------------------------------------

No podrán almacenarse:

\- Trust Oficial.  
\- IMF Oficial.  
\- Cashback Oficial.  
\- Liquidaciones.  
\- Información financiera crítica.

La fuente oficial será siempre Backend.

\--------------------------------------------------  
17\. INVALIDACIÓN DE CACHE  
\--------------------------------------------------

La invalidación será automática cuando:

\- Exista actualización Realtime.  
\- Exista cambio de sesión.  
\- Exista modificación de datos.

\--------------------------------------------------  
18\. REALTIME  
\--------------------------------------------------

Realtime será utilizado para:

\- Nuevos servicios.  
\- Nuevas ofertas.  
\- Contraofertas.  
\- Cambios de estado.  
\- Notificaciones operativas.

\--------------------------------------------------  
19\. REGLA REALTIME  
\--------------------------------------------------

Realtime no reemplaza Backend.

Realtime únicamente notifica cambios.

Posteriormente:

Flutter

↓

API

↓

Backend

↓

Datos actualizados

\--------------------------------------------------  
20\. REFRESH MANUAL  
\--------------------------------------------------

Toda pantalla crítica deberá soportar:

Pull To Refresh

\--------------------------------------------------  
21\. POLÍTICA DE REINTENTOS  
\--------------------------------------------------

Errores temporales deberán soportar:

\- Retry automático.  
\- Retry manual.

\--------------------------------------------------  
22\. ESTADOS ESTÁNDAR  
\--------------------------------------------------

Todo Provider asíncrono deberá contemplar:

Loading

Success

Error

Empty

\--------------------------------------------------  
23\. MANEJO DE ERRORES  
\--------------------------------------------------

Los errores deberán clasificarse como:

NetworkError

ValidationError

BusinessError

SecurityError

UnknownError

\--------------------------------------------------  
24\. CONFIGURACIÓN DINÁMICA  
\--------------------------------------------------

La aplicación cargará desde Backend:

\- Parámetros.  
\- Configuraciones.  
\- Límites.  
\- Reglas.

Nunca desde constantes hardcodeadas.

\--------------------------------------------------  
25\. NOTIFICACIONES  
\--------------------------------------------------

Las notificaciones deberán actualizar:

\- Providers.  
\- Caché.  
\- Estado visual.

sin reiniciar la aplicación.

\--------------------------------------------------  
26\. MULTIROL  
\--------------------------------------------------

El estado deberá soportar:

Cliente

Asesor

sin duplicar lógica.

\--------------------------------------------------  
27\. CAMBIO DE SESIÓN  
\--------------------------------------------------

Al cerrar sesión deberá limpiarse:

\- Cache.  
\- Providers.  
\- Tokens.  
\- Datos temporales.

\--------------------------------------------------  
28\. SEGURIDAD  
\--------------------------------------------------

Los Providers no almacenarán:

\- API Keys.  
\- Secrets.  
\- Service Keys.  
\- Credenciales de terceros.

\--------------------------------------------------  
29\. PERFORMANCE  
\--------------------------------------------------

Evitar:

\- Rebuilds innecesarios.  
\- Consultas repetidas.  
\- Providers gigantes.

\--------------------------------------------------  
30\. OBSERVABILIDAD  
\--------------------------------------------------

Toda excepción crítica deberá registrarse para:

\- Auditoría.  
\- Diagnóstico.  
\- Monitoreo.

\--------------------------------------------------  
31\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura deberá soportar:

\- Nuevos módulos.  
\- Nuevos servicios.  
\- Nuevos países.  
\- Nuevos roles.

sin rediseño.

\--------------------------------------------------  
32\. FUTURA COMPATIBILIDAD OFFLINE  
\--------------------------------------------------

Aunque la V1 no soportará operación offline completa, la arquitectura deberá permitir incorporar posteriormente:

\- Caché persistente.  
\- Cola de sincronización.  
\- Reintentos diferidos.

sin modificar la estructura principal.

\--------------------------------------------------  
33\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La gestión de estado deberá permanecer simple, predecible, desacoplada y centrada en Riverpod, garantizando que PostgreSQL continúe siendo la única fuente oficial de verdad y evitando que Flutter almacene lógica de negocio o información crítica fuera del Backend.  
