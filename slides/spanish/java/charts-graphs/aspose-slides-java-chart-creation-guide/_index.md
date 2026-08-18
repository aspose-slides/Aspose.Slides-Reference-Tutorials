---
date: '2026-06-03'
description: Aprenda cómo crear un gráfico de columnas agrupadas en Java usando Aspose.Slides.
  Esta guía cubre la dependencia de Maven, los pasos de creación del gráfico y el
  manejo de datos.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Crear gráfico de columnas agrupadas en Java con Aspose.Slides
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráfico de columnas agrupadas en Java con Aspose.Slides

## Cómo crear un gráfico en Java: Introducción
Crear presentaciones dinámicas a menudo implica visualizar datos mediante gráficos. Con **Aspose.Slides for Java**, puedes crear fácilmente objetos de **gráfico de columnas agrupadas**, mejorar la claridad y causar un mayor impacto en tu audiencia. Este tutorial te guía a través de la configuración de la biblioteca, la adición de un gráfico de columnas agrupadas, la gestión de series y la inversión condicional de puntos de datos negativos.

**Lo que aprenderás**
- Cómo configurar Aspose.Slides for Java.
- Pasos para **crear un gráfico de columnas agrupadas** en tu presentación.
- Técnicas para gestionar series de gráficos y puntos de datos.
- Métodos para invertir condicionalmente los puntos de datos negativos para una mejor visualización.
- Cómo guardar la presentación de forma segura.

## Respuestas rápidas
- **¿Qué biblioteca se usa?** Aspose.Slides for Java.  
- **¿Qué tipo de gráfico se muestra?** Gráfico de columnas agrupadas.  
- **¿Puedo invertir valores negativos?** Sí, usando `invertIfNegative`.  
- **¿Qué versión de Java se requiere?** JDK 16 o posterior.  
- **¿Se necesita una licencia para producción?** Sí, una licencia válida de Aspose.

## ¿Qué es un gráfico de columnas agrupadas?
Un gráfico de columnas agrupadas es una representación visual que coloca múltiples series de datos una al lado de la otra para cada categoría, lo que permite una comparación rápida entre grupos. Es perfecto para informes financieros, paneles de ventas y cualquier escenario donde necesites contrastar varias métricas a la vez.

## ¿Por qué usar Aspose.Slides para crear gráficos?
Aspose.Slides te permite generar y personalizar completamente los gráficos de forma programática, eliminando la necesidad de editar PowerPoint manualmente. Soporta **más de 70 formatos de entrada y salida** y puede procesar presentaciones con **hasta 10 000 diapositivas** sin cargar todo el archivo en memoria, garantizando un alto rendimiento para informes a gran escala.

## Requisitos previos
1. **Required Libraries**  
   - Aspose.Slides for Java (versión 25.4 o posterior).  

2. **Environment**  
   - JDK 16 o más reciente.  
   - Maven o Gradle para la gestión de dependencias.  

3. **Knowledge**  
   - Programación básica en Java.  
   - Familiaridad con herramientas de compilación (Maven/Gradle).  

## Configuración de Aspose.Slides para Java
### Instalación con Maven
Agrega la siguiente dependencia a tu archivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalación con Gradle
Agrega la siguiente línea a tu archivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia
- **Prueba gratuita:** Explora las funciones sin una licencia.  
- **Licencia temporal:** Úsala durante la evaluación.  
- **Licencia completa:** Compra para implementaciones en producción.  

### Inicialización básica
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## ¿Cómo añado un gráfico de columnas agrupadas a una diapositiva?
`Presentation` es la clase principal que representa un archivo PowerPoint. Carga una nueva `Presentation`, agrega una diapositiva y llama a `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Esta única llamada crea un gráfico de columnas agrupadas totalmente funcional posicionado en las coordenadas especificadas. Luego puedes acceder al objeto del gráfico para modificar series, puntos de datos y estilos visuales.

## Guía paso a paso

### Paso 1: Crear una presentación y agregar un gráfico de columnas agrupadas
`Presentation` representa un documento PowerPoint y permite crear diapositivas.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Paso 2: Gestionar series del gráfico
Ahora eliminaremos cualquier serie predeterminada, añadiremos una nueva y la rellenaremos con valores tanto positivos como negativos.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Paso 3: Invertir condicionalmente los puntos de datos negativos
El método `invertIfNegative` permite la inversión de valores negativos en una serie de gráfico.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Errores comunes y consejos
- **¿Olvidaste liberar el objeto `Presentation`?** Siempre llama a `dispose()` en un bloque `finally` para liberar recursos nativos.  
- **¿Los valores negativos no se muestran invertidos?** Asegúrate de llamar a `invertIfNegative(true)` **después** de agregar el punto de datos.  
- **Problemas de tamaño del gráfico:** Las coordenadas (X, Y) y dimensiones (ancho, alto) están en puntos; ajústalas para que encajen en el diseño de tu diapositiva.  

## Preguntas frecuentes

**Q:** ¿Puedo crear otros tipos de gráficos con el mismo enfoque?  
A: Sí, simplemente reemplaza `ChartType.ClusteredColumn` por cualquier otro valor del enum `ChartType` (p. ej., `Line`, `Pie`).  

**Q:** ¿Necesito una licencia para compilaciones de desarrollo?  
A: Se requiere una licencia temporal o de evaluación para acceder a todas las funciones; de lo contrario, la biblioteca funciona en modo de prueba con limitaciones de marca de agua.  

**Q:** ¿Cómo exporto la presentación a PDF después de agregar gráficos?  
`SaveFormat.Pdf` especifica PDF como formato de salida para guardar una presentación. Usa `pres.save("output.pdf", SaveFormat.Pdf);` después de terminar la manipulación del gráfico.  

**Q:** ¿Es posible dar estilo a columnas individuales (color, borde)?  
`IChartDataPoint` representa un único punto de datos en un gráfico y permite formatearlo. Cada `IChartDataPoint` ofrece opciones como `getFillFormat().setFillType(FillType.Solid)` y `getLineFormat()`.  

**Q:** ¿Qué pasa si necesito actualizar los datos del gráfico después de guardar la presentación?  
A: Carga la presentación nuevamente con `new Presentation("file.pptx")`, modifica los datos del gráfico y vuelve a guardarla.  

---

**Última actualización:** 2026-06-03  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear un gráfico de columnas apiladas en Java con Aspose.Slides – Guía completa](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Cómo crear un gráfico en Java con Aspose.Slides – Dominando la creación y validación de gráficos](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Crear y dar formato a gráficos en Java usando Aspose.Slides: Guía completa](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}