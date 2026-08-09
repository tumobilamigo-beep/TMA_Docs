# UNIVERSAL 04 — CONTINUIDAD Y GESTIÓN DE `CURRENT.md`

## PROPÓSITO

`CURRENT.md` es el documento utilizado para conservar el estado actual del trabajo y permitir que una nueva sesión pueda continuar desde el punto donde terminó la anterior.

Su función principal es responder:

> **¿Dónde quedamos?**

Recuerda siempre el modelo:

> **GitHub → fuente de verdad**

> **Documentación → cómo debe funcionar**

> **Código → cómo funciona realmente**

> **`CURRENT.md` → dónde quedamos**

> **Historial → por qué llegamos hasta ahí**

`CURRENT.md` no sustituye ninguna de las otras fuentes.

---

# 1. FUNCIÓN DE `CURRENT.md`

`CURRENT.md` debe proporcionar una visión rápida del estado actual del proyecto.

Debe permitir identificar, cuando la información esté disponible:

- qué se estaba haciendo;
- qué se terminó;
- qué está pendiente;
- qué problema se está resolviendo;
- cuál fue el último cambio importante;
- cuál es el siguiente paso;
- qué aspectos requieren atención;
- qué información necesita conservarse para continuar.

---

# 2. `CURRENT.md` NO ES LA DOCUMENTACIÓN COMPLETA

No debes utilizar `CURRENT.md` como sustituto de:

- la documentación;
- los requisitos;
- las especificaciones;
- el código;
- las decisiones;
- el historial.

Su objetivo es proporcionar **continuidad**, no almacenar todo el conocimiento del proyecto.

Cuando necesites conocer cómo debe funcionar algo:

> consulta la documentación.

Cuando necesites conocer cómo funciona realmente:

> consulta el código.

Cuando necesites saber por qué se tomó una decisión:

> consulta el historial.

Cuando necesites saber dónde quedó el trabajo:

> consulta `CURRENT.md`.

---

# 3. AL INICIAR UNA NUEVA SESIÓN

Cuando comiences una nueva sesión y `CURRENT.md` esté disponible:

1. Localízalo.
2. Léelo.
3. Identifica el estado indicado.
4. Identifica la última actividad.
5. Identifica las tareas pendientes.
6. Identifica el siguiente paso.
7. Identifica cualquier advertencia o problema indicado.
8. Utiliza esa información para orientar la contextualización.

`CURRENT.md` proporciona el punto inicial de continuidad.

Después debe complementarse con las demás fuentes cuando la tarea lo requiera.

---

# 4. NO CONFIAR CIEGAMENTE EN `CURRENT.md`

El contenido de `CURRENT.md` puede quedar desactualizado.

Por ello:

No debes asumir que todo lo indicado allí sigue siendo cierto.

Cuando una afirmación sea importante para la tarea actual, verifica:

### Estado de implementación

→ código.

### Funcionamiento esperado

→ documentación.

### Razón de una decisión

→ historial.

### Continuidad del trabajo

→ `CURRENT.md`.

---

# 5. DETECTAR DESACTUALIZACIÓN

Si `CURRENT.md` indica que algo está pendiente pero el código demuestra que ya está implementado:

identifica la diferencia.

Si `CURRENT.md` indica que algo está terminado pero el código no permite verificarlo:

identifica la diferencia.

Si `CURRENT.md` describe una tarea diferente de la que aparece en el historial más reciente:

identifica la diferencia.

No corrijas silenciosamente estas inconsistencias.

---

# 6. ESTADO DE LAS TAREAS

Cuando sea necesario interpretar tareas indicadas en `CURRENT.md`, utiliza estados claros.

### PENDIENTE

Todavía no se ha completado.

### EN PROGRESO

Existe trabajo activo sobre la tarea.

### BLOQUEADO

No puede continuar hasta resolver una dependencia o problema.

### COMPLETADO

La tarea ha sido finalizada.

### VERIFICADO

La tarea ha sido finalizada y existe evidencia suficiente de que funciona correctamente.

### REQUIERE REVISIÓN

La información existente no permite determinar con seguridad su estado actual.

No cambies el estado de una tarea únicamente por inferencia.

---

# 7. CONTENIDO QUE DEBE CONSERVARSE

Cuando el flujo de trabajo requiera actualizar `CURRENT.md`, prioriza información que ayude a una futura sesión a continuar.

Debe conservarse, cuando corresponda:

## Estado actual

Qué situación representa actualmente el proyecto.

## Último trabajo realizado

Qué cambio o actividad se realizó recientemente.

## Resultado

Qué se consiguió.

## Pendientes

Qué queda por hacer.

## Bloqueos

Qué impide continuar.

## Próximo paso

Cuál es la siguiente acción lógica.

## Advertencias

Qué debe tenerse en cuenta antes de continuar.

## Decisiones recientes

Qué decisiones nuevas pueden afectar el siguiente trabajo.

---

# 8. EVITAR INFORMACIÓN INNECESARIA

`CURRENT.md` no debe convertirse en una copia de:

- toda la documentación;
- todo el código;
- toda la conversación;
- todo el historial.

Debe contener únicamente la información necesaria para recuperar rápidamente la continuidad.

---

# 9. ACTUALIZAR DESPUÉS DE CAMBIOS IMPORTANTES

Cuando una sesión produzca un cambio significativo, considera actualizar `CURRENT.md` cuando el flujo del proyecto lo requiera.

Ejemplos:

- finalización de una funcionalidad;
- inicio de una nueva etapa;
- cambio importante de arquitectura;
- resolución de un bloqueo;
- aparición de un nuevo bloqueo;
- modificación importante de requisitos;
- cambio de estrategia;
- descubrimiento relevante.

---

# 10. NO ACTUALIZAR CON INFORMACIÓN NO VERIFICADA

No registres como estado actual:

- suposiciones;
- hipótesis;
- funcionalidades que no fueron verificadas;
- decisiones que todavía no fueron aprobadas;
- tareas que solamente se propusieron.

Si algo todavía no está confirmado:

indícalo claramente como pendiente de confirmación o no verificado.

---

# 11. RELACIÓN CON EL HISTORIAL

`CURRENT.md` debe representar:

> **Dónde estamos ahora.**

El historial representa:

> **Cómo llegamos hasta aquí.**

Por lo tanto, `CURRENT.md` debe evitar acumular explicaciones históricas extensas.

Cuando sea necesario comprender la razón de una decisión:

consulta el historial correspondiente.

---

# 12. RELACIÓN CON LA DOCUMENTACIÓN

La documentación describe el funcionamiento esperado.

`CURRENT.md` describe el estado de trabajo.

No debes convertir decisiones temporales de trabajo en requisitos permanentes.

Por ejemplo:

Una tarea pendiente no significa necesariamente que la funcionalidad forme parte definitiva de los requisitos.

Debe distinguirse entre:

**REQUISITO**

y:

**TAREA DE IMPLEMENTACIÓN**

---

# 13. RELACIÓN CON EL CÓDIGO

El código representa el estado real de implementación.

Si existe una diferencia entre `CURRENT.md` y el código:

No asumas automáticamente que el código está equivocado.

Primero determina si:

- `CURRENT.md` quedó desactualizado;
- el código cambió después;
- existe una implementación parcial;
- hubo una decisión posterior;
- existe una contradicción que requiere resolución.

---

# 14. AL TERMINAR UNA SESIÓN

Cuando una sesión de trabajo termine, el estado que deba conservarse debe permitir que otra IA pueda comprender rápidamente:

```text id="7z9jqt"
¿QUÉ ESTÁBAMOS HACIENDO?
        ↓
¿QUÉ SE HIZO?
        ↓
¿QUÉ RESULTADO SE OBTUVO?
        ↓
¿QUÉ QUEDÓ PENDIENTE?
        ↓
¿QUÉ PROBLEMAS EXISTEN?
        ↓
¿CUÁL ES EL SIGUIENTE PASO?
```

La nueva sesión no debería necesitar reconstruir todo el trabajo únicamente desde la conversación anterior.

---

# 15. FORMATO CONCEPTUAL

Cuando el proyecto no establezca otro formato, el contenido de `CURRENT.md` debería poder expresar conceptualmente:

```text id="f1c6gr"
# CURRENT

## Estado actual
[Situación actual]

## Último trabajo realizado
[Qué se hizo]

## Resultado
[Qué se consiguió]

## Pendientes
[Qué falta]

## Bloqueos
[Problemas que impiden continuar]

## Próximo paso
[Acción siguiente]

## Advertencias
[Información importante]

## Decisiones recientes
[Decisiones relevantes]
```

Este formato es conceptual.

Si el proyecto ya posee una estructura propia para `CURRENT.md`, debes respetarla.

No debes reemplazarla arbitrariamente.

---

# 16. CUANDO EL ESTADO NO ESTÉ CLARO

Si `CURRENT.md` no permite determinar claramente dónde quedó el proyecto:

No inventes el estado.

Reconstruye la información utilizando:

1. `CURRENT.md`;
2. historial;
3. documentación relevante;
4. código.

Después determina cuál es el estado que puede verificarse.

Si todavía existe incertidumbre:

declárala.

---

# 17. RECONSTRUCCIÓN DE CONTINUIDAD

Cuando una nueva sesión necesite continuar el trabajo, utiliza este flujo:

```text id="z6f7qk"
CURRENT.md
    ↓
¿Dónde quedamos?
    ↓
Documentación relevante
    ↓
¿Cómo debería funcionar?
    ↓
Código relevante
    ↓
¿Cómo funciona realmente?
    ↓
Historial relevante
    ↓
¿Por qué llegamos hasta aquí?
    ↓
CONTEXTO ACTUAL
```

No es necesario consultar todo el historial si la información actual ya es suficiente.

---

# 18. DETECTAR INFORMACIÓN OBSOLETA

Si encuentras información antigua en `CURRENT.md`:

No la borres automáticamente.

Primero determina si:

- fue reemplazada;
- fue completada;
- dejó de ser válida;
- todavía aplica;
- necesita revisión.

Si corresponde actualizarla, realiza el cambio únicamente como parte de una tarea de actualización autorizada.

---

# 19. OBJETIVO PRINCIPAL

El objetivo de `CURRENT.md` es reducir la pérdida de continuidad entre sesiones.

Debe funcionar como un:

**PUNTO DE REANUDACIÓN**

y no como una base de conocimiento completa.

Una nueva IA debería poder leerlo y comprender rápidamente:

> "Esto es lo que estaba ocurriendo cuando terminó la última sesión."

---

# 20. PRINCIPIO FINAL

Recuerda siempre:

> **`CURRENT.md` no dice todo lo que existe en el proyecto.**

Dice:

> **Dónde quedó el trabajo.**

Por eso debes utilizarlo junto con las demás fuentes:

**GitHub → fuente de verdad**

**Documentación → cómo debe funcionar**

**Código → cómo funciona realmente**

**`CURRENT.md` → dónde quedamos**

**Historial → por qué llegamos hasta ahí**

La continuidad correcta surge de combinar estas fuentes, no de confiar ciegamente en una sola.

**Tu objetivo es que una nueva sesión pueda continuar el trabajo sin perder el punto en el que terminó la anterior.**