---
title: Gráfico disperso en diapositivas de Java
linktitle: Gráfico disperso en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear gráficos de dispersión en Java usando Aspose.Slides. Guía paso a paso con código fuente Java para visualización de datos en presentaciones.
weight: 11
url: /es/java/chart-creation/scattered-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introducción al gráfico disperso en Aspose.Slides para Java

En este tutorial, lo guiaremos a través del proceso de creación de un gráfico de dispersión usando Aspose.Slides para Java. Los gráficos de dispersión son útiles para visualizar puntos de datos en un plano bidimensional. Proporcionaremos instrucciones paso a paso e incluiremos código fuente Java para su comodidad.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1. [Aspose.Slides para Java](https://products.aspose.com/slides/java) instalado.
2. Un entorno de desarrollo Java configurado.

## Paso 1: Inicialice la presentación

Primero, importe las bibliotecas necesarias y cree una nueva presentación.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Cree un directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Crear una nueva presentación
Presentation pres = new Presentation();
```

## Paso 2: agregue una diapositiva y cree el gráfico de dispersión

 A continuación, agregue una diapositiva y cree el gráfico de dispersión en ella. Usaremos el`ScatterWithSmoothLines`tipo de gráfico en este ejemplo.

```java
// Obtenga la primera diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Creando el gráfico de dispersión
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Paso 3: preparar los datos del gráfico

Ahora, preparemos los datos para nuestro gráfico de dispersión. Agregaremos dos series, cada una con múltiples puntos de datos.

```java
// Obtener el índice predeterminado de la hoja de cálculo de datos del gráfico
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Eliminar serie de demostración
chart.getChartData().getSeries().clear();

// Agrega la primera serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Tome la primera serie de gráficos.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Agregar puntos de datos a la primera serie.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Editar el tipo de serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Cambiar tamaño de marcador
series.getMarker().setSymbol(MarkerStyleType.Star); // Cambiar símbolo de marcador

// Tome la segunda serie de gráficos.
series = chart.getChartData().getSeries().get_Item(1);

// Agregar puntos de datos a la segunda serie.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Cambiar el estilo del marcador para la segunda serie.
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Paso 4: guarde la presentación

Finalmente, guarde la presentación con el gráfico de dispersión en un archivo PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Ha creado con éxito un gráfico de dispersión utilizando Aspose.Slides para Java. Ahora puede personalizar aún más este ejemplo para adaptarlo a sus datos específicos y requisitos de diseño.

## Código fuente completo para gráficos dispersos en diapositivas de Java
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Cree un directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Creando el gráfico predeterminado
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Obtener el índice predeterminado de la hoja de cálculo de datos del gráfico
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Eliminar serie de demostración
chart.getChartData().getSeries().clear();
// Agregar nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Agregue un nuevo punto (1:3) allí.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Agregar nuevo punto (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Editar el tipo de serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Cambiar el marcador de serie del gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Agregue un nuevo punto (5:2) allí.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Añadir nuevo punto (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Agregar nuevo punto (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Agregar nuevo punto (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Cambiar el marcador de serie del gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, lo guiamos a través del proceso de creación de un gráfico de dispersión usando Aspose.Slides para Java. Los gráficos de dispersión son herramientas poderosas para visualizar puntos de datos en un espacio bidimensional, lo que facilita el análisis y la comprensión de relaciones de datos complejas.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

 Para cambiar el tipo de gráfico, utilice el`setType` método en la serie de gráficos y proporcione el tipo de gráfico deseado. Por ejemplo,`series.setType(ChartType.Line)` cambiaría la serie a un gráfico de líneas.

### ¿Cómo personalizo el tamaño y el estilo del marcador?

 Puede cambiar el tamaño y el estilo del marcador usando el`getMarker` método en la serie y luego establezca las propiedades de tamaño y símbolo. Por ejemplo:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

No dude en explorar más opciones de personalización en la documentación de Aspose.Slides para Java.

 Recuerde reemplazar`"Your Document Directory"` con la ruta real donde desea guardar la presentación.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
