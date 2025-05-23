---
"description": "Aprenda a configurar modos de diseño para diapositivas de Java con Aspose.Slides. Personalice la posición y el tamaño de los gráficos con esta guía paso a paso con código fuente."
"linktitle": "Establecer el modo de diseño en Java Slides"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Establecer el modo de diseño en Java Slides"
"url": "/es/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Establecer el modo de diseño en Java Slides


## Introducción al modo de diseño de conjuntos en diapositivas de Java

En este tutorial, aprenderemos a configurar el modo de diseño de un gráfico en diapositivas de Java con Aspose.Slides para Java. El modo de diseño determina la posición y el tamaño del gráfico dentro de la diapositiva.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Crear una presentación

Primero necesitamos crear una nueva presentación.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Paso 2: Agregar una diapositiva y un gráfico

A continuación, le agregaremos una diapositiva y un gráfico. En este ejemplo, crearemos un gráfico de columnas agrupadas.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Paso 3: Establecer el diseño del gráfico

Ahora, configuremos el diseño del gráfico. Ajustaremos la posición y el tamaño del gráfico dentro de la diapositiva usando `setX`, `setY`, `setWidth`, `setHeight` métodos. Además, configuraremos el `LayoutTargetType` para determinar el modo de diseño.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

En este ejemplo, hemos configurado el gráfico para que tenga como tipo de destino de diseño "Interno", lo que significa que se posicionará y dimensionará en relación con el área interna de la diapositiva.

## Paso 4: Guardar la presentación

Por último, guardemos la presentación con la configuración del diseño del gráfico.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Código fuente completo para el modo de diseño en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

En este tutorial, aprendimos a configurar el modo de diseño de un gráfico en diapositivas de Java con Aspose.Slides para Java. Puede personalizar la posición y el tamaño del gráfico según sus necesidades específicas ajustando los valores en el... `setX`, `setY`, `setWidth`, `setHeight`, y `setLayoutTargetType` métodos. Esto le permite controlar la ubicación de los gráficos dentro de sus diapositivas.

## Preguntas frecuentes

### ¿Cómo cambio el modo de diseño de un gráfico en Aspose.Slides para Java?

Para cambiar el modo de diseño de un gráfico en Aspose.Slides para Java, puede utilizar el `setLayoutTargetType` método en el área de trazado del gráfico. Puede configurarlo en `LayoutTargetType.Inner` o `LayoutTargetType.Outer` dependiendo del diseño deseado.

### ¿Puedo personalizar la posición y el tamaño del gráfico dentro de la diapositiva?

Sí, puede personalizar la posición y el tamaño del gráfico dentro de la diapositiva utilizando el `setX`, `setY`, `setWidth`, y `setHeight` Métodos en el área de trazado del gráfico. Ajuste estos valores para posicionar y dimensionar el gráfico según sus necesidades.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para Java?

Puede encontrar más información sobre Aspose.Slides para Java en [documentación](https://reference.aspose.com/slides/java/)Incluye referencias API detalladas y ejemplos para ayudarle a trabajar con diapositivas y gráficos de manera eficaz en Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}