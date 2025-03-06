---
title: Gráfico de líneas de tendencia en diapositivas de Java
linktitle: Gráfico de líneas de tendencia en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar varias líneas de tendencia a las diapositivas de Java usando Aspose.Slides para Java. Guía paso a paso con ejemplos de código para una visualización de datos eficaz.
weight: 15
url: /es/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a las líneas de tendencia del gráfico en diapositivas de Java: una guía paso a paso

En esta guía completa, exploraremos cómo crear líneas de tendencia de gráficos en Java Slides usando Aspose.Slides para Java. Las líneas de tendencia de los gráficos pueden ser una valiosa adición a sus presentaciones, ya que ayudan a visualizar y analizar las tendencias de los datos de manera efectiva. Lo guiaremos a través del proceso con explicaciones claras y ejemplos de código.

## Requisitos previos

Antes de sumergirnos en la creación de líneas de tendencia gráficas, asegúrese de cumplir con los siguientes requisitos previos:

- Entorno de desarrollo Java
- Biblioteca Aspose.Slides para Java
- Un editor de código de su elección

## Paso 1: Comenzar

Comencemos configurando el entorno necesario y creando una nueva presentación:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Cree un directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Creando una presentación vacía
Presentation pres = new Presentation();
```

Hemos inicializado nuestra presentación y ahora estamos listos para agregar un gráfico de columnas agrupadas:

```java
// Crear un gráfico de columnas agrupadas
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Paso 2: agregar una línea de tendencia exponencial

Comencemos agregando una línea de tendencia exponencial a nuestra serie de gráficos:

```java
// Agregar una línea de tendencia exponencial para la serie de gráficos 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Paso 3: agregar una línea de tendencia lineal

continuación, agregaremos una línea de tendencia lineal a nuestra serie de gráficos:

```java
// Agregar una línea de tendencia lineal para la serie de gráficos 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Paso 4: agregar una línea de tendencia logarítmica

Ahora, agreguemos una línea de tendencia logarítmica a una serie de gráficos diferente:

```java
// Agregar una línea de tendencia logarítmica para la serie de gráficos 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Paso 5: Agregar una línea de tendencia de media móvil

También podemos agregar una línea de tendencia de media móvil:

```java
// Agregar una línea de tendencia de promedio móvil para la serie de gráficos 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Paso 6: Agregar una línea de tendencia polinómica

Agregar una línea de tendencia polinómica:

```java
// Agregar una línea de tendencia polinómica para la serie de gráficos 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Paso 7: Agregar línea de tendencia de energía

Finalmente, agreguemos una línea de tendencia de potencia:

```java
// Agregar línea de tendencia de energía para la serie de gráficos 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Paso 8: guardar la presentación

Ahora que hemos agregado varias líneas de tendencia a nuestro gráfico, guardemos la presentación:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

¡Felicidades! Ha creado con éxito una presentación con diferentes tipos de líneas de tendencia en Java Slides utilizando Aspose.Slides para Java.

## Código fuente completo para líneas de tendencia de gráficos en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Cree un directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Creando una presentación vacía
Presentation pres = new Presentation();
// Crear un gráfico de columnas agrupadas
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Agregar una línea de tendencia potencial para la serie de gráficos 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Agregar una línea de tendencia lineal para la serie de gráficos 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Agregar una línea de tendencia logarítmica para la serie de gráficos 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Agregar línea de tendencia MovingAverage para la serie de gráficos 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Agregar una línea de tendencia polinómica para la serie de gráficos 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Agregar línea de tendencia de energía para la serie de gráficos 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Guardar presentación
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, aprendimos cómo agregar diferentes tipos de líneas de tendencia a gráficos en Java Slides usando la biblioteca Aspose.Slides para Java. Ya sea que esté trabajando en análisis de datos o creando presentaciones informativas, la capacidad de visualizar tendencias puede ser una herramienta poderosa.

## Preguntas frecuentes

### ¿Cómo cambio el color de una línea de tendencia en Aspose.Slides para Java?

 Para cambiar el color de una línea de tendencia, puede utilizar el`getSolidFillColor().setColor(Color)` método, como se muestra en el ejemplo para agregar una línea de tendencia lineal.

### ¿Puedo agregar varias líneas de tendencia a una única serie de gráficos?

Sí, puedes agregar varias líneas de tendencia a una sola serie de gráficos. Simplemente llame al`getTrendLines().add()` método para cada línea de tendencia que desee agregar.

### ¿Cómo elimino una línea de tendencia de un gráfico en Aspose.Slides para Java?

 Para eliminar una línea de tendencia de un gráfico, puede utilizar el`removeAt(int index)` método, especificando el índice de la línea de tendencia que desea eliminar.

### ¿Es posible personalizar la visualización de la ecuación de la línea de tendencia?

 Sí, puede personalizar la visualización de la ecuación de la línea de tendencia utilizando el`setDisplayEquation(boolean)` método, como se demuestra en el ejemplo.

### ¿Cómo puedo acceder a más recursos y ejemplos de Aspose.Slides para Java?

 Puede acceder a recursos, documentación y ejemplos adicionales para Aspose.Slides para Java en el[Aspose sitio web](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
