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

Documento 17 — Modelo Lógico

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir la estructura lógica de almacenamiento de informadeción de Tu Mobil Amigo V1.0.  
Este modelo traduce el negocio definido en el Modelo Conceptual hacia entidades persistentes que posteriormente serán implementadas en PostgreSQL/Supabase.

2\. Principios de Diseño

ML-01 — Configuración sobre Código  
Toda regla modificable deberá almacenarse en base de datos.  
Nunca en código.  
Ejemplos:  
Tarifas.  
Comisiones.  
Cashback.  
Límites.  
Tiempos.  
Score.  
IMF.

ML-02 — Una Fuente de Verdad  
Cada dato tendrá una única tabla propietaria.  
Evitar duplicidad.

ML-03 — Auditoría Total  
Toda operación financiera u operativa deberá poder reconstruirse históricamente.

3\. Núcleo de Usuarios  
usuarios  
Contiene:  
Cliente  
Asesor  
Administrador

Campos principales:  
id  
tipo\_usuario  
nombre  
apellido  
documento  
telefono  
email  
estado  
fecha\_registro  
dispositivos

Relaciona usuarios con equipos autorizados.

id  
usuario\_id  
fingerprint  
modelo  
sistema\_operativo  
version\_app  
fecha\_registro  
ultimo\_acceso  
activo

4\. Núcleo Geográfico  
ciudades  
id  
nombre  
codigo\_dane  
activo  
zonas\_operacion  
id  
ciudad\_id  
nombre  
activo

5\. Configuración Global  
configuracion\_sistema  
Centraliza parámetros globales.  
Ejemplos:  
oferta\_expira\_segundos  
porcentaje\_comision  
cashback\_programado  
saldo\_minimo\_operacion  
max\_contraofertas  
meses\_maduracion  
trust\_score\_minimo

6\. Motor Tarifario  
Una única tabla: parametros\_tarifarios  
Cada registro corresponde a una ciudad y vigencia específica.  
Campos:  
id  
nombre  
codigo\_dane  
ciudad\_id  
valor\_banderazo  
valor\_km  
valor\_minuto  
recargo\_nocturno  
recargo\_dominical  
recargo\_festivo  
factor\_moto  
factor\_taxi  
vigente\_desde  
vigente\_hasta

activo

Principio:

Todas las variables tarifarias  
deben vivir aquí.

7\. Servicios  
servicios  
Tabla principal del negocio.  
Campos:  
id  
cliente\_id  
asesor\_id  
ciudad\_id  
tipo\_servicio  
modalidad  
inmediato  
programado  
qr  
estado  
origen  
destino  
distancia\_km  
duracion\_minutos  
valor\_sugerido  
valor\_final  
fecha\_servicio  
fecha\_creacion

8\. Ofertas  
ofertas  
id  
servicio\_id  
usuario\_origen  
valor  
estado  
fecha\_creacion  
fecha\_expiracion

9\. Contraofertas  
contraofertas  
id  
oferta\_id  
asesor\_id  
valor  
estado  
fecha\_creacion

10\. QR  
qr\_clientes  
id  
usuario\_id  
codigo\_qr  
fecha\_generacion  
activo

11\. Finanzas  
billeteras  
Una sola tabla.  
Separada por tipo.  
Tipos:  
OPERATIVA  
BENEFICIOS  
Campos:  
id  
usuario\_id  
tipo\_billetera  
saldo  
estado  
Ventaja:  
No necesitamos:  
billetera\_operativa  
billetera\_beneficios

12\. Movimientos Financieros  
movimientos\_financieros  
Tabla maestra.  
Campos:  
id  
usuario\_id  
billetera\_id  
tipo\_movimiento  
valor  
descripcion  
referencia  
fecha

Ejemplos:  
recarga  
comision  
cashback  
liberacion  
retiro  
ajuste  
reserva

13\. Cashback  
cashback  
id  
usuario\_id  
servicio\_id  
valor  
estado  
fecha\_generacion  
fecha\_liberacion  
Estados:  
ganado  
liberado  
retirado

14\. Red Multinivel  
red\_multinivel  
usuario\_id  
upliner\_nivel\_1  
upliner\_nivel\_2  
fecha\_vinculacion  
Optimización:  
No crear tablas por nivel.

15\. Comisiones  
comisiones  
id  
usuario\_id  
servicio\_id  
nivel  
valor  
estado  
fecha\_generacion

16\. Incentivos QR  
incentivos\_qr  
id  
usuario\_id  
servicio\_id  
valor  
estado  
fecha\_generacion

17\. Trust Score  
trust\_score  
usuario\_id  
puntaje  
categoria  
ultima\_actualizacion

18\. IPA  
ipa  
usuario\_id  
puntaje  
categoria  
periodo

19\. IPR  
ipr  
usuario\_id  
puntaje  
categoria  
periodo

20\. IMF  
imf  
usuario\_id  
puntaje  
categoria  
ultima\_actualizacion

21\. Antifraude  
eventos\_antifraude  
id  
usuario\_id  
tipo\_evento  
nivel\_riesgo  
descripcion  
estado  
fecha

22\. Auditoría  
auditoria  
Tabla universal.  
id  
usuario\_id  
evento  
tabla\_origen  
registro\_origen  
detalle  
fecha

23\. Notificaciones  
notificaciones  
id  
usuario\_id  
tipo  
titulo  
mensaje  
leida  
fecha

24\. Integraciones  
integraciones\_externas  
Permite registrar:  
Telegram  
PSE  
Pasarelas  
Maps  
SMS

25\. Relación General Simplificada  
usuarios  
│  
├─ dispositivos  
├─ qr\_clientes  
├─ billeteras  
├─ trust\_score  
├─ ipa  
├─ ipr  
├─ imf  
│  
├─ servicios  
│   ├─ ofertas  
│   ├─ contraofertas  
│   ├─ cashback  
│   ├─ comisiones  
│   └─ incentivos\_qr  
│  
├─ eventos\_antifraude  
└── device\_registry   
├─ auditoria  
└─ notificaciones  
└── liquidaciones   
├── liquidacion\_detalles   
      	└── liquidacion\_auditoria 

26\. Optimización Alcanzada  
Con todas las reglas aprobadas:  
24 tablas principales  
en lugar de:  
50-70 tablas  
que normalmente aparecerían en una plataforma con:  
Movilidad.  
Multinivel.  
Cashback.  
Trust Score.  
IMF.  
Antifraude.  
QR.

### **27\. cierres\_mensuales**

Responsable de almacenar cada cierre financiero mensual.

---

### **28\. liquidaciones\_mensuales**

Responsable de almacenar la liquidación consolidada por usuario.

---

### **29\. detalle\_liquidacion**

Responsable de almacenar cada concepto incluido dentro de la liquidación.

---

### **30\. pagos\_liquidacion**

Responsable de registrar los pagos efectuados por la empresa.

### **31\.roles
- id_rol (PK)
- nombre (Cliente | Asesor | Administrador | Superadministrador)
- descripcion
- nivel_privilegio (entero, para jerarquía)

permisos
- id_permiso (PK)
- codigo (único, ej. EJECUTAR_REAPERTURA_PERIODO)
- descripcion
- dominio (referencia a los dominios de DA-034: Auth, Core, Operations, Pricing, Finance, Multilevel, Trust, IMF, Security, Notifications, Integrations, Admin, Audit)

roles_permisos
- id_rol (FK → roles)
- id_permiso (FK → permisos)

usuarios_roles
- id_usuario (FK → usuarios)
- id_rol (FK → roles)
- fecha_asignacion
- asignado_por (FK → usuarios, debe ser Superadministrador para asignar rol Administrador/Superadministrador)

### **32\. Principio Rector Final  
La base de datos deberá ser capaz de reconstruir completamente la historia operativa, financiera y de confianza de cualquier usuario sin depender de lógica almacenada fuera de la base de datos.
Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 17 — Modelo Lógico  

Documento 18 — Modelo Físico

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir la estructura física que será implementada en PostgreSQL/Supabase.  
Este documento establece:

Tablas.  
Claves primarias.  
Claves foráneas.  
Índices.  
Restricciones.  
Relaciones.

2\. Convenciones

MF-01  
Todas las tablas:  
snake\_case

MF-02  
Clave primaria:  
uuid

MF-03  
Todas las tablas deberán incluir:  
created\_at  
updated\_at

MF-04  
Soft Delete.  
No se eliminan registros.  
deleted\_at  
cuando aplique.

3\. Tabla usuarios  
usuarios  
Campo		Tipo  
id		uuid PK  
tipo\_usuario	varchar(20)  
documento	varchar(30)  
nombre		varchar(150)  
telefono	varchar(30)  
email		varchar(150)  
estado		varchar(30)  
created\_at	timestamptz  
updated\_at	timestamptz

Índices  
idx\_usuarios\_documento  
idx\_usuarios\_telefono  
idx\_usuarios\_tipo

4\. Tabla asesores  
Extensión especializada.

asesores  
Campo			Tipo  
usuario\_id		uuid PK/FK  
tipo\_asesor		varchar(20)  
placa			varchar(20)  
marca\_vehiculo		varchar(50)  
modelo\_vehiculo		varchar(50)  
licencia\_vigente	boolean  
soat\_vigente		boolean  
tecnomecanica\_vigente	boolean

Tipos permitidos:  
MOTO  
CARRO  
MOTOCARRO

5\. Tabla ciudades  
ciudades  
Campo		Tipo  
id		uuid PK  
codigo\_dane	varchar(20)  
nombre		varchar(100)  
activo		boolean

6\. Tabla catalogos  
Optimización global.  
catalogos  
Campo	Tipo  
id	uuid PK  
codigo	varchar(100)  
nombre	varchar(150)

Ejemplos:

PARAMETROS\_TARIFARIOS  
TIPOS\_SERVICIO  
TIPOS\_EVENTO  
ESTADOS\_SERVICIO

7\. Tabla catalogo\_detalles  
catalogo\_detalles  
Campo		Tipo  
id		uuid PK  
catalogo\_id	uuid FK  
codigo		varchar(100)  
nombre		varchar(150)  
valor		text  
Ventaja:  
Nuevos parámetros sin crear tablas.

8\. Tabla parametros\_tarifarios

Optimizada para múltiples ciudades.  
parametros\_tarifarios  
Campo			Tipo  
id			uuid PK  
ciudad\_id		uuid FK  
parametro\_codigo	varchar(100)  
valor			numeric  
vigente\_desde		date  
vigente\_hasta		date  
activo			boolean

Ejemplos:  
valor\_banderazo  
valor\_km  
valor\_minuto  
recargo\_nocturno  
factor\_moto

9\. Tabla dispositivos  
dispositivos  
Campo		Tipo  
id		uuid PK  
usuario\_id	uuid FK  
fingerprint	varchar(255)  
modelo		varchar(100)  
so		varchar(50)  
version\_app	varchar(50)  
ultimo\_acceso	timestamptz  
activo		boolean

10\. Tabla servicios  
Núcleo operativo.  
servicios  
Campo			Tipo  
id			uuid PK  
cliente\_id		uuid FK  
asesor\_id		uuid FK  
ciudad\_id		uuid FK  
tipo\_servicio		varchar(50)  
modalidad		varchar(50)  
estado			varchar(50)  
origen\_lat		numeric  
origen\_lng		numeric  
destino\_lat		numeric  
destino\_lng		numeric  
distancia\_km		numeric  
duracion\_minutos	numeric  
valor\_sugerido		numeric  
valor\_final		numeric  
fecha\_programada	timestamptz  
created\_at		timestamptz

Modalidades:  
INMEDIATO  
PROGRAMADO  
QR

11\. Tabla ofertas  
ofertas  
Campo		Tipo  
id			uuid PK  
servicio\_id		uuid FK  
usuario\_origen	uuid FK  
valor			numeric  
estado			varchar(30)  
fecha\_expiracion	timestamptz

12\. Tabla contraofertas  
contraofertas  
Campo		Tipo  
id			uuid PK  
oferta\_id		uuid FK  
asesor\_id		uuid FK  
valor			numeric  
estado			varchar(30)

13\. Tabla billeteras  
Modelo único.  
billeteras  
Campo		Tipo  
id			uuid PK  
usuario\_id		uuid FK  
tipo\_billetera		varchar(30)  
saldo			numeric  
Tipos:  
OPERATIVA  
BENEFICIOS

14\. Tabla movimientos\_financieros  
Libro contable.  
movimientos\_financieros  
Campo		Tipo  
id			uuid PK  
billetera\_id		uuid FK  
usuario\_id		uuid FK  
tipo\_movimiento	varchar(50)  
valor			numeric  
referencia\_id		uuid  
descripcion		text

15\. Tabla red\_multinivel  
red\_multinivel  
Campo		Tipo  
usuario\_id		uuid PK  
upliner\_1		uuid FK  
upliner\_2		uuid FK

16\. Tabla trust\_score  
trust\_score  
Campo		Tipo  
usuario\_id		uuid PK  
puntaje			numeric  
categoria		varchar(30)

17\. Tabla ipa  
ipa  
Campo		Tipo  
usuario\_id		uuid PK  
puntaje			numeric  
categoria		varchar(30)

18\. Tabla ipr  
ipr  
Campo		Tipo  
usuario\_id		uuid PK  
puntaje			numeric  
categoria		varchar(30)

19\. Tabla imf  
imf  
Campo		Tipo  
usuario\_id		uuid PK  
puntaje			numeric  
categoria		varchar(30)

20\. Tabla eventos\_antifraude  
eventos\_antifraude  
Campo		Tipo  
id			uuid PK  
usuario\_id		uuid FK  
tipo\_evento		varchar(100)  
nivel\_riesgo		integer  
descripcion		text  
estado			varchar(30)

21\. Tabla auditoria  
auditoria  
Campo		Tipo  
id			uuid PK  
usuario\_id		uuid FK  
evento			varchar(150)  
tabla\_origen		varchar(150)  
registro\_origen	uuid  
detalle			jsonb

22\. Índices Críticos  
Crear obligatoriamente índices sobre:  
servicios(cliente\_id)  
servicios(asesor\_id)  
servicios(estado)  
ofertas(servicio\_id)  
contraofertas(oferta\_id)  
movimientos\_financieros(usuario\_id)  
eventos\_antifraude(usuario\_id)  
auditoria(usuario\_id)

23\. Particionado Futuro  
Cuando el sistema supere:  
1 millón de servicios  
particionar:  
servicios  
movimientos\_financieros  
auditoria  
por fecha.

24\. Resultado de Optimización  
Modelo inicial estimado:  
18 a 22 tablas reales  
Capacidad proyectada:  
100.000+ usuarios  
10.000.000+ servicios  
sin rediseño estructural.

**25\. Tabla liquidaciones**  
liquidaciones

id 			uuid PK

codigo\_liquidacion 	varchar(50) UNIQUE

usuario\_id 		uuid FK  
tipo\_liquidacion 	varchar(30)  
estado\_liquidacion 	varchar(30)  
periodo\_inicio 		timestamp  
periodo\_fin 		timestamp  
fecha\_generacion 	timestamp  
fecha\_aprobacion 	timestamp  
fecha\_ejecucion 	timestamp  
fecha\_pago 		timestamp  
cashback\_total 	numeric(18,2)  
nivel1\_total 		numeric(18,2)  
nivel2\_total 		numeric(18,2)  
incentivos\_total 	numeric(18,2)  
ajustes\_total 		numeric(18,2)  
total\_liquidacion 	numeric(18,2)  
motivo 			text  
aprobado\_por 		uuid  
ejecutado\_por 	uuid  
pagado\_por 		uuid  
numero\_version 	integer   
observaciones 	text  
created\_at 		timestamp  
updated\_at 		timestamp  
---

# **Estados permitidos**

BORRADOR  
APROBADA  
EJECUTADA  
PENDIENTE\_PAGO  
PAGADA  
ANULADA  
---

# **Tipos permitidos**

ORDINARIA

EXTRAORDINARIA  
---

# **Regla financiera**

Una liquidación  
NO genera dinero.

Una liquidación  
agrupa dinero ya generado.

Esto es importante.

Los cálculos nacen de:

* servicios;  
* cashback;  
* multinivel;  
* incentivos.

La liquidación únicamente los consolida.

---

# **Nueva Tabla: liquidacion\_detalles**

Esta tabla es incluso más importante.

Permite auditar de dónde sale cada peso.

liquidacion\_detalles  
id 			uuid PK  
liquidacion\_id 		uuid FK  
tipo\_movimiento 	varchar(50)  
referencia\_id 		uuid  
descripcion 		text  
valor 			numeric(18,2)  
created\_at 		timestamp  
---

# **Tipo movimiento**

CASHBACK

MULTINIVEL\_N1  
MULTINIVEL\_N2  
INCENTIVO  
AJUSTE  
REVERSO  
---

# **Ejemplo**

Liquidación

Carlos

$50.000

Detalle:

Cashback  
$20.000

Nivel 1  
$15.000

Nivel 2  
$10.000

Incentivo  
$5.000  
---

# **Nueva Tabla: liquidacion\_auditoria**

Debido al nivel financiero del proyecto.

liquidacion\_auditoria  
id 			uuid PK  
liquidacion\_id 		uuid FK  
evento 			varchar(50)  
usuario\_responsable 	uuid  
detalle 			jsonb  
created\_at 		timestamp  
---

# **Eventos**

SIMULADA  
APROBADA  
EJECUTADA  
PAGADA  
ANULADA

**25\. Tabla: device\_registry**  
device\_registry

id 				uuid primary key  
usuario\_id 			uuid not null  
fingerprint 			varchar(255) not null  
device\_trust\_score 		numeric(5,2) default 100  
estado 			varchar(30) not null  
reputacion 			varchar(30) not null  
fabricante 			varchar(100)  
modelo			 varchar(100)  
sistema\_operativo 		varchar(100)  
version\_so 			varchar(50)  
idioma 				varchar(20)  
zona\_horaria 			varchar(100)  
resolucion\_pantalla 		varchar(50)  
ip\_registro 			inet  
ultima\_ip 			inet  
ciudad 				varchar(100)  
region 				varchar(100)  
pais 				varchar(100)  
vpn\_detectado 		boolean default false  
proxy\_detectado 		boolean default false  
tor\_detectado 			boolean default false  
datacenter\_ip 			boolean default false  
fecha\_primer\_acceso 	timestamp  
fecha\_ultimo\_acceso 		timestamp  
cantidad\_accesos 		bigint default 0  
cantidad\_alertas 		integer default 0  
cantidad\_bloqueos 		integer default 0  
created\_at 			timestamp not null  
updated\_at 			timestamp not null  
---

## **Índices recomendados**

create index idx\_device\_usuario  
on device\_registry(usuario\_id);

create index idx\_device\_fingerprint  
on device\_registry(fingerprint);

create index idx\_device\_estado  
on device\_registry(estado);

create index idx\_device\_score  
on device\_registry(device\_trust\_score);  
---

## **Restricciones**

Estado:

ACTIVO  
OBSERVACION  
SUSPENDIDO  
BLOQUEADO  
---

Reputación:

CONFIABLE  
NORMAL  
RIESGO\_MEDIO  
RIESGO\_ALTO  
CRITICO

26\. Principio Rector Final  
La estructura física deberá priorizar simplicidad, trazabilidad, rendimiento y escalabilidad antes que la hiper-normalización innecesaria.

Fin del Documento 18 — Modelo Físico  

# **Documento 18A — Plan Maestro de Implementación de la Base de Datos**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir el proceso oficial para construir, validar, desplegar y evolucionar la base de datos de Tu Mobil Amigo.

Este documento establece el orden de implementación, las dependencias técnicas y los criterios de aprobación de cada fase.

Ninguna fase podrá iniciarse hasta que la anterior haya sido aprobada.

---

# **2\. Principios**

Toda implementación deberá cumplir los siguientes principios:

* Incremental.  
* Reversible.  
* Versionada.  
* Parametrizada.  
* Auditada.  
* Probada.  
* Documentada.

---

# **3\. Flujo General**

Documentación

↓

Diseño

↓

Migraciones SQL

↓

Validación

↓

Pruebas

↓

Integración

↓

Producción  
---

# **4\. Reglas Generales**

Antes de crear cualquier objeto deberán cumplirse las siguientes reglas.

✓ Documento aprobado.

✓ Dependencias implementadas.

✓ Convenciones SQL cumplidas.

✓ RLS definido.

✓ Auditoría definida.

✓ Índices definidos.

✓ Casos de prueba definidos.

---

# **5\. Orden Oficial de Construcción**

## **Fase 0 — Infraestructura**

Objetivo

Preparar Supabase.

Incluye:

* Proyecto.  
* Regiones.  
* Storage.  
* Secrets.  
* Extensiones PostgreSQL.  
* Roles.  
* Esquemas.  
* Configuración inicial.

Entregable:

Base vacía lista para construir.

---

# **Fase 1 — Catálogos Maestros**

Crear únicamente tablas de referencia.

Ejemplos:

* países  
* departamentos  
* ciudades  
* monedas  
* tipos\_servicio  
* tipos\_vehiculo  
* marcas  
* colores  
* parámetros\_generales  
* estados

No existen aún usuarios ni servicios.

---

# **Fase 2 — Núcleo (Core)**

Crear:

* usuarios  
* perfiles  
* documentos  
* dispositivos  
* vehículos  
* asesores  
* clientes  
* QR

Al finalizar esta fase será posible registrar usuarios.

---

# **Fase 3 — Configuración**

Crear:

* variables\_tarifarias  
* decretos  
* configuración  
* versiones

No se implementa aún el motor tarifario.

Solo parametrización.

---

# **Fase 4 — Operación**

Crear:

* servicios  
* ofertas  
* contraofertas  
* servicios\_programados  
* historial\_estados

Al finalizar esta fase podrá ejecutarse un flujo completo de solicitud y asignación.

---

# **Fase 5 — Finanzas**

Crear:

* billeteras  
* bolsa\_operativa  
* movimientos  
* cashback  
* comisiones  
* reservas  
* retiros  
* recargas

Implementar:

* distribución  
* liquidación  
* liberación

---

# **Fase 6 — Multinivel**

Crear:

* red  
* upliners  
* historial\_red  
* comisiones\_red

Implementar:

* distribución  
* validaciones  
* prevención de ciclos

---

# **Fase 7 — Trust**

Crear:

* trust  
* IPA  
* IPR  
* categorías

Implementar:

* actualización automática  
* historial

---

# **Fase 8 — IMF**

Crear:

* historial IMF  
* liberaciones  
* reglas

Implementar:

* cálculo  
* liberación parcial  
* maduración financiera

---

# **Fase 9 — Antifraude**

Crear:

* eventos\_fraude  
* fingerprints  
* IPs  
* dispositivos  
* riesgo

Implementar:

* motor de detección  
* alertas

---

# **Fase 10 — Auditoría**

Crear:

* logs  
* auditoría  
* reconstrucción histórica

Esta fase deberá cubrir el 100% de las tablas críticas.

---

# **6\. Desarrollo por Fases**

Cada fase seguirá exactamente el mismo proceso.

Crear tablas

↓

Constraints

↓

Foreign Keys

↓

Índices

↓

Funciones

↓

Triggers

↓

RLS

↓

Realtime

↓

Seeds

↓

Testing

↓

Aprobación

Ningún paso podrá omitirse.

---

# **7\. Orden de Desarrollo de Cada Tabla**

Para cada tabla individual:

## **Paso 1**

Diseño lógico.

---

## **Paso 2**

CREATE TABLE.

---

## **Paso 3**

Constraints.

---

## **Paso 4**

Índices.

---

## **Paso 5**

Comentarios.

---

## **Paso 6**

Funciones.

---

## **Paso 7**

Triggers.

---

## **Paso 8**

RLS.

---

## **Paso 9**

Seeds.

---

## **Paso 10**

Pruebas.

---

# **8\. Migraciones**

Toda modificación deberá realizarse mediante migraciones versionadas.

Formato recomendado:

0001\_schema.sql

0002\_catalogos.sql

0003\_core.sql

0004\_operacion.sql

0005\_finanzas.sql

Nunca editar migraciones ya ejecutadas.

Las modificaciones posteriores deberán realizarse mediante nuevas migraciones.

---

# **9\. Datos Semilla (Seeds)**

Los datos iniciales deberán separarse completamente de la estructura.

Ejemplos:

* países  
* ciudades  
* tipos de servicio  
* tipos de vehículo  
* colores  
* parámetros  
* configuraciones  
* estados

Nunca insertar datos de prueba en producción.

---

# **10\. Estrategia de Pruebas**

Cada fase deberá aprobar:

## **Integridad**

* Relaciones.  
* Restricciones.  
* Auditoría.

---

## **Rendimiento**

* Índices.  
* Planes de ejecución.  
* Consultas críticas.

---

## **Seguridad**

* RLS.  
* Permisos.  
* Roles.

---

## **Funcional**

* Funciones.  
* Triggers.  
* Realtime.

---

## **Escalabilidad**

Pruebas con:

* 100 usuarios.  
* 1.000 usuarios.  
* 10.000 usuarios.  
* 100.000 usuarios.  
* 1 millón de registros.

---

# **11\. Política de Versionado**

Cada versión deberá registrar:

* número;  
* fecha;  
* responsable;  
* motivo;  
* dependencias;  
* migraciones aplicadas.

---

# **12\. Integración Continua**

Toda modificación estructural deberá ejecutarse automáticamente en un entorno de pruebas antes de llegar a producción.

No se permitirán cambios manuales en producción.

---

# **13\. Criterios de Aprobación**

Una fase solo podrá aprobarse cuando:

✓ Todas las tablas compilen.

✓ Todas las funciones compilen.

✓ Todos los triggers funcionen.

✓ Todas las políticas RLS funcionen.

✓ Todas las pruebas pasen.

✓ La documentación esté actualizada.

---

# **14\. Estrategia de Despliegue**

Se definen tres entornos independientes.

## **Desarrollo**

Uso diario.

---

## **Preproducción**

Pruebas completas.

---

## **Producción**

Usuarios reales.

Nunca desarrollar directamente sobre Producción.

---

# **15\. Plan de Recuperación**

Cada despliegue deberá incluir:

* copia de seguridad;  
* script de reversión;  
* validación posterior;  
* verificación de integridad.

Toda migración deberá poder revertirse de forma controlada.

---

# **16\. Checklist de Implementación**

Antes de cerrar una fase deberá verificarse:

* Documentación aprobada.  
* Modelo actualizado.  
* SQL validado.  
* Funciones revisadas.  
* Triggers revisados.  
* Índices optimizados.  
* RLS validado.  
* Seeds cargados.  
* Auditoría operativa.  
* Realtime operativo.  
* Casos de prueba ejecutados.  
* Rendimiento aceptable.

---

# **17\. Cronograma Recomendado**

| Etapa | Resultado |
| ----- | ----- |
| Infraestructura | Supabase listo |
| Catálogos | Datos maestros |
| Core | Usuarios operativos |
| Operación | Servicios funcionando |
| Finanzas | Billeteras activas |
| Multinivel | Red funcional |
| Trust | Reputación operativa |
| IMF | Liberaciones automáticas |
| Antifraude | Riesgo controlado |
| Auditoría | Sistema trazable |

Cada etapa constituye un hito verificable y no depende de funcionalidades aún no implementadas.

---

# **18\. Criterios de Evolución**

Ninguna fase podrá modificarse directamente una vez aprobada.

Las mejoras deberán implementarse mediante nuevas migraciones y actualización de la documentación correspondiente.

---

# **19\. Estrategia de Automatización**

Todo el proceso deberá poder ejecutarse de forma automatizada mediante un pipeline que incluya:

* aplicación ordenada de migraciones;  
* carga de datos semilla;  
* ejecución de pruebas unitarias e integración;  
* validación de políticas RLS;  
* verificación de rendimiento;  
* generación de reportes de despliegue.

El objetivo es que una nueva instancia de la base de datos pueda construirse desde cero de forma reproducible y sin intervención manual.

---

# **20\. Principio Rector Final**

> **La base de datos de Tu Mobil Amigo no se construye mediante scripts aislados, sino mediante un proceso controlado, incremental y verificable. Cada fase produce un estado funcional, auditable y desplegable del sistema, garantizando que la evolución tecnológica preserve la integridad del negocio, reduzca el riesgo operativo y permita la incorporación de nuevas capacidades sin comprometer la arquitectura existente.**


Fin de Documento 18A — Plan Maestro de Implementación de la Base de Datos

Documento 19 — Catálogo de Tablas

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir el inventario oficial de tablas del sistema.  
Este documento constituye la fuente de verdad para:  
Backend.  
Flutter.  
Seguridad.  
Reportes.  
Auditoría.  
IA.  
Integraciones.  
Toda nueva tabla deberá incorporarse a este catálogo.

2\. Clasificación General  
Las tablas se agrupan en:  
Núcleo de Usuarios  
Operación  
Finanzas  
Multinivel  
Confianza  
Antifraude  
Configuración  
Auditoría

3\. Núcleo de Usuarios  
usuarios  
Descripción  
Entidad principal del sistema.  
Representa cualquier persona registrada.  
Responsable  
Autenticación.  
Dependencias  
asesores  
dispositivos  (device_registry)
billeteras  
trust\_score  
ipa  
ipr  
imf  
asesores  
Descripción  
Información profesional y documental de los asesores.  
Responsable  
Operación.  
Dependencias  
usuarios  
dispositivos  (device_registry)
Descripción  
Control de equipos autorizados.  
Responsable  
Seguridad.  
Dependencias  
usuarios

4\. Configuración Territorial  
ciudades  
Descripción  
Ciudades habilitadas.  
Responsable  
Administración.  
zonas\_operacion  
Descripción  
Segmentación geográfica.  
Responsable  
Operación.

5\. Catálogos Corporativos  
catalogos  
Descripción  
Catálogos maestros reutilizables.  
Responsable  
Arquitectura.  
catalogo\_detalles  
Descripción  
Valores parametrizados.  
Responsable  
Arquitectura.  
Ejemplos:  
ESTADOS\_SERVICIO  
TIPOS\_SERVICIO  
TIPOS\_NOTIFICACION  
PARAMETROS\_TARIFARIOS  
PARAMETROS\_IMF  
PARAMETROS\_TRUST

6\. Motor Tarifario  
parametros\_tarifarios  
Descripción  
Almacena parámetros configurables por ciudad.  
Responsable  
Motor Tarifario.  
Ejemplos:  
valor\_banderazo  
valor\_km  
valor\_minuto  
factor\_moto  
factor\_taxi  
recargo\_nocturno  
recargo\_festivo  
Regla Arquitectónica  
Toda variable tarifaria  
debe existir como registro.  
Nunca como columna.

7\. Operación  
servicios  
Descripción  
Tabla principal del negocio.  
Responsable  
Motor Operativo.  
Modalidades:  
INMEDIATO  
PROGRAMADO  
QR

Estados:  
CREADO  
OFERTADO  
NEGOCIANDO  
ACEPTADO  
EN\_CURSO  
FINALIZADO  
CANCELADO

ofertas  
Descripción  
Ofertas económicas emitidas.  
Responsable  
Motor de Negociación.  
Regla:  
Expiración inicial:  
180 segundos  
Configurable desde BD.  
contraofertas  
Descripción  
Contraofertas emitidas por asesores.  
Responsable  
Motor de Negociación.  
Regla:  
Una única contraoferta  
por cliente.  
Regla:  
Expiran con el mismo tiempo  
de las ofertas.  
qr\_clientes  
Descripción  
Identificador QR único del cliente.  
Responsable  
Operación.

Objetivos:  
Servicios QR  
Validación cliente  
Trazabilidad

8\. Finanzas  
billeteras  
Descripción  
Almacena saldos de usuarios.  
Responsable  
Motor Financiero.  
Tipos:  
OPERATIVA  
BENEFICIOS  
Regla Operativa  
La billetera operativa:  
Recibe recargas.  
Paga comisiones.  
No participa en IMF.  
La billetera de beneficios:  
Cashback.  
Comisiones multinivel.  
Incentivos QR.  
Participa en IMF.  
movimientos\_financieros

Descripción  
Libro contable oficial.  
Responsable  
Motor Financiero.

Tipos:  
RECARGA  
COMISION  
CASHBACK  
LIBERACION  
RETIRO  
INCENTIVO\_QR  
AJUSTE

9\. Cashback  
cashback  
Descripción  
Beneficios generados por servicios.  
Responsable  
Motor Financiero.  
Distribución estándar:  
15% Comisión Operativa  
│  
├── Empresa .......... 30%  
├── Cashback ......... 30%  
├── Upliner 1 ........ 20%  
├── Upliner 2 ........ 10%  
└── Fondo Reserva .... 10%

Servicios programados:  
Empresa .......... 25%  
Cashback ......... 35%

El incremento del 5% se financia desde la participación de la empresa.

10\. Multinivel  
red\_multinivel  
Descripción  
Relación genealógica.  
Responsable  
Motor Multinivel.  
Profundidad máxima:  
Nivel 1  
Nivel 2  
comisiones  
Descripción  
Comisiones generadas por red.  
Responsable  
Motor Multinivel.  
Estados:  
GENERADA  
MADURANDO  
LIBERADA  
PAGADA

11\. Incentivos QR  
incentivos\_qr  
Descripción  
Beneficio otorgado a asesores por registrar servicios realizados fuera de la plataforma.  
Responsable  
Motor Financiero.  
Regla:  
El incentivo se financia desde la participación de la empresa.  
Participa en IMF.

12\. Confianza  
trust\_score  
Descripción  
Nivel de confianza del usuario.  
Responsable  
Motor de Confianza.

Escala:  
0 \- 100  
Categorías:  
Explorador  
Viajero  
Experto  
Leyenda  
ipa

Descripción  
Índice de Participación Activa.  
Responsable  
Motor de Confianza.  
Evalúa:  
Servicios  
Actividad  
Uso del sistema  
ipr

Descripción  
Índice de Participación en Red.  
Responsable  
Motor de Confianza.  
Evalúa:  
Referidos activos  
Actividad de red  
imf  
Descripción  
Índice de Maduración Financiera.  
Responsable  
Motor Financiero.  
Factores:  
Antigüedad  
Trust Score  
IPA  
IPR

13\. Antifraude  
eventos\_antifraude  
Descripción  
Registro de anomalías detectadas.  
Responsable  
Motor Antifraude.  
Ejemplos:  
Autorreferencia  
Múltiples dispositivos  
Patrones sospechosos  
Manipulación de servicios  
Abuso cashback  
Abuso multinivel

14\. Auditoría  
auditoria  
Descripción  
Bitácora corporativa.  
Responsable  
Auditoría.  
Regla:  
Nada se elimina.  
Todo se registra.

15\. Notificaciones  
notificaciones  
Descripción  
Mensajería interna.  
Responsable  
Comunicaciones.  
Canales futuros:  
Push  
Telegram  
Email  
SMS

16\. Integraciones  
integraciones\_externas  
Descripción  
Control de conexiones externas.  
Responsable  
Backend.  
Integraciones previstas:  
Telegram  
OpenStreetMap  
Leaflet (Flutter/Web)  
Nominatim (Geocoding)  
GraphHopper u OSRM (Rutas)  
PSE  
Pasarela de pagos  
Siigo  
Banco Empresarial

17\. Resumen Ejecutivo  
Dominio		Cantidad  
Usuarios	3  
Operación	4  
Finanzas	3  
Multinivel	2  
Confianza	4  
Antifraude	1  
Auditoría	1  
Integraciones	1  
Configuración	4

18\. Principio Rector Final

Toda tabla deberá tener:

Propósito claro.  
Responsable definido.  
Trazabilidad.  
Relación con una necesidad real del negocio.

Se prohíbe la creación de tablas sin justificación funcional documentada.

# **Integración Contable Futura**

Todos los procesos financieros deberán diseñarse de forma que puedan ser exportados a sistemas ERP externos.

Entre ellos:

* liquidaciones;  
* pagos;  
* cashback;  
* multinivel;  
* incentivos;  
* ajustes contables;  
* conciliaciones.

# **tipo\_liquidacion**

ORDINARIA  
EXTRAORDINARIA

y además:

motivo  
ejecutado\_por  
fecha\_ejecucion

## **Tabla: device\_registry**

### **Propósito**

Registrar y monitorear los dispositivos utilizados por los usuarios del ecosistema Tu Mobil Amigo.

Constituye una de las principales fuentes de información para:

* Motor Antifraude.  
* Trust Score.  
* Gestión de Dispositivos.  
* Ciberseguridad.  
* Auditoría.

---

### **Relaciones**

usuarios  
    │  
    └── device\_registry

Relación:

1 usuario  
N dispositivos  
---

### **Campos relevantes**

| Campo | Descripción |
| ----- | ----- |
| fingerprint | Identificador único lógico del dispositivo |
| device\_trust\_score | Puntaje interno de confianza |
| estado | Estado operativo del dispositivo |
| reputacion | Clasificación de riesgo |
| vpn\_detectado | Detección de VPN |
| proxy\_detectado | Detección de Proxy |
| tor\_detectado | Detección de red TOR |
| datacenter\_ip | Uso de IP de datacenter |
| cantidad\_alertas | Alertas acumuladas |
| cantidad\_bloqueos | Bloqueos históricos |

---

### **Reglas de negocio**

#### **RN-DR-001**

Todo acceso autenticado deberá asociarse a un dispositivo registrado.

---

#### **RN-DR-002**

El sistema podrá registrar múltiples dispositivos por usuario.

El límite será configurable desde Base de Datos.

---

#### **RN-DR-003**

Un mismo dispositivo podrá asociarse a múltiples usuarios únicamente cuando las reglas antifraude lo permitan.

---

#### **RN-DR-004**

Cambios frecuentes de dispositivo podrán generar eventos de riesgo.

---

#### **RN-DR-005**

La detección de VPN, Proxy, TOR o IPs de Datacenter incrementará el riesgo antifraude.

---

#### **RN-DR-006**

Los dispositivos bloqueados no podrán operar dentro del ecosistema.

---

#### **RN-DR-007**

Los dispositivos podrán afectar indirectamente:

Trust Score  
Elegibilidad operativa  
Validaciones de seguridad  
Controles antifraude  
---

### **Integraciones**

Consumido por:

Documento 13 — Trust Score
Documento 15 — Motor Antifraude
Documento 32 — Ciberseguridad
Documento 34 — Gestión de Dispositivos

Tabla: roles
Propósito: Catálogo de niveles de privilegio del sistema (Cliente, Asesor, Administrador, Superadministrador).
Responsable: Seguridad / Backend.
Consumido por: Documento 28 (RBAC), Documento 03, Documento 35 (Auditoría).

Tabla: permisos
Propósito: Catálogo de capacidades granulares del sistema, organizadas por dominio (ver DA-034).
Responsable: Seguridad / Backend.

Tabla: roles_permisos
Propósito: Asociación N:N entre roles y permisos.

Tabla: usuarios_roles
Propósito: Asignación de rol(es) a cada usuario, con trazabilidad de quién asignó el rol y cuándo.
Reglas de negocio:
RN-UR-001: Solo un Superadministrador podrá asignar el rol Administrador o Superadministrador a otro usuario.
RN-UR-002: Toda asignación o revocación de rol deberá generar evento de auditoría (ver Documento 21 — Catálogo de Triggers).

Fin del Documento 19 — Catálogo de Tablas

Documento 20 — Catálogo de Funciones

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

1\. Objetivo  
Definir las funciones almacenadas (Stored Procedures y Functions) autorizadas dentro de PostgreSQL/Supabase.  
Las funciones constituyen la capa de negocio crítica ejecutada dentro de la base de datos.

2\. Principios Generales  
CF-001  
Toda lógica crítica financiera deberá ejecutarse en Base de Datos.

CF-002  
Ningún cálculo económico dependerá exclusivamente del frontend.

CF-003  
Las funciones deberán ser determinísticas y auditables.

CF-004  
Toda función financiera deberá generar trazabilidad.

3\. Motor Tarifario  
calcular\_tarifa()  
Objetivo  
Calcular valor sugerido del servicio.

Entradas  
ciudad\_id  
tipo\_servicio  
distancia\_km  
duracion\_minutos  
Salidas  
valor\_sugerido  
valor\_piso  
valor\_techo

Reglas  
Parámetros obtenidos desde BD.  
Sin valores hardcodeados.  
Redondeo superior múltiplo de 200\.

Ejemplos:  
5001 → 5200  
5199 → 5200  
5200 → 5200

obtener\_parametro\_tarifario()  
Objetivo  
Consultar parámetros vigentes.

Entradas  
ciudad\_id  
codigo\_parametro  
Salidas  
valor

4\. Motor de Negociación  
validar\_rango\_negociacion()  
Objetivo  
Verificar límites de negociación.

Entradas  
usuario\_id  
valor\_sugerido  
valor\_ofertado

Salidas  
permitido  
porcentaje\_utilizado

Reglas  
Depende de Trust Score.  
Depende de IPA.  
Depende de IPR.

Respeta límites máximos definidos.  
crear\_oferta()  
Objetivo

Crear oferta inicial.  
crear\_contraoferta()

Objetivo  
Crear contraoferta de asesor.

Reglas  
Máximo una contraoferta por cliente.  
cerrar\_negociacion()

Objetivo  
Finalizar negociación.  
Resultado  
ACEPTADA  
RECHAZADA  
EXPIRADA

5\. Operación  
crear\_servicio()  
Objetivo  
Crear solicitud.  
programar\_servicio()

Reglas  
Mínimo 2 horas.  
Máximo 12 horas.  
asignar\_asesor()

Objetivo  
Asignación final.  
finalizar\_servicio()

Objetivo  
Cerrar operación.  
Procesos asociados  
Comisión.  
Cashback.  
Multinivel.  
IMF.  
Auditoría.

6\. Servicios QR  
validar\_qr\_cliente()

Objetivo  
Validar identidad.  
registrar\_servicio\_qr()

Objetivo  
Registrar servicio realizado fuera de plataforma.

Validaciones  
Cliente válido.  
Asesor válido.  
No autorreferencia.  
otorgar\_incentivo\_qr()

Objetivo  
Asignar incentivo financiero QR.  
Fuente  
Participación Empresa.

7\. Billeteras  
crear\_billetera()  
Objetivo  
Crear billeteras iniciales.  
recargar\_billetera\_operativa()  
Objetivo  
Ingresar fondos.  
validar\_saldo\_operativo()  
Regla  
Saldo mínimo:  
5.000 COP  
Resultado  
Puede recibir servicios  
No puede recibir servicios  
debitar\_comision\_servicio()  
Objetivo  
Descontar comisión al asesor.  
liberar\_beneficios()  
Objetivo  
Liberar beneficios IMF.

8\. Cashback  
calcular\_cashback()  
Distribución estándar  
15% Comisión Operativa

Empresa .......... 30%  
Cliente .......... 30%  
Upliner 1 ........ 20%  
Upliner 2 ........ 10%  
Reserva .......... 10%

calcular\_cashback\_programado()  
Distribución  
Empresa .......... 25%  
Cliente .......... 35%  
Upliner 1 ........ 20%  
Upliner 2 ........ 10%  
Reserva .......... 10%

9\. Multinivel  
generar\_comisiones\_red()  
Objetivo  
Generar comisiones.  
validar\_upliner()  
Objetivo  
Validar estructura.  
calcular\_ipr()  
Objetivo  
Actualizar IPR.

10\. Trust Score  
actualizar\_trust\_score()  
Factores  
Servicios.  
Calificaciones.  
Fraude.  
Antigüedad.  
calcular\_categoria\_usuario()  
Resultado  
Explorador  
Viajero  
Experto  
Leyenda

11\. IPA  
calcular\_ipa()  
Factores  
Servicios.  
Actividad.  
Uso mensual.

12\. IMF  
calcular\_imf()  
Factores  
Antigüedad.  
Trust Score.  
IPA.  
IPR.  
Actividad mínima.  
validar\_liberacion\_imf()  
Objetivo  
Determinar porcentaje liberable.

13\. Antifraude  
detectar\_autorreferencia()  
Objetivo  
Evitar:  
Cliente \= Asesor  
detectar\_patrones\_sospechosos()  
Evalúa  
Servicios repetitivos.  
Abuso QR.  
Abuso Cashback.  
Abuso Multinivel.  
registrar\_evento\_antifraude()  
Objetivo  
Crear incidente.

14\. Auditoría  
registrar\_auditoria()  
Objetivo  
Registrar eventos críticos.  
consultar\_historial()  
Objetivo  
Trazabilidad completa.

15\. Administración  
activar\_usuario()  
suspender\_usuario()  
bloquear\_usuario()  
aprobar\_recarga()  
aprobar\_retiro()

## **Nuevas Funciones**

### **generar\_cierre\_mensual()**

Genera el cierre oficial del período.

---

### **generar\_liquidaciones()**

Genera las liquidaciones individuales.

---

### **fn\_generar\_excel\_liquidacion()**

Genera el reporte corporativo en Excel.

---

### **confirmar\_pago\_liquidacion()**

Registra la confirmación de pago.

---

### **registrar\_ajuste\_contable()**

Registra correcciones posteriores al cierre.

**generar\_liquidacion\_manual()** 

**generar\_liquidacion\_preview()** 

**aprobar\_liquidacion()** 

**ejecutar\_liquidacion()** 

**generar\_liquidacion\_preview()** 

**aprobar\_liquidacion()** 

**ejecutar\_liquidacion()** 

**registrar\_pago\_liquidacion()** 

**anular\_liquidacion()** 

fn_usuario_tiene_permiso(id_usuario, codigo_permiso) → boolean
Verifica si un usuario posee, mediante su(s) rol(es) asignado(s), el permiso solicitado. Debe usarse como base de las políticas RLS de tablas sensibles (financieras, configuración global, motores).

fn_asignar_rol(id_usuario, id_rol, asignado_por) → void
Encapsula la Regla RN-UR-001; rechaza la operación si `asignado_por` no tiene rol Superadministrador cuando el rol a asignar es Administrador o Superadministrador.

16\. Principio Rector Final  
Toda función deberá existir porque resuelve  
una regla de negocio claramente identificada.

Se prohíbe crear funciones sin trazabilidad,  
sin auditoría o sin un propósito operativo definido.

Fin del Documento 20 — Catálogo de Funciones.

# **Documento 21 — Catálogo de Triggers**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Definir el catálogo oficial de triggers de la base de datos, estableciendo su finalidad, eventos asociados y responsabilidades.

Los triggers tienen como misión garantizar la consistencia automática del sistema, la trazabilidad de las operaciones y la sincronización entre los diferentes dominios del negocio.

---

# **2\. Principios**

## **CT-001**

Los triggers no contienen reglas de negocio.

Toda lógica será ejecutada mediante funciones documentadas en el Documento 20\.

---

## **CT-002**

Cada trigger tendrá una única responsabilidad.

---

## **CT-003**

Los triggers nunca modificarán directamente múltiples dominios.

Si una operación afecta varios dominios, invocará la función correspondiente.

---

## **CT-004**

Todo trigger deberá ser idempotente.

Ejecutarlo dos veces nunca deberá generar resultados distintos.

---

## **CT-005**

Los triggers deberán ejecutarse dentro de transacciones.

---

# **3\. Clasificación**

Los triggers quedan agrupados por dominio.

Core

Operación

Finanzas

Trust

Seguridad

Configuración

Auditoría  
---

# **4\. Triggers del Dominio Core**

## **trg\_usuario\_creado**

Evento

AFTER INSERT

Tabla

core.usuarios

Responsabilidades

* Crear perfil inicial.  
* Crear QR.  
* Crear billeteras.  
* Inicializar Trust.  
* Inicializar IPA.  
* Inicializar IPR.  
* Inicializar IMF.  
* Registrar auditoría.

Función ejecutada

fn\_registrar\_usuario()  
---

## **trg\_documento\_actualizado**

Evento

AFTER UPDATE

Tabla

usuarios\_documentos

Responsabilidad

Revalidar documentación.

---

## **trg\_dispositivo\_registrado**

Evento

AFTER INSERT

Acciones

* Validar fingerprint.  
* Detectar duplicados.  
* Registrar auditoría.

---

# **5\. Triggers del Dominio Operación**

## **trg\_servicio\_creado**

Evento

AFTER INSERT

Tabla

servicios

Responsabilidades

* Validar servicio.  
* Publicar ofertas.  
* Registrar auditoría.

---

## **trg\_servicio\_programado**

Evento

AFTER INSERT

Tabla

servicios\_programados

Acciones

* Validar ventana de 2 a 12 horas.  
* Registrar incentivo financiero.  
* Programar publicación automática.

---

## **trg\_oferta\_creada**

Evento

AFTER INSERT

Acciones

* Programar expiración.  
* Registrar evento.

---

## **trg\_contraoferta\_creada**

Acciones

* Validar expiración.  
* Registrar historial.

---

## **trg\_servicio\_finalizado**

Este es uno de los triggers más importantes.

Evento

AFTER UPDATE

Condición

Estado:

FINALIZADO

Acciones

Invocar

fn\_finalizar\_servicio()

La función realizará:

* Liquidación financiera.  
* Descuento de Bolsa Operativa.  
* Distribución de comisiones.  
* Generación de Cashback.  
* Actualización Trust.  
* Actualización IPA.  
* Actualización IPR.  
* Actualización IMF.  
* Actualización Categoría.  
* Auditoría.

---

# **6\. Triggers del Dominio Finanzas**

## **trg\_movimiento\_financiero**

Evento

AFTER INSERT

Tabla

movimientos\_billetera

Acciones

* Actualizar saldo.  
* Validar consistencia.  
* Registrar auditoría.

---

## **trg\_recarga\_confirmada**

Condición

Estado:

APROBADA

Acciones

* Actualizar Bolsa Operativa.  
* Registrar movimiento.  
* Notificar usuario.

---

## **trg\_retiro\_aprobado**

Acciones

* Debitar billetera.  
* Registrar movimiento.  
* Registrar auditoría.

---

## **trg\_cashback\_generado**

Acciones

* Crear registro de Cashback Ganado.  
* Programar liberación.

---

## **trg\_cashback\_liberado**

Acciones

* Trasladar a Cashback Liberado.  
* Registrar histórico.

---

# **7\. Triggers del Dominio Trust**

## **trg\_calificacion\_insertada**

Evento

AFTER INSERT

Tabla

calificaciones

Acciones

* Recalcular Trust.  
* Recalcular IPA.  
* Recalcular Categoría.

---

## **trg\_servicio\_qr\_registrado**

Acciones

* Actualizar IPA.  
* Actualizar IMF.

---

## **trg\_red\_actualizada**

Acciones

* Recalcular IPR.

---

# **8\. Triggers del Dominio Seguridad**

## **trg\_login**

Acciones

* Registrar dispositivo.  
* Registrar IP.  
* Evaluar riesgo.

---

## **trg\_evento\_antifraude**

Acciones

* Calcular nivel de riesgo.  
* Generar alertas.  
* Registrar auditoría.

---

## **trg\_qr\_utilizado**

Acciones

Validar

UUID Cliente ≠ UUID Asesor

Si son iguales:

* Cancelar operación.  
* Registrar fraude.  
* Notificar.

---

# **9\. Triggers del Dominio Configuración**

## **trg\_variable\_tarifaria**

Evento

AFTER INSERT

Acciones

* Crear nueva versión.  
* Registrar histórico.

---

## **trg\_decreto**

Acciones

* Versionar parámetros.  
* Mantener histórico.

---

# **10\. Triggers del Dominio Auditoría**

## **trg\_auditoria\_global**

Todas las tablas críticas tendrán un trigger común.

Eventos

INSERT

UPDATE

DELETE (Soft Delete)

Información registrada

* Usuario.  
* Fecha.  
* IP.  
* Dispositivo.  
* Valores anteriores.  
* Valores nuevos.

---

## **trg\_error**

Registra excepciones críticas.

---

# **11\. Flujo General**

Usuario

↓

Flutter / React / Telegram

↓

Edge Function

↓

Función PostgreSQL

↓

INSERT / UPDATE

↓

Trigger

↓

Auditoría

↓

Realtime

↓

Clientes conectados  
---

# **12\. Integración con Realtime**

Los triggers podrán publicar eventos hacia Supabase Realtime únicamente para:

* Nuevos servicios.  
* Cambios de estado.  
* Asignaciones.  
* Mensajes.  
* Notificaciones.  
* Cambios en Bolsa Operativa.  
* Actualizaciones de Cashback.  
* Alertas críticas.

No deberán emitir eventos para cambios internos que no aporten valor a los clientes conectados.

---

# **13\. Restricciones**

Queda prohibido que un trigger:

* Llame directamente a otro trigger.  
* Modifique múltiples dominios sin pasar por funciones.  
* Contenga consultas complejas de negocio.  
* Realice cálculos financieros.  
* Calcule tarifas.  
* Calcule Trust Score.  
* Tome decisiones operativas.

Todas esas responsabilidades pertenecen exclusivamente a las funciones del Documento 20\.

---

# **14\. Monitorización**

Todos los triggers deberán registrar:

* Tiempo de ejecución.  
* Resultado.  
* Errores.  
* Número de registros afectados.

Estos indicadores permitirán identificar cuellos de botella y optimizar el rendimiento de la base de datos.

---

# **15\. Política de Evolución**

Antes de crear un nuevo trigger se deberá verificar si la funcionalidad puede incorporarse a uno existente mediante una nueva función especializada.

El objetivo es mantener un conjunto reducido de triggers, cada uno claramente identificado y con una responsabilidad específica.

---

## **Nuevos Triggers**

### **trg\_generar\_cierre\_mensual**

# Ejecuta el proceso de cierre.

# ---

### **trg\_generar\_liquidacion**

# Genera las liquidaciones correspondientes.

# ---

### **trg\_actualizar\_estado\_pago**

# Actualiza estados posteriores al pago.

trg\_liquidacion\_aprobada

trg\_liquidacion\_ejecutada

trg\_liquidacion\_pagada

trg_auditar_asignacion_rol
Se dispara en cada INSERT/DELETE sobre usuarios_roles.
Genera registro obligatorio en la tabla de auditoría (ver Documento 35) con: usuario afectado, rol, quién ejecutó el cambio, timestamp.

# **16\. Principio Rector Final**

> **Los triggers de Tu Mobil Amigo representan el mecanismo automático de sincronización entre dominios, no el lugar donde reside la lógica del negocio. Toda decisión funcional deberá implementarse mediante funciones especializadas, mientras que los triggers actuarán únicamente como detectores de eventos y orquestadores de la ejecución.**

Fin de Documento 21 — Catálogo de Triggers

# **Anexo A — Estándares SQL y Convenciones de Desarrollo**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Establecer los estándares oficiales para el desarrollo de la base de datos de Tu Mobil Amigo, garantizando uniformidad, mantenibilidad, rendimiento y seguridad durante todo el ciclo de vida del proyecto.

Este documento es de obligatorio cumplimiento para cualquier modificación realizada sobre PostgreSQL/Supabase.

---

# **2\. Principios Generales**

Toda implementación deberá cumplir los siguientes principios:

* Simplicidad.  
* Legibilidad.  
* Modularidad.  
* Reutilización.  
* Escalabilidad.  
* Trazabilidad.  
* Parametrización.  
* Seguridad.

---

# **3\. Convenciones de Nombres**

## **3.1 Tablas**

Siempre:

* minúsculas  
* snake\_case  
* plural

Ejemplos

usuarios

servicios

movimientos\_billetera

variables\_tarifarias  
---

## **3.2 Columnas**

Siempre:

snake\_case

Ejemplos

usuario\_id

created\_at

trust\_score

cashback\_liberado  
---

## **3.3 Claves Primarias**

Siempre

id UUID

Nunca

id SERIAL  
---

## **3.4 Claves Foráneas**

Formato

tabla\_id

Ejemplos

usuario\_id

servicio\_id

vehiculo\_id

ciudad\_id  
---

# **4\. Convención de Objetos SQL**

## **Funciones**

Prefijo

fn\_

Ejemplo

fn\_calcular\_tarifa()

fn\_finalizar\_servicio()  
---

## **Procedimientos**

sp\_  
---

## **Triggers**

trg\_  
---

## **Índices**

idx\_  
---

## **Constraints**

ck\_  
---

## **Foreign Keys**

fk\_  
---

## **Unique**

uq\_  
---

## **Views**

vw\_  
---

## **Materialized Views**

mv\_  
---

# **5\. Estándar para Funciones**

Toda función deberá contener:

* Objetivo.  
* Parámetros.  
* Valor de retorno.  
* Excepciones.  
* Dependencias.  
* Registro de auditoría cuando aplique.

---

Ejemplo

fn\_calcular\_tarifa()

Entrada:  
    ciudad\_id  
    tipo\_servicio  
    distancia

Salida:  
    valor\_total  
---

# **6\. Estándar de Transacciones**

Toda operación crítica utilizará transacciones.

Ejemplo

BEGIN

↓

Validaciones

↓

Operación

↓

Auditoría

↓

COMMIT

En caso de error

ROLLBACK

obligatorio.

---

# **7\. Manejo de Errores**

Nunca utilizar errores genéricos.

Cada excepción deberá poseer:

* Código.  
* Mensaje.  
* Severidad.  
* Fecha.  
* Usuario.  
* Función.  
* Parámetros.

---

Ejemplo

ERR-TRUST-001

Trust insuficiente.  
---

# **8\. Política de Soft Delete**

Queda prohibido eliminar registros críticos.

Toda eliminación utilizará:

activo

deleted\_at

deleted\_by  
---

# **9\. Política de Auditoría**

Toda operación deberá registrar:

* usuario  
* fecha  
* IP  
* dispositivo  
* función  
* valores anteriores  
* valores nuevos

---

# **10\. Uso de JSONB**

JSONB únicamente podrá utilizarse cuando:

* la estructura sea dinámica;  
* no sea posible modelarla relacionalmente;  
* exista una justificación documentada.

Nunca utilizar JSONB para reemplazar un modelo relacional correctamente diseñado.

---

# **11\. Versionamiento**

Toda configuración deberá permitir:

vigente\_desde

vigente\_hasta

version

estado

Nunca sobrescribir registros históricos.

---

# **12\. Índices**

Se crearán índices únicamente sobre:

* UUID.  
* Foreign Keys.  
* Fechas.  
* Estados.  
* Campos de búsqueda frecuente.

Antes de crear un nuevo índice deberá verificarse su impacto mediante análisis del plan de ejecución.

---

# **13\. Optimización de Consultas**

Toda consulta crítica deberá analizarse utilizando:

EXPLAIN ANALYZE

No se aprobarán consultas con recorridos completos de tablas (Full Table Scan) cuando exista una alternativa eficiente mediante índices o rediseño.

---

# **14\. Política de Parametrización**

Queda prohibido escribir valores fijos en funciones o procedimientos.

Ejemplos prohibidos:

180 segundos

5000 COP

15 %

2 horas

12 horas

Estos valores deberán obtenerse desde las tablas de configuración.

---

# **15\. Seguridad (RLS)**

Toda tabla deberá implementar Row Level Security (RLS).

Las políticas deberán seguir el principio de mínimo privilegio.

Cada usuario solo podrá acceder a la información estrictamente necesaria para su rol.

---

# **16\. Uso de Edge Functions**

Flutter, React y Telegram no accederán directamente a operaciones críticas.

El flujo oficial será:

Cliente

↓

Edge Function

↓

Función PostgreSQL

↓

Respuesta  
---

# **17\. Política de Migraciones**

Toda modificación estructural deberá realizarse mediante scripts versionados.

Cada migración deberá ser:

* incremental;  
* reversible cuando sea posible;  
* identificable mediante versión;  
* documentada.

Queda prohibido modificar la estructura manualmente en producción.

---

# **18\. Gestión de Rendimiento**

Se deberán monitorizar periódicamente:

* tiempo medio de ejecución de funciones;  
* consultas lentas;  
* uso de índices;  
* bloqueos;  
* consumo de CPU;  
* consumo de memoria;  
* crecimiento de tablas.

---

# **19\. Gestión de Bloqueos**

Las transacciones deberán mantenerse abiertas el menor tiempo posible.

Se evitarán:

* bloqueos innecesarios;  
* transacciones largas;  
* esperas activas;  
* actualizaciones masivas sin segmentación.

---

# **20\. Integridad Referencial**

Toda relación entre entidades deberá implementarse mediante claves foráneas.

Solo podrán omitirse cuando exista una justificación técnica documentada y aprobada.

---

# **21\. Escalabilidad**

La estructura deberá permitir incorporar:

* nuevas ciudades;  
* nuevos países;  
* nuevas monedas;  
* nuevos idiomas;  
* nuevos métodos de pago;  
* nuevos servicios;  
* nuevos tipos de vehículos;  
* nuevos motores de incentivos;  
* nuevos proveedores cartográficos.

Sin rediseñar el modelo existente.

---

# **22\. Política de Documentación**

Toda función, trigger o procedimiento deberá mantenerse sincronizado con los documentos oficiales del proyecto.

No se permitirá código sin documentación.

---

# **23\. Revisión de Código**

Toda modificación deberá verificar, como mínimo:

* cumplimiento de nomenclatura;  
* rendimiento;  
* seguridad;  
* integridad referencial;  
* compatibilidad con RLS;  
* cumplimiento de la arquitectura por dominios;  
* ausencia de lógica de negocio en interfaces cliente.

---

# **24\. Arquitectura de Base de Datos**

La base de datos deberá seguir el siguiente flujo de responsabilidades:

Flutter / React / Telegram  
            │  
            ▼  
      Edge Functions  
            │  
            ▼  
    Funciones PostgreSQL  
            │  
            ▼  
        Triggers  
            │  
            ▼  
      Auditoría / Realtime

Ninguna capa superior podrá omitir las capas inferiores para ejecutar operaciones críticas.

---

# **25\. Principio Rector Final**

> **La base de datos de Tu Mobil Amigo constituye el núcleo transaccional y normativo del sistema. Toda implementación deberá priorizar la integridad, la trazabilidad y la parametrización sobre la rapidez de desarrollo, garantizando que el crecimiento futuro del proyecto se produzca mediante evolución controlada y no mediante refactorizaciones disruptivas.**

 Fin de Anexo A — Estándares SQL y Convenciones de Desarrollo

 # **Anexo B — Guía de Modelado de Nuevas Entidades**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Establecer los criterios oficiales para diseñar nuevas entidades, relaciones, funciones y procesos dentro de Tu Mobil Amigo, garantizando que la arquitectura evolucione de forma consistente sin comprometer la estabilidad del sistema.

Este anexo complementa los Documentos 16 al 21A y será de cumplimiento obligatorio para cualquier ampliación futura.

---

# **2\. Principio Rector**

Antes de crear cualquier elemento nuevo deberá responderse la siguiente pregunta:

> **¿Realmente es necesario crear algo nuevo o la arquitectura actual ya puede resolver el problema mediante parametrización o reutilización?**

La creación de nuevas entidades será siempre la última alternativa.

---

# **3\. Árbol de Decisión**

Todo desarrollo seguirá el siguiente flujo:

Nueva necesidad

        │  
        ▼

¿Puede resolverse modificando un parámetro?

        │

   Sí ─────────► Modificar parámetro

        │

        No

        ▼

¿Puede resolverse creando un registro?

        │

   Sí ─────────► Crear registro

        │

        No

        ▼

¿Puede resolverse mediante una nueva relación?

        │

   Sí ─────────► Crear relación

        │

        No

        ▼

¿Puede resolverse mediante una función?

        │

   Sí ─────────► Crear función

        │

        No

        ▼

¿Puede resolverse creando una nueva entidad?

        │

   Sí ─────────► Nueva tabla

        │

        No

        ▼

Replantear el diseño  
---

# **4\. ¿Cuándo crear una nueva tabla?**

Una tabla nueva solo podrá crearse cuando represente un concepto completamente independiente.

Debe cumplir las siguientes condiciones:

* posee identidad propia;  
* tiene ciclo de vida independiente;  
* requiere auditoría propia;  
* posee relaciones propias;  
* evolucionará de forma independiente.

Ejemplo correcto

Servicios

Vehículos

Billeteras

Cashback

Comisiones

Ejemplo incorrecto

Crear una tabla únicamente para almacenar:

Color del botón

Tiempo de espera

Porcentaje

Configuración

Esto pertenece a parámetros.

---

# **5\. ¿Cuándo crear una tabla de parámetros?**

Siempre que el dato pueda cambiar sin alterar la lógica del negocio.

Ejemplos:

✔ correcto

Tiempo máximo oferta

Saldo mínimo

Porcentaje Empresa

Porcentaje Cashback

Tiempo Programación

Ventana de negociación

Trust mínimo

IMF mínimo

Incorrecto

Tarifa fija escrita en código  
---

# **6\. ¿Cuándo reutilizar una entidad?**

Siempre que el nuevo requerimiento represente una especialización del concepto existente.

Ejemplo

Ya existe

servicios

No crear

servicios\_moto

servicios\_taxi

servicios\_mensajeria

Debe existir

tipos\_servicio

como catálogo.

---

# **7\. ¿Cuándo versionar una entidad?**

Cuando el cambio de información deba conservar el histórico.

Ejemplos:

Variables tarifarias.

Decretos.

Configuraciones.

Porcentajes.

Trust.

IMF.

Nunca sobrescribir información histórica.

---

# **8\. ¿Cuándo crear una función?**

Cuando exista una regla de negocio reutilizable.

Ejemplos:

Calcular tarifa.

Liberar Cashback.

Validar QR.

Actualizar Trust.

Distribuir comisiones.

Calcular IMF.

Nunca crear funciones para operaciones triviales como consultas simples.

---

# **9\. ¿Cuándo crear una Edge Function?**

Las Edge Functions deberán utilizarse cuando sea necesario:

* interactuar con servicios externos;  
* proteger claves privadas;  
* coordinar procesos entre varios motores;  
* exponer una API segura a Flutter o React.

Ejemplos:

* Telegram.  
* PSE.  
* OpenStreetMap.  
* GraphHopper.  
* Notificaciones Push.

---

# **10\. ¿Cuándo usar PostgreSQL directamente?**

Las funciones PostgreSQL deberán concentrar toda regla crítica del negocio.

Ejemplos:

* cálculo financiero;  
* trust score;  
* motor tarifario;  
* liberación de cashback;  
* distribución multinivel;  
* antifraude.

---

# **11\. ¿Cuándo usar Flutter?**

Flutter únicamente será responsable de:

* presentar información;  
* capturar datos;  
* gestionar navegación;  
* validar formularios básicos;  
* consumir APIs.

Nunca contendrá reglas financieras, tarifarias o de seguridad.

---

# **12\. ¿Cuándo usar React?**

El Panel Administrativo en React será responsable de:

* gestión administrativa;  
* monitoreo;  
* reportes;  
* parametrización;  
* auditoría;  
* aprobación de procesos.

No implementará lógica de negocio distinta a la interfaz.

---

# **13\. ¿Cómo elegir el dominio correcto?**

Antes de crear una entidad deberá identificarse el dominio al que pertenece.

| Si representa... | Dominio |
| ----- | ----- |
| Personas, roles, vehículos | Core |
| Servicios y ofertas | Operations |
| Dinero y movimientos | Finance |
| Tarifas y ciudades | Pricing |
| Trust, IPA, IPR, IMF | Trust |
| Fraude y dispositivos | Security |
| Parámetros | Configuration |
| APIs externas | Integration |
| Auditoría | Audit |
| Administración | Admin |

Una entidad no podrá pertenecer simultáneamente a dos dominios.

---

# **14\. ¿Cuándo crear una nueva billetera?**

Solo cuando represente dinero con reglas de negocio completamente distintas.

Ejemplos válidos

* Bolsa Operativa.  
* Cashback.  
* Comisiones Multinivel.

No crear billeteras únicamente para separar saldos visualmente.

---

# **15\. ¿Cuándo crear una nueva métrica?**

Una métrica nueva deberá cumplir:

* objetivo claramente definido;  
* fórmula documentada;  
* impacto operativo;  
* actualización automática;  
* utilidad para la toma de decisiones.

No se crearán métricas únicamente por fines estadísticos.

---

# **16\. ¿Cuándo crear una nueva categoría?**

Las categorías deberán representar cambios reales de comportamiento dentro del ecosistema.

No se crearán categorías únicamente para distinguir usuarios.

Actualmente:

Explorador

Viajero

Experto

Leyenda

Estas categorías podrán evolucionar mediante parametrización, sin modificar la lógica de los motores que las consumen.

---

# **17\. ¿Cuándo modificar una estructura existente?**

Antes de añadir una nueva columna deberá responderse:

1. ¿Puede resolverse mediante un parámetro?  
2. ¿Puede resolverse mediante una relación?  
3. ¿Puede resolverse mediante una tabla hija?  
4. ¿Puede resolverse mediante una versión?

Solo si todas las respuestas son negativas podrá añadirse una nueva columna.

---

# **18\. Antipatrones Prohibidos**

Quedan expresamente prohibidas las siguientes prácticas:

* duplicar información entre tablas;  
* almacenar valores calculados sin justificación;  
* escribir porcentajes o tiempos en código;  
* eliminar registros críticos;  
* crear tablas específicas para un único tipo de servicio;  
* utilizar JSONB para evitar un correcto modelado relacional;  
* acceder directamente a tablas críticas desde Flutter o React;  
* crear excepciones específicas para un único cliente, asesor o ciudad.

---

# **19\. Lista de Verificación para Nuevas Funcionalidades**

Antes de aprobar cualquier desarrollo deberá verificarse:

* ¿Respeta la arquitectura por dominios?  
* ¿Puede resolverse mediante parametrización?  
* ¿Existe una función reutilizable?  
* ¿Requiere auditoría?  
* ¿Impacta la seguridad?  
* ¿Impacta el modelo financiero?  
* ¿Requiere una nueva métrica?  
* ¿Cumple las políticas RLS?  
* ¿Es escalable a múltiples ciudades y países?  
* ¿Está documentado?

Si alguna respuesta es negativa, el diseño deberá revisarse antes de implementarse.

---

# **20\. Preparación para la Internacionalización**

Toda nueva entidad deberá diseñarse considerando que Tu Mobil Amigo podrá operar en diferentes países.

Por tanto, deberá evitar dependencias implícitas de:

* una única moneda;  
* una única ciudad;  
* un único idioma;  
* un único proveedor de mapas;  
* un único proveedor de pagos;  
* una única normativa local.

Las particularidades de cada jurisdicción deberán resolverse mediante parametrización y versionado.

---

# **21\. Principio Rector Final**

> **Toda evolución de Tu Mobil Amigo deberá construirse ampliando una arquitectura estable y coherente, nunca mediante excepciones aisladas. Cada nueva entidad, función o proceso deberá fortalecer el modelo existente, preservando la separación por dominios, la parametrización, la trazabilidad y la escalabilidad como pilares fundamentales del proyecto.**


Fin de Anexo B — Guía de Modelado de Nuevas Entidades

Fin del Documento 16 — Modelo Conceptual  

