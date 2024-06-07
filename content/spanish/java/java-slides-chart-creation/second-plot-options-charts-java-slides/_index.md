---
title: Opciones de segunda trama para gráficos en diapositivas de Java
linktitle: Opciones de segunda trama para gráficos en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a personalizar gráficos en Java Slides usando Aspose.Slides para Java. Explora opciones de segunda trama y mejora tus presentaciones.
type: docs
weight: 12
url: /es/java/chart-creation/second-plot-options-charts-java-slides/
---

## Introducción a las opciones de segundo gráfico para gráficos en diapositivas de Java

En este tutorial, exploraremos cómo agregar segundas opciones de trazado a los gráficos usando Aspose.Slides para Java. Las opciones del segundo gráfico le permiten personalizar la apariencia y el comportamiento de los gráficos, particularmente en escenarios como los gráficos circulares. Proporcionaremos instrucciones paso a paso y ejemplos de código fuente para lograrlo. 

## Requisitos previos
Antes de comenzar, asegúrese de tener Aspose.Slides para Java instalado y configurado en su proyecto Java.

## Paso 1: crea una presentación
Comencemos creando una nueva presentación:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

## Paso 2: agregar un gráfico a una diapositiva
A continuación, agregaremos un gráfico a una diapositiva. En este ejemplo, crearemos un gráfico circular:

```java
// Agregar gráfico en la diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Paso 3: personalizar las propiedades del gráfico
Ahora, establezcamos diferentes propiedades para el gráfico, incluidas las segundas opciones de trazado:

```java
// Mostrar etiquetas de datos para la primera serie.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Establecer el tamaño del segundo pastel (en porcentaje)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dividir el pastel por porcentaje
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Establecer la posición de la división
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Paso 4: guarde la presentación
Finalmente, guarde la presentación con el gráfico y las segundas opciones de trazado:

```java
// Escribir presentación en disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Código fuente completo para las opciones de la segunda trama

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
// Agregar gráfico en la diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Establecer diferentes propiedades
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Escribir presentación en disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, aprendimos cómo agregar segundas opciones de trazado a gráficos en Java Slides usando Aspose.Slides para Java. Puede personalizar varias propiedades para mejorar la apariencia y funcionalidad de sus gráficos, haciendo que sus presentaciones sean más informativas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tamaño del segundo pastel en un gráfico circular?

 Para cambiar el tamaño del segundo gráfico circular en un gráfico circular, utilice el`setSecondPieSize` método como se muestra en el ejemplo de código anterior. Ajuste el valor para especificar el tamaño en porcentaje.

###  Que hace`PieSplitBy` control in a Pie of Pie chart?

 El`PieSplitBy` La propiedad controla cómo se divide el gráfico circular. Puedes configurarlo en cualquiera de los dos`PieSplitType.ByPercentage` o`PieSplitType.ByValue` para dividir el gráfico por porcentaje o por un valor específico, respectivamente.

### ¿Cómo configuro la posición de la división en un gráfico circular?

Puede establecer la posición de la división en un gráfico circular utilizando el`setPieSplitPosition` método. Ajuste el valor para especificar la posición deseada.