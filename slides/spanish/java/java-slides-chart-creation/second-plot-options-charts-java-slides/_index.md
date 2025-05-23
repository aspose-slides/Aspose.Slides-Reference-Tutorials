---
"description": "Aprenda a personalizar gráficos en Java Slides con Aspose.Slides para Java. Explore las opciones de gráficos secundarios y mejore sus presentaciones."
"linktitle": "Opciones de segundo gráfico para gráficos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Opciones de segundo gráfico para gráficos en diapositivas de Java"
"url": "/es/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opciones de segundo gráfico para gráficos en diapositivas de Java


## Introducción a las opciones de segundo gráfico para gráficos en diapositivas de Java

En este tutorial, exploraremos cómo agregar opciones de gráfico secundario a los gráficos usando Aspose.Slides para Java. Estas opciones permiten personalizar la apariencia y el comportamiento de los gráficos, especialmente en escenarios como los gráficos circulares. Proporcionaremos instrucciones paso a paso y ejemplos de código fuente para lograrlo. 

## Prerrequisitos
Antes de comenzar, asegúrese de tener Aspose.Slides para Java instalado y configurado en su proyecto Java.

## Paso 1: Crear una presentación
Comencemos creando una nueva presentación:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

## Paso 2: Agregar un gráfico a una diapositiva
A continuación, agregaremos un gráfico a una diapositiva. En este ejemplo, crearemos un gráfico circular:

```java
// Agregar gráfico a la diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Paso 3: Personalizar las propiedades del gráfico
Ahora, configuremos diferentes propiedades para el gráfico, incluidas las opciones del segundo gráfico:

```java
// Mostrar etiquetas de datos para la primera serie
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Establecer el tamaño del segundo gráfico circular (en porcentaje)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dividir el pastel por porcentaje
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Establecer la posición de la división
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Paso 4: Guardar la presentación
Por último, guarde la presentación con las opciones de gráfico y segundo gráfico:

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
// Agregar gráfico a la diapositiva
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

En este tutorial, aprendimos a añadir opciones de segundo gráfico a los gráficos en Java Slides usando Aspose.Slides para Java. Puedes personalizar diversas propiedades para mejorar la apariencia y la funcionalidad de tus gráficos, haciendo que tus presentaciones sean más informativas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tamaño del segundo gráfico circular en un gráfico circular?

Para cambiar el tamaño del segundo gráfico circular en un gráfico circular, utilice el `setSecondPieSize` Método como se muestra en el ejemplo de código anterior. Ajuste el valor para especificar el tamaño en porcentaje.

### ¿Qué significa? `PieSplitBy` ¿Control en un gráfico circular?

El `PieSplitBy` La propiedad controla cómo se divide el gráfico circular. Puede configurarla como `PieSplitType.ByPercentage` o `PieSplitType.ByValue` para dividir el gráfico por porcentaje o por un valor específico, respectivamente.

### ¿Cómo establezco la posición de la división en un gráfico circular?

Puede establecer la posición de la división en un gráfico circular utilizando el `setPieSplitPosition` método. Ajuste el valor para especificar la posición deseada.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}