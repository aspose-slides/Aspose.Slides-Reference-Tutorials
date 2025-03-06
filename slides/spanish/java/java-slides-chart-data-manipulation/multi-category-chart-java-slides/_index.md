---
title: Gráfico de múltiples categorías en diapositivas de Java
linktitle: Gráfico de múltiples categorías en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Cree gráficos de múltiples categorías en diapositivas de Java utilizando Aspose.Slides para Java. Guía paso a paso con código fuente para una visualización de datos impresionante en presentaciones.
weight: 20
url: /es/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de múltiples categorías en diapositivas de Java


## Introducción al gráfico de categorías múltiples en diapositivas de Java con Aspose.Slides

En este tutorial, aprenderemos cómo crear un gráfico de múltiples categorías en diapositivas de Java utilizando la API Aspose.Slides para Java. Esta guía proporcionará instrucciones paso a paso junto con el código fuente para ayudarle a crear un gráfico de columnas agrupadas con múltiples categorías y series.

## Requisitos previos
Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su entorno de desarrollo Java.

## Paso 1: configurar el entorno
Primero, importe las clases necesarias y cree un nuevo objeto de presentación para trabajar con diapositivas.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: agregar una diapositiva y un gráfico
A continuación, cree una diapositiva y agréguele un gráfico de columnas agrupadas.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Paso 3: borrar los datos existentes
Borre cualquier dato existente del gráfico.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Paso 4: configurar categorías de datos
Ahora, configuremos categorías de datos para el gráfico. Crearemos múltiples categorías y las agruparemos.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Añade categorías y agrúpalas
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Paso 5: Agregar series
Ahora, agreguemos una serie al gráfico junto con puntos de datos.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Paso 6: guardar la presentación
Finalmente, guarde la presentación con el gráfico.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Ha creado con éxito un gráfico de múltiples categorías en una diapositiva de Java usando Aspose.Slides. Puede personalizar aún más este gráfico para adaptarlo a sus requisitos específicos.

## Código fuente completo para gráficos de múltiples categorías en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Agregar series
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Guardar presentación con gráfico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, hemos aprendido cómo crear un gráfico de múltiples categorías en diapositivas de Java utilizando la API Aspose.Slides para Java. Revisamos una guía paso a paso con código fuente para crear un gráfico de columnas agrupadas con múltiples categorías y series.

## Preguntas frecuentes

### ¿Cómo puedo personalizar la apariencia del gráfico?

Puede personalizar la apariencia del gráfico modificando propiedades como colores, fuentes y estilos. Consulte la documentación de Aspose.Slides para obtener opciones de personalización detalladas.

### ¿Puedo agregar más series al gráfico?

Sí, puede agregar series adicionales al gráfico siguiendo un proceso similar al que se muestra en el Paso 5.

### ¿Cómo cambio el tipo de gráfico?

 Para cambiar el tipo de gráfico, reemplace`ChartType.ClusteredColumn` con el tipo de gráfico deseado al agregar el gráfico en el Paso 2.

### ¿Cómo puedo agregar un título al gráfico?

 Puede agregar un título al gráfico usando el`ch.getChartTitle().getTextFrame().setText("Chart Title");` método.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
