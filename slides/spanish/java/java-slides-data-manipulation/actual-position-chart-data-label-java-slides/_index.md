---
"description": "Aprenda a obtener la posición real de las etiquetas de datos de gráficos en Java Slides usando Aspose.Slides para Java. Guía paso a paso con código fuente."
"linktitle": "Obtener la posición actual de la etiqueta de datos del gráfico en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Obtener la posición actual de la etiqueta de datos del gráfico en diapositivas de Java"
"url": "/es/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtener la posición actual de la etiqueta de datos del gráfico en diapositivas de Java


## Introducción a la obtención de la posición real de la etiqueta de datos de un gráfico en diapositivas de Java

En este tutorial, aprenderá a recuperar la posición real de las etiquetas de datos de un gráfico con Aspose.Slides para Java. Crearemos un programa Java que genera una presentación de PowerPoint con un gráfico, personaliza las etiquetas de datos y luego agrega formas que representan su posición.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java configurada en su proyecto Java.

## Paso 1: Crear una presentación de PowerPoint

Primero, creemos una nueva presentación de PowerPoint y añadamos un gráfico. Personalizaremos las etiquetas de datos del gráfico más adelante en el tutorial.

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

## Paso 2: Personalizar las etiquetas de datos
Ahora, personalicemos las etiquetas de datos de la serie gráfica. Estableceremos su posición y mostraremos los valores.

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

## Paso 3: Obtener la posición real de las etiquetas de datos
En este paso, iteraremos a través de los puntos de datos de la serie de gráficos y recuperaremos la posición real de las etiquetas de datos que tengan un valor mayor a 4. Luego, agregaremos puntos suspensivos para representar estas posiciones.

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

## Paso 4: Guardar la presentación
Por último, guarde la presentación generada en un archivo.

```java
try {
    // ... (código anterior)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Código fuente completo para obtener la posición real de la etiqueta de datos de un gráfico en diapositivas de Java

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

En este tutorial, aprendió a recuperar la posición real de las etiquetas de datos de gráficos en Java Slides usando Aspose.Slides para Java. Ahora puede usar este conocimiento para mejorar sus presentaciones de PowerPoint con etiquetas de datos personalizadas y representaciones visuales de sus posiciones.

## Preguntas frecuentes

### ¿Cómo puedo personalizar las etiquetas de datos en un gráfico?

Para personalizar las etiquetas de datos en un gráfico, puede utilizar el `setDefaultDataLabelFormat` Método en la serie de gráficos y configuración de propiedades como la posición y la visibilidad. Por ejemplo:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### ¿Cómo puedo agregar formas para representar posiciones de etiquetas de datos?

Puede iterar a través de los puntos de datos de una serie de gráficos y utilizar la `getActualX`, `getActualY`, `getActualWidth`, y `getActualHeight` Métodos de la etiqueta de datos para obtener su posición. Luego, puede agregar formas usando `addAutoShape` Método. Aquí tienes un ejemplo:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### ¿Cómo puedo guardar la presentación generada?

Puede guardar la presentación generada utilizando el `save` método. Proporcione la ruta del archivo deseado y el `SaveFormat` como parámetros. Por ejemplo:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}