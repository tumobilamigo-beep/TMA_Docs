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
39\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Los portales React serán responsables exclusivamente de la administración, gobierno, auditoría y supervisión del ecosistema Tu Mobil Amigo.

Toda lógica crítica de negocio, motores financieros, reglas de seguridad, antifraude, multinivel, Trust, IMF y liquidaciones permanecerá centralizada en PostgreSQL y Backend para garantizar integridad, trazabilidad y seguridad empresarial.  
