Documento 02 — Contexto Maestro

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Propósito

Este documento define el contexto oficial del proyecto Tu Mobil Amigo V1.0.

Toda Inteligencia Artificial, desarrollador, arquitecto o consultor deberá utilizar este documento como referencia principal para comprender el negocio antes de proponer soluciones.

2\. ¿Qué es Tu Mobil Amigo?

Tu Mobil Amigo es un ecosistema tecnológico de movilidad, servicios y beneficios económicos diseñado para conectar clientes y asesores mediante una plataforma segura, trazable y escalable.

El objetivo no es únicamente intermediar servicios de transporte.

El objetivo es construir una red económica sostenible que genere valor para:

Clientes.  
Asesores.  
Empresa.  
Ecosistema comercial futuro.  
3\. Problemas que Resuelve  
Para el Cliente  
Dificultad para conseguir transporte confiable.  
Falta de trazabilidad.  
Falta de beneficios por uso recurrente.  
Inseguridad en servicios informales.  
Para el Asesor  
Falta de oportunidades de trabajo.  
Ingresos inestables.  
Ausencia de herramientas tecnológicas.  
Ausencia de beneficios por fidelización.  
Para la Empresa  
Crear un ecosistema escalable.  
Construir una red comercial propia.  
Generar sostenibilidad financiera.  
Reducir fraude y abuso.  
4\. Ciudad de Lanzamiento

La primera ciudad de operación será:

Santa Marta  
Magdalena  
Colombia

Toda parametrización inicial deberá diseñarse considerando esta ciudad.

5\. Servicios Iniciales  
V1

Servicios habilitados:

Mototaxi.  
Taxi.  
V2

Servicios proyectados:

Mensajería.  
Domicilios.  
V3

Servicios proyectados:

Motocarro.  
Carga liviana.  

6\. Roles del Ecosistema

Existen cuatro roles oficiales.
Cliente
Solicita servicios.
Puede:
Negociar servicios.
Generar historial.
Acumular beneficios.
Participar en la red.
Asesor
Prestador de servicios.
Puede operar como:
Mototaxista.
Taxista.
Mensajero.
Domiciliario.
Operador de motocarro.
Administrador
Responsable de la operación diaria de la plataforma:
Gestión de usuarios y asesores.
Servicios, recargas y retiros.
Liquidaciones ordinarias.
Soporte y reportes.
No puede modificar motores financieros, Trust, IMF, Antifraude ni parámetros globales.
Superadministrador
Responsable del gobierno integral del ecosistema:
Gestión de administradores.
Parámetros globales y configuraciones financieras.
Integraciones y seguridad.
Auditoría completa.
Motores del sistema (Tarifario, Antifraude, Trust, IMF).
Único rol habilitado para liquidaciones extraordinarias y reapertura de períodos contables.
Cliente y Asesor operan desde Flutter. Administrador y Superadministrador operan desde portales web independientes en React (ver Documento 06 — DA-033 y Documento 28).

7\. Filosofía del Sistema

La plataforma no busca controlar el mercado.

Busca crear un mecanismo transparente donde:

El sistema sugiera.  
Las personas negocien.  
La plataforma registre.  
La operación sea trazable.  
8\. Modelo de Servicios

Existen dos modelos oficiales.

Servicio Digital

Originado dentro de la plataforma.

Flujo:

Cliente  
↓  
Plataforma  
↓  
Asesor

Utiliza:

Motor Tarifario.  
Motor de Negociación.  
Realtime.  
Trust Score.  
Servicio Externo

Originado fuera de la plataforma.

Flujo:

Cliente  
↔  
Asesor

↓

Registro QR

Características:

Negociación libre.  
Registro posterior.  
Genera historial.  
Genera actividad.  
Genera beneficios.  
9\. Registro mediante QR

Cada usuario tendrá un QR único.

El QR permitirá:

Identificación.  
Registro de servicios externos.  
Trazabilidad.  
Prevención de fraude.  
10\. Restricción de Autobeneficio

Se encuentra prohibido:

cliente\_uuid \= asesor\_uuid

La plataforma deberá bloquear cualquier intento de:

Autocontratación.  
Autorregistro.  
Autobeneficio.  
Generación artificial de actividad.  
11\. Modelo Económico

La plataforma combina:

Movilidad.  
Beneficios económicos.  
Cashback.  
Red multinivel.

Todo dentro de un modelo sostenible.

12\. Bolsas Financieras  
Cliente

Podrá tener:

Saldo Disponible.  
Cashback Ganado.  
Cashback Liberado.  
Comisiones Ganadas.  
Comisiones Liberadas.  
Histórico.  
Asesor

Tendrá dos mundos independientes.

Bolsa Operativa

Utilizada exclusivamente para:

Recargas.  
Descuentos operativos.  
Servicios.

Es la única billetera válida para operar.

Bolsa de Beneficios

Utilizada para:

Cashback.  
Comisiones.  
Beneficios.  
Liberaciones.

Nunca podrá mezclarse con la Bolsa Operativa.

13\. Bolsa Operativa

Todo asesor deberá mantener un saldo mínimo.

Regla actual:

$5.000 COP

Si el saldo baja del mínimo:

No podrá recibir servicios.  
No podrá aceptar servicios.  
No podrá participar en la operación.  
14\. Sistema Multinivel

La plataforma utilizará una red de dos niveles.

Nivel 1

Referente directo.

Padre  
Nivel 2

Referente indirecto.

Abuelo  
15\. Distribución de Beneficios

La distribución será definida en el Modelo Financiero.

Sin embargo se establece que:

Empresa participa.  
Cliente participa.  
Red participa.

Todo beneficio deberá surgir de actividad real y verificable.

16\. Categorías de Participación

Los usuarios serán clasificados mediante categorías evolutivas.

Explorador

Nivel inicial.

Viajero

Participación frecuente.

Experto

Participación avanzada.

Leyenda

Máximo nivel del ecosistema.

17\. Indicadores Estratégicos

La plataforma utilizará:

IPA

Índice de Participación Activa.

IPR

Índice de Participación de Red.

Trust Score

Confiabilidad del usuario.

IMF

Índice de Maduración Financiera.

18\. Principio Antifraude

Toda funcionalidad deberá responder:

¿Cómo podría abusarse?

Antes de aprobar cualquier desarrollo deberá existir una estrategia de mitigación.

19\. Ecosistema Futuro

La visión de largo plazo contempla:

Comercio aliado.  
Talleres aliados.  
Supermercados aliados.

Y posteriormente:

Talleres propios.  
Supermercados propios.  
Ecosistema comercial Tu Mobil Amigo.  
20\. Meta Final

Convertir Tu Mobil Amigo en una plataforma nacional que combine:

Movilidad.  
Seguridad.  
Beneficios económicos.  
Red comercial.  
Red multinivel.  
Tecnología.

Manteniendo siempre:

Seguridad  
\+  
Escalabilidad  
\+  
Trazabilidad  
\+  
Sostenibilidad Financiera

Fin del Documento 02 — Contexto Maestro
