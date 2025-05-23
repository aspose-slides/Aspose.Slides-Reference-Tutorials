---
"description": "Aprenda a crear histogramas en presentaciones de PowerPoint con Aspose.Slides para Java. Guía paso a paso con código fuente para la visualización de datos."
"linktitle": "Gráfico de histograma en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Gráfico de histograma en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de histograma en diapositivas de Java


## Introducción al gráfico de histograma en diapositivas de Java con Aspose.Slides

En este tutorial, le guiaremos en el proceso de creación de un histograma en una presentación de PowerPoint utilizando la API de Aspose.Slides para Java. Un histograma se utiliza para representar la distribución de datos en un intervalo continuo.

## Prerrequisitos

Antes de comenzar, asegúrese de tener instalada la biblioteca Aspose.Slides para Java. Puede descargarla desde [Sitio web de Aspose](https://releases.aspose.com/slides/java/).

## Paso 1: Inicialice su proyecto

Cree un proyecto Java e incluya la biblioteca Aspose.Slides en las dependencias de su proyecto.

## Paso 2: Importar las bibliotecas necesarias

```java
import com.aspose.slides.*;
```

## Paso 3: Cargar una presentación existente

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Asegúrese de reemplazar `"Your Document Directory"` con la ruta real a su documento de PowerPoint.

## Paso 4: Crear un gráfico de histograma

Ahora, vamos a crear un gráfico de histograma en una diapositiva de la presentación.

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
    
    // Establezca el tipo de agregación del eje horizontal en Automático
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Guardar la presentación
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

En este código, primero borramos las categorías y series existentes del gráfico. Luego, añadimos puntos de datos a la serie mediante `getDataPoints().addDataPointForHistogramSeries` Método. Finalmente, configuramos el tipo de agregación del eje horizontal en Automático y guardamos la presentación.

## Código fuente completo para gráficos de histograma en Java (diapositivas)

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

En este tutorial, hemos explorado cómo crear un histograma en una presentación de PowerPoint usando la API de Aspose.Slides para Java. Los histogramas son herramientas valiosas para visualizar la distribución de datos en un intervalo continuo y pueden ser una herramienta muy útil para sus presentaciones, especialmente al trabajar con contenido estadístico o analítico.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para Java?

Puede descargar la biblioteca Aspose.Slides para Java desde [aquí](https://releases.aspose.com/slides/java/). Siga las instrucciones de instalación proporcionadas en su sitio web.

### ¿Para qué se utiliza un gráfico de histograma?

Un gráfico de histograma se utiliza para visualizar la distribución de datos en un intervalo continuo. Se usa comúnmente en estadística para representar distribuciones de frecuencias.

### ¿Puedo personalizar la apariencia del gráfico de histograma?

Sí, puede personalizar la apariencia del gráfico, incluidos sus colores, etiquetas y ejes, utilizando la API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}