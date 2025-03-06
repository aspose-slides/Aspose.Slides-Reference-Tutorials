---
title: Agregue color a los puntos de datos en diapositivas de Java
linktitle: Agregue color a los puntos de datos en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar color a puntos de datos en diapositivas de Java usando Aspose.Slides para Java.
type: docs
weight: 10
url: /es/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Introducción a agregar color a puntos de datos en diapositivas de Java

En este tutorial, demostraremos cómo agregar color a puntos de datos en diapositivas de Java usando Aspose.Slides para Java. Esta guía paso a paso incluye ejemplos de código fuente para ayudarle a realizar esta tarea.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Entorno de desarrollo Java
- Biblioteca Aspose.Slides para Java

## Paso 1: crea una nueva presentación

Primero, crearemos una nueva presentación usando Aspose.Slides para Java. Esta presentación servirá como contenedor de nuestro gráfico.

```java
Presentation pres = new Presentation();
```

## Paso 2: agregue un gráfico Sunburst

Ahora, agreguemos un gráfico Sunburst a la presentación. Especificamos el tipo de gráfico, la posición y el tamaño.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Paso 3: acceder a los puntos de datos

 Para modificar puntos de datos en el gráfico, debemos acceder a la`IChartDataPointCollection` objeto.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Paso 4: Personaliza los puntos de datos

En este paso, personalizaremos puntos de datos específicos. Aquí, estamos cambiando el color de los puntos de datos y configurando los ajustes de las etiquetas.

```java
// Personalizar el punto de datos 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Personalizar el punto de datos 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Paso 5: guarde la presentación

Finalmente, guarde la presentación con el gráfico personalizado.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Ha agregado color con éxito a puntos de datos específicos en una diapositiva de Java usando Aspose.Slides para Java.

## Código fuente completo para agregar color a puntos de datos en diapositivas de Java

```java
Presentation pres = new Presentation();
try
{
	// La ruta al directorio de documentos.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//HACER
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendió cómo agregar color a puntos de datos en diapositivas de Java usando Aspose.Slides para Java. Puede personalizar aún más sus gráficos y presentaciones según sus requisitos específicos.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el color de otros puntos de datos?

Para cambiar el color de otros puntos de datos, puede seguir un enfoque similar al que se muestra en el Paso 4. Acceda al punto de datos que desea personalizar y modifique su configuración de color y etiqueta.

### ¿Puedo personalizar otros aspectos del gráfico?

 Sí, puedes personalizar varios aspectos del gráfico, incluidas fuentes, etiquetas, títulos y más. Referirse a[Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para opciones de personalización detalladas.

### ¿Dónde puedo encontrar más ejemplos y documentación?

 Puede encontrar más ejemplos y documentación detallada sobre el uso de Aspose.Slides para Java en el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/java/) sitio web.