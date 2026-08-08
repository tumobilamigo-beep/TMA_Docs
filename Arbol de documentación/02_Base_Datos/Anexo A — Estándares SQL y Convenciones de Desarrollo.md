# **Anexo A — Estándares SQL y Convenciones de Desarrollo**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Establecer los estándares oficiales para el desarrollo de la base de datos de Tu Mobil Amigo, garantizando uniformidad, mantenibilidad, rendimiento y seguridad durante todo el ciclo de vida del proyecto.

Este documento es de obligatorio cumplimiento para cualquier modificación realizada sobre PostgreSQL/Supabase.

---

# **2\. Principios Generales**

Toda implementación deberá cumplir los siguientes principios:

* Simplicidad.  
* Legibilidad.  
* Modularidad.  
* Reutilización.  
* Escalabilidad.  
* Trazabilidad.  
* Parametrización.  
* Seguridad.

---

# **3\. Convenciones de Nombres**

## **3.1 Tablas**

Siempre:

* minúsculas  
* snake\_case  
* plural

Ejemplos

usuarios

servicios

movimientos\_billetera

variables\_tarifarias  
---

## **3.2 Columnas**

Siempre:

snake\_case

Ejemplos

usuario\_id

created\_at

trust\_score

cashback\_liberado  
---

## **3.3 Claves Primarias**

Siempre

id UUID

Nunca

id SERIAL  
---

## **3.4 Claves Foráneas**

Formato

tabla\_id

Ejemplos

usuario\_id

servicio\_id

vehiculo\_id

ciudad\_id  
---

# **4\. Convención de Objetos SQL**

## **Funciones**

Prefijo

fn\_

Ejemplo

fn\_calcular\_tarifa()

fn\_finalizar\_servicio()  
---

## **Procedimientos**

sp\_  
---

## **Triggers**

trg\_  
---

## **Índices**

idx\_  
---

## **Constraints**

ck\_  
---

## **Foreign Keys**

fk\_  
---

## **Unique**

uq\_  
---

## **Views**

vw\_  
---

## **Materialized Views**

mv\_  
---

# **5\. Estándar para Funciones**

Toda función deberá contener:

* Objetivo.  
* Parámetros.  
* Valor de retorno.  
* Excepciones.  
* Dependencias.  
* Registro de auditoría cuando aplique.

---

Ejemplo

fn\_calcular\_tarifa()

Entrada:  
    ciudad\_id  
    tipo\_servicio  
    distancia

Salida:  
    valor\_total  
---

# **6\. Estándar de Transacciones**

Toda operación crítica utilizará transacciones.

Ejemplo

BEGIN

↓

Validaciones

↓

Operación

↓

Auditoría

↓

COMMIT

En caso de error

ROLLBACK

obligatorio.

---

# **7\. Manejo de Errores**

Nunca utilizar errores genéricos.

Cada excepción deberá poseer:

* Código.  
* Mensaje.  
* Severidad.  
* Fecha.  
* Usuario.  
* Función.  
* Parámetros.

---

Ejemplo

ERR-TRUST-001

Trust insuficiente.  
---

# **8\. Política de Soft Delete**

Queda prohibido eliminar registros críticos.

Toda eliminación utilizará:

activo

deleted\_at

deleted\_by  
---

# **9\. Política de Auditoría**

Toda operación deberá registrar:

* usuario  
* fecha  
* IP  
* dispositivo  
* función  
* valores anteriores  
* valores nuevos

---

# **10\. Uso de JSONB**

JSONB únicamente podrá utilizarse cuando:

* la estructura sea dinámica;  
* no sea posible modelarla relacionalmente;  
* exista una justificación documentada.

Nunca utilizar JSONB para reemplazar un modelo relacional correctamente diseñado.

---

# **11\. Versionamiento**

Toda configuración deberá permitir:

vigente\_desde

vigente\_hasta

version

estado

Nunca sobrescribir registros históricos.

---

# **12\. Índices**

Se crearán índices únicamente sobre:

* UUID.  
* Foreign Keys.  
* Fechas.  
* Estados.  
* Campos de búsqueda frecuente.

Antes de crear un nuevo índice deberá verificarse su impacto mediante análisis del plan de ejecución.

---

# **13\. Optimización de Consultas**

Toda consulta crítica deberá analizarse utilizando:

EXPLAIN ANALYZE

No se aprobarán consultas con recorridos completos de tablas (Full Table Scan) cuando exista una alternativa eficiente mediante índices o rediseño.

---

# **14\. Política de Parametrización**

Queda prohibido escribir valores fijos en funciones o procedimientos.

Ejemplos prohibidos:

180 segundos

5000 COP

15 %

2 horas

12 horas

Estos valores deberán obtenerse desde las tablas de configuración.

---

# **15\. Seguridad (RLS)**

Toda tabla deberá implementar Row Level Security (RLS).

Las políticas deberán seguir el principio de mínimo privilegio.

Cada usuario solo podrá acceder a la información estrictamente necesaria para su rol.

---

# **16\. Uso de Edge Functions**

Flutter, React y Telegram no accederán directamente a operaciones críticas.

El flujo oficial será:

Cliente

↓

Edge Function

↓

Función PostgreSQL

↓

Respuesta  
---

# **17\. Política de Migraciones**

Toda modificación estructural deberá realizarse mediante scripts versionados.

Cada migración deberá ser:

* incremental;  
* reversible cuando sea posible;  
* identificable mediante versión;  
* documentada.

Queda prohibido modificar la estructura manualmente en producción.

---

# **18\. Gestión de Rendimiento**

Se deberán monitorizar periódicamente:

* tiempo medio de ejecución de funciones;  
* consultas lentas;  
* uso de índices;  
* bloqueos;  
* consumo de CPU;  
* consumo de memoria;  
* crecimiento de tablas.

---

# **19\. Gestión de Bloqueos**

Las transacciones deberán mantenerse abiertas el menor tiempo posible.

Se evitarán:

* bloqueos innecesarios;  
* transacciones largas;  
* esperas activas;  
* actualizaciones masivas sin segmentación.

---

# **20\. Integridad Referencial**

Toda relación entre entidades deberá implementarse mediante claves foráneas.

Solo podrán omitirse cuando exista una justificación técnica documentada y aprobada.

---

# **21\. Escalabilidad**

La estructura deberá permitir incorporar:

* nuevas ciudades;  
* nuevos países;  
* nuevas monedas;  
* nuevos idiomas;  
* nuevos métodos de pago;  
* nuevos servicios;  
* nuevos tipos de vehículos;  
* nuevos motores de incentivos;  
* nuevos proveedores cartográficos.

Sin rediseñar el modelo existente.

---

# **22\. Política de Documentación**

Toda función, trigger o procedimiento deberá mantenerse sincronizado con los documentos oficiales del proyecto.

No se permitirá código sin documentación.

---

# **23\. Revisión de Código**

Toda modificación deberá verificar, como mínimo:

* cumplimiento de nomenclatura;  
* rendimiento;  
* seguridad;  
* integridad referencial;  
* compatibilidad con RLS;  
* cumplimiento de la arquitectura por dominios;  
* ausencia de lógica de negocio en interfaces cliente.

---

# **24\. Arquitectura de Base de Datos**

La base de datos deberá seguir el siguiente flujo de responsabilidades:

Flutter / React / Telegram  
            │  
            ▼  
      Edge Functions  
            │  
            ▼  
    Funciones PostgreSQL  
            │  
            ▼  
        Triggers  
            │  
            ▼  
      Auditoría / Realtime

Ninguna capa superior podrá omitir las capas inferiores para ejecutar operaciones críticas.

---

# **25\. Principio Rector Final**

> **La base de datos de Tu Mobil Amigo constituye el núcleo transaccional y normativo del sistema. Toda implementación deberá priorizar la integridad, la trazabilidad y la parametrización sobre la rapidez de desarrollo, garantizando que el crecimiento futuro del proyecto se produzca mediante evolución controlada y no mediante refactorizaciones disruptivas.**

