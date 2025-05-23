---
"description": "Aprenda a configurar colores de relleno invertidos para gráficos de Java Slides con Aspose.Slides. Mejore sus visualizaciones de gráficos con esta guía paso a paso y su código fuente."
"linktitle": "Establecer la tabla de colores de relleno invertido en Java Slides"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Establecer la tabla de colores de relleno invertido en Java Slides"
"url": "/es/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Establecer la tabla de colores de relleno invertido en Java Slides


## Introducción a la tabla de colores de relleno e inversión de conjuntos en diapositivas de Java

En este tutorial, demostraremos cómo invertir el color de relleno de un gráfico en Java Slides usando Aspose.Slides para Java. Invertir el color de relleno es una función útil para resaltar valores negativos en un gráfico con un color específico. Proporcionaremos instrucciones paso a paso y el código fuente para lograrlo.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Biblioteca Aspose.Slides para Java instalada.
2. Configuración del entorno de desarrollo Java.

## Paso 1: Crear una presentación

Primero, necesitamos crear una presentación para agregar nuestro gráfico. Puedes usar el siguiente código para crear una presentación:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: Agregar un gráfico

A continuación, agregaremos un gráfico de columnas agrupadas a la presentación. Así es como se hace:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Paso 3: Configurar los datos del gráfico

Ahora, configuremos los datos del gráfico, incluidas las series y categorías:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Añadiendo nuevas series y categorías
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Paso 4: Rellenar los datos de la serie

Ahora, vamos a completar los datos de la serie para el gráfico:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Paso 5: Establecer el color de relleno invertido

Para establecer el color de relleno invertido para la serie de gráficos, puede utilizar el siguiente código:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

En el código anterior, configuramos la serie para invertir el color de relleno para valores negativos y especificamos el color para el relleno invertido.

## Paso 6: Guardar la presentación

Por último, guarde la presentación con el gráfico:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Código fuente completo para la tabla de colores de relleno invertido en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Añadiendo nuevas series y categorías
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Tome la primera serie de gráficos y complete los datos de la serie.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, le mostramos cómo configurar el color de relleno invertido para un gráfico en Java Slides usando Aspose.Slides para Java. Esta función le permite resaltar los valores negativos en sus gráficos con un color específico, lo que hace que sus datos sean visualmente más informativos.

## Preguntas frecuentes

En esta sección, abordaremos algunas preguntas comunes relacionadas con la configuración del color de relleno invertido para un gráfico en Java Slides usando Aspose.Slides para Java.

### ¿Cómo instalo Aspose.Slides para Java?

Puede instalar Aspose.Slides para Java incluyendo los archivos JAR de Aspose.Slides en su proyecto Java. Puede descargar la biblioteca desde [Página de descarga de Aspose.Slides para Java](https://releases.aspose.com/slides/java/). Siga las instrucciones de instalación proporcionadas en la documentación para su entorno de desarrollo específico.

### ¿Puedo personalizar el color del relleno invertido en la serie de gráficos?

Sí, puedes personalizar el color del relleno invertido en la serie de gráficos. En el ejemplo de código proporcionado, `series.getInvertedSolidFillColor().setColor(Color.RED)` La línea establece el color rojo para el relleno invertido. Puedes reemplazar `Color.RED` con cualquier otro color de su elección.

### ¿Cómo puedo modificar el tipo de gráfico en Aspose.Slides para Java?

Puede modificar el tipo de gráfico cambiando el `ChartType` Parámetro al agregar un gráfico a la presentación. En el ejemplo de código, usamos `ChartType.ClusteredColumn`Puede explorar otros tipos de gráficos, como gráficos de líneas, gráficos de barras, gráficos circulares, etc., especificando el tipo adecuado. `ChartType` valor de enumeración.

### ¿Cómo agrego múltiples series de datos a un gráfico?

Para agregar varias series de datos a un gráfico, puede utilizar el `chart.getChartData().getSeries().add(...)` Método para cada serie que desee agregar. Asegúrese de proporcionar los puntos de datos y las etiquetas adecuados para cada serie a fin de que el gráfico se llene con varias series.

### ¿Hay alguna manera de personalizar otros aspectos de la apariencia del gráfico?

Sí, puede personalizar varios aspectos de la apariencia del gráfico, como las etiquetas de los ejes, los títulos, las leyendas y más, con Aspose.Slides para Java. Consulte la documentación para obtener instrucciones detalladas sobre cómo personalizar los elementos y la apariencia del gráfico.

### ¿Puedo guardar el gráfico en diferentes formatos?

Sí, puedes guardar el gráfico en diferentes formatos con Aspose.Slides para Java. En el ejemplo de código proporcionado, guardamos la presentación como un archivo PPTX. Puedes usar diferentes formatos. `SaveFormat` opciones para guardarlo en otros formatos como PDF, PNG o SVG, según sus requisitos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}