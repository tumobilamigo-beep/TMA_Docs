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

Responsable de:

Seguridad.  
Finanzas.  
Auditoría.  
Operación.

\#\# Administrador

Responsable de:

\* Configuración.  
\* Seguridad.  
\* Auditoría.  
\* Operación financiera.  
\* Supervisión del sistema.

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
