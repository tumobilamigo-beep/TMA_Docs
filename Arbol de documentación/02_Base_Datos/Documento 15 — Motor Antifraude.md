Base de Datos

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


Documento 16 — Modelo Conceptual

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir las entidades de negocio principales del ecosistema Tu Mobil Amigo V1.0 y las relaciones existentes entre ellas, independientemente de cualquier tecnología específica de base de datos.  
Este documento representa la visión conceptual del sistema y servirá como base para:

Modelo Lógico.  
Modelo Físico.  
APIs.  
Backend.  
Seguridad.  
Auditoría.  
Analítica.

2\. Principios de Diseño

MC-01 — El modelo representa el negocio  
Las entidades deben reflejar procesos reales.  
No deben diseñarse pensando únicamente en la implementación técnica.

MC-02 — Escalabilidad  
El modelo deberá soportar:  
Nuevas ciudades.  
Nuevos servicios.  
Nuevos medios de pago.  
Nuevos tipos de asesores.  
Nuevos programas de incentivos.  
Sin rediseños estructurales.

MC-03 — Auditoría Total  
Toda operación crítica deberá ser trazable.

MC-04 — Seguridad por Diseño  
Toda entidad sensible deberá ser compatible con:  
Trust Score.  
IMF.  
Motor Antifraude.  
Auditoría.

3\. Macro Dominios del Sistema  
El ecosistema se divide en:  
Usuarios  
Movilidad  
Negociación  
Finanzas  
Multinivel  
Confianza  
Seguridad  
Configuración  
Auditoría

4\. Dominio Usuarios  
Entidad: Usuario  
Representa cualquier persona registrada.  
Tipos:  
Cliente  
Asesor  
Administrador

Atributos conceptuales:  
Identificación  
Nombre  
Contacto  
Estado  
Fecha registro

5\. Dominio Dispositivos  
Entidad: Dispositivo  
Representa equipos autorizados.  
Relación:  
Usuario  
1 → N  
Dispositivos  
Permite:  
Control de acceso.  
Detección de fraude.  
Historial de cambios.

6\. Dominio Geográfico

Entidad: Ciudad  
Representa una ciudad habilitada.  
Ejemplos:  
Santa Marta  
Barranquilla  
Cartagena  
Bogotá

Relación:  
Ciudad  
1 → N  
Zonas Operativas

7\. Dominio Movilidad  
Entidad: Servicio  
Representa una solicitud de movilidad.

Modalidades:  
Inmediato  
Programado  
QR Calle

Estados:  
Creado  
Ofertado  
Negociación  
Aceptado  
En Curso  
Finalizado  
Cancelado

Relaciones:  
Cliente  
1 → N

Servicios  
Asesor  
1 → N  
Servicios

8\. Dominio Ofertas  
Entidad: Oferta  
Representa una propuesta económica.  
Relación:  
Servicio  
1 → N  
Ofertas

Características:  
Valor ofertado  
Fecha  
Estado  
Vigencia

9\. Dominio Negociación  
Entidad: Contraoferta  
Representa una respuesta económica.

Relación:  
Oferta  
1 → N  
Contraofertas  
Regla aprobada:  
Un asesor puede emitir  
una única contraoferta  
por cliente.  
El cliente tiene decisión final.

10\. Dominio Tarifario  
Entidad: Parámetro Tarifario  
Contiene variables configurables.  
Principio obligatorio:  
Todas las variables  
residen en base de datos.  
Ninguna variable  
se almacena en código.

Permite:  
Ajuste por ciudad.  
Ajuste normativo.  
Ajuste operacional.

11\. Dominio QR  
Entidad: QR Cliente  
Representa el identificador único del cliente.  
Objetivos:  
Radicar servicios de calle.  
Asociar servicios externos.  
Generar trazabilidad.  
Relación:  
Cliente  
1 → 1  
QR

12\. Dominio Financiero  
Entidad: Bolsa Operativa  
Exclusiva para asesores.  
Función:  
Recargas.  
Débitos operativos.  
Comisión de servicios.  
Restricción:  
No participa en IMF.  
Entidad: Bolsa de Beneficios  
Contiene:  
Cashback.  
Comisiones.  
Incentivos.  
Participa en IMF.

13\. Dominio Cashback  
Entidad: Cashback  
Representa beneficios generados.  
Estados:  
Ganado  
Liberado  
Retirado

14\. Dominio Multinivel  
Entidad: Red Multinivel  
Representa relaciones padre-hijo.  
Profundidad máxima:  
2 niveles  
Nivel 1  
Padre.  
Nivel 2  
Abuelo.

15\. Dominio Comisiones  
Entidad: Comisión  
Representa beneficios generados por red.  
Estados:  
Generada  
Madurando  
Liberada  
Pagada

16\. Dominio Incentivos QR  
Entidad: Incentivo QR  
Representa beneficios obtenidos por radicación válida de servicios QR.  
Estados:  
Generado  
Madurando  
Liberado  
Pagado  
Participa en IMF.

17\. Dominio Trust Score  
Entidad: Trust Score  
Representa la confianza acumulada.

Escala:  
0 \- 100

Categorías:  
Explorador  
Viajero  
Experto  
Leyenda

18\. Dominio IMF  
Entidad: Índice de Maduración Financiera  
Representa el nivel de maduración financiera.  
Factores:  
Antigüedad.  
Trust Score.  
IPA.  
IPR.  
Resultado:  
0 \- 100

19\. Dominio Antifraude  
Entidad: Evento Antifraude  
Representa cualquier anomalía detectada.  
Estados:  
Abierto  
En Investigación  
Resuelto  
Descartado

20\. Dominio Auditoría  
Entidad: Bitácora  
Registra eventos del sistema.  
Ejemplos:  
Login.  
Cambio de dispositivo.  
Servicio creado.  
Servicio finalizado.  
Liberación IMF.  
Retiro.

21\. Dominio Configuración  
Entidad: Configuración del Sistema  
Permite parametrizar:  
Tiempos.  
Porcentajes.  
Límites.  
Umbrales.  
Reglas operativas.  
Principio:  
Configuración en BD.  
No en código.

22\. Relación Conceptual Principal  
Usuario  
│  
├── Dispositivos  
│  
├── Servicios  
│     ├── Ofertas  
│     └── Contraofertas  
│  
├── QR  
│  
├── Trust Score  
│  
├── IMF  
│  
├── Cashback  
│  
├── Comisiones  
│  
├── Incentivos QR  
│  
└── Eventos Antifraude

23\. Liquidación

Relacionada con:

Usuario  
Cashback  
Multinivel  
Incentivos  
Auditoría

24\. Principio Rector Final  
Toda entidad del ecosistema deberá contribuir a uno o más de los siguientes objetivos:  
Operación.  
Seguridad.  
Confianza.  
Escalabilidad.  
Rentabilidad.  
Cumplimiento normativo.  
Ninguna entidad deberá existir sin una justificación directa de negocio.

25\. Entidad:

Device\_registry
y relación con:

usuarios

Entidad: Rol
Descripción: representa un nivel de privilegio dentro del sistema (Cliente, Asesor, Administrador, Superadministrador).
Relación: 1 usuario → 1 rol principal (mínimo); un usuario administrativo podrá tener permisos adicionales granulares.

Entidad: Permiso
Descripción: representa una capacidad específica del sistema (ej. "ejecutar_reapertura_periodo", "editar_parametros_globales").
Relación: N permisos ↔ N roles (tabla de asociación).

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 16 — Modelo Conceptual  

