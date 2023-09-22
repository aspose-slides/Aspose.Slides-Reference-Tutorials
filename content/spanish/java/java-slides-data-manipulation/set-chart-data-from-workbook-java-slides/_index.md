---
title: Establecer datos de gráficos del libro de trabajo en diapositivas de Java
linktitle: Establecer datos de gráficos del libro de trabajo en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar datos de gráficos de un libro de Excel en Java Slides usando Aspose.Slides. Guía paso a paso con ejemplos de código para presentaciones dinámicas.
type: docs
weight: 15
url: /es/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Introducción a establecer datos de gráficos desde el libro de trabajo en diapositivas de Java

Aspose.Slides para Java es una poderosa biblioteca que permite a los desarrolladores trabajar con presentaciones de PowerPoint mediante programación. Proporciona amplias funciones para crear, manipular y administrar diapositivas de PowerPoint. Un requisito común al trabajar con presentaciones es configurar los datos del gráfico de forma dinámica desde una fuente de datos externa, como un libro de Excel. En este tutorial, demostraremos cómo lograr esto usando Java.

## Requisitos previos

Antes de profundizar en la implementación, asegúrese de tener los siguientes requisitos previos:

- Kit de desarrollo de Java (JDK) instalado en su sistema.
- Biblioteca Aspose.Slides para Java agregada a su proyecto.
- Un libro de Excel con los datos que desea utilizar para el gráfico.

## Paso 1: crea una presentación

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Comenzamos creando una nueva presentación de PowerPoint usando Aspose.Slides para Java.

## Paso 2: agregar un gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

A continuación, agregamos un gráfico a una de las diapositivas de la presentación. En este ejemplo, agregamos un gráfico circular, pero usted puede elegir el tipo de gráfico que se adapte a sus necesidades.

## Paso 3: borrar los datos del gráfico

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Borramos cualquier dato existente del gráfico para prepararlo para nuevos datos del libro de Excel.

## Paso 4: cargar el libro de Excel

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Cargamos el libro de Excel que contiene los datos que queremos usar para el gráfico. Reemplazar`"book1.xlsx"` con la ruta a su archivo de Excel.

## Paso 5: escribir flujo de libro de trabajo en datos del gráfico

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Convertimos los datos del libro de Excel en una secuencia y los escribimos en los datos del gráfico.

## Paso 6: establecer el rango de datos del gráfico

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Especificamos el rango de celdas del libro de Excel que deben usarse como datos para el gráfico. Ajuste el rango según sea necesario para sus datos.

## Paso 7: personalizar la serie de gráficos

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Puede personalizar varias propiedades de la serie de gráficos para que se ajusten a sus necesidades. En este ejemplo, habilitamos varios colores para la serie de gráficos.

## Paso 8: guarde la presentación

```java
pres.save(outPath, SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con los datos del gráfico actualizados en la ruta de salida especificada.

## Código fuente completo para establecer datos de gráficos del libro de trabajo en diapositivas de Java

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, hemos aprendido cómo configurar datos de gráficos de un libro de Excel en Java Slides usando la biblioteca Aspose.Slides para Java. Si sigue la guía paso a paso y utiliza los ejemplos de código fuente proporcionados, puede integrar fácilmente datos de gráficos dinámicos en sus presentaciones de PowerPoint.

## Preguntas frecuentes

### ¿Cómo puedo personalizar la apariencia del gráfico en mi presentación?

Puede personalizar la apariencia del gráfico modificando propiedades como colores, fuentes, etiquetas y más. Consulte la documentación de Aspose.Slides para Java para obtener información detallada sobre las opciones de personalización de gráficos.

### ¿Puedo utilizar datos de un archivo de Excel diferente para el gráfico?

Sí, puede utilizar datos de cualquier archivo de Excel especificando la ruta correcta del archivo al cargar el libro en el código.

### ¿Qué otros tipos de gráficos puedo crear con Aspose.Slides para Java?

Aspose.Slides para Java admite varios tipos de gráficos, incluidos gráficos de barras, gráficos de líneas, gráficos de dispersión y más. Puede elegir el tipo de gráfico que mejor se adapte a sus necesidades de representación de datos.

### ¿Es posible actualizar los datos del gráfico dinámicamente en una presentación en ejecución?

Sí, puede actualizar los datos del gráfico dinámicamente en una presentación modificando el libro subyacente y luego actualizando los datos del gráfico.

### ¿Dónde puedo encontrar más ejemplos y recursos para trabajar con Aspose.Slides para Java?

 Puede explorar ejemplos y recursos adicionales en el[Aspose sitio web](https://www.aspose.com/). Además, la documentación de Aspose.Slides para Java proporciona una guía completa sobre cómo trabajar con la biblioteca.