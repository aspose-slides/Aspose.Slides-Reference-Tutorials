---
title: Gráfico de cuadros en diapositivas de Java
linktitle: Gráfico de cuadros en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear gráficos de cajas en presentaciones Java con Aspose.Slides. Guía paso a paso y código fuente incluidos para una visualización de datos eficaz.
weight: 10
url: /es/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de cuadros en diapositivas de Java


## Introducción al gráfico de cajas en Aspose.Slides para Java

En este tutorial, lo guiaremos a través del proceso de creación de un gráfico de caja usando Aspose.Slides para Java. Los gráficos de cajas son útiles para visualizar datos estadísticos con varios cuartiles y valores atípicos. Le proporcionaremos instrucciones paso a paso junto con el código fuente para ayudarle a comenzar.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Biblioteca Aspose.Slides para Java instalada y configurada.
- Un entorno de desarrollo Java configurado.

## Paso 1: Inicialice la presentación

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

En este paso, inicializamos un objeto de presentación usando la ruta a un archivo de PowerPoint existente ("test.pptx" en este ejemplo).

## Paso 2: crea el gráfico de cajas

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

En este paso, creamos una forma de gráfico de cuadro en la primera diapositiva de la presentación. También borramos del gráfico cualquier categoría y serie existente.

## Paso 3: definir categorías

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 En este paso, definimos las categorías para el gráfico de cajas. Usamos el`IChartDataWorkbook` para agregar categorías y etiquetarlas en consecuencia.

## Paso 4: crea la serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Aquí, creamos una serie BoxAndWhisker para el gráfico y configuramos varias opciones como el método de cuartil, la línea media, los marcadores de media, los puntos internos y los puntos atípicos.

## Paso 5: agregar puntos de datos

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

En este paso, agregamos puntos de datos a la serie BoxAndWhisker. Estos puntos de datos representan los datos estadísticos del gráfico.

## Paso 6: guarde la presentación

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Finalmente, guardamos la presentación con Box Chart en un nuevo archivo de PowerPoint llamado "BoxAndWhisker.pptx".

¡Felicidades! Ha creado con éxito un gráfico de caja utilizando Aspose.Slides para Java. Puede personalizar aún más el gráfico ajustando varias propiedades y agregando más puntos de datos según sea necesario.

## Código fuente completo para el gráfico de cuadros en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, hemos aprendido cómo crear un gráfico de caja usando Aspose.Slides para Java. Los gráficos de cajas son herramientas valiosas para visualizar datos estadísticos, incluidos cuartiles y valores atípicos. Proporcionamos una guía paso a paso junto con el código fuente para ayudarle a comenzar a crear Box Charts en sus aplicaciones Java.

## Preguntas frecuentes

### ¿Cómo puedo cambiar la apariencia del gráfico de cuadros?

Puede personalizar la apariencia del gráfico de cuadros modificando propiedades como estilos de línea, colores y fuentes. Consulte la documentación de Aspose.Slides para Java para obtener detalles sobre la personalización de gráficos.

### ¿Puedo agregar series de datos adicionales al gráfico de cajas?

 Sí, puede agregar varias series de datos al gráfico de cuadros creando`IChartSeries` objetos y agregarles puntos de datos.

### ¿Qué significa QuartileMethodType.Exclusive?

 El`QuartileMethodType.Exclusive` La configuración especifica que los cálculos de cuartiles deben realizarse utilizando el método exclusivo. Puede elegir diferentes métodos de cálculo de cuartiles según sus datos y requisitos.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
