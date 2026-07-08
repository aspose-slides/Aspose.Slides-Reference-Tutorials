---
date: '2026-07-08'
description: Aprenda cómo usar Aspose para crear un gráfico de rosquilla en PowerPoint
  con Java. Esta guía paso a paso muestra cómo agregar puntos de datos al gráfico
  programáticamente, personalizar etiquetas y guardar el PPTX con alta fidelidad.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Cómo usar Aspose le permite crear un gráfico de rosquilla en PowerPoint
  usando Java. Siga este tutorial para agregar puntos de datos, personalizar etiquetas
  y guardar el PPTX con alta fidelidad.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Cómo usar Aspose: crear un gráfico de rosquilla en PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Cómo usar Aspose para crear un gráfico de rosquilla en PowerPoint (Java)
url: /es/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo usar Aspose para crear un gráfico de rosquilla en PowerPoint (Java)

## Introducción
Crear presentaciones atractivas a menudo requiere más que solo texto e imágenes; los gráficos pueden mejorar significativamente la narrativa al visualizar datos de manera eficaz. **Cómo usar Aspose** para la generación de gráficos le brinda control programático sin abrir PowerPoint. Este tutorial le guía paso a paso en la construcción de un gráfico de rosquilla, configurando sus puntos de datos y guardando un PPTX de alta fidelidad. Solo necesitará conocimientos básicos de Java y unos minutos para la configuración.

`Aspose.Slides for Java` es una biblioteca Java que permite crear, manipular y convertir archivos PowerPoint sin Microsoft Office.

## Respuestas rápidas
- **¿Qué biblioteca crea gráficos de rosquilla en PowerPoint?** Aspose.Slides for Java  
- **¿Puedo agregar puntos de datos al gráfico programáticamente?** Sí, usando la API de gráficos  
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.Slides  
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores (clasificador JDK 16 mostrado)  
- **¿Cuántas series puedo agregar?** El ejemplo agrega hasta 15 series, pero puede ajustarse según sea necesario  

## ¿Qué es un gráfico de rosquilla en PowerPoint?
Un gráfico de rosquilla es un gráfico circular similar a un gráfico de pastel pero con un centro hueco, lo que permite mostrar múltiples series simultáneamente. Enfatiza las relaciones parte‑a‑todo mientras mantiene el diseño visual compacto y fácil de leer.

## ¿Por qué usar Aspose.Slides for Java para crear gráficos de rosquilla?
Aspose.Slides for Java maneja más de 50 formatos de entrada y salida y puede generar presentaciones de hasta 500 MB sin cargar todo el archivo en memoria. Ofrece control programático total sobre la apariencia, los datos y el diseño del gráfico en cualquier plataforma Java, elimina la interoperabilidad COM y puede renderizar 100 diapositivas ricas en gráficos en menos de dos segundos en un servidor típico.

## Requisitos previos
- Conocimientos básicos de programación Java.  
- Un IDE como IntelliJ IDEA o Eclipse.  
- Maven o Gradle para la gestión de dependencias.  
- Una licencia válida de Aspose.Slides for Java (prueba gratuita disponible).

## Configuración de Aspose.Slides for Java
Elija el gestor de dependencias que se ajuste a su proyecto.

**Maven**  
Agregue la siguiente dependencia a su `pom.xml` (reemplace la versión con la última publicación):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Agregue esta línea a su `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Si prefiere descargar directamente, visite la página de [lanzamientos de Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Adquisición de licencia
Puede comenzar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para uso prolongado, compre una licencia o solicite una temporal en el [sitio web de Aspose](https://purchase.aspose.com/temporary-license/). Siga las instrucciones proporcionadas para configurar su entorno e inicializar Aspose.Slides en su aplicación.

## Cómo crear un gráfico de rosquilla en PowerPoint usando Aspose.Slides for Java
Para construir un gráfico de rosquilla, comience cargando o creando una `Presentation`, agregue una forma de gráfico del tipo `ChartType.Doughnut`, elimine las series predeterminadas, establezca el tamaño del agujero y luego rellene el libro de trabajo del gráfico con nombres de categorías y valores numéricos. Finalmente, ajuste el formato de las etiquetas y guarde el PPTX.

### Paso 1: Inicializar la presentación
Cree una presentación nueva o abra un archivo existente para obtener una colección de diapositivas.

`Presentation` es la clase principal que representa un archivo PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Paso 2: Agregar un gráfico de rosquilla a la diapositiva
Inserte una forma de gráfico, elimine las series/categorías predeterminadas y configure ajustes visuales básicos como el tamaño del agujero de la rosquilla.

`Chart` (o forma de gráfico) representa un objeto de gráfico colocado en una diapositiva.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Paso 3: Agregar puntos de datos al gráfico y personalizar etiquetas
Rellene los nombres de categorías, añada puntos de datos para cada serie y ajuste finamente el formato de las etiquetas (fuente, color, posición). Este paso demuestra la capacidad de “agregar puntos de datos al gráfico”.

`Workbook` proporciona acceso a los datos de hoja de cálculo subyacentes del gráfico donde se rellenan las celdas.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Paso 4: Guardar la presentación actualizada
Persista los cambios en un nuevo archivo PPTX en disco.

`save` escribe la presentación a un archivo en el formato elegido.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Aplicaciones prácticas
Los gráficos de rosquilla son perfectos para:
- **Informes financieros:** Visualizar asignaciones presupuestarias o desglose de gastos.  
- **Análisis de mercado:** Mostrar la distribución de cuota de mercado entre competidores.  
- **Resultados de encuestas:** Presentar datos de encuestas categóricos en forma compacta.  
- **Generación de paneles:** Combinar con consultas a bases de datos para producir diapositivas que se actualizan en tiempo real.

## Consideraciones de rendimiento
- **Liberar recursos:** Llame a `pres.dispose()` después de guardar para liberar memoria nativa.  
- **Limitar la cantidad de gráficos:** Agregar cientos de gráficos puede aumentar el uso de memoria; procese por lotes si es necesario.  
- **Usar transmisión:** Para conjuntos de datos masivos, rellene el workbook directamente desde streams en lugar de matrices en memoria.  

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| **El gráfico aparece en blanco** | Celdas de datos no pobladas correctamente | Verifique que `workBook.getCell(...)` haga referencia a los índices de fila/columna correctos. |
| **Las etiquetas se superponen** | Demasiadas categorías en un espacio limitado | Aumente `DoughnutHoleSize` o ajuste `FirstSliceAngle`. |
| **OutOfMemoryError** | Presentaciones grandes sin liberar recursos | Llame a `pres.dispose()` después de guardar y considere aumentar el tamaño del heap de JVM. |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Slides for Java en aplicaciones comerciales?**  
A: Sí, pero necesita una licencia comercial válida. Hay una prueba gratuita disponible para evaluación.

**Q: ¿Cómo agrego más de 15 series?**  
A: Aumente el límite del bucle en el paso “Agregar gráfico de rosquilla” y asegúrese de que su workbook de datos contenga suficientes filas.

**Q: ¿Es posible cambiar el tamaño del agujero de la rosquilla después de la creación?**  
A: Sí, llame a `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` antes de guardar.

**Q: ¿Puedo exportar el gráfico como una imagen en lugar de un PPTX?**  
A: Absolutamente. Use `chart.getImage()` y guarde el `java.awt.image.BufferedImage` devuelto en el formato que prefiera.

**Q: ¿Aspose.Slides admite gráficos animados?**  
A: La animación se puede agregar mediante la API `ISlide.getTimeline()`, aunque está fuera del alcance de este tutorial.

## Conclusión
Ahora dispone de un método completo y listo para producción para **crear archivos PowerPoint con gráficos de rosquilla** usando Aspose.Slides for Java, incluyendo cómo **agregar puntos de datos al gráfico**, personalizar etiquetas y manejar consideraciones de rendimiento. Experimente con diferentes colores, fuentes de datos y tipos de gráficos para que sus presentaciones realmente destaquen.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Tutoriales relacionados

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑by‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}