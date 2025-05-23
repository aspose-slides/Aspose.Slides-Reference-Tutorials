---
"description": "Aprenda a crear gráficos de dispersión en Java con Aspose.Slides. Guía paso a paso con código fuente Java para la visualización de datos en presentaciones."
"linktitle": "Gráfico disperso en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Gráfico disperso en diapositivas de Java"
"url": "/es/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico disperso en diapositivas de Java


## Introducción a los gráficos dispersos en Aspose.Slides para Java

En este tutorial, le guiaremos en el proceso de creación de un gráfico de dispersión con Aspose.Slides para Java. Los gráficos de dispersión son útiles para visualizar puntos de datos en un plano bidimensional. Le proporcionaremos instrucciones paso a paso e incluiremos el código fuente de Java para su comodidad.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. [Aspose.Slides para Java](https://products.aspose.com/slides/java) instalado.
2. Un entorno de desarrollo Java configurado.

## Paso 1: Inicializar la presentación

Primero, importe las bibliotecas necesarias y cree una nueva presentación.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Crear directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Crear una nueva presentación
Presentation pres = new Presentation();
```

## Paso 2: Agregar una diapositiva y crear el gráfico de dispersión

A continuación, agregue una diapositiva y cree el gráfico de dispersión en ella. Usaremos el `ScatterWithSmoothLines` tipo de gráfico en este ejemplo.

```java
// Obtener la primera diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Creando el gráfico de dispersión
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Paso 3: Preparar los datos del gráfico

Ahora, preparemos los datos para nuestro gráfico de dispersión. Agregaremos dos series, cada una con múltiples puntos de datos.

```java
// Obtener el índice de la hoja de cálculo con datos del gráfico predeterminado
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Eliminar la serie de demostración
chart.getChartData().getSeries().clear();

// Añade la primera serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Agregar puntos de datos a la primera serie
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Editar el tipo de serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Cambiar el tamaño del marcador
series.getMarker().setSymbol(MarkerStyleType.Star); // Cambiar el símbolo del marcador

// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Agregar puntos de datos a la segunda serie
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Cambiar el estilo del marcador para la segunda serie
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Paso 4: Guardar la presentación

Por último, guarde la presentación con el gráfico de dispersión en un archivo PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has creado correctamente un gráfico de dispersión con Aspose.Slides para Java. Ahora puedes personalizar este ejemplo para adaptarlo a tus datos y requisitos de diseño.

## Código fuente completo para gráficos dispersos en Java (diapositivas)
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Creando el gráfico predeterminado
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Obtener el índice de la hoja de cálculo con datos del gráfico predeterminado
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Eliminar la serie de demostración
chart.getChartData().getSeries().clear();
// Añadir nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Añade allí un nuevo punto (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Añadir nuevo punto (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Editar el tipo de serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Cambiar el marcador de la serie del gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Añade allí el nuevo punto (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Añadir nuevo punto (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Añadir nuevo punto (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Añadir nuevo punto (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Cambiar el marcador de la serie del gráfico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, le explicamos el proceso de creación de un gráfico de dispersión con Aspose.Slides para Java. Los gráficos de dispersión son herramientas eficaces para visualizar puntos de datos en un espacio bidimensional, lo que facilita el análisis y la comprensión de relaciones complejas entre datos.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

Para cambiar el tipo de gráfico, utilice el `setType` Método en la serie de gráficos y proporcione el tipo de gráfico deseado. Por ejemplo, `series.setType(ChartType.Line)` Cambiaría la serie a un gráfico de líneas.

### ¿Cómo personalizo el tamaño y el estilo del marcador?

Puede cambiar el tamaño y el estilo del marcador utilizando el `getMarker` Método en la serie y luego configure el tamaño y las propiedades del símbolo. Por ejemplo:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Siéntase libre de explorar más opciones de personalización en la documentación de Aspose.Slides para Java.

Recuerde reemplazar `"Your Document Directory"` con la ruta real donde desea guardar la presentación.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}