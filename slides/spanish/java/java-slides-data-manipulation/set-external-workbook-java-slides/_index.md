---
"description": "Aprenda a configurar libros externos en Java Slides con Aspose.Slides para Java. Cree presentaciones dinámicas con integración de datos de Excel."
"linktitle": "Establecer un libro de trabajo externo en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Establecer un libro de trabajo externo en diapositivas de Java"
"url": "/es/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Establecer un libro de trabajo externo en diapositivas de Java


## Diapositivas de introducción a la configuración de libros de trabajo externos en Java

En este tutorial, exploraremos cómo configurar un libro externo en Java Slides con Aspose.Slides. Aprenderá a crear una presentación de PowerPoint con un gráfico que referencia datos de un libro externo de Excel. Al finalizar esta guía, comprenderá claramente cómo integrar datos externos en sus presentaciones de Java Slides.

## Prerrequisitos

Antes de sumergirnos en la implementación, asegúrese de tener los siguientes requisitos previos:

- Java Development Kit (JDK) instalado en su sistema.
- Se agregó la biblioteca Aspose.Slides para Java a su proyecto.
- Un libro de Excel con los datos que desea referenciar en su presentación.

## Paso 1: Crear una nueva presentación

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Comenzamos creando una nueva presentación de PowerPoint utilizando Aspose.Slides.

## Paso 2: Agregar un gráfico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

A continuación, insertamos un gráfico circular en la presentación. Puedes personalizar el tipo y la posición del gráfico según tus necesidades.

## Paso 3: Acceder al libro de trabajo externo

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Para acceder al libro de trabajo externo, utilizamos el `setExternalWorkbook` método y proporcionar la ruta al libro de Excel que contiene los datos.

## Paso 4: Vincular datos del gráfico

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Vinculamos el gráfico a los datos del libro externo especificando las referencias de celda para las series y categorías.

## Paso 5: Guardar la presentación

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con la referencia del libro externo como un archivo de PowerPoint.

## Código fuente completo para configurar un libro de trabajo externo en Java (diapositivas)

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

En este tutorial, aprendimos a configurar un libro externo en Java Slides con Aspose.Slides. Ahora puede crear presentaciones que hagan referencia dinámica a datos de libros de Excel, lo que mejora la flexibilidad y la interactividad de sus diapositivas.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para Java?

Aspose.Slides para Java se puede instalar añadiendo la biblioteca a su proyecto Java. Puede descargarla del sitio web de Aspose y seguir las instrucciones de instalación que se proporcionan en la documentación.

### ¿Puedo utilizar diferentes tipos de gráficos con libros de trabajo externos?

Sí, puede usar varios tipos de gráficos compatibles con Aspose.Slides y vincularlos a datos de libros de trabajo externos. El proceso puede variar ligeramente según el tipo de gráfico que elija.

### ¿Qué pasa si cambia la estructura de datos de mi libro de trabajo externo?

Si cambia la estructura de los datos de su libro de trabajo externo, es posible que necesite actualizar las referencias de celda en su código Java para garantizar que los datos del gráfico sigan siendo precisos.

### ¿Aspose.Slides es compatible con las últimas versiones de Java?

Aspose.Slides para Java se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de Java. Asegúrese de buscar actualizaciones y usar la última versión de la biblioteca para un rendimiento y una compatibilidad óptimos.

### ¿Puedo agregar varios gráficos que hagan referencia al mismo libro de trabajo externo?

Sí, puedes agregar varios gráficos a tu presentación, todos haciendo referencia al mismo libro de trabajo externo. Simplemente repite los pasos de este tutorial para cada gráfico que quieras crear.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}