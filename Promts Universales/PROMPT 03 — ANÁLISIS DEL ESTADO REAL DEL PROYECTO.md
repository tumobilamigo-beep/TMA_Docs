# PROMPT UNIVERSAL 03 — ANÁLISIS DEL ESTADO REAL DEL PROYECTO

## PROPÓSITO

El objetivo de este proceso es determinar el **estado real y verificable del proyecto** utilizando el código y los archivos disponibles en GitHub.

Recuerda el modelo de contextualización:

> **GitHub → fuente de verdad**

> **Documentación → cómo debe funcionar**

> **Código → cómo funciona realmente**

> **CURRENT.md → dónde quedamos**

> **Historial → por qué llegamos hasta ahí**

Este Universal se concentra principalmente en la tercera fuente:

> **CÓDIGO → CÓMO FUNCIONA REALMENTE**

---

# 1. NO ASUMIR EL ESTADO DEL PROYECTO

No debes asumir que una funcionalidad está implementada porque:

- aparezca en la documentación;
- aparezca en un prompt;
- haya sido mencionada en una conversación;
- aparezca en el historial;
- aparezca como pendiente o terminada en `CURRENT.md`.

El estado real debe verificarse utilizando los archivos y código disponibles.

---

# 2. EXPLORAR ANTES DE ANALIZAR

Antes de determinar el estado del proyecto:

1. Identifica la estructura principal del repositorio.
2. Localiza el código fuente.
3. Identifica los componentes principales.
4. Identifica configuraciones relevantes.
5. Identifica pruebas cuando existan.
6. Identifica archivos de entrada.
7. Identifica dependencias.
8. Identifica los archivos relacionados con la tarea actual.

No debes limitar el análisis a un único archivo cuando una funcionalidad dependa de varios componentes.

---

# 3. DETERMINAR QUÉ ESTÁ IMPLEMENTADO

Para cada funcionalidad relevante determina, cuando sea posible:

- si existe;
- dónde está implementada;
- qué componentes participan;
- cómo funciona;
- qué dependencias tiene;
- si parece completa;
- si existen partes pendientes;
- si existen errores evidentes;
- si existen pruebas relacionadas.

No declares una funcionalidad como completamente implementada si solamente encuentras una parte de ella.

---

# 4. DIFERENCIAR IMPLEMENTACIÓN PARCIAL

Una funcionalidad puede encontrarse en diferentes estados.

Utiliza las siguientes categorías:

### NO IMPLEMENTADO

No existe evidencia suficiente de implementación.

### PARCIALMENTE IMPLEMENTADO

Existe código relacionado, pero la funcionalidad no está completa.

### IMPLEMENTADO

Existe una implementación identificable.

### IMPLEMENTADO Y VERIFICADO

Existe implementación y además existe evidencia suficiente de funcionamiento, por ejemplo mediante pruebas o verificaciones disponibles.

### IMPLEMENTACIÓN NO VERIFICABLE

Existe código aparentemente relacionado, pero no es posible determinar con suficiente seguridad si funciona correctamente.

### OBSOLETO

Existe código relacionado, pero parece pertenecer a una versión anterior o haber sido reemplazado.

---

# 5. NO CONFUNDIR CÓDIGO CON FUNCIONALIDAD COMPLETA

La existencia de una función, clase, componente o archivo no significa necesariamente que una funcionalidad esté terminada.

Debes analizar:

- integración;
- llamadas;
- dependencias;
- flujo;
- configuración;
- manejo de errores;
- conexiones con otros componentes;
- pruebas cuando existan.

Por ejemplo:

Encontrar una función `login()` no significa necesariamente que el sistema de autenticación esté implementado completamente.

Debes comprobar cómo se utiliza y cómo se integra con el resto del proyecto.

---

# 6. ANALIZAR DEPENDENCIAS

Cuando una funcionalidad dependa de varios componentes:

identifica la cadena necesaria para que funcione.

Por ejemplo, conceptualmente:

```text
Interfaz
   ↓
Lógica
   ↓
Servicio
   ↓
API
   ↓
Base de datos
```

No declares una funcionalidad completa si una dependencia fundamental todavía no está implementada o configurada.

---

# 7. ANALIZAR CONFIGURACIÓN

Cuando corresponda, verifica también:

- archivos de configuración;
- variables necesarias;
- dependencias;
- rutas;
- servicios externos;
- permisos;
- configuraciones de compilación;
- configuración de ejecución.

No expongas secretos, claves privadas, contraseñas o credenciales.

Si detectas información sensible almacenada incorrectamente, indícalo como un problema de seguridad.

---

# 8. ANALIZAR PRUEBAS

Cuando existan pruebas:

Identifica qué partes del proyecto cubren.

Diferencia entre:

**CÓDIGO EXISTENTE**

y:

**COMPORTAMIENTO VERIFICADO**

Una funcionalidad sin pruebas no debe considerarse automáticamente defectuosa.

Sin embargo, tampoco debe considerarse verificada simplemente porque exista el código.

---

# 9. COMPARAR CON LA DOCUMENTACIÓN

Una vez comprendido el estado del código, compáralo con la información obtenida mediante:

`Arbol de documentación`

Busca específicamente:

### DOCUMENTADO + IMPLEMENTADO

La especificación existe y existe implementación.

### DOCUMENTADO + PARCIALMENTE IMPLEMENTADO

La especificación existe, pero la implementación está incompleta.

### DOCUMENTADO + NO IMPLEMENTADO

La especificación existe, pero no se encontró implementación.

### IMPLEMENTADO + NO DOCUMENTADO

Existe una funcionalidad en el código que no está claramente documentada.

### CONTRADICCIÓN

La documentación indica un comportamiento diferente al comportamiento encontrado en el código.

Estas diferencias son importantes y deben conservarse para el análisis posterior.

---

# 10. COMPARAR CON `CURRENT.md`

Después de analizar el código, compara el estado encontrado con:

`CURRENT.md`

Determina si:

- el estado coincide;
- existen cambios posteriores;
- existen tareas marcadas como pendientes que ya fueron implementadas;
- existen tareas marcadas como terminadas que no pueden verificarse;
- existen nuevos cambios que todavía no aparecen en `CURRENT.md`.

No modifiques `CURRENT.md` automáticamente durante este análisis.

Primero identifica las diferencias.

---

# 11. COMPARAR CON EL HISTORIAL

Utiliza el historial cuando sea necesario para comprender:

- por qué existe determinado código;
- cuándo se introdujo un cambio;
- qué problema intentaba solucionar;
- qué decisión originó una implementación;
- si una parte del código reemplazó una implementación anterior.

Recuerda:

**Historial → por qué llegamos hasta ahí**

No utilices el historial como sustituto de la inspección del código actual.

---

# 12. DETECTAR CONTRADICCIONES

Cuando encuentres diferencias entre:

- documentación;
- código;
- `CURRENT.md`;
- historial;

registra la contradicción.

Utiliza esta estructura:

## CONTRADICCIÓN

**Fuente:**

[Fuente]

**Indica:**

[Información]

**Estado real encontrado:**

[Información]

**Diferencia:**

[Explicación]

**Impacto:**

[Impacto potencial]

**Requiere decisión:**

SÍ / NO

---

# 13. NO CORREGIR SILENCIOSAMENTE

El objetivo de este Universal es **analizar el estado**, no corregir automáticamente las diferencias.

Si encuentras una contradicción:

No cambies automáticamente:

- código;
- documentación;
- `CURRENT.md`;
- historial.

Primero informa del problema.

La corrección será una tarea posterior.

---

# 14. CONSTRUIR EL ESTADO REAL

Al terminar el análisis debes construir una representación del estado actual:

## ESTADO REAL DEL PROYECTO

### Componentes identificados

[Componentes]

### Funcionalidades implementadas

[Lista]

### Funcionalidades parcialmente implementadas

[Lista]

### Funcionalidades no implementadas

[Lista]

### Funcionalidades no verificables

[Lista]

### Código posiblemente obsoleto

[Lista]

### Dependencias relevantes

[Lista]

### Pruebas existentes

[Lista]

### Problemas encontrados

[Lista]

### Contradicciones con documentación

[Lista]

### Diferencias con `CURRENT.md`

[Lista]

### Información que requiere investigación adicional

[Lista]

---

# 15. REGLA DE EVIDENCIA

Cuando afirmes que algo está implementado, debes poder señalar la evidencia correspondiente dentro del proyecto.

Cuando no exista evidencia suficiente:

indica:

**NO VERIFICADO**

No conviertas una suposición en un hecho.

---

# 16. ALCANCE

No es necesario realizar una auditoría completa del proyecto para cada tarea.

El análisis debe adaptarse al objetivo actual.

Sin embargo, si una tarea afecta:

- arquitectura;
- seguridad;
- base estructural;
- múltiples componentes;
- comportamiento global;

debes ampliar el análisis para evitar conclusiones basadas en una visión incompleta.

---

# 17. RESULTADO ESPERADO

Al finalizar este proceso debes poder responder:

1. ¿Qué existe realmente?
2. ¿Qué está parcialmente implementado?
3. ¿Qué no está implementado?
4. ¿Qué puede verificarse?
5. ¿Qué componentes participan?
6. ¿Qué dependencias existen?
7. ¿Qué pruebas existen?
8. ¿Qué contradicciones existen con la documentación?
9. ¿Qué diferencias existen con `CURRENT.md`?
10. ¿Qué información histórica ayuda a explicar el estado actual?
11. ¿Qué aspectos requieren investigación adicional?

---

# PRINCIPIO FINAL

Recuerda:

> **La documentación indica cómo debe funcionar.**

> **El código indica cómo funciona realmente.**

Tu función en este Universal es descubrir el segundo punto de forma objetiva y verificable.

No debes modificar el proyecto simplemente por encontrar diferencias.

Primero:

**OBSERVA → ANALIZA → VERIFICA → COMPARA → INFORMA**

Después, mediante la tarea correspondiente, podrán realizarse las modificaciones necesarias.
