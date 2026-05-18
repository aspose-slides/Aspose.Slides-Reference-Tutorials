---
date: '2026-02-22'
description: Aprenda a crear un gráfico de columnas apiladas en Java usando Aspose.Slides.
  Este tutorial cubre la dependencia Maven de Aspose Slides, la incorporación de un
  gráfico apilado de porcentajes, el formato de las etiquetas de datos del gráfico
  y la guardado de la presentación como PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Cómo crear un gráfico de columnas apiladas en Java con Aspose.Slides – Guía
  completa
url: /es/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

.

Also there are bullet points with URLs; keep URLs unchanged.

Translate.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear un gráfico de columnas apiladas en Java con Aspose.Slides – Guía completa

## Introducción

Eleve sus presentaciones incorporando visualizaciones de datos perspicaces con el poder de Aspose.Slides para Java. En esta guía **creará gráficos de columnas apiladas** que se verán profesionales, ya sea que esté preparando informes empresariales o mostrando estadísticas de proyectos. Al final de este tutorial podrá:

- Configurar su entorno con la dependencia Maven de Aspose Slides
- Crear una presentación desde cero
- **Agregar un gráfico apilado porcentual** y personalizar su apariencia
- **Dar formato a las etiquetas de datos del gráfico** y **cambiar el formato del eje vertical**
- **Guardar la presentación como PPTX** con una sola línea de código

Recorra cada paso para que pueda comenzar a crear presentaciones atractivas de inmediato.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Dependencia Maven/Gradle `aspose-slides` (ver “aspose slides maven dependency” más abajo)  
- **¿Qué tipo de gráfico se usa?** `ChartType.PercentsStackedColumn` para un gráfico de columnas apiladas porcentual  
- **¿Cómo cambio el formato numérico del eje?** Use `IAxis.setNumberFormat()` y desactive la vinculación al origen  
- **¿Puedo personalizar las etiquetas de datos?** Sí – recorra los objetos `IChartDataPoint` y establezca un `ITextFrame` personalizado  
- **¿Cómo guardo el archivo?** Llame a `presentation.save("output.pptx", SaveFormat.Pptx)`

## ¿Qué es un gráfico de columnas apiladas?
Un gráfico de columnas apiladas visualiza varias series de datos apiladas una sobre otra en columnas verticales. Cuando se usa la variante **apilada porcentual**, cada columna siempre suma 100 %, lo que facilita comparar contribuciones proporcionales entre categorías.

## ¿Por qué usar Aspose.Slides para Java?
Aspose.Slides ofrece una API pura de Java que funciona en cualquier plataforma sin necesidad de Microsoft Office instalado. Proporciona control granular sobre los objetos de gráficos, admite una amplia gama de formatos y permite generar presentaciones programáticamente—perfecto para informes automatizados o generación de documentos del lado del servidor.

## Requisitos previos
- **Java Development Kit (JDK):** 8 o superior  
- **IDE:** IntelliJ IDEA, Eclipse o cualquier editor compatible con Java  
- **Herramienta de compilación:** Maven o Gradle (opcional pero recomendado)  
- **Conocimientos básicos de Java** – debe estar cómodo con clases y métodos  

## Configuración de Aspose.Slides para Java
Para comenzar, agregue la biblioteca Aspose.Slides a su proyecto.

### Dependencia Maven de Aspose Slides
Agregue lo siguiente a su `pom.xml` (esta es la **aspose slides maven dependency** que necesitará):

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

### Obtención de licencia
Puede comenzar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para eliminar las limitaciones de evaluación, considere obtener una licencia temporal o comprada.

- **Prueba gratuita:** Acceda a funciones limitadas sin costos inmediatos.  
- **Licencia temporal:** Solicite a través del [sitio de Aspose](https://purchase.aspose.com/temporary-license/).  
- **Compra:** Visite la página de compra para acceso completo.

### Inicialización básica
Aquí hay un fragmento mínimo que muestra cómo crear un objeto `Presentation`:

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
**Resumen:**  
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

### Agregar un gráfico de columnas apiladas porcentual a una diapositiva
**Resumen:**  
Ahora colocaremos un **gráfico apilado porcentual** en la primera diapositiva.

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
**Resumen:**  
Para una mejor legibilidad, **cambiaremos el formato del eje vertical** para mostrar porcentajes.

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
**Resumen:**  
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

### Dar formato al color de relleno de las series
**Resumen:**  
Asigne a cada serie un color distinto para que el gráfico sea más fácil de leer.

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

### Dar formato a las etiquetas de datos
**Resumen:**  
Ahora **daremos formato a las etiquetas de datos del gráfico** para que muestren texto personalizado.

#### Paso 1: Acceder a las series del gráfico y a los puntos de datos
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

#### Paso 2: Personalizar las etiquetas de datos
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
- **El gráfico aparece vacío:** Asegúrese de haber agregado al menos una serie de datos y un punto de datos antes de guardar.  
- **Los números del eje no muestran porcentajes:** Recuerde establecer `verticalAxis.setNumberFormatLinkedToSource(false)`; de lo contrario, se ignora el formato personalizado.  
- **Mensaje de evaluación de licencia:** Aplique un archivo de licencia válido antes de crear el objeto `Presentation` para suprimir la barra de evaluación.

## Preguntas frecuentes

**P: ¿Puedo usar este código con Java 11 o superior?**  
R: Sí. La biblioteca soporta JDK 8+; solo use el clasificador apropiado (p. ej., `jdk16` para JDK 16 o superior).

**P: ¿Cómo exporto el gráfico como imagen en lugar de PPTX?**  
R: Use `chart.getImage().save("chart.png", ImageFormat.Png);` después de agregar el gráfico a la diapositiva.

**P: ¿Es posible agregar una leyenda al gráfico de columnas apiladas?**  
R: Absolutamente. Llame a `chart.getChartTitle().addTextFrameForOverriding("My Chart");` y configure `chart.getLegend()` según sea necesario.

**P: ¿Qué pasa si necesito actualizar los datos después de generar la presentación?**  
R: Puede modificar las celdas del `ChartDataWorkbook` y luego llamar a `chart.refresh();` para reflejar los cambios.

**P: ¿Aspose.Slides funciona en servidores Linux?**  
R: Sí. La biblioteca es Java puro y se ejecuta en cualquier OS con una JRE compatible.

## Conclusión
Al seguir esta guía ha aprendido a **crear presentaciones con gráficos de columnas apiladas** usando Aspose.Slides para Java, desde la configuración del entorno hasta el estilo visual afinado. Experimente con diferentes conjuntos de datos, colores y formatos de etiquetas para que sus informes realmente destaquen.

---

**Última actualización:** 2026-02-22  
**Probado con:** Aspose.Slides 25.4 (clasificador jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}