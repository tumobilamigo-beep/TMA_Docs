\# Documento 31 — Componentes

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir el catálogo oficial de componentes reutilizables para las aplicaciones Flutter de Tu Mobil Amigo.

Este documento busca:

\- Reducir duplicidad.  
\- Mejorar mantenibilidad.  
\- Aumentar consistencia visual.  
\- Disminuir deuda técnica.  
\- Facilitar escalabilidad.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo elemento visual reutilizable deberá convertirse en componente.  
Prohibido duplicar código visual entre módulos.

\--------------------------------------------------  
3\. ORGANIZACIÓN OFICIAL  
\--------------------------------------------------

shared/  
components/  
atoms/  
molecules/  
organisms/  
templates/

\--------------------------------------------------  
4\. CLASIFICACIÓN  
\--------------------------------------------------

Atoms  
Elementos básicos.  
Molecules  
Conjunto pequeño de atoms.

Organisms  
Componentes complejos.  
Templates  
Estructuras completas.

\--------------------------------------------------  
5\. ATOMS  
\--------------------------------------------------

Componentes mínimos reutilizables.

\--------------------------------------------------  
6\. APP BUTTON  
\--------------------------------------------------

Responsable de:

\- acciones primarias;  
\- secundarias;  
\- terciarias.

Variantes:

Primary  
Secondary  
Text  
Danger  
Success

\--------------------------------------------------  
7\. APP INPUT  
\--------------------------------------------------

Campos de entrada estándar.

Soporte:

\- texto;  
\- email;  
\- teléfono;  
\- numérico;  
\- contraseña.

\--------------------------------------------------  
8\. APP DROPDOWN  
\--------------------------------------------------

Listas desplegables reutilizables.

\--------------------------------------------------  
9\. APP CHECKBOX  
\--------------------------------------------------

Selección múltiple.

\--------------------------------------------------  
10\. APP RADIO  
\--------------------------------------------------

Selección única.

\--------------------------------------------------  
11\. APP SWITCH  
\--------------------------------------------------

Activación de opciones.

\--------------------------------------------------  
12\. APP LOADER  
\--------------------------------------------------

Indicadores de carga.

\--------------------------------------------------  
13\. APP BADGE  
\--------------------------------------------------

Etiquetas visuales.

Ejemplos:

\- Programado  
\- Nuevo  
\- Pendiente  
\- Pagado

\--------------------------------------------------  
14\. APP AVATAR  
\--------------------------------------------------

Representación visual de usuario.

\--------------------------------------------------  
15\. APP ICON  
\--------------------------------------------------

Wrapper oficial para iconografía.

\--------------------------------------------------  
16\. APP DIVIDER  
\--------------------------------------------------

Separadores visuales.

\--------------------------------------------------  
17\. APP TOOLTIP  
\--------------------------------------------------

Mensajes contextuales.

\--------------------------------------------------  
18\. MOLECULES  
\--------------------------------------------------

Agrupación de componentes básicos.

\--------------------------------------------------  
19\. SEARCH BAR  
\--------------------------------------------------

Búsquedas reutilizables.

\--------------------------------------------------  
20\. FILTER BAR  
\--------------------------------------------------

Filtros dinámicos.

\--------------------------------------------------  
21\. FORM FIELD  
\--------------------------------------------------

Label  
Input  
Error  
Helper Text  
Todo integrado.

\--------------------------------------------------  
22\. DATE PICKER  
\--------------------------------------------------

Selección de fechas.

\--------------------------------------------------  
23\. TIME PICKER  
\--------------------------------------------------

Selección de horas.  
Importante para:  
Servicios Programados.

\--------------------------------------------------  
24\. LOCATION PICKER  
\--------------------------------------------------

Selección geográfica.  
Integrado con:  
OpenStreetMap.

\--------------------------------------------------  
25\. MONEY DISPLAY  
\--------------------------------------------------

Visualización estandarizada de valores monetarios.

\--------------------------------------------------  
26\. ORGANISMS  
\--------------------------------------------------

Componentes de negocio.

\--------------------------------------------------  
27\. SERVICE CARD  
\--------------------------------------------------

Componente principal del sistema.

Mostrará:

\- origen;  
\- destino;  
\- valor;  
\- distancia;  
\- estado;  
\- fecha.

\--------------------------------------------------  
28\. PROGRAMMED SERVICE CARD  
\--------------------------------------------------

Versión especializada.

Mostrará:

\- fecha programada;  
\- hora programada;  
\- incentivo adicional.

\--------------------------------------------------  
29\. OFFER CARD  
\--------------------------------------------------

Visualización de ofertas.

\--------------------------------------------------  
30\. COUNTEROFFER CARD  
\--------------------------------------------------

Visualización de contraofertas.

\--------------------------------------------------  
31\. ADVISOR CARD  
\--------------------------------------------------

Información resumida de asesor.

Mostrará:

\- nombre;  
\- score;  
\- distancia;  
\- servicios realizados.

\--------------------------------------------------  
32\. TRUST CARD  
\--------------------------------------------------

Visualización Trust Score.

Mostrará:

\- score;  
\- categoría;  
\- tendencia.

\--------------------------------------------------  
33\. IMF CARD  
\--------------------------------------------------

Visualización de maduración financiera.

Mostrará:

\- categoría;  
\- progreso;  
\- beneficios.

\--------------------------------------------------  
34\. WALLET CARD  
\--------------------------------------------------

Visualización financiera.

Mostrará:

\- saldo;  
\- cashback;  
\- pendiente;  
\- liquidado.

\--------------------------------------------------  
35\. CASHBACK CARD  
\--------------------------------------------------

Detalle de cashback.

\--------------------------------------------------  
36\. MULTILEVEL CARD  
\--------------------------------------------------

Visualización resumida de red.

\--------------------------------------------------  
37\. LIQUIDATION CARD  
\--------------------------------------------------

Visualización de liquidaciones.

Estados:

\- Pendiente  
\- Procesada  
\- Pagada

\--------------------------------------------------  
38\. NOTIFICATION CARD  
\--------------------------------------------------

Visualización de notificaciones.

\--------------------------------------------------  
39\. AUDIT CARD  
\--------------------------------------------------

Visualización de eventos relevantes.

\--------------------------------------------------  
40\. FRAUD ALERT CARD  
\--------------------------------------------------

Visualización de alertas de riesgo.

\--------------------------------------------------  
41\. QR SCANNER COMPONENT  
\--------------------------------------------------

Componente oficial para lectura QR.

\--------------------------------------------------  
42\. QR DISPLAY COMPONENT  
\--------------------------------------------------

Generación de QR.

\--------------------------------------------------  
43\. MAP COMPONENT  
\--------------------------------------------------

Mapa oficial.

Proveedor inicial:

OpenStreetMap

\--------------------------------------------------  
44\. ROUTE COMPONENT  
\--------------------------------------------------

Visualización de rutas.

Proveedor inicial:

GraphHopper

\--------------------------------------------------  
45\. CHAT COMPONENT  
\--------------------------------------------------

Preparado para futuras versiones.

No obligatorio en V1.

\--------------------------------------------------  
46\. TEMPLATES  
\--------------------------------------------------

Estructuras completas reutilizables.

\--------------------------------------------------  
47\. AUTH TEMPLATE  
\--------------------------------------------------

Pantallas:

\- Login  
\- Registro  
\- Recuperación

\--------------------------------------------------  
48\. DASHBOARD TEMPLATE  
\--------------------------------------------------

Pantallas principales.

\--------------------------------------------------  
49\. LIST TEMPLATE  
\--------------------------------------------------

Pantallas con listados.

\--------------------------------------------------  
50\. DETAIL TEMPLATE  
\--------------------------------------------------

Pantallas de detalle.

\--------------------------------------------------  
51\. FORM TEMPLATE  
\--------------------------------------------------

Pantallas de captura.

\--------------------------------------------------  
52\. MODAL TEMPLATE  
\--------------------------------------------------

Ventanas emergentes.

\--------------------------------------------------  
53\. EMPTY STATE TEMPLATE  
\--------------------------------------------------

Estados sin información.

\--------------------------------------------------  
54\. ERROR STATE TEMPLATE  
\--------------------------------------------------

Estados de error.

\--------------------------------------------------  
55\. LOADING TEMPLATE  
\--------------------------------------------------

Estados de carga.

\--------------------------------------------------  
56\. DARK MODE  
\--------------------------------------------------

Todos los componentes deberán soportar:

\- Light Theme  
\- Dark Theme

desde su construcción inicial.

\--------------------------------------------------  
57\. ACCESIBILIDAD  
\--------------------------------------------------

Todos los componentes deberán cumplir:

\- Contraste AA.  
\- Escalado de fuente.  
\- Compatibilidad con lectores de pantalla.

\--------------------------------------------------  
58\. RESPONSIVE  
\--------------------------------------------------

Todos los componentes deberán adaptarse a:

\- Android  
\- iOS  
\- Windows

\--------------------------------------------------  
59\. OBSERVABILIDAD  
\--------------------------------------------------

Los componentes críticos deberán permitir:

\- logging;  
\- métricas;  
\- diagnóstico.

sin alterar la lógica de negocio.

\--------------------------------------------------  
60\. PROHIBICIONES  
\--------------------------------------------------

No se permitirá:

\- lógica financiera en componentes;  
\- lógica Trust;  
\- lógica IMF;  
\- consultas directas a Base de Datos;  
\- llamadas directas a proveedores externos.

\--------------------------------------------------  
61\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Los componentes Flutter deberán ser reutilizables, desacoplados, consistentes y completamente independientes de las reglas de negocio, permitiendo que la evolución funcional de Tu Mobil Amigo ocurra en Backend y Base de Datos sin requerir rediseños constantes en la interfaz.  
