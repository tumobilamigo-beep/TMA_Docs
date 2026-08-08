# **Documento 26 — Integraciones**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura, estándares, proveedores, mecanismos de seguridad y lineamientos para todas las integraciones externas del ecosistema Tu Mobil Amigo.

Las integraciones permitirán conectar la plataforma con servicios externos sin comprometer la seguridad, estabilidad, auditabilidad ni independencia tecnológica del proyecto.

---

# **2\. Principios Rectores**

Toda integración deberá cumplir:

* Seguridad por defecto.  
* Desacoplamiento.  
* Trazabilidad.  
* Auditabilidad.  
* Sustituibilidad.  
* Configuración dinámica.  
* Escalabilidad.  
* Alta disponibilidad.

---

# **3\. Principio de Independencia**

Ninguna integración deberá convertirse en una dependencia estructural irremplazable.

Toda integración deberá poder ser sustituida por otra equivalente sin modificar:

* Flutter.  
* React Admin.  
* PostgreSQL.  
* Modelo de negocio.

---

# **4\. Arquitectura Oficial**

Cliente

↓

API Tu Mobil Amigo

↓

Edge Function

↓

Adapter

↓

Proveedor Externo  
---

# **5\. Regla de Oro**

Ninguna aplicación cliente podrá comunicarse directamente con proveedores externos.

Prohibido:

Flutter → PSE

Flutter → OpenStreetMap

Flutter → Telegram

Flutter → Firebase

Obligatorio:

Flutter

↓

API Tu Mobil Amigo

↓

Proveedor Externo  
---

# **6\. Modelo Adapter**

Cada proveedor deberá estar encapsulado mediante un Adapter.

Ejemplos:

PSEAdapter

MapAdapter

NotificationAdapter

TelegramAdapter

EmailAdapter  
---

# **7\. Configuración Dinámica**

Toda configuración deberá almacenarse en:

configuracion\_sistema

o

parametros\_integracion

Nunca en código.

---

# **8\. Gestión de Secretos**

Las credenciales deberán almacenarse exclusivamente mediante:

Supabase Secrets

o

Secret Manager

según la infraestructura utilizada.

---

# **9\. Integraciones Iniciales Aprobadas**

## **Cartografía**

### **OpenStreetMap**

Uso principal:

* mapas;  
* georreferenciación;  
* visualización.

---

### **GraphHopper**

Uso principal:

* cálculo de rutas;  
* cálculo de distancia;  
* tiempo estimado de desplazamiento.

---

# **10\. Estrategia Cartográfica**

Fase Inicial:

OpenStreetMap  
\+  
GraphHopper  
---

Justificación:

* costo cero o muy bajo;  
* independencia tecnológica;  
* suficiente para etapas tempranas;  
* comunidad madura.

---

# **11\. Evolución Cartográfica**

Cuando la operación lo justifique podrá migrarse hacia:

### **Opción 1**

MapTiler  
---

### **Opción 2**

Tile Server Propio  
---

### **Opción 3**

Proveedor Empresarial

Ejemplos:

* Google Maps.  
* HERE.  
* TomTom.

---

# **12\. Política de Migración**

La sustitución de proveedores deberá requerir únicamente:

Cambio de Adapter

Sin modificar:

* Flutter;  
* APIs;  
* PostgreSQL.

---

# **13\. Integración Telegram**

Objetivo:

* autenticación secundaria;  
* notificaciones;  
* canal de soporte;  
* Mini App.

---

Servicios permitidos:

* envío de mensajes;  
* alertas;  
* validaciones.

---

# **14\. Integración Firebase**

Objetivo:

* Push Notifications.

Uso autorizado:

Firebase Cloud Messaging  
---

No se utilizará Firebase como base de datos principal.

---

# **15\. Integración PSE**

Objetivo:

* recargas;  
* pagos;  
* conciliaciones.

---

# **16\. Estrategia PSE**

Fase Inicial:

Operación asistida.

Las recargas podrán validarse manualmente mientras el volumen lo permita.

---

Fase de crecimiento:

Integración directa mediante proveedor autorizado.

---

# **17\. Abstracción de Pagos**

La plataforma no dependerá directamente de un proveedor específico.

Se utilizará:

PaymentAdapter  
---

Implementaciones posibles:

PSE

Wompi

ePayco

PayU

MercadoPago

Proveedor Bancario  
---

# **18\. Integración Correo Electrónico**

Objetivos:

* recuperación de cuenta;  
* notificaciones;  
* comunicaciones oficiales.

---

Abstracción:

EmailAdapter  
---

Implementaciones posibles:

Resend

SendGrid

Amazon SES

SMTP Corporativo  
---

# **19\. Integración SMS**

Uso restringido.

Aplicaciones:

* recuperación crítica;  
* validaciones regulatorias.

---

Abstracción:

SmsAdapter  
---

# **20\. Integración QR**

Objetivos:

* radicación de servicios en calle;  
* validación de operaciones;  
* antifraude.

---

El QR nunca almacenará:

* datos financieros;  
* información sensible;  
* credenciales.

---

# **21\. Integración de Archivos**

El sistema deberá soportar:

* Excel;  
* PDF;  
* CSV.

---

Aplicaciones:

* liquidaciones mensuales;  
* auditorías;  
* reportes administrativos.

---

# **22\. Integración de Reportes**

El sistema deberá generar automáticamente:

## **Reporte de Liquidación Mensual**

Contenido mínimo:

* Usuario.  
* Ciudad.  
* Categoría.  
* Trust.  
* IPA.  
* IPR.  
* IMF.  
* Cashback.  
* Nivel 1\.  
* Nivel 2\.  
* Incentivos.  
* Total a pagar.

---

Formato oficial:

Excel (.xlsx)  
---

# **23\. Integración de Auditoría**

Toda integración deberá registrar:

* fecha;  
* proveedor;  
* endpoint;  
* usuario;  
* resultado;  
* duración;  
* requestId.

---

# **24\. Reintentos**

Las integraciones deberán soportar:

* reintentos automáticos;  
* backoff exponencial;  
* trazabilidad.

---

# **25\. Timeouts**

Los timeouts deberán configurarse desde Base de Datos.

Nunca hardcodeados.

---

# **26\. Monitoreo**

Se deberá monitorear:

* disponibilidad;  
* latencia;  
* errores;  
* consumo;  
* cuotas.

---

# **27\. Gestión de Fallos**

Ante caída de un proveedor:

Proveedor

↓

Error

↓

Adapter

↓

Fallback

↓

Registro Auditoría  
---

# **28\. Seguridad**

Toda integración deberá:

* validar certificados;  
* utilizar HTTPS;  
* utilizar TLS actualizado;  
* validar firmas cuando existan;  
* registrar actividad.

---

# **29\. Protección de Datos**

Las integraciones nunca expondrán:

* secretos;  
* tokens;  
* claves privadas;  
* reglas antifraude;  
* lógica financiera.

---

# **30\. Integraciones y Multinivel**

Las integraciones no podrán modificar:

* Trust;  
* IMF;  
* Cashback;  
* Comisiones;  
* Categorías.

La lógica permanecerá exclusivamente en PostgreSQL.

---

# **31\. Integraciones y Liquidaciones**

Las integraciones únicamente podrán:

* exportar reportes;  
* registrar pagos;  
* consultar estados.

No podrán alterar liquidaciones ya cerradas.

---

# **32\. Escalabilidad**

La arquitectura deberá permitir agregar nuevos proveedores sin rediseñar:

* Flutter;  
* APIs;  
* Base de Datos;  
* Motores de negocio.

---

# **33\. Principio Rector Final**

> **Toda integración de Tu Mobil Amigo deberá implementarse mediante capas de abstracción desacopladas, configurables y seguras, garantizando que ningún proveedor externo tenga dependencia estructural sobre la plataforma y permitiendo la evolución tecnológica sin afectar la operación, la seguridad ni las reglas del negocio.**

