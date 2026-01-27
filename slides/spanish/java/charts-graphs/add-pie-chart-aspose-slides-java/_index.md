---
date: '2026-01-09'
description: Descubre cómo usar Aspose Slides Maven para agregar un gráfico a una
  diapositiva y personalizar un gráfico circular en presentaciones Java. Configuración
  paso a paso, código y ejemplos del mundo real.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Añadir un gráfico de pastel a una presentación'
url: /es/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar un gráfico circular a una presentación usando Aspose.Slides Java

## Introducción
Crear presentaciones visualmente atractivas es crucial para transmitir información de manera eficaz, especialmente cuando la visualización de datos juega un papel clave. Si deseas automatizar este proceso con **aspose slides maven**, has llegado al lugar correcto. En este tutorial aprenderás a **add chart to slide** — específicamente un gráfico circular — usando Aspose.Slides para Java, y verás cómo personalizarlo para escenarios del mundo real.

### Lo que aprenderás
- Cómo inicializar un objeto de presentación en Java.  
- Pasos para **add a pie chart java** en la primera diapositiva de una presentación.  
- Acceder a los libros de datos del gráfico y enumerar las hojas de cálculo dentro de ellos.  

¡Vamos a profundizar en cómo puedes aprovechar Aspose.Slides Java para mejorar tus presentaciones con gráficos dinámicos!

## Respuestas rápidas
- **¿Qué biblioteca agrega gráficos mediante Maven?** aspose slides maven  
- **¿Qué tipo de gráfico se demuestra?** Gráfico circular (add chart to slide)  
- **¿Versión mínima de Java requerida?** JDK 16 o posterior  
- **¿Necesito una licencia para pruebas?** Una prueba gratuita funciona; la producción requiere una licencia  
- **¿Dónde puedo encontrar la dependencia de Maven?** En la sección de configuración a continuación  

## ¿Qué es Aspose Slides Maven?
Aspose.Slides for Java es una API potente que permite a los desarrolladores crear, modificar y renderizar archivos PowerPoint de forma programática. El paquete Maven (`aspose-slides`) simplifica la gestión de dependencias, permitiéndote centrarte en construir y personalizar diapositivas—como agregar un gráfico circular—sin preocuparte por el manejo de archivos de bajo nivel.

## ¿Por qué usar Aspose.Slides Maven para agregar un gráfico a una diapositiva?
- **Automatización:** Genera informes y paneles automáticamente.  
- **Precisión:** Control total sobre tipos de gráficos, datos y estilo.  
- **Multiplataforma:** Funciona en cualquier entorno compatible con Java.  

## Requisitos previos
- **Aspose.Slides for Java** versión 25.4 o posterior (Maven/Gradle).  
- JDK 16+ instalado.  
- Un IDE (IntelliJ IDEA, Eclipse, etc.).  
- Conocimientos básicos de Java y familiaridad con Maven o Gradle.

## Configuración de Aspose.Slides para Java
Primero, incluye Aspose.Slides en tu proyecto mediante Maven o Gradle.

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, puedes [download the latest release](https://releases.aspose.com/slides/java/) directamente desde el sitio web de Aspose.

### Obtención de licencia
Aspose.Slides for Java ofrece una prueba gratuita con una licencia temporal para pruebas. Para uso ilimitado en producción, adquiere una licencia a través de la [purchase page](https://purchase.aspose.com/buy).

## Guía de implementación
A continuación dividimos la solución en dos funcionalidades: agregar un gráfico circular y acceder a su libro de datos.

### Funcionalidad 1: Crear una presentación y agregar un gráfico
#### Visión general
Esta parte muestra cómo crear una nueva presentación y **add a pie chart** a la primera diapositiva.

#### Paso a paso

**Paso 1: Inicializar un nuevo objeto Presentation**  
```java
Presentation pres = new Presentation();
```
*Crea la instancia `Presentation` que contendrá todas las diapositivas.*

**Paso 2: Agregar un gráfico circular**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Coloca un gráfico circular en las coordenadas (50, 50) con un ancho de 400 y una altura de 500. El enumerado `ChartType.Pie` indica a Aspose que renderice un gráfico circular.*

**Paso 3: Liberar recursos**  
```java
if (pres != null) pres.dispose();
```
*Libera los recursos nativos; siempre llama a `dispose()` cuando termines.*

### Funcionalidad 2: Acceder al libro de datos del gráfico y a las hojas de cálculo
#### Visión general
Aprende a alcanzar el libro subyacente que almacena los datos del gráfico e iterar a través de sus hojas de cálculo.

#### Paso a paso

**Paso 1: (Reusar) Inicializar un nuevo objeto Presentation**  
*Igual que en la Funcionalidad 1, Paso 1.*

**Paso 2: (Reusar) Agregar un gráfico circular**  
*Igual que en la Funcionalidad 1, Paso 2.*

**Paso 3: Obtener el libro de datos del gráfico**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Recupera el `IChartDataWorkbook` asociado al gráfico.*

**Paso 4: Iterar a través de las hojas de cálculo**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Imprime el nombre de cada hoja de cálculo, permitiéndote verificar la estructura de datos.*

**Paso 5: Liberar recursos**  
*Igual que en la Funcionalidad 1, Paso 3.*

## Aplicaciones prácticas
- **Informes de datos:** Genera automáticamente presentaciones con métricas actualizadas para inteligencia empresarial.  
- **Presentaciones académicas:** Visualiza resultados de investigación sin crear gráficos manualmente.  
- **Material de marketing:** Muestra el rendimiento de productos o resultados de encuestas al instante.

## Consideraciones de rendimiento
- Mantén razonable la cantidad de diapositivas y gráficos; cada uno consume memoria.  
- Siempre llama a `dispose()` para liberar recursos nativos.  
- Optimiza el manejo de datos del libro de trabajo—evita cargar conjuntos de datos masivos en un solo gráfico.

## Conclusión
Hemos cubierto cómo **aspose slides maven** te permite **add chart to slide** de forma programática y cómo trabajar con el libro de datos del gráfico. Con estos bloques de construcción puedes automatizar cualquier flujo de trabajo de informes que requiera una salida de PowerPoint pulida.

### Próximos pasos
- Explora opciones de estilo de gráficos (colores, leyendas, etiquetas de datos).  
- Conecta a fuentes de datos externas (CSV, bases de datos) para poblar gráficos dinámicamente.  
- Combina varios tipos de gráficos en una sola presentación para una narración más rica.

## Preguntas frecuentes

**P: ¿Cómo instalo Aspose.Slides para Java?**  
R: Usa la dependencia Maven o Gradle mostrada arriba, o descarga la biblioteca desde la página de lanzamientos.

**P: ¿Cuáles son los requisitos del sistema para Aspose.Slides?**  
R: JDK 16 o posterior; la biblioteca es independiente de la plataforma.

**P: ¿Puedo agregar otros tipos de gráficos además de los circulares?**  
R: Sí, Aspose.Slides admite barras, líneas, dispersión y muchos más tipos de gráficos.

**P: ¿Cómo debo manejar presentaciones grandes de manera eficiente?**  
R: Libera los objetos con prontitud, limita la cantidad de imágenes de alta resolución y reutiliza plantillas de gráficos cuando sea posible.

**P: ¿Dónde puedo encontrar más detalles sobre las funciones de Aspose.Slides?**  
R: Visita la [Aspose documentation](https://reference.aspose.com/slides/java/) para una referencia completa de la API.

**P: ¿Se requiere una licencia para uso comercial?**  
R: Se necesita una licencia válida para producción; una prueba gratuita está disponible para evaluación.

**P: ¿El paquete Maven incluye todas las capacidades de gráficos?**  
R: Sí, el artefacto Maven `aspose-slides` contiene todo el motor de gráficos.

## Recursos
- Documentación: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Descarga: [Latest Releases](https://releases.aspose.com/slides/java/)
- Compra y prueba: [Purchase Page](https://purchase.aspose.com/buy)
- Prueba gratuita: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Licencia temporal: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Foro de soporte: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Última actualización:** 2026-01-09  
**Probado con:** Aspose.Slides 25.4 for Java (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
