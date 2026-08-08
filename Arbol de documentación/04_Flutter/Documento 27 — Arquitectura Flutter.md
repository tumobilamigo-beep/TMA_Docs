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

