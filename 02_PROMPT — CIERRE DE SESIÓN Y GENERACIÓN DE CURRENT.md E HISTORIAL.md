# PROMPT — CIERRE DE SESIÓN Y GENERACIÓN DE CURRENT.md E HISTORIAL

## PROPÓSITO

Este prompt se utiliza cuando una sesión de trabajo debe finalizar y es necesario preservar correctamente el estado del proyecto para una futura sesión.

Puede utilizarse cuando:

- el contexto está próximo a agotarse;
- el contexto se agotó;
- se realiza un cierre preventivo;
- se finalizó una sesión manualmente;
- se completó un módulo;
- se produjo un bloqueo;
- se requiere preservar el estado antes de continuar en otro chat.

Su función es convertir el estado REAL de la sesión en información persistente mediante:

1. actualización de `CURRENT.md`;
2. generación del registro correspondiente de `HISTORIAL`.

La estructura y reglas de ambos documentos están definidas en:

PROMPT UNIVERSAL 04 — GESTIÓN DE CURRENT.md E HISTORIAL

La gestión del consumo de contexto está definida en:

PROMPT UNIVERSAL 05 — GESTIÓN ACTIVA DEL CONTEXTO


# 1. PRINCIPIO FUNDAMENTAL

Antes de generar los documentos debes determinar qué ocurrió REALMENTE durante la sesión.

No debes generar documentos basándote únicamente en:

- la intención inicial;
- planes que no fueron ejecutados;
- propuestas;
- suposiciones;
- conversaciones hipotéticas.

Debes distinguir entre:

REALIZADO
→ ocurrió realmente.

PROPUESTO
→ fue sugerido pero no necesariamente implementado.

DECIDIDO
→ fue aceptado como decisión.

DESCARTADO
→ fue considerado y rechazado.

PENDIENTE
→ todavía no fue realizado.

NO VERIFICADO
→ no existe evidencia suficiente.


# 2. FUENTES QUE DEBES UTILIZAR

Para preparar el cierre utiliza, en el siguiente orden lógico:

1. conversación actual;
2. documentación del proyecto relevante;
3. código relevante;
4. `CURRENT.md` existente;
5. `HISTORIAL` relevante.

La conversación permite identificar qué ocurrió durante la sesión.

La documentación determina cómo debería funcionar el proyecto.

El código determina cómo funciona realmente.

`CURRENT.md` determina dónde estaba el proyecto antes de esta sesión.

`HISTORIAL` permite comprender por qué llegó a ese estado.


# 3. NO MODIFICAR LA FUENTE DE VERDAD

Este prompt no debe modificar arbitrariamente:

- documentación;
- arquitectura;
- requisitos;
- código;
- decisiones previamente establecidas.

Si durante el análisis aparece una contradicción:

1. identificarla;
2. documentarla;
3. no ocultarla;
4. no inventar una resolución.

La contradicción debe quedar registrada en HISTORIAL y, cuando afecte a la continuidad, reflejarse también en CURRENT.md.


# 4. IDENTIFICAR EL MÓDULO

Antes de generar los documentos determina:

- proyecto;
- módulo actual;
- ruta del módulo dentro del Árbol de Documentación;
- estado real del módulo.

Estados válidos por defecto:

- NO INICIADO
- EN PROGRESO
- COMPLETADO
- BLOQUEADO

No marcar un módulo como COMPLETADO únicamente porque esta sesión terminó.


# 5. DETERMINAR EL TIPO DE CIERRE

Determina cuál de las siguientes situaciones corresponde:

- CONTEXTO AGOTADO
- CIERRE PREVENTIVO
- MÓDULO COMPLETADO
- CIERRE MANUAL
- BLOQUEO
- CAMBIO DE SESIÓN
- OTRO

Si no existe evidencia suficiente:

NO VERIFICADO


# 6. DIFERENCIAR SESIÓN Y MÓDULO

Esta distinción es obligatoria.

Una sesión puede terminar mientras el módulo continúa.

Ejemplo:

Módulo:
03_Backend

Estado:
EN PROGRESO

Motivo:
CONTEXTO AGOTADO

Resultado:

La sesión termina.

El módulo NO termina.

CURRENT debe establecer:

Estado del módulo:
EN PROGRESO

Estado de transición:
CONTINUAR MÓDULO ACTUAL


# 7. DETERMINAR SI EL MÓDULO TERMINÓ

Antes de marcar un módulo como COMPLETADO debes verificar:

- criterios de finalización definidos por el proyecto;
- trabajo requerido;
- resultados obtenidos;
- pruebas o verificaciones necesarias;
- pendientes que puedan impedir considerar terminada la fase.

Si existen dudas:

NO marcar como COMPLETADO.


# 8. DETERMINAR LA TRANSICIÓN

Una vez determinado el estado real, establecer una de estas transiciones:

CONTINUAR MÓDULO ACTUAL

INICIAR SIGUIENTE MÓDULO

ESPERAR RESOLUCIÓN DE BLOQUEO

REQUIERE VERIFICACIÓN


# 9. REGLA DE CONTINUIDAD POR CONTEXTO

Si el cierre se produce por contexto insuficiente:

- conservar el módulo actual;
- mantener su estado real;
- registrar el trabajo realizado;
- registrar el resultado;
- registrar pendientes;
- registrar bloqueos;
- registrar el motivo del cierre;
- establecer:

Estado de transición:
CONTINUAR MÓDULO ACTUAL

NO avanzar al siguiente módulo automáticamente.


# 10. REGLA DE FINALIZACIÓN DE MÓDULO

Si el módulo fue realmente completado:

- marcarlo como COMPLETADO;
- registrar el resultado;
- registrar decisiones;
- registrar pendientes residuales;
- identificar el siguiente módulo;
- establecer:

Estado de transición:
INICIAR SIGUIENTE MÓDULO

El siguiente chat deberá ser informado de que corresponde iniciar la siguiente fase.


# 11. REGLA DE BLOQUEO

Si existe un bloqueo:

- marcar el módulo como BLOQUEADO;
- describir el problema;
- explicar por qué impide continuar;
- indicar qué se necesita para resolverlo;
- conservar el módulo actual;
- establecer:

Estado de transición:
ESPERAR RESOLUCIÓN DE BLOQUEO


# 12. ACTUALIZACIÓN DE CURRENT.md

Si existe un `CURRENT.md` anterior:

NO debes crear automáticamente otro CURRENT.

Debes actualizar el existente.

Utiliza conceptualmente:

CURRENT ANTERIOR
+
CAMBIOS REALES DE LA SESIÓN
=
CURRENT ACTUALIZADO


# 13. CONTENIDO DE CURRENT.md

La actualización debe respetar la estructura definida por:

PROMPT UNIVERSAL 04

Como mínimo debe quedar determinado:

## Identificación del proyecto
[Proyecto]

## Estado general del proyecto
[Estado actual]

## Módulo / fase actual
[Módulo]

## Estado del módulo
[Estado]

## Estado de la sesión actual
[Estado]

## Motivo del último cierre
[Motivo]

## Último trabajo realizado
[Trabajo real]

## Resultado obtenido
[Resultado]

## Pendientes
[Pendientes]

## Bloqueos
[Bloqueos]

## Decisiones recientes
[Decisiones]

## Advertencias
[Advertencias]

## Próximo paso
[Acción concreta]

## Próximo módulo
[Si corresponde]

## Estado de transición
[Transición]

## Referencias de continuidad
[Fuentes necesarias]


# 14. REGLA DE ACTUALIDAD DE CURRENT

CURRENT.md representa el estado actual.

Por lo tanto:

- actualizar información que cambió;
- eliminar estados que ya no sean vigentes;
- conservar información que siga siendo válida;
- no acumular cronológicamente eventos antiguos.

La información histórica pertenece a HISTORIAL.


# 15. GENERACIÓN DEL HISTORIAL

Al finalizar una sesión debe generarse el registro histórico correspondiente cuando exista un evento relevante de cierre.

No sobrescribir registros históricos anteriores.

El nuevo registro debe conservarse según la estructura documental definida por el proyecto.


# 16. CONTENIDO DEL HISTORIAL

El registro deberá respetar la estructura definida en:

PROMPT UNIVERSAL 04 — GESTIÓN DE CURRENT.md E HISTORIAL

Debe registrar, cuando corresponda:

## Objetivo de la sesión
[Qué se pretendía conseguir]

## Estado inicial
[Situación al comenzar]

## Módulo / fase
[Módulo trabajado]

## Trabajo realizado
[Trabajo real]

## Descubrimientos
[Información nueva]

## Problemas encontrados
[Problemas]

## Soluciones aplicadas
[Soluciones]

## Decisiones tomadas
[Decisiones aceptadas]

## Cambios realizados
[Modificaciones]

## Alternativas consideradas y descartadas
[Alternativas]

## Contradicciones detectadas
[Contradicciones]

## Información pendiente de verificación
[Información no confirmada]

## Consecuencias para el proyecto
[Impacto]

## Estado del módulo al finalizar
[Estado]

## Estado final de la sesión
[Estado]

## Motivo del cierre
[Motivo]

## Próximo paso
[Acción]

## Próximo módulo
[Si corresponde]

## Estado de transición
[Transición]

## Referencias
[Fuentes relacionadas]


# 17. HISTORIAL NO DEBE SER UNA COPIA DE LA CONVERSACIÓN

No copiar:

- conversaciones completas;
- preguntas irrelevantes;
- respuestas completas;
- código completo;
- logs completos;
- explicaciones innecesarias.

El historial debe conservar la información necesaria para comprender:

QUÉ OCURRIÓ

POR QUÉ OCURRIÓ

QUÉ DECISIÓN SE TOMÓ

QUÉ CONSECUENCIA TUVO

QUÉ DEBE HACERSE DESPUÉS


# 18. CONSERVAR DECISIONES

Toda decisión relevante debe registrarse.

Para cada decisión importante indicar:

- decisión;
- motivo;
- impacto;
- estado.

Cuando sea necesario distinguir:

DECIDIDA
PROPUESTA
DESCARTADA
PENDIENTE


# 19. CONSERVAR CONTRADICCIONES

Si durante la sesión se detectó una contradicción entre:

- documentación;
- código;
- CURRENT;
- HISTORIAL;
- requisitos;
- decisiones;

debe registrarse.

No resolverla silenciosamente.


# 20. CONSERVAR BLOQUEOS

Si existe un bloqueo, el HISTORIAL debe explicar:

- qué ocurrió;
- cuándo fue detectado;
- qué lo provoca;
- qué se intentó;
- qué no funcionó;
- qué se necesita para resolverlo.

Esto permitirá que otra sesión pueda retomar el problema sin reconstruir toda la conversación.


# 21. CONSERVAR EL MOTIVO DEL CIERRE

El historial debe indicar explícitamente por qué terminó la sesión.

Ejemplo:

Motivo del cierre:
CONTEXTO AGOTADO

Esto no debe interpretarse como:

Módulo completado.


# 22. SI EL MÓDULO TERMINÓ

Cuando el módulo realmente haya terminado, registrar:

- criterios cumplidos;
- resultado;
- verificaciones realizadas;
- pendientes residuales;
- decisiones relevantes;
- siguiente módulo;
- transición.

La siguiente sesión deberá recibir la instrucción conceptual:

INICIAR SIGUIENTE MÓDULO


# 23. SI EL MÓDULO NO TERMINÓ

Registrar:

- estado EN PROGRESO;
- trabajo realizado;
- resultado;
- pendientes;
- próximo paso;
- referencias necesarias.

La siguiente sesión deberá recibir:

CONTINUAR MÓDULO ACTUAL


# 24. SI EXISTE BLOQUEO

Registrar:

Estado:
BLOQUEADO

Transición:
ESPERAR RESOLUCIÓN DE BLOQUEO


# 25. VERIFICACIÓN ANTES DE GENERAR

Antes de finalizar los documentos realiza internamente esta comprobación:

[ ] ¿Identifiqué correctamente el proyecto?

[ ] ¿Identifiqué el módulo correcto?

[ ] ¿Diferencié sesión y módulo?

[ ] ¿Determiné correctamente el motivo del cierre?

[ ] ¿Separé realizado de propuesto?

[ ] ¿Separé decidido de pendiente?

[ ] ¿Registré los resultados reales?

[ ] ¿Registré los pendientes?

[ ] ¿Registré bloqueos?

[ ] ¿Registré decisiones?

[ ] ¿Registré contradicciones?

[ ] ¿Determiné si el módulo continúa o terminó?

[ ] ¿Definí correctamente el próximo paso?

[ ] ¿Definí el estado de transición?

[ ] ¿Actualicé CURRENT sin convertirlo en historial?

[ ] ¿Generé HISTORIAL sin sobrescribir información anterior?

[ ] ¿Evité inventar información?

[ ] ¿Las referencias permiten continuar?


# 26. REGLA DE CONSISTENCIA

Antes de entregar los documentos compara:

CURRENT actualizado
vs.
HISTORIAL generado

Ambos deben ser consistentes.

CURRENT representa el estado final.

HISTORIAL explica cómo se llegó a ese estado.

Si existe una diferencia:

- identificarla;
- corregirla si existe evidencia;
- si no existe evidencia suficiente, registrarla como incertidumbre.


# 27. REGLA DE REFERENCIAS

Cuando sea necesario continuar el trabajo, indicar las fuentes que deberá consultar la siguiente sesión.

Las referencias pueden incluir:

- documentación;
- código;
- CURRENT;
- HISTORIAL;
- archivos;
- configuraciones;
- especificaciones;
- decisiones previas.

No copiar grandes cantidades de contenido cuando basta con indicar dónde se encuentra.


# 28. NO MODIFICAR EL CÓDIGO

Este prompt genera información de continuidad.

No debe modificar código salvo que el usuario lo solicite expresamente como parte de la tarea de cierre.

El objetivo principal es preservar el estado.


# 29. NO MODIFICAR LA DOCUMENTACIÓN

No modificar documentación del proyecto únicamente para generar CURRENT o HISTORIAL.

Si se detecta una necesidad de actualización documental:

registrarla como:

PENDIENTE

o:

ADVERTENCIA

según corresponda.


# 30. RESULTADO FINAL

Al terminar el análisis debes producir DOS RESULTADOS:

1. `CURRENT.md`
2. registro de `HISTORIAL`

Ambos deben estar listos para ser almacenados en el repositorio correspondiente.


# 31. REGLA DE PRIORIDAD

Si existe conflicto entre una suposición de la conversación y evidencia verificable:

priorizar la evidencia.

Orden conceptual:

Evidencia del código
+
Documentación vigente
+
Estado documental
+
Conversación

Cuando exista una contradicción no suficientemente resuelta:

registrarla.


# 32. PRINCIPIO DE MÍNIMA PÉRDIDA

El objetivo del cierre no es producir documentos largos.

El objetivo es garantizar que la siguiente sesión pueda continuar sin perder información relevante.

Por lo tanto:

No conservar ruido.

No conservar conversaciones irrelevantes.

No conservar contenido duplicado innecesariamente.

Conservar:

- estado;
- decisiones;
- resultados;
- pendientes;
- bloqueos;
- razones;
- consecuencias;
- transición;
- referencias.


# 33. PRINCIPIO FINAL

Al cerrar una sesión recuerda:

CURRENT.md
→ dónde quedamos.

HISTORIAL
→ por qué llegamos hasta ahí.

Universal 04
→ define cómo deben estructurarse ambos.

Universal 05
→ determina cuándo debe prepararse la continuidad.

Este prompt
→ ejecuta el cierre y genera los documentos.

Prompt de Continuidad
→ recupera el estado y permite comenzar la siguiente sesión.

La regla fundamental es:

FIN DE SESIÓN
≠
FIN DE MÓDULO

Si terminó el contexto:

→ preservar
→ cerrar
→ continuar posteriormente el mismo módulo.

Si terminó el módulo:

→ preservar
→ cerrar
→ iniciar el siguiente módulo.
