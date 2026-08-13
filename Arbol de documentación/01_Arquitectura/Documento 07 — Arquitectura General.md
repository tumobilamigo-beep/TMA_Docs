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

Documento 09 — Modelo Financiero

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Definir el modelo económico oficial de Tu Mobil Amigo V1.0.

Este documento establece:

Cómo ingresa el dinero al ecosistema.  
Cómo se distribuyen los beneficios.  
Cómo se garantiza la liquidez.  
Cómo se financia la operación.  
Cómo se evita el fraude financiero.  
Cómo se construye sostenibilidad a largo plazo.

2\. Principios Financieros

Toda decisión financiera deberá respetar los siguientes principios:

PF-01 — Liquidez Real  
El sistema nunca podrá generar dinero sin respaldo económico real.

PF-02 — Separación de Fondos  
Los fondos operativos jamás podrán mezclarse con:

Cashback.  
Comisiones multinivel.  
Incentivos.

PF-03 — Trazabilidad Total  
Todo movimiento financiero deberá ser auditable.

PF-04 — Sostenibilidad  
La empresa deberá mantener rentabilidad positiva.

PF-05 — Antifraude Financiero  
Todo beneficio deberá originarse en actividad económica legítima.

3\. Fuentes de Ingreso del Ecosistema

Inicialmente existirán dos fuentes.

Fuente 1 — Recargas de Bolsa Operativa  
Realizadas por asesores.

Objetivo:  
Habilitar operación.

Fuente 2 — Comisión Operativa por Servicio  
Generada cuando un servicio finaliza correctamente.

4\. Bolsas Financieras Oficiales  
Cliente  
Billetera de Beneficios

Componentes:

Saldo Disponible

Cashback Ganado  
Cashback Liberado

Comisiones Ganadas  
Comisiones Liberadas

Histórico Total  
Asesor  
Bolsa Operativa

Utilizada exclusivamente para:

Operar.  
Cubrir comisiones.  
Mantener elegibilidad.  
Bolsa de Beneficios

Utilizada para:

Cashback.  
Comisiones.  
Incentivos.  
Beneficios liberados.  
5\. Separación Obligatoria de Fondos

Queda prohibido transferir recursos entre:

Bolsa Operativa  
↔  
Bolsa de Beneficios  
Objetivo

Garantizar:

Liquidez real.  
Sostenibilidad.  
Control antifraude.

6\. Comisión Operativa

Cuando un servicio finaliza:

Valor Servicio  
↓  
Comisión Operativa

La comisión será debitada automáticamente desde:

Bolsa Operativa del Asesor

7\. Distribución de Beneficios  
Servicio Normal

| Destino | Participación |
| :---- | :---- |
| Empresa | 30% |
| Cashback Cliente | 30% |
| Upliner Nivel 1 | 20% |
| Upliner Nivel 2 | 10% |
| Fondo Reserva | 10% |

---

Servicio Programado

| Destino | Participación |
| :---- | :---- |
| Empresa | 25% |
| Cashback Cliente | 35% |
| Upliner Nivel 1 | 20% |
| Upliner Nivel 2 | 10% |
| Fondo Reserva | 10% |

---

# Incentivo de Programación

Objetivo:

Incentivar la programación anticipada de servicios.

Condiciones:

Anticipación mínima:  
2 horas

Anticipación máxima:  
12 horas

Beneficio:

\+5%

sobre la participación de cashback.

Financiación:

Se descuenta de la participación empresarial.

### **Servicios QR Radicados**

Cuando un asesor registre correctamente un servicio mediante QR oficial del cliente y el servicio sea finalizado exitosamente, la distribución interna de la comisión operativa será:

| Destino | Participación |
| ----- | ----- |
| Empresa | 25% |
| Cashback Cliente | 30% |
| Upliner Nivel 1 | 20% |
| Upliner Nivel 2 | 10% |
| Fondo Reserva | 10% |
| Incentivo Asesor QR | 5% |

### **Objetivo**

Incentivar:

* Radicación de servicios externos.  
* Uso permanente de la plataforma.  
* Construcción de historial transaccional.  
* Trazabilidad operativa.

---

### **Restricción**

El incentivo únicamente se genera cuando:

* QR válido.  
* Cliente válido.  
* Asesor válido.  
* Servicio finalizado.  
* Sin alertas antifraude

9\. Cashback

El cashback busca incentivar:

Uso recurrente.  
Fidelización.  
Registro de servicios.  
Tipos  
Cashback Ganado

Generado por actividad válida.

No disponible.

Cashback Liberado

Disponible según reglas IMF.

10\. Comisiones Multinivel

La red multinivel operará inicialmente con:

2 niveles

Nivel 1  
Padre.

Nivel 2  
Abuelo.

11\. Principio de Actividad Real

Las comisiones únicamente podrán generarse cuando exista:

Servicio válido  
\+  
Cliente válido  
\+  
Asesor válido

12\. Índice de Maduración Financiera (IMF)  
Ningún beneficio se libera inmediatamente.

Todo beneficio deberá madurar.

Variables del IMF  
Antigüedad

40%

Trust Score  
30%

Actividad Real  
20%

Participación de Red  
10%

Total:

100%

13\. Participación de Red

Se incorpora oficialmente como componente financiero.

Objetivos:

Evitar redes pasivas.  
Incentivar crecimiento sano.  
Reducir fraude.

14\. Categorías Oficiales  
Todos los usuarios pertenecerán a las siguientes categorías, teniendo en cuenta la cantidad de servicios al mes;

Categoría		Cliente		Asesor Moto		Asesor Vehículo  
Explorador		0-9		0-149			0-59  
Viajero			10-19		150-199		60-79  
Experto		20-39		200-249		80-99  
Leyenda		40+		250+			100+

15\. Índice de Participación Activa (IPA)

Puntaje máximo:  
100 puntos

Distribución:

Categoría	IPA Máximo  
Explorador	25  
Viajero		50  
Experto	75  
Leyenda	100

16\. Índice de Participación de Red (IPR)

Puntaje máximo:

100 puntos

Distribución:

Categoría	IPR Máximo  
Explorador	25  
Viajero		50  
Experto	75  
Leyenda	100

17\. Liberación de Beneficios

La liberación dependerá del IMF.

No dependerá únicamente del tiempo.

Variables evaluadas  
Antigüedad.  
Actividad.  
Red.  
Trust Score.  
18\. Retiro de Beneficios

Solo podrán retirarse recursos ubicados en:

Cashback Liberado

Comisiones Liberadas

No podrán retirarse recursos ubicados en:

Cashback Ganado  
Comisiones Ganadas

19\. Servicios Externos

Los servicios registrados mediante QR:

Generan actividad.  
Generan historial.  
Generan reputación.

Los beneficios financieros dependerán de las reglas antifraude vigentes.

20\. Prevención de Lavado de Activos

El modelo financiero adopta:

Capa 1  
Trust Score.

Capa 2  
IMF.

Capa 3  
Motor Antifraude.

Capa 4  
Device Fingerprint.

Capa 5  
Auditoría financiera.

21\. Principio de No Discriminación Económica

Las siguientes variables jamás modificarán:

Tarifa sugerida.  
Piso.  
Techo.

Variables protegidas:

Trust Score.  
IPA.  
IPR.  
Categoría.  
IMF.  
22\. Recargas de Bolsa Operativa

Las recargas serán realizadas mediante:

Transferencia  
PSE  
Pasarela de pagos  
Métodos autorizados

La validación podrá ser:

Manual (V1)  
Automática (V2)

23\. Saldo Operativo Mínimo  
Todo asesor deberá mantener:  
$5.000 COP  
como saldo operativo mínimo.

Si el saldo es inferior:

No recibe servicios.  
No acepta servicios.  
No aparece disponible.

24\. Objetivo Financiero del Ecosistema

Construir un modelo capaz de:  
Generar rentabilidad para la empresa.  
Generar beneficios para clientes.  
Generar crecimiento para la red.  
Generar liquidez para asesores.  
Minimizar fraude financiero.  
Escalar nacionalmente.

25\. Evolución Financiera Futura

La arquitectura deberá permitir integrar:

Pagos internos.  
Aliados comerciales.  
Talleres.  
Supermercados.  
Beneficios corporativos.  
Créditos internos controlados.  
Sin rediseñar el núcleo financiero.  
Registro de Cambios

## **26\. Liquidación Mensual de Beneficios**

Todos los valores generados por:

* Cashback.  
* Comisiones Multinivel Nivel 1\.  
* Comisiones Multinivel Nivel 2\.  
* Incentivos Operativos.  
* Beneficios Promocionales.  
* Liberaciones provenientes del IMF.

No serán pagados inmediatamente.

Serán acumulados durante el período contable mensual bajo el estado:

PENDIENTE\_LIQUIDACION  
---

## **27\. Corte Oficial**

El cierre financiero mensual se realizará automáticamente el último día calendario de cada mes a las:

23:59:59

Hora oficial configurada para la plataforma.

El proceso consolidará todos los movimientos pendientes de liquidación.

---

## **28\. Generación Automática de Liquidaciones**

Al finalizar el corte mensual, el sistema deberá:

* Consolidar valores por usuario.  
* Consolidar valores por concepto.  
* Generar liquidaciones individuales.  
* Generar liquidación general corporativa.  
* Registrar trazabilidad completa.

---

## **29\. Ventana de Pago**

La empresa dispondrá de:

5 días calendario

contados a partir del primer día del mes siguiente para efectuar los pagos correspondientes.

---

## **30\. Inmutabilidad del Cierre**

Una vez ejecutado un cierre mensual:

CERRADO

los movimientos asociados a dicho período no podrán modificarse.

Las correcciones posteriores deberán registrarse mediante:

AJUSTES\_CONTABLES

en el período siguiente.

**31\. Integración Contable Futura**

Todos los procesos financieros deberán diseñarse de forma que puedan ser exportados a sistemas ERP externos.

Entre ellos:

* liquidaciones;  
* pagos;  
* cashback;  
* multinivel;  
* incentivos;  
* ajustes contables;  
* conciliaciones.

Los procedimientos de conciliación, cierre contable, liquidación manual y reapertura de período que operacionalizan este modelo financiero se encuentran desarrollados en detalle en el Documento 33A — Conciliación Financiera y Cierre Contable, el cual debe considerarse extensión obligatoria de este documento para efectos de implementación.

### **32\. Liquidaciones Ordinarias y Extraordinarias**

El sistema soportará:

Liquidación Ordinaria  
Liquidación Extraordinaria

La extraordinaria no reemplaza la ordinaria.

Versión	Cambio  
1.0	Creación inicial

Fin del Documento 09 — Modelo Financiero

Documento 10 — Motor Tarifario

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Definir el sistema oficial de cálculo de tarifas de Tu Mobil Amigo.

El Motor Tarifario será responsable de:

Calcular la tarifa sugerida.  
Generar el rango de negociación.  
Garantizar precios coherentes.  
Adaptarse a múltiples ciudades.  
Cumplir regulaciones locales.  
Permitir crecimiento nacional sin modificar código.

2\. Principios Rectores

MT-01 — Tarifa Justa  
El sistema deberá generar un valor razonable para:  
Cliente.  
Asesor.  
Plataforma.

MT-02 — Parametrización Total  
Ninguna variable tarifaria podrá existir en código fuente.  
Toda variable deberá almacenarse en base de datos.

MT-03 — Ciudad Configurable  
Cada ciudad operará mediante configuración independiente.  
La incorporación de una nueva ciudad no podrá requerir:  
Modificación de Flutter.  
Modificación de Backend.  
Despliegues especiales.

MT-04 — Transparencia  
La tarifa sugerida deberá ser explicable y auditable.

MT-05 — No Discriminación  
La tarifa nunca podrá variar por:  
Trust Score.  
Categoría.  
IPA.  
IPR.  
IMF.  
Antigüedad.  
Todos los usuarios recibirán exactamente la misma lógica de cálculo.

3\. Actualización Tarifaria

Método  
Manual.  
Responsable  
Administrador del sistema.  
Fuente Oficial

La actualización deberá realizarse únicamente cuando exista:

Decreto.  
Resolución.  
Acto administrativo.  
que modifique los parámetros oficiales de la ciudad correspondiente.

4\. Variables Base

Toda tarifa deberá construirse utilizando:  
Valor Base  
Valor mínimo operacional.  
Distancia  
Kilómetros estimados.  
Tiempo  
Tiempo estimado de recorrido.

5\. Variables Adicionales

Horario Nocturno  
Domingo o Festivo  
Configurado desde base de datos.

Lluvia  
Configurable manualmente.  
Niveles:  
Sin lluvia.  
Lluvia moderada.  
Lluvia fuerte.

Alta Demanda  
Activación automática o manual.

Límite máximo configurable.

6\. Variables Eliminadas

Queda prohibido utilizar:  
UVT.  
ACPM.  
Gasolina extra.  
Eventos masivos.  
Variables arbitrarias.

7\. Parámetros Obligatorios en Base de Datos  
La configuración deberá existir en tablas parametrizables.  
Como mínimo:  
Parámetro  
valor\_base  
valor\_km  
valor\_minuto  
recargo\_nocturno  
recargo\_festivo  
recargo\_lluvia  
recargo\_alta\_demanda  
margen\_negociacion  
escala\_redondeo

8\. Fórmula Oficial  
La tarifa sugerida será calculada mediante:  
Tarifa Base  
\+  
(KM × Valor\_KM)  
\+  
(Minutos × Valor\_Minuto)  
\+  
Recargos Aplicables

9\. Tarifa Sugerida

Resultado generado por el sistema.  
La tarifa sugerida constituye únicamente:  
Punto Inicial de Negociación  
No obliga al cliente.  
No obliga al asesor.

10\. Sistema de Negociación

Una vez calculada la tarifa:  
Tarifa Sugerida  
se generará automáticamente:  
Piso  
Techo  
utilizando el margen configurado.  
Valor inicial aprobado:  
±15%

11\. Score de Negociación  
El Score de Negociación podrá modificar:  
Piso.  
Techo.  
Dentro de límites definidos por el Documento 11\.

12\. Regla Oficial de Redondeo

Toda tarifa deberá redondearse:  
Hacia arriba  
Escala  
200 COP  
Ejemplos  
Valor Calculado	Valor Final  
5.001	5.200  
5.199	5.200  
5.201	5.400  
6.980	7.000

13\. Modalidades Tarifarias

Servicio Inmediato  
Tarifa calculada en tiempo real.

Servicio Programado  
Tarifa calculada para ejecución futura.  
Restricciones:  
Mínimo:  
2 horas  
Máximo:  
12 horas  
La programación no altera la fórmula tarifaria.

14\. Compatibilidad Multiservicio

El motor deberá soportar:

V1  
Mototaxi.  
Taxi.

Futuras Versiones  
Domicilios.  
Mensajería.  
Motocarro.  
Carga liviana.  
Nuevos servicios.  
Sin rediseño estructural.

15\. Compatibilidad Multiciudad  
El motor deberá soportar:  
Santa Marta.  
Barranquilla.  
Cartagena.  
Bogotá.  
Medellín.  
Cualquier ciudad futura.  
Mediante configuración.

16\. Auditoría Tarifaria  
Toda modificación deberá registrar:  
Usuario administrador.  
Fecha.  
Valor anterior.  
Valor nuevo.  
Justificación.

17\. Prohibiciones  
Queda prohibido:  
Tarifas ocultas.  
Tarifas manipuladas manualmente durante la negociación.  
Tarifas basadas en reputación.  
Tarifas discriminatorias.  
Tarifas calculadas con valores hardcodeados.

18\. Principio de Escalabilidad  
La incorporación de:  
Nuevas ciudades.  
Nuevos servicios.  
Nuevos recargos.  
deberá realizarse mediante parametrización.  
Nunca mediante cambios estructurales del código.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 10 — Motor Tarifario  


