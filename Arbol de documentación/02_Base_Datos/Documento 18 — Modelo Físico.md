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
