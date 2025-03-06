---
title: Configuración de colores automáticos de sectores de gráficos circulares en diapositivas de Java
linktitle: Configuración de colores automáticos de sectores de gráficos circulares en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear gráficos circulares dinámicos con colores de corte automáticos en presentaciones de PowerPoint en Java utilizando Aspose.Slides para Java. Guía paso a paso con código fuente.
weight: 24
url: /es/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de colores automáticos de sectores de gráficos circulares en diapositivas de Java


## Introducción a la configuración de colores automáticos de sectores de gráficos circulares en diapositivas de Java

En este tutorial, exploraremos cómo crear un gráfico circular en una presentación de PowerPoint usando Aspose.Slides para Java y estableceremos colores de corte automáticos para el gráfico. Proporcionaremos orientación paso a paso junto con el código fuente.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargar la biblioteca desde el sitio web de Aspose:[Descargar Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

## Paso 1: importar los paquetes necesarios

Primero, necesitas importar los paquetes necesarios desde Aspose.Slides para Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Paso 2: crea una presentación de PowerPoint

 Instanciar el`Presentation` clase para crear una nueva presentación de PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Paso 3: agregar una diapositiva

Accede a la primera diapositiva de la presentación y agrégale un gráfico con los datos predeterminados:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Paso 4: establecer el título del gráfico

Establezca un título para el gráfico:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Paso 5: configurar los datos del gráfico

Configure el gráfico para mostrar valores para la primera serie y configure los datos del gráfico:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Paso 6: agregar categorías y series

Agregue nuevas categorías y series al gráfico:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Paso 7: completar los datos de la serie

Complete los datos de la serie para el gráfico circular:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Paso 8: habilite colores de corte variados

Habilite varios colores de corte para el gráfico circular:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Paso 9: guarde la presentación

Finalmente, guarde la presentación en un archivo de PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Código fuente completo para configurar colores automáticos de sectores de gráficos circulares en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation presentation = new Presentation();
try
{
	// Acceder a la primera diapositiva
	ISlide slides = presentation.getSlides().get_Item(0);
	// Agregar gráfico con datos predeterminados
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Título del cuadro de configuración
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Establecer la primera serie para Mostrar valores
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Configuración del índice de la hoja de datos del gráfico
	int defaultWorksheetIndex = 0;
	// Obtener la hoja de trabajo de datos del gráfico
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Eliminar series y categorías generadas por defecto
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Agregar nuevas categorías
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Añadiendo nueva serie
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Ahora completando datos de series
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

Ha creado con éxito un gráfico circular en una presentación de PowerPoint utilizando Aspose.Slides para Java y lo ha configurado para que tenga colores de corte automáticos. Esta guía paso a paso le proporciona el código fuente necesario para lograrlo. Puede personalizar aún más el gráfico y la presentación según sea necesario.

## Preguntas frecuentes

### ¿Cómo puedo personalizar los colores de sectores individuales en el gráfico circular?

 Para personalizar los colores de sectores individuales en el gráfico circular, puede utilizar el`getAutomaticSeriesColors` método para recuperar el esquema de color predeterminado y luego modificar los colores según sea necesario. He aquí un ejemplo:

```java
//Obtener el esquema de color predeterminado
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modifica los colores según sea necesario.
colors.get_Item(0).setColor(Color.RED); // Establece el color de la primera rebanada en rojo.
colors.get_Item(1).setColor(Color.BLUE); // Establece el color del segundo corte en azul.
// Agregue más modificaciones de color según sea necesario
```

### ¿Cómo puedo agregar una leyenda al gráfico circular?

 Para agregar una leyenda al gráfico circular, puede utilizar el`getLegend` método y configúrelo de la siguiente manera:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Establecer la posición de la leyenda
legend.setOverlay(true); // Mostrar la leyenda sobre el gráfico.
```

### ¿Puedo cambiar la fuente y el estilo del título?

Sí, puedes cambiar la fuente y el estilo del título. Utilice el siguiente código para configurar la fuente y el estilo del título:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Establecer tamaño de fuente
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Pon el título en negrita
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Pon el título en cursiva
```

Puede ajustar el tamaño de fuente, la negrita y el estilo de cursiva según sea necesario.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
