---
"description": "Mejore sus presentaciones de PowerPoint con Aspose.Slides para Java. Aprenda a modificar gráficos existentes mediante programación. Guía paso a paso con código fuente para personalizar gráficos."
"linktitle": "Gráfico existente en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Gráfico existente en diapositivas de Java"
"url": "/es/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico existente en diapositivas de Java


## Introducción a los gráficos existentes en diapositivas de Java con Aspose.Slides para Java

En este tutorial, demostraremos cómo modificar un gráfico existente en una presentación de PowerPoint con Aspose.Slides para Java. Repasaremos los pasos para cambiar los datos del gráfico, los nombres de las categorías y los nombres de las series, y para agregar una nueva serie al gráfico. Asegúrese de tener Aspose.Slides para Java configurado en su proyecto.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Biblioteca Aspose.Slides para Java incluida en su proyecto.
2. Una presentación de PowerPoint existente con un gráfico que desea modificar.
3. Configuración del entorno de desarrollo Java.

## Paso 1: Cargar la presentación

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Paso 2: Acceda a la diapositiva y al gráfico

```java
// Acceda a la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);

// Acceda al gráfico en la diapositiva
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Paso 3: Cambiar los datos del gráfico y los nombres de las categorías

```java
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Cambiar los nombres de las categorías de gráficos
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Paso 4: Actualizar la primera serie de gráficos

```java
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Actualizar el nombre de la serie
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Actualizar datos de la serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Paso 5: Actualizar la segunda serie de gráficos

```java
// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Actualizar el nombre de la serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Actualizar datos de la serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Paso 6: Agregar una nueva serie al gráfico

```java
// Añadiendo una nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Tome la tercera serie de gráficos
series = chart.getChartData().getSeries().get_Item(2);

// Rellenar datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Paso 7: Cambiar el tipo de gráfico

```java
// Cambie el tipo de gráfico a Cilindro agrupado
chart.setType(ChartType.ClusteredCylinder);
```

## Paso 8: Guardar la presentación modificada

```java
// Guarde la presentación con el gráfico modificado
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

¡Felicitaciones! Has modificado correctamente un gráfico existente en una presentación de PowerPoint con Aspose.Slides para Java. Ahora puedes usar este código para personalizar gráficos en tus presentaciones de PowerPoint mediante programación.

## Código fuente completo para gráficos existentes en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX // Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Acceda al primer marcador de diapositivas
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
// Ahora actualizando los datos de la serie
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modificar el nombre de la serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Serie de gráficos Take Second
series = chart.getChartData().getSeries().get_Item(1);
// Ahora actualizando los datos de la serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modificar el nombre de la serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Ahora, agregando una nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Toma la 3ª serie de gráficos
series = chart.getChartData().getSeries().get_Item(2);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Guardar presentación con gráfico
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusión

En este completo tutorial, hemos aprendido a modificar un gráfico existente en una presentación de PowerPoint con Aspose.Slides para Java. Siguiendo la guía paso a paso y utilizando ejemplos de código fuente, podrá personalizar y actualizar fácilmente los gráficos para adaptarlos a sus necesidades específicas. A continuación, un resumen de lo que vimos:

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

Puede cambiar el tipo de gráfico mediante el uso de `chart.setType(ChartType.ChartTypeHere)` método. Reemplazar `ChartTypeHere` con el tipo de gráfico deseado, como por ejemplo `ChartType.ClusteredCylinder` en nuestro ejemplo.

### ¿Puedo agregar más puntos de datos a una serie?

Sí, puedes agregar más puntos de datos a una serie usando el `series.getDataPoints().addDataPointForBarSeries(cell)` método. Asegúrese de proporcionar los datos de celda apropiados.

### ¿Cómo actualizo los nombres de las categorías?

Puede actualizar los nombres de las categorías utilizando `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para establecer los nuevos nombres de categorías.

### ¿Cómo modifico los nombres de las series?

Para modificar los nombres de las series, utilice `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` para establecer los nuevos nombres de las series.

### ¿Hay alguna forma de eliminar una serie del gráfico?

Sí, puedes eliminar una serie del gráfico mediante el uso del `chart.getChartData().getSeries().removeAt(index)` método, donde `index` es el índice de la serie que desea eliminar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}