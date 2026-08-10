# PROMPT DE CONTINUIDAD — REINICIO DE CHAT DEL PROYECTO

## PROPÓSITO

Este prompt se utiliza al iniciar una NUEVA SESIÓN de un proyecto existente.

Su objetivo es recuperar correctamente el estado persistente del proyecto y continuar el trabajo sin depender de la memoria de la conversación anterior.

La nueva sesión debe reconstruir el contexto utilizando las fuentes persistentes del proyecto.

Las fuentes principales son:

GitHub
→ fuente de verdad

Documentación
→ cómo debe funcionar

Código
→ cómo funciona realmente

CURRENT.md
→ dónde quedamos

HISTORIAL
→ por qué llegamos hasta ahí


# 1. PRINCIPIO FUNDAMENTAL

No comenzar inmediatamente a trabajar sobre el proyecto.

Primero debes recuperar y verificar el contexto.

La nueva sesión debe determinar:

- qué proyecto está trabajando;
- qué documentación corresponde;
- cuál es el módulo actual;
- cuál era el estado del módulo;
- qué trabajo ya fue realizado;
- qué quedó pendiente;
- qué bloqueos existen;
- por qué terminó la sesión anterior;
- cuál es el próximo paso;
- si debe continuar el módulo actual;
- si debe iniciar el siguiente módulo.


# 2. FUENTES DEL PROYECTO

Los enlaces proporcionados al iniciar esta sesión deben considerarse las referencias oficiales del proyecto.

Normalmente existirán estas ubicaciones principales:

### FUENTE 01 — PROMPTS UNIVERSALES

https://github.com/tumobilamigo-beep/TMA_Docs/tree/c378a0b56e4172131fbf602ee844cb34b5f6a23f/Promts%20Universales

### FUENTE 02 — ÁRBOL DE DOCUMENTACIÓN

https://github.com/tumobilamigo-beep/TMA_Docs/tree/0e5fba4369e155968e40a41a71ee369930e41553/Arbol%20de%20documentaci%C3%B3n

### FUENTE 03 — GOBIERNO DEL PROYECTO

https://github.com/tumobilamigo-beep/TMA_Docs/tree/a8ab05166c5afb51d7200ae85819d5a53e76cfb2/Arbol%20de%20documentaci%C3%B3n/00_Gobierno_Proyecto

### FUENTE 04 — CÓDIGO DEL PROYECTO

[PEGAR AQUÍ EL LINK DEL REPOSITORIO DEL CÓDIGO]

### FUENTE 05 — CONTEXTO

https://github.com/tumobilamigo-beep/TMA_Docs/tree/0256136bcc0d78524f0461d6e993a64b2f4c0aaa/CONTEXTO

### FUENTE 06 — HISTORIAL

https://github.com/tumobilamigo-beep/TMA_Docs/tree/b30b2ac124ab837130f4c1ab996f51e7afad83cd/CONTEXTO/Historial

### FUENTE 07 — CURRENT.md

https://github.com/tumobilamigo-beep/TMA_Docs/blob/b30b2ac124ab837130f4c1ab996f51e7afad83cd/CONTEXTO/Current.md

No volver a solicitar estos enlaces si ya fueron proporcionados dentro del prompt.

Utilizarlos como referencias durante toda la sesión.


# 3. UBICACIÓN DE LA INFORMACIÓN DEL PROYECTO

Toda la información específica del proyecto se encuentra dentro del:

Árbol de Documentación

Dentro de este árbol existe la carpeta:

Gobierno_Proyecto

Esta carpeta contiene la información global específica que la IA necesita para comprender:

- qué es el proyecto;
- qué se pretende construir;
- objetivos;
- alcance;
- reglas;
- arquitectura;
- decisiones generales;
- información necesaria para gobernar el proyecto.

Los demás módulos contienen la información específica correspondiente a cada fase.


# 4. NO CARGAR TODO INNECESARIAMENTE

No es obligatorio leer nuevamente toda la documentación histórica del proyecto.

Primero debes identificar qué información es necesaria para continuar.

Utilizar:

CURRENT.md
→ para determinar dónde estamos.

Después consultar:

documentación del módulo actual
→ para determinar qué debe hacerse.

Después consultar:

código relevante
→ para determinar qué existe realmente.

Consultar HISTORIAL
→ para comprender decisiones o situaciones que CURRENT.md no explique suficientemente.


# 5. ORDEN DE RECUPERACIÓN

Utilizar el siguiente orden:

1. Identificar el proyecto.
2. Leer la información relevante de `Gobierno_Proyecto`.
3. Localizar `CURRENT.md`.
4. Leer el CURRENT vigente.
5. Determinar el módulo actual.
6. Identificar el estado del módulo.
7. Identificar el motivo del último cierre.
8. Identificar el estado de transición.
9. Consultar la documentación específica del módulo.
10. Consultar el código relevante.
11. Consultar HISTORIAL cuando sea necesario.
12. Comparar la información.
13. Determinar el punto real de continuidad.

# VERIFICACIÓN DE ACCESO DURANTE LA CONTINUIDAD

Antes de reconstruir el contexto de la sesión anterior debes verificar que tienes acceso a las fuentes necesarias para continuar.

Debes comprobar especialmente:

- repositorio de código;
- Árbol de Documentación;
- `Gobierno_Proyecto`;
- documentación del módulo actual;
- `CURRENT.md`;
- HISTORIAL relevante;
- cualquier otro documento referenciado por CURRENT o HISTORIAL.

Si alguno de estos recursos no está disponible, debes informarlo explícitamente antes de continuar.

NO debes asumir que una fuente fue consultada simplemente porque aparece mencionada en `CURRENT.md`, HISTORIAL o en el prompt.

Diferencia claramente entre:

✅ ACCESIBLE
→ puedes consultar directamente la fuente.

⚠️ REFERENCIADO PERO NO ACCESIBLE
→ sabes que existe porque otra fuente lo menciona, pero no puedes consultarlo.

❌ NO ENCONTRADO
→ no has podido localizarlo.

⚠️ REQUIERE VERIFICACIÓN
→ existe información relacionada, pero no puedes confirmar que corresponde a la versión vigente.


## FORMATO DE REPORTE

Si existe alguna fuente no accesible, informa:

FUENTE:
[Nombre]

TIPO:
[Repositorio / carpeta / documento / archivo]

UBICACIÓN:
[Ruta o enlace]

ESTADO:
[ACCESIBLE / REFERENCIADO PERO NO ACCESIBLE / NO ENCONTRADO / REQUIERE VERIFICACIÓN]

IMPACTO:
[Qué información no puede verificarse]

ACCIÓN NECESARIA:
[Qué debe proporcionar o habilitar el usuario]


## REGLA DE CONTINUIDAD

Si la fuente faltante es crítica para determinar correctamente el estado del proyecto:

NO debes inventar el contexto faltante.

Debes detener la parte del proceso que dependa de dicha fuente e informar al usuario.

Si la fuente faltante NO es crítica para continuar:

puedes continuar con las fuentes disponibles, pero debes indicar claramente qué información permanece sin verificar.

# 6. CURRENT.md ES EL PUNTO DE ENTRADA

`CURRENT.md` debe ser utilizado inicialmente para determinar:

¿Dónde quedamos?

No asumir que toda la conversación anterior es necesaria.

Utilizar CURRENT para identificar:

- proyecto;
- módulo;
- estado;
- último trabajo;
- resultado;
- pendientes;
- bloqueos;
- próximo paso;
- transición.


# 7. VERIFICAR CURRENT

No asumir automáticamente que CURRENT.md es correcto.

Compararlo con las fuentes relevantes cuando sea necesario:

CURRENT
↓
Documentación
↓
Código
↓
HISTORIAL


Si existe una contradicción:

no ignorarla.

Determinar cuál información puede verificarse.


# 8. INTERPRETAR EL ESTADO DE TRANSICIÓN

CURRENT.md puede indicar:

CONTINUAR MÓDULO ACTUAL

INICIAR SIGUIENTE MÓDULO

ESPERAR RESOLUCIÓN DE BLOQUEO

REQUIERE VERIFICACIÓN


La nueva sesión debe respetar esta transición salvo que exista evidencia verificable que demuestre que el estado cambió.


# 9. CONTINUAR MÓDULO ACTUAL

Si CURRENT indica:

CONTINUAR MÓDULO ACTUAL

debes:

1. identificar el módulo;
2. leer la documentación correspondiente;
3. revisar el último trabajo realizado;
4. revisar pendientes;
5. revisar bloqueos;
6. revisar el código relevante;
7. determinar el próximo paso;
8. continuar desde ese punto.

NO reiniciar el módulo desde cero.


# 10. INICIAR SIGUIENTE MÓDULO

Si CURRENT indica:

INICIAR SIGUIENTE MÓDULO

debes:

1. confirmar que el módulo anterior realmente está COMPLETADO;
2. identificar el siguiente módulo según el Árbol de Documentación;
3. localizar su documentación;
4. leer la información específica necesaria;
5. identificar los requisitos de entrada;
6. revisar dependencias;
7. revisar el código relacionado;
8. determinar el primer paso del nuevo módulo.

No asumir que el siguiente módulo puede comenzar sin verificar sus dependencias.


# 11. ESPERAR RESOLUCIÓN DE BLOQUEO

Si CURRENT indica:

ESPERAR RESOLUCIÓN DE BLOQUEO

debes:

1. identificar el bloqueo;
2. consultar el HISTORIAL correspondiente;
3. consultar documentación y código relevantes;
4. determinar si el bloqueo continúa;
5. si continúa, no avanzar artificialmente;
6. si fue resuelto, actualizar el estado correspondiente antes de continuar.


# 12. REQUIERE VERIFICACIÓN

Si CURRENT indica:

REQUIERE VERIFICACIÓN

debes identificar qué información requiere verificación.

Consultar las fuentes correspondientes:

- documentación;
- código;
- historial;
- requisitos;
- configuración.

No asumir que la información es correcta hasta verificarla.


# 13. RELACIÓN CON HISTORIAL

HISTORIAL no debe utilizarse automáticamente como sustituto de CURRENT.

Su función es explicar:

- decisiones;
- problemas;
- descubrimientos;
- cambios;
- soluciones;
- contradicciones;
- consecuencias.

Consultar HISTORIAL cuando:

- CURRENT no sea suficiente;
- exista una contradicción;
- una decisión requiera explicación;
- exista un bloqueo;
- sea necesario comprender por qué se llegó al estado actual.


# 14. NO RECONSTRUIR TODO EL HISTORIAL

No leer innecesariamente todo el historial del proyecto.

Priorizar:

1. historial relacionado con el módulo actual;
2. historial relacionado con el último cambio;
3. historial relacionado con decisiones que afectan la continuidad;
4. historial relacionado con bloqueos.

Expandir la consulta solamente cuando sea necesario.


# 15. RELACIÓN CON EL CÓDIGO

La documentación indica:

cómo debería funcionar.

El código indica:

cómo funciona realmente.

Antes de continuar una implementación:

consultar el código relevante cuando sea necesario.

No asumir que una funcionalidad está implementada solamente porque la documentación indique que debería existir.


# 16. RELACIÓN CON LA DOCUMENTACIÓN

La documentación específica del módulo determina:

- objetivos;
- requisitos;
- comportamiento esperado;
- restricciones;
- dependencias;
- criterios de finalización.

La documentación tiene prioridad sobre suposiciones derivadas de conversaciones anteriores.


# 17. VERIFICACIÓN DEL ESTADO REAL

Después de revisar las fuentes, determinar:

### Estado documental
¿Qué debería existir?

### Estado del código
¿Qué existe realmente?

### Estado operativo
¿Dónde quedó el trabajo?

### Estado histórico
¿Por qué se llegó a ese punto?

Si todos son coherentes:

continuar.

Si existen contradicciones:

detener la inferencia automática y determinar qué debe verificarse.


# 18. NO INVENTAR CONTINUIDAD

No inventar:

- tareas realizadas;
- funcionalidades existentes;
- decisiones;
- resultados;
- módulos completados;
- criterios cumplidos;
- soluciones;
- próximos pasos no sustentados.

Si no existe información suficiente:

indicar:

INFORMACIÓN INSUFICIENTE PARA DETERMINAR EL ESTADO


# 19. PRIMERA RESPUESTA DEL NUEVO CHAT

Después de analizar las fuentes, NO comenzar inmediatamente con una implementación extensa.

Primero presentar un resumen operativo:

PROYECTO:
[Nombre]

MÓDULO:
[Módulo]

ESTADO:
[Estado]

ÚLTIMO RESULTADO:
[Resultado]

PENDIENTES:
[Pendientes]

BLOQUEOS:
[Si existen]

MOTIVO DEL ÚLTIMO CIERRE:
[Motivo]

TRANSICIÓN:
[Continuar / siguiente módulo / bloqueo / verificación]

PRÓXIMO PASO:
[Acción]

FUENTES CONSULTADAS:
[Documentación / código / CURRENT / HISTORIAL]


# 20. CONFIRMACIÓN DE CONTINUIDAD

Después del resumen anterior, comenzar el trabajo correspondiente según el estado recuperado.

No solicitar al usuario que vuelva a explicar toda la historia del proyecto cuando la información ya esté disponible en las fuentes.


# 21. SI EL ÚLTIMO CIERRE FUE POR CONTEXTO

Si CURRENT indica:

Motivo:
CONTEXTO AGOTADO

y:

Estado del módulo:
EN PROGRESO

entonces:

NO iniciar un módulo nuevo.

Continuar exactamente desde el módulo actual.

Utilizar los pendientes y el próximo paso registrados en CURRENT.


# 22. SI EL ÚLTIMO CIERRE FUE POR FINALIZACIÓN DEL MÓDULO

Si CURRENT indica:

Estado:
COMPLETADO

y:

Transición:
INICIAR SIGUIENTE MÓDULO

entonces:

iniciar la recuperación del siguiente módulo.

No volver a desarrollar innecesariamente el módulo anterior.


# 23. SI EL CIERRE FUE MANUAL

Determinar el estado real del módulo.

No asumir que estaba terminado.

Utilizar CURRENT, documentación, código e HISTORIAL para establecer la continuidad.


# 24. SI EXISTE UN CURRENT ANTIGUO

No asumir que el archivo más recientemente modificado sea necesariamente el correcto.

Verificar:

- contenido;
- fecha o versión cuando sea relevante;
- coherencia con historial;
- coherencia con código;
- coherencia con documentación.

El contenido debe tener prioridad sobre una simple fecha de modificación.


# 25. SI EXISTEN VARIOS REGISTROS DE HISTORIAL

Identificar el historial correspondiente al último estado conocido.

No mezclar automáticamente eventos de diferentes módulos.

Priorizar los registros relacionados con el módulo actual.


# 26. GESTIÓN DEL CONTEXTO DURANTE LA NUEVA SESIÓN

Esta sesión debe aplicar las reglas establecidas en:

PROMPT UNIVERSAL 05 — GESTIÓN ACTIVA DEL CONTEXTO

La nueva sesión debe comenzar a vigilar el contexto desde el inicio.

No esperar a que el contexto esté cerca del límite para comenzar la gestión.


# 27. NO DUPLICAR EL GESTOR DE CONTEXTO

Este prompt no redefine:

- cálculo de tokens;
- límites de contexto;
- porcentajes;
- estados de consumo.

Esas reglas pertenecen exclusivamente al:

PROMPT UNIVERSAL 05 — GESTIÓN ACTIVA DEL CONTEXTO


# 28. CUANDO EL NUEVO CHAT NECESITE CERRAR

Si durante esta nueva sesión el contexto se aproxima a su límite:

utilizar:

PROMPT — CIERRE DE SESIÓN Y GENERACIÓN DE CURRENT.md E HISTORIAL

para preservar el estado.

Después de generar los documentos:

la siguiente sesión volverá a utilizar este PROMPT DE CONTINUIDAD.


# 29. TRANSICIÓN ENTRE MÓDULOS

Cuando un módulo esté completado:

CURRENT deberá indicar:

Estado:
COMPLETADO

y:

Estado de transición:
INICIAR SIGUIENTE MÓDULO

La siguiente sesión deberá entonces:

1. confirmar el cierre del módulo anterior;
2. localizar el siguiente módulo;
3. leer su documentación;
4. identificar sus dependencias;
5. revisar el estado del código;
6. determinar el punto de inicio.


# 30. NO SALTAR MÓDULOS

No saltar automáticamente módulos definidos en el Árbol de Documentación.

Si se requiere cambiar el orden:

debe existir una decisión explícita o una regla del proyecto que lo justifique.

Si existe una dependencia que obliga a modificar el orden:

registrarla como decisión.


# 31. CAMBIO DE MÓDULO

Al iniciar un nuevo módulo:

identificar explícitamente:

Módulo anterior:
[Nombre]

Estado:
COMPLETADO

Nuevo módulo:
[Nombre]

Objetivo:
[Objetivo del módulo]

Dependencias:
[Dependencias]

Documentación:
[Documentos relevantes]

Código relacionado:
[Componentes relevantes]


# 32. GOBIERNO DEL PROYECTO

Antes de iniciar un módulo nuevo, consultar la información relevante de:

Gobierno_Proyecto

cuando sea necesaria para mantener coherencia con:

- objetivos;
- alcance;
- reglas;
- arquitectura;
- decisiones globales;
- restricciones.


# 33. PRINCIPIO DE MÍNIMA CARGA DE CONTEXTO

No cargar información innecesaria.

El objetivo es obtener suficiente contexto para trabajar correctamente sin consumir innecesariamente la ventana disponible.

Prioridad:

1. Gobierno_Proyecto cuando sea relevante;
2. CURRENT;
3. documentación del módulo;
4. código relevante;
5. HISTORIAL relevante;
6. documentación adicional solamente cuando sea necesaria.


# 34. DETECCIÓN DE CONTRADICCIONES

Si encuentras:

CURRENT ≠ HISTORIAL

o:

CURRENT ≠ DOCUMENTACIÓN

o:

DOCUMENTACIÓN ≠ CÓDIGO

o:

HISTORIAL ≠ CÓDIGO

no ocultes la contradicción.

Indica:

CONTRADICCIÓN DETECTADA

y explica:

- fuentes involucradas;
- diferencia;
- qué evidencia existe;
- qué debe verificarse.


# 35. NO MODIFICAR DOCUMENTOS DURANTE LA RECUPERACIÓN

La recuperación de contexto no implica automáticamente modificar:

- CURRENT;
- HISTORIAL;
- documentación;
- código.

Primero recuperar y comprender.

Modificar solamente cuando:

- sea parte de la tarea;
- exista una contradicción que deba corregirse;
- el usuario lo solicite;
- o corresponda al flujo definido para una actualización.


# 36. RESULTADO ESPERADO

Al finalizar la fase de recuperación, debes poder responder con seguridad:

¿QUÉ PROYECTO ESTAMOS TRABAJANDO?

¿EN QUÉ MÓDULO ESTAMOS?

¿CUÁL ES EL ESTADO REAL?

¿QUÉ SE HIZO?

¿QUÉ RESULTADO SE OBTUVO?

¿QUÉ QUEDÓ PENDIENTE?

¿EXISTEN BLOQUEOS?

¿POR QUÉ TERMINÓ LA SESIÓN ANTERIOR?

¿DEBEMOS CONTINUAR EL MÓDULO?

¿DEBEMOS INICIAR EL SIGUIENTE?

¿QUÉ DEBEMOS HACER AHORA?


# 37. PRINCIPIO FINAL

La nueva sesión no comienza desde cero.

Comienza desde el estado persistente del proyecto.

La recuperación debe seguir:

GitHub
↓
fuente de verdad

Gobierno_Proyecto
↓
contexto global del proyecto

CURRENT.md
↓
dónde quedamos

Documentación del módulo
↓
cómo debe funcionar

Código
↓
cómo funciona realmente

HISTORIAL
↓
por qué llegamos hasta ahí

Estado verificado
↓
punto de continuidad

Después:

CONTINUAR MÓDULO ACTUAL

o:

INICIAR SIGUIENTE MÓDULO

según corresponda.


# 38. REGLA FUNDAMENTAL DE CONTINUIDAD

Nunca confundir:

FIN DE CHAT
con
FIN DE MÓDULO

Si terminó el chat por contexto:

→ recuperar CURRENT
→ continuar el módulo actual.

Si terminó el módulo:

→ verificarlo
→ consultar el siguiente módulo
→ iniciar la nueva fase.

El objetivo de este prompt es que el nuevo chat pueda continuar el proyecto exactamente desde donde quedó, sin perder el contexto persistente y sin reconstruir innecesariamente toda la conversación anterior.
