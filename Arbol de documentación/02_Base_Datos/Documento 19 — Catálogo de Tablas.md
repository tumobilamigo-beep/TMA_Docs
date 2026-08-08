Documento 19 — Catálogo de Tablas

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir el inventario oficial de tablas del sistema.  
Este documento constituye la fuente de verdad para:  
Backend.  
Flutter.  
Seguridad.  
Reportes.  
Auditoría.  
IA.  
Integraciones.  
Toda nueva tabla deberá incorporarse a este catálogo.

2\. Clasificación General  
Las tablas se agrupan en:  
Núcleo de Usuarios  
Operación  
Finanzas  
Multinivel  
Confianza  
Antifraude  
Configuración  
Auditoría

3\. Núcleo de Usuarios  
usuarios  
Descripción  
Entidad principal del sistema.  
Representa cualquier persona registrada.  
Responsable  
Autenticación.  
Dependencias  
asesores  
dispositivos  
billeteras  
trust\_score  
ipa  
ipr  
imf  
asesores  
Descripción  
Información profesional y documental de los asesores.  
Responsable  
Operación.  
Dependencias  
usuarios  
dispositivos  
Descripción  
Control de equipos autorizados.  
Responsable  
Seguridad.  
Dependencias  
usuarios

4\. Configuración Territorial  
ciudades  
Descripción  
Ciudades habilitadas.  
Responsable  
Administración.  
zonas\_operacion  
Descripción  
Segmentación geográfica.  
Responsable  
Operación.

5\. Catálogos Corporativos  
catalogos  
Descripción  
Catálogos maestros reutilizables.  
Responsable  
Arquitectura.  
catalogo\_detalles  
Descripción  
Valores parametrizados.  
Responsable  
Arquitectura.  
Ejemplos:  
ESTADOS\_SERVICIO  
TIPOS\_SERVICIO  
TIPOS\_NOTIFICACION  
PARAMETROS\_TARIFARIOS  
PARAMETROS\_IMF  
PARAMETROS\_TRUST

6\. Motor Tarifario  
parametros\_tarifarios  
Descripción  
Almacena parámetros configurables por ciudad.  
Responsable  
Motor Tarifario.  
Ejemplos:  
valor\_banderazo  
valor\_km  
valor\_minuto  
factor\_moto  
factor\_taxi  
recargo\_nocturno  
recargo\_festivo  
Regla Arquitectónica  
Toda variable tarifaria  
debe existir como registro.  
Nunca como columna.

7\. Operación  
servicios  
Descripción  
Tabla principal del negocio.  
Responsable  
Motor Operativo.  
Modalidades:  
INMEDIATO  
PROGRAMADO  
QR

Estados:  
CREADO  
OFERTADO  
NEGOCIANDO  
ACEPTADO  
EN\_CURSO  
FINALIZADO  
CANCELADO

ofertas  
Descripción  
Ofertas económicas emitidas.  
Responsable  
Motor de Negociación.  
Regla:  
Expiración inicial:  
180 segundos  
Configurable desde BD.  
contraofertas  
Descripción  
Contraofertas emitidas por asesores.  
Responsable  
Motor de Negociación.  
Regla:  
Una única contraoferta  
por cliente.  
Regla:  
Expiran con el mismo tiempo  
de las ofertas.  
qr\_clientes  
Descripción  
Identificador QR único del cliente.  
Responsable  
Operación.

Objetivos:  
Servicios QR  
Validación cliente  
Trazabilidad

8\. Finanzas  
billeteras  
Descripción  
Almacena saldos de usuarios.  
Responsable  
Motor Financiero.  
Tipos:  
OPERATIVA  
BENEFICIOS  
Regla Operativa  
La billetera operativa:  
Recibe recargas.  
Paga comisiones.  
No participa en IMF.  
La billetera de beneficios:  
Cashback.  
Comisiones multinivel.  
Incentivos QR.  
Participa en IMF.  
movimientos\_financieros

Descripción  
Libro contable oficial.  
Responsable  
Motor Financiero.

Tipos:  
RECARGA  
COMISION  
CASHBACK  
LIBERACION  
RETIRO  
INCENTIVO\_QR  
AJUSTE

9\. Cashback  
cashback  
Descripción  
Beneficios generados por servicios.  
Responsable  
Motor Financiero.  
Distribución estándar:  
15% Comisión Operativa  
│  
├── Empresa .......... 30%  
├── Cashback ......... 30%  
├── Upliner 1 ........ 20%  
├── Upliner 2 ........ 10%  
└── Fondo Reserva .... 10%

Servicios programados:  
Empresa .......... 25%  
Cashback ......... 35%

El incremento del 5% se financia desde la participación de la empresa.

10\. Multinivel  
red\_multinivel  
Descripción  
Relación genealógica.  
Responsable  
Motor Multinivel.  
Profundidad máxima:  
Nivel 1  
Nivel 2  
comisiones  
Descripción  
Comisiones generadas por red.  
Responsable  
Motor Multinivel.  
Estados:  
GENERADA  
MADURANDO  
LIBERADA  
PAGADA

11\. Incentivos QR  
incentivos\_qr  
Descripción  
Beneficio otorgado a asesores por registrar servicios realizados fuera de la plataforma.  
Responsable  
Motor Financiero.  
Regla:  
El incentivo se financia desde la participación de la empresa.  
Participa en IMF.

12\. Confianza  
trust\_score  
Descripción  
Nivel de confianza del usuario.  
Responsable  
Motor de Confianza.

Escala:  
0 \- 100  
Categorías:  
Explorador  
Viajero  
Experto  
Leyenda  
ipa

Descripción  
Índice de Participación Activa.  
Responsable  
Motor de Confianza.  
Evalúa:  
Servicios  
Actividad  
Uso del sistema  
ipr

Descripción  
Índice de Participación en Red.  
Responsable  
Motor de Confianza.  
Evalúa:  
Referidos activos  
Actividad de red  
imf  
Descripción  
Índice de Maduración Financiera.  
Responsable  
Motor Financiero.  
Factores:  
Antigüedad  
Trust Score  
IPA  
IPR

13\. Antifraude  
eventos\_antifraude  
Descripción  
Registro de anomalías detectadas.  
Responsable  
Motor Antifraude.  
Ejemplos:  
Autorreferencia  
Múltiples dispositivos  
Patrones sospechosos  
Manipulación de servicios  
Abuso cashback  
Abuso multinivel

14\. Auditoría  
auditoria  
Descripción  
Bitácora corporativa.  
Responsable  
Auditoría.  
Regla:  
Nada se elimina.  
Todo se registra.

15\. Notificaciones  
notificaciones  
Descripción  
Mensajería interna.  
Responsable  
Comunicaciones.  
Canales futuros:  
Push  
Telegram  
Email  
SMS

16\. Integraciones  
integraciones\_externas  
Descripción  
Control de conexiones externas.  
Responsable  
Backend.  
Integraciones previstas:  
Telegram  
OpenStreetMap  
Leaflet (Flutter/Web)  
Nominatim (Geocoding)  
GraphHopper u OSRM (Rutas)  
PSE  
Pasarela de pagos  
Siigo  
Banco Empresarial

17\. Resumen Ejecutivo  
Dominio		Cantidad  
Usuarios	3  
Operación	4  
Finanzas	3  
Multinivel	2  
Confianza	4  
Antifraude	1  
Auditoría	1  
Integraciones	1  
Configuración	4

18\. Principio Rector Final

Toda tabla deberá tener:

Propósito claro.  
Responsable definido.  
Trazabilidad.  
Relación con una necesidad real del negocio.

Se prohíbe la creación de tablas sin justificación funcional documentada.

# **Integración Contable Futura**

Todos los procesos financieros deberán diseñarse de forma que puedan ser exportados a sistemas ERP externos.

Entre ellos:

* liquidaciones;  
* pagos;  
* cashback;  
* multinivel;  
* incentivos;  
* ajustes contables;  
* conciliaciones.

# **tipo\_liquidacion**

ORDINARIA  
EXTRAORDINARIA

y además:

motivo  
ejecutado\_por  
fecha\_ejecucion

## **Tabla: device\_registry**

### **Propósito**

Registrar y monitorear los dispositivos utilizados por los usuarios del ecosistema Tu Mobil Amigo.

Constituye una de las principales fuentes de información para:

* Motor Antifraude.  
* Trust Score.  
* Gestión de Dispositivos.  
* Ciberseguridad.  
* Auditoría.

---

### **Relaciones**

usuarios  
    │  
    └── device\_registry

Relación:

1 usuario  
N dispositivos  
---

### **Campos relevantes**

| Campo | Descripción |
| ----- | ----- |
| fingerprint | Identificador único lógico del dispositivo |
| device\_trust\_score | Puntaje interno de confianza |
| estado | Estado operativo del dispositivo |
| reputacion | Clasificación de riesgo |
| vpn\_detectado | Detección de VPN |
| proxy\_detectado | Detección de Proxy |
| tor\_detectado | Detección de red TOR |
| datacenter\_ip | Uso de IP de datacenter |
| cantidad\_alertas | Alertas acumuladas |
| cantidad\_bloqueos | Bloqueos históricos |

---

### **Reglas de negocio**

#### **RN-DR-001**

Todo acceso autenticado deberá asociarse a un dispositivo registrado.

---

#### **RN-DR-002**

El sistema podrá registrar múltiples dispositivos por usuario.

El límite será configurable desde Base de Datos.

---

#### **RN-DR-003**

Un mismo dispositivo podrá asociarse a múltiples usuarios únicamente cuando las reglas antifraude lo permitan.

---

#### **RN-DR-004**

Cambios frecuentes de dispositivo podrán generar eventos de riesgo.

---

#### **RN-DR-005**

La detección de VPN, Proxy, TOR o IPs de Datacenter incrementará el riesgo antifraude.

---

#### **RN-DR-006**

Los dispositivos bloqueados no podrán operar dentro del ecosistema.

---

#### **RN-DR-007**

Los dispositivos podrán afectar indirectamente:

Trust Score  
Elegibilidad operativa  
Validaciones de seguridad  
Controles antifraude  
---

### **Integraciones**

Consumido por:

Documento 13 — Trust Score

Documento 15 — Motor Antifraude

Documento 32 — Ciberseguridad

Documento 34 — Gestión de Dispositivos

Fin del Documento 19 — Catálogo de Tablas