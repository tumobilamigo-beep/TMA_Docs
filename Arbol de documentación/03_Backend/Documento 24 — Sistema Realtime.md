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

# **34\. Principio Rector Final**

> **Realtime es un mecanismo de sincronización y distribución de eventos, no un motor de negocio. Toda decisión crítica permanece en PostgreSQL, mientras Realtime garantiza que clientes, asesores y administradores reciban información autorizada de forma instantánea, segura, auditable y escalable.**

