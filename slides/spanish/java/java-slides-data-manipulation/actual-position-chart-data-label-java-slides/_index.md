---
title: Obtener la posición real de la etiqueta de datos del gráfico en diapositivas de Java
linktitle: Obtener la posición real de la etiqueta de datos del gráfico en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo obtener la posición real de las etiquetas de datos del gráfico en Java Slides usando Aspose.Slides para Java. Guía paso a paso con código fuente.
weight: 18
url: /es/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a la obtención de la posición real de la etiqueta de datos del gráfico en diapositivas de Java

En este tutorial, aprenderá cómo recuperar la posición real de las etiquetas de datos del gráfico usando Aspose.Slides para Java. Crearemos un programa Java que genere una presentación de PowerPoint con un gráfico, personalice las etiquetas de datos y luego agregue formas que representen las posiciones de estas etiquetas de datos.

## Requisitos previos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java configurada en su proyecto Java.

## Paso 1: crea una presentación de PowerPoint

Primero, creemos una nueva presentación de PowerPoint y agreguemosle un gráfico. Personalizaremos las etiquetas de datos del gráfico más adelante en el tutorial.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Paso 2: personaliza las etiquetas de datos
Ahora, personalicemos las etiquetas de datos para la serie de gráficos. Estableceremos su posición y mostraremos los valores.

```java
try {
    // ... (código anterior)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (código restante)
} finally {
    if (pres != null) pres.dispose();
}
```

## Paso 3: obtener la posición real de las etiquetas de datos
En este paso, recorreremos los puntos de datos de la serie de gráficos y recuperaremos la posición real de las etiquetas de datos que tienen un valor mayor que 4. Luego agregaremos elipses para representar estas posiciones.

```java
try {
    // ... (código anterior)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (código restante)
} finally {
    if (pres != null) pres.dispose();
}
```

## Paso 4: guarde la presentación
Finalmente, guarde la presentación generada en un archivo.

```java
try {
    // ... (código anterior)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Código fuente completo para obtener la posición real de la etiqueta de datos del gráfico en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//HACER
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendió cómo recuperar la posición real de las etiquetas de datos del gráfico en Java Slides usando Aspose.Slides para Java. Ahora puede utilizar este conocimiento para mejorar sus presentaciones de PowerPoint con etiquetas de datos personalizadas y representaciones visuales de sus posiciones.

## Preguntas frecuentes

### ¿Cómo puedo personalizar las etiquetas de datos en un gráfico?

 Para personalizar las etiquetas de datos en un gráfico, puede utilizar el`setDefaultDataLabelFormat` método en la serie de gráficos y establecer propiedades como posición y visibilidad. Por ejemplo:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### ¿Cómo puedo agregar formas para representar las posiciones de las etiquetas de datos?

 Puede iterar a través de los puntos de datos de una serie de gráficos y utilizar el`getActualX`, `getActualY`, `getActualWidth` , y`getActualHeight`métodos de la etiqueta de datos para obtener su posición. Luego, puedes agregar formas usando el`addAutoShape` método. He aquí un ejemplo:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### ¿Cómo puedo guardar la presentación generada?

 Puede guardar la presentación generada usando el`save` método. Proporcione la ruta del archivo deseada y el`SaveFormat` como parámetros. Por ejemplo:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
