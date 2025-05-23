---
"description": "Aprenda a crear y personalizar gráficos de Java Slides con Aspose.Slides. Mejore sus presentaciones con potentes entidades gráficas."
"linktitle": "Entidades de gráficos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Entidades de gráficos en diapositivas de Java"
"url": "/es/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Entidades de gráficos en diapositivas de Java


## Diapositivas de introducción a las entidades gráficas en Java

Los gráficos son herramientas potentes para visualizar datos en presentaciones. Ya sea que esté creando informes empresariales, presentaciones académicas o cualquier otro tipo de contenido, los gráficos ayudan a transmitir la información eficazmente. Aspose.Slides para Java ofrece funciones robustas para trabajar con gráficos, lo que lo convierte en una opción predilecta para los desarrolladores de Java.

## Prerrequisitos

Antes de sumergirnos en el mundo de las entidades gráficas, asegúrese de tener los siguientes requisitos previos:

- Kit de desarrollo de Java (JDK) instalado
- Biblioteca Aspose.Slides para Java descargada y agregada a su proyecto
- Conocimientos básicos de programación Java

Ahora, comencemos a crear y personalizar gráficos utilizando Aspose.Slides para Java.

## Paso 1: Crear una presentación

El primer paso es crear una nueva presentación donde agregarás el gráfico. Aquí tienes un fragmento de código para crear una presentación:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: Agregar un gráfico

Una vez que tengas lista tu presentación, es hora de agregar un gráfico. En este ejemplo, agregaremos un gráfico de líneas simple con marcadores. Así es como puedes hacerlo:

```java
// Accediendo a la primera diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Añadiendo el gráfico de muestra
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Paso 3: Personalizar el título del gráfico

Un gráfico bien definido debe tener un título. Vamos a definir un título para nuestro gráfico:

```java
// Título del cuadro de configuración
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Paso 4: Dar formato a las líneas de la cuadrícula

Puedes formatear las líneas de cuadrícula principales y secundarias de tu gráfico. Configuremos el formato de las líneas de cuadrícula del eje vertical:

```java
// Configuración del formato de las líneas de cuadrícula principales para el eje de valores
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Configuración del formato de líneas de cuadrícula menores para el eje de valores
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Paso 5: Personalización del eje de valores

Tienes control sobre el formato numérico y los valores máximo y mínimo del eje de valores. Aquí te explicamos cómo personalizarlo:

```java
// Formato del número del eje de valores de configuración
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Configuración de los valores máximos y mínimos del gráfico
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Paso 6: Agregar título al eje de valores

Para que su gráfico sea más informativo, puede agregar un título al eje de valores:

```java
// Título del eje de valores de configuración
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Paso 7: Formato del eje de categorías

El eje de categorías, que normalmente representa categorías de datos, también se puede personalizar:

```java
// Configuración del formato de las líneas de cuadrícula principales para el eje de categorías
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Configuración del formato de líneas de cuadrícula menores para el eje de categorías
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Paso 8: Agregar leyendas

Las leyendas ayudan a explicar las series de datos de tu gráfico. Personalicemos las leyendas:

```java
// Configuración de las propiedades del texto de las leyendas
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Establecer mostrar leyendas de gráficos sin superponer gráficos
chart.getLegend().setOverlay(true);
```

## Paso 9: Guardar la presentación

Por último, guarda tu presentación con el gráfico:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Código fuente completo para entidades gráficas en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear directorio si aún no está presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanciando una presentación// Instanciando una presentación
Presentation pres = new Presentation();
try
{
	// Accediendo a la primera diapositiva
	ISlide slide = pres.getSlides().get_Item(0);
	// Añadiendo el gráfico de muestra
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Título del cuadro de configuración
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Configuración del formato de las líneas de cuadrícula principales para el eje de valores
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Configuración del formato de líneas de cuadrícula menores para el eje de valores
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Formato del número del eje de valores de configuración
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Configuración de los valores máximos y mínimos del gráfico
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Configuración de las propiedades del texto del eje de valores
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Título del eje de valores de configuración
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Formato de línea del eje de valores de configuración: ahora obsoleto
	// gráfico.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Configuración del formato de las líneas de cuadrícula principales para el eje de categorías
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Configuración del formato de líneas de cuadrícula menores para el eje de categorías
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Configuración de las propiedades del texto del eje de categorías
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Título de la categoría de configuración
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Configuración de la posición de la etiqueta del eje de categoría
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Configuración del ángulo de rotación de la etiqueta del eje de categoría
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Configuración de las propiedades del texto de las leyendas
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Establecer mostrar leyendas de gráficos sin superponer gráficos
	chart.getLegend().setOverlay(true);
	// Trazado de la primera serie en el eje de valores secundarios
	// Gráfico.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = verdadero;
	// Configuración del color de la pared posterior del gráfico
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Configuración del color del área de la gráfica
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Guardar presentación
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este artículo, exploramos el mundo de las entidades gráficas en Java Slides con Aspose.Slides para Java. Aprendió a crear, personalizar y manipular gráficos para mejorar sus presentaciones. Los gráficos no solo hacen que sus datos sean visualmente atractivos, sino que también ayudan a su audiencia a comprender información compleja con mayor facilidad.

## Preguntas frecuentes

### ¿Cómo cambio el tipo de gráfico?

Para cambiar el tipo de gráfico, utilice el `chart.setType()` método y especifique el tipo de gráfico deseado.

### ¿Puedo agregar múltiples series de datos a un gráfico?

Sí, puede agregar varias series de datos a un gráfico utilizando el `chart.getChartData().getSeries().addSeries()` método.

### ¿Cómo personalizo los colores del gráfico?

Puede personalizar los colores del gráfico configurando el formato de relleno para distintos elementos del gráfico, como líneas de cuadrícula, título y leyendas.

### ¿Puedo crear gráficos en 3D?

Sí, Aspose.Slides para Java permite crear gráficos 3D. Puedes configurar... `ChartType` a un tipo de gráfico 3D para crear uno.

### ¿Aspose.Slides para Java es compatible con las últimas versiones de Java?

Sí, Aspose.Slides para Java se actualiza periódicamente para admitir las últimas versiones de Java y proporciona compatibilidad en una amplia gama de entornos Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}