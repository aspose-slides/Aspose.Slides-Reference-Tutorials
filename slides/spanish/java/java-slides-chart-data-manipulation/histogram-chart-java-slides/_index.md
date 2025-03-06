---
title: Gráfico de histograma en diapositivas de Java
linktitle: Gráfico de histograma en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear gráficos de histograma en presentaciones de PowerPoint usando Aspose.Slides para Java. Guía paso a paso con código fuente para visualización de datos.
weight: 19
url: /es/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de histograma en diapositivas de Java


## Introducción al gráfico de histograma en diapositivas de Java usando Aspose.Slides

En este tutorial, lo guiaremos a través del proceso de creación de un gráfico de histograma en una presentación de PowerPoint utilizando la API Aspose.Slides para Java. Se utiliza un gráfico de histograma para representar la distribución de datos en un intervalo continuo.

## Requisitos previos

 Antes de comenzar, asegúrese de tener instalada la biblioteca Aspose.Slides para Java. Puedes descargarlo desde el[Aspose sitio web](https://releases.aspose.com/slides/java/).

## Paso 1: Inicialice su proyecto

Cree un proyecto Java e incluya la biblioteca Aspose.Slides en las dependencias de su proyecto.

## Paso 2: Importe las bibliotecas necesarias

```java
import com.aspose.slides.*;
```

## Paso 3: cargue una presentación existente

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Asegúrate de reemplazar`"Your Document Directory"` con la ruta real a su documento de PowerPoint.

## Paso 4: crea un gráfico de histograma

Ahora, creemos un gráfico de histograma en una diapositiva de la presentación.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Agregar puntos de datos a la serie
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Establecer el tipo de agregación del eje horizontal en Automático
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // guardar la presentación
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 En este código, primero borramos del gráfico todas las categorías y series existentes. Luego, agregamos puntos de datos a la serie usando el`getDataPoints().addDataPointForHistogramSeries` método. Finalmente, configuramos el tipo de agregación del eje horizontal en Automático y guardamos la presentación.

## Código fuente completo para gráfico de histograma en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, exploramos cómo crear un gráfico de histograma en una presentación de PowerPoint usando la API Aspose.Slides para Java. Los gráficos de histograma son herramientas valiosas para visualizar la distribución de datos en un intervalo continuo y pueden ser una poderosa adición a sus presentaciones, especialmente cuando se trata de contenido estadístico o analítico.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para Java?

 Puede descargar la biblioteca Aspose.Slides para Java desde[aquí](https://releases.aspose.com/slides/java/). Siga las instrucciones de instalación proporcionadas en su sitio web.

### ¿Para qué se utiliza un gráfico de histograma?

Se utiliza un gráfico de histograma para visualizar la distribución de datos en un intervalo continuo. Se usa comúnmente en estadística para representar distribuciones de frecuencia.

### ¿Puedo personalizar la apariencia del gráfico de histograma?

Sí, puedes personalizar la apariencia del gráfico, incluidos sus colores, etiquetas y ejes, utilizando la API Aspose.Slides.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
