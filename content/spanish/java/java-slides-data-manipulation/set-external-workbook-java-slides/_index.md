---
title: Establecer un libro de trabajo externo en diapositivas de Java
linktitle: Establecer un libro de trabajo externo en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar libros de trabajo externos en Java Slides usando Aspose.Slides para Java. Cree presentaciones dinámicas con integración de datos de Excel.
type: docs
weight: 19
url: /es/java/data-manipulation/set-external-workbook-java-slides/
---

## Introducción a configurar un libro de trabajo externo en diapositivas de Java

En este tutorial, exploraremos cómo configurar un libro de trabajo externo en Java Slides usando Aspose.Slides. Aprenderá cómo crear una presentación de PowerPoint con un gráfico que haga referencia a datos de un libro de Excel externo. Al final de esta guía, comprenderá claramente cómo integrar datos externos en sus presentaciones de Java Slides.

## Requisitos previos

Antes de profundizar en la implementación, asegúrese de tener los siguientes requisitos previos:

- Kit de desarrollo de Java (JDK) instalado en su sistema.
- Biblioteca Aspose.Slides para Java agregada a su proyecto.
- Un libro de Excel con los datos a los que desea hacer referencia en su presentación.

## Paso 1: crea una nueva presentación

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Comenzamos creando una nueva presentación de PowerPoint usando Aspose.Slides.

## Paso 2: agregar un gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

A continuación, insertamos un gráfico circular en la presentación. Puede personalizar el tipo de gráfico y la posición según sea necesario.

## Paso 3: acceder al libro de trabajo externo

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Para acceder al libro de trabajo externo, utilizamos el`setExternalWorkbook` método y proporcione la ruta al libro de Excel que contiene los datos.

## Paso 4: vincular datos del gráfico

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Vinculamos el gráfico a los datos del libro de trabajo externo especificando las referencias de celda para series y categorías.

## Paso 5: guarde la presentación

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con la referencia del libro externo como un archivo de PowerPoint.

## Código fuente completo para establecer un libro de trabajo externo en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, hemos aprendido cómo configurar un libro de trabajo externo en Java Slides usando Aspose.Slides. Ahora puede crear presentaciones que hagan referencia dinámicamente a datos de libros de Excel, mejorando la flexibilidad y la interactividad de sus diapositivas.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para Java?

Aspose.Slides para Java se puede instalar agregando la biblioteca a su proyecto Java. Puede descargar la biblioteca desde el sitio web de Aspose y seguir las instrucciones de instalación proporcionadas en la documentación.

### ¿Puedo utilizar diferentes tipos de gráficos con libros externos?

Sí, puede utilizar varios tipos de gráficos compatibles con Aspose.Slides y vincularlos a datos de libros externos. El proceso puede variar ligeramente según el tipo de gráfico que elija.

### ¿Qué pasa si cambia la estructura de datos de mi libro externo?

Si la estructura de los datos de su libro externo cambia, es posible que necesite actualizar las referencias de celda en su código Java para asegurarse de que los datos del gráfico sigan siendo precisos.

### ¿Aspose.Slides es compatible con las últimas versiones de Java?

Aspose.Slides para Java se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de Java. Asegúrese de buscar actualizaciones y utilizar la última versión de la biblioteca para obtener un rendimiento y compatibilidad óptimos.

### ¿Puedo agregar varios gráficos que hagan referencia al mismo libro externo?

Sí, puede agregar varios gráficos a su presentación, todos haciendo referencia al mismo libro externo. Simplemente repita los pasos descritos en este tutorial para cada gráfico que desee crear.