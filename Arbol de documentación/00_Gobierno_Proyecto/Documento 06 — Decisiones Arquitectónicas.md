Documento 06 — Decisiones Arquitectónicas

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Este documento registra las decisiones estratégicas, funcionales, tecnológicas y arquitectónicas oficialmente aprobadas para Tu Mobil Amigo V1.0.

Su propósito es evitar que decisiones previamente aceptadas vuelvan a discutirse o modificarse sin justificación técnica, financiera o de seguridad.

2\. Regla de Gobierno

Toda decisión registrada en este documento se considera:

OFICIAL

Hasta que exista:

Nueva evaluación.  
Justificación documentada.  
Aprobación formal.

DA-001 — Tecnologías Oficiales  
Aplicaciones Operativas  
Flutter  
Utilizado para:  
Cliente.  
Asesor.  
---

Plataforma Administrativa  
React  
Next.js  
TypeScript  
Utilizado para:

* Administración.  
* Finanzas.  
* Auditoría.  
* Antifraude.  
* Reportes.

---

## Backend

Supabase  
PostgreSQL

DA-002 — Backend Oficial  
Decisión  
El backend será construido utilizando:  
Supabase  
Componentes  
PostgreSQL.  
Realtime.  
Storage.  
Authentication.  
Edge Functions.  
Estado  
APROBADA

DA-003 — Base de Datos Oficial  
Decisión  
La base de datos oficial será:  
PostgreSQL  
Estado  
APROBADA  

DA-004 — Metodología de Construcción  
Decisión  
El proyecto deberá construirse por fases.  
Orden obligatorio:  
Gobierno  
↓  
Arquitectura  
↓  
Base de Datos  
↓  
Backend  
↓  
Flutter  
↓  
Seguridad  
↓  
Testing  
↓  
Producción  
Estado  
APROBADA

DA-005 — Modelo Oficial de Roles

#### Contexto

La plataforma requiere una separación estricta entre usuarios operativos, administrativos y estratégicos.

Inicialmente se definieron tres roles.

Posteriormente la evolución del proyecto hizo necesaria la incorporación de un cuarto rol con capacidades superiores de gobierno tecnológico y operativo.

#### Decisión

La plataforma operará oficialmente con cuatro roles:

##### Cliente

Usuario consumidor de servicios.

Responsabilidades:

* solicitar servicios;
* negociar ofertas;
* gestionar perfil;
* participar en programas de cashback;
* participar en red multinivel.

##### Asesor

Prestador de servicios.

Responsabilidades:

* recibir ofertas;
* negociar servicios;
* ejecutar servicios;
* administrar disponibilidad.

##### Administrador

Responsable de la operación diaria.

Responsabilidades:

* gestión operativa;
* soporte;
* monitoreo;
* validaciones;
* conciliaciones autorizadas;
* gestión de usuarios.

##### Superadministrador

Máxima autoridad funcional y tecnológica del sistema.

Responsabilidades:

* administración global;
* gestión de configuraciones críticas;
* gestión de infraestructura;
* gestión de releases;
* reapertura de períodos;
* administración de secretos;
* gestión de incidentes críticos;
* control de seguridad;
* aprobación de cambios estructurales.

#### Consecuencias

Toda implementación futura deberá respetar este modelo de cuatro roles.

Cualquier ampliación requerirá una nueva ADR.

DA-006 — Servicios Iniciales  
Decisión  
La primera versión operará con:  
Mototaxi.  
Taxi.  
Estado  
APROBADA

DA-007 — Servicios Futuros  
Decisión  
La arquitectura deberá soportar:  
Mensajería.  
Domicilios.  
Motocarro.  
Carga liviana.  
Sin rediseños estructurales.  
Estado  
APROBADA

DA-008 — Modalidades de Servicio  
Decisión  
Existirán dos modalidades oficiales.

Servicio Digital

Generado desde la plataforma.  
Servicio Externo  
Generado fuera de la plataforma y registrado mediante QR.  
Estado  
APROBADA

DA-009 — Sistema QR  
Decisión  
Todo usuario tendrá un QR único.  
El QR será utilizado para:  
Identificación.  
Registro de servicios externos.  
Trazabilidad.  
Estado  
APROBADA

DA-010 — Restricción de Autobeneficio  
Decisión  
Queda prohibido:  
cliente\_uuid \= asesor\_uuid  
Aplicación  
Servicios.  
Beneficios.  
Cashback.  
Comisiones.  
Estado  
APROBADA

DA-011 — Sistema Tarifario  
Decisión  
El sistema calculará una tarifa sugerida.  
La tarifa será utilizada como referencia de negociación.  
La plataforma no impondrá un precio obligatorio.  
Estado  
APROBADA

DA-012 — Motor de Negociación  
Decisión  
El cliente podrá ofertar.  
El asesor podrá:  
Aceptar.  
Rechazar.  
Contraofertar una única vez.  
La decisión final siempre pertenecerá al cliente.  
Estado  
APROBADA

DA-013 — Exclusividad Transaccional  
Decisión  
Un asesor podrá mantener múltiples negociaciones abiertas simultáneamente.  
Cuando un cliente acepte una negociación:  
El servicio será adjudicado.  
Todas las demás negociaciones quedarán cerradas.  
Todos los participantes serán notificados.  
Estado  
APROBADA

DA-014 — Trust Score  
Decisión  
Todos los usuarios tendrán un Trust Score.  
Restricción  
El Trust Score jamás modificará:  
Tarifas.  
Valores sugeridos.  
Costos operativos.  
Función  
Medir confianza y riesgo.  
Estado  
APROBADA

DA-015 — Score de Negociación  
Decisión  
El historial de negociación influirá en la amplitud permitida para futuras negociaciones.  
No modificará el valor base calculado por el sistema.  
Estado  
APROBADA

DA-016 — Categorías del Ecosistema  
Decisión  
Las categorías oficiales serán:  
Explorador  
↓  
Viajero  
↓  
Experto  
↓  
Leyenda  
Estado  
APROBADA

DA-017 — Modelo Multinivel  
Decisión  
La red multinivel operará inicialmente con:  
2 niveles  
Nivel 1  
Padre.  
Nivel 2  
Abuelo.  
Estado  
APROBADA

DA-018 — Billeteras del Cliente  
Decisión  
El cliente tendrá una única billetera de beneficios.  
Componentes  
Saldo Disponible.  
Cashback Ganado.  
Cashback Liberado.  
Comisiones Ganadas.  
Comisiones Liberadas.  
Histórico.  
Estado  
APROBADA

DA-019 — Billeteras del Asesor  
Decisión  
El asesor tendrá dos mundos financieros independientes.  
Bolsa Operativa  
Para operar.  
Bolsa de Beneficios  
Para incentivos.  
Restricción  
No podrán mezclarse.  
Estado  
APROBADA

DA-020 — Saldo Operativo Mínimo  
Decisión

Todo asesor deberá mantener saldo mínimo.  
Valor inicial:  
$5.000 COP  
Si el saldo es inferior:  
No recibe servicios.  
No acepta servicios.  
No aparece disponible.  
Estado  
APROBADA

DA-021 — IMF  
Decisión  
Se implementará un Índice de Maduración Financiera.  
Objetivo:  
Controlar liberaciones.  
Reducir fraude.  
Incentivar permanencia.  
Estado  
APROBADA

DA-022 — Participación Mínima  
Decisión  
La liberación de beneficios no dependerá únicamente del tiempo.  
También dependerá de:  
Actividad real.  
Participación.  
Red activa.  
Estado  
APROBADA

DA-023 — Motor Antifraude  
Decisión  
La plataforma utilizará análisis conductual.  
Detectará:  
Servicios simulados.  
Redes ficticias.  
Patrones sospechosos.  
Multicuentas.  
Estado  
APROBADA

DA-024 — Device Fingerprint  
Decisión  
Todos los dispositivos generarán una huella digital.  
Objetivo:  
Detección de fraude.  
Detección de multicuentas.  
Auditoría.  
Estado  
APROBADA

DA-025 — Principio de Escalabilidad  
Decisión  
Toda arquitectura deberá diseñarse pensando en:  
Santa Marta  
↓  
Magdalena  
↓  
Colombia  
↓  
Latinoamérica  
Sin rediseños estructurales.  
Estado  
APROBADA

DA-026 — Ecosistema Comercial Futuro  
Decisión  
La arquitectura deberá permitir integrar posteriormente:  
Comercios aliados.  
Talleres aliados.  
Supermercados aliados.  
Negocios propios.  
Estado  
APROBADA

DA-027 — Fuente de Verdad  
Decisión  
Cuando exista conflicto entre:  
Código.  
Conversaciones.  
Documentación antigua.  
Prevalecerá:  
Documentación aprobada  
Estado  
APROBADA  

DA-028 — Incentivo por Programación  
Decisión  
Los servicios programados entre 2 y 12 horas de anticipación recibirán una redistribución de beneficios.  
Distribución  
Servicio Normal:  
Empresa 30%  
Cliente 30%  
Servicio Programado:  
Empresa 25%  
Cliente 35%  
Justificación  
Reducir costos operativos.  
Mejorar planificación.  
Incrementar adopción del sistema.  
Estado  
APROBADA

DA-029  
Ningún parámetro de negocio configurable  
podrá modelarse mediante columnas fijas  
cuando exista la posibilidad razonable de crecimiento futuro.  
Se priorizará el modelo:  
Configuración → Registro  
sobre  
Configuración → Columna

### DA-030 — Tiempo Único de Negociación

Todas las ofertas y contraofertas  
compartirán el mismo tiempo máximo de vida.  
Valor inicial:  
180 segundos.

Configurado desde base de datos.

DA-031 — Evolución de Infraestructura Cartográfica  
Estado: Aprobada  
Fase V1  
Flutter  
\+  
flutter\_map  
\+  
OpenStreetMap  
\+  
Nominatim  
\+  
GraphHopper  
Objetivo:  
Coste operativo mínimo.  
Validación del modelo de negocio.  
Independencia de proveedores comerciales.  
---

Fase V2  
Evaluar:  
MapTiler  
cuando se alcancen métricas de crecimiento que justifiquen SLA, rendimiento y soporte empresarial.  
---

Fase V3  
Evaluar:  
TileServer Propio  
\+  
PostGIS  
\+  
Planetiler  
\+  
Infraestructura dedicada  
cuando el volumen operativo requiera independencia total de terceros.  
---

Principio Rector  
La plataforma deberá construirse desde V1  
de forma agnóstica al proveedor cartográfico.

Flutter nunca consumirá directamente  
Google Maps, MapTiler o TileServer.

Toda interacción cartográfica deberá  
realizarse mediante una capa de abstracción  
propia del backend.  
---

Justificación  
Permite migrar entre proveedores  
sin reescribir la aplicación.  
Reduce dependencia tecnológica.  
Facilita crecimiento progresivo  
según disponibilidad financiera.

## **DA-031 — Arquitectura Modular por Dominios**

**Estado:** Aprobada

### **Decisión**

El Backend de Tu Mobil Amigo se implementará como un **Modular Monolith**, organizado por dominios funcionales completamente desacoplados.

Cada dominio será responsable exclusivamente de su contexto de negocio y se comunicará mediante interfaces, contratos (DTO) y eventos internos.

### **Justificación**

Se busca obtener las ventajas de un monolito durante las primeras etapas del proyecto:

* menor complejidad operativa;  
* despliegue simplificado;  
* menor costo de infraestructura;  
* facilidad de depuración;  
* mayor velocidad de desarrollo.

Sin renunciar a la posibilidad de evolucionar posteriormente hacia microservicios.

### **Dominios definidos**

* Auth  
* Core  
* Operations  
* Pricing  
* Finance  
* Multilevel  
* Trust  
* IMF  
* Security  
* Notifications  
* Integrations  
* Admin  
* Audit

### **Regla**

Ningún dominio podrá acceder directamente a la implementación interna de otro dominio.

La comunicación deberá realizarse mediante contratos públicos.

**DA-032 — Compatibilidad ERP**

La arquitectura deberá permitir integración futura con sistemas ERP y contables sin requerir rediseño estructural de:

* Base de Datos.  
* Backend.  
* APIs.  
* Flutter.  
* Portal Administrativo.

La integración deberá realizarse mediante adaptadores desacoplados.

### **DA-033 — Separación Tecnológica Frontend**

Las aplicaciones operativas (Cliente y Asesor) serán desarrolladas en Flutter.
Los portales de gestión (Administrador y Superadministrador) serán desarrollados en React.
La lógica de negocio permanecerá centralizada en Backend y PostgreSQL.

### DA-034 — Arquitectura Híbrida Flutter + React

#### Contexto

Durante la evolución del proyecto se evaluaron múltiples alternativas para el desarrollo de interfaces.

#### Decisión

La plataforma adoptará una arquitectura híbrida:

##### Flutter

Aplicaciones:

* Cliente;
* Asesor.

##### React

Aplicaciones:

* Administrador;
* Superadministrador.

#### Justificación

Flutter ofrece una experiencia superior para usuarios móviles.

React ofrece mayor productividad para herramientas administrativas.

#### Consecuencias

Toda documentación futura deberá asumir esta separación tecnológica.

### DA-032 — Gestión Centralizada de Secretos

#### Estado

Aprobada

#### Decisión

Ninguna credencial, API Key, Secret, Token o cadena de conexión podrá almacenarse en código fuente.

Toda información sensible deberá gestionarse mediante mecanismos seguros de almacenamiento.

#### Consecuencias

Se prohíbe:

* hardcodear credenciales;
* exponer secretos en repositorios;
* almacenar tokens en frontend.

Toda implementación deberá cumplir el Documento 32A.

### DA-035 — Separación Formal de Ambientes

#### Decisión

La plataforma operará mediante ambientes independientes:

* Desarrollo;
* Staging;
* Producción.

#### Consecuencias

No se permitirá despliegue directo desde desarrollo a producción.
Toda liberación deberá seguir el flujo definido en los documentos 40A y 41A.

### DA-036 — Cierre Financiero y Liquidación Mensual

#### Decisión

La plataforma realizará cierres financieros mensuales automáticos.

El sistema generará:

* liquidaciones;
* conciliaciones;
* reportes Excel oficiales.

#### Consecuencias

Toda funcionalidad financiera deberá respetar los procesos definidos en el Documento 33A.

### DA-037 — Gestión Integral de Alertas e Incidentes

#### Decisión

Toda anomalía operacional, financiera, técnica o de seguridad deberá generar alertas clasificadas por severidad.

Se adopta oficialmente el modelo:

* SEV-1;
* SEV-2;
* SEV-3;
* SEV-4.

#### Consecuencias

Toda plataforma deberá integrarse con el catálogo definido en el Documento 42A.



Registro de Cambios  
Fecha	Decisión	Estado  
V1.0	Creación inicial	Activa  
Fin del Documento 06 — Decisiones Arquitectónicas
