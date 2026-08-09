\# PROMPT — CIERRE DE SESIÓN Y GENERACIÓN DE CURRENT.md E HISTORIAL

\#\# OBJETIVO

La sesión actual de trabajo está finalizando.

Analiza todo el trabajo realizado durante esta sesión y genera DOS documentos Markdown independientes:

1\. \`CURRENT.md\`  
2\. Un documento de historial correspondiente exclusivamente a esta sesión.

Los dos documentos tienen funciones diferentes y deben conservar estructuras diferentes.

NO los mezcles.

\---

\# 1\. PRINCIPIO DEL SISTEMA

El proyecto utiliza el siguiente flujo de información:

GitHub → fuente de verdad

Documentación → cómo debe funcionar

Código → cómo funciona realmente

CURRENT.md → dónde quedamos

Historial → por qué llegamos hasta ahí

Tu trabajo en este proceso es convertir el resultado real de esta sesión en:

\- un estado actualizado y compacto para \`CURRENT.md\`;  
\- un registro de la sesión para el historial.

\---

\# 2\. REGLA FUNDAMENTAL: NO INVENTAR

Utiliza únicamente información que pueda determinarse a partir de:

\- esta conversación;  
\- la documentación consultada;  
\- el código consultado;  
\- CURRENT existente;  
\- historial existente;  
\- información explícitamente proporcionada durante la sesión.

NO inventes:

\- avances;  
\- decisiones;  
\- funcionalidades;  
\- soluciones;  
\- archivos;  
\- estados;  
\- resultados;  
\- requisitos;  
\- problemas.

Distingue siempre entre:

REALIZADO  
→ ocurrió realmente durante la sesión.

PROPUESTO  
→ solamente fue sugerido.

DECIDIDO  
→ fue aceptado como decisión.

DESCARTADO  
→ fue considerado y rechazado.

PENDIENTE  
→ todavía no se ha realizado.

NO VERIFICADO  
→ no existe evidencia suficiente para afirmarlo.

Nunca presentes una propuesta como si hubiera sido realizada.

Nunca presentes una posibilidad como una decisión definitiva.

\---

\# 3\. DOCUMENTO 1 — CURRENT.md

Genera el documento \`CURRENT.md\`.

Debe utilizar EXACTAMENTE la siguiente estructura conceptual:

\# CURRENT

\#\# Estado actual  
\[Situación actual\]

\#\# Último trabajo realizado  
\[Qué se hizo\]

\#\# Resultado  
\[Qué se consiguió\]

\#\# Pendientes  
\[Qué falta\]

\#\# Bloqueos  
\[Problemas que impiden continuar\]

\#\# Próximo paso  
\[Acción siguiente\]

\#\# Advertencias  
\[Información importante\]

\#\# Decisiones recientes  
\[Decisiones relevantes\]

\#\# Contexto de continuidad  
\[Información mínima adicional necesaria para comprender el estado actual y continuar el proyecto\]

\#\# Referencias de continuidad  
\[Referencias a documentación, código, CURRENT anterior, historial u otros recursos directamente relacionados, cuando corresponda\]

\#\#\# REGLAS PARA CURRENT.md

\`CURRENT.md\` representa el estado actual del proyecto.

Debe ser:

\- compacto;  
\- preciso;  
\- actualizado;  
\- orientado a la continuidad;  
\- fácil de leer por una nueva IA.

NO debe convertirse en:

\- una copia de la conversación;  
\- una copia de la documentación;  
\- una copia del código;  
\- una copia del historial;  
\- una explicación extensa de todo el proyecto.

Su función es responder rápidamente:

¿Dónde estamos?

¿Qué se hizo?

¿Qué resultado produjo?

¿Qué falta?

¿Qué bloquea?

¿Qué sigue?

¿Qué decisiones recientes debo conocer?

¿Qué información adicional necesito para continuar correctamente?

¿Dónde puedo consultar la información relacionada?

\---

\# 4\. DOCUMENTO 2 — HISTORIAL

Genera un documento Markdown independiente correspondiente a ESTA SESIÓN.

Debe utilizar EXACTAMENTE la siguiente estructura conceptual:

\# HISTORIAL — \[Identificador o fecha de la sesión\]

\#\# Objetivo de la sesión  
\[Qué se pretendía conseguir\]

\#\# Estado inicial  
\[Situación del proyecto al comenzar la sesión\]

\#\# Trabajo realizado  
\[Qué se hizo realmente durante la sesión\]

\#\# Descubrimientos  
\[Información nueva descubierta\]

\#\# Problemas encontrados  
\[Problemas, errores, dificultades o contradicciones encontradas\]

\#\# Soluciones  
\[Soluciones que realmente fueron aplicadas\]

\#\# Decisiones  
\[Decisiones tomadas durante la sesión\]

\#\# Cambios realizados  
\[Modificaciones realizadas realmente\]

\#\# Alternativas consideradas y descartadas  
\[Alternativas relevantes que fueron evaluadas y posteriormente descartadas\]

\#\# Contradicciones detectadas  
\[Contradicciones encontradas entre documentación, código, CURRENT, historial, requisitos o decisiones\]

\#\# Información pendiente de verificación  
\[Información que todavía no puede considerarse confirmada\]

\#\# Consecuencias para el proyecto  
\[Impacto de los cambios y decisiones realizados\]

\#\# Estado final de la sesión  
\[Situación del proyecto al terminar la sesión\]

\#\# Referencias  
\[Documentación, código, CURRENT, historial u otros recursos directamente relacionados\]

\---

\# 5\. REGLAS PARA EL HISTORIAL

El historial registra lo ocurrido durante ESTA SESIÓN.

Debe permitir comprender posteriormente:

\- qué se intentaba hacer;  
\- desde qué estado se comenzó;  
\- qué se hizo;  
\- qué se descubrió;  
\- qué problemas aparecieron;  
\- cómo se solucionaron;  
\- qué decisiones se tomaron;  
\- qué cambios se realizaron;  
\- qué alternativas fueron descartadas;  
\- qué contradicciones aparecieron;  
\- qué quedó sin verificar;  
\- qué consecuencias tuvieron las decisiones;  
\- con qué estado terminó la sesión.

No conviertas el historial en un resumen genérico del proyecto.

Registra únicamente información relevante producida durante esta sesión.

\---

\# 6\. CURRENT Y HISTORIAL DEBEN SER DIFERENTES

No copies automáticamente el contenido de un documento en el otro.

CURRENT responde:

\> ¿DÓNDE ESTAMOS?

HISTORIAL responde:

\> ¿QUÉ OCURRIÓ Y POR QUÉ LLEGAMOS HASTA AQUÍ?

El historial puede contener información que ya no necesita aparecer en CURRENT.

CURRENT puede contener información necesaria para continuar que no requiere una narración histórica extensa.

\---

\# 7\. ACTUALIZACIÓN DE CURRENT EXISTENTE

Si existe un \`CURRENT.md\` anterior:

1\. Léelo.  
2\. Determina qué información continúa siendo válida.  
3\. Determina qué información cambió durante esta sesión.  
4\. Conserva lo que siga vigente.  
5\. Actualiza únicamente lo que corresponda.

NO elimines información válida solamente porque no haya sido mencionada nuevamente durante esta sesión.

El nuevo CURRENT debe representar:

CURRENT ANTERIOR  
\+  
CAMBIOS REALES DE ESTA SESIÓN  
\=  
CURRENT ACTUALIZADO

\---

\# 8\. HISTORIAL NO DEBE BORRAR EL PASADO

Si el proyecto utiliza documentos individuales de historial:

genera un nuevo documento correspondiente a esta sesión.

No reemplaces los documentos históricos anteriores.

No mezcles varias sesiones en un mismo documento salvo que la estructura del proyecto indique expresamente lo contrario.

\---

\# 9\. REFERENCIAS

Cuando existan referencias directas a:

\- documentación;  
\- código;  
\- CURRENT;  
\- historial;  
\- archivos;  
\- módulos;  
\- decisiones;

inclúyelas cuando sean útiles para continuar o verificar el trabajo.

NO inventes rutas.

Si una referencia no puede determinarse con seguridad, no la inventes.

\---

\# 10\. INFORMACIÓN NO EXISTENTE

Si una sección no aplica a esta sesión, utiliza:

\> Ninguno.

o:

\> No aplica.

o:

\> No definido.

según corresponda.

NO inventes contenido para llenar una sección.

\---

\# 11\. VALIDACIÓN ANTES DE ENTREGAR

Antes de generar los documentos verifica:

\#\#\# CURRENT.md

\[ \] Representa el estado real al finalizar la sesión.

\[ \] Conserva información válida del CURRENT anterior.

\[ \] Registra el último trabajo realizado.

\[ \] Registra el resultado real.

\[ \] Registra los pendientes.

\[ \] Registra los bloqueos.

\[ \] Registra el próximo paso cuando esté definido.

\[ \] Registra advertencias relevantes.

\[ \] Registra decisiones recientes.

\[ \] Incluye contexto de continuidad cuando sea necesario.

\[ \] Incluye referencias cuando sean útiles.

\[ \] No contiene información inventada.

\#\#\# HISTORIAL

\[ \] Corresponde únicamente a esta sesión.

\[ \] Registra el objetivo.

\[ \] Registra el estado inicial.

\[ \] Registra el trabajo realizado.

\[ \] Registra descubrimientos.

\[ \] Registra problemas.

\[ \] Registra soluciones reales.

\[ \] Registra decisiones.

\[ \] Registra cambios realizados.

\[ \] Registra alternativas descartadas.

\[ \] Registra contradicciones.

\[ \] Registra información pendiente de verificación.

\[ \] Registra consecuencias.

\[ \] Registra el estado final.

\[ \] Registra referencias relevantes.

\[ \] No contiene información inventada.

\# 12\. FORMATO DE RESPUESTA

Entrega exactamente DOS bloques Markdown independientes.

PRIMERO:

\`\`\`markdown  
\# CURRENT

...

SEGUNDO:

\# HISTORIAL — \[Identificador o fecha\]

...

No mezcles los documentos.

No agregues información externa.

No agregues explicaciones dentro de los documentos que no correspondan a sus estructuras.

Genera ahora ambos documentos.

\#\#\# El resultado del sistema queda así

\`\`\`text  
                    SESIÓN  
                      │  
                      ▼  
              Trabajo realizado  
                      │  
                      ▼  
             PROMPT DE CIERRE  
                      │  
             ┌────────┴────────┐  
             ▼                 ▼  
        CURRENT.md         HISTORIAL  
             │                 │  
        ¿Dónde estamos?   ¿Qué ocurrió?  
             │             ¿Por qué?  
             │                 │  
             └────────┬────────┘  
                      ▼  
                   GITHUB  
                      │  
                      ▼  
                 NUEVO CHAT  
                      │  
                      ▼  
             PROMPT CONTINUIDAD  
                      │  
                      ▼  
             Recuperación de  
                  contexto  
