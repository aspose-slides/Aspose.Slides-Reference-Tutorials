---
"description": "Aprenda a configurar un formato de fecha para el eje de categorías en un gráfico de PowerPoint con Aspose.Slides para Java. Guía paso a paso con código fuente."
"linktitle": "Configuración del formato de fecha para el eje de categorías en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Configuración del formato de fecha para el eje de categorías en diapositivas de Java"
"url": "/es/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Configuración del formato de fecha para el eje de categorías en diapositivas de Java


## Introducción a la configuración del formato de fecha para el eje de categorías en diapositivas de Java

En este tutorial, aprenderemos a configurar un formato de fecha para el eje de categorías en un gráfico de PowerPoint con Aspose.Slides para Java. Aspose.Slides para Java es una potente biblioteca que permite crear, manipular y gestionar presentaciones de PowerPoint mediante programación.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Biblioteca Aspose.Slides para Java (puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).
2. Configuración del entorno de desarrollo Java.

## Paso 1: Crear una presentación de PowerPoint

Primero, necesitamos crear una presentación de PowerPoint donde añadiremos un gráfico. Asegúrate de haber importado las clases Aspose.Slides necesarias.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: Agregar un gráfico a la diapositiva

Ahora, agreguemos un gráfico a la diapositiva de PowerPoint. En este ejemplo, usaremos un gráfico de áreas.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Paso 3: Preparar los datos del gráfico

Configuraremos los datos y las categorías del gráfico. En este ejemplo, usaremos categorías de fecha.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Agregar categorías de fechas
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Adición de series de datos
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Paso 4: Personalizar el eje de categorías
Ahora, personalicemos el eje de categorías para mostrar las fechas en un formato específico (por ejemplo, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Paso 5: Guardar la presentación
Por último, guarde la presentación de PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

¡Listo! Has configurado correctamente el formato de fecha para el eje de categorías en un gráfico de PowerPoint con Aspose.Slides para Java.

## Código fuente completo para configurar el formato de fecha del eje de categorías en diapositivas de Java

```java
	// La ruta al directorio de documentos.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Conclusión

Ha personalizado correctamente el formato de fecha del eje de categorías en un gráfico de Java Slides con Aspose.Slides para Java. Esto le permite presentar los valores de fecha en el formato deseado en sus gráficos. Explore otras opciones de personalización según sus necesidades.

## Preguntas frecuentes

### ¿Cómo cambio el formato de fecha para el eje de categorías?

Para cambiar el formato de fecha para el eje de categorías, utilice el `setNumberFormat` en el eje de categorías y proporcione el formato de fecha deseado, como "aaaa-MM-dd" o "MM/aaaa". Asegúrese de configurar `setNumberFormatLinkedToSource(false)` para anular el formato predeterminado.

### ¿Puedo utilizar diferentes formatos de fecha para diferentes gráficos en la misma presentación?

Sí, puede configurar diferentes formatos de fecha para los ejes de categorías en distintos gráficos de la misma presentación. Simplemente personalice el eje de categorías de cada gráfico según sus necesidades.

### ¿Cómo agrego más puntos de datos al gráfico?

Para agregar más puntos de datos al gráfico, utilice el `getDataPoints().addDataPointForLineSeries` método sobre la serie de datos y proporcionar los valores de los datos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}