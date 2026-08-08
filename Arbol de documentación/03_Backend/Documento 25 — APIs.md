# **Documento 25 — APIs**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir el estándar oficial de APIs de Tu Mobil Amigo, estableciendo reglas de diseño, seguridad, versionado, contratos, autorización, auditoría y exposición de servicios.

Las APIs constituyen la única puerta de entrada autorizada al Backend para:

* Flutter App.  
* Portal Administrativo.  
* Telegram Mini App.  
* Integraciones futuras.  
* Servicios externos autorizados.

---

# **2\. Principios**

Todas las APIs deberán cumplir:

* API First.  
* Secure by Design.  
* Versionadas.  
* Auditables.  
* Escalables.  
* Documentadas.  
* Consistentes.  
* Desacopladas.  
* Orientadas al dominio.

---

# **3\. Arquitectura General**

Cliente

↓

API

↓

Edge Function

↓

PostgreSQL

↓

Triggers

↓

Realtime

↓

Respuesta

Las APIs nunca accederán directamente a tablas.

---

# **4\. Organización por Dominios**

Las APIs estarán organizadas por dominio de negocio.

/api/v1/auth/

/api/v1/core/

/api/v1/operations/

/api/v1/pricing/

/api/v1/finance/

/api/v1/multilevel/

/api/v1/trust/

/api/v1/imf/

/api/v1/security/

/api/v1/admin/  
---

# **5\. Regla de Diseño**

Las APIs se diseñarán alrededor de procesos de negocio.

Correcto:

crear-servicio

aceptar-oferta

programar-servicio

consultar-billetera

Incorrecto:

insert-servicio

update-tabla

select-billetera  
---

# **6\. Versionado**

Formato oficial:

/api/v1/

Ejemplo:

/api/v1/operations/crear-servicio

Cuando exista una modificación incompatible:

/api/v2/operations/crear-servicio

Nunca se romperá una versión existente.

---

# **7\. Formato de Respuesta**

## **Respuesta Exitosa**

{  
  "success": true,  
  "data": {},  
  "requestId": "uuid",  
  "timestamp": "2026-01-01T12:00:00Z"  
}  
---

## **Respuesta de Error**

{  
  "success": false,  
  "code": "ERR-OPS-001",  
  "message": "Oferta expirada",  
  "requestId": "uuid",  
  "timestamp": "2026-01-01T12:00:00Z"  
}  
---

# **8\. Request ID**

Toda solicitud generará un identificador único.

Objetivos:

* auditoría;  
* trazabilidad;  
* soporte;  
* investigación de incidentes.

---

# **9\. Autenticación**

Mecanismo oficial:

JWT

Emitido por Supabase Auth.

Toda solicitud protegida requerirá:

Authorization: Bearer \<token\>  
---

# **10\. Autorización**

La autenticación no implica autorización.

Además del JWT se validará:

* rol;  
* estado del usuario;  
* estado del dispositivo;  
* nivel de riesgo;  
* permisos específicos.

---

# **11\. Roles Oficiales**

Roles iniciales:

cliente

asesor

administrador

superadministrador  
---

# **12\. Principio de Mínimo Privilegio**

Una API únicamente podrá acceder a la información estrictamente necesaria para cumplir su función.

---

# **13\. Protección de Datos**

Las APIs nunca expondrán:

* contraseñas;  
* tokens;  
* secretos;  
* fingerprints;  
* IPs internas;  
* reglas antifraude;  
* algoritmos financieros;  
* claves privadas.

---

# **14\. Validación de Entrada**

Toda solicitud deberá validarse mediante DTO.

Validaciones mínimas:

* formato;  
* longitud;  
* tipo;  
* obligatoriedad;  
* rango permitido.

---

# **15\. Sanitización**

Toda entrada deberá sanitizarse antes de ser procesada.

Protecciones obligatorias:

* SQL Injection;  
* XSS;  
* Payload Manipulation;  
* Parameter Pollution.

---

# **16\. Rate Limiting**

Toda API tendrá límites configurables.

Los límites se almacenarán en Base de Datos.

Ejemplos:

| Operación | Límite |
| ----- | ----- |
| Login | Configurable |
| Crear Servicio | Configurable |
| Ofertar | Configurable |
| Retiro | Configurable |

Nunca hardcodeados.

---

# **17\. APIs Públicas**

Permitidas únicamente para:

* registro;  
* login;  
* recuperación de acceso;  
* validaciones públicas.

No requerirán JWT.

---

# **18\. APIs Privadas**

Requerirán:

* JWT válido;  
* usuario activo;  
* dispositivo autorizado.

---

# **19\. APIs Administrativas**

Requerirán:

* rol administrativo;  
* auditoría obligatoria;  
* trazabilidad completa.

---

# **20\. Catálogo Inicial**

## **Auth**

POST /auth/login

POST /auth/logout

POST /auth/refresh

POST /auth/recovery  
---

## **Core**

POST /core/register-user

PUT /core/update-profile

POST /core/register-vehicle

GET /core/profile  
---

## **Operations**

POST /operations/create-service

POST /operations/schedule-service

POST /operations/offer

POST /operations/counteroffer

POST /operations/cancel-service

POST /operations/finish-service

POST /operations/register-street-service  
---

## **Pricing**

GET /pricing/calculate

GET /pricing/estimate  
---

## **Finance**

GET /finance/wallet

GET /finance/movements

POST /finance/topup

POST /finance/withdraw  
---

## **Trust**

GET /trust/score

GET /trust/category  
---

## **IMF**

GET /imf/status

GET /imf/history  
---

## **Multilevel**

GET /multilevel/network

GET /multilevel/commissions

GET /multilevel/upliners  
---

# **21\. Paginación**

Toda consulta masiva deberá soportar paginación.

Formato:

{  
  "page": 1,  
  "pageSize": 20,  
  "total": 500,  
  "items": \[\]  
}  
---

# **22\. Ordenamiento**

Las APIs deberán soportar ordenamiento configurable.

Ejemplo:

?sort=created\_at

?order=desc  
---

# **23\. Filtros**

Ejemplo:

?city=santa-marta

?status=active  
---

# **24\. Auditoría**

Toda operación crítica registrará:

* usuario;  
* dispositivo;  
* IP;  
* acción;  
* resultado;  
* fecha;  
* requestId.

---

# **25\. Idempotencia**

Operaciones financieras deberán utilizar:

Idempotency-Key

Ejemplos:

* recargas;  
* retiros;  
* liberaciones;  
* cashback.

---

# **26\. Timeouts**

Configurables desde Base de Datos.

Ejemplos:

| Tipo | Tiempo |
| ----- | ----- |
| Consulta | Configurable |
| Operación | Configurable |
| Integración | Configurable |

---

# **27\. Integraciones Externas**

Las APIs nunca expondrán directamente proveedores externos.

Ejemplo:

Incorrecto:

/flutter → graphhopper

Correcto:

flutter

↓

api

↓

adapter

↓

graphhopper  
---

# **28\. Configuración Dinámica**

Las siguientes variables deberán provenir exclusivamente de Base de Datos:

* porcentajes financieros;  
* expiración de ofertas;  
* expiración de contraofertas;  
* trust mínimo;  
* IMF;  
* cashback;  
* categorías;  
* límites operativos;  
* parámetros tarifarios;  
* decretos municipales.

---

# **29\. Compatibilidad Futura**

Las APIs deberán soportar:

* nuevos países;  
* nuevas ciudades;  
* nuevos tipos de servicio;  
* nuevas monedas;  
* nuevos métodos de pago.

Sin rediseño estructural.

---

# **30\. Observabilidad**

Toda API deberá registrar:

* tiempo de ejecución;  
* errores;  
* latencia;  
* consumo;  
* origen;  
* dominio.

---

# **31\. Protección Contra Enumeración**

Todos los recursos públicos utilizarán:

UUID v4

Nunca IDs secuenciales.

---

# **32\. Política de Exposición**

Las APIs solo expondrán información necesaria para la interfaz.

No expondrán:

* estructura interna;  
* nombres de tablas;  
* nombres de funciones PostgreSQL;  
* reglas antifraude;  
* fórmulas financieras;  
* cálculos internos.

---

# **33\. APIs y Programación de Servicios**

Se incorpora oficialmente el soporte para servicios programados.

Reglas:

* mínimo: 2 horas;  
* máximo: 12 horas;

Valores configurables desde Base de Datos.

---

## **Beneficio Financiero**

Cuando un servicio sea programado:

Empresa:  
30% → 25%

Cashback Cliente:  
30% → 35%

La diferencia del 5% será asumida por la participación de la empresa.

Las APIs nunca calcularán este valor.

La lógica residirá exclusivamente en PostgreSQL.

---

# **34\. APIs y Beneficio por Servicio en Calle**

Se incorpora oficialmente el incentivo para asesores que registren servicios en calle mediante QR.

Regla:

El incentivo será financiado mediante una reducción de hasta el 5% de la participación de la empresa.

La distribución exacta será determinada por el Motor Financiero y el IMF.

Las APIs únicamente ejecutarán la operación.

---

# **35\. Seguridad Avanzada**

Las APIs deberán protegerse contra:

* fuerza bruta;  
* replay attacks;  
* credential stuffing;  
* scraping;  
* DDoS;  
* abuso automatizado;  
* enumeración de recursos.

---

# **36\. Gestión de Secretos**

Queda prohibido almacenar:

* API Keys;  
* Passwords;  
* Tokens;  
* Service Keys;  
* JWT Secrets;

en:

* Flutter;  
* React;  
* Telegram;  
* repositorios Git;  
* archivos públicos;  
* código fuente.

Toda credencial deberá almacenarse mediante:

Supabase Secrets

o gestores equivalentes.

### **Nueva consideración arquitectónica**

Las APIs financieras deberán diseñarse para exponer información compatible con procesos ERP futuros.

---

# **37\. endpoint administrativo futuro**

POST

/liquidaciones/manual

con acceso restringido.

# **38\. Principio Rector Final**

> **Las APIs de Tu Mobil Amigo constituyen una capa segura, versionada y desacoplada de acceso al ecosistema. Su función es exponer capacidades de negocio sin revelar la implementación interna, garantizando seguridad, trazabilidad, escalabilidad y compatibilidad futura, mientras toda la lógica crítica permanece centralizada en PostgreSQL y sus motores especializados.**

La seguridad operativa de APIs se regirá por los controles definidos en el Documento 32 y posteriormente en el Documento 38A.

