---
"description": "Aprenda a establecer etiquetas de datos con signos de porcentaje en presentaciones de PowerPoint con Aspose.Slides para Java. Cree gráficos atractivos con instrucciones paso a paso y código fuente."
"linktitle": "Establecer etiquetas de datos con el signo de porcentaje en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Establecer etiquetas de datos con el signo de porcentaje en diapositivas de Java"
"url": "/es/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Establecer etiquetas de datos con el signo de porcentaje en diapositivas de Java


## Introducción al uso del signo de porcentaje en etiquetas de datos de conjuntos en Aspose.Slides para Java

En esta guía, le guiaremos a través del proceso de configurar etiquetas de datos con un signo de porcentaje usando Aspose.Slides para Java. Crearemos una presentación de PowerPoint con un gráfico de columnas apiladas y configuraremos las etiquetas de datos para mostrar porcentajes.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java agregada a su proyecto. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Crear una nueva presentación

Primero, creamos una nueva presentación de PowerPoint usando Aspose.Slides.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

## Paso 2: Agregar una diapositiva y un gráfico

continuación, agregamos una diapositiva y un gráfico de columnas apiladas a la presentación.

```java
// Obtener referencia de la diapositiva
ISlide slide = presentation.getSlides().get_Item(0);

// Agregar el gráfico PercentsStackedColumn en una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Paso 3: Configurar el formato del número de eje

Para mostrar porcentajes, necesitamos configurar el formato de número para el eje vertical del gráfico.

```java
// Establezca NumberFormatLinkedToSource en falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Paso 4: Agregar datos del gráfico

Agregamos datos al gráfico creando series y puntos de datos. En este ejemplo, agregamos dos series con sus respectivos puntos de datos.

```java
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Añadir nueva serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Añadir nueva serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Paso 5: Personalizar las etiquetas de datos

Ahora, personalicemos la apariencia de las etiquetas de datos.

```java
// Configuración de las propiedades de LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Paso 6: Guardar la presentación

Por último, guardamos la presentación en un archivo de PowerPoint.

```java
// Escribir presentación en disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has creado correctamente una presentación de PowerPoint con un gráfico de columnas apiladas y has configurado las etiquetas de datos para mostrar porcentajes usando Aspose.Slides para Java.

## Código fuente completo para etiquetas de datos de conjuntos con signos de porcentaje en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
// Obtener referencia de la diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Agregar el gráfico PercentsStackedColumn en una diapositiva
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Establezca NumberFormatLinkedToSource en falso
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Añadir nueva serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Establecer el color de relleno de la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Configuración de las propiedades de LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Añadir nueva serie
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Configuración del tipo y color de relleno
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Escribir presentación en disco
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Conclusión

Al seguir esta guía, aprenderá a crear presentaciones atractivas con etiquetas de datos basadas en porcentajes, que pueden ser especialmente útiles para transmitir información de manera eficaz en informes comerciales, materiales educativos y más.

## Preguntas frecuentes

### ¿Cómo puedo cambiar los colores de la serie de gráficos?

Puede cambiar el color de relleno de las series de gráficos utilizando el `setFill` método como se muestra en el ejemplo.

### ¿Puedo personalizar el tamaño de fuente de las etiquetas de datos?

Sí, puede personalizar el tamaño de fuente de las etiquetas de datos configurando el `setFontHeight` propiedad como se muestra en el código.

### ¿Cómo puedo agregar más series al gráfico?

Puede agregar series adicionales al gráfico utilizando el `add` método en el `IChartSeriesCollection` objeto.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}