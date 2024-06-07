---
title: Gráfico circular en diapositivas de Java
linktitle: Gráfico circular en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a crear impresionantes gráficos circulares en presentaciones de PowerPoint utilizando Aspose.Slides para Java. Guía paso a paso con código fuente para desarrolladores de Java.
type: docs
weight: 23
url: /es/java/chart-data-manipulation/pie-chart-java-slides/
---

## Introducción a la creación de un gráfico circular en diapositivas de Java utilizando Aspose.Slides

En este tutorial, demostraremos cómo crear un gráfico circular en una presentación de PowerPoint usando Aspose.Slides para Java. Le proporcionaremos instrucciones paso a paso y el código fuente de Java para ayudarle a comenzar. Esta guía asume que ya ha configurado su entorno de desarrollo con Aspose.Slides para Java.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/java/).

## Paso 1: importar las bibliotecas necesarias

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Asegúrese de importar las clases necesarias de la biblioteca Aspose.Slides.

## Paso 2: Inicialice la presentación

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation presentation = new Presentation();
```

 Cree un nuevo objeto de presentación para representar su archivo de PowerPoint. Reemplazar`"Your Document Directory"` con la ruta real donde desea guardar la presentación.

## Paso 3: agregar una diapositiva

```java
// Accede a la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

Obtenga la primera diapositiva de la presentación donde desea agregar el gráfico circular.

## Paso 4: agregue un gráfico circular

```java
//Agregar un gráfico circular con datos predeterminados
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Agregue un gráfico circular a la diapositiva en la posición y el tamaño especificados.

## Paso 5: establecer el título del gráfico

```java
// Establecer título del gráfico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Establezca un título para el gráfico circular. Puede personalizar el título según sea necesario.

## Paso 6: personalizar los datos del gráfico

```java
// Establecer la primera serie para mostrar valores.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;

// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Eliminar series y categorías generadas por defecto
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Agregar nuevas categorías
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Añadiendo nueva serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Poblar datos de series
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personalice los datos del gráfico agregando categorías y series, y estableciendo sus valores. En este ejemplo, tenemos tres categorías y una serie con los puntos de datos correspondientes.

## Paso 7: personalizar los sectores del gráfico circular

```java
// Establecer colores de sector
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personaliza la apariencia de cada sector.
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Personalizar el borde del sector
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Personaliza otros sectores de forma similar
```

Personaliza la apariencia de cada sector en el gráfico circular. Puede cambiar los colores, estilos de borde y otras propiedades visuales.

## Paso 8: Personaliza las etiquetas de datos

```java
// Personalizar etiquetas de datos
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personalice las etiquetas de datos para otros puntos de datos de manera similar
```

Personalice las etiquetas de datos para cada punto de datos en el gráfico circular. Puede controlar qué valores se muestran en el gráfico.

## Paso 9: mostrar líneas guía

```java
// Mostrar líneas guía para el gráfico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Habilite líneas guía para conectar etiquetas de datos a sus sectores correspondientes.

## Paso 10: Establecer el ángulo de rotación del gráfico circular

```java
// Establecer el ángulo de rotación para los sectores del gráfico circular
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Establezca el ángulo de rotación para los sectores del gráfico circular. En este ejemplo, lo configuramos en 180 grados.

## Paso 11: guarde la presentación

```java
// Guarde la presentación con el gráfico circular
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Guarde la presentación con el gráfico circular en el directorio especificado.

## Código fuente completo para gráfico circular en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase de presentación que representa el archivo PPTX
Presentation presentation = new Presentation();
// Acceder a la primera diapositiva
ISlide slides = presentation.getSlides().get_Item(0);
// Agregar gráfico con datos predeterminados
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Título del cuadro de configuración
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Establecer la primera serie para Mostrar valores
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Eliminar series y categorías generadas por defecto
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Agregar nuevas categorías
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Añadiendo nueva serie
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
//Ahora completando datos de series
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// No funciona en la nueva versión
// Agregar nuevos puntos y configurar el color del sector
// series.IsColorVaried = verdadero;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Configuración del borde del sector
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Configuración del borde del sector
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Configuración del borde del sector
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Cree etiquetas personalizadas para cada una de las categorías de nuevas series.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(verdadero);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Mostrar líneas guía para el gráfico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Configuración del ángulo de rotación para sectores de gráficos circulares
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Guardar presentación con gráfico
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusión

Ha creado con éxito un gráfico circular en una presentación de PowerPoint utilizando Aspose.Slides para Java. Puede personalizar la apariencia del gráfico y las etiquetas de datos según sus requisitos específicos. Este tutorial proporciona un ejemplo básico y puede mejorar y personalizar aún más sus gráficos según sea necesario.

## Preguntas frecuentes

### ¿Cómo puedo cambiar los colores de sectores individuales en el gráfico circular?

 Para cambiar los colores de sectores individuales en el gráfico circular, puede personalizar el color de relleno de cada punto de datos. En el ejemplo de código proporcionado, demostramos cómo establecer el color de relleno para cada sector usando el`getSolidFillColor().setColor()` método. Puede modificar los valores de color para lograr la apariencia deseada.

### ¿Puedo agregar más categorías y series de datos al gráfico circular?

 Sí, puede agregar categorías y series de datos adicionales al gráfico circular. Para hacer esto, puedes usar el`getChartData().getCategories().add()` y`getChartData().getSeries().add()` métodos, como se muestra en el ejemplo. Simplemente proporcione los datos y etiquetas apropiados para las nuevas categorías y series para expandir su gráfico.

### ¿Cómo personalizo la apariencia de las etiquetas de datos?

 Puede personalizar la apariencia de las etiquetas de datos usando el`getDataLabelFormat()` método en la etiqueta de cada punto de datos. En el ejemplo, demostramos cómo mostrar el valor en las etiquetas de datos usando`getDataLabelFormat().setShowValue(true)`. Puede personalizar aún más las etiquetas de datos controlando qué valores se muestran, mostrando claves de leyenda y ajustando otras opciones de formato.

### ¿Puedo cambiar el título del gráfico circular?

 Sí, puedes cambiar el título del gráfico circular. En el código proporcionado, configuramos el título del gráfico usando`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . puedes reemplazar`"Sample Title"` con el texto del título que desee.

### ¿Cómo guardo la presentación generada con el gráfico circular?

 Para guardar la presentación con el gráfico circular, utilice el`presentation.save()` método. Proporcione la ruta y el nombre del archivo deseado junto con el formato en el que desea guardar la presentación. Por ejemplo:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Asegúrese de especificar la ruta y el formato del archivo correctos.

### ¿Puedo crear otros tipos de gráficos usando Aspose.Slides para Java?

Sí, Aspose.Slides para Java admite varios tipos de gráficos, incluidos gráficos de barras, gráficos de líneas y más. Puede crear diferentes tipos de gráficos cambiando el`ChartType` al agregar un gráfico. Consulte la documentación de Aspose.Slides para obtener más detalles sobre la creación de diferentes tipos de gráficos.

### ¿Cómo puedo encontrar más información y ejemplos para trabajar con Aspose.Slides para Java?

 Para obtener más información, documentación detallada y ejemplos adicionales, puede visitar el[Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/). Proporciona recursos completos para ayudarle a utilizar la biblioteca de forma eficaz.