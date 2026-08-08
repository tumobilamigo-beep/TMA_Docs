# **Anexo B — Guía de Modelado de Nuevas Entidades**

**Versión:** 1.0  
 **Estado:** Aprobado  
 **Proyecto:** Tu Mobil Amigo V1.0

---

# **1\. Objetivo**

Establecer los criterios oficiales para diseñar nuevas entidades, relaciones, funciones y procesos dentro de Tu Mobil Amigo, garantizando que la arquitectura evolucione de forma consistente sin comprometer la estabilidad del sistema.

Este anexo complementa los Documentos 16 al 21A y será de cumplimiento obligatorio para cualquier ampliación futura.

---

# **2\. Principio Rector**

Antes de crear cualquier elemento nuevo deberá responderse la siguiente pregunta:

> **¿Realmente es necesario crear algo nuevo o la arquitectura actual ya puede resolver el problema mediante parametrización o reutilización?**

La creación de nuevas entidades será siempre la última alternativa.

---

# **3\. Árbol de Decisión**

Todo desarrollo seguirá el siguiente flujo:

Nueva necesidad

        │  
        ▼

¿Puede resolverse modificando un parámetro?

        │

   Sí ─────────► Modificar parámetro

        │

        No

        ▼

¿Puede resolverse creando un registro?

        │

   Sí ─────────► Crear registro

        │

        No

        ▼

¿Puede resolverse mediante una nueva relación?

        │

   Sí ─────────► Crear relación

        │

        No

        ▼

¿Puede resolverse mediante una función?

        │

   Sí ─────────► Crear función

        │

        No

        ▼

¿Puede resolverse creando una nueva entidad?

        │

   Sí ─────────► Nueva tabla

        │

        No

        ▼

Replantear el diseño  
---

# **4\. ¿Cuándo crear una nueva tabla?**

Una tabla nueva solo podrá crearse cuando represente un concepto completamente independiente.

Debe cumplir las siguientes condiciones:

* posee identidad propia;  
* tiene ciclo de vida independiente;  
* requiere auditoría propia;  
* posee relaciones propias;  
* evolucionará de forma independiente.

Ejemplo correcto

Servicios

Vehículos

Billeteras

Cashback

Comisiones

Ejemplo incorrecto

Crear una tabla únicamente para almacenar:

Color del botón

Tiempo de espera

Porcentaje

Configuración

Esto pertenece a parámetros.

---

# **5\. ¿Cuándo crear una tabla de parámetros?**

Siempre que el dato pueda cambiar sin alterar la lógica del negocio.

Ejemplos:

✔ correcto

Tiempo máximo oferta

Saldo mínimo

Porcentaje Empresa

Porcentaje Cashback

Tiempo Programación

Ventana de negociación

Trust mínimo

IMF mínimo

Incorrecto

Tarifa fija escrita en código  
---

# **6\. ¿Cuándo reutilizar una entidad?**

Siempre que el nuevo requerimiento represente una especialización del concepto existente.

Ejemplo

Ya existe

servicios

No crear

servicios\_moto

servicios\_taxi

servicios\_mensajeria

Debe existir

tipos\_servicio

como catálogo.

---

# **7\. ¿Cuándo versionar una entidad?**

Cuando el cambio de información deba conservar el histórico.

Ejemplos:

Variables tarifarias.

Decretos.

Configuraciones.

Porcentajes.

Trust.

IMF.

Nunca sobrescribir información histórica.

---

# **8\. ¿Cuándo crear una función?**

Cuando exista una regla de negocio reutilizable.

Ejemplos:

Calcular tarifa.

Liberar Cashback.

Validar QR.

Actualizar Trust.

Distribuir comisiones.

Calcular IMF.

Nunca crear funciones para operaciones triviales como consultas simples.

---

# **9\. ¿Cuándo crear una Edge Function?**

Las Edge Functions deberán utilizarse cuando sea necesario:

* interactuar con servicios externos;  
* proteger claves privadas;  
* coordinar procesos entre varios motores;  
* exponer una API segura a Flutter o React.

Ejemplos:

* Telegram.  
* PSE.  
* OpenStreetMap.  
* GraphHopper.  
* Notificaciones Push.

---

# **10\. ¿Cuándo usar PostgreSQL directamente?**

Las funciones PostgreSQL deberán concentrar toda regla crítica del negocio.

Ejemplos:

* cálculo financiero;  
* trust score;  
* motor tarifario;  
* liberación de cashback;  
* distribución multinivel;  
* antifraude.

---

# **11\. ¿Cuándo usar Flutter?**

Flutter únicamente será responsable de:

* presentar información;  
* capturar datos;  
* gestionar navegación;  
* validar formularios básicos;  
* consumir APIs.

Nunca contendrá reglas financieras, tarifarias o de seguridad.

---

# **12\. ¿Cuándo usar React?**

El Panel Administrativo en React será responsable de:

* gestión administrativa;  
* monitoreo;  
* reportes;  
* parametrización;  
* auditoría;  
* aprobación de procesos.

No implementará lógica de negocio distinta a la interfaz.

---

# **13\. ¿Cómo elegir el dominio correcto?**

Antes de crear una entidad deberá identificarse el dominio al que pertenece.

| Si representa... | Dominio |
| ----- | ----- |
| Personas, roles, vehículos | Core |
| Servicios y ofertas | Operations |
| Dinero y movimientos | Finance |
| Tarifas y ciudades | Pricing |
| Trust, IPA, IPR, IMF | Trust |
| Fraude y dispositivos | Security |
| Parámetros | Configuration |
| APIs externas | Integration |
| Auditoría | Audit |
| Administración | Admin |

Una entidad no podrá pertenecer simultáneamente a dos dominios.

---

# **14\. ¿Cuándo crear una nueva billetera?**

Solo cuando represente dinero con reglas de negocio completamente distintas.

Ejemplos válidos

* Bolsa Operativa.  
* Cashback.  
* Comisiones Multinivel.

No crear billeteras únicamente para separar saldos visualmente.

---

# **15\. ¿Cuándo crear una nueva métrica?**

Una métrica nueva deberá cumplir:

* objetivo claramente definido;  
* fórmula documentada;  
* impacto operativo;  
* actualización automática;  
* utilidad para la toma de decisiones.

No se crearán métricas únicamente por fines estadísticos.

---

# **16\. ¿Cuándo crear una nueva categoría?**

Las categorías deberán representar cambios reales de comportamiento dentro del ecosistema.

No se crearán categorías únicamente para distinguir usuarios.

Actualmente:

Explorador

Viajero

Experto

Leyenda

Estas categorías podrán evolucionar mediante parametrización, sin modificar la lógica de los motores que las consumen.

---

# **17\. ¿Cuándo modificar una estructura existente?**

Antes de añadir una nueva columna deberá responderse:

1. ¿Puede resolverse mediante un parámetro?  
2. ¿Puede resolverse mediante una relación?  
3. ¿Puede resolverse mediante una tabla hija?  
4. ¿Puede resolverse mediante una versión?

Solo si todas las respuestas son negativas podrá añadirse una nueva columna.

---

# **18\. Antipatrones Prohibidos**

Quedan expresamente prohibidas las siguientes prácticas:

* duplicar información entre tablas;  
* almacenar valores calculados sin justificación;  
* escribir porcentajes o tiempos en código;  
* eliminar registros críticos;  
* crear tablas específicas para un único tipo de servicio;  
* utilizar JSONB para evitar un correcto modelado relacional;  
* acceder directamente a tablas críticas desde Flutter o React;  
* crear excepciones específicas para un único cliente, asesor o ciudad.

---

# **19\. Lista de Verificación para Nuevas Funcionalidades**

Antes de aprobar cualquier desarrollo deberá verificarse:

* ¿Respeta la arquitectura por dominios?  
* ¿Puede resolverse mediante parametrización?  
* ¿Existe una función reutilizable?  
* ¿Requiere auditoría?  
* ¿Impacta la seguridad?  
* ¿Impacta el modelo financiero?  
* ¿Requiere una nueva métrica?  
* ¿Cumple las políticas RLS?  
* ¿Es escalable a múltiples ciudades y países?  
* ¿Está documentado?

Si alguna respuesta es negativa, el diseño deberá revisarse antes de implementarse.

---

# **20\. Preparación para la Internacionalización**

Toda nueva entidad deberá diseñarse considerando que Tu Mobil Amigo podrá operar en diferentes países.

Por tanto, deberá evitar dependencias implícitas de:

* una única moneda;  
* una única ciudad;  
* un único idioma;  
* un único proveedor de mapas;  
* un único proveedor de pagos;  
* una única normativa local.

Las particularidades de cada jurisdicción deberán resolverse mediante parametrización y versionado.

---

# **21\. Principio Rector Final**

> **Toda evolución de Tu Mobil Amigo deberá construirse ampliando una arquitectura estable y coherente, nunca mediante excepciones aisladas. Cada nueva entidad, función o proceso deberá fortalecer el modelo existente, preservando la separación por dominios, la parametrización, la trazabilidad y la escalabilidad como pilares fundamentales del proyecto.**

