**Arquitectura

# **Documento 07 — Arquitectura General**

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

Fin de Documento 07 — Arquitectura General


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


Documento 11 — Sistema de Negociación

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Definir el mecanismo oficial de negociación entre clientes y asesores dentro de Tu Mobil Amigo.

El sistema busca:

Mantener precios justos.  
Evitar abusos.  
Permitir flexibilidad comercial.  
Proteger al cliente.  
Proteger al asesor.  
Reducir conflictos operativos.  
Mantener liquidez del ecosistema.

2\. Principios del Sistema  
SN-01 — Negociación Controlada  
La negociación será libre únicamente dentro de los límites definidos por el sistema.

SN-02 — Cliente Decide  
La decisión final siempre corresponderá al cliente.

SN-03 — Igualdad Tarifaria  
La negociación jamás modificará:  
Tarifa sugerida.  
Piso.  
Techo.  
según:  
Trust Score.  
Categoría.  
IPA.  
IPR.  
IMF.

SN-04 — Transparencia  
Todas las ofertas deberán quedar registradas.

SN-05 — Trazabilidad  
Toda negociación deberá ser auditable.

3\. Tarifa Inicial  
El proceso inicia con:  
Tarifa Sugerida  
calculada por el Motor Tarifario.

4\. Rango de Negociación  
El sistema generará automáticamente:  
Piso  
Tarifa Sugerida  
Techo  
Valor inicial aprobado:  
±15%  
respecto a la tarifa sugerida.

5\. Flujo General

Paso 1  
Cliente solicita servicio.

Paso 2  
Sistema calcula:  
Tarifa Sugerida

Paso 3  
Cliente propone valor.

Paso 4  
La solicitud es enviada a los asesores elegibles.

Paso 5  
Cada asesor podrá:  
Aceptar.  
Rechazar.  
Contraofertar.

Paso 6  
Cliente decide.

Paso 7  
Servicio asignado.

6\. Oferta Inicial del Cliente  
El cliente deberá ingresar un valor dentro del rango permitido.  
Ejemplo:  
Tarifa Sugerida \= 10.000  
Piso \= 8.500  
Techo \= 11.500  
Valores válidos:  
8.500  
9.000  
10.000  
11.500  
Valores inválidos:  
7.000  
12.000  
15.000

7\. Derechos del Asesor  
Cada asesor podrá:  
Aceptar  
Acepta el valor ofrecido.  
Rechazar  
Descarta la solicitud.  
Contraofertar

8\. Regla de Contraoferta Única  
Cada asesor podrá realizar:  
Una única contraoferta  
por cada cliente  
No podrá generar una segunda contraoferta sobre la misma negociación.

9\. Contraofertas Simultáneas  
Un asesor podrá mantener:  
Múltiples contraofertas activas  
con distintos clientes simultáneamente.  
Ejemplo:  
Cliente A  
Contraoferta activa  
Cliente B  
Contraoferta activa  
Cliente C  
Contraoferta activa  
Esto es válido.

10\. Cierre Automático de Negociaciones  
Cuando un cliente acepta una oferta:  
Servicio Asignado  
el sistema deberá:  
Cerrar todas las demás negociaciones activas del asesor.  
Liberar solicitudes pendientes.  
Bloquear nuevas aceptaciones.

11\. Notificaciones Automáticas  
Los demás clientes recibirán:  
El asesor ya no se encuentra disponible.  
El asesor recibirá:  
Servicio asignado exitosamente.

12\. Expiración de Ofertas  
Toda oferta tendrá tiempo máximo de vida.  
Valor inicial:  
180 segundos  
Parámetro configurable desde base de datos

13\. Expiración de Contraofertas  
Toda contraoferta tendrá el tiempo máximo de vida de la Expiración de Ofertas

14\. Estados de Negociación  
Estados oficiales:

CREADA  
OFERTADA  
ACEPTADA  
RECHAZADA  
CONTRAOFERTADA  
EXPIRADA  
CANCELADA  
ASIGNADA

15\. Score de Negociación  
Se crea oficialmente el:  
Score de Negociación  
Objetivo:  
Medir calidad de negociación.  
No afecta:  
Tarifas.  
Prioridades.  
Asignaciones.

Sí afecta:  
Rango de negociación futuro.

16\. Variables del Score  
El sistema podrá analizar:  
Servicios completados.  
Cancelaciones.  
Rechazos.  
Cumplimiento.  
Historial operativo.

17\. Niveles del Score  
Bajo  
Rango reducido.  
Medio  
Rango estándar.  
Alto  
Rango ampliado.

18\. Límites del Score  
Incluso con score alto:  
Nunca podrá superar  
los límites definidos por administración.  
Todo deberá ser parametrizable.

19\. Protección Contra Manipulación  
Queda prohibido:  
Negociaciones ficticias.  
Auto negociación.  
Simulación de demanda.  
Creación masiva de ofertas.

20\. Restricción de Autoasignación  
Un asesor no podrá gestionar:  
Servicios creados por sí mismo.  
Servicios asociados a su UUID.  
Servicios asociados a cuentas vinculadas por reglas antifraude.

21\. Servicios Externos  
Los servicios registrados mediante QR:  
No utilizan negociación digital.  
Porque la negociación ocurre físicamente entre:  
Cliente.  
Asesor.  
El sistema únicamente registra:  
Valor final.  
Participantes.  
Evidencia.  
Historial.

22\. Integración con Trust Score  
El Trust Score podrá consumir:  
Cancelaciones.  
Abandono de ofertas.  
Incumplimientos.  
No modificará precios.

23\. Integración con Motor Antifraude  
El Motor Antifraude analizará:  
Contraofertas repetitivas.  
Patrones anormales.  
Redes coordinadas.  
Colusión.

24\. Parametrización Total  
Todos los límites deberán almacenarse en base de datos.  
Nunca en código.  
Ejemplos:  
margen\_negociacion  
tiempo\_expiracion  
max\_contraofertas  
score\_minimo  
score\_maximo

25\. Principio de Escalabilidad  
El sistema deberá soportar:  
Miles de negociaciones simultáneas.  
Múltiples ciudades.  
Nuevos tipos de servicios.  
Sin rediseñar el motor de negociación.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 11 — Sistema de Negociación

Documento 12 — Sistema Multinivel

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

Definir la estructura de crecimiento de red de Tu Mobil Amigo.

El sistema multinivel tiene como propósito:

Incentivar la expansión orgánica.  
Reducir costos de adquisición de usuarios.  
Premiar la actividad real.  
Generar crecimiento sostenible.  
Evitar estructuras especulativas.  
Integrarse con Trust Score e IMF.

2\. Principios Fundamentales

SM-00 Principio de Legalidad Multinivel.  
Prohibición de Comisiones por Registro.  
Producto Principal.  
Prohibición de Estructuras Piramidales.

SM-01 — La actividad vale más que el registro  
Registrar usuarios no genera beneficios.  
Los beneficios se generan únicamente cuando existen servicios reales.

SM-02 — La red debe producir valor  
Toda comisión multinivel deberá originarse en:  
Servicios completados.  
Nunca por:  
Inscripciones.  
Membresías.  
Compras de paquetes.  
Venta de posiciones.

SM-03 — Modelo Antipirámide  
El sistema está diseñado para recompensar actividad económica real.  
No recompensa reclutamiento pasivo.

SM-04 — Crecimiento Sostenible  
La red deberá poder crecer durante años sin comprometer:  
Liquidez.  
Operación.  
Seguridad financiera.

3\. Estructura de Red  
La red estará limitada a:  
Nivel 1  
Nivel 2

Nivel 1  
Padre directo.

Nivel 2  
Abuelo directo.

Ejemplo:

Carlos  
↓  
Juan  
↓  
María

Si María genera un servicio:  
Juan \= Nivel 1  
Carlos \= Nivel 2

4\. Profundidad Máxima  
Profundidad oficial:  
2 niveles

No existirán:

Nivel 3\.  
Nivel 4\.  
Nivel infinito.

5\. Generación de Comisiones  
Las comisiones se generan únicamente cuando:  
Servicio \= Finalizado  
y:  
Comisión operativa \= Cobrada

6\. Distribución Oficial  
Distribución interna de la comisión operativa:

Destino		Participación  
Empresa				30%  
Cashback 	Cliente		30%  
Upliner 	Nivel 1		20%  
Upliner 	Nivel 2		10%  
Fondo Reserva			10%

7\. Requisitos para Generar Comisión  
El usuario deberá:  
Estar activo.  
Tener cuenta válida.  
No estar suspendido.  
No presentar alertas críticas de fraude.

8\. Participación Mínima de Red (IPR)  
Se crea oficialmente el:  
Índice de Participación de Red (IPR)  
Objetivo:  
Medir la calidad y actividad de la red.  
No mide:  
Cantidad total de registros.  
Sí mide:  
Actividad real.  
Uso real.  
Permanencia.

9\. Categorías Oficiales  
Todos los usuarios pertenecerán a una categoría.  
Explorador  
Nivel inicial.  
Viajero  
Participación frecuente.  
Experto  
Participación avanzada.  
Leyenda  
Participación sobresaliente.

10\. Tabla Oficial de Categorías  
Categoría	Clientes (Servicios/Mes)	Asesores (Servicios/Mes)	IPA Máximo	IPR Máximo  
Explorador	0 \- 9				0 \- 149				25		25  
Viajero		10 \- 19				150 \- 199			50		50  
Experto		20 \- 39				200 \- 249			75		75  
Leyenda		40+				250+				100		100

11\. Referidos Activos  
Un referido se considera activo cuando:  
Tiene cuenta habilitada.  
Genera actividad real.  
Cumple reglas antifraude.

12\. Referidos Inactivos  
Se consideran inactivos:  
Suspendidos.  
Abandonados.  
Fraudulentos.  
Sin actividad mínima.

13\. Calidad de Red  
El IPR prioriza:  
Calidad  
sobre  
Cantidad  
Ejemplo:  
10 referidos activos  
valen más que:  
100 referidos inactivos

14\. Integración con Trust Score  
La red influirá positivamente cuando:  
Exista actividad real.  
Exista permanencia.  
Exista comportamiento correcto.  
La red influirá negativamente cuando:  
Existan fraudes.  
Existan cuentas falsas.  
Existan patrones coordinados.

15\. Integración con IMF  
Las comisiones multinivel:  
NO se liberan inmediatamente.  
Se acumulan como:  
Comisiones Ganadas  
Y posteriormente pasan a:  
Comisiones Liberadas  
según las reglas del IMF.

16\. Restricciones Operativas  
Queda prohibido:  
Comprar posiciones.  
Transferir posiciones.  
Vender posiciones.  
Heredar posiciones automáticamente.

17\. Auto Patrocinio  
Está prohibido.  
Ejemplos:  
Misma persona  
\+  
Múltiples cuentas  
Mismo dispositivo  
\+  
Múltiples registros  
Misma identidad  
\+  
Múltiples redes

18\. Eventos de Riesgo  
El sistema deberá monitorear:  
Crecimiento anormal.  
Redes cerradas.  
Actividad coordinada.  
Patrones de simulación.

19\. Congelamiento Preventivo  
Las comisiones podrán congelarse cuando:  
Exista investigación activa.  
Exista sospecha de fraude.  
Exista incumplimiento normativo.

20\. Fondo de Reserva  
El Fondo de Reserva tendrá como finalidad:  
Contingencias operativas.  
Riesgos financieros.  
Protección del ecosistema.  
No podrá utilizarse para:  
Pago de comisiones.  
Pago de cashback.  
Pago operativo normal.

21\. Escalabilidad  
La estructura multinivel deberá soportar:  
Miles de usuarios.  
Miles de asesores.  
Múltiples ciudades.  
Nuevos servicios.  
Sin modificar la lógica central.

22\. Principio Rector Final  
La red multinivel de Tu Mobil Amigo existe para fortalecer el ecosistema de movilidad y comercio.  
Nunca será el producto principal.  
El producto principal siempre será:  
La prestación real de servicios.  
Registro de Cambios

23\. Prohibición de Comisiones por Registro

Ningún usuario podrá recibir:  
Bonos.  
Cashback.  
Comisiones.  
Incentivos.  
por:  
Registrar personas.  
Activar cuentas.  
Completar formularios.  
Verificar identidad.  
Vincular usuarios.

Las compensaciones solo podrán originarse en actividad económica real derivada de servicios efectivamente prestados.

## **24\. Política de Liquidación**

Las comisiones multinivel generadas por la actividad de la red no serán abonadas en tiempo real.

Todas las comisiones permanecerán acumuladas hasta el cierre mensual oficial.

---

## **25\. Estado de Comisiones**

Estados permitidos:

GENERADA
PENDIENTE\_LIQUIDACION
LIQUIDADA
PENDIENTE\_PAGO
PAGADA
ANULADA

## **26\. Supervisión Administrativa
El Administrador podrá:
Consultar árbol de referidos.
Consultar comisiones acumuladas e históricos.
El Superadministrador podrá adicionalmente:
Ajustar manualmente comisiones ante disputas o eventos de fraude confirmado, dejando registro de auditoría obligatorio.
Suspender la participación de un nodo de la red ante sospecha de estructura ficticia (ver Documento 15 — Motor Antifraude).
Toda intervención administrativa sobre la red multinivel deberá registrarse conforme al Documento 35 — Auditoría y Trazabilidad, y nunca podrá alterar retroactivamente comisiones ya liberadas y auditadas.

Versión	Cambio  
1.0	Creación inicial
Fin del Documento 12 — Sistema Multinivel  

Documento 13 — Trust Score

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

## **1\. Objetivo

El Trust Score (TS) es el sistema central de confianza de Tu Mobil Amigo.  
Su propósito es medir el nivel de confiabilidad de cada usuario mediante el análisis continuo de comportamiento, actividad, cumplimiento y reputación dentro del ecosistema.  
El Trust Score no modifica tarifas, no discrimina servicios y no altera el acceso económico a la plataforma.

Su función principal es:  
Reducir fraude.  
Aumentar seguridad.  
Mejorar calidad operativa.  
Alimentar el IMF.  
Alimentar el Motor Antifraude.  
Alimentar procesos de auditoría.

## **2\. Principios Fundamentales

TS-01 — Igualdad Comercial  
El Trust Score nunca podrá:  
Alterar el valor de un servicio.  
Modificar la tarifa sugerida.  
Incrementar precios.  
Reducir precios.  
Favorecer económicamente a usuarios.  
Todos los usuarios tendrán acceso al mismo Motor Tarifario.

TS-02 — Confianza Ganada  
La confianza se construye mediante comportamiento real.  
Nunca podrá ser comprada.  
Nunca podrá ser transferida.  
Nunca podrá heredarse.

TS-03 — Evolución Continua  
El Trust Score será dinámico.  
Podrá subir o bajar de acuerdo con el comportamiento observado.

TS-04 — Transparencia Parcial  
El usuario conocerá:  
Su categoría.  
Su nivel de avance.  
Recomendaciones de mejora.  
No conocerá:  
Fórmulas exactas.  
Pesos internos.  
Algoritmos antifraude.

## **3\. Escala Oficial  
El Trust Score utilizará una escala:  
0 \- 100 puntos

## **4\. Categorías de Confianza

Categoría	Puntaje  
Explorador	0 \- 25  
Viajero		26 \- 50  
Experto		51 \- 75  
Leyenda		76 \- 100

## **5\. Factores de Evaluación  
El Trust Score se alimentará de cinco grandes pilares.

Actividad Real  
Evalúa:  
Servicios completados.  
Frecuencia de uso.  
Consistencia de participación.  
Peso inicial sugerido:  
30%

Reputación Operativa  
Evalúa:  
Calificaciones.  
Quejas válidas.  
Cumplimiento.  
Peso inicial:  
25%

Seguridad de Cuenta  
Evalúa:  
Verificación de identidad.  
Dispositivo confiable.  "(tabla device_registry, ver Documento 19 y Documento 34)"
Historial de accesos.  
Peso inicial:  
15%

Calidad de Red  
Evalúa:  
Actividad de referidos.  
Permanencia.  
Participación.  
Peso inicial:  
15%

Comportamiento Financiero  
Evalúa:  
Historial de billeteras.  
Consistencia operativa.  
Eventos sospechosos.  
Peso inicial:  
15%

## **6\. Trust Score para Clientes  
Variables consideradas:  
Solicitudes creadas.  
Servicios completados.  
Uso de servicios programados.  
Registro de servicios QR.  
Participación de red.  
Antigüedad.

## **7\. Trust Score para Asesores  
Variables consideradas:  
Servicios completados.  
Cumplimiento operativo.  
Cancelaciones.  
Actividad QR.  
Participación de red.  
Antigüedad.

## **8\. Factores Positivos  
Incrementan Trust Score:  
Servicios finalizados.  
Antigüedad.  
Participación constante.  
Verificación completa.  
Buenas calificaciones.  
Actividad real de red.  
Uso frecuente de la plataforma.

## **9\. Factores Negativos  
Reducen Trust Score:  
Cancelaciones recurrentes.  
Reportes confirmados.  
Inactividad prolongada.  
Comportamientos anómalos.  
Intentos de fraude.  
Manipulación de servicios.

## **10\. Eventos Críticos  
Los siguientes eventos pueden generar reducción inmediata:  
Suplantación.  
Múltiples cuentas.  
Fraude financiero.  
Documentación falsa.  
Manipulación del sistema.

## **11\. Recuperación de Confianza  
Todo usuario podrá recuperar puntaje mediante:  
Actividad real.  
Cumplimiento.  
Permanencia.  
Buen comportamiento.  
No existirán penalizaciones permanentes automáticas.

## **12\. Relación con IPA  
El Trust Score utilizará información proveniente del:

IPA  
Índice de Participación y Actividad  
IPA mide:  
Cantidad.  
Frecuencia.  
Participación.  
Trust Score mide:  
Calidad.  
Confiabilidad.  
Riesgo.

## **13\. Relación con IPR  
El sistema utilizará información proveniente del:  
IPR  
Índice de Participación de Red  
El crecimiento saludable de la red contribuirá positivamente.  
Las redes sospechosas contribuirán negativamente.

## **14\. Relación con IMF  
El Trust Score será uno de los factores principales para la liberación progresiva de:  
Cashback.  
Comisiones multinivel.  
Incentivos QR.

## **15\. Relación con el Motor Antifraude  
El Trust Score compartirá información con el Motor Antifraude.  
No obstante:  
Trust Score ≠ Antifraude  
El Trust Score mide confianza.  
El Motor Antifraude mide riesgo.

## **16\. Restricciones  
El Trust Score no podrá:  
Ser vendido.  
Ser transferido.  
Ser intercambiado.  
Ser comprado.

## **17\. Reinicio de Cuenta  
En caso de cierre y reapertura:  
El puntaje anterior no será transferido automáticamente.

## **18\. Auditoría  
Todos los cambios de Trust Score deberán registrarse.  
Información mínima:  
Fecha.  
Evento.  
Motivo.  
Variación.  
Sistema origen.

## **19\. Escalabilidad  
El sistema deberá soportar:  
Nuevos servicios.  
Nuevas ciudades.  
Nuevas categorías.  
Nuevos indicadores.  
Sin modificar la lógica principal.

## **20\. Principio Rector Final  
La confianza es un activo que se construye mediante comportamiento real y sostenido.  
El Trust Score existe para proteger el ecosistema, mejorar la experiencia de los usuarios y fortalecer la sostenibilidad de Tu Mobil Amigo V1.0.

## **21\. Fuente de Eventos y Alertas
Los eventos generados por el Motor Antifraude que requieran notificación o escalamiento se catalogan formalmente en el Documento 42A — Catálogo de Alertas e Incidentes, el cual debe mantenerse sincronizado con los tipos de evento descritos en este documento.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 13 — Trust Score

Documento 14 — Índice de Maduración Financiera (IMF)

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

El Índice de Maduración Financiera (IMF) es el mecanismo encargado de administrar la liberación progresiva de beneficios económicos dentro del ecosistema Tu Mobil Amigo.

Su propósito es:

Incentivar la permanencia.  
Incentivar el uso real de la plataforma.  
Reducir fraude financiero.  
Reducir lavado de activos.  
Reducir cuentas artificiales.  
Proteger la liquidez del ecosistema.  
Fortalecer la economía interna.

2\. Principio Fundamental  
Todo beneficio económico generado dentro del ecosistema deberá atravesar un proceso de maduración antes de convertirse en saldo liberado.

3\. Beneficios Sujetos a IMF  
Clientes  
Participan en IMF:  
Cashback Ganado.  
Comisiones Ganadas.  
Bonificaciones futuras aprobadas.  
Asesores  
Participan en IMF:  
Comisiones Ganadas.  
Incentivos QR Ganados.  
Bonificaciones futuras aprobadas.  
Exclusiones  
No participan en IMF:  
Bolsa Operativa del Asesor.  
Recargas.  
Saldos operativos.  
Pagos directos de servicios.

4\. Estructura de Saldos  
Cliente  
Saldo Disponible  
Recursos liberados y utilizables.

Cashback Ganado  
Beneficios acumulados pendientes de maduración.

Cashback Liberado  
Beneficios disponibles para retiro o consumo.

Comisiones Ganadas  
Comisiones multinivel pendientes de maduración.

Comisiones Liberadas  
Comisiones disponibles.

Total Histórico  
Registro acumulado de toda la actividad financiera.

Asesor

Bolsa Operativa  
Utilizada exclusivamente para:  
Recargas.  
Descuentos de comisiones.  
Operación diaria.

Bolsa de Beneficios  
Contiene:  
Comisiones Ganadas.  
Comisiones Liberadas.  
Incentivos QR Ganados.  
Incentivos QR Liberados.

5\. Principio de Separación  
La Bolsa Operativa y la Bolsa de Beneficios serán completamente independientes.  
No podrán mezclarse.  
No podrán transferirse recursos entre ellas.

6\. Variables de Liberación  
La liberación financiera dependerá de:

Factor				Participación  
Antigüedad			30%  
Trust Score			35%  
Actividad Real (IPA)		25%  
Participación de Red (IPR)	10%  
Total: 				100%

7\. Antigüedad  
La permanencia máxima considerada será:  
12 meses  
Escala:  
Meses	Puntaje  
0-1	0  
2-3	25  
4-6	50  
7-9	75  
10-12+	100

8\. Trust Score  
Se utilizará el puntaje vigente del usuario.  
Escala:         0 \- 100

9\. Actividad Real (IPA)  
Se medirá mediante el Índice de Participación y Actividad.  
Objetivos:

Clientes  
Categoría	Servicios Mes  
Explorador	0 \- 9  
Viajero		10 \- 19  
Experto		20 \- 39  
Leyenda		40+

Asesores 	Moto  
Categoría	Servicios Mes  
Explorador	0 \- 149  
Viajero		150 \- 199  
Experto		200 \- 249  
Leyenda		250+

Asesores 	Vehículo  
Categoría	Servicios Mes  
Explorador	0 \- 59  
Viajero		60 \- 79  
Experto		80 \- 99  
Leyenda		100+

10\. Participación de Red (IPR)  
Evalúa:  
Referidos activos.  
Permanencia.  
Actividad real.  
Calidad de la red.  
No evalúa únicamente cantidad.

11\. Fórmula Conceptual IMF  
IMF \= (Antigüedad × 30%) \+ (Trust Score × 35%) \+ (IPA × 25%) \+ (IPR × 10%)

Resultado: 0 \- 100

12\. Niveles de Maduración

Nivel		IMF  
Inicial		0 \- 25  
Intermedio	26 \- 50  
Avanzado	51 \- 75  
Consolidado	76 \- 100

13\. Porcentaje Máximo de Liberación  
Nivel	Liberación Máxima  
Inicial		10%  
Intermedio	35%  
Avanzado	70%  
Consolidado	100%

14\. Regla de Liberación Continua  
La liberación será progresiva.  
Nunca ocurrirá una liberación total automática únicamente por cumplir tiempo.

15\. Restricción Antifraude  
La antigüedad por sí sola no genera liberación.  
Siempre deberá existir:  
Actividad real.  
Trust Score suficiente.  
Participación válida.

16\. Congelamiento Preventivo  
El sistema podrá congelar liberaciones cuando existan:  
Alertas de fraude.  
Investigación interna.  
Inconsistencias financieras.  
Riesgos AML.

17\. Incentivos QR  
Los incentivos provenientes de servicios QR:  
Participan en IMF.  
Se acumulan como Incentivos QR Ganados.  
Se liberan progresivamente.

18\. Cashback de Servicios Programados  
Los beneficios adicionales obtenidos por programación de servicios:  
Participan en IMF.  
Se consideran Cashback Ganado.  
Siguen exactamente las mismas reglas de liberación.

19\. Consumo Interno Futuro  
El sistema podrá permitir en versiones futuras:  
Uso de beneficios liberados.  
Consumo en comercios aliados.  
Uso en ecosistemas propios.  
Siempre sujeto a controles financieros y antifraude.

20\. Objetivo Estratégico  
El IMF no busca retrasar pagos.  
Busca garantizar que los beneficios económicos estén asociados a usuarios reales, actividad real y crecimiento sostenible.

21\. Principio Rector Final  
Todo beneficio económico dentro de Tu Mobil Amigo deberá madurar mediante confianza, actividad, permanencia y participación antes de convertirse en un recurso completamente disponible.

## **22\. Relación entre IMF y Liquidaciones**

La liberación de recursos por cumplimiento del IMF no implica pago inmediato.

Todo valor liberado ingresará automáticamente al proceso de liquidación mensual.

---

## **23\. Flujo Financiero**

IMF

↓

Liberación

↓

Pendiente Liquidación

↓

Liquidación Mensual

↓

Pago

↓

Finalizado

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 14 — Índice de Maduración Financiera (IMF)  


Documento 15 — Motor Antifraude

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo

El Motor Antifraude es el sistema encargado de identificar, prevenir, contener y registrar comportamientos que representen riesgos para la operación, la seguridad, la estabilidad financiera o la legalidad del ecosistema Tu Mobil Amigo.  
Su función no es castigar usuarios.  
Su función es:  
Detectar riesgos.  
Proteger usuarios.  
Proteger asesores.  
Proteger la red multinivel.  
Proteger el cashback.  
Proteger las billeteras.  
Proteger la sostenibilidad financiera.

2\. Principios Fundamentales

AF-01 — Presunción de Buena Fe  
Todo usuario será considerado legítimo hasta que existan evidencias suficientes de comportamiento anómalo.

AF-02 — Riesgo Acumulativo  
Un único evento aislado no deberá provocar sanciones automáticas.  
El sistema evaluará patrones.

AF-03 — Evidencia Digital  
Toda alerta deberá estar sustentada por evidencia trazable.

AF-04 — Escalabilidad  
Las reglas deberán funcionar para:  
100 usuarios.  
10.000 usuarios.  
100.000 usuarios.  
1.000.000 usuarios.  
Múltiples ciudades.  
Sin modificaciones estructurales.

3\. Arquitectura General

El Motor Antifraude estará compuesto por:  
Módulo de Identidad  
Módulo de Dispositivos  
Módulo Operativo  
Módulo Financiero  
Módulo Multinivel  
Módulo QR  
Módulo de Auditoría

4\. Niveles de Riesgo

Nivel	Riesgo  
0	Sin riesgo  
1	Riesgo Bajo  
2	Riesgo Medio  
3	Riesgo Alto  
4	Riesgo Crítico

5\. Módulo de Identidad  
Evalúa:  
Documento de identidad.  
Coincidencia de datos.  
Duplicidad de registros.  
Inconsistencias de información.  
Alertas:  
Documento duplicado.  
Teléfono duplicado.  
Correo duplicado.  
Identidad sospechosa.

6\. Módulo de Dispositivos  
Evalúa:  
Dispositivo principal.  
Cambios frecuentes.  
Huella digital del dispositivo.  
Historial de acceso.  
Variables sugeridas:  
UUID dispositivo  
Modelo  
Sistema operativo  
Versión App  
IP histórica  
Zona horaria  
Patrones de conexión

7\. Módulo Dispositivo Confiable  
Todo usuario tendrá un dispositivo principal.  
Los cambios frecuentes aumentarán el riesgo.

8\. Módulo Operativo  
Evalúa:  
Servicios solicitados.  
Servicios completados.  
Cancelaciones.  
Negociaciones.  
Alertas:  
Cancelaciones masivas.  
Servicios simulados.  
Comportamiento coordinado.

9\. Módulo de Negociación  
Evalúa:  
Contraofertas repetitivas.  
Negociaciones artificiales.  
Patrones de manipulación.  
El sistema deberá identificar:  
Cliente A  
↓  
Asesor B  
↓  
Mismo patrón repetitivo

10\. Módulo Financiero  
Evalúa:  
Recargas.  
Retiros.  
Liberaciones IMF.  
Comisiones.  
Cashback.  
Alertas:  
Movimientos anormales.  
Crecimiento acelerado.  
Patrones incompatibles con la actividad.

11\. Módulo Multinivel  
Evalúa:  
Crecimiento de red.  
Calidad de referidos.  
Concentración de actividad.  
Alertas:  
Auto patrocinio.  
Redes artificiales.  
Estructuras coordinadas.

12\. Módulo QR  
Evalúa:  
Uso de QR.  
Servicios de calle.  
Frecuencia.  
Repetición de usuarios.  
Alertas:  
Servicios QR ficticios.  
Clientes repetitivos.  
Montos anormales.  
Incentivos QR artificiales.

13\. Servicios Espejo  
Se consideran de alto riesgo los patrones donde:  
Cliente A  
↓  
Asesor B

Cliente A  
↓  
Asesor B

Cliente A  
↓  
Asesor B

durante periodos prolongados sin variación operativa razonable.

14\. Módulo de Geolocalización  
Evalúa:  
Distancias recorridas.  
Ubicaciones frecuentes.  
Consistencia operacional.  
Alertas:  
Servicios físicamente imposibles.  
Cambios instantáneos de ubicación.  
Operación simultánea incompatible.

15\. Integración con Trust Score  
El Motor Antifraude alimentará el Trust Score.  
Podrá:  
Reducir puntajes.  
Limitar beneficios.  
Generar observaciones.  
No podrá:  
Modificar tarifas.  
Alterar negociaciones.

16\. Integración con IMF  
Las alertas podrán:  
Congelar beneficios.  
Suspender liberaciones.  
Requerir revisión.

17\. Eventos Críticos  
Se consideran críticos:  
Suplantación.  
Documentación falsa.  
Multiplicidad de cuentas.  
Fraude financiero.  
Manipulación deliberada.

18\. Sistema de Puntuación de Riesgo  
Cada evento generará una puntuación.

Ejemplo conceptual:  
Evento	Riesgo  
Cambio de dispositivo	\+5  
Teléfono duplicado	\+15  
Servicio sospechoso	\+20  
QR fraudulento		\+25  
Identidad falsa		\+50

19\. Acciones Automáticas  
Según el nivel de riesgo:

Riesgo Bajo  
Monitoreo.

Riesgo Medio  
Observación reforzada.

Riesgo Alto  
Restricción temporal.

Riesgo Crítico  
Congelamiento preventivo.  
Revisión manual.

20\. Auditoría Obligatoria  
Toda acción del motor deberá generar:  
Fecha  
Usuario  
Evento  
Origen  
Nivel de riesgo  
Acción aplicada

21\. Conservación de Evidencia  
La evidencia deberá conservarse para:  
Auditoría interna.  
Cumplimiento normativo.  
Investigación de fraude.

22\. Prevención de Lavado de Activos  
El motor deberá identificar:  
Actividad económica inconsistente.  
Redes financieras artificiales.  
Movimientos incompatibles con el perfil del usuario.  
Acumulaciones anormales de beneficios.

23\. Cumplimiento Normativo  
El Motor Antifraude deberá alinearse con:  
Legislación colombiana vigente.  
Protección de datos.  
Normativa financiera aplicable.  
Requisitos de prevención de fraude.  
Requisitos de prevención de lavado de activos.

24.Fuente de Señales

Device Fingerprint  
Device Trust Score  
VPN Detection  
Proxy Detection  
Device Reputation  
 

25\. Principio Rector Final  
La confianza se presume.  
El fraude se investiga.  
La evidencia decide.

Toda acción del Motor Antifraude deberá estar sustentada por información verificable, trazable y auditable.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 15 — Motor Antifraude  
