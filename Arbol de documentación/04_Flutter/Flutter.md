Flutter

# **Documento 27 — Arquitectura Flutter**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura oficial de las aplicaciones cliente desarrolladas en Flutter para el ecosistema Tu Mobil Amigo.

Este documento establece:

* estructura del proyecto;  
* capas de aplicación;  
* responsabilidades;  
* comunicación con Backend;  
* gestión de estado;  
* seguridad;  
* escalabilidad;  
* mantenibilidad.

---

# **2\. Principios Arquitectónicos**

La aplicación deberá cumplir:

* Clean Architecture.  
* Modularidad.  
* Bajo acoplamiento.  
* Alta cohesión.  
* Escalabilidad.  
* Testabilidad.  
* Seguridad.  
* Reutilización.

---

# **3\. Plataformas Objetivo**

Flutter será la tecnología oficial para:

Android  
iOS  
Windows  
Web (opcional)  
---

# **4\. Estrategia Oficial**

Se aprueba:

Flutter

para:

* Cliente.  
* Asesor.

---

Se aprueba:

React

para:

* Portal Administrativo.  
* Portal Superadministrador.

---

# **5\. Justificación**

Cliente y Asesor requieren:

* GPS.  
* Cámara.  
* QR.  
* Notificaciones Push.  
* Operación móvil.

Flutter es superior para estos escenarios.

---

Administración requiere:

* Dashboards.  
* Reportes.  
* Excel.  
* Gestión operativa.  
* Auditoría.

React es superior para estos escenarios.

---

# **6\. Aplicaciones Oficiales**

## **App Cliente**

Responsable de:

* solicitar servicios;  
* programar servicios;  
* negociar ofertas;  
* consultar cashback;  
* consultar multinivel;  
* consultar IMF;  
* consultar Trust.

---

## **App Asesor**

Responsable de:

* recibir oportunidades;  
* ofertar;  
* contraofertar;  
* registrar servicios en calle;  
* consultar ganancias;  
* consultar métricas.

---

# **7\. Estructura Base**

lib/

├── core/  
├── shared/  
├── features/  
├── services/  
├── routes/  
├── app/  
└── main.dart  
---

# **8\. Core**

Contiene componentes globales.

core/

config/  
constants/  
errors/  
security/  
theme/  
utils/  
---

# **9\. Shared**

Componentes reutilizables.

shared/

widgets/  
models/  
components/  
extensions/  
---

# **10\. Features**

Organización por dominio.

features/

auth/  
services/  
wallet/  
multilevel/  
trust/  
imf/  
profile/  
notifications/  
---

# **11\. Regla de Organización**

Se prohíbe organizar por tipo técnico.

Incorrecto:

screens/  
controllers/  
providers/

Correcto:

features/auth/

features/services/

features/wallet/  
---

# **12\. Arquitectura Interna por Feature**

feature/

data/  
domain/  
presentation/  
---

# **13\. Capa Domain**

Contendrá:

* entidades;  
* casos de uso;  
* contratos;  
* reglas de negocio cliente.

---

# **14\. Capa Data**

Contendrá:

* repositories;  
* datasources;  
* DTOs;  
* adapters.

---

# **15\. Capa Presentation**

Contendrá:

* pantallas;  
* widgets;  
* providers;  
* controladores UI.

---

# **16\. Comunicación**

Toda comunicación deberá seguir:

Flutter

↓

API

↓

Backend

↓

PostgreSQL  
---

# **17\. Regla Arquitectónica**

Prohibido:

Flutter

↓

Base de Datos  
---

# **18\. Integraciones Externas**

Prohibido:

Flutter

↓

Proveedor Externo  
---

Obligatorio:

Flutter

↓

API Tu Mobil Amigo

↓

Proveedor Externo  
---

# **19\. Gestión de Estado**

Tecnología oficial:

Riverpod  
---

Justificación:

* rendimiento;  
* testabilidad;  
* desacoplamiento;  
* escalabilidad.

---

# **20\. Navegación**

Tecnología oficial:

GoRouter  
---

# **21\. Inyección de Dependencias**

Toda dependencia deberá registrarse mediante:

Provider

o mecanismos compatibles con Riverpod.

---

# **22\. Manejo de Errores**

Se implementará un sistema centralizado.

Tipos:

NetworkError

ValidationError

SecurityError

BusinessError

UnknownError  
---

# **23\. Configuración**

Toda configuración provendrá del Backend.

Prohibido hardcodear:

* porcentajes;  
* cashback;  
* IMF;  
* tarifas;  
* Trust;  
* categorías;  
* límites.

---

# **24\. Seguridad**

La aplicación nunca almacenará:

* claves privadas;  
* secrets;  
* service keys;  
* credenciales de terceros.

---

# **25\. Gestión de Tokens**

Los tokens deberán almacenarse mediante almacenamiento seguro del sistema operativo.

Ejemplos:

Android Keystore

iOS Keychain  
---

# **26\. Modo Offline**

Versión inicial:

No soportado  
---

Motivo:

Evitar complejidad innecesaria durante el lanzamiento.

---

# **27\. Notificaciones**

Proveedor aprobado:

Firebase Cloud Messaging  
---

Tipos:

* servicios;  
* ofertas;  
* pagos;  
* seguridad;  
* liquidaciones.

---

# **28\. Geolocalización**

Proveedor inicial aprobado:

OpenStreetMap  
\+  
GraphHopper  
---

Motivos:

* bajo costo;  
* independencia;  
* escalabilidad inicial.

---

# **29\. Evolución Cartográfica**

La arquitectura deberá permitir migrar posteriormente a:

MapTiler

o

Tile Server Propio

sin modificar la aplicación.

---

# **30\. QR**

La aplicación soportará:

* lectura QR;  
* generación QR;  
* validación QR.

---

Aplicaciones:

* servicios en calle;  
* validaciones;  
* antifraude.

---

# **31\. Auditoría**

Toda acción crítica deberá generar trazabilidad.

Ejemplos:

* login;  
* oferta;  
* contraoferta;  
* pago;  
* retiro.

---

# **32\. Performance**

Objetivos iniciales:

Inicio \< 3 segundos

Carga pantallas \< 2 segundos

Acciones críticas \< 1 segundo

Valores ajustables posteriormente.

---

# **33\. Testing**

Toda feature deberá soportar:

* Unit Testing.  
* Widget Testing.  
* Integration Testing.

---

# **34\. Escalabilidad**

La arquitectura deberá permitir incorporar:

* nuevos países;  
* nuevas ciudades;  
* nuevos servicios;  
* nuevos idiomas;  
* nuevas monedas.

Sin rediseño.

---

# **35\. Compatibilidad Empresarial**

La arquitectura deberá permitir futuras integraciones con:

ERP

CRM

BI

Analytics

sin modificar la estructura principal de la aplicación.

---

# **36\. Roles Soportados**

Roles oficiales:

Cliente

Asesor

Administrador (Portal React)

Superadministrador (Portal React)

Flutter no implementará interfaces administrativas.

---

### **Soporte de Temas**

La arquitectura deberá soportar:

Light Theme  
Dark Theme

mediante:

ThemeData  
ThemeExtensions

centralizados.

### **Preferencias Visuales Locales**

Las preferencias exclusivamente visuales podrán almacenarse localmente en el dispositivo cuando no afecten reglas de negocio, auditoría, seguridad u operación.

Ejemplos:

Tema claro

Tema oscuro  
Tema automático

# **37\. Principio Rector Final**

> La arquitectura Flutter de Tu Mobil Amigo deberá mantenerse ligera, modular, segura y desacoplada, enfocándose exclusivamente en la experiencia operativa de clientes y asesores, mientras toda la lógica crítica de negocio, seguridad, liquidaciones, motores financieros y reglas corporativas permanecen centralizadas en Backend y Base de Datos.

Fin de Documento 27 — Arquitectura Flutter

\# Documento 28 — Arquitectura React (Administrador y Superadministrador)

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la arquitectura oficial de los portales web de:

\- Administrador  
\- Superadministrador

utilizando React como tecnología principal.

Este documento establece:

\- Estructura de la solución.  
\- Módulos funcionales.  
\- Seguridad.  
\- Auditoría.  
\- Gestión financiera.  
\- Configuración del sistema.  
\- Escalabilidad.  
\- Integración con Backend.

\--------------------------------------------------  
2\. ALCANCE  
\--------------------------------------------------

La arquitectura React será utilizada exclusivamente para:

Administrador  
Superadministrador

No será utilizada para:

Cliente  
Asesor

Los roles operativos permanecerán en Flutter.

\--------------------------------------------------  
3\. PRINCIPIO ARQUITECTÓNICO  
\--------------------------------------------------

React será responsable únicamente de:

\- Visualización.  
\- Administración.  
\- Configuración.  
\- Monitoreo.  
\- Auditoría.  
\- Reportes.

Toda lógica crítica permanecerá en:

\- PostgreSQL.  
\- Edge Functions.  
\- Backend.

\--------------------------------------------------  
4\. STACK OFICIAL  
\--------------------------------------------------

Frontend  
React  
Lenguaje  
TypeScript  
UI  
Material UI  
Routing  
React Router  
Estado  
TanStack Query  
Formularios  
React Hook Form  
Validaciones  
Zod  
Tablas  
AG Grid  
Gráficas  
Recharts  
Exportaciones  
ExcelJS

\--------------------------------------------------  
5\. ESTRUCTURA OFICIAL  
\--------------------------------------------------

src/  
app/  
core/  
features/

shared/  
layouts/  
routes/  
services/

\--------------------------------------------------  
6\. CORE  
\--------------------------------------------------

Contendrá:

config/  
security/  
permissions/  
constants/  
utils/

\--------------------------------------------------  
7\. SHARED  
\--------------------------------------------------

Componentes reutilizables.

shared/

components/  
tables/  
forms/  
dialogs/  
charts/

\--------------------------------------------------  
8\. FEATURES  
\--------------------------------------------------

Organización por dominio.

features/  
dashboard/  
usuarios/  
asesores/  
servicios/  
finanzas/  
multinivel/  
trust/  
imf/  
fraude/

liquidaciones/  
integraciones/  
configuracion/  
auditoria/

\--------------------------------------------------  
9\. ROLES OFICIALES  
\--------------------------------------------------

Administrador  
Superadministrador

\--------------------------------------------------  
10\. ADMINISTRADOR  
\--------------------------------------------------

Podrá gestionar:

\- Usuarios.  
\- Asesores.  
\- Servicios.  
\- Recargas.  
\- Retiros.  
\- Liquidaciones.  
\- Soporte.  
\- Reportes.

No podrá modificar:

\- Motores financieros.  
\- Trust.  
\- IMF.  
\- Antifraude.  
\- Variables globales.

\--------------------------------------------------  
11\. SUPERADMINISTRADOR  
\--------------------------------------------------

Podrá gestionar:

\- Todo el ecosistema.  
\- Administradores.  
\- Parámetros globales.  
\- Configuraciones financieras.  
\- Integraciones.  
\- Seguridad.  
\- Auditoría.  
\- Motores del sistema.

\--------------------------------------------------  
12\. DASHBOARD CORPORATIVO  
\--------------------------------------------------

Indicadores mínimos:

\- Usuarios activos.  
\- Asesores activos.  
\- Servicios del día.  
\- Servicios del mes.  
\- Ingresos.  
\- Cashback generado.  
\- Comisiones multinivel.  
\- Liquidaciones pendientes.  
\- Trust promedio.  
\- Riesgos detectados.

\--------------------------------------------------  
13\. GESTIÓN DE USUARIOS  
\--------------------------------------------------

Funciones:

\- Crear.  
\- Consultar.  
\- Suspender.  
\- Reactivar.  
\- Auditar.

\--------------------------------------------------  
14\. GESTIÓN DE ASESORES  
\--------------------------------------------------

Funciones:

\- Aprobar.  
\- Suspender.  
\- Bloquear.  
\- Auditar.

Visualización:

\- Trust.  
\- IMF.  
\- Servicios.  
\- Ingresos.

\--------------------------------------------------  
15\. GESTIÓN DE SERVICIOS  
\--------------------------------------------------

Consulta completa de:

\- Inmediatos.  
\- Programados.

Estados:

\- Creado.  
\- Ofertado.  
\- Negociación.  
\- Aceptado.  
\- Finalizado.  
\- Cancelado.

\--------------------------------------------------  
16\. GESTIÓN FINANCIERA  
\--------------------------------------------------

Módulos:

\- Recargas.  
\- Retiros.  
\- Cashback.  
\- Comisiones.  
\- Liquidaciones.

\--------------------------------------------------  
17\. LIQUIDACIONES MENSUALES  
\--------------------------------------------------

Visualización:

\- Pendientes.  
\- Pagadas.  
\- Vencidas.

Exportación:

Excel  
PDF  
CSV

\--------------------------------------------------  
18\. MULTINIVEL  
\--------------------------------------------------

Visualización:

\- Árbol.  
\- Comisiones.  
\- Acumulados.  
\- Históricos.

\--------------------------------------------------  
19\. TRUST SCORE  
\--------------------------------------------------

Visualización:

\- Score actual.  
\- Historial.  
\- Componentes.

\--------------------------------------------------  
20\. IMF  
\--------------------------------------------------

Visualización:

\- Categoría.  
\- Evolución.  
\- Liberaciones.

\--------------------------------------------------  
21\. MOTOR ANTIFRAUDE  
\--------------------------------------------------

Visualización:

\- Eventos.  
\- Alertas.  
\- Riesgos.

Acciones:

\- Revisar.  
\- Escalar.  
\- Bloquear.

\--------------------------------------------------  
22\. AUDITORÍA  
\--------------------------------------------------

Toda acción administrativa deberá quedar registrada.

Ejemplos:

\- Login.  
\- Cambio de parámetros.  
\- Bloqueos.  
\- Pagos.  
\- Liquidaciones.

\--------------------------------------------------  
23\. CONFIGURACIÓN DEL SISTEMA  
\--------------------------------------------------

Todos los parámetros deberán administrarse desde interfaz.

Prohibido:  
Hardcodear valores.

\--------------------------------------------------  
24\. PARÁMETROS TARIFARIOS  
\--------------------------------------------------

Administración completa de:

\- Ciudades.  
\- Tarifas.  
\- Factores.  
\- Decretos.

Todos los valores se almacenan en Base de Datos.

Nunca en código.

\--------------------------------------------------  
25\. CONFIGURACIÓN FINANCIERA  
\--------------------------------------------------

Administración de:

\- Empresa.  
\- Cashback.  
\- Nivel 1\.  
\- Nivel 2\.  
\- Reserva.

\--------------------------------------------------  
26\. CONFIGURACIÓN DE PROGRAMACIÓN  
\--------------------------------------------------

Administración de:

\- Anticipación mínima.  
\- Anticipación máxima.  
\- Incentivos.

Valores aprobados:

Mínimo:  
2 horas

Máximo:  
12 horas

\--------------------------------------------------  
27\. CONFIGURACIÓN DE OFERTAS  
\--------------------------------------------------

Administración de:

Expiración de ofertas.

Valor inicial:

180 segundos

Configurable desde Base de Datos.

\--------------------------------------------------  
28\. CONFIGURACIÓN DE CONTRAOFERTAS  
\--------------------------------------------------

Administración de:  
Expiración de contraofertas.  
Valor inicial:  
180 segundos  
Configurable desde Base de Datos.

\--------------------------------------------------  
29\. INTEGRACIONES  
\--------------------------------------------------

Visualización y monitoreo de:

\- Telegram.  
\- Firebase.  
\- OpenStreetMap.  
\- GraphHopper.  
\- ERP.  
\- Pasarelas de pago.

\--------------------------------------------------  
30\. ERP FUTURO  
\--------------------------------------------------

Preparado para integración con:

\- Siigo.  
\- Alegra.  
\- Odoo.  
\- SAP Business One.  
\- World Office.

\--------------------------------------------------  
31\. SEGURIDAD  
\--------------------------------------------------

Prohibido almacenar:

\- Passwords.  
\- Tokens.  
\- Secrets.  
\- API Keys.

en frontend.

\--------------------------------------------------  
32\. AUTORIZACIÓN  
\--------------------------------------------------

Modelo:

RBAC

Roles:

Administrador  
Superadministrador

\--------------------------------------------------  
33\. DOBLE FACTOR  
\--------------------------------------------------

Obligatorio para:

\- Superadministrador.

Recomendado para:

\- Administrador.

\--------------------------------------------------  
34\. EXPORTACIONES  
\--------------------------------------------------

Formatos soportados:

\- Excel.  
\- PDF.  
\- CSV.

\--------------------------------------------------  
35\. REPORTE OFICIAL DE LIQUIDACIÓN  
\--------------------------------------------------

El sistema deberá generar:

Liquidación Mensual Oficial

incluyendo:

\- Usuario.  
\- Ciudad.  
\- Trust.  
\- IMF.  
\- Cashback.  
\- Nivel 1\.  
\- Nivel 2\.  
\- Incentivos.  
\- Total.

\--------------------------------------------------  
36\. MONITOREO  
\--------------------------------------------------

Visualización:

\- Salud del sistema.  
\- APIs.  
\- Realtime.  
\- Integraciones.

\--------------------------------------------------  
37\. ESCALABILIDAD  
\--------------------------------------------------

La arquitectura deberá soportar:

\- Nuevos países.  
\- Nuevas ciudades.  
\- Nuevos servicios.  
\- Nuevas monedas.

sin rediseño.

\--------------------------------------------------  
38\. LIQUIDACIÓN EXTRAORDINARIA  
\--------------------------------------------------

visible únicamente para:

Superadministrador

\--------------------------------------------------  
39\. Centro de Liquidaciones  
\--------------------------------------------------

con:

* Simulación.  
* Aprobación.  
* Ejecución.  
* Pago  
* Historial.

\--------------------------------------------------  
40\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Los portales React serán responsables exclusivamente de la administración, gobierno, auditoría y supervisión del ecosistema Tu Mobil Amigo.

Toda lógica crítica de negocio, motores financieros, reglas de seguridad, antifraude, multinivel, Trust, IMF y liquidaciones permanecerá centralizada en PostgreSQL y Backend para garantizar integridad, trazabilidad y seguridad empresarial.  

Fin de Documento 28 — Arquitectura React (Administrador y Superadministrador)

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

Fin de Documento 29 — Gestión de Estado

# **Documento 30 — UI Kit**

Versión: 1.0  
 Estado: Aprobado  
 Proyecto: Tu Mobil Amigo V1.0

---

## **1\. Objetivo**

Definir el sistema visual oficial de Tu Mobil Amigo para garantizar:

* Consistencia visual.  
* Escalabilidad.  
* Accesibilidad.  
* Reutilización.  
* Uniformidad entre Cliente y Asesor.

---

## **2\. Principios de Diseño**

La interfaz deberá ser:

* Clara.  
* Rápida.  
* Minimalista.  
* Operativa.  
* Escalable.

Priorizar:

Velocidad de uso  
\>  
Cantidad de elementos visuales  
---

## **3\. Identidad Corporativa**

### **Azul Corporativo**

Aprobado previamente:

\#002B5B

Uso:

* Header.  
* Botones primarios.  
* Navegación.

---

### **Celeste Corporativo**

\#00AEEF

Uso:

* Indicadores.  
* Estados activos.  
* Resaltados.

---

### **Blanco**

\#FFFFFF

Uso:

* Fondo principal.

---

### **Gris Claro**

\#F5F7FA

Uso:

* Tarjetas.  
* Contenedores.  
* Formularios.

---

## **4\. Colores de Estado**

### **Éxito**

\#22C55E  
---

### **Advertencia**

\#F59E0B  
---

### **Error**

\#EF4444  
---

### **Información**

\#3B82F6  
---

## **5\. Tipografía Oficial**

Flutter:

Google Fonts

Fuente principal:

Inter  
---

## **6\. Jerarquía Tipográfica**

### **Título Principal**

32 px  
Bold  
---

### **Título Secundario**

24 px  
SemiBold  
---

### **Título de Sección**

20 px  
SemiBold  
---

### **Texto Normal**

16 px  
Regular  
---

### **Texto Auxiliar**

14 px  
Regular  
---

## **7\. Grid Base**

Sistema:

8 px

Todos los espacios deberán ser múltiplos de:

8  
---

## **8\. Border Radius**

Estándar:

12 px  
---

## **9\. Sombras**

Utilizar sombras suaves.

Evitar:

Sombras agresivas  
---

## **10\. Botones**

### **Primario**

Color:

\#002B5B

Texto blanco.

---

### **Secundario**

Borde azul.

Fondo transparente.

---

### **Terciario**

Solo texto.

---

## **11\. Campos de Entrada**

Todos los formularios deberán incluir:

* Label.  
* Placeholder.  
* Mensaje de error.  
* Validación visual.

---

## **12\. Tarjetas**

Uso obligatorio para:

* Servicios.  
* Ofertas.  
* Wallet.  
* Cashback.  
* Liquidaciones.

---

## **13\. Navegación Inferior**

Máximo:

5 elementos  
---

## **14\. Iconografía**

Biblioteca oficial:

Material Symbols  
---

## **15\. Estados de Carga**

Todo proceso asíncrono deberá mostrar:

* Skeleton.  
* Loader.  
* Indicador visual.

---

## **16\. Estados Vacíos**

Toda pantalla deberá contemplar:

Sin datos  
---

## **17\. Estados de Error**

Toda pantalla deberá contemplar:

Error recuperable  
---

## **18\. Accesibilidad**

Soporte mínimo:

* Contraste AA.  
* Escalado de fuentes.  
* Lectores de pantalla.

---

## **19\. Responsive**

Diseño oficial:

### **Mobile First**

Objetivo principal:

Android  
iOS  
---

## **20\. Trust Score**

Representación visual:

0 \- 100

mediante:

* color;  
* barra;  
* porcentaje.

---

## **21\. IMF**

Representación visual:

Categorías:

Bronce  
Plata  
Oro  
Platino  
Diamante  
---

## **22\. Wallet**

Visualización obligatoria:

* Saldo disponible.  
* Saldo pendiente.  
* Cashback acumulado.  
* Próxima liquidación.

---

## **23\. Servicios Programados**

Indicador visual especial:

PROGRAMADO

con distintivo visual.

---

## **24\. Servicios en Calle**

Indicador visual:

SERVICIO EN CALLE  
---

## **25\. Liquidaciones**

Visualización obligatoria:

* Pendiente.  
* Procesada.  
* Pagada.

---

## **26\. Notificaciones**

Clasificación:

* Operativas.  
* Financieras.  
* Seguridad.  
* Sistema.

---

## **27\. Animaciones**

Regla:

Animaciones sutiles

Prohibido:

Animaciones decorativas excesivas  
---

## **28\. Modo Oscuro**

El sistema soportará desde la V1:

Modo Claro

Modo Oscuro

---

### **Selección**

El usuario podrá elegir manualmente:

Claro

Oscuro

Automático

---

### **Modo Automático**

El sistema podrá adoptar automáticamente la configuración del dispositivo.

---

### **Persistencia**

La preferencia deberá almacenarse en:

perfil\_usuario

para mantener consistencia entre sesiones.

---

### **Principio de Diseño**

El modo oscuro no consistirá únicamente en invertir colores.

Cada componente deberá tener una definición específica.

---

### **Paleta Oscura Oficial**

#### **Fondo Principal**

\#121212

---

#### **Fondo Secundario**

\#1E1E1E

---

#### **Tarjetas**

\#242424

---

#### **Texto Principal**

\#FFFFFF

---

#### **Texto Secundario**

\#D1D5DB

---

#### **Azul Corporativo**

Se mantiene:

\#002B5B

ajustando contraste cuando sea necesario.

---

#### **Celeste Corporativo**

Se mantiene:

\#00AEEF

---

### **Componentes Obligatorios**

Todos los componentes deberán soportar:

* Light Theme.  
* Dark Theme.

Incluyendo:

* Wallet.  
* Trust.  
* IMF.  
* Servicios.  
* Ofertas.  
* Liquidaciones.  
* Notificaciones.  
* QR.  
* Formularios.

---

### **Restricción Arquitectónica**

Prohibido utilizar:

Colors.white

Colors.black

directamente dentro de Widgets.

Toda referencia visual deberá provenir de:

ThemeData

ColorScheme

ThemeExtensions

---

## **29\. Internacionalización**

Arquitectura preparada para:

* Español.  
* Inglés.  
* Portugués.

---

## **30\. Consistencia**

Todo componente deberá construirse utilizando:

ThemeData

centralizado.

Prohibido definir estilos visuales directamente en pantallas.

---

## **31\. Principio Rector Final**

> La interfaz de Tu Mobil Amigo deberá priorizar rapidez operativa, claridad visual y consistencia, garantizando una experiencia simple para clientes y asesores, evitando complejidad visual innecesaria y manteniendo una identidad corporativa uniforme en toda la plataforma.


Fin de Documento 30 — UI Kit

\# Documento 31 — Componentes

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el catálogo oficial de componentes reutilizables para las aplicaciones Flutter de Tu Mobil Amigo.

Este documento busca:

\- Reducir duplicidad.  
\- Mejorar mantenibilidad.  
\- Aumentar consistencia visual.  
\- Disminuir deuda técnica.  
\- Facilitar escalabilidad.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo elemento visual reutilizable deberá convertirse en componente.  
Prohibido duplicar código visual entre módulos.

\--------------------------------------------------  
3\. ORGANIZACIÓN OFICIAL  
\--------------------------------------------------

shared/  
components/  
atoms/  
molecules/  
organisms/  
templates/

\--------------------------------------------------  
4\. CLASIFICACIÓN  
\--------------------------------------------------

Atoms  
Elementos básicos.  
Molecules  
Conjunto pequeño de atoms.

Organisms  
Componentes complejos.  
Templates  
Estructuras completas.

\--------------------------------------------------  
5\. ATOMS  
\--------------------------------------------------

Componentes mínimos reutilizables.

\--------------------------------------------------  
6\. APP BUTTON  
\--------------------------------------------------

Responsable de:

\- acciones primarias;  
\- secundarias;  
\- terciarias.

Variantes:

Primary  
Secondary  
Text  
Danger  
Success

\--------------------------------------------------  
7\. APP INPUT  
\--------------------------------------------------

Campos de entrada estándar.

Soporte:

\- texto;  
\- email;  
\- teléfono;  
\- numérico;  
\- contraseña.

\--------------------------------------------------  
8\. APP DROPDOWN  
\--------------------------------------------------

Listas desplegables reutilizables.

\--------------------------------------------------  
9\. APP CHECKBOX  
\--------------------------------------------------

Selección múltiple.

\--------------------------------------------------  
10\. APP RADIO  
\--------------------------------------------------

Selección única.

\--------------------------------------------------  
11\. APP SWITCH  
\--------------------------------------------------

Activación de opciones.

\--------------------------------------------------  
12\. APP LOADER  
\--------------------------------------------------

Indicadores de carga.

\--------------------------------------------------  
13\. APP BADGE  
\--------------------------------------------------

Etiquetas visuales.

Ejemplos:

\- Programado  
\- Nuevo  
\- Pendiente  
\- Pagado

\--------------------------------------------------  
14\. APP AVATAR  
\--------------------------------------------------

Representación visual de usuario.

\--------------------------------------------------  
15\. APP ICON  
\--------------------------------------------------

Wrapper oficial para iconografía.

\--------------------------------------------------  
16\. APP DIVIDER  
\--------------------------------------------------

Separadores visuales.

\--------------------------------------------------  
17\. APP TOOLTIP  
\--------------------------------------------------

Mensajes contextuales.

\--------------------------------------------------  
18\. MOLECULES  
\--------------------------------------------------

Agrupación de componentes básicos.

\--------------------------------------------------  
19\. SEARCH BAR  
\--------------------------------------------------

Búsquedas reutilizables.

\--------------------------------------------------  
20\. FILTER BAR  
\--------------------------------------------------

Filtros dinámicos.

\--------------------------------------------------  
21\. FORM FIELD  
\--------------------------------------------------

Label  
Input  
Error  
Helper Text  
Todo integrado.

\--------------------------------------------------  
22\. DATE PICKER  
\--------------------------------------------------

Selección de fechas.

\--------------------------------------------------  
23\. TIME PICKER  
\--------------------------------------------------

Selección de horas.  
Importante para:  
Servicios Programados.

\--------------------------------------------------  
24\. LOCATION PICKER  
\--------------------------------------------------

Selección geográfica.  
Integrado con:  
OpenStreetMap.

\--------------------------------------------------  
25\. MONEY DISPLAY  
\--------------------------------------------------

Visualización estandarizada de valores monetarios.

\--------------------------------------------------  
26\. ORGANISMS  
\--------------------------------------------------

Componentes de negocio.

\--------------------------------------------------  
27\. SERVICE CARD  
\--------------------------------------------------

Componente principal del sistema.

Mostrará:

\- origen;  
\- destino;  
\- valor;  
\- distancia;  
\- estado;  
\- fecha.

\--------------------------------------------------  
28\. PROGRAMMED SERVICE CARD  
\--------------------------------------------------

Versión especializada.

Mostrará:

\- fecha programada;  
\- hora programada;  
\- incentivo adicional.

\--------------------------------------------------  
29\. OFFER CARD  
\--------------------------------------------------

Visualización de ofertas.

\--------------------------------------------------  
30\. COUNTEROFFER CARD  
\--------------------------------------------------

Visualización de contraofertas.

\--------------------------------------------------  
31\. ADVISOR CARD  
\--------------------------------------------------

Información resumida de asesor.

Mostrará:

\- nombre;  
\- score;  
\- distancia;  
\- servicios realizados.

\--------------------------------------------------  
32\. TRUST CARD  
\--------------------------------------------------

Visualización Trust Score.

Mostrará:

\- score;  
\- categoría;  
\- tendencia.

\--------------------------------------------------  
33\. IMF CARD  
\--------------------------------------------------

Visualización de maduración financiera.

Mostrará:

\- categoría;  
\- progreso;  
\- beneficios.

\--------------------------------------------------  
34\. WALLET CARD  
\--------------------------------------------------

Visualización financiera.

Mostrará:

\- saldo;  
\- cashback;  
\- pendiente;  
\- liquidado.

\--------------------------------------------------  
35\. CASHBACK CARD  
\--------------------------------------------------

Detalle de cashback.

\--------------------------------------------------  
36\. MULTILEVEL CARD  
\--------------------------------------------------

Visualización resumida de red.

\--------------------------------------------------  
37\. LIQUIDATION CARD  
\--------------------------------------------------

Visualización de liquidaciones.

Estados:

\- Pendiente  
\- Procesada  
\- Pagada

\--------------------------------------------------  
38\. NOTIFICATION CARD  
\--------------------------------------------------

Visualización de notificaciones.

\--------------------------------------------------  
39\. AUDIT CARD  
\--------------------------------------------------

Visualización de eventos relevantes.

\--------------------------------------------------  
40\. FRAUD ALERT CARD  
\--------------------------------------------------

Visualización de alertas de riesgo.

\--------------------------------------------------  
41\. QR SCANNER COMPONENT  
\--------------------------------------------------

Componente oficial para lectura QR.

\--------------------------------------------------  
42\. QR DISPLAY COMPONENT  
\--------------------------------------------------

Generación de QR.

\--------------------------------------------------  
43\. MAP COMPONENT  
\--------------------------------------------------

Mapa oficial.

Proveedor inicial:

OpenStreetMap

\--------------------------------------------------  
44\. ROUTE COMPONENT  
\--------------------------------------------------

Visualización de rutas.

Proveedor inicial:

GraphHopper

\--------------------------------------------------  
45\. CHAT COMPONENT  
\--------------------------------------------------

Preparado para futuras versiones.

No obligatorio en V1.

\--------------------------------------------------  
46\. TEMPLATES  
\--------------------------------------------------

Estructuras completas reutilizables.

\--------------------------------------------------  
47\. AUTH TEMPLATE  
\--------------------------------------------------

Pantallas:

\- Login  
\- Registro  
\- Recuperación

\--------------------------------------------------  
48\. DASHBOARD TEMPLATE  
\--------------------------------------------------

Pantallas principales.

\--------------------------------------------------  
49\. LIST TEMPLATE  
\--------------------------------------------------

Pantallas con listados.

\--------------------------------------------------  
50\. DETAIL TEMPLATE  
\--------------------------------------------------

Pantallas de detalle.

\--------------------------------------------------  
51\. FORM TEMPLATE  
\--------------------------------------------------

Pantallas de captura.

\--------------------------------------------------  
52\. MODAL TEMPLATE  
\--------------------------------------------------

Ventanas emergentes.

\--------------------------------------------------  
53\. EMPTY STATE TEMPLATE  
\--------------------------------------------------

Estados sin información.

\--------------------------------------------------  
54\. ERROR STATE TEMPLATE  
\--------------------------------------------------

Estados de error.

\--------------------------------------------------  
55\. LOADING TEMPLATE  
\--------------------------------------------------

Estados de carga.

\--------------------------------------------------  
56\. DARK MODE  
\--------------------------------------------------

Todos los componentes deberán soportar:

\- Light Theme  
\- Dark Theme

desde su construcción inicial.

\--------------------------------------------------  
57\. ACCESIBILIDAD  
\--------------------------------------------------

Todos los componentes deberán cumplir:

\- Contraste AA.  
\- Escalado de fuente.  
\- Compatibilidad con lectores de pantalla.

\--------------------------------------------------  
58\. RESPONSIVE  
\--------------------------------------------------

Todos los componentes deberán adaptarse a:

\- Android  
\- iOS  
\- Windows

\--------------------------------------------------  
59\. OBSERVABILIDAD  
\--------------------------------------------------

Los componentes críticos deberán permitir:

\- logging;  
\- métricas;  
\- diagnóstico.

sin alterar la lógica de negocio.

\--------------------------------------------------  
60\. PROHIBICIONES  
\--------------------------------------------------

No se permitirá:

\- lógica financiera en componentes;  
\- lógica Trust;  
\- lógica IMF;  
\- consultas directas a Base de Datos;  
\- llamadas directas a proveedores externos.

\--------------------------------------------------  
61\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Los componentes Flutter deberán ser reutilizables, desacoplados, consistentes y completamente independientes de las reglas de negocio, permitiendo que la evolución funcional de Tu Mobil Amigo ocurra en Backend y Base de Datos sin requerir rediseños constantes en la interfaz.  

Fin de Documento 31 — Componentes
