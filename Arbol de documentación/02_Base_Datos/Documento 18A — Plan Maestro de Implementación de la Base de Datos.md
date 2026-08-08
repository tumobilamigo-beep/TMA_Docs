# **Documento 18A — Plan Maestro de Implementación de la Base de Datos**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir el proceso oficial para construir, validar, desplegar y evolucionar la base de datos de Tu Mobil Amigo.

Este documento establece el orden de implementación, las dependencias técnicas y los criterios de aprobación de cada fase.

Ninguna fase podrá iniciarse hasta que la anterior haya sido aprobada.

---

# **2\. Principios**

Toda implementación deberá cumplir los siguientes principios:

* Incremental.  
* Reversible.  
* Versionada.  
* Parametrizada.  
* Auditada.  
* Probada.  
* Documentada.

---

# **3\. Flujo General**

Documentación

↓

Diseño

↓

Migraciones SQL

↓

Validación

↓

Pruebas

↓

Integración

↓

Producción  
---

# **4\. Reglas Generales**

Antes de crear cualquier objeto deberán cumplirse las siguientes reglas.

✓ Documento aprobado.

✓ Dependencias implementadas.

✓ Convenciones SQL cumplidas.

✓ RLS definido.

✓ Auditoría definida.

✓ Índices definidos.

✓ Casos de prueba definidos.

---

# **5\. Orden Oficial de Construcción**

## **Fase 0 — Infraestructura**

Objetivo

Preparar Supabase.

Incluye:

* Proyecto.  
* Regiones.  
* Storage.  
* Secrets.  
* Extensiones PostgreSQL.  
* Roles.  
* Esquemas.  
* Configuración inicial.

Entregable:

Base vacía lista para construir.

---

# **Fase 1 — Catálogos Maestros**

Crear únicamente tablas de referencia.

Ejemplos:

* países  
* departamentos  
* ciudades  
* monedas  
* tipos\_servicio  
* tipos\_vehiculo  
* marcas  
* colores  
* parámetros\_generales  
* estados

No existen aún usuarios ni servicios.

---

# **Fase 2 — Núcleo (Core)**

Crear:

* usuarios  
* perfiles  
* documentos  
* dispositivos  
* vehículos  
* asesores  
* clientes  
* QR

Al finalizar esta fase será posible registrar usuarios.

---

# **Fase 3 — Configuración**

Crear:

* variables\_tarifarias  
* decretos  
* configuración  
* versiones

No se implementa aún el motor tarifario.

Solo parametrización.

---

# **Fase 4 — Operación**

Crear:

* servicios  
* ofertas  
* contraofertas  
* servicios\_programados  
* historial\_estados

Al finalizar esta fase podrá ejecutarse un flujo completo de solicitud y asignación.

---

# **Fase 5 — Finanzas**

Crear:

* billeteras  
* bolsa\_operativa  
* movimientos  
* cashback  
* comisiones  
* reservas  
* retiros  
* recargas

Implementar:

* distribución  
* liquidación  
* liberación

---

# **Fase 6 — Multinivel**

Crear:

* red  
* upliners  
* historial\_red  
* comisiones\_red

Implementar:

* distribución  
* validaciones  
* prevención de ciclos

---

# **Fase 7 — Trust**

Crear:

* trust  
* IPA  
* IPR  
* categorías

Implementar:

* actualización automática  
* historial

---

# **Fase 8 — IMF**

Crear:

* historial IMF  
* liberaciones  
* reglas

Implementar:

* cálculo  
* liberación parcial  
* maduración financiera

---

# **Fase 9 — Antifraude**

Crear:

* eventos\_fraude  
* fingerprints  
* IPs  
* dispositivos  
* riesgo

Implementar:

* motor de detección  
* alertas

---

# **Fase 10 — Auditoría**

Crear:

* logs  
* auditoría  
* reconstrucción histórica

Esta fase deberá cubrir el 100% de las tablas críticas.

---

# **6\. Desarrollo por Fases**

Cada fase seguirá exactamente el mismo proceso.

Crear tablas

↓

Constraints

↓

Foreign Keys

↓

Índices

↓

Funciones

↓

Triggers

↓

RLS

↓

Realtime

↓

Seeds

↓

Testing

↓

Aprobación

Ningún paso podrá omitirse.

---

# **7\. Orden de Desarrollo de Cada Tabla**

Para cada tabla individual:

## **Paso 1**

Diseño lógico.

---

## **Paso 2**

CREATE TABLE.

---

## **Paso 3**

Constraints.

---

## **Paso 4**

Índices.

---

## **Paso 5**

Comentarios.

---

## **Paso 6**

Funciones.

---

## **Paso 7**

Triggers.

---

## **Paso 8**

RLS.

---

## **Paso 9**

Seeds.

---

## **Paso 10**

Pruebas.

---

# **8\. Migraciones**

Toda modificación deberá realizarse mediante migraciones versionadas.

Formato recomendado:

0001\_schema.sql

0002\_catalogos.sql

0003\_core.sql

0004\_operacion.sql

0005\_finanzas.sql

Nunca editar migraciones ya ejecutadas.

Las modificaciones posteriores deberán realizarse mediante nuevas migraciones.

---

# **9\. Datos Semilla (Seeds)**

Los datos iniciales deberán separarse completamente de la estructura.

Ejemplos:

* países  
* ciudades  
* tipos de servicio  
* tipos de vehículo  
* colores  
* parámetros  
* configuraciones  
* estados

Nunca insertar datos de prueba en producción.

---

# **10\. Estrategia de Pruebas**

Cada fase deberá aprobar:

## **Integridad**

* Relaciones.  
* Restricciones.  
* Auditoría.

---

## **Rendimiento**

* Índices.  
* Planes de ejecución.  
* Consultas críticas.

---

## **Seguridad**

* RLS.  
* Permisos.  
* Roles.

---

## **Funcional**

* Funciones.  
* Triggers.  
* Realtime.

---

## **Escalabilidad**

Pruebas con:

* 100 usuarios.  
* 1.000 usuarios.  
* 10.000 usuarios.  
* 100.000 usuarios.  
* 1 millón de registros.

---

# **11\. Política de Versionado**

Cada versión deberá registrar:

* número;  
* fecha;  
* responsable;  
* motivo;  
* dependencias;  
* migraciones aplicadas.

---

# **12\. Integración Continua**

Toda modificación estructural deberá ejecutarse automáticamente en un entorno de pruebas antes de llegar a producción.

No se permitirán cambios manuales en producción.

---

# **13\. Criterios de Aprobación**

Una fase solo podrá aprobarse cuando:

✓ Todas las tablas compilen.

✓ Todas las funciones compilen.

✓ Todos los triggers funcionen.

✓ Todas las políticas RLS funcionen.

✓ Todas las pruebas pasen.

✓ La documentación esté actualizada.

---

# **14\. Estrategia de Despliegue**

Se definen tres entornos independientes.

## **Desarrollo**

Uso diario.

---

## **Preproducción**

Pruebas completas.

---

## **Producción**

Usuarios reales.

Nunca desarrollar directamente sobre Producción.

---

# **15\. Plan de Recuperación**

Cada despliegue deberá incluir:

* copia de seguridad;  
* script de reversión;  
* validación posterior;  
* verificación de integridad.

Toda migración deberá poder revertirse de forma controlada.

---

# **16\. Checklist de Implementación**

Antes de cerrar una fase deberá verificarse:

* Documentación aprobada.  
* Modelo actualizado.  
* SQL validado.  
* Funciones revisadas.  
* Triggers revisados.  
* Índices optimizados.  
* RLS validado.  
* Seeds cargados.  
* Auditoría operativa.  
* Realtime operativo.  
* Casos de prueba ejecutados.  
* Rendimiento aceptable.

---

# **17\. Cronograma Recomendado**

| Etapa | Resultado |
| ----- | ----- |
| Infraestructura | Supabase listo |
| Catálogos | Datos maestros |
| Core | Usuarios operativos |
| Operación | Servicios funcionando |
| Finanzas | Billeteras activas |
| Multinivel | Red funcional |
| Trust | Reputación operativa |
| IMF | Liberaciones automáticas |
| Antifraude | Riesgo controlado |
| Auditoría | Sistema trazable |

Cada etapa constituye un hito verificable y no depende de funcionalidades aún no implementadas.

---

# **18\. Criterios de Evolución**

Ninguna fase podrá modificarse directamente una vez aprobada.

Las mejoras deberán implementarse mediante nuevas migraciones y actualización de la documentación correspondiente.

---

# **19\. Estrategia de Automatización**

Todo el proceso deberá poder ejecutarse de forma automatizada mediante un pipeline que incluya:

* aplicación ordenada de migraciones;  
* carga de datos semilla;  
* ejecución de pruebas unitarias e integración;  
* validación de políticas RLS;  
* verificación de rendimiento;  
* generación de reportes de despliegue.

El objetivo es que una nueva instancia de la base de datos pueda construirse desde cero de forma reproducible y sin intervención manual.

---

# **20\. Principio Rector Final**

> **La base de datos de Tu Mobil Amigo no se construye mediante scripts aislados, sino mediante un proceso controlado, incremental y verificable. Cada fase produce un estado funcional, auditable y desplegable del sistema, garantizando que la evolución tecnológica preserve la integridad del negocio, reduzca el riesgo operativo y permita la incorporación de nuevas capacidades sin comprometer la arquitectura existente.**

