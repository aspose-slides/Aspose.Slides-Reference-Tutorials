---
title: Leyenda del tamaño de fuente en diapositivas de Java
linktitle: Leyenda del tamaño de fuente en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Mejore las presentaciones de PowerPoint con Aspose.Slides para Java. Aprenda cómo personalizar los tamaños de fuente de las leyendas y más en nuestra guía paso a paso.
type: docs
weight: 13
url: /es/java/chart-elements/font-size-legend-java-slides/
---

## Introducción a la leyenda del tamaño de fuente en diapositivas de Java

En este tutorial, aprenderá cómo personalizar el tamaño de fuente de la leyenda en una diapositiva de PowerPoint usando Aspose.Slides para Java. Proporcionaremos instrucciones paso a paso y código fuente para realizar esta tarea.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Inicialice la presentación

Primero, importe las clases necesarias e inicialice su presentación de PowerPoint.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Reemplazar`"Your Document Directory"` con la ruta real a su archivo de PowerPoint.

## Paso 2: agregar un gráfico

A continuación, agregaremos un gráfico a la diapositiva y estableceremos el tamaño de fuente de la leyenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 En este código, creamos un gráfico de columnas agrupadas en la primera diapositiva y configuramos el tamaño de fuente del texto de la leyenda en 20 puntos. Puedes ajustar el`setFontHeight`valor para cambiar el tamaño de fuente según sea necesario.

## Paso 3: personalizar los valores del eje

Ahora, personalicemos los valores del eje vertical del gráfico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aquí, establecemos los valores mínimo y máximo para el eje vertical. Puede modificar los valores según sus requisitos de datos.

## Paso 4: guarde la presentación

Finalmente, guarde la presentación modificada en un archivo nuevo.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Este código guarda la presentación modificada como "output.pptx" en el directorio especificado.

## Código fuente completo para la leyenda del tamaño de fuente en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

Ha personalizado con éxito el tamaño de fuente de la leyenda en una diapositiva de PowerPoint de Java utilizando Aspose.Slides para Java. Puede explorar más a fondo las capacidades de Aspose.Slides para crear presentaciones interactivas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo cambio el tamaño de fuente del texto de la leyenda en un gráfico?

Para cambiar el tamaño de fuente del texto de la leyenda en un gráfico, puede utilizar el siguiente código:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 En este código, creamos un gráfico y configuramos el tamaño de fuente del texto de la leyenda en 20 puntos. Puedes ajustar el`setFontHeight` valor para cambiar el tamaño de fuente.

### ¿Puedo personalizar otras propiedades de la leyenda en un gráfico?

Sí, puedes personalizar varias propiedades de la leyenda en un gráfico usando Aspose.Slides. Algunas de las propiedades comunes que puede personalizar incluyen el formato del texto, la posición, la visibilidad y más. Por ejemplo, para cambiar la posición de la leyenda, puedes usar:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Este código configura la leyenda para que aparezca en la parte inferior del gráfico. Explore la documentación de Aspose.Slides para obtener más opciones de personalización.

### ¿Cómo configuro valores mínimos y máximos para el eje vertical en un gráfico?

Para establecer valores mínimos y máximos para el eje vertical en un gráfico, puede utilizar el siguiente código:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aquí, deshabilitamos el escalado automático del eje y especificamos los valores mínimo y máximo para el eje vertical. Ajuste los valores según sea necesario para los datos de su gráfico.

### ¿Dónde puedo encontrar más información y documentación para Aspose.Slides?

 Puede encontrar documentación completa y referencias de API para Aspose.Slides para Java en el sitio web de documentación de Aspose. Visita[aquí](https://reference.aspose.com/slides/java/) para obtener información detallada sobre el uso de la biblioteca.