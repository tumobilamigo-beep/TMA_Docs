# PROMPT MAESTRO 02 — NAVEGACIÓN Y CONTEXTUALIZACIÓN DEL ÁRBOL DE DOCUMENTACIÓN

## PROPÓSITO

El proyecto con el que estás trabajando dispone de una estructura documental centralizada dentro de una carpeta denominada:

`Arbol de documentación`

Esta carpeta forma parte del repositorio del proyecto y contiene la información específica necesaria para comprender cómo debe desarrollarse, funcionar y evolucionar el proyecto.

Tu función en esta etapa es **navegar, identificar, seleccionar y comprender la documentación relevante**, sin asumir previamente cómo está organizada.

---

# 1. ARBOL DE DOCUMENTACIÓN

La carpeta:

`Arbol de documentación`

es el punto de entrada documental del proyecto.

Dentro de ella pueden existir:

- carpetas;
- subcarpetas;
- documentos;
- especificaciones;
- instrucciones;
- reglas;
- decisiones;
- diagramas;
- procedimientos;
- prompts;
- referencias;
- documentación técnica;
- documentación funcional;
- documentación histórica;
- cualquier otro recurso definido por el proyecto.

No debes asumir una estructura fija.

La estructura documental puede ser diferente para cada proyecto.

Debes descubrirla.

---

# 2. PRIMERA ACCIÓN: EXPLORAR

Antes de intentar comprender el proyecto mediante la documentación:

1. Localiza `Arbol de documentación`.
2. Examina su estructura.
3. Identifica las carpetas principales.
4. Identifica los documentos disponibles.
5. Identifica los documentos que contienen instrucciones.
6. Identifica los documentos que describen el proyecto.
7. Identifica posibles documentos de referencia.
8. Determina cómo está organizada la información.

No comiences leyendo documentos al azar.

Primero comprende el árbol documental.

---

# 3. NO ASUMIR LA ESTRUCTURA

No debes asumir que todos los proyectos tendrán:

- las mismas carpetas;
- los mismos nombres;
- la misma cantidad de documentos;
- las mismas categorías;
- la misma metodología;
- los mismos prompts;
- la misma arquitectura.

La única estructura que debes asumir inicialmente es:

```text
Repositorio
└── Arbol de documentación
```

Todo lo demás debe descubrirse.

---

# 4. INSTRUCCIONES ESPECÍFICAS DEL PROYECTO

Dentro de `Arbol de documentación` pueden existir instrucciones específicas para el proyecto.

Estas instrucciones pueden determinar:

- cómo debe desarrollarse;
- qué reglas deben respetarse;
- cómo debe organizarse el código;
- cómo deben realizarse determinadas tareas;
- qué decisiones ya fueron establecidas;
- cómo deben actualizarse determinados documentos;
- cómo debe utilizarse el contexto;
- qué procedimientos deben seguirse.

Debes identificar estas instrucciones antes de realizar tareas importantes.

No debes inventar instrucciones que no estén disponibles.

---

# 5. PROMPTS ESPECÍFICOS DEL PROYECTO

El árbol documental puede contener prompts diseñados específicamente para el proyecto.

Estos prompts pueden complementar los prompts maestros universales.

Debes distinguir entre:

### PROMPTS MAESTROS

Definen el comportamiento general del sistema de contextualización.

### PROMPTS ESPECÍFICOS DEL PROYECTO

Contienen instrucciones particulares relacionadas con ese proyecto.

Los prompts específicos deben descubrirse dentro del árbol documental.

No debes asumir su existencia, nombre, ubicación ni contenido.

Si existen, debes identificarlos y comprender su función antes de realizar las tareas para las que fueron diseñados.

---

# 6. JERARQUÍA DE CONTEXTUALIZACIÓN

La información debe interpretarse teniendo en cuenta la relación entre:

```text
PROMPTS MAESTROS
        ↓
REGLAS DEL PROYECTO
        ↓
DOCUMENTACIÓN DEL PROYECTO
        ↓
ESTADO ACTUAL
        ↓
TAREA SOLICITADA
```

Los prompts maestros establecen el comportamiento general del sistema.

La documentación y las instrucciones específicas establecen cómo debe tratarse el proyecto concreto.

La tarea actual determina qué parte del contexto resulta relevante.

---

# 7. DESCUBRIR ANTES DE LEER PROFUNDAMENTE

No es necesario procesar todos los documentos con la misma profundidad en cada sesión.

Primero determina:

**¿Qué necesito saber para realizar correctamente esta tarea?**

Después identifica dentro de `Arbol de documentación` los documentos relacionados.

Sin embargo, si la tarea afecta a una decisión global, arquitectura, seguridad, estructura o cualquier elemento transversal, debes ampliar la revisión para evitar tomar decisiones aisladas.

---

# 8. RELACIONES ENTRE DOCUMENTOS

Los documentos pueden depender unos de otros.

Si un documento:

- referencia otro documento;
- depende de otra especificación;
- menciona una decisión;
- utiliza una definición;
- enlaza con otro componente documental;

debes seguir esas referencias cuando sean necesarias para comprender correctamente el contexto.

No interpretes una especificación aislada si existe otra documentación que modifica o complementa su significado.

---

# 9. DOCUMENTOS DE DIFERENTE NATURALEZA

Debes determinar qué función cumple cada documento.

Por ejemplo, un documento puede ser:

- una instrucción;
- una especificación;
- una decisión;
- una descripción;
- una guía;
- un procedimiento;
- un registro;
- una referencia;
- un historial;
- una propuesta.

No debes tratar todos los documentos como si fueran instrucciones.

Primero identifica su función.

---

# 10. INFORMACIÓN HISTÓRICA

Si encuentras documentación histórica:

No la descartes automáticamente.

Puede explicar:

- por qué se tomó una decisión;
- por qué se modificó una arquitectura;
- por qué se eliminó una funcionalidad;
- qué problemas existieron;
- qué alternativas fueron descartadas.

Sin embargo, la información histórica no debe confundirse con las instrucciones o especificaciones vigentes.

---

# 11. CONTRADICCIONES DOCUMENTALES

Si dos documentos proporcionan información diferente:

No elijas arbitrariamente uno.

Identifica:

- documento A;
- documento B;
- información diferente;
- posible causa;
- impacto.

Después determina si existe otra fuente documental que permita resolver la contradicción.

Si no puede resolverse objetivamente, marca:

**CONTRADICCIÓN NO RESUELTA**

No modifiques silenciosamente ninguna fuente.

---

# 12. DOCUMENTACIÓN Y CÓDIGO

Recuerda el modelo definido en el Prompt Maestro 01:

**Documentación → cómo debe funcionar**

**Código → cómo funciona realmente**

Por lo tanto, el análisis de `Arbol de documentación` tiene como objetivo comprender las especificaciones y reglas del proyecto.

No debes afirmar que una funcionalidad está implementada únicamente porque la documentación la describa.

La implementación deberá verificarse posteriormente contra el código.

---

# 13. DOCUMENTACIÓN Y CURRENT.MD

Recuerda:

**`CURRENT.md` → dónde quedamos**

Cuando contextualices una nueva sesión, la información documental debe complementarse posteriormente con `CURRENT.md`.

La documentación explica el proyecto.

`CURRENT.md` explica el punto actual de continuidad.

No confundas ambas funciones.

---

# 14. DOCUMENTACIÓN E HISTORIAL

Recuerda:

**Historial → por qué llegamos hasta ahí**

El historial puede explicar decisiones y evolución.

La documentación describe las especificaciones y reglas vigentes.

Si existe una diferencia entre ambos:

No asumas automáticamente que el historial representa el estado actual.

Debe verificarse cuál información continúa vigente.

---

# 15. CONSTRUIR EL MAPA DOCUMENTAL

Después de explorar `Arbol de documentación`, construye internamente un mapa conceptual:

```text
Arbol de documentación
        │
        ├── Instrucciones
        │
        ├── Prompts específicos
        │
        ├── Documentación
        │
        ├── Decisiones
        │
        ├── Referencias
        │
        └── Información histórica
```

Los nombres reales y las categorías reales deben obtenerse del árbol.

No debes inventarlos.

---

# 16. SELECCIÓN DEL CONTEXTO

Cuando recibas una tarea:

1. identifica qué necesita la tarea;
2. consulta el mapa documental;
3. localiza la documentación relevante;
4. lee los documentos necesarios;
5. sigue referencias cuando corresponda;
6. identifica instrucciones aplicables;
7. separa información vigente de información histórica;
8. prepara el contexto documental necesario.

No cargues información irrelevante simplemente por estar disponible.

---

# 17. NO MODIFICAR DURANTE LA EXPLORACIÓN

Durante este proceso:

**LEER**

→ **IDENTIFICAR**

→ **RELACIONAR**

→ **COMPRENDER**

No debes modificar la documentación solamente como consecuencia de haberla analizado.

Las modificaciones deben realizarse únicamente cuando la tarea solicitada requiera actualizar documentación.

---

# 18. RESULTADO ESPERADO

Al finalizar la contextualización documental debes poder determinar:

### Estructura

¿Cómo está organizado `Arbol de documentación`?

### Instrucciones

¿Qué instrucciones específicas aplican al proyecto?

### Prompts

¿Qué prompts específicos existen y para qué sirven?

### Documentación

¿Qué documentos explican el funcionamiento del proyecto?

### Decisiones

¿Qué decisiones importantes están documentadas?

### Dependencias

¿Qué documentos deben consultarse conjuntamente?

### Vigencia

¿Qué información parece actual y qué información parece histórica?

### Relevancia

¿Qué documentos son relevantes para la tarea actual?

### Incertidumbre

¿Qué información todavía no puede determinarse?

---

# 19. REGLA FUNDAMENTAL

`Arbol de documentación` no es simplemente una carpeta de archivos.

Es el **sistema documental mediante el cual el proyecto proporciona a la IA el conocimiento específico que necesita para trabajar correctamente**.

Por ello:

No debes asumir su contenido.

No debes asumir su estructura.

No debes asumir sus nombres.

No debes asumir sus categorías.

Debes **explorarlo y descubrirlo**.

---

# 20. PRINCIPIO FINAL

Cuando necesites comprender cómo debe funcionar una parte del proyecto:

**primero busca en `Arbol de documentación`.**

Cuando necesites saber qué existe realmente:

**verifica el código.**

Cuando necesites saber dónde quedó el trabajo:

**consulta `CURRENT.md`.**

Cuando necesites saber por qué se llegó a una determinada situación:

**consulta el historial.**

Y recuerda siempre:

> **GitHub → fuente de verdad**

> **Documentación → cómo debe funcionar**

> **Código → cómo funciona realmente**

> **CURRENT.md → dónde quedamos**

> **Historial → por qué llegamos hasta ahí**