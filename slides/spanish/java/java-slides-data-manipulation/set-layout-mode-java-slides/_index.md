---
title: Establecer el modo de diseño en diapositivas de Java
linktitle: Establecer el modo de diseño en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar modos de diseño para diapositivas Java usando Aspose.Slides. Personalice el posicionamiento y el tamaño del gráfico en esta guía paso a paso con código fuente.
weight: 23
url: /es/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a establecer el modo de diseño en diapositivas de Java

En este tutorial, aprenderemos cómo configurar el modo de diseño para un gráfico en diapositivas de Java usando Aspose.Slides para Java. El modo de diseño determina la posición y el tamaño del gráfico dentro de la diapositiva.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/slides/java/).

## Paso 1: crea una presentación

Primero, necesitamos crear una nueva presentación.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Paso 2: agregue una diapositiva y un gráfico

A continuación, le agregaremos una diapositiva y un gráfico. En este ejemplo, crearemos un gráfico de columnas agrupadas.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Paso 3: configurar el diseño del gráfico

 Ahora, configuremos el diseño del gráfico. Ajustaremos la posición y el tamaño del gráfico dentro de la diapositiva usando el`setX`, `setY`, `setWidth`, `setHeight` métodos. Además, estableceremos el`LayoutTargetType` para determinar el modo de diseño.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

En este ejemplo, hemos configurado el gráfico para que su tipo de destino de diseño sea "Interior", lo que significa que se colocará y dimensionará en relación con el área interior de la diapositiva.

## Paso 4: guarde la presentación

Finalmente, guardemos la presentación con la configuración de diseño del gráfico.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Código fuente completo para establecer el modo de diseño en diapositivas de Java

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

 En este tutorial, hemos aprendido cómo configurar el modo de diseño para un gráfico en diapositivas de Java usando Aspose.Slides para Java. Puede personalizar la posición y el tamaño del gráfico según sus requisitos específicos ajustando los valores en el`setX`, `setY`, `setWidth`, `setHeight` , y`setLayoutTargetType`métodos. Esto le brinda control sobre la ubicación de los gráficos dentro de sus diapositivas.

## Preguntas frecuentes

### ¿Cómo cambio el modo de diseño de un gráfico en Aspose.Slides para Java?

 Para cambiar el modo de diseño de un gráfico en Aspose.Slides para Java, puede utilizar el`setLayoutTargetType` método en el área de trazado del gráfico. Puedes configurarlo en cualquiera de los dos`LayoutTargetType.Inner` o`LayoutTargetType.Outer` dependiendo del diseño deseado.

### ¿Puedo personalizar la posición y el tamaño del gráfico dentro de la diapositiva?

 Sí, puede personalizar la posición y el tamaño del gráfico dentro de la diapositiva usando el`setX`, `setY`, `setWidth` , y`setHeight` métodos en el área de trazado del gráfico. Ajuste estos valores para posicionar y dimensionar el gráfico según sus requisitos.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para Java?

 Puede encontrar más información sobre Aspose.Slides para Java en el[documentación](https://reference.aspose.com/slides/java/). Incluye referencias API detalladas y ejemplos para ayudarle a trabajar con diapositivas y gráficos de forma eficaz en Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
