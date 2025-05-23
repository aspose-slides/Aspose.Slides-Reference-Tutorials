---
"description": "Cree gráficos normales en presentaciones de Java con Aspose.Slides para Java. Guía paso a paso y código fuente para crear, personalizar y guardar gráficos en presentaciones de PowerPoint."
"linktitle": "Diapositivas sobre gráficos normales en Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Diapositivas sobre gráficos normales en Java"
"url": "/es/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diapositivas sobre gráficos normales en Java


## Diapositivas de introducción a los gráficos normales en Java

En este tutorial, explicaremos el proceso de creación de gráficos normales en Java Slides mediante la API de Aspose.Slides para Java. Utilizaremos instrucciones paso a paso y el código fuente para demostrar cómo crear un gráfico de columnas agrupadas en una presentación de PowerPoint.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Aspose.Slides para API de Java instalada.
2. Un entorno de desarrollo Java configurado.
3. Conocimientos básicos de programación Java.

## Paso 1: Configuración del proyecto

Asegúrate de tener un directorio para tu proyecto. Lo llamaremos "Tu directorio de documentos", como se menciona en el código. Puedes reemplazarlo con la ruta real del directorio de tu proyecto.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Paso 2: Crear una presentación

Ahora, creemos una presentación de PowerPoint y accedamos a su primera diapositiva.

```java
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation();
// Acceder a la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```

## Paso 3: Agregar un gráfico

Agregaremos un gráfico de columnas agrupadas a la diapositiva y estableceremos su título.

```java
// Agregar gráfico con datos predeterminados
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Título del cuadro de configuración
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Paso 4: Configuración de los datos del gráfico

A continuación, configuraremos los datos del gráfico definiendo series y categorías.

```java
// Establecer la primera serie en Mostrar valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Eliminar series y categorías generadas por defecto
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Añadiendo nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Añadiendo nuevas categorías
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Paso 5: Rellenar los datos de la serie

Ahora, vamos a completar los puntos de datos de la serie para el gráfico.

```java
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Población de datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Configuración del color de relleno para la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);

// Población de datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Configuración del color de relleno para la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Paso 6: Personalización de etiquetas

Personalicemos las etiquetas de datos para la serie de gráficos.

```java
// La primera etiqueta mostrará el nombre de la categoría.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Mostrar el valor de la tercera etiqueta con el nombre de la serie y el separador
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Paso 7: Guardar la presentación

Por último, guarde la presentación con el gráfico en el directorio de su proyecto.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has creado correctamente un gráfico de columnas agrupadas en una presentación de PowerPoint con Aspose.Slides para Java. Puedes personalizarlo aún más según tus necesidades.

## Código fuente completo para gráficos normales en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation pres = new Presentation();
// Acceder a la primera diapositiva
ISlide sld = pres.getSlides().get_Item(0);
// Agregar gráfico con datos predeterminados
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Título del cuadro de configuración
// Chart.getChartTitle().getTextFrameForOverriding().setText("Título de muestra");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Establecer la primera serie en Mostrar valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Eliminar series y categorías generadas por defecto
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Añadiendo nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Añadiendo nuevas categorías
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Configuración del color de relleno para la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Configuración del color de relleno para la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// La primera etiqueta mostrará el nombre de la categoría.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Mostrar valor para la tercera etiqueta
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Guardar presentación con gráfico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusión

En este tutorial, aprendimos a crear gráficos normales en Java Slides usando la API de Aspose.Slides para Java. Recorrimos una guía paso a paso con código fuente para crear un gráfico de columnas agrupadas en una presentación de PowerPoint.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

Para cambiar el tipo de gráfico, modifique el `ChartType` parámetro al agregar el gráfico usando `sld.getShapes().addChart()`Puede elegir entre varios tipos de gráficos disponibles en Aspose.Slides.

### ¿Puedo cambiar los colores de la serie de gráficos?

Sí, puede cambiar los colores de las series de gráficos configurando el color de relleno para cada serie usando `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### ¿Cómo puedo agregar más categorías o series al gráfico?

Puede agregar más categorías o series al gráfico agregando nuevos puntos de datos y etiquetas mediante el `chart.getChartData().getCategories().add()` y `chart.getChartData().getSeries().add()` métodos.

### ¿Cómo puedo personalizar aún más el título del gráfico?

Puede personalizar aún más el título del gráfico modificando las propiedades de `chart.getChartTitle()` como la alineación del texto, el tamaño de fuente y el color.

### ¿Cómo guardo el gráfico en un formato de archivo diferente?

Para guardar el gráfico en un formato de archivo diferente, cambie el `SaveFormat` parámetro en el `pres.save()` método al formato deseado (por ejemplo, PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}