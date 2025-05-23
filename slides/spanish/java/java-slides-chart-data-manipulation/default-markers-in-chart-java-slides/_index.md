---
"description": "Aprenda a crear diapositivas Java con marcadores predeterminados en gráficos usando Aspose.Slides para Java. Guía paso a paso con código fuente."
"linktitle": "Marcadores predeterminados en gráficos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Marcadores predeterminados en gráficos en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Marcadores predeterminados en gráficos en diapositivas de Java


## Introducción a los marcadores predeterminados en gráficos de diapositivas de Java

En este tutorial, exploraremos cómo crear un gráfico con marcadores predeterminados usando Aspose.Slides para Java. Los marcadores predeterminados son símbolos o formas que se añaden a los puntos de datos de un gráfico para resaltarlos. Crearemos un gráfico de líneas con marcadores para visualizar los datos.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java.

## Paso 1: Crear una presentación

Primero, crearemos una presentación y le añadiremos una diapositiva. Luego, le añadiremos un gráfico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Paso 2: Agregar un gráfico de líneas con marcadores

Ahora, agreguemos un gráfico de líneas con marcadores a la diapositiva. También borraremos los datos predeterminados del gráfico.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Paso 3: Completar los datos del gráfico

Completaremos el gráfico con datos de muestra. En este ejemplo, crearemos dos series con puntos de datos y categorías.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Serie 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Serie 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Población de datos de series
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Paso 4: Personaliza el gráfico

Puede personalizar aún más el gráfico, como agregar una leyenda y ajustar su apariencia.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Paso 5: Guardar la presentación

Por último, guarde la presentación con el gráfico en la ubicación deseada.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

¡Listo! Has creado un gráfico de líneas con marcadores predeterminados usando Aspose.Slides para Java.

## Código fuente completo para marcadores predeterminados en gráficos de diapositivas de Java

```java
        // La ruta al directorio de documentos.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Tome la segunda serie de gráficos
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Ahora se están rellenando los datos de la serie
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusión

En este completo tutorial, aprendiste a crear diapositivas de Java con marcadores predeterminados en gráficos usando Aspose.Slides para Java. Cubrimos todo el proceso, desde la configuración de una presentación hasta la personalización de la apariencia del gráfico y el guardado del resultado.

## Preguntas frecuentes

### ¿Cómo puedo cambiar los símbolos del marcador?

Puede personalizar los símbolos de los marcadores configurando el estilo de marcador para cada punto de datos. Usar `IDataPoint.setMarkerStyle()` para cambiar el símbolo del marcador.

### ¿Cómo ajusto los colores del gráfico?

Para modificar los colores del gráfico, puede utilizar el `IChartSeriesFormat` y `IShapeFillFormat` Interfaces para establecer propiedades de relleno y línea.

### ¿Puedo agregar etiquetas a los puntos de datos?

Sí, puede agregar etiquetas a los puntos de datos utilizando el `IDataPoint.getLabel()` método y personalizarlos según sea necesario.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}