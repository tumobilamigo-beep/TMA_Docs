# **Documento 21 — Catálogo de Triggers**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir el catálogo oficial de triggers de la base de datos, estableciendo su finalidad, eventos asociados y responsabilidades.

Los triggers tienen como misión garantizar la consistencia automática del sistema, la trazabilidad de las operaciones y la sincronización entre los diferentes dominios del negocio.

---

# **2\. Principios**

## **CT-001**

Los triggers no contienen reglas de negocio.

Toda lógica será ejecutada mediante funciones documentadas en el Documento 20\.

---

## **CT-002**

Cada trigger tendrá una única responsabilidad.

---

## **CT-003**

Los triggers nunca modificarán directamente múltiples dominios.

Si una operación afecta varios dominios, invocará la función correspondiente.

---

## **CT-004**

Todo trigger deberá ser idempotente.

Ejecutarlo dos veces nunca deberá generar resultados distintos.

---

## **CT-005**

Los triggers deberán ejecutarse dentro de transacciones.

---

# **3\. Clasificación**

Los triggers quedan agrupados por dominio.

Core

Operación

Finanzas

Trust

Seguridad

Configuración

Auditoría  
---

# **4\. Triggers del Dominio Core**

## **trg\_usuario\_creado**

Evento

AFTER INSERT

Tabla

core.usuarios

Responsabilidades

* Crear perfil inicial.  
* Crear QR.  
* Crear billeteras.  
* Inicializar Trust.  
* Inicializar IPA.  
* Inicializar IPR.  
* Inicializar IMF.  
* Registrar auditoría.

Función ejecutada

fn\_registrar\_usuario()  
---

## **trg\_documento\_actualizado**

Evento

AFTER UPDATE

Tabla

usuarios\_documentos

Responsabilidad

Revalidar documentación.

---

## **trg\_dispositivo\_registrado**

Evento

AFTER INSERT

Acciones

* Validar fingerprint.  
* Detectar duplicados.  
* Registrar auditoría.

---

# **5\. Triggers del Dominio Operación**

## **trg\_servicio\_creado**

Evento

AFTER INSERT

Tabla

servicios

Responsabilidades

* Validar servicio.  
* Publicar ofertas.  
* Registrar auditoría.

---

## **trg\_servicio\_programado**

Evento

AFTER INSERT

Tabla

servicios\_programados

Acciones

* Validar ventana de 2 a 12 horas.  
* Registrar incentivo financiero.  
* Programar publicación automática.

---

## **trg\_oferta\_creada**

Evento

AFTER INSERT

Acciones

* Programar expiración.  
* Registrar evento.

---

## **trg\_contraoferta\_creada**

Acciones

* Validar expiración.  
* Registrar historial.

---

## **trg\_servicio\_finalizado**

Este es uno de los triggers más importantes.

Evento

AFTER UPDATE

Condición

Estado:

FINALIZADO

Acciones

Invocar

fn\_finalizar\_servicio()

La función realizará:

* Liquidación financiera.  
* Descuento de Bolsa Operativa.  
* Distribución de comisiones.  
* Generación de Cashback.  
* Actualización Trust.  
* Actualización IPA.  
* Actualización IPR.  
* Actualización IMF.  
* Actualización Categoría.  
* Auditoría.

---

# **6\. Triggers del Dominio Finanzas**

## **trg\_movimiento\_financiero**

Evento

AFTER INSERT

Tabla

movimientos\_billetera

Acciones

* Actualizar saldo.  
* Validar consistencia.  
* Registrar auditoría.

---

## **trg\_recarga\_confirmada**

Condición

Estado:

APROBADA

Acciones

* Actualizar Bolsa Operativa.  
* Registrar movimiento.  
* Notificar usuario.

---

## **trg\_retiro\_aprobado**

Acciones

* Debitar billetera.  
* Registrar movimiento.  
* Registrar auditoría.

---

## **trg\_cashback\_generado**

Acciones

* Crear registro de Cashback Ganado.  
* Programar liberación.

---

## **trg\_cashback\_liberado**

Acciones

* Trasladar a Cashback Liberado.  
* Registrar histórico.

---

# **7\. Triggers del Dominio Trust**

## **trg\_calificacion\_insertada**

Evento

AFTER INSERT

Tabla

calificaciones

Acciones

* Recalcular Trust.  
* Recalcular IPA.  
* Recalcular Categoría.

---

## **trg\_servicio\_qr\_registrado**

Acciones

* Actualizar IPA.  
* Actualizar IMF.

---

## **trg\_red\_actualizada**

Acciones

* Recalcular IPR.

---

# **8\. Triggers del Dominio Seguridad**

## **trg\_login**

Acciones

* Registrar dispositivo.  
* Registrar IP.  
* Evaluar riesgo.

---

## **trg\_evento\_antifraude**

Acciones

* Calcular nivel de riesgo.  
* Generar alertas.  
* Registrar auditoría.

---

## **trg\_qr\_utilizado**

Acciones

Validar

UUID Cliente ≠ UUID Asesor

Si son iguales:

* Cancelar operación.  
* Registrar fraude.  
* Notificar.

---

# **9\. Triggers del Dominio Configuración**

## **trg\_variable\_tarifaria**

Evento

AFTER INSERT

Acciones

* Crear nueva versión.  
* Registrar histórico.

---

## **trg\_decreto**

Acciones

* Versionar parámetros.  
* Mantener histórico.

---

# **10\. Triggers del Dominio Auditoría**

## **trg\_auditoria\_global**

Todas las tablas críticas tendrán un trigger común.

Eventos

INSERT

UPDATE

DELETE (Soft Delete)

Información registrada

* Usuario.  
* Fecha.  
* IP.  
* Dispositivo.  
* Valores anteriores.  
* Valores nuevos.

---

## **trg\_error**

Registra excepciones críticas.

---

# **11\. Flujo General**

Usuario

↓

Flutter / React / Telegram

↓

Edge Function

↓

Función PostgreSQL

↓

INSERT / UPDATE

↓

Trigger

↓

Auditoría

↓

Realtime

↓

Clientes conectados  
---

# **12\. Integración con Realtime**

Los triggers podrán publicar eventos hacia Supabase Realtime únicamente para:

* Nuevos servicios.  
* Cambios de estado.  
* Asignaciones.  
* Mensajes.  
* Notificaciones.  
* Cambios en Bolsa Operativa.  
* Actualizaciones de Cashback.  
* Alertas críticas.

No deberán emitir eventos para cambios internos que no aporten valor a los clientes conectados.

---

# **13\. Restricciones**

Queda prohibido que un trigger:

* Llame directamente a otro trigger.  
* Modifique múltiples dominios sin pasar por funciones.  
* Contenga consultas complejas de negocio.  
* Realice cálculos financieros.  
* Calcule tarifas.  
* Calcule Trust Score.  
* Tome decisiones operativas.

Todas esas responsabilidades pertenecen exclusivamente a las funciones del Documento 20\.

---

# **14\. Monitorización**

Todos los triggers deberán registrar:

* Tiempo de ejecución.  
* Resultado.  
* Errores.  
* Número de registros afectados.

Estos indicadores permitirán identificar cuellos de botella y optimizar el rendimiento de la base de datos.

---

# **15\. Política de Evolución**

Antes de crear un nuevo trigger se deberá verificar si la funcionalidad puede incorporarse a uno existente mediante una nueva función especializada.

El objetivo es mantener un conjunto reducido de triggers, cada uno claramente identificado y con una responsabilidad específica.

---

## **Nuevos Triggers**

### **trg\_generar\_cierre\_mensual**

# Ejecuta el proceso de cierre.

# ---

### **trg\_generar\_liquidacion**

# Genera las liquidaciones correspondientes.

# ---

### **trg\_actualizar\_estado\_pago**

# Actualiza estados posteriores al pago.

trg\_liquidacion\_aprobada

trg\_liquidacion\_ejecutada

trg\_liquidacion\_pagada

# **16\. Principio Rector Final**

> **Los triggers de Tu Mobil Amigo representan el mecanismo automático de sincronización entre dominios, no el lugar donde reside la lógica del negocio. Toda decisión funcional deberá implementarse mediante funciones especializadas, mientras que los triggers actuarán únicamente como detectores de eventos y orquestadores de la ejecución.**

