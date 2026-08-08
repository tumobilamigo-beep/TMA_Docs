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

31\. Principio Rector Final  
La base de datos deberá ser capaz de reconstruir completamente la historia operativa, financiera y de confianza de cualquier usuario sin depender de lógica almacenada fuera de la base de datos.

Registro de Cambios  
Versión	Cambio  
1.0	Creación inicial

Fin del Documento 17 — Modelo Lógico  
