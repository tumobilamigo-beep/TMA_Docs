Backend

# **Documento 22 — Arquitectura Backend**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura oficial del Backend de Tu Mobil Amigo, estableciendo la organización de sus componentes, responsabilidades, flujos de comunicación y principios de implementación.

El Backend actuará como una capa de orquestación desacoplada entre las aplicaciones cliente, la base de datos y los servicios externos.

---

# **2\. Objetivos Arquitectónicos**

El Backend deberá garantizar:

* Alta disponibilidad.  
* Escalabilidad horizontal.  
* Baja latencia.  
* Seguridad.  
* Observabilidad.  
* Desacoplamiento.  
* Mantenibilidad.  
* Facilidad de evolución.

---

# **3\. Principios**

Toda implementación deberá cumplir:

* Stateless.  
* Domain Driven.  
* API First.  
* Event Driven.  
* Secure by Design.  
* Configuration Driven.  
* Database First.

---

# **4\. Arquitectura General**

                   Flutter  
                   React Admin  
              Telegram Mini App  
                  APIs Futuras  
                        │  
                        ▼  
             API Gateway / Edge Functions  
                        │  
 ┌──────────────────────┼──────────────────────┐  
 │                      │                      │  
 ▼                      ▼                      ▼  
Autenticación      Orquestación         Integraciones  
 │                      │                      │  
 └──────────────┬───────┴──────────────┬───────┘  
                ▼  
        PostgreSQL / Supabase  
                │  
                ▼  
Funciones → Triggers → Auditoría → Realtime  
---

# **5\. Componentes**

## **Cliente**

Responsable de:

* Capturar datos.  
* Mostrar información.  
* Gestionar navegación.  
* Consumir APIs.

Nunca implementará reglas de negocio.

---

## **Edge Functions**

Responsables de:

* Validar autenticación.  
* Validar autorización.  
* Validar formato.  
* Orquestar procesos.  
* Consumir proveedores externos.  
* Gestionar secretos.  
* Transformar respuestas.

---

## **PostgreSQL**

Responsable de:

* Reglas del negocio.  
* Motor financiero.  
* Motor tarifario.  
* Trust Score.  
* IMF.  
* Multinivel.  
* Antifraude.  
* Auditoría.

---

## **Realtime**

Responsable de:

* Sincronización instantánea.  
* Estado de servicios.  
* Notificaciones.  
* Actualización de mapas.  
* Mensajería interna.

---

# **6\. Dominios del Backend**

El Backend se dividirá por dominios funcionales.

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

settlement/ 

Dominio responsable de:

* cierres mensuales;  
* liquidaciones;  
* generación de reportes;  
* control de pagos;  
* ajustes contables.

Cada dominio será completamente independiente.

erp/

Responsable de:

* exportaciones;  
* sincronizaciones;  
* conciliaciones;  
* integración contable.

---

# **7\. Organización del Proyecto**

backend/

src/

├── auth/  
├── core/  
├── operations/  
├── pricing/  
├── finance/  
├── multilevel/  
├── trust/  
├── imf/  
├── security/  
├── integrations/  
├── notifications/  
├── admin/  
├── audit/  
│  
├── shared/  
│  
│   ├── dto/  
│   ├── utils/  
│   ├── middleware/  
│   ├── constants/  
│   ├── config/  
│   ├── logger/  
│   ├── validation/  
│   └── errors/  
│  
└── tests/  
---

# **8\. Flujo Oficial de una Solicitud**

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

Auditoría

↓

Realtime

↓

Respuesta  
---

# **9\. Flujo de un Servicio**

Cliente solicita servicio

↓

Edge Function

↓

fn\_crear\_servicio()

↓

Trigger

↓

Publicación de ofertas

↓

Realtime

↓

Asesores

↓

Aceptación

↓

Asignación

↓

Finalización

↓

Motor Financiero

↓

Trust

↓

IMF

↓

Cashback

↓

Auditoría

↓

Respuesta  
---

# **10\. Comunicación Interna**

Los módulos nunca accederán directamente entre sí.

Toda comunicación deberá realizarse mediante:

* Interfaces.  
* DTO.  
* Eventos.  
* Funciones PostgreSQL.

---

# **11\. Gestión de Configuración**

Todas las variables del negocio deberán obtenerse desde PostgreSQL.

Ejemplos:

* Tiempo de expiración de ofertas.  
* Tiempo de contraofertas.  
* Bolsa Operativa mínima.  
* Porcentajes financieros.  
* Trust mínimo.  
* Ventanas de programación.  
* Parámetros del IMF.  
* Parámetros del IPA/IPR.  
* Configuración de OpenStreetMap.  
* Configuración de GraphHopper.

---

# **12\. Gestión de Proveedores**

El Backend deberá abstraer completamente los proveedores externos.

Ejemplo:

Servicio de Mapas

        │

 ┌──────┴────────┐

 OpenStreetMap

 MapTiler

 TileServer

 Google Maps (futuro)

Flutter nunca sabrá qué proveedor se está utilizando.

La sustitución de un proveedor no requerirá cambios en las aplicaciones cliente.

---

# **13\. Gestión de Pagos**

El Backend actuará como intermediario entre la plataforma y los proveedores financieros.

Inicialmente soportará:

* PSE.  
* Transferencias bancarias.  
* Confirmación manual por Administrador.

Posteriormente podrá integrar:

* ACH Colombia.  
* Transfiya.  
* Open Finance.  
* Pasarelas certificadas.

Toda integración deberá mantenerse desacoplada del núcleo financiero.

---

# **14\. Estrategia de Seguridad**

Cada solicitud será validada mediante:

* JWT.  
* Rol.  
* Permisos.  
* Trust.  
* Estado del usuario.  
* Estado del dispositivo.  
* Riesgo antifraude.

Ninguna operación crítica podrá ejecutarse únicamente con autenticación.

---

# **15\. Observabilidad**

Cada solicitud generará:

* Request ID.  
* Usuario.  
* Rol.  
* Ciudad.  
* Tiempo de respuesta.  
* Consumo de recursos.  
* Resultado.  
* Errores.  
* Eventos asociados.

Toda esta información estará disponible para el Panel Administrativo.

---

# **16\. Escalabilidad**

El Backend deberá permitir:

* múltiples instancias;  
* balanceo de carga;  
* escalado horizontal;  
* nuevos servicios;  
* nuevos países;  
* nuevas monedas;  
* nuevos proveedores.

Sin modificar la arquitectura principal.

---

# **17\. Estrategia de Despliegue**

Entornos definidos:

* Desarrollo.  
* Integración.  
* Preproducción.  
* Producción.

Cada entorno tendrá:

* configuración independiente;  
* secretos independientes;  
* base de datos independiente;  
* monitoreo independiente.

---

# **18\. Dependencias Tecnológicas**

## **Plataforma**

* Supabase.  
* PostgreSQL.  
* Edge Functions.

## **Lenguaje**

* TypeScript.

## **Runtime**

* Deno (Edge Functions de Supabase).

## **Comunicación**

* REST.  
* Realtime.  
* Webhooks.

---

# **19\. Reglas de Desarrollo**

Queda prohibido:

* escribir reglas financieras en TypeScript;  
* calcular tarifas en el Backend;  
* modificar tablas críticas mediante SQL directo;  
* almacenar secretos en código;  
* duplicar lógica existente en PostgreSQL.

---

# **20\. Arquitectura para Evolución**

Todo nuevo módulo deberá cumplir:

* pertenecer a un dominio;  
* tener responsabilidad única;  
* documentarse antes de implementarse;  
* reutilizar componentes compartidos;  
* mantener compatibilidad con la arquitectura existente.

---

# **21\.El Backend reconoce explícitamente los dominios "Admin" y "Audit" como parte del Modular Monolith (ver Documento 06 — DA-034), responsables respectivamente de:
Admin: operaciones exclusivas de Administrador/Superadministrador (gestión de usuarios administrativos, parámetros globales, liquidaciones extraordinarias).
Audit: generación y consulta de trazas de auditoría transversales a todos los dominios.

# **22\. Principio Rector Final**

> **El Backend de Tu Mobil Amigo constituye la capa de orquestación del ecosistema. Su misión es coordinar clientes, servicios externos y motores internos sin asumir reglas de negocio, preservando que todas las decisiones críticas permanezcan centralizadas en PostgreSQL, garantizando consistencia, seguridad, escalabilidad y una evolución tecnológica sostenible.**

Toda funcionalidad Backend deberá cumplir los controles definidos en el Documento 32 — Ciberseguridad.  

Fin de Documento 22 — Arquitectura Backend

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

Fin de Documento 23 — Edge Functions

# **Documento 24 — Sistema Realtime**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura, reglas y mecanismos de comunicación en tiempo real del ecosistema Tu Mobil Amigo.

El sistema Realtime será responsable de sincronizar instantáneamente eventos entre:

* Clientes.  
* Asesores.  
* Administradores.  
* Backend.  
* PostgreSQL.

Sin necesidad de recargar la aplicación.

---

# **2\. Principios**

El sistema Realtime deberá ser:

* Instantáneo.  
* Escalable.  
* Seguro.  
* Auditado.  
* Tolerante a fallos.  
* Event Driven.  
* Desacoplado.

---

# **3\. Tecnología Base**

La plataforma utilizará inicialmente:

Supabase Realtime

Basado en:

PostgreSQL Logical Replication

Esta decisión minimiza complejidad y costos durante las primeras etapas del proyecto.

---

# **4\. Filosofía de Operación**

Realtime no contiene lógica de negocio.

Realtime únicamente comunica eventos.

Ejemplo:

Servicio creado

↓

PostgreSQL decide

↓

Trigger

↓

Realtime publica

↓

Asesores reciben

Realtime nunca:

* calcula tarifas;  
* asigna servicios;  
* calcula cashback;  
* valida trust;  
* libera comisiones.

---

# **5\. Arquitectura General**

Cliente

↓

Edge Function

↓

PostgreSQL

↓

Trigger

↓

Canal Realtime

↓

Suscriptores

↓

Actualización UI  
---

# **6\. Eventos Oficiales**

Los eventos deberán representar hechos del negocio.

Nunca acciones técnicas.

Correcto:

servicio\_creado

servicio\_programado

oferta\_generada

oferta\_aceptada

servicio\_cancelado

servicio\_finalizado

Incorrecto:

insert\_servicio

update\_estado

query\_ejecutada  
---

# **7\. Dominios Realtime**

## **Operación**

Eventos relacionados con servicios.

## **Finanzas**

Eventos relacionados con movimientos financieros.

## **Trust**

Eventos relacionados con reputación.

## **IMF**

Eventos relacionados con maduración financiera.

## **Seguridad**

Eventos relacionados con fraude y dispositivos.

## **Administración**

Eventos relacionados con configuraciones y decretos.

---

# **8\. Canales Oficiales**

## **Canal Servicios**

rt\_servicios

Eventos:

* servicio\_creado  
* servicio\_programado  
* servicio\_cancelado  
* servicio\_finalizado

---

## **Canal Ofertas**

rt\_ofertas

Eventos:

* oferta\_generada  
* oferta\_expirada  
* oferta\_aceptada  
* contraoferta\_generada  
* contraoferta\_expirada

---

## **Canal Finanzas**

rt\_finanzas

Eventos:

* recarga\_aprobada  
* retiro\_aprobado  
* cashback\_generado  
* cashback\_liberado  
* comision\_generada  
* comision\_liberada

---

## **Canal Trust**

rt\_trust

Eventos:

* trust\_actualizado  
* categoria\_actualizada

---

## **Canal IMF**

rt\_imf

Eventos:

* imf\_actualizado  
* liberacion\_realizada

---

## **Canal Seguridad**

rt\_seguridad

Eventos:

* dispositivo\_bloqueado  
* fraude\_detectado  
* acceso\_sospechoso

---

# **9\. Servicios Inmediatos**

Flujo oficial:

Cliente

↓

Crear Servicio

↓

PostgreSQL

↓

Trigger

↓

Realtime

↓

Asesores Elegibles

↓

Visualización Instantánea

No se permitirá:

* polling constante;  
* recargas automáticas de pantalla;  
* consultas repetitivas.

---

# **10\. Servicios Programados**

Flujo:

Cliente

↓

Programa Servicio

↓

PostgreSQL

↓

Estado Programado

↓

Ventana de Publicación

↓

Realtime

↓

Asesores  
---

# **11\. Publicación Inteligente**

No todos los asesores recibirán todos los servicios.

Realtime deberá filtrar por:

* ciudad;  
* zona operativa;  
* tipo de servicio;  
* estado;  
* disponibilidad;  
* permisos.

Esto reduce tráfico y mejora escalabilidad.

---

# **12\. Protección Contra Autoasignación**

Regla obligatoria:

Un asesor jamás visualizará servicios generados por su propio UUID.

Validación:

servicio.usuario\_id

≠

asesor.usuario\_id

Si son iguales:

No publicar  
---

# **13\. Protección de Radicación en Calle**

Cuando un asesor radique un servicio mediante QR:

Validación:

UUID Asesor

≠

UUID Cliente

Si coinciden:

Violación de Política

Acciones:

* bloqueo de operación;  
* auditoría;  
* evento antifraude.

---

# **14\. Expiración de Ofertas**

Parámetro oficial:

180 segundos

Configurado exclusivamente desde Base de Datos.

Nunca desde código.

---

# **15\. Expiración de Contraofertas**

Regla oficial:

Mismo valor que Expiración de Ofertas

También configurable desde Base de Datos.

---

# **16\. Estado de Presencia**

Los asesores podrán reportar:

Disponible

Ocupado

Pausado

Desconectado

La presencia será utilizada únicamente como criterio operativo.

---

# **17\. Reconexión Automática**

Ante pérdida de conexión:

Desconexión

↓

Reconexión

↓

Sincronización

↓

Reanudación

El usuario no deberá reiniciar la aplicación.

---

# **18\. Entrega Garantizada**

Los eventos críticos deberán poder reconstruirse desde PostgreSQL.

Realtime acelera la comunicación.

La Base de Datos mantiene la verdad oficial.

---

# **19\. Recuperación de Estado**

Al reconectarse:

La aplicación deberá consultar:

* servicios activos;  
* ofertas activas;  
* movimientos pendientes;  
* notificaciones pendientes.

Nunca depender exclusivamente de eventos perdidos.

---

# **20\. Realtime Financiero**

Eventos permitidos:

* cashback generado;  
* cashback liberado;  
* comisión generada;  
* comisión liberada;  
* recarga aprobada;  
* retiro aprobado.

Eventos prohibidos:

* saldo completo de otros usuarios;  
* estructuras financieras internas;  
* cálculos del motor financiero.

---

# **21\. Seguridad de Canales**

Todo canal deberá validar:

* JWT válido;  
* usuario activo;  
* dispositivo autorizado;  
* permisos del rol.

---

# **22\. Row Level Security**

Todas las suscripciones deberán respetar RLS.

Un usuario solamente podrá recibir información autorizada.

---

# **23\. Protección Contra Enumeración**

Realtime nunca expondrá:

* IDs secuenciales;  
* correos;  
* teléfonos;  
* billeteras;  
* identificadores internos.

Se utilizarán UUID v4.

---

# **24\. Protección Contra Flooding**

Cada cliente tendrá límites configurables.

Ejemplos:

* máximo eventos por minuto;  
* máximo suscripciones simultáneas;  
* máximo reconexiones.

Parámetros almacenados en Base de Datos.

---

# **25\. Auditoría**

Todo evento crítico generará:

* timestamp;  
* usuario;  
* dispositivo;  
* canal;  
* tipo de evento;  
* resultado.

---

# **26\. Observabilidad**

Se monitoreará:

* conexiones activas;  
* eventos por segundo;  
* latencia;  
* reconexiones;  
* errores.

---

# **27\. Escalabilidad**

El diseño deberá soportar:

* múltiples ciudades;  
* múltiples países;  
* múltiples tipos de servicio;  
* millones de eventos mensuales.

Sin rediseño arquitectónico.

---

# **28\. Realtime y Multinivel**

Eventos permitidos:

* comisión generada;  
* comisión liberada;  
* cambio de categoría.

Eventos prohibidos:

* estructura completa de red;  
* datos financieros de terceros.

---

# **29\. Realtime y Trust**

Eventos permitidos:

* actualización de categoría;  
* actualización de Trust Score.

La fórmula de cálculo nunca será expuesta.

---

# **30\. Realtime y Seguridad**

El motor antifraude podrá emitir:

fraude\_detectado

dispositivo\_bloqueado

riesgo\_alto

Estos eventos podrán provocar:

* cierre de sesión;  
* bloqueo temporal;  
* validaciones adicionales.

---

# **31\. Integración con Notificaciones**

Realtime y notificaciones son sistemas diferentes.

Realtime  
↓  
Usuario conectado

Push  
↓  
Usuario desconectado

El Backend decidirá cuál utilizar.

---

# **32\. Evolución Futura**

La arquitectura deberá permitir migrar posteriormente a:

* Redis Streams.  
* Kafka.  
* NATS.  
* RabbitMQ.

Sin modificar la lógica de negocio.

---

# **33\. Workflow Engine (Decisión de Evolución)**

Se aprueba como línea evolutiva futura la incorporación de un:

Workflow Engine

Responsable de coordinar procesos complejos mediante máquinas de estado.

Ejemplos:

* ciclo completo de servicios;  
* flujo de pagos;  
* gestión de retiros;  
* liberación IMF;  
* resolución de incidencias.

No forma parte de la V1.

La V1 operará mediante:

* PostgreSQL;  
* Triggers;  
* Realtime;  
* Edge Functions.

---

# **34\. Catálogo de Eventos
Los eventos operativos de negocio transmitidos por este canal (nuevos servicios, ofertas, contraofertas, cambios de estado) deben mantenerse alineados con el Documento 42A — Catálogo de Alertas e Incidentes en lo que respecta a nomenclatura y severidad, para evitar duplicidad de criterios entre eventos operativos y eventos de alerta/incidente.

# **35\. Principio Rector Final**

> **Realtime es un mecanismo de sincronización y distribución de eventos, no un motor de negocio. Toda decisión crítica permanece en PostgreSQL, mientras Realtime garantiza que clientes, asesores y administradores reciban información autorizada de forma instantánea, segura, auditable y escalable.**

Fin de Documento 24 — Sistema Realtime

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

# **38\. Endpoints Exclusivos de Superadministrador
Los siguientes endpoints requieren rol Superadministrador (validado mediante fn_usuario_tiene_permiso — ver Documento 20):
POST /admin/periodos/reapertura
POST /admin/liquidaciones/extraordinaria
PUT /admin/parametros-globales
POST /admin/usuarios-administrativos
Todo intento de acceso sin el permiso correspondiente deberá registrarse como evento de seguridad (ver Documento 32).

# **39\. Principio Rector Final**

> **Las APIs de Tu Mobil Amigo constituyen una capa segura, versionada y desacoplada de acceso al ecosistema. Su función es exponer capacidades de negocio sin revelar la implementación interna, garantizando seguridad, trazabilidad, escalabilidad y compatibilidad futura, mientras toda la lógica crítica permanece centralizada en PostgreSQL y sus motores especializados.**

La seguridad operativa de APIs se regirá por los controles definidos en el Documento 32 y posteriormente en el Documento 38A.

Fin de Documento 25 — APIs

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

# **33\ Integración ERP
Objetivo:
Exportación de liquidaciones, pagos, cashback y comisiones hacia sistemas contables externos (ver Documento 06 — DA-032, Documento 09 — Sección 31).
[N+1]. Estrategia ERP
Fase Inicial:
Exportación manual mediante reportes (Excel/CSV) generados desde el portal Superadministrador (ver Documento 28, Sección 34).
Fase de Crecimiento:
Integración directa mediante adaptador `ERPAdapter`, siguiendo el mismo principio de abstracción ya aplicado a `PSEAdapter` y `MapAdapter`.
[N+2]. Abstracción ERP
Interfaz:
ERPAdapter
Implementaciones posibles:
Siigo
Alegra
Odoo
SAP Business One
World Office
(ver Documento 28, Sección 30 — ERP Futuro, para el listado ya aprobado de proveedores candidatos)

# **34\. Principio Rector Final**

> **Toda integración de Tu Mobil Amigo deberá implementarse mediante capas de abstracción desacopladas, configurables y seguras, garantizando que ningún proveedor externo tenga dependencia estructural sobre la plataforma y permitiendo la evolución tecnológica sin afectar la operación, la seguridad ni las reglas del negocio.**

Fin de Documento 26 — Integraciones

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

Fin de Anexo C — Principios de Arquitectura Backend
