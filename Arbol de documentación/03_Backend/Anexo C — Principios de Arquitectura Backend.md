# **Anexo C — Principios de Arquitectura Backend**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir los principios arquitectónicos que regirán el desarrollo del Backend de Tu Mobil Amigo, garantizando una plataforma escalable, desacoplada, segura, observable y preparada para crecer durante los próximos años sin requerir rediseños estructurales.

Este documento complementa los Documentos 22 al 26 y será de obligatorio cumplimiento para cualquier desarrollo backend.

---

# **2\. Filosofía Arquitectónica**

El Backend de Tu Mobil Amigo no será el lugar donde resida la lógica del negocio.

Su responsabilidad será:

* recibir solicitudes;  
* autenticar usuarios;  
* validar formato de entrada;  
* coordinar procesos;  
* invocar funciones PostgreSQL;  
* integrar servicios externos;  
* responder al cliente.

Las decisiones de negocio permanecerán en PostgreSQL.

---

# **3\. Principio Rector**

> **El Backend orquesta. La Base de Datos decide. El Cliente presenta.**

Toda nueva funcionalidad deberá respetar esta separación.

---

# **4\. Arquitectura General**

Flutter  
React  
Telegram  
API Externa  
        │  
        ▼  
Edge Functions  
        │  
        ▼  
Servicios Backend  
        │  
        ▼  
Funciones PostgreSQL  
        │  
        ▼  
Base de Datos

Ningún cliente accederá directamente a tablas críticas.

---

# **5\. Backend Stateless**

Todas las Edge Functions y servicios backend deberán ser completamente **stateless**.

No almacenarán:

* sesiones;  
* estados temporales;  
* cachés de usuario;  
* información financiera.

Cada solicitud deberá poder ejecutarse independientemente.

---

# **6\. Responsabilidad Única**

Cada Edge Function tendrá un único objetivo.

Ejemplo correcto:

crear\_servicio()

aceptar\_oferta()

finalizar\_servicio()

consultar\_billetera()

aprobar\_recarga()

Ejemplo incorrecto:

gestionar\_servicios()

procesar\_usuario()

administracion\_general()  
---

# **7\. Orquestación**

El Backend coordina procesos.

Ejemplo:

Flutter

↓

Edge Function

↓

Validar Token

↓

Validar Entrada

↓

Invocar fn\_crear\_servicio()

↓

Respuesta

El Backend nunca recalcula tarifas ni modifica reglas de negocio.

---

# **8\. Contratos (DTO)**

Toda comunicación utilizará contratos explícitos.

Ejemplo:

{  
  "ciudad\_id": "...",  
  "tipo\_servicio\_id": "...",  
  "origen": {},  
  "destino": {}  
}

No se aceptarán objetos ambiguos ni estructuras dinámicas sin justificación.

---

# **9\. Validaciones**

El Backend validará únicamente:

* formato;  
* longitud;  
* tipos de datos;  
* campos obligatorios;  
* autenticación;  
* autorización.

Las reglas funcionales permanecerán en PostgreSQL.

---

# **10\. Idempotencia**

Las operaciones críticas deberán ser idempotentes.

Ejemplos:

* pagos;  
* recargas;  
* retiros;  
* finalización de servicios;  
* generación de cashback.

Una misma solicitud repetida no podrá producir efectos duplicados.

---

# **11\. Manejo de Errores**

Todas las respuestas deberán utilizar un formato uniforme.

Ejemplo:

{  
  "codigo": "ERR-FIN-001",  
  "mensaje": "Saldo insuficiente",  
  "detalle": null,  
  "timestamp": "..."  
}

Nunca devolver errores internos del motor de base de datos al cliente.

---

# **12\. Integraciones Externas**

Toda comunicación con terceros se realizará exclusivamente desde el Backend.

Ejemplos:

* Telegram.  
* PSE.  
* OpenStreetMap.  
* GraphHopper.  
* Notificaciones Push.  
* Correo electrónico.  
* SMS.

Las credenciales nunca estarán disponibles en Flutter o React.

---

# **13\. Gestión de Configuración**

Todas las variables configurables deberán obtenerse desde la base de datos.

Queda prohibido utilizar constantes de negocio en el código del Backend.

---

# **14\. Observabilidad**

Cada solicitud deberá generar:

* identificador único (Request ID);  
* usuario;  
* IP;  
* dispositivo;  
* tiempo de ejecución;  
* resultado;  
* errores.

Esta información permitirá reconstruir cualquier incidente.

---

# **15\. Logging**

Se definen tres niveles:

| Nivel | Uso |
| ----- | ----- |
| INFO | Operación normal |
| WARN | Situación anómala recuperable |
| ERROR | Fallo funcional o técnico |

Los registros nunca contendrán:

* contraseñas;  
* tokens;  
* datos bancarios completos;  
* documentos completos.

---

# **16\. Seguridad**

Toda Edge Function deberá:

* verificar autenticación;  
* verificar autorización;  
* validar RLS cuando corresponda;  
* limitar intentos;  
* registrar accesos críticos.

---

# **17\. Gestión de Secretos**

Las claves privadas deberán almacenarse exclusivamente en el gestor de secretos del entorno.

Nunca podrán:

* almacenarse en Flutter;  
* almacenarse en React;  
* subirse al repositorio;  
* escribirse en archivos de configuración públicos.

---

# **18\. Rendimiento**

Las Edge Functions deberán:

* minimizar llamadas a la base de datos;  
* reutilizar conexiones cuando la plataforma lo permita;  
* evitar operaciones bloqueantes innecesarias;  
* delegar cálculos complejos a PostgreSQL.

---

# **19\. Reintentos**

Solo podrán reintentarse automáticamente operaciones idempotentes.

Las operaciones financieras no idempotentes requerirán mecanismos de confirmación explícita.

---

# **20\. Eventos**

El Backend podrá publicar eventos hacia:

* Supabase Realtime;  
* sistemas de notificaciones;  
* servicios de monitoreo.

Nunca generará eventos duplicados para una misma operación.

---

# **21\. Escalabilidad Horizontal**

El diseño deberá permitir ejecutar múltiples instancias del Backend simultáneamente sin compartir estado.

Esto facilitará el crecimiento de la plataforma sin modificaciones arquitectónicas.

---

# **22\. Versionado de APIs**

Toda API pública deberá incorporar versionado.

Ejemplo:

/api/v1/servicios

/api/v1/usuarios

/api/v1/finanzas

Las versiones antiguas se mantendrán durante un periodo de transición previamente definido.

---

# **23\. Política de Dependencias**

Solo se incorporarán nuevas librerías cuando:

* resuelvan un problema real;  
* tengan mantenimiento activo;  
* posean licencia compatible;  
* no dupliquen funcionalidades existentes.

Se priorizará un Backend ligero y con pocas dependencias externas.

---

# **24\. Pruebas**

Cada Edge Function deberá contar con:

* pruebas unitarias;  
* pruebas de integración;  
* validación de casos de error;  
* validación de permisos.

No se considerará finalizada una funcionalidad sin pruebas automatizadas.

---

# **25\. Compatibilidad Tecnológica**

La arquitectura backend deberá mantenerse independiente del framework cliente.

El mismo Backend deberá atender sin modificaciones a:

* Flutter (Android, iOS, Windows, Linux, macOS y Web).  
* Panel Administrativo React.  
* Telegram Mini App.  
* APIs de terceros.  
* Futuras aplicaciones del ecosistema.

---

# **26\. Evolución Tecnológica**

El Backend deberá diseñarse para permitir la sustitución de componentes sin afectar la lógica del negocio.

Ejemplos:

* reemplazar OpenStreetMap por un proveedor comercial;  
* cambiar GraphHopper por otro motor de rutas;  
* incorporar nuevos medios de pago;  
* integrar nuevos canales de comunicación.

La sustitución de un proveedor no deberá implicar cambios en Flutter ni en la base de datos.

---

# **27\. Principio Rector Final**

> **El Backend de Tu Mobil Amigo es una capa de orquestación desacoplada, segura y sin estado. Su propósito es conectar clientes, servicios externos y la base de datos, preservando que toda regla crítica permanezca centralizada, parametrizada y auditada en PostgreSQL, garantizando así consistencia funcional, escalabilidad y facilidad de mantenimiento a largo plazo.**

