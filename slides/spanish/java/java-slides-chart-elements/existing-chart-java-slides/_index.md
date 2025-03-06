---
title: Gráfico existente en diapositivas de Java
linktitle: Gráfico existente en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Mejore sus presentaciones de PowerPoint con Aspose.Slides para Java. Aprenda a modificar gráficos existentes mediante programación. Guía paso a paso con código fuente para la personalización de gráficos.
weight: 12
url: /es/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico existente en diapositivas de Java


## Introducción al gráfico existente en diapositivas de Java utilizando Aspose.Slides para Java

En este tutorial, demostraremos cómo modificar un gráfico existente en una presentación de PowerPoint usando Aspose.Slides para Java. Revisaremos los pasos para cambiar los datos del gráfico, los nombres de las categorías, los nombres de las series y agregaremos una nueva serie al gráfico. Asegúrese de tener Aspose.Slides para Java configurado en su proyecto.

## Requisitos previos

Antes de comenzar, asegúrese de tener implementados los siguientes requisitos previos:

1. Biblioteca Aspose.Slides para Java incluida en su proyecto.
2. Una presentación de PowerPoint existente con un gráfico que desea modificar.
3. Configuración del entorno de desarrollo Java.

## Paso 1: Cargue la presentación

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Paso 2: acceda a la diapositiva y al gráfico

```java
// Accede a la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);

// Accede al gráfico en la diapositiva.
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Paso 3: cambiar los datos del gráfico y los nombres de las categorías

```java
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Cambiar nombres de categorías de gráficos
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Paso 4: actualice la primera serie de gráficos

```java
// Tome la primera serie de gráficos.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Actualizar nombre de la serie
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Actualizar datos de la serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Paso 5: actualice la segunda serie de gráficos

```java
// Tome la segunda serie de gráficos.
series = chart.getChartData().getSeries().get_Item(1);

// Actualizar nombre de la serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Actualizar datos de la serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Paso 6: agregue una nueva serie al gráfico

```java
// Añadiendo una nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Tome la tercera serie de gráficos.
series = chart.getChartData().getSeries().get_Item(2);

// Rellenar datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Paso 7: cambiar el tipo de gráfico

```java
//Cambiar el tipo de gráfico a Cilindro agrupado
chart.setType(ChartType.ClusteredCylinder);
```

## Paso 8: guarde la presentación modificada

```java
// Guarde la presentación con el gráfico modificado.
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

¡Felicidades! Ha modificado con éxito un gráfico existente en una presentación de PowerPoint utilizando Aspose.Slides para Java. Ahora puede utilizar este código para personalizar gráficos en sus presentaciones de PowerPoint mediante programación.

## Código fuente completo para gráficos existentes en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Acceder al primer marcador de diapositivas
ISlide sld = pres.getSlides().get_Item(0);
// Agregar gráfico con datos predeterminados
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Cambiar el nombre de la categoría del gráfico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ahora actualizando datos de la serie.
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modificando el nombre de la serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Ahora actualizando datos de la serie.
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modificando el nombre de la serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Ahora, agregando una nueva serie.
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Tome la tercera serie de gráficos
series = chart.getChartData().getSeries().get_Item(2);
// Ahora completando datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Guardar presentación con gráfico
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusión

En este completo tutorial, hemos aprendido cómo modificar un gráfico existente en una presentación de PowerPoint usando Aspose.Slides para Java. Si sigue la guía paso a paso y utiliza ejemplos de código fuente, puede personalizar y actualizar gráficos fácilmente para cumplir con sus requisitos específicos. Aquí hay un resumen de lo que cubrimos:

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

 Puede cambiar el tipo de gráfico utilizando el`chart.setType(ChartType.ChartTypeHere)` método. Reemplazar`ChartTypeHere` con el tipo de gráfico deseado, como`ChartType.ClusteredCylinder` en nuestro ejemplo.

### ¿Puedo agregar más puntos de datos a una serie?

 Sí, puedes agregar más puntos de datos a una serie usando el`series.getDataPoints().addDataPointForBarSeries(cell)` método. Asegúrese de proporcionar los datos de celda adecuados.

### ¿Cómo actualizo los nombres de las categorías?

 Puede actualizar los nombres de las categorías utilizando`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para establecer los nuevos nombres de categorías.

### ¿Cómo modifico los nombres de las series?

 Para modificar los nombres de las series, utilice`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para establecer los nuevos nombres de las series.

### ¿Hay alguna manera de eliminar una serie del gráfico?

 Sí, puede eliminar una serie del gráfico utilizando el`chart.getChartData().getSeries().removeAt(index)` método, donde`index`es el índice de la serie que desea eliminar.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
