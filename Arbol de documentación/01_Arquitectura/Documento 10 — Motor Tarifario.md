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
