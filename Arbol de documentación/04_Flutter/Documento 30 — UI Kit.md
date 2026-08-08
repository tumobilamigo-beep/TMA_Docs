# **Documento 30 — UI Kit**

Versión: 1.0  
 Estado: Aprobado  
 Proyecto: Tu Mobil Amigo V1.0

---

## **1\. Objetivo**

Definir el sistema visual oficial de Tu Mobil Amigo para garantizar:

* Consistencia visual.  
* Escalabilidad.  
* Accesibilidad.  
* Reutilización.  
* Uniformidad entre Cliente y Asesor.

---

## **2\. Principios de Diseño**

La interfaz deberá ser:

* Clara.  
* Rápida.  
* Minimalista.  
* Operativa.  
* Escalable.

Priorizar:

Velocidad de uso  
\>  
Cantidad de elementos visuales  
---

## **3\. Identidad Corporativa**

### **Azul Corporativo**

Aprobado previamente:

\#002B5B

Uso:

* Header.  
* Botones primarios.  
* Navegación.

---

### **Celeste Corporativo**

\#00AEEF

Uso:

* Indicadores.  
* Estados activos.  
* Resaltados.

---

### **Blanco**

\#FFFFFF

Uso:

* Fondo principal.

---

### **Gris Claro**

\#F5F7FA

Uso:

* Tarjetas.  
* Contenedores.  
* Formularios.

---

## **4\. Colores de Estado**

### **Éxito**

\#22C55E  
---

### **Advertencia**

\#F59E0B  
---

### **Error**

\#EF4444  
---

### **Información**

\#3B82F6  
---

## **5\. Tipografía Oficial**

Flutter:

Google Fonts

Fuente principal:

Inter  
---

## **6\. Jerarquía Tipográfica**

### **Título Principal**

32 px  
Bold  
---

### **Título Secundario**

24 px  
SemiBold  
---

### **Título de Sección**

20 px  
SemiBold  
---

### **Texto Normal**

16 px  
Regular  
---

### **Texto Auxiliar**

14 px  
Regular  
---

## **7\. Grid Base**

Sistema:

8 px

Todos los espacios deberán ser múltiplos de:

8  
---

## **8\. Border Radius**

Estándar:

12 px  
---

## **9\. Sombras**

Utilizar sombras suaves.

Evitar:

Sombras agresivas  
---

## **10\. Botones**

### **Primario**

Color:

\#002B5B

Texto blanco.

---

### **Secundario**

Borde azul.

Fondo transparente.

---

### **Terciario**

Solo texto.

---

## **11\. Campos de Entrada**

Todos los formularios deberán incluir:

* Label.  
* Placeholder.  
* Mensaje de error.  
* Validación visual.

---

## **12\. Tarjetas**

Uso obligatorio para:

* Servicios.  
* Ofertas.  
* Wallet.  
* Cashback.  
* Liquidaciones.

---

## **13\. Navegación Inferior**

Máximo:

5 elementos  
---

## **14\. Iconografía**

Biblioteca oficial:

Material Symbols  
---

## **15\. Estados de Carga**

Todo proceso asíncrono deberá mostrar:

* Skeleton.  
* Loader.  
* Indicador visual.

---

## **16\. Estados Vacíos**

Toda pantalla deberá contemplar:

Sin datos  
---

## **17\. Estados de Error**

Toda pantalla deberá contemplar:

Error recuperable  
---

## **18\. Accesibilidad**

Soporte mínimo:

* Contraste AA.  
* Escalado de fuentes.  
* Lectores de pantalla.

---

## **19\. Responsive**

Diseño oficial:

### **Mobile First**

Objetivo principal:

Android  
iOS  
---

## **20\. Trust Score**

Representación visual:

0 \- 100

mediante:

* color;  
* barra;  
* porcentaje.

---

## **21\. IMF**

Representación visual:

Categorías:

Bronce  
Plata  
Oro  
Platino  
Diamante  
---

## **22\. Wallet**

Visualización obligatoria:

* Saldo disponible.  
* Saldo pendiente.  
* Cashback acumulado.  
* Próxima liquidación.

---

## **23\. Servicios Programados**

Indicador visual especial:

PROGRAMADO

con distintivo visual.

---

## **24\. Servicios en Calle**

Indicador visual:

SERVICIO EN CALLE  
---

## **25\. Liquidaciones**

Visualización obligatoria:

* Pendiente.  
* Procesada.  
* Pagada.

---

## **26\. Notificaciones**

Clasificación:

* Operativas.  
* Financieras.  
* Seguridad.  
* Sistema.

---

## **27\. Animaciones**

Regla:

Animaciones sutiles

Prohibido:

Animaciones decorativas excesivas  
---

## **28\. Modo Oscuro**

El sistema soportará desde la V1:

Modo Claro

Modo Oscuro

---

### **Selección**

El usuario podrá elegir manualmente:

Claro

Oscuro

Automático

---

### **Modo Automático**

El sistema podrá adoptar automáticamente la configuración del dispositivo.

---

### **Persistencia**

La preferencia deberá almacenarse en:

perfil\_usuario

para mantener consistencia entre sesiones.

---

### **Principio de Diseño**

El modo oscuro no consistirá únicamente en invertir colores.

Cada componente deberá tener una definición específica.

---

### **Paleta Oscura Oficial**

#### **Fondo Principal**

\#121212

---

#### **Fondo Secundario**

\#1E1E1E

---

#### **Tarjetas**

\#242424

---

#### **Texto Principal**

\#FFFFFF

---

#### **Texto Secundario**

\#D1D5DB

---

#### **Azul Corporativo**

Se mantiene:

\#002B5B

ajustando contraste cuando sea necesario.

---

#### **Celeste Corporativo**

Se mantiene:

\#00AEEF

---

### **Componentes Obligatorios**

Todos los componentes deberán soportar:

* Light Theme.  
* Dark Theme.

Incluyendo:

* Wallet.  
* Trust.  
* IMF.  
* Servicios.  
* Ofertas.  
* Liquidaciones.  
* Notificaciones.  
* QR.  
* Formularios.

---

### **Restricción Arquitectónica**

Prohibido utilizar:

Colors.white

Colors.black

directamente dentro de Widgets.

Toda referencia visual deberá provenir de:

ThemeData

ColorScheme

ThemeExtensions

---

## **29\. Internacionalización**

Arquitectura preparada para:

* Español.  
* Inglés.  
* Portugués.

---

## **30\. Consistencia**

Todo componente deberá construirse utilizando:

ThemeData

centralizado.

Prohibido definir estilos visuales directamente en pantallas.

---

## **31\. Principio Rector Final**

> La interfaz de Tu Mobil Amigo deberá priorizar rapidez operativa, claridad visual y consistencia, garantizando una experiencia simple para clientes y asesores, evitando complejidad visual innecesaria y manteniendo una identidad corporativa uniforme en toda la plataforma.

