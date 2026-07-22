---
date: '2026-07-22'
description: Aprende a usar Aspose Slides Maven Dependency para crear un stacked column
  chart en Java, agregar data labels, cambiar el vertical axis number format y exportar
  el resultado como un archivo PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency te permite crear un stacked column
  chart en Java, personalizar data labels, ajustar el vertical axis format y guardar
  como PPTX, todo con código conciso y listo para producción.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart en Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart en Java'
url: /es/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dependencia Maven de Aspose Slides: Gráfico de columnas apiladas en Java

## Introducción

Eleve sus presentaciones incorporando visualizaciones de datos perspicaces con el poder de **Aspose.Slides for Java**. En esta guía usted **creará un gráfico de columnas apiladas** que se ve profesional, ya sea que esté preparando informes empresariales o mostrando estadísticas de proyectos. Al final de este tutorial podrá:

- Configurar su entorno con la **dependencia Maven de Aspose Slides**
- Crear una presentación desde cero
- **Agregar un gráfico apilado en porcentaje** y personalizar su apariencia
- **Formatear las etiquetas de datos del gráfico** y **cambiar el formato numérico del eje vertical**
- **Guardar la presentación como PPTX** con una sola línea de código

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Añada la dependencia Maven/Gradle `aspose-slides` (vea “Dependencia Maven de Aspose Slides” a continuación).  
- **¿Qué tipo de gráfico crea una vista apilada?** Use `ChartType.PercentsStackedColumn` para un gráfico de columnas apiladas en porcentaje.  
- **¿Cómo puedo cambiar el formato numérico del eje?** Llame a `IAxis.setNumberFormat()` y establezca `setNumberFormatLinkedToSource(false)`.  
- **¿Puedo personalizar las etiquetas de datos?** Sí – itere a través de cada `IChartDataPoint` y asigne un `ITextFrame` personalizado.  
- **¿Cómo guardo el archivo?** Invoque `presentation.save("output.pptx", SaveFormat.Pptx)`.

## ¿Qué es un gráfico de columnas apiladas?
Un gráfico de columnas apiladas visualiza múltiples series de datos apiladas verticalmente en cada columna de categoría, con la variante **percentage‑stacked** normalizando cada columna al 100 % para una comparación de proporciones fácil. Este formato permite a los espectadores evaluar rápidamente cómo cada componente contribuye al total en diferentes categorías, haciendo que las tendencias y tamaños relativos sean instantáneamente claros.

## ¿Por qué usar Aspose.Slides para Java?
Aspose.Slides for Java le permite generar, editar y convertir archivos PowerPoint **sin necesidad de Microsoft Office** y soporta **más de 50 formatos de salida** en Windows, Linux y macOS. La biblioteca se ejecuta completamente en una JRE, habilitando automatización del lado del servidor y generación de informes de alto rendimiento. También brinda control granular sobre objetos de gráficos, diseños de diapositivas y propiedades del documento, lo que la hace ideal para generación de presentaciones a nivel empresarial.

## Requisitos previos
- **Java Development Kit (JDK):** 8 o superior  
- **IDE:** IntelliJ IDEA, Eclipse, o cualquier editor compatible con Java  
- **Herramienta de compilación:** Maven o Gradle (opcional pero recomendado)  
- **Conocimientos básicos de Java** – debe sentirse cómodo con clases y métodos  

## Configuración de Aspose.Slides para Java
Para comenzar, añada la biblioteca Aspose.Slides a su proyecto.

### Dependencia Maven de Aspose Slides
Agregue lo siguiente a su `pom.xml` (esta es la **dependencia Maven de aspose slides** que necesitará):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa Gradle
Si prefiere Gradle, incluya esta línea en `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, descargue el JAR más reciente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Adquisición de licencia
Puede comenzar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para eliminar las limitaciones de evaluación, considere obtener una licencia temporal o comprada.

- **Prueba gratuita:** Acceda a funciones limitadas sin costos inmediatos.  
- **Licencia temporal:** Solicítela a través del [sitio de Aspose](https://purchase.aspose.com/temporary-license/).  
- **Compra:** Visite la página de compra para acceso completo.

### Inicialización básica
`Presentation` es la clase central de Aspose.Slides que representa un archivo PowerPoint en memoria. El siguiente fragmento mínimo muestra cómo crear un objeto `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guía de implementación

### Crear una presentación y agregar una diapositiva
**Visión general:**  
Primero, crearemos una presentación en blanco y verificaremos que exista una diapositiva.

#### Paso 1: Inicializar el objeto Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Paso 2: Guardar la presentación
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Agregar gráfico de columnas apiladas en porcentaje a una diapositiva
**Visión general:**  
Ahora colocaremos un **gráfico apilado en porcentaje** en la primera diapositiva.

`ChartType.PercentsStackedColumn` especifica un tipo de gráfico de columnas apiladas en porcentaje.

#### Paso 1: Inicializar y acceder a la diapositiva
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Paso 2: Agregar el gráfico a la diapositiva
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizar el formato numérico del eje del gráfico
**Visión general:**  
Para una mejor legibilidad, **cambiaremos el formato del eje vertical** para mostrar porcentajes.

`IAxis` es la interfaz que representa un eje de gráfico, permitiendo ajustes de formato y escala.

#### Paso 1: Agregar y acceder al gráfico
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Paso 2: Establecer formato numérico personalizado
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Agregar series y puntos de datos al gráfico
**Visión general:**  
Poblaremos el gráfico con series de datos de ejemplo.

#### Paso 1: Inicializar la presentación y el gráfico
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Paso 2: Agregar series de datos
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatear el color de relleno de la serie
**Visión general:**  
Dé a cada serie un color distinto para que el gráfico sea más fácil de leer.

#### Paso 1: Inicializar y acceder al gráfico
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Paso 2: Establecer colores de relleno
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatear etiquetas de datos
**Visión general:**  
Ahora **formatearemos las etiquetas de datos del gráfico** para que muestren texto personalizado.

`IChartDataPoint` representa un punto de datos individual dentro de una serie de gráfico, y `ITextFrame` contiene el texto de la etiqueta.

#### Paso 1: Acceder a series y puntos de datos del gráfico
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Paso 2: Personalizar etiquetas de datos
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Problemas comunes y soluciones
- **El gráfico aparece vacío:** Asegúrese de haber añadido al menos una serie de datos y un punto de datos antes de guardar.  
- **Los números del eje no muestran porcentajes:** Recuerde establecer `verticalAxis.setNumberFormatLinkedToSource(false)`; de lo contrario, el formato personalizado se ignora.  
- **Mensaje de evaluación de licencia:** Aplique un archivo de licencia válido antes de crear el objeto `Presentation` para suprimir el banner de evaluación.

## Preguntas frecuentes

**P: ¿Puedo usar este código con Java 11 o superior?**  
R: Sí. La biblioteca soporta JDK 8+; simplemente use el clasificador apropiado (p.ej., `jdk16` para JDK 16 o posterior).

**P: ¿Cómo exporto el gráfico como una imagen en lugar de un PPTX?**  
R: Use `chart.getImage().save("chart.png", ImageFormat.Png);` después de agregar el gráfico a la diapositiva.

**P: ¿Es posible agregar una leyenda al gráfico de columnas apiladas?**  
R: Absolutamente. Llame a `chart.getChartTitle().addTextFrameForOverriding("My Chart");` y configure `chart.getLegend()` según sea necesario.

**P: ¿Qué pasa si necesito actualizar los datos después de generar la presentación?**  
R: Puede modificar las celdas del `ChartDataWorkbook` y luego llamar a `chart.refresh();` para reflejar los cambios.

**P: ¿Aspose.Slides funciona en servidores Linux?**  
R: Sí. La biblioteca es Java puro y se ejecuta en cualquier SO con un JRE compatible.

## Conclusión
Siguiendo esta guía ha aprendido a **crear un gráfico de columnas apiladas** en Java usando la **dependencia Maven de Aspose Slides**, desde la configuración del entorno hasta el estilo visual afinado. Experimente con diferentes conjuntos de datos, colores y formatos de etiquetas para que sus informes realmente destaquen.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo crear un gráfico de columnas agrupadas en Java con Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Cómo establecer formatos numéricos en puntos de datos de gráficos usando Aspose.Slides para Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Cómo agregar y configurar gráficos en presentaciones usando Aspose.Slides para Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}