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
