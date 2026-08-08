# **Documento 04 — Arquitectura General**

**Versión:** 1.0  
**Estado:** Aprobado  
**Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir la arquitectura tecnológica oficial de Tu Mobil Amigo V1.0 estableciendo los principios estructurales, componentes, responsabilidades y restricciones que deberán respetar todos los desarrollos presentes y futuros.

Este documento constituye la fuente oficial de diseño arquitectónico del proyecto.

---

# **2\. Principios Arquitectónicos**

## **Modularidad Obligatoria**

Ningún componente podrá contener lógica perteneciente a otro dominio.

Cada módulo deberá ser independiente, mantenible y escalable.

---

## **Escalabilidad Horizontal**

La arquitectura deberá permitir crecimiento progresivo sin requerir rediseños estructurales.

El sistema deberá soportar:

* Nuevas ciudades.  
* Nuevos servicios.  
* Nuevos países.  
* Nuevos modelos comerciales.  
* Nuevos canales digitales.

---

## **Seguridad por Diseño**

Toda funcionalidad deberá asumir que existe un intento potencial de fraude.

La seguridad será una responsabilidad transversal de toda la plataforma.

---

## **Trazabilidad Total**

Toda acción relevante deberá generar:

* Registro.  
* Evidencia.  
* Auditoría.  
* Historial.

---

## **Bajo Acoplamiento**

Los módulos deberán comunicarse mediante contratos claramente definidos.

Los cambios internos de un módulo no deberán afectar otros módulos.

---

# **3\. Arquitectura Base**

La plataforma estará compuesta por:

Cliente APK Flutter  
          │  
          ▼  
 Supabase Backend  
          │  
 ┌────────┼────────┐  
 ▼        ▼        ▼

Base   Edge      Realtime  
Datos  Functions  
          │  
          ▼  
   Servicios Externos

---

# **4\. Componentes Principales**

## **Frontend Mobile**

Tecnología oficial:

Flutter

Responsabilidades:

* Interfaz de usuario.  
* Geolocalización.  
* Gestión de sesión.  
* Solicitud de servicios.  
* Negociación.  
* Wallets.  
* Perfil.  
* Trust Score.  
* QR.

---

## **Backend**

Tecnología oficial:

Supabase

Responsabilidades:

* Persistencia.  
* Seguridad.  
* Realtime.  
* Autenticación.  
* Auditoría.  
* Cálculos.  
* Antifraude.

---

## **PostgreSQL**

Base de datos oficial.

Responsable de:

* Información operacional.  
* Información financiera.  
* Información de seguridad.  
* Información histórica.

---

## **Edge Functions**

Responsables de:

* Reglas críticas.  
* Validaciones.  
* Integraciones.  
* Cálculos protegidos.

---

## **Realtime**

Responsable de:

* Nuevos servicios.  
* Ofertas.  
* Contraofertas.  
* Estados.  
* Notificaciones operativas.

---

# **5\. Dominios de Negocio**

La aplicación estará dividida en dominios independientes.

---

## **Dominio Usuarios**

Responsable de:

* Clientes.  
* Asesores.  
* Administradores.  
* Perfil.  
* Identidad.

---

## **Dominio Servicios**

Responsable de:

* Solicitudes.  
* Asignación.  
* Estados.  
* Historial.

---

## **Dominio Negociación**

Responsable de:

* Oferta inicial.  
* Contraoferta.  
* Aceptación.  
* Rechazo.

---

## **Dominio Tarifario**

Responsable de:

* Tarifas base.  
* Parámetros económicos.  
* Valores sugeridos.  
* Pisos.  
* Techos.

---

## **Dominio Financiero**

Responsable de:

* Bolsas.  
* Cashback.  
* Comisiones.  
* Liberaciones.  
* IMF.

---

## **Dominio Multinivel**

Responsable de:

* Referidos.  
* Upline.  
* Comisiones.  
* IPR.

---

## **Dominio Trust Score**

Responsable de:

* Reputación.  
* Riesgo.  
* Comportamiento.

---

## **Dominio Antifraude**

Responsable de:

* Detección.  
* Alertas.  
* Bloqueos.  
* Investigación.

---

## **Dominio QR**

Responsable de:

* Registro de servicios externos.  
* Validación de identidad.  
* Prevención de autobeneficio.

---

# **6\. Canales Oficiales**

## **APK Android**

Canal principal.

Toda funcionalidad nueva deberá diseñarse primero para APK.

---

## **Telegram**

Canal complementario.

Responsabilidades:

* Registro inicial.  
* Recuperación de acceso.  
* Gestión de dispositivos.  
* Notificaciones críticas.

Telegram no será el canal operativo principal.

---

# **7\. Reglas de Integridad Arquitectónica**

Queda prohibido:

* Lógica de negocio en interfaces.  
* Consultas SQL incrustadas en pantallas.  
* Reglas financieras en Flutter.  
* Validaciones críticas en cliente.  
* Cálculos sensibles fuera del backend.

---

# **8\. Servicios Externos**

Los servicios externos registrados mediante QR serán tratados como ciudadanos de primera clase dentro del ecosistema.

Deben:

* Generar historial.  
* Generar Trust Score.  
* Generar actividad.  
* Generar participación de red.  
* Generar trazabilidad.

No utilizarán:

* Motor Tarifario.  
* Motor de Negociación.

---

# **9\. Evolución Futura**

La arquitectura deberá permitir incorporar sin rediseño:

* Mensajería.  
* Domicilios.  
* Motocarro.  
* Servicios empresariales.  
* Comercios aliados.  
* Supermercados propios.  
* Talleres propios.  
* Ecosistema comercial ampliado.

---

# **10\. Principio Rector**

Toda decisión técnica futura deberá responder a la siguiente pregunta:

"¿Esta decisión mantiene la seguridad, la trazabilidad, la escalabilidad y la sostenibilidad de Tu Mobil Amigo V1.0?"

Si la respuesta es negativa, la decisión deberá ser rechazada.

