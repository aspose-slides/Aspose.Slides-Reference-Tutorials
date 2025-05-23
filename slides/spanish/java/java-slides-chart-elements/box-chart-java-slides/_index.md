---
"description": "Aprenda a crear gráficos de caja en presentaciones Java con Aspose.Slides. Incluye guía paso a paso y código fuente para una visualización de datos eficaz."
"linktitle": "Diagrama de caja en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Diagrama de caja en diapositivas de Java"
"url": "/es/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagrama de caja en diapositivas de Java


## Introducción al gráfico de caja en Aspose.Slides para Java

En este tutorial, le guiaremos a través del proceso de creación de un gráfico de caja con Aspose.Slides para Java. Los gráficos de caja son útiles para visualizar datos estadísticos con varios cuartiles y valores atípicos. Le proporcionaremos instrucciones paso a paso junto con el código fuente para ayudarle a comenzar.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- Biblioteca Aspose.Slides para Java instalada y configurada.
- Un entorno de desarrollo Java configurado.

## Paso 1: Inicializar la presentación

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

En este paso, inicializamos un objeto de presentación utilizando la ruta a un archivo de PowerPoint existente ("test.pptx" en este ejemplo).

## Paso 2: Crea el gráfico de caja

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

En este paso, creamos un gráfico de caja en la primera diapositiva de la presentación. También borramos las categorías y series existentes del gráfico.

## Paso 3: Definir categorías

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

En este paso, definimos las categorías para el gráfico de caja. Usamos el `IChartDataWorkbook` para agregar categorías y etiquetarlas en consecuencia.

## Paso 4: Crea la serie

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Aquí, creamos una serie BoxAndWhisker para el gráfico y configuramos varias opciones como el método de cuartil, la línea media, marcadores de media, puntos internos y puntos atípicos.

## Paso 5: Agregar puntos de datos

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

En este paso, añadimos puntos de datos a la serie BoxAndWhisker. Estos puntos representan los datos estadísticos del gráfico.

## Paso 6: Guardar la presentación

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Por último, guardamos la presentación con el gráfico de caja en un nuevo archivo de PowerPoint llamado "BoxAndWhisker.pptx".

¡Felicitaciones! Ha creado correctamente un gráfico de caja con Aspose.Slides para Java. Puede personalizarlo aún más ajustando diversas propiedades y añadiendo más puntos de datos según sea necesario.

## Código fuente completo para diagramas de caja en Java Slides

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

En este tutorial, aprendimos a crear un gráfico de caja con Aspose.Slides para Java. Los gráficos de caja son herramientas valiosas para visualizar datos estadísticos, incluyendo cuartiles y valores atípicos. Proporcionamos una guía paso a paso junto con el código fuente para ayudarte a empezar a crear gráficos de caja en tus aplicaciones Java.

## Preguntas frecuentes

### ¿Cómo puedo cambiar la apariencia del gráfico de caja?

Puede personalizar la apariencia del gráfico de caja modificando propiedades como estilos de línea, colores y fuentes. Consulte la documentación de Aspose.Slides para Java para obtener más información sobre la personalización de gráficos.

### ¿Puedo agregar series de datos adicionales al gráfico de caja?

Sí, puede agregar varias series de datos al gráfico de caja creando series de datos adicionales. `IChartSeries` objetos y agregarles puntos de datos.

### ¿Qué significa QuartileMethodType.Exclusive?

El `QuartileMethodType.Exclusive` La configuración especifica que los cálculos de cuartiles deben realizarse con el método exclusivo. Puede elegir diferentes métodos de cálculo de cuartiles según sus datos y requisitos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}