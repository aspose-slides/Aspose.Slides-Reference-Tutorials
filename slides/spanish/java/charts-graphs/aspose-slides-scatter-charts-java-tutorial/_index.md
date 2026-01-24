---
date: '2026-01-24'
description: Guía paso a paso para crear un gráfico de dispersión en Java usando Aspose.Slides,
  agregar puntos de datos al gráfico de dispersión y trabajar con varios series de
  gráficos de dispersión.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Crear gráfico de dispersión en Java con Aspose.Slides – Personalizar y guardar
url: /es/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráfico de dispersión Java con Aspose.Slides

En este tutorial **create scatter chart java** proyectos desde cero, añada puntos de datos de dispersión y aprenda a trabajar con gráficos de dispersión de series múltiples, todo usando Aspose.Slides para Java. Recorreremos la configuración del directorio, la inicialización de la presentación, la creación del gráfico, la gestión de datos, la personalización de marcadores y, finalmente, el guardado de la presentación.

**Lo que aprenderá**
- Configurar un directorio para almacenar archivos de presentación  
- Inicializar y manipular presentaciones usando Aspose.Slides  
- Crear un gráfico de dispersión en una diapositiva  
- Agregar y gestionar puntos de datos para cada serie  
- Personalizar tipos de series, marcadores y manejar gráficos de dispersión de series múltiples  
- Guardar la presentación finalizada  

Comencemos con los requisitos previos.

## Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Which Java version is required?** JDK 8 or higher (JDK 16 recommended)  
- **Can I add more than two series?** Sí – puede agregar cualquier número de series a un gráfico de dispersión  
- **How do I change marker colors?** Use `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Is a license needed for production?** Sí, una licencia comercial elimina los límites de evaluación  

## Prerequisites

Para seguir este tutorial, asegúrese de tener:
- **Aspose.Slides for Java** – versión 25.4 o posterior.  
- **Java Development Kit (JDK)** – JDK 8 o más reciente.  
- Conocimientos básicos de Java y familiaridad con Maven o Gradle.  

## Setting Up Aspose.Slides for Java

Integre Aspose.Slides en su proyecto con uno de los siguientes métodos.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Or download the latest package from [Aspose Releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- **Free Trial** – 30‑day evaluation.  
- **Temporary License** – Extended testing.  
- **Commercial License** – Full production use.

Ahora profundicemos en el código.

## Implementation Guide

### Step 1: Directory Setup
Primero, asegúrese de que la carpeta de salida exista para que la presentación pueda guardarse sin errores.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Step 2: Presentation Initialization
Cree una nueva presentación y obtenga la primera diapositiva.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Step 3: Add a Scatter Chart
Inserte un gráfico de dispersión con líneas suaves en la diapositiva.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Step 4: Manage Chart Data (Clear & Add Series)
Elimine cualquier serie predeterminada y añada nuestras propias series para el **multiple series scatter chart**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Step 5: Add Data Points Scatter
Complete cada serie con valores X‑Y usando **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Step 6: Customize Series Types & Markers
Ajuste el estilo visual—cambie a líneas rectas con marcadores y establezca símbolos de marcador distintos.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Step 7: Save the Presentation
Guarde el archivo en disco.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Financial Analysis** – Trace movimientos de precios de acciones con un gráfico de dispersión de series múltiples.  
- **Scientific Research** – Visualice mediciones experimentales usando add data points scatter para una representación precisa de los datos.  
- **Project Management** – Muestre tendencias de asignación de recursos a través de varios proyectos en un solo gráfico de dispersión.  

## Performance Considerations
- Deseche el objeto `Presentation` después de guardar para liberar memoria.  
- Para conjuntos de datos grandes, rellene el libro de trabajo en lotes en lugar de uno por uno.  
- Evite aplicar estilos excesivos dentro de bucles ajustados; aplique estilos después de la inserción de datos.  

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Chart appears empty** | Verifique que los puntos de datos se añadan a la serie correcta y que los índices del libro de trabajo coincidan. |
| **Markers not visible** | Asegúrese de que `series.getMarker().setSize()` esté configurado a un valor mayor que 0 y que el símbolo del marcador esté definido. |
| **OutOfMemoryError on large charts** | Use `pres.dispose()` después de guardar y considere aumentar el tamaño del heap de JVM (`-Xmx`). |

## Frequently Asked Questions

### How do I change the color of the markers?
Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color` is an instance of `java.awt.Color`.

### Can I add more than two series to a scatter chart?
Absolutamente. Repita el bloque de creación de series (Step 4) para cada serie adicional que necesite.

### Is it possible to export the chart as an image?
Sí. Llame a `chart.exportChartImage("chart.png", ImageFormat.Png)` después de añadir todos los datos.

### Does Aspose.Slides support interactive tooltips on scatter points?
Aunque PowerPoint no proporciona tooltips en tiempo de ejecución, puede incrustar etiquetas de datos usando `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### How can I animate the scatter series?
Use `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` para añadir una animación simple de aparición.

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}