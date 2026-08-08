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
