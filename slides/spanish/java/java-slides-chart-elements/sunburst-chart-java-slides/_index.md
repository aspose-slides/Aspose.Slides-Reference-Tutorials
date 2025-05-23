---
"description": "Crea impresionantes gráficos de rayos de sol en Java Slides con Aspose.Slides. Aprende paso a paso a crear gráficos y manipular datos."
"linktitle": "Gráfico de rayos de sol en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Gráfico de rayos de sol en diapositivas de Java"
"url": "/es/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gráfico de rayos de sol en diapositivas de Java


## Introducción al gráfico Sunburst en Java (diapositivas con Aspose.Slides)

En este tutorial, aprenderá a crear un gráfico de rayos de sol en una presentación de PowerPoint con la API de Aspose.Slides para Java. Un gráfico de rayos de sol es un gráfico radial que se utiliza para representar datos jerárquicos. Le proporcionaremos instrucciones paso a paso junto con el código fuente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Importar las bibliotecas necesarias

Primero, importe las bibliotecas necesarias para trabajar con Aspose.Slides y cree un gráfico Sunburst en su aplicación Java.

```java
import com.aspose.slides.*;
```

## Paso 2: Inicializar la presentación

Inicialice una presentación de PowerPoint y especifique el directorio donde se guardará el archivo de presentación.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Paso 3: Crear el gráfico de rayos de sol

Creamos un gráfico de rayos de sol en una diapositiva. Especificamos la posición (X, Y) y las dimensiones (ancho, alto) del gráfico.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Paso 4: Preparar los datos del gráfico

Borre todas las categorías y datos de series existentes del gráfico y cree un libro de trabajo de datos para el gráfico.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Paso 5: Definir la jerarquía del gráfico

Define la estructura jerárquica del gráfico Sunburst. Puedes añadir ramas, tallos y hojas como categorías.

```java
// Sucursal 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Sucursal 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Paso 6: Agregar datos al gráfico

Agregue puntos de datos a la serie de gráficos Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Paso 7: Guardar la presentación

Por último, guarde la presentación con el gráfico Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Código fuente completo para el gráfico Sunburst en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//rama 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//rama 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendiste a crear un gráfico Sunburst en una presentación de PowerPoint usando la API de Aspose.Slides para Java. Viste cómo inicializar la presentación, crear el gráfico, definir su jerarquía, agregar puntos de datos y guardar la presentación. Ahora puedes usar estos conocimientos para crear gráficos Sunburst interactivos e informativos en tus aplicaciones Java.

## Preguntas frecuentes

### ¿Cómo personalizo la apariencia del gráfico Sunburst?

Puede personalizar la apariencia del gráfico Sunburst modificando propiedades como colores, etiquetas y estilos. Consulte la documentación de Aspose.Slides para obtener información detallada sobre las opciones de personalización.

### ¿Puedo agregar más puntos de datos al gráfico?

Sí, puede agregar más puntos de datos al gráfico utilizando el `series.getDataPoints().addDataPointForSunburstSeries()` método para cada punto de datos que desee incluir.

### ¿Cómo puedo agregar información sobre herramientas al gráfico Sunburst?

Para agregar información sobre herramientas al gráfico Sunburst, puede configurar el formato de la etiqueta de datos para mostrar información adicional, como valores o descripciones, al pasar el cursor sobre los segmentos del gráfico.

### ¿Es posible crear gráficos Sunburst interactivos con hipervínculos?

Sí, puede crear gráficos Sunburst interactivos con hipervínculos añadiéndolos a elementos o segmentos específicos del gráfico. Consulte la documentación de Aspose.Slides para obtener más información sobre cómo añadir hipervínculos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}