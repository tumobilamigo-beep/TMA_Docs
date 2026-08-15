Testing

\# Documento 37 — Estrategia de Testing

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia oficial de validación de calidad para todo el ecosistema Tu Mobil Amigo.

El propósito del testing no es demostrar que el sistema funciona.

El propósito es encontrar fallos antes de que lleguen a producción.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Todo componente deberá ser probado.

Ninguna funcionalidad crítica podrá liberarse sin validación.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

La estrategia cubre:

\- Base de Datos.  
\- Backend.  
\- APIs.  
\- Realtime.  
\- Flutter Cliente.  
\- Flutter Asesor.  
\- React Administrador.  
\- React Superadministrador.  
\- Seguridad.  
\- Integraciones.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Garantizar:

\- calidad;  
\- estabilidad;  
\- seguridad;  
\- trazabilidad;  
\- confiabilidad.

\--------------------------------------------------  
5\. PIRÁMIDE DE TESTING  
\--------------------------------------------------

La estrategia oficial será:

\`\`\`text  
Unit Testing  
    ↓

Integration Testing  
    ↓

End To End Testing  
\`\`\`

\--------------------------------------------------  
6\. NIVELES DE TESTING  
\--------------------------------------------------

Se implementarán:

\- Unitarios.  
\- Integración.  
\- Sistema.  
\- End To End.  
\- Seguridad.  
\- Rendimiento.  
\- Regresión.

\--------------------------------------------------  
7\. UNIT TESTING  
\--------------------------------------------------

Validará:

\- funciones;  
\- reglas;  
\- algoritmos;  
\- cálculos.

\--------------------------------------------------  
8\. COBERTURA UNITARIA  
\--------------------------------------------------

Objetivo mínimo:

\`\`\`text  
80%  
\`\`\`

para módulos críticos.

\--------------------------------------------------  
9\. TESTING DE BASE DE DATOS  
\--------------------------------------------------

Validar:

\- tablas;  
\- constraints;  
\- funciones;  
\- triggers;  
\- índices.

\--------------------------------------------------  
10\. TESTING DE FUNCIONES SQL  
\--------------------------------------------------

Especial atención a:

\- motor tarifario;  
\- trust score;  
\- IMF;  
\- cashback;  
\- multinivel;  
\- liquidaciones.

\--------------------------------------------------  
11\. TESTING DE TRIGGERS  
\--------------------------------------------------

Todo trigger deberá validar:

\- comportamiento esperado;  
\- concurrencia;  
\- consistencia.

\--------------------------------------------------  
12\. TESTING DE BACKEND  
\--------------------------------------------------

Validar:

\- reglas de negocio;  
\- autorización;  
\- validaciones;  
\- respuestas.

\--------------------------------------------------  
13\. TESTING DE EDGE FUNCTIONS  
\--------------------------------------------------

Toda Edge Function deberá tener pruebas específicas.

\--------------------------------------------------  
14\. TESTING DE APIS  
\--------------------------------------------------

Validar:

\- request;  
\- response;  
\- errores;  
\- permisos.

\--------------------------------------------------  
15\. TESTING DE REACT  
\--------------------------------------------------

Validar:

\- navegación;  
\- permisos;  
\- componentes;  
\- formularios.

\--------------------------------------------------  
16\. TESTING DE FLUTTER  
\--------------------------------------------------

Validar:

\- navegación;  
\- estado;  
\- componentes;  
\- experiencia de usuario.

\--------------------------------------------------  
17\. TESTING DE UI  
\--------------------------------------------------

Validar:

\- consistencia visual;  
\- responsividad;  
\- accesibilidad.

\--------------------------------------------------  
18\. TESTING DE NAVEGACIÓN  
\--------------------------------------------------

Toda ruta deberá probarse.

\--------------------------------------------------  
19\. TESTING DE AUTENTICACIÓN  
\--------------------------------------------------

Validar:

\- login;  
\- logout;  
\- recuperación;  
\- MFA.

\--------------------------------------------------  
20\. TESTING DE AUTORIZACIÓN  
\--------------------------------------------------

Validar:

\- Cliente;  
\- Asesor;  
\- Administrador;  
\- Superadministrador.

\--------------------------------------------------  
21\. TESTING DE SEGURIDAD  
\--------------------------------------------------

Validar:

\- acceso indebido;  
\- escalamiento de privilegios;  
\- bypass de permisos.

\--------------------------------------------------  
22\. TESTING ANTIFRAUDE  
\--------------------------------------------------

Validar:

\- multicuentas;  
\- VPN;  
\- Proxy;  
\- dispositivos sospechosos.

\--------------------------------------------------  
23\. TESTING DE TRUST SCORE  
\--------------------------------------------------

Validar:

\- aumentos;  
\- disminuciones;  
\- límites;  
\- recalculación.

\--------------------------------------------------  
24\. TESTING DE IMF  
\--------------------------------------------------

Validar:

\- maduración;  
\- cambios de nivel;  
\- restricciones.

\--------------------------------------------------  
25\. TESTING DE CASHBACK  
\--------------------------------------------------

Validar:

\- cálculo;  
\- acumulación;  
\- reversos;  
\- liquidación.

\--------------------------------------------------  
26\. TESTING MULTINIVEL  
\--------------------------------------------------

Validar:

\- elegibilidad;  
\- distribución;  
\- límites;  
\- trazabilidad.

\--------------------------------------------------  
27\. TESTING DE INCENTIVOS  
\--------------------------------------------------

Validar:

\- generación;  
\- maduración;  
\- liquidación.

\--------------------------------------------------  
28\. TESTING DE SERVICIOS  
\--------------------------------------------------

Validar:

\- inmediato;  
\- programado;  
\- negociación;  
\- cancelación.

\--------------------------------------------------  
29\. TESTING DE LIQUIDACIONES  
\--------------------------------------------------

Validar:

\- simulación;  
\- aprobación;  
\- ejecución;  
\- pago;  
\- anulación.

\--------------------------------------------------  
30\. TESTING DE REPORTES  
\--------------------------------------------------

Validar:

\- Excel;  
\- CSV;  
\- PDF.

\--------------------------------------------------  
31\. TESTING DE INTEGRACIONES  
\--------------------------------------------------

Validar:

\- Telegram;  
\- OpenStreetMap;  
\- GraphHopper;  
\- ERP futuros.

\--------------------------------------------------  
32\. TESTING DE REALTIME  
\--------------------------------------------------

Validar:

\- recepción;  
\- sincronización;  
\- reconexión;  
\- recuperación.

\--------------------------------------------------  
33\. TESTING DE DISPOSITIVOS  
\--------------------------------------------------

Validar:

\- registro;  
\- bloqueo;  
\- reputación;  
\- cambios.

\--------------------------------------------------  
34\. TESTING DE CONCURRENCIA  
\--------------------------------------------------

Validar:

\- múltiples usuarios;  
\- operaciones simultáneas;  
\- conflictos.

\--------------------------------------------------  
35\. TESTING DE RECUPERACIÓN  
\--------------------------------------------------

Validar:

\- restauración;  
\- reprocesamiento;  
\- continuidad operativa.

\--------------------------------------------------  
36\. TESTING DE EXPORTACIONES  
\--------------------------------------------------

Validar:

\- contenido;  
\- formato;  
\- integridad.

\--------------------------------------------------  
37\. TESTING DE DATOS  
\--------------------------------------------------

Validar:

\- integridad;  
\- consistencia;  
\- restricciones.

\--------------------------------------------------  
38\. TESTING DE ERRORES  
\--------------------------------------------------

Validar:

\- errores controlados;  
\- excepciones;  
\- mensajes.

\--------------------------------------------------  
39\. TESTING DE REGRESIÓN  
\--------------------------------------------------

Toda corrección deberá validar que no rompa funcionalidades existentes.

\--------------------------------------------------  
40\. TESTING DE RENDIMIENTO  
\--------------------------------------------------

Validar:

\- tiempos de respuesta;  
\- uso de recursos;  
\- escalabilidad.

\--------------------------------------------------  
41\. TESTING DE CARGA  
\--------------------------------------------------

Simular:

\- usuarios concurrentes;  
\- crecimiento progresivo.

\--------------------------------------------------  
42\. TESTING DE ESTRÉS  
\--------------------------------------------------

Evaluar comportamiento ante límites operativos.

\--------------------------------------------------  
43\. TESTING DE FALLAS  
\--------------------------------------------------

Simular:

\- pérdida de red;  
\- caída de servicios;  
\- errores de integración.

\--------------------------------------------------  
44\. AUTOMATIZACIÓN  
\--------------------------------------------------

Las pruebas deberán automatizarse cuando sea viable.

\--------------------------------------------------  
45\. PIPELINE DE CALIDAD  
\--------------------------------------------------

Ningún despliegue deberá omitir validaciones obligatorias.

\--------------------------------------------------  
46\. CRITERIOS DE APROBACIÓN  
\--------------------------------------------------

Una funcionalidad se considerará aprobada cuando:

\- cumpla requisitos;  
\- supere pruebas;  
\- no presente defectos críticos.

\--------------------------------------------------  
47\. CLASIFICACIÓN DE DEFECTOS  
\--------------------------------------------------

\`\`\`text  
CRITICO

ALTO

MEDIO

BAJO  
\`\`\`

\--------------------------------------------------  
48\. BLOQUEADORES DE PRODUCCIÓN  
\--------------------------------------------------

No podrá liberarse una versión con defectos:

\`\`\`text  
CRITICO  
\`\`\`

abiertos.

\--------------------------------------------------  
49\. TRAZABILIDAD  
\--------------------------------------------------

Toda prueba deberá poder relacionarse con:

\- requisito;  
\- regla de negocio;  
\- resultado.

\--------------------------------------------------  
50\. EVIDENCIAS  
\--------------------------------------------------

Toda ejecución deberá generar evidencia verificable.

\--------------------------------------------------  
51\. AUDITORÍA DE TESTING  
\--------------------------------------------------

Las pruebas críticas deberán conservar historial.

\--------------------------------------------------  
52\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia deberá crecer junto con la plataforma.

La estrategia podrá complementarse mediante documentos especializados de testing financiero, seguridad y rendimiento cuando la complejidad del proyecto lo requiera.

\--------------------------------------------------  
53\. Testing de Portales React  
\--------------------------------------------------
Categoría de pruebas dedicada a Administrador/Superadministrador, complementaria al Documento 37A (que cubre específicamente seguridad y pentesting de estos portales). Debe incluir pruebas funcionales de RBAC: verificar que un Administrador no pueda acceder a funciones exclusivas de Superadministrador ni a la inversa mediante manipulación de rutas o payloads.

\--------------------------------------------------  
54\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

La calidad de Tu Mobil Amigo deberá demostrarse mediante pruebas objetivas, repetibles y trazables, garantizando que cada módulo del sistema funcione correctamente antes de llegar a los usuarios o impactar procesos financieros, operativos y de seguridad.  

Fin de Documento 37 — Estrategia de Testing

\# Documento 37A — Testing de Seguridad y Pentesting

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir la estrategia especializada de pruebas de seguridad ofensiva y defensiva para identificar vulnerabilidades antes de que puedan ser explotadas en ambientes productivos.

Este documento complementa:

Documento 32 — Ciberseguridad

Documento 37 — Estrategia de Testing

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Toda funcionalidad deberá considerarse vulnerable hasta que haya sido validada mediante pruebas de seguridad.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Flutter Cliente;  
\- Flutter Asesor;  
\- React Administrador;  
\- React Superadministrador;  
\- APIs;  
\- Edge Functions;  
\- Base de Datos;  
\- Realtime;  
\- Integraciones;  
\- Infraestructura.

\--------------------------------------------------  
4\. OBJETIVOS  
\--------------------------------------------------

Detectar:

\- vulnerabilidades;  
\- errores de configuración;  
\- exposición de información;  
\- escalamiento de privilegios;  
\- riesgos financieros.

\--------------------------------------------------  
5\. MODELO DE REFERENCIA  
\--------------------------------------------------

La estrategia tomará como referencia:

\`\`\`text  
OWASP Top 10

OWASP API Security Top 10

OWASP Mobile Top 10  
\`\`\`

\--------------------------------------------------  
6\. MOMENTOS DE EJECUCIÓN  
\--------------------------------------------------

Las pruebas deberán ejecutarse:

\- antes de producción;  
\- después de cambios críticos;  
\- después de incidentes;  
\- periódicamente.

\--------------------------------------------------  
7\. TIPOS DE PRUEBA  
\--------------------------------------------------

Se implementarán:

\`\`\`text  
SAST

DAST

Pentesting

API Security Testing

Mobile Security Testing

Database Security Testing  
\`\`\`

\--------------------------------------------------  
8\. SAST  
\--------------------------------------------------

Static Application Security Testing.

Analiza:

\- código fuente;  
\- dependencias;  
\- configuraciones.

\--------------------------------------------------  
9\. OBJETIVO DEL SAST  
\--------------------------------------------------

Detectar:

\- secretos expuestos;  
\- código inseguro;  
\- dependencias vulnerables;  
\- configuraciones incorrectas.

\--------------------------------------------------  
10\. DAST  
\--------------------------------------------------

Dynamic Application Security Testing.

Analiza aplicaciones en ejecución.

\--------------------------------------------------  
11\. OBJETIVO DEL DAST  
\--------------------------------------------------

Detectar:

\- vulnerabilidades explotables;  
\- errores de autorización;  
\- errores de autenticación.

\--------------------------------------------------  
12\. PENTESTING  
\--------------------------------------------------

Se realizarán pruebas controladas simulando ataques reales.

\--------------------------------------------------  
13\. ALCANCE DEL PENTEST  
\--------------------------------------------------

Como mínimo:

\- Frontend;  
\- Backend;  
\- APIs;  
\- Seguridad financiera.

\--------------------------------------------------  
14\. SEGURIDAD DE APIs  
\--------------------------------------------------

Toda API deberá someterse a pruebas específicas.

\--------------------------------------------------  
15\. OWASP API TOP 10  
\--------------------------------------------------

Validar:

\- Broken Object Level Authorization;  
\- Broken Authentication;  
\- Excessive Data Exposure;  
\- Mass Assignment;  
\- Security Misconfiguration;  
\- Injection;  
\- Improper Assets Management.

\--------------------------------------------------  
16\. SQL INJECTION  
\--------------------------------------------------

Toda API deberá probar resistencia frente a:

\`\`\`text  
SQL Injection  
\`\`\`

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
17\. NOSQL INJECTION  
\--------------------------------------------------

Validar protección frente a inyecciones equivalentes.

\--------------------------------------------------  
18\. XSS  
\--------------------------------------------------

Validar:

\`\`\`text  
Cross Site Scripting  
\`\`\`

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
19\. CSRF  
\--------------------------------------------------

Validar:

\`\`\`text  
Cross Site Request Forgery  
\`\`\`

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
20\. SSRF  
\--------------------------------------------------

Validar:

\`\`\`text  
Server Side Request Forgery  
\`\`\`

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
21\. IDOR  
\--------------------------------------------------

Validar:

\`\`\`text  
Insecure Direct Object Reference  
\`\`\`

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
22\. ESCALAMIENTO DE PRIVILEGIOS  
\--------------------------------------------------

Validar intentos de:

\- Cliente → Asesor  
\- Asesor → Administrador  
\- Administrador → Superadministrador

\--------------------------------------------------  
23\. CONTROL DE ROLES  
\--------------------------------------------------

Validar exhaustivamente:

\`\`\`text  
Cliente

Asesor

Administrador

Superadministrador  
\`\`\`

\--------------------------------------------------  
24\. SEGURIDAD DE TOKENS  
\--------------------------------------------------

Validar:

\- expiración;  
\- revocación;  
\- reutilización.

\--------------------------------------------------  
25\. JWT TESTING  
\--------------------------------------------------

Validar manipulación de:

\- payload;  
\- firma;  
\- expiración.

\--------------------------------------------------  
26\. MFA TESTING  
\--------------------------------------------------

Validar:

\- bypass;  
\- reutilización;  
\- expiración.

\--------------------------------------------------  
27\. RATE LIMIT TESTING  
\--------------------------------------------------

Validar límites configurados.

\--------------------------------------------------  
28\. FUERZA BRUTA  
\--------------------------------------------------

Simular:

\- login masivo;  
\- recuperación masiva.

\--------------------------------------------------  
29\. ENUMERACIÓN DE USUARIOS  
\--------------------------------------------------

Validar que no sea posible descubrir usuarios válidos mediante respuestas del sistema.

\--------------------------------------------------  
30\. SEGURIDAD DE DISPOSITIVOS  
\--------------------------------------------------

Validar:

\- spoofing;  
\- fingerprint manipulation;  
\- evasión de controles.

\--------------------------------------------------  
31\. SEGURIDAD ANTIFRAUDE  
\--------------------------------------------------

Validar intentos de evasión del:

\`\`\`text  
Motor Antifraude  
\`\`\`

\--------------------------------------------------  
32\. SEGURIDAD DE TRUST SCORE  
\--------------------------------------------------

Validar intentos de manipulación.

\--------------------------------------------------  
33\. SEGURIDAD DE IMF  
\--------------------------------------------------

Validar intentos de alterar:

\- maduración;  
\- niveles;  
\- beneficios.

\--------------------------------------------------  
34\. SEGURIDAD DE CASHBACK  
\--------------------------------------------------

Validar intentos de:

\- generación fraudulenta;  
\- duplicación;  
\- abuso.

\--------------------------------------------------  
35\. SEGURIDAD MULTINIVEL  
\--------------------------------------------------

Validar:

\- auto-referidos;  
\- estructuras artificiales;  
\- fraude de patrocinadores.

\--------------------------------------------------  
36\. SEGURIDAD DE LIQUIDACIONES  
\--------------------------------------------------

Validar:

\- ejecución no autorizada;  
\- modificación de montos;  
\- fraude interno.

\--------------------------------------------------  
37\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

Validar:

\- aprobación;  
\- ejecución;  
\- pago.

No deberán poder vulnerarse.

\--------------------------------------------------  
38\. SEGURIDAD DE BASE DE DATOS  
\--------------------------------------------------

Validar:

\- permisos;  
\- acceso directo;  
\- exposición.

\--------------------------------------------------  
39\. TESTING DE RLS  
\--------------------------------------------------

Toda política RLS deberá probarse.

\--------------------------------------------------  
40\. VALIDACIÓN RLS  
\--------------------------------------------------

Confirmar:

\`\`\`text  
Lo permitido funciona.

Lo prohibido falla.  
\`\`\`

\--------------------------------------------------  
41\. SECRETOS Y CREDENCIALES  
\--------------------------------------------------

Validar ausencia de:

\- API Keys expuestas;  
\- Secrets expuestos;  
\- Tokens expuestos;  
\- Contraseñas hardcodeadas.

\--------------------------------------------------  
42\. GESTIÓN DE DEPENDENCIAS  
\--------------------------------------------------

Analizar vulnerabilidades conocidas.

\--------------------------------------------------  
43\. SEGURIDAD DE OPENSTREETMAP  
\--------------------------------------------------

Validar uso seguro de servicios de mapas.

\--------------------------------------------------  
44\. SEGURIDAD DE GRAPHHOPPER  
\--------------------------------------------------

Validar:

\- autenticación;  
\- límites;  
\- abuso.

\--------------------------------------------------  
45\. SEGURIDAD DE TELEGRAM  
\--------------------------------------------------

Validar:

\- identidad;  
\- integridad;  
\- autenticidad.

\--------------------------------------------------  
46\. SEGURIDAD DE EXPORTACIONES  
\--------------------------------------------------

Validar:

\- Excel;  
\- CSV;  
\- PDF.

\--------------------------------------------------  
47\. SEGURIDAD DE AUDITORÍA  
\--------------------------------------------------

Validar imposibilidad de:

\- modificar;  
\- eliminar;  
\- ocultar evidencia.

\--------------------------------------------------  
48\. SEGURIDAD DE BACKUPS  
\--------------------------------------------------

Validar:

\- cifrado;  
\- acceso;  
\- restauración.

\--------------------------------------------------  
49\. TESTING DE CONTINUIDAD  
\--------------------------------------------------

Validar comportamiento bajo:

\- fallos;  
\- ataques;  
\- degradación.

\--------------------------------------------------  
50\. CLASIFICACIÓN DE HALLAZGOS  
\--------------------------------------------------

\`\`\`text  
CRITICO

ALTO

MEDIO

BAJO

INFORMATIVO  
\`\`\`

\--------------------------------------------------  
51\. CRITERIOS DE BLOQUEO  
\--------------------------------------------------

No podrá liberarse una versión que contenga vulnerabilidades:

\`\`\`text  
CRITICO  
\`\`\`

o

\`\`\`text  
ALTO  
\`\`\`

sin aprobación formal del Superadministrador.

\--------------------------------------------------  
52\. REMEDIACIÓN  
\--------------------------------------------------

Todo hallazgo deberá generar:

\- responsable;  
\- fecha objetivo;  
\- evidencia de corrección.

\--------------------------------------------------  
53\. TRAZABILIDAD  
\--------------------------------------------------

Toda prueba deberá generar evidencia auditable.

\--------------------------------------------------  
54\. EVOLUCIÓN  
\--------------------------------------------------

La estrategia deberá actualizarse conforme evolucionen:

\- amenazas;  
\- tecnologías;  
\- regulaciones.

\--------------------------------------------------  
55\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda funcionalidad de Tu Mobil Amigo deberá resistir intentos razonables de explotación técnica, financiera y operativa antes de ser considerada apta para producción.  

Fin de Documento 37A — Testing de Seguridad y Pentesting

\# Documento 38 — Casos de Prueba

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir los casos de prueba oficiales que permitirán validar funcionalmente, operativamente, financieramente y técnicamente el ecosistema Tu Mobil Amigo.

Este documento transforma las reglas de negocio aprobadas en escenarios verificables.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Toda regla de negocio deberá tener al menos un caso de prueba asociado.

Toda funcionalidad crítica deberá tener múltiples escenarios de validación.

\--------------------------------------------------  
3\. ESTRUCTURA ESTÁNDAR  
\--------------------------------------------------

Cada caso de prueba deberá contener:

\`\`\`text  
ID

Nombre

Objetivo

Precondiciones

Pasos

Resultado Esperado

Prioridad

Estado  
\`\`\`

\--------------------------------------------------  
4\. CLASIFICACIÓN  
\--------------------------------------------------

Los casos de prueba se clasifican en:

\`\`\`text  
FUNCIONAL

NEGOCIO

FINANCIERO

SEGURIDAD

INTEGRACIÓN

RENDIMIENTO

RECUPERACIÓN  
\`\`\`

\--------------------------------------------------  
5\. CASOS DE AUTENTICACIÓN  
\--------------------------------------------------

\#\#\# CP-AUT-001

Login válido.

Resultado esperado:

Acceso exitoso.

\---

\#\#\# CP-AUT-002

Contraseña incorrecta.

Resultado esperado:

Acceso denegado.

\---

\#\#\# CP-AUT-003

Usuario suspendido.

Resultado esperado:

Acceso bloqueado.

\---

\#\#\# CP-AUT-004

MFA exitoso.

Resultado esperado:

Acceso autorizado.

\---

\#\#\# CP-AUT-005

MFA inválido.

Resultado esperado:

Acceso denegado.

\--------------------------------------------------  
6\. CASOS DE ROLES  
\--------------------------------------------------

\#\#\# CP-ROL-001

Cliente accede únicamente a recursos de cliente.

\---

\#\#\# CP-ROL-002

Asesor accede únicamente a recursos de asesor.

\---

\#\#\# CP-ROL-003

Administrador accede únicamente a recursos administrativos.

\---

\#\#\# CP-ROL-004

Superadministrador posee acceso total autorizado.

\---

\#\#\# CP-ROL-005

Intento de escalamiento de privilegios.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
7\. CASOS DE SERVICIOS  
\--------------------------------------------------

\#\#\# CP-SRV-001

Crear servicio inmediato.

\---

\#\#\# CP-SRV-002

Crear servicio programado.

\---

\#\#\# CP-SRV-003

Cancelar servicio.

\---

\#\#\# CP-SRV-004

Finalizar servicio.

\---

\#\#\# CP-SRV-005

Servicio expirado.

\--------------------------------------------------  
8\. CASOS DE NEGOCIACIÓN  
\--------------------------------------------------

\#\#\# CP-NEG-001

Oferta válida.

\---

\#\#\# CP-NEG-002

Contraoferta válida.

\---

\#\#\# CP-NEG-003

Aceptación de oferta.

\---

\#\#\# CP-NEG-004

Expiración de oferta.

\---

\#\#\# CP-NEG-005

Oferta fuera de límites permitidos.

Resultado esperado:

Rechazada.

\--------------------------------------------------  
9\. CASOS DE MOTOR TARIFARIO  
\--------------------------------------------------

\#\#\# CP-TAR-001

Cálculo correcto de tarifa.

\---

\#\#\# CP-TAR-002

Aplicación correcta de variables por ciudad.

\---

\#\#\# CP-TAR-003

Cambio de parámetros sin modificación de código.

\---

\#\#\# CP-TAR-004

Validación de límites mínimos.

\---

\#\#\# CP-TAR-005

Validación de límites máximos.

\--------------------------------------------------  
10\. CASOS DE TRUST SCORE  
\--------------------------------------------------

\#\#\# CP-TRUST-001

Incremento por operación exitosa.

\---

\#\#\# CP-TRUST-002

Disminución por cancelación.

\---

\#\#\# CP-TRUST-003

Límite inferior.

\---

\#\#\# CP-TRUST-004

Límite superior.

\---

\#\#\# CP-TRUST-005

Recalculo completo.

\--------------------------------------------------  
11\. CASOS DE IMF  
\--------------------------------------------------

\#\#\# CP-IMF-001

Maduración correcta.

\---

\#\#\# CP-IMF-002

Cambio de nivel.

\---

\#\#\# CP-IMF-003

Validación de restricciones.

\---

\#\#\# CP-IMF-004

Liquidación anticipada.

Resultado esperado:

No altera IMF.

\--------------------------------------------------  
12\. CASOS DE CASHBACK  
\--------------------------------------------------

\#\#\# CP-CASH-001

Generación correcta.

\---

\#\#\# CP-CASH-002

Servicio programado.

Resultado esperado:

35%.

\---

\#\#\# CP-CASH-003

Servicio inmediato.

Resultado esperado:

30%.

\---

\#\#\# CP-CASH-004

Reverso.

\---

\#\#\# CP-CASH-005

Ajuste manual.

\--------------------------------------------------  
13\. CASOS MULTINIVEL  
\--------------------------------------------------

\#\#\# CP-MLM-001

Distribución Nivel 1\.

\---

\#\#\# CP-MLM-002

Distribución Nivel 2\.

\---

\#\#\# CP-MLM-003

Sin patrocinador elegible.

\---

\#\#\# CP-MLM-004

Patrocinador suspendido.

\---

\#\#\# CP-MLM-005

Validación legal del esquema.

\--------------------------------------------------  
14\. CASOS DE INCENTIVOS  
\--------------------------------------------------

\#\#\# CP-INC-001

Generación de incentivo.

\---

\#\#\# CP-INC-002

Maduración correcta.

\---

\#\#\# CP-INC-003

Liquidación.

\---

\#\#\# CP-INC-004

Reverso.

\--------------------------------------------------  
15\. CASOS DE LIQUIDACIONES  
\--------------------------------------------------

\#\#\# CP-LIQ-001

Generación de simulación.

\---

\#\#\# CP-LIQ-002

Aprobación.

\---

\#\#\# CP-LIQ-003

Ejecución.

\---

\#\#\# CP-LIQ-004

Pago.

\---

\#\#\# CP-LIQ-005

Anulación.

\---

\#\#\# CP-LIQ-006

Liquidación extraordinaria por usuario.

\---

\#\#\# CP-LIQ-007

Liquidación extraordinaria por ciudad.

\---

\#\#\# CP-LIQ-008

Intento de ejecutar sin aprobación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
16\. CASOS DE AUDITORÍA  
\--------------------------------------------------

\#\#\# CP-AUD-001

Registro de login.

\---

\#\#\# CP-AUD-002

Registro financiero.

\---

\#\#\# CP-AUD-003

Registro administrativo.

\---

\#\#\# CP-AUD-004

Registro de liquidación.

\--------------------------------------------------  
17\. CASOS DE DISPOSITIVOS  
\--------------------------------------------------

\#\#\# CP-DEV-001

Registro de nuevo dispositivo.

\---

\#\#\# CP-DEV-002

Cambio frecuente de dispositivo.

\---

\#\#\# CP-DEV-003

VPN detectada.

\---

\#\#\# CP-DEV-004

Proxy detectado.

\---

\#\#\# CP-DEV-005

Dispositivo bloqueado.

\--------------------------------------------------  
18\. CASOS ANTIFRAUDE  
\--------------------------------------------------

\#\#\# CP-AF-001

Multicuenta.

\---

\#\#\# CP-AF-002

Abuso de incentivos.

\---

\#\#\# CP-AF-003

Patrones sospechosos.

\---

\#\#\# CP-AF-004

Manipulación de ubicación.

\--------------------------------------------------  
19\. CASOS DE SEGURIDAD  
\--------------------------------------------------

\#\#\# CP-SEC-001

SQL Injection.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-002

XSS.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-003

CSRF.

Resultado esperado:

Bloqueado.

\---

\#\#\# CP-SEC-004

Acceso sin autenticación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
20\. CASOS DE APIs  
\--------------------------------------------------

\#\#\# CP-API-001

Solicitud válida.

\---

\#\#\# CP-API-002

Token inválido.

\---

\#\#\# CP-API-003

Permiso insuficiente.

\---

\#\#\# CP-API-004

Rate limit excedido.

\--------------------------------------------------  
21\. CASOS DE REALTIME  
\--------------------------------------------------

\#\#\# CP-RT-001

Recepción de evento.

\---

\#\#\# CP-RT-002

Reconexión automática.

\---

\#\#\# CP-RT-003

Recuperación tras desconexión.

\--------------------------------------------------  
22\. CASOS DE OPENSTREETMAP  
\--------------------------------------------------

\#\#\# CP-MAP-001

Obtención de coordenadas.

\---

\#\#\# CP-MAP-002

Ruta válida.

\---

\#\#\# CP-MAP-003

Falla temporal del proveedor.

Resultado esperado:

Degradación controlada.

\--------------------------------------------------  
23\. CASOS DE INTEGRACIONES  
\--------------------------------------------------

\#\#\# CP-INT-001

Telegram disponible.

\---

\#\#\# CP-INT-002

Telegram no disponible.

\---

\#\#\# CP-INT-003

ERP futuro disponible.

\--------------------------------------------------  
24\. CASOS DE REPORTES  
\--------------------------------------------------

\#\#\# CP-REP-001

Excel mensual generado.

\---

\#\#\# CP-REP-002

CSV generado.

\---

\#\#\# CP-REP-003

PDF generado.

\--------------------------------------------------  
25\. CASOS DE CONTINUIDAD OPERATIVA  
\--------------------------------------------------

\#\#\# CP-CO-001

Caída de integración.

\---

\#\#\# CP-CO-002

Caída de Realtime.

\---

\#\#\# CP-CO-003

Recuperación de Base de Datos.

\---

\#\#\# CP-CO-004

Restauración desde backup.

\--------------------------------------------------  
26\. CASOS DE CONCURRENCIA  
\--------------------------------------------------

\#\#\# CP-CON-001

100 usuarios simultáneos.

\---

\#\#\# CP-CON-002

500 usuarios simultáneos.

\---

\#\#\# CP-CON-003

Múltiples ofertas simultáneas.

\--------------------------------------------------  
27\. CASOS DE EXPORTACIÓN  
\--------------------------------------------------

\#\#\# CP-EXP-001

Excel correcto.

\---

\#\#\# CP-EXP-002

CSV correcto.

\---

\#\#\# CP-EXP-003

PDF correcto.

\--------------------------------------------------  
28\. MATRIZ DE COBERTURA  
\--------------------------------------------------

Todo requisito deberá vincularse con:

\- caso de prueba;  
\- resultado;  
\- evidencia.

\--------------------------------------------------  
29\. TRAZABILIDAD  
\--------------------------------------------------

Toda ejecución deberá generar evidencia auditable.

\--------------------------------------------------  
30\. CP-SA-001:  
\--------------------------------------------------
 Superadministrador ejecuta reapertura de período con justificación → período recalculado, evidencia conservada, evento auditado.
 
\--------------------------------------------------  
31\. CP-SA-002:  
\-------------------------------------------------- 
Superadministrador intenta reapertura sin justificación → operación rechazada.

\--------------------------------------------------  
32\. CP-SA-003:  
\--------------------------------------------------
Administrador intenta ejecutar reapertura de período → operación rechazada por falta de permiso (403).

\--------------------------------------------------  
33\. CP-SA-004:  
\--------------------------------------------------
Superadministrador ejecuta liquidación extraordinaria → visible solo para Superadministrador, registrada en Centro de Liquidaciones (ver Documento 28, Sección 39).

\--------------------------------------------------  
34\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Ninguna funcionalidad de Tu Mobil Amigo podrá considerarse aprobada hasta que los casos de prueba asociados hayan sido ejecutados, documentados y validados satisfactoriamente.  

Fin de Documento 38 — Casos de Prueba

\# Documento 38A — Casos de Prueba Financieros

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir los casos de prueba especializados para validar la integridad financiera de Tu Mobil Amigo.

Este documento complementa:

\- Documento 09 — Modelo Financiero  
\- Documento 10 — Motor Tarifario  
\- Documento 12 — Sistema Multinivel  
\- Documento 14 — IMF  
\- Documento 33 — Protección Financiera  
\- Documento 38 — Casos de Prueba

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ningún cálculo financiero deberá llegar a producción sin evidencia verificable de funcionamiento correcto.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Tarifas  
\- Cashback  
\- Multinivel  
\- Incentivos  
\- IMF  
\- Liquidaciones  
\- Conciliaciones  
\- Fondo de Reserva  
\- Reportes Financieros

\--------------------------------------------------  
4\. CRITERIOS DE ÉXITO  
\--------------------------------------------------

Toda prueba financiera deberá validar:

\`\`\`text  
Exactitud

Trazabilidad

Repetibilidad

Auditabilidad

No duplicidad  
\`\`\`

\--------------------------------------------------  
5\. MOTOR TARIFARIO  
\--------------------------------------------------

\#\#\# CPF-TAR-001

Tarifa mínima válida.

Resultado esperado:

Cálculo correcto.

\---

\#\#\# CPF-TAR-002

Tarifa máxima válida.

Resultado esperado:

Cálculo correcto.

\---

\#\#\# CPF-TAR-003

Ciudad sin parámetros.

Resultado esperado:

Operación bloqueada.

\---

\#\#\# CPF-TAR-004

Cambio de parámetros desde BD.

Resultado esperado:

Sin cambios de código.

\---

\#\#\# CPF-TAR-005

Cambio de tarifa durante operación activa.

Resultado esperado:

No afecta servicio ya creado.

\--------------------------------------------------  
6\. NEGOCIACIÓN  
\--------------------------------------------------

\#\#\# CPF-NEG-001

Oferta dentro de límites.

\---

\#\#\# CPF-NEG-002

Oferta fuera de límites.

Resultado esperado:

Rechazada.

\---

\#\#\# CPF-NEG-003

Contraoferta válida.

\---

\#\#\# CPF-NEG-004

Expiración de negociación.

\--------------------------------------------------  
7\. CASHBACK  
\--------------------------------------------------

\#\#\# CPF-CASH-001

Servicio inmediato.

Resultado esperado:

30%.

\---

\#\#\# CPF-CASH-002

Servicio programado.

Resultado esperado:

35%.

\---

\#\#\# CPF-CASH-003

Cancelación antes de finalizar.

Resultado esperado:

No genera cashback.

\---

\#\#\# CPF-CASH-004

Servicio anulado.

Resultado esperado:

Reverso completo.

\---

\#\#\# CPF-CASH-005

Intento de doble generación.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-CASH-006

Reprocesamiento del evento.

Resultado esperado:

No duplica valores.

\--------------------------------------------------  
8\. MULTINIVEL  
\--------------------------------------------------

\#\#\# CPF-MLM-001

Patrocinador Nivel 1 válido.

Resultado esperado:

20%.

\---

\#\#\# CPF-MLM-002

Patrocinador Nivel 2 válido.

Resultado esperado:

10%.

\---

\#\#\# CPF-MLM-003

Sin patrocinador.

Resultado esperado:

No genera distribución.

\---

\#\#\# CPF-MLM-004

Patrocinador suspendido.

Resultado esperado:

No recibe beneficio.

\---

\#\#\# CPF-MLM-005

Auto-referido.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-MLM-006

Cadena circular.

Resultado esperado:

Bloqueada.

\--------------------------------------------------  
9\. FONDO DE RESERVA  
\--------------------------------------------------

\#\#\# CPF-RES-001

Generación correcta.

Resultado esperado:

10%.

\---

\#\#\# CPF-RES-002

Acumulación histórica.

\---

\#\#\# CPF-RES-003

Consulta histórica.

\--------------------------------------------------  
10\. INCENTIVOS  
\--------------------------------------------------

\#\#\# CPF-INC-001

Generación correcta.

\---

\#\#\# CPF-INC-002

Maduración correcta.

\---

\#\#\# CPF-INC-003

Liquidación correcta.

\---

\#\#\# CPF-INC-004

Reverso autorizado.

\--------------------------------------------------  
11\. IMF  
\--------------------------------------------------

\#\#\# CPF-IMF-001

Cambio de nivel.

\---

\#\#\# CPF-IMF-002

Maduración correcta.

\---

\#\#\# CPF-IMF-003

No pérdida de historial.

\---

\#\#\# CPF-IMF-004

Intento de manipulación.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
12\. BILLETERAS  
\--------------------------------------------------

\#\#\# CPF-WAL-001

Abono válido.

\---

\#\#\# CPF-WAL-002

Débito válido.

\---

\#\#\# CPF-WAL-003

Saldo insuficiente.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-WAL-004

Concurrencia simultánea.

Resultado esperado:

Consistencia garantizada.

\--------------------------------------------------  
13\. MOVIMIENTOS FINANCIEROS  
\--------------------------------------------------

\#\#\# CPF-MOV-001

Movimiento único.

\---

\#\#\# CPF-MOV-002

Movimiento duplicado.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-MOV-003

Movimiento revertido.

\---

\#\#\# CPF-MOV-004

Movimiento auditado.

\--------------------------------------------------  
14\. LIQUIDACIONES MENSUALES  
\--------------------------------------------------

\#\#\# CPF-LIQ-001

Generación automática.

\---

\#\#\# CPF-LIQ-002

Corte:

\`\`\`text  
Último día del mes  
23:59:59  
\`\`\`

\---

\#\#\# CPF-LIQ-003

Reporte Excel generado.

\---

\#\#\# CPF-LIQ-004

Discriminación correcta:

\- Cashback  
\- Multinivel  
\- Incentivos  
\- Totales

\---

\#\#\# CPF-LIQ-005

Auditoría generada.

\--------------------------------------------------  
15\. LIQUIDACIONES EXTRAORDINARIAS  
\--------------------------------------------------

\#\#\# CPF-LIQ-006

Liquidación individual.

\---

\#\#\# CPF-LIQ-007

Liquidación por ciudad.

\---

\#\#\# CPF-LIQ-008

Liquidación por grupo.

\---

\#\#\# CPF-LIQ-009

Sin afectar liquidaciones futuras.

\--------------------------------------------------  
16\. PAGOS  
\--------------------------------------------------

\#\#\# CPF-PAG-001

Pago aprobado.

\---

\#\#\# CPF-PAG-002

Pago rechazado.

\---

\#\#\# CPF-PAG-003

Pago duplicado.

Resultado esperado:

Bloqueado.

\---

\#\#\# CPF-PAG-004

Pago auditado.

\--------------------------------------------------  
17\. CONCILIACIÓN  
\--------------------------------------------------

\#\#\# CPF-CON-001

Conciliación completa.

\---

\#\#\# CPF-CON-002

Diferencia detectada.

\---

\#\#\# CPF-CON-003

Reconciliación exitosa.

\--------------------------------------------------  
18\. REPORTES  
\--------------------------------------------------

\#\#\# CPF-REP-001

Excel mensual.

\---

\#\#\# CPF-REP-002

Exportación CSV.

\---

\#\#\# CPF-REP-003

Exportación PDF.

\---

\#\#\# CPF-REP-004

Totales coinciden con Base de Datos.

\--------------------------------------------------  
19\. RECUPERACIÓN  
\--------------------------------------------------

\#\#\# CPF-REC-001

Recuperación desde backup.

\---

\#\#\# CPF-REC-002

No pérdida financiera.

\---

\#\#\# CPF-REC-003

No duplicidad.

\--------------------------------------------------  
20\. CONCURRENCIA  
\--------------------------------------------------

\#\#\# CPF-CC-001

100 liquidaciones simultáneas.

\---

\#\#\# CPF-CC-002

1000 movimientos simultáneos.

\---

\#\#\# CPF-CC-003

Múltiples procesos de cálculo.

Resultado esperado:

Consistencia total.

\--------------------------------------------------  
21\. FRAUDE FINANCIERO  
\--------------------------------------------------

\#\#\# CPF-FRD-001

Manipulación de cashback.

\---

\#\#\# CPF-FRD-002

Manipulación de multinivel.

\---

\#\#\# CPF-FRD-003

Manipulación de liquidación.

\---

\#\#\# CPF-FRD-004

Manipulación de billetera.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
22\. SEGREGACIÓN DE FUNCIONES  
\--------------------------------------------------

\#\#\# CPF-SGF-001

Aprobador ≠ Ejecutor.

\---

\#\#\# CPF-SGF-002

Ejecutor ≠ Pagador.

\---

\#\#\# CPF-SGF-003

Intento de bypass.

Resultado esperado:

Bloqueado.

\--------------------------------------------------  
23\. AUDITORÍA FINANCIERA  
\--------------------------------------------------

\#\#\# CPF-AUD-001

Todo movimiento genera auditoría.

\---

\#\#\# CPF-AUD-002

Toda liquidación genera auditoría.

\---

\#\#\# CPF-AUD-003

Todo pago genera auditoría.

\--------------------------------------------------  
24\. ESCENARIOS DE BORDE  
\--------------------------------------------------

Validar:

\- valores mínimos;  
\- valores máximos;  
\- cero movimientos;  
\- millones de movimientos;  
\- usuarios suspendidos;  
\- usuarios eliminados lógicamente.

\--------------------------------------------------  
25\. MATRIZ DE COBERTURA  
\--------------------------------------------------

Toda regla financiera deberá vincularse con:

\- caso de prueba;  
\- evidencia;  
\- resultado.

\--------------------------------------------------  
26\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Todo flujo financiero de Tu Mobil Amigo deberá demostrar exactitud matemática, trazabilidad completa, resistencia al fraude y consistencia transaccional antes de ser liberado a producción.  

Fin de Documento 38A — Casos de Prueba Financieros

\# Documento 39 — Validaciones

Versión: 1.0  
Estado: Aprobado  
Proyecto: Tu Mobil Amigo V1.0

\--------------------------------------------------  
1\. OBJETIVO  
\--------------------------------------------------

Definir las validaciones obligatorias que deberán ejecutarse antes de permitir operaciones dentro del ecosistema Tu Mobil Amigo.

Toda acción relevante deberá superar las validaciones correspondientes.

\--------------------------------------------------  
2\. PRINCIPIO RECTOR  
\--------------------------------------------------

Ninguna operación crítica deberá ejecutarse únicamente por confianza.

Toda operación deberá validarse.

\--------------------------------------------------  
3\. ALCANCE  
\--------------------------------------------------

Aplica a:

\- Usuarios.  
\- Servicios.  
\- Negociación.  
\- Trust Score.  
\- IMF.  
\- Cashback.  
\- Multinivel.  
\- Liquidaciones.  
\- APIs.  
\- Seguridad.  
\- Integraciones.

\--------------------------------------------------  
4\. TIPOS DE VALIDACIÓN  
\--------------------------------------------------

Se clasifican en:

\`\`\`text  
FUNCIONAL

NEGOCIO

FINANCIERA

SEGURIDAD

OPERATIVA

LEGAL  
\`\`\`

\--------------------------------------------------  
5\. VALIDACIONES DE USUARIO  
\--------------------------------------------------

Verificar:

\- existencia;  
\- estado;  
\- permisos;  
\- rol.

\--------------------------------------------------  
6\. VALIDACIONES DE AUTENTICACIÓN  
\--------------------------------------------------

Verificar:

\- identidad;  
\- sesión activa;  
\- MFA cuando aplique.

\--------------------------------------------------  
7\. VALIDACIONES DE AUTORIZACIÓN  
\--------------------------------------------------

Verificar:

\- rol;  
\- permisos;  
\- alcance autorizado.

\--------------------------------------------------  
8\. VALIDACIONES DE DISPOSITIVO  
\--------------------------------------------------

Verificar:

\- dispositivo registrado;  
\- estado;  
\- reputación;  
\- riesgo.

\--------------------------------------------------  
9\. VALIDACIONES DE SERVICIOS  
\--------------------------------------------------

Verificar:

\- origen válido;  
\- destino válido;  
\- ciudad activa;  
\- parámetros activos.

\--------------------------------------------------  
10\. VALIDACIONES DE NEGOCIACIÓN  
\--------------------------------------------------

Verificar:

\- límites tarifarios;  
\- tiempo de vigencia;  
\- elegibilidad.

\--------------------------------------------------  
11\. VALIDACIONES DE TARIFA  
\--------------------------------------------------

Verificar:

\- existencia de parámetros;  
\- vigencia;  
\- consistencia.

\--------------------------------------------------  
12\. VALIDACIONES DE CIUDAD  
\--------------------------------------------------

Verificar:

\- ciudad activa;  
\- configuración disponible.

\--------------------------------------------------  
13\. VALIDACIONES DE TRUST SCORE  
\--------------------------------------------------

Verificar:

\- rango permitido;  
\- consistencia histórica.

\--------------------------------------------------  
14\. VALIDACIONES DE IMF  
\--------------------------------------------------

Verificar:

\- nivel vigente;  
\- requisitos mínimos;  
\- reglas de maduración.

\--------------------------------------------------  
15\. VALIDACIONES DE CASHBACK  
\--------------------------------------------------

Verificar:

\- elegibilidad;  
\- porcentaje vigente;  
\- estado del servicio.

\--------------------------------------------------  
16\. VALIDACIONES MULTINIVEL  
\--------------------------------------------------

Verificar:

\- patrocinador válido;  
\- patrocinador activo;  
\- cumplimiento normativo.

\--------------------------------------------------  
17\. VALIDACIONES DE INCENTIVOS  
\--------------------------------------------------

Verificar:

\- cumplimiento de condiciones;  
\- maduración.

\--------------------------------------------------  
18\. VALIDACIONES DE LIQUIDACIÓN  
\--------------------------------------------------

Verificar:

\- usuario válido;  
\- período válido;  
\- movimientos conciliados.

\--------------------------------------------------  
19\. VALIDACIONES DE LIQUIDACIÓN EXTRAORDINARIA  
\--------------------------------------------------

Verificar:

\- autorización;  
\- justificación;  
\- trazabilidad.

\--------------------------------------------------  
20\. VALIDACIONES DE PAGO  
\--------------------------------------------------

Verificar:

\- monto;  
\- destinatario;  
\- autorización.

\--------------------------------------------------  
21\. VALIDACIONES DE REPORTE  
\--------------------------------------------------

Verificar:

\- integridad;  
\- consistencia;  
\- trazabilidad.

\--------------------------------------------------  
22\. VALIDACIONES DE API  
\--------------------------------------------------

Verificar:

\- token;  
\- permisos;  
\- límites.

\--------------------------------------------------  
23\. VALIDACIONES DE RATE LIMIT  
\--------------------------------------------------

Verificar:

\- frecuencia;  
\- origen;  
\- riesgo.

\--------------------------------------------------  
24\. VALIDACIONES DE SEGURIDAD  
\--------------------------------------------------

Verificar:

\- intentos fallidos;  
\- accesos sospechosos;  
\- patrones anómalos.

\--------------------------------------------------  
25\. VALIDACIONES ANTIFRAUDE  
\--------------------------------------------------

Verificar:

\- multicuentas;  
\- abuso de beneficios;  
\- manipulación.

\--------------------------------------------------  
26\. VALIDACIONES DE VPN  
\--------------------------------------------------

Verificar:

\- VPN;  
\- Proxy;  
\- TOR;  
\- Datacenter IP.

\--------------------------------------------------  
27\. VALIDACIONES DE GEOLOCALIZACIÓN  
\--------------------------------------------------

Verificar:

\- coherencia operativa;  
\- consistencia geográfica.

\--------------------------------------------------  
28\. VALIDACIONES DE INTEGRACIONES  
\--------------------------------------------------

Verificar:

\- disponibilidad;  
\- respuesta;  
\- autenticación.

\--------------------------------------------------  
29\. VALIDACIONES DE TELEGRAM  
\--------------------------------------------------

Verificar:

\- identidad;  
\- disponibilidad;  
\- permisos.

\--------------------------------------------------  
30\. VALIDACIONES DE OPENSTREETMAP  
\--------------------------------------------------

Verificar:

\- respuesta válida;  
\- coordenadas válidas.

\--------------------------------------------------  
31\. VALIDACIONES DE GRAPHHOPPER  
\--------------------------------------------------

Verificar:

\- cálculo correcto;  
\- disponibilidad.

\--------------------------------------------------  
32\. VALIDACIONES FINANCIERAS  
\--------------------------------------------------

Verificar:

\- integridad;  
\- conciliación;  
\- trazabilidad.

\--------------------------------------------------  
33\. VALIDACIONES DE CONCILIACIÓN  
\--------------------------------------------------

Verificar:

\- coincidencia de movimientos;  
\- diferencias.

\--------------------------------------------------  
34\. VALIDACIONES DE AUDITORÍA  
\--------------------------------------------------

Verificar:

\- existencia de evidencia;  
\- consistencia.

\--------------------------------------------------  
35\. VALIDACIONES DE CONFIGURACIÓN  
\--------------------------------------------------

Verificar:

\- parámetros obligatorios;  
\- vigencia.

\--------------------------------------------------  
36\. VALIDACIONES DE ADMINISTRADOR  
\--------------------------------------------------

Verificar:

\- permisos;  
\- alcance autorizado.

\--------------------------------------------------  
37\. VALIDACIONES DE SUPERADMINISTRADOR  
\--------------------------------------------------

Verificar:

\- autenticación reforzada;  
\- trazabilidad obligatoria.

\--------------------------------------------------  
38\. VALIDACIONES DE EXPORTACIÓN  
\--------------------------------------------------

Verificar:

\- formato;  
\- contenido;  
\- integridad.

\--------------------------------------------------  
39\. VALIDACIONES DE RECUPERACIÓN  
\--------------------------------------------------

Verificar:

\- restauración;  
\- consistencia posterior.

\--------------------------------------------------  
40\. VALIDACIONES DE BACKUP  
\--------------------------------------------------

Verificar:

\- existencia;  
\- completitud;  
\- recuperabilidad.

\--------------------------------------------------  
41\. VALIDACIONES DE REPROCESAMIENTO  
\--------------------------------------------------

Verificar:

\- no duplicidad;  
\- integridad.

\--------------------------------------------------  
42\. VALIDACIONES DE REVERSIONES  
\--------------------------------------------------

Verificar:

\- autorización;  
\- trazabilidad;  
\- auditoría.

\--------------------------------------------------  
43\. VALIDACIONES DE CONCURRENCIA  
\--------------------------------------------------

Verificar:

\- bloqueos;  
\- consistencia;  
\- integridad transaccional.

\--------------------------------------------------  
44\. VALIDACIONES DE ESTADO  
\--------------------------------------------------

Toda transición deberá validar:

\- origen;  
\- destino;  
\- reglas permitidas.

\--------------------------------------------------  
45\. VALIDACIONES DE DATOS  
\--------------------------------------------------

Verificar:

\- obligatoriedad;  
\- formato;  
\- unicidad.

\--------------------------------------------------  
46\. VALIDACIONES DE BASE DE DATOS  
\--------------------------------------------------

Verificar:

\- constraints;  
\- funciones;  
\- triggers.

\--------------------------------------------------  
47\. VALIDACIONES PREVIAS A PRODUCCIÓN  
\--------------------------------------------------

Toda versión deberá aprobar:

\- pruebas;  
\- seguridad;  
\- auditoría.

\--------------------------------------------------  
48\. VALIDACIONES DE CUMPLIMIENTO  
\--------------------------------------------------

Verificar:

\- normativas aplicables;  
\- políticas internas.

\--------------------------------------------------  
49\. MATRIZ DE VALIDACIONES  
\--------------------------------------------------

Toda regla de negocio deberá asociarse a:

\- validación;  
\- evidencia;  
\- resultado.

\--------------------------------------------------  
50\. Validaciones de Operaciones Superadministrativas  
\--------------------------------------------------
Verificar:
Rol del ejecutor antes de permitir reapertura o liquidación extraordinaria.
Justificación obligatoria no vacía en toda reapertura.
Integridad del período: un período ya reabierto y recalculado no podrá reabrirse nuevamente sin nueva justificación independiente.

\--------------------------------------------------  
51\. PRINCIPIO RECTOR FINAL  
\--------------------------------------------------

Toda operación ejecutada dentro de Tu Mobil Amigo deberá cumplir previamente las validaciones funcionales, operativas, financieras, legales y de seguridad definidas por la arquitectura, garantizando integridad, trazabilidad y protección del ecosistema.  

Fin de Documento 39 — Validaciones
