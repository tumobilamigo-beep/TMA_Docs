# **Documento 23 — Edge Functions**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura, organización, responsabilidades, nomenclatura y ciclo de vida de las Edge Functions que conformarán el Backend de Tu Mobil Amigo.

Las Edge Functions constituirán la capa de orquestación entre las aplicaciones cliente, PostgreSQL y los servicios externos.

---

# **2\. Principios**

Toda Edge Function deberá cumplir los siguientes principios:

* Responsabilidad única.  
* Stateless.  
* Idempotencia cuando aplique.  
* Alta cohesión.  
* Bajo acoplamiento.  
* Seguridad por defecto.  
* Observabilidad.  
* Reutilización.  
* Trazabilidad.

---

# **3\. Responsabilidades**

Las Edge Functions podrán realizar únicamente las siguientes tareas:

* Autenticar solicitudes.  
* Autorizar usuarios.  
* Validar estructura de entrada.  
* Orquestar procesos.  
* Invocar funciones PostgreSQL.  
* Consumir APIs externas.  
* Publicar eventos.  
* Transformar respuestas.

No implementarán reglas de negocio.

---

# **4\. Responsabilidades Prohibidas**

Queda prohibido que una Edge Function:

* calcule tarifas;  
* calcule Trust Score;  
* calcule IMF;  
* distribuya comisiones;  
* modifique porcentajes;  
* determine reglas del negocio;  
* ejecute consultas SQL complejas;  
* acceda directamente a tablas críticas.

Toda lógica funcional permanecerá centralizada en PostgreSQL.

---

# **5\. Flujo Oficial**

Cliente

↓

JWT

↓

Edge Function

↓

Validación

↓

Autorización

↓

DTO

↓

Función PostgreSQL

↓

Trigger

↓

Realtime

↓

Respuesta  
---

# **6\. Organización**

Las Edge Functions se organizarán por dominios.

edge-functions/

auth/

core/

operations/

pricing/

finance/

multilevel/

trust/

imf/

security/

notifications/

integration/

admin/

audit/

Cada dominio será completamente independiente.

---

# **7\. Convención de Nombres**

Formato oficial:

verbo\_recurso

Ejemplos:

crear\_servicio

aceptar\_oferta

cancelar\_servicio

consultar\_billetera

registrar\_recarga

validar\_qr

aprobar\_retiro

Nunca utilizar nombres ambiguos.

Incorrecto:

servicios

procesar

gestionar

main

index  
---

# **8\. Estructura Interna**

Cada Edge Function deberá contener como mínimo:

index.ts

handler.ts

validation.ts

dto.ts

service.ts

repository.ts (si aplica)

config.ts

constants.ts

errors.ts

tests/

Esta estructura garantiza uniformidad y facilita el mantenimiento.

---

# **9\. Ciclo de Ejecución**

Todas las Edge Functions seguirán el mismo flujo:

1. Recepción de la solicitud.  
2. Validación del JWT.  
3. Validación de permisos.  
4. Validación del DTO.  
5. Registro del Request ID.  
6. Invocación de la función PostgreSQL correspondiente.  
7. Gestión de errores.  
8. Publicación de eventos Realtime (si aplica).  
9. Registro en auditoría.  
10. Respuesta al cliente.

---

# **10\. Comunicación con PostgreSQL**

Las Edge Functions solo podrán interactuar con PostgreSQL mediante:

* funciones (`fn_*`);  
* procedimientos (`sp_*`) cuando existan;  
* vistas autorizadas para consultas.

Nunca ejecutarán lógica SQL de negocio embebida.

---

# **11\. Gestión de Transacciones**

Las transacciones deberán gestionarse preferentemente dentro de PostgreSQL.

La Edge Function solo coordinará el proceso.

---

# **12\. Integraciones Externas**

Las integraciones estarán encapsuladas en adaptadores.

Ejemplos:

TelegramAdapter

GraphHopperAdapter

OpenStreetMapAdapter

PSEAdapter

FirebaseAdapter

EmailAdapter

Si en el futuro cambia un proveedor, únicamente se sustituirá el adaptador correspondiente.

---

# **13\. Gestión de Configuración**

Toda configuración se obtendrá desde PostgreSQL o desde el gestor de secretos del entorno.

Ejemplos:

* tiempo de expiración;  
* porcentajes;  
* límites;  
* URLs de proveedores;  
* tokens;  
* claves privadas.

No se utilizarán constantes de negocio en el código.

---

# **14\. Manejo de Errores**

Todas las respuestas de error seguirán un formato uniforme:

{  
  "success": false,  
  "code": "ERR-FIN-001",  
  "message": "Saldo insuficiente",  
  "requestId": "...",  
  "timestamp": "..."  
}

Los errores internos se registrarán en auditoría, pero no se expondrán al cliente.

---

# **15\. Registro y Observabilidad**

Cada ejecución registrará:

* Request ID.  
* Usuario.  
* Rol.  
* Ciudad.  
* Dominio.  
* Función invocada.  
* Duración.  
* Resultado.  
* Código de error (si existe).

---

# **16\. Seguridad**

Antes de ejecutar cualquier operación se verificará:

* autenticación;  
* autorización por rol;  
* estado del usuario;  
* estado del dispositivo;  
* políticas RLS aplicables;  
* nivel de riesgo antifraude.

---

# **17\. Idempotencia**

Las siguientes operaciones deberán ser idempotentes:

* recargas;  
* retiros;  
* generación de cashback;  
* liberación de comisiones;  
* finalización de servicios;  
* creación de órdenes de pago.

Las solicitudes repetidas no podrán generar efectos duplicados.

---

# **18\. Reintentos**

Las operaciones con proveedores externos deberán implementar una política de reintentos controlada.

Se recomienda:

* máximo 3 intentos;  
* backoff exponencial;  
* registro de cada intento.

Las operaciones financieras solo podrán reintentarse si son idempotentes.

---

# **19\. Timeouts**

Toda Edge Function deberá definir tiempos máximos de ejecución.

Valores iniciales recomendados (parametrizables):

| Tipo | Tiempo máximo |
| ----- | ----- |
| Consultas | 5 segundos |
| Operaciones internas | 10 segundos |
| Integraciones externas | 20 segundos |

Los valores definitivos deberán almacenarse en la base de datos para permitir ajustes sin modificar el código.

---

# **20\. Versionado**

Las funciones públicas deberán soportar versionado.

Ejemplo:

/api/v1/operations/crear-servicio

/api/v1/finance/consultar-billetera

Las nuevas versiones no romperán la compatibilidad de las aplicaciones existentes.

---

# **21\. Catálogo Inicial de Edge Functions**

## **Auth**

* iniciar\_sesion  
* cerrar\_sesion  
* renovar\_token  
* recuperar\_contrasena

## **Core**

* registrar\_usuario  
* actualizar\_perfil  
* registrar\_vehiculo  
* generar\_qr

## **Operations**

* crear\_servicio  
* programar\_servicio  
* aceptar\_oferta  
* rechazar\_oferta  
* cancelar\_servicio  
* finalizar\_servicio  
* radicar\_servicio\_calle

## **Pricing**

* consultar\_tarifa  
* estimar\_ruta

## **Finance**

* consultar\_bolsa\_operativa  
* registrar\_recarga  
* solicitar\_retiro  
* consultar\_movimientos

## **Multilevel**

* consultar\_red  
* consultar\_comisiones  
* consultar\_upliners

## **Trust**

* consultar\_trust  
* consultar\_categoria

## **IMF**

* consultar\_imf  
* consultar\_liberaciones

## **Security**

* registrar\_dispositivo  
* validar\_dispositivo  
* reportar\_fraude

## **Notifications**

* enviar\_push  
* enviar\_telegram  
* enviar\_email

## **Admin**

* aprobar\_recarga  
* aprobar\_retiro  
* actualizar\_parametros  
* publicar\_decreto

### **Settlement**

* generar\_cierre\_mensual  
* consultar\_liquidacion  
* exportar\_liquidacion\_excel  
* registrar\_pago\_liquidacion  
* consultar\_estado\_pago

**Agregar como capacidad futura:**

* exportar\_erp()  
* sincronizar\_erp()  
* consultar\_estado\_erp()

No se implementan inicialmente.

---

# **22\. Evolución**

Toda nueva Edge Function deberá cumplir:

* pertenecer a un dominio existente o justificar la creación de uno nuevo;  
* tener responsabilidad única;  
* reutilizar componentes compartidos;  
* documentarse antes de implementarse;  
* incluir pruebas automatizadas.

---

## **24\. Seguridad de Infraestructura**

Todas las Edge Functions deberán diseñarse bajo el principio:

> **Zero Trust Architecture**

Ninguna solicitud será considerada confiable por defecto.

Toda petición deberá validar:

* autenticación;  
* autorización;  
* integridad;  
* dispositivo;  
* origen;  
* riesgo antifraude;  
* límites operativos.

## **24A. Reportes Corporativos Automáticos**

Al ejecutarse el cierre mensual, el sistema deberá generar automáticamente un archivo Excel consolidado.

El reporte deberá contener como mínimo:

* Periodo  
* Usuario  
* Nombre  
* Tipo Documento  
* Ciudad  
* Categoría  
* Trust Score  
* IPA  
* IPR  
* IMF  
* Cashback  
* Comisión Nivel 1  
* Comisión Nivel 2  
* Incentivos  
* Otros Beneficios  
* Total Liquidado  
* Estado  
* Fecha de Pago

El archivo será utilizado como documento oficial de conciliación financiera de la compañía.

---

## **25\. Protección de Credenciales y Secretos**

Queda absolutamente prohibido almacenar información sensible en:

* Flutter;  
* React;  
* Telegram Mini App;  
* repositorios Git;  
* archivos públicos;  
* código fuente;  
* variables hardcodeadas.

Incluye:

* API Keys;  
* Tokens;  
* JWT Secrets;  
* Database Passwords;  
* SMTP Credentials;  
* Firebase Keys Privadas;  
* PSE Credentials;  
* Webhooks Secretos;  
* Access Tokens;  
* Service Keys Supabase.

---

### **Gestión Obligatoria**

Toda credencial deberá almacenarse exclusivamente mediante:

Supabase Secrets

o

Secret Manager del proveedor

según corresponda.

---

### **Regla de Oro**

Ninguna aplicación cliente deberá conocer:

* credenciales;  
* secretos;  
* endpoints internos;  
* arquitectura interna;  
* estructura financiera.

---

## **26\. Protección Contra Ataques**

El Backend deberá implementar mecanismos de defensa contra:

### **Ataques de Fuerza Bruta**

Protecciones:

* Rate Limiting.  
* Captcha adaptativo.  
* Bloqueo temporal.  
* Escalamiento progresivo.

---

### **Credential Stuffing**

Protecciones:

* Device Fingerprint.  
* Historial de IP.  
* Trust Score.  
* Detección de comportamiento anómalo.

---

### **Replay Attacks**

Protecciones:

* Request ID único.  
* Idempotency Keys.  
* Expiración de Tokens.  
* Nonces cuando aplique.

---

### **API Abuse**

Protecciones:

* Cuotas por usuario.  
* Cuotas por dispositivo.  
* Cuotas por IP.  
* Monitoreo de patrones.

---

### **Enumeración de Recursos**

Protecciones:

* UUID v4.  
* Respuestas genéricas.  
* Ocultamiento de existencia de registros.

---

### **Inyección**

Protecciones:

* SQL parametrizado.  
* DTO obligatorios.  
* Sanitización de entrada.  
* Validaciones estrictas.

---

### **DDoS**

Protecciones:

* CDN.  
* WAF.  
* Rate Limiting.  
* Protección del proveedor cloud.

---

## **27\. Principio de Exposición Mínima**

Todo componente deberá exponer únicamente lo estrictamente necesario.

Ejemplo:

Correcto:

{  
  "servicio\_id": "...",  
  "estado": "aceptado"  
}

Incorrecto:

{  
  "servicio\_id": "...",  
  "usuario\_id": "...",  
  "trust": 84,  
  "imf": 73,  
  "wallet": "...",  
  "device\_id": "...",  
  "ip": "..."  
}  
---

## **28\. Política de Dependencias Externas**

Toda librería incorporada deberá:

* tener mantenimiento activo;  
* ser auditada;  
* poseer licencia compatible;  
* tener comunidad activa;  
* superar revisión de seguridad.

Dependencias abandonadas deberán eliminarse.

---

## **29\. Escaneo Continuo**

El pipeline CI/CD deberá ejecutar:

* análisis SAST;  
* análisis de dependencias;  
* detección de secretos expuestos;  
* análisis de vulnerabilidades;  
* revisión automática de licencias.

Ningún despliegue podrá aprobarse con vulnerabilidades críticas abiertas.

# **30\. Principio Rector Final**

> **Las Edge Functions de Tu Mobil Amigo constituyen la capa de orquestación del ecosistema. Su responsabilidad es coordinar de forma segura, desacoplada y observable la interacción entre clientes, PostgreSQL y servicios externos, manteniendo toda la lógica crítica del negocio centralizada en la base de datos y garantizando una evolución ordenada del Backend mediante funciones pequeñas, especializadas y organizadas por dominios.**

> **Toda Edge Function deberá implementar validación de autenticación, autorización y auditoría conforme al Documento 32\.**

