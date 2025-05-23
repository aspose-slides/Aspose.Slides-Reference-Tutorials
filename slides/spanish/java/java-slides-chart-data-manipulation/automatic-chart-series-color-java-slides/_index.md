---
"description": "Aprenda a crear gráficos dinámicos con color de serie automático en presentaciones de PowerPoint con Aspose.Slides para Java. Mejore sus visualizaciones de datos fácilmente."
"linktitle": "Color automático de series de gráficos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Color automático de series de gráficos en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Color automático de series de gráficos en diapositivas de Java


## Introducción al color automático de series de gráficos en Aspose.Slides para Java

En este tutorial, exploraremos cómo crear una presentación de PowerPoint con un gráfico usando Aspose.Slides para Java y configurar colores de relleno automáticos para series de gráficos. Los colores de relleno automáticos pueden hacer que sus gráficos sean más atractivos visualmente y ahorrarle tiempo, ya que la biblioteca puede elegir los colores automáticamente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener instalada la biblioteca Aspose.Slides para Java en su proyecto. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Crear una nueva presentación

Primero, crearemos una nueva presentación de PowerPoint y le agregaremos una diapositiva.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

## Paso 2: Agregar un gráfico a la diapositiva

A continuación, agregaremos un gráfico de columnas agrupadas a la diapositiva. También configuraremos la primera serie para que muestre valores.

```java
// Acceder a la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Agregar gráfico con datos predeterminados
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Establecer la primera serie en Mostrar valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Paso 3: Completar los datos del gráfico

Ahora, completaremos el gráfico con datos. Comenzaremos eliminando las series y categorías predeterminadas y luego agregaremos nuevas series y categorías.

```java
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

## Paso 4: Rellenar los datos de la serie

Completaremos los datos de la serie tanto para la Serie 1 como para la Serie 2.

```java
// Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Tome la segunda serie de gráficos
series = chart.getChartData().getSeries().get_Item(1);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Paso 5: Establecer el color de relleno automático para la serie

Ahora, configuremos colores de relleno automáticos para la serie de gráficos. Esto hará que la biblioteca elija los colores automáticamente.

```java
// Configuración del color de relleno automático para las series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Paso 6: Guardar la presentación

Por último, guardaremos la presentación con el gráfico en un archivo de PowerPoint.

```java
// Guardar presentación con gráfico
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Código fuente completo para la coloración automática de series de gráficos en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
try
{
	// Acceder a la primera diapositiva
	ISlide slide = presentation.getSlides().get_Item(0);
	// Agregar gráfico con datos predeterminados
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Configuración del color de relleno automático para las series
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Tome la segunda serie de gráficos
	series = chart.getChartData().getSeries().get_Item(1);
	// Ahora se están rellenando los datos de la serie
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Configuración del color de relleno para la serie
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Guardar presentación con gráfico
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

En este tutorial, aprendimos a crear una presentación de PowerPoint con un gráfico usando Aspose.Slides para Java y a configurar colores de relleno automáticos para las series de gráficos. Los colores automáticos pueden mejorar el atractivo visual de sus gráficos y hacer que sus presentaciones sean más atractivas. Puede personalizar aún más el gráfico según sus necesidades específicas.

## Preguntas frecuentes

### ¿Cómo configuro colores de relleno automáticos para series de gráficos en Aspose.Slides para Java?

Para establecer colores de relleno automáticos para series de gráficos en Aspose.Slides para Java, utilice el siguiente código:

```java
// Configuración del color de relleno automático para las series
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Este código permitirá que la biblioteca elija colores automáticamente para la serie de gráficos.

### ¿Puedo personalizar los colores del gráfico si es necesario?

Sí, puede personalizar los colores del gráfico según sea necesario. En el ejemplo proporcionado, usamos colores de relleno automáticos, pero puede configurar colores específicos modificando el... `FillType` y `SolidFillColor` Propiedades del formato de la serie.

### ¿Cómo puedo agregar series o categorías adicionales al gráfico?

Para agregar series o categorías adicionales al gráfico, utilice el `getSeries()` y `getCategories()` métodos del gráfico `ChartData` objeto. Puede agregar nuevas series y categorías especificando sus datos y etiquetas.

### ¿Es posible dar mejor formato al gráfico y a las etiquetas?

Sí, puede formatear el gráfico, las series y las etiquetas según sea necesario. Aspose.Slides para Java ofrece amplias opciones de formato para gráficos, incluyendo fuentes, colores, estilos y más. Puede consultar la documentación para obtener más información sobre las opciones de formato.

### ¿Dónde puedo encontrar más información sobre cómo trabajar con Aspose.Slides para Java?

Para obtener más información y documentación detallada sobre Aspose.Slides para Java, puede visitar la documentación de referencia. [aquí](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}