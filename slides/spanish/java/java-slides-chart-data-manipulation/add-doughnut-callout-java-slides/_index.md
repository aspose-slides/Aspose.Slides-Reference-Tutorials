---
"description": "Aprenda a añadir llamadas de dona en presentaciones de Java con Aspose.Slides para Java. Guía paso a paso con código fuente para mejorar sus presentaciones."
"linktitle": "Agregar llamada de dona en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Agregar llamada de dona en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Agregar llamada de dona en diapositivas de Java


## Introducción a la adición de una llamada de dona en diapositivas de Java con Aspose.Slides para Java

En este tutorial, le guiaremos a través del proceso de agregar un Llamado de Anillo a una diapositiva en Java usando Aspose.Slides para Java. Un Llamado de Anillo es un elemento gráfico que permite resaltar puntos de datos específicos en un gráfico de anillos. Le proporcionaremos instrucciones paso a paso y el código fuente completo para su comodidad.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1. Entorno de desarrollo de Java
2. Biblioteca Aspose.Slides para Java
3. Entorno de desarrollo integrado (IDE) como Eclipse o IntelliJ IDEA
4. Una presentación de PowerPoint en la que desea agregar el llamado Donut

## Paso 1: Configura tu proyecto Java

1. Crea un nuevo proyecto Java en el IDE elegido.
2. Agregue la biblioteca Aspose.Slides para Java a su proyecto como una dependencia.

## Paso 2: Inicializar la presentación

Para empezar, deberá inicializar una presentación de PowerPoint y crear una diapositiva donde desee agregar el texto destacado de dona. Aquí está el código para lograrlo:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Asegúrese de reemplazar `"Your Document Directory"` con la ruta real a su archivo de presentación de PowerPoint.

## Paso 3: Crea un gráfico de anillos

A continuación, creará un gráfico de anillos en la diapositiva. Puede personalizar la posición y el tamaño del gráfico según sus necesidades. Aquí está el código para agregar un gráfico de anillos:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Paso 4: Personaliza el gráfico de anillos

Ahora es momento de personalizar el gráfico de anillos. Configuraremos varias propiedades, como eliminar la leyenda, configurar el tamaño del agujero y ajustar el ángulo del primer corte. Aquí está el código:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Este fragmento de código define las propiedades del gráfico de anillos. Puede ajustar los valores según sus necesidades.

## Paso 5: Agregar datos al gráfico de anillos

Ahora, agreguemos datos al gráfico de anillos. También personalizaremos la apariencia de los puntos de datos. Aquí está el código para lograrlo:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Personalice la apariencia del punto de datos aquí
        i++;
    }
    categoryIndex++;
}
```

En este código, agregamos categorías y puntos de datos al gráfico de anillos. Puede personalizar aún más la apariencia de los puntos de datos según sea necesario.

## Paso 6: Guardar la presentación

Por último, no olvides guardar la presentación después de añadir el texto de dona. Aquí tienes el código para guardarla:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Asegúrese de reemplazar `"chart.pptx"` con el nombre de archivo deseado.

¡Felicitaciones! Ha agregado correctamente un gráfico de anillo a una diapositiva de Java con Aspose.Slides para Java. Ahora puede ejecutar su aplicación Java para generar la presentación de PowerPoint con el gráfico de anillo y el gráfico de anillo.

## Código fuente completo para añadir una llamada de donut en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(verdadero);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, hemos explicado cómo añadir un gráfico de anillo a una diapositiva de Java con Aspose.Slides para Java. Ha aprendido a crear un gráfico de anillo, personalizar su apariencia y añadir puntos de datos. Siéntase libre de mejorar sus presentaciones con esta potente biblioteca y explorar más opciones de gráficos.

## Preguntas frecuentes

### ¿Cómo puedo cambiar la apariencia del cuadro de diálogo Donut?

Puede personalizar la apariencia de la llamada de anillo modificando las propiedades de los puntos de datos en el gráfico. En el código proporcionado, puede ver cómo configurar el color de relleno, el color de línea, el estilo de fuente y otros atributos de los puntos de datos.

### ¿Puedo agregar más puntos de datos al gráfico de anillos?

Sí, puede agregar tantos puntos de datos como necesite al gráfico de anillos. Simplemente extienda los bucles en el código donde se agregan las categorías y los puntos de datos, y proporcione los datos y el formato adecuados.

### ¿Cómo puedo ajustar la posición y el tamaño del gráfico de anillos en la diapositiva?

Puede cambiar la posición y el tamaño del gráfico de anillos modificando los parámetros en el `addChart` método. Los cuatro números de ese método corresponden a las coordenadas X e Y de la esquina superior izquierda del gráfico y a su ancho y alto, respectivamente.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}