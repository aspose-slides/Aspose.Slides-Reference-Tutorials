---
title: Configuración de llamada para etiqueta de datos en diapositivas de Java
linktitle: Configuración de llamada para etiqueta de datos en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar llamadas para etiquetas de datos en Aspose.Slides para Java. Guía paso a paso con código fuente.
weight: 25
url: /es/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introducción a la configuración de llamadas para etiquetas de datos en Aspose.Slides para Java

En este tutorial, demostraremos cómo configurar llamadas para etiquetas de datos en un gráfico usando Aspose.Slides para Java. Las llamadas pueden resultar útiles para resaltar puntos de datos específicos en su gráfico. Revisaremos el código paso a paso y proporcionaremos el código fuente necesario.

## Requisitos previos

- Deberías tener instalado Aspose.Slides para Java.
- Cree un proyecto Java y agregue la biblioteca Aspose.Slides a su proyecto.

## Paso 1: cree una presentación y agregue un gráfico

 Primero, necesitamos crear una presentación y agregar un gráfico a una diapositiva. Asegúrate de reemplazar`"Your Document Directory"` con la ruta real a su directorio de documentos.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Paso 2: configurar el gráfico

A continuación, configuraremos el gráfico estableciendo propiedades como leyenda, series y categorías.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configurar series y categorías (Puedes ajustar el número de series y categorías)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Agregue puntos de datos aquí
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Paso 3: personaliza las etiquetas de datos

Ahora, personalizaremos las etiquetas de datos, incluida la configuración de llamadas para la última serie.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Personalice el formato de los puntos de datos (relleno, línea, etc.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Personalice el formato de la etiqueta (fuente, relleno, etc.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Habilitar llamadas
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Paso 4: guarde la presentación

Finalmente, guarde la presentación con el gráfico configurado.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Ahora ha configurado correctamente llamadas para etiquetas de datos en un gráfico utilizando Aspose.Slides para Java. Personalice el código de acuerdo con sus requisitos de datos y gráficos específicos.

## Código fuente completo para configurar la llamada para la etiqueta de datos en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, exploramos cómo configurar llamadas para etiquetas de datos en un gráfico usando Aspose.Slides para Java. Las llamadas son herramientas valiosas para enfatizar puntos de datos específicos en sus gráficos y presentaciones. Proporcionamos una guía paso a paso junto con el código fuente para ayudarle a lograr esta personalización.

## Preguntas frecuentes

### ¿Cómo personalizo la apariencia de las etiquetas de datos?

Para personalizar la apariencia de las etiquetas de datos, puede modificar propiedades como fuente, relleno y estilos de línea. Por ejemplo:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### ¿Cómo puedo habilitar o deshabilitar llamadas para etiquetas de datos?

 Para habilitar o deshabilitar llamadas para etiquetas de datos, use el`setShowLabelAsDataCallout` método. Configúrelo en`true` para habilitar llamadas y`false`para desactivarlos.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Habilitar llamadas
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Deshabilitar llamadas
```

### ¿Puedo personalizar las líneas guía de las etiquetas de datos?

Sí, puede personalizar las líneas guía de las etiquetas de datos utilizando propiedades como estilo, color y ancho de línea. Por ejemplo:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Habilitar líneas guía
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Estas son algunas opciones de personalización comunes para etiquetas de datos y llamadas en Aspose.Slides para Java. Puede adaptar aún más la apariencia a sus necesidades específicas.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
