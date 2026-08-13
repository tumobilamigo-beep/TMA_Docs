**Arquitectura

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

# **3\. Arquitectura Base
La plataforma estará compuesta por dos capas de frontend y un backend único:

Flutter Cliente     Flutter Asesor     React Administrador     React Superadministrador
        │                  │                    │                        │
        └──────────────────┴────────────────────┴────────────────────────┘
                                       │
                                       ▼
                              Supabase Backend
                                       │
                    ┌──────────────────┼──────────────────┐
                    ▼                  ▼                  ▼
                  Base              Edge              Realtime
                  Datos             Functions
                                       │
                                       ▼
                             Servicios Externos

Los roles operativos (Cliente, Asesor) consumen la plataforma mediante Flutter.
Los roles de gobierno (Administrador, Superadministrador) consumen la plataforma mediante portales web independientes en React (ver Documento 06 — DA-033, Documento 28).
Toda lógica de negocio, financiera y de seguridad permanece centralizada en el Backend, independientemente del frontend de origen.

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

## **Frontend Administrativo

Tecnología oficial:
React, Next.js, TypeScript.
Responsabilidades:
Administración de usuarios, asesores y servicios.
Gestión financiera (recargas, retiros, liquidaciones).
Configuración de parámetros del sistema (tarifas, programación, ofertas).
Monitoreo, auditoría y supervisión del Motor Antifraude.
Este componente no contiene lógica de negocio, financiera ni de seguridad crítica — toda decisión se ejecuta y valida en el Backend (ver Documento 28, Sección 3).

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
Clientes.
Asesores.
Administradores.
Superadministradores.
Perfil.
Identidad.
Roles y permisos (RBAC).

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

Canal principal para roles operativos (Cliente, Asesor).
Toda funcionalidad nueva orientada a Cliente/Asesor deberá diseñarse primero para APK.

## **Telegram
Canal complementario para roles operativos.

Responsabilidades:
Registro inicial.
Recuperación de acceso.
Gestión de dispositivos.
Notificaciones críticas.
Telegram no será el canal operativo principal.

Portal Web (React)
Canal exclusivo para roles de gobierno (Administrador, Superadministrador).
No será utilizado por Cliente ni Asesor.
Responsabilidades: administración, configuración, auditoría, monitoreo y supervisión (ver Documento 28).

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

Documento 08 — Modelo Operativo

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Definir el funcionamiento operativo oficial de Tu Mobil Amigo V1.0.estableciendo la forma en que interactúan clientes, asesores, administradores y los diferentes motores de negocio de la plataforma.

Este documento describe:

Cómo se generan los servicios.  
Cómo participan clientes y asesores.  
Cómo se registran operaciones.  
Cómo se generan beneficios.  
Cómo se protege el ecosistema.

2\. Actores del Sistema

Cliente  
Usuario que solicita servicios.

Puede:

Solicitar servicios digitales.  
Participar en negociaciones.  
Acumular beneficios.  
Construir red multinivel.  
Registrar actividad verificable.

Asesor  
Prestador de servicios.

Puede operar como:

Mototaxista.  
Taxista.  
Mensajero.  
Domiciliario.  
Operador de motocarro.  

Administrador
Responsable de la operación diaria:
Configuración operativa.

Seguridad de primer nivel.
Finanzas operativas (recargas, retiros, liquidaciones ordinarias).

Superadministrador
Responsable del gobierno integral:
Configuración global y motores del sistema.
Seguridad avanzada, auditoría e integraciones.
Finanzas extraordinarias: liquidaciones extraordinarias y reapertura de períodos.
Supervisión y gestión de administradores.

3\. Modalidades de Servicio

1. Servicio Inmediato

2. Servicio Programado

La plataforma operará bajo dos modalidades.

Modalidad A — Servicio Digital

Servicio originado desde la aplicación.

Flujo:

Cliente  
↓  
Solicitud  
↓  
Motor Tarifario  
↓  
Oferta Inicial  
↓  
Negociación  
↓  
Asignación  
↓  
Ejecución  
↓  
Finalización

Modalidad A — Servicio Externo

Servicio originado fuera de la plataforma.

Ejemplo:

Cliente encuentra asesor en la calle.

Posteriormente:

Cliente presenta QR  
↓  
Asesor escanea QR  
↓  
Servicio registrado  
↓  
Auditoría  
↓  
Beneficios

Modalidad B \- Servicios Programados

Características:

* Programación mínima de 2 horas.  
* Programación máxima de 12 horas.  
* Genera incentivo adicional para el cliente.  
* Reduce consumo operativo del ecosistema.  
* Mejora capacidad de planificación.

Beneficio:

El cashback del cliente aumenta del 30% al 35% de la comisión distribuible.

La diferencia será asumida por la participación empresarial.

4\. Principio de Registro Universal

Todo servicio legítimo deberá poder registrarse.

No importa si fue generado:

Dentro de la aplicación.  
Fuera de la aplicación.

La plataforma debe capturar actividad económica real.

5\. Ciclo de Vida de un Servicio Digital  
Paso 1

Cliente solicita servicio.

Paso 2

Motor Tarifario calcula:

Tarifa sugerida.  
Piso permitido.  
Techo permitido.  
Paso 3

Cliente envía oferta inicial.

Paso 4

Asesores disponibles reciben la solicitud.

Paso 5

Cada asesor puede:

Aceptar.  
Rechazar.  
Realizar una única contraoferta.  
Paso 6

Cliente toma decisión final.

Puede:

Aceptar.  
Rechazar.  
Paso 7

Servicio adjudicado.

Paso 8

Servicio ejecutado.

Paso 9

Servicio finalizado.

Paso 10

Sistema genera:

Historial.  
Auditoría.  
Métricas.  
Beneficios.

6\. Exclusividad Transaccional

Un asesor podrá mantener múltiples negociaciones simultáneas.

Sin embargo:

Cuando un cliente acepta:

Servicio adjudicado

Automáticamente:

Todas las demás negociaciones  
quedan cerradas.

7\. Registro de Servicios Externos

Los servicios externos forman parte oficial del modelo operativo.

Objetivo:

Capturar actividad económica real.

Flujo  
Cliente  
↓  
Presenta QR  
↓  
Asesor escanea  
↓  
Registra servicio  
↓  
Ingresa valor cobrado  
↓  
Servicio auditado

7.1 

Regla de Contraoferta

Cada asesor podrá realizar:

1 única contraoferta  
por servicio.

Sin embargo podrá mantener múltiples contraofertas activas en servicios distintos simultáneamente.

8\. Restricción de Autobeneficio

Queda prohibido:

cliente\_uuid \= asesor\_uuid

La operación será rechazada automáticamente.

9\. Operación del Asesor

Todo asesor deberá mantener:

Bolsa Operativa Activa  
Saldo Mínimo

Valor inicial:

$5.000 COP  
Si el saldo es insuficiente

No podrá:

Aparecer disponible.  
Recibir servicios.  
Aceptar servicios.  
10\. Billeteras del Ecosistema  
Cliente

Billetera de Beneficios.

Contendrá:

Cashback Ganado.  
Cashback Liberado.  
Comisiones Ganadas.  
Comisiones Liberadas.  
Asesor  
Bolsa Operativa

Utilizada para operar.

Bolsa de Beneficios

Utilizada para incentivos.

11\. Principio de Liquidez Operativa

La Bolsa Operativa del asesor nunca podrá alimentarse mediante:

Cashback.  
Comisiones.  
Beneficios.

Objetivo:

Garantizar liquidez real dentro del sistema.

12\. Participación en la Red

Todo usuario podrá:

Invitar usuarios.  
Construir red.  
Generar actividad legítima.

La red se utilizará para:

Comisiones.  
Crecimiento.  
Fidelización.

13\. Categorías de Participación

Todos los usuarios pertenecerán a una categoría.

Explorador  
↓  
Viajero  
↓  
Experto  
↓  
Leyenda

Las categorías serán determinadas por:

IPA.  
IPR.  
Actividad.  
Permanencia.

14\. Principio de Igualdad Tarifaria

El sistema jamás modificará:

Tarifas.  
Costos.  
Valores sugeridos.

Basándose en:

Trust Score.  
IPA.  
IPR.  
Categoría.

Todos los usuarios recibirán la misma referencia tarifaria.

15\. Trust Score

Mide:

Riesgo.  
Confiabilidad.  
Comportamiento.

No modifica precios.

16\. Índice de Participación Activa (IPA)

Mide:

Uso real.  
Frecuencia.  
Participación verificable.

La plataforma clasificará a los usuarios mediante categorías de actividad.

| Categoría  | Cliente (Servicios/Mes) | Asesor (Servicios/Mes) | IPA Máximo |  
| \---------- | \----------------------- | \---------------------- | \---------- |  
| Explorador | 0 \- 9                   | 0 \- 149                | 25         |  
| Viajero    | 10 \- 19                 | 150 \- 199              | 50         |  
| Experto    | 20 \- 39                 | 200 \- 249              | 75         |  
| Leyenda    | 40+                     | 250+                   | 100        |

17\. Índice de Participación de Red (IPR)

Mide:

Crecimiento de red.  
Calidad de red.  
Actividad de referidos.

La plataforma clasificará la actividad multinivel.

| Categoría  | Referidos Activos | IPR Máximo |  
| \---------- | \----------------- | \---------- |  
| Explorador | 0                 | 0          |  
| Viajero    | 1 \- 3             | 25         |  
| Experto    | 4 \- 10            | 75         |  
| Leyenda    | 11+               | 100        |

18\. Índice de Maduración Financiera (IMF)

Controla:

Liberación de cashback.  
Liberación de comisiones.  
Velocidad de maduración.

El IMF controlará la liberación progresiva de beneficios.

Composición:

| Variable       | Peso |  
| \-------------- | \---- |  
| Antigüedad     | 20%  |  
| Trust Score    | 25%  |  
| Actividad Real | 25%  |  
| IPA            | 15%  |  
| IPR            | 15%  |

19\. Motor Antifraude

Analiza:

Servicios.  
Negociaciones.  
Redes.  
Dispositivos.  
Billeteras.

Objetivo:

Detectar abuso antes de generar pérdidas.

20\. Principio de Actividad Real

Ningún beneficio podrá generarse sin actividad verificable.

Todo beneficio deberá estar respaldado por:

Servicio válido  
\+  
Usuario válido  
\+  
Actividad válida  
21\. Evolución del Ecosistema

El modelo operativo deberá soportar futuras integraciones:

Comercio aliado.  
Talleres aliados.  
Supermercados aliados.  
Servicios financieros.

Sin modificar la arquitectura central.

22\. Objetivo Final

Construir un ecosistema donde:  
Clientes obtienen seguridad.  
Asesores obtienen más servicios.  
La empresa obtiene sostenibilidad.  
La red obtiene crecimiento.  
El sistema obtiene trazabilidad.  
Manteniendo:  
Seguridad  
\+  
Escalabilidad  
\+  
Liquidez Real  
\+  
Control Antifraude  
\+  
Sostenibilidad Financiera

Las negociaciones expiran automáticamente  
según el parámetro oficial de negociación.

Fin del Documento 08 — Modelo Operativo  

