---
title: Creación de gráficos radiales en diapositivas Java
linktitle: Creación de gráficos radiales en diapositivas Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear gráficos radiales en presentaciones de PowerPoint de Java utilizando Aspose.Slides para la API de Java.
type: docs
weight: 10
url: /es/java/chart-creation/radar-chart-creating-java-slides/
---

## Introducción a la creación de un gráfico radial en diapositivas de Java

En este tutorial, lo guiaremos a través del proceso de creación de un gráfico radial utilizando la API Aspose.Slides para Java. Los gráficos radiales son útiles para visualizar datos en un patrón circular, lo que facilita la comparación de varias series de datos. Proporcionaremos instrucciones paso a paso junto con el código fuente de Java.

## Requisitos previos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java integrada en su proyecto. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/slides/java/).

## Paso 1: configurar la presentación

Comencemos configurando una nueva presentación de PowerPoint y agregándole una diapositiva.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Paso 2: agregar un gráfico de radar

A continuación, agregaremos un gráfico de radar a la diapositiva. Especificaremos la posición y las dimensiones del gráfico.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Paso 3: configurar los datos del gráfico

Ahora configuraremos los datos del gráfico. Esto implica crear un libro de datos, agregar categorías y agregar series.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Establecer título del gráfico
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Eliminar series y categorías generadas por defecto
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Agregar nuevas categorías
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Añadiendo nueva serie
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Paso 4: completar los datos de la serie

Ahora, completaremos los datos de la serie para nuestro gráfico de radar.

```java
// Complete los datos de la serie para la Serie 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Establecer color de serie
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Completar los datos de la serie para la Serie 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Establecer color de serie
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Paso 5: Personalizar ejes y leyendas

Personalicemos el eje y las leyendas de nuestro gráfico de radar.

```java
//Establecer posición de leyenda
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Configuración de las propiedades del texto del eje de categorías
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Configuración de propiedades de texto de leyendas
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Configuración de las propiedades del texto del eje de valores
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Configuración del formato del número del eje del valor
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Configuración del valor de unidad principal del gráfico
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Paso 6: guardar la presentación

Finalmente, guarde la presentación generada con el gráfico radar.

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

¡Eso es todo! Ha creado con éxito un gráfico de radar en una presentación de PowerPoint utilizando Aspose.Slides para Java. Ahora puede personalizar aún más este ejemplo para adaptarlo a sus necesidades específicas.

## Código fuente completo para la creación de gráficos radiales en diapositivas Java

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Acceder a la primera diapositiva
	ISlide sld = pres.getSlides().get_Item(0);
	// Agregar gráfico de radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Configuración del índice de la hoja de datos del gráfico
	int defaultWorksheetIndex = 0;
	// Obtener la hoja de trabajo de datos del gráfico
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Establecer título del gráfico
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Eliminar series y categorías generadas por defecto
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Agregar nuevas categorías
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Añadiendo nueva serie
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Ahora completando datos de series
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Establecer color de serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ahora completando datos de otra serie
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Establecer color de serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	//Establecer posición de leyenda
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Configuración de las propiedades del texto del eje de categorías
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Configuración de propiedades de texto de leyendas
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Configuración de las propiedades del texto del eje de valores
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Configuración del formato del número del eje del valor
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Configuración del valor de unidad principal del gráfico
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Guardar presentación generada
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendió cómo crear un gráfico de radar en una presentación de PowerPoint usando Aspose.Slides para Java. Puede aplicar estos conceptos para visualizar y presentar sus datos de manera efectiva en sus aplicaciones Java.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el título del gráfico?

Para cambiar el título del gráfico, modifique la siguiente línea:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### ¿Puedo agregar más series de datos al gráfico de radar?

Sí, puede agregar más series de datos siguiendo los pasos del "Paso 3" y el "Paso 4" para cada serie adicional que desee incluir.

### ¿Cómo personalizo los colores del gráfico?

 Puedes personalizar los colores de la serie modificando las líneas que configuran el`SolidFillColor` propiedad para cada serie. Por ejemplo:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### ¿Cómo puedo cambiar las etiquetas de los ejes y el formato?

Consulte el "Paso 5" para personalizar las etiquetas y el formato de los ejes, incluido el tamaño y el color de la fuente.

### ¿Cómo guardo el gráfico en un formato de archivo diferente?

 Puede cambiar el formato de salida modificando la extensión del archivo en el`outPath`variable y utilizando el adecuado`SaveFormat` . Por ejemplo, para guardar como PDF, utilice`SaveFormat.Pdf`.