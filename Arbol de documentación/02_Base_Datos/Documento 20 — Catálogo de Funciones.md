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
