---
"description": "Aprenda a agregar color a los puntos de datos en diapositivas de Java usando Aspose.Slides para Java."
"linktitle": "Agregar color a los puntos de datos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Agregar color a los puntos de datos en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Agregar color a los puntos de datos en diapositivas de Java


## Introducción a la adición de color a puntos de datos en Java (diapositivas)

En este tutorial, demostraremos cómo agregar color a los puntos de datos en diapositivas de Java usando Aspose.Slides para Java. Esta guía paso a paso incluye ejemplos de código fuente para ayudarle a lograr esta tarea.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Entorno de desarrollo de Java
- Biblioteca Aspose.Slides para Java

## Paso 1: Crear una nueva presentación

Primero, crearemos una nueva presentación con Aspose.Slides para Java. Esta presentación servirá como contenedor para nuestro gráfico.

```java
Presentation pres = new Presentation();
```

## Paso 2: Agregar un gráfico de rayos de sol

Ahora, agreguemos un gráfico Sunburst a la presentación. Especificamos el tipo, la posición y el tamaño del gráfico.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Paso 3: Acceder a los puntos de datos

Para modificar los puntos de datos en el gráfico, necesitamos acceder a la `IChartDataPointCollection` objeto.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Paso 4: Personalizar los puntos de datos

En este paso, personalizaremos puntos de datos específicos. Aquí, cambiaremos el color de los puntos de datos y configuraremos las etiquetas.

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

## Paso 5: Guardar la presentación

Por último, guarde la presentación con el gráfico personalizado.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

¡Listo! Has añadido color a puntos de datos específicos en una diapositiva de Java usando Aspose.Slides para Java.

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

En este tutorial, aprendiste a agregar color a los puntos de datos en diapositivas de Java con Aspose.Slides para Java. Puedes personalizar aún más tus gráficos y presentaciones según tus necesidades.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el color de otros puntos de datos?

Para cambiar el color de otros puntos de datos, puede seguir un enfoque similar al que se muestra en el Paso 4. Acceda al punto de datos que desea personalizar y modifique su configuración de color y etiqueta.

### ¿Puedo personalizar otros aspectos del gráfico?

Sí, puedes personalizar varios aspectos del gráfico, como fuentes, etiquetas, títulos y más. Consulta la [Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para opciones de personalización detalladas.

### ¿Dónde puedo encontrar más ejemplos y documentación?

Puede encontrar más ejemplos y documentación detallada sobre el uso de Aspose.Slides para Java en [Documentación de Aspose.Slides](https://reference.aspose.com/slides/java/) sitio web.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}