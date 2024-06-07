---
title: Personalización avanzada de gráficos en Aspose.Slides
linktitle: Personalización avanzada de gráficos en Aspose.Slides
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda la personalización avanzada de gráficos en Aspose.Slides para .NET. Cree gráficos visualmente atractivos con orientación paso a paso.
type: docs
weight: 10
url: /es/net/advanced-chart-customization/advanced-chart-customization/
---

La creación de gráficos visualmente atractivos e informativos es una parte esencial de la presentación de datos en muchas aplicaciones. Aspose.Slides para .NET proporciona herramientas sólidas para la personalización de gráficos, lo que le permite ajustar cada aspecto de sus gráficos. En este tutorial, exploraremos técnicas avanzadas de personalización de gráficos utilizando Aspose.Slides para .NET.

## Requisitos previos

Antes de sumergirse en la personalización avanzada de gráficos con Aspose.Slides para .NET, asegúrese de cumplir con los siguientes requisitos previos:

1. Aspose.Slides para la biblioteca .NET: debe tener la biblioteca Aspose.Slides instalada y configurada correctamente en su proyecto .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

2. Un entorno de desarrollo .NET: debe tener configurado un entorno de desarrollo .NET, incluido Visual Studio o cualquier otro IDE de su elección.

3. Conocimientos básicos de C#: será útil estar familiarizado con el lenguaje de programación C#, ya que escribiremos código C# para trabajar con Aspose.Slides.

Ahora, dividamos la personalización avanzada de gráficos en varios pasos para guiarlo a través del proceso.

## Paso 1: crea una presentación

Primero, cree una nueva presentación usando Aspose.Slides.

```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";

// Cree un directorio si aún no está presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Presentación de instancias
Presentation pres = new Presentation();
```

En este paso, iniciamos una nueva presentación que contendrá nuestro gráfico.

## Paso 2: acceda a la primera diapositiva

A continuación, acceda a la primera diapositiva de la presentación donde desea agregar el gráfico.

```csharp
// Accediendo a la primera diapositiva
ISlide slide = pres.Slides[0];
```

Este fragmento de código le permite trabajar con la primera diapositiva de la presentación.

## Paso 3: agregar un gráfico de muestra

Ahora, agreguemos un gráfico de muestra a la diapositiva. En este ejemplo, crearemos un gráfico de líneas con marcadores.

```csharp
// Agregar el gráfico de muestra
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Aquí especificamos el tipo de gráfico (LineWithMarkers) y su posición y dimensiones en la diapositiva.

## Paso 4: configurar el título del gráfico

Establezcamos un título para el gráfico para proporcionar contexto.

```csharp
// Configuración del título del gráfico
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

Este código establece un título para el gráfico, especificando su texto, apariencia y estilo de fuente.

## Paso 5: personalice las líneas de cuadrícula principales

Ahora, personalicemos las líneas principales de la cuadrícula para el eje de valores.

```csharp
// Configuración del formato de líneas de cuadrícula principales para el eje de valores
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Este paso configura la apariencia de las principales líneas de la cuadrícula en el eje de valores.

## Paso 6: personaliza las líneas de cuadrícula menores

De manera similar, podemos personalizar las líneas de la cuadrícula menor para el eje de valores.

```csharp
// Configuración del formato de líneas de cuadrícula menores para el eje de valores
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Este código ajusta la apariencia de las líneas de cuadrícula menores en el eje de valores.

## Paso 7: Definir el formato del número del eje del valor

Personalice el formato numérico para el eje de valores.

```csharp
// Configuración del formato del número del eje del valor
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Este paso le permite formatear los números que se muestran en el eje de valores.

## Paso 8: Establecer los valores máximos y mínimos del gráfico

Defina los valores máximo y mínimo para el gráfico.

```csharp
// Tabla de configuración de valores máximos y mínimos
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Aquí, usted especifica el rango de valores que debe mostrar el eje del gráfico.

## Paso 9: personalizar las propiedades del texto del eje de valores

También puede personalizar las propiedades de texto del eje de valores.

```csharp
// Configuración de las propiedades del texto del eje de valor
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Este código le permite ajustar el estilo de fuente y la apariencia de las etiquetas del eje de valores.

## Paso 10: Título del eje de valor agregado

Si su gráfico requiere un título para el eje de valores, puede agregarlo con este paso.

```csharp
// Título del eje de valor de configuración
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

En este paso, puede establecer un título para el eje de valores.

## Paso 11: Personalice las líneas de cuadrícula principales para el eje de categorías

Ahora, centrémonos en las principales líneas de la cuadrícula del eje de categorías.

```csharp
// Configuración del formato de líneas de cuadrícula principales para el eje de categorías
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Este código configura la apariencia de las principales líneas de la cuadrícula en el eje de categorías.

## Paso 12: Personalice las líneas de cuadrícula menores para el eje de categorías

De manera similar al eje de valores, puede personalizar las líneas de cuadrícula menores para el eje de categorías.

```csharp
//Configuración del formato de líneas de cuadrícula menores para el eje de categorías
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Aquí ajusta la apariencia de las líneas de cuadrícula menores en el eje de categorías.

## Paso 13: Personalizar las propiedades del texto del eje de categorías

Personalice las propiedades de texto para las etiquetas del eje de categorías.

```csharp
// Configuración de las propiedades del texto del eje de categorías
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Este código le permite ajustar el estilo de fuente y la apariencia de las etiquetas del eje de categorías.

## Paso 14: Agregar título del eje de categoría

También puede agregar un título al eje de categorías si es necesario.

```csharp
// Configuración del título de categoría
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

En este paso, puede establecer un título para el eje de categorías.

## Paso 15: personalizaciones adicionales

Puede explorar más personalizaciones, como leyendas, colores de la pared posterior del gráfico, del suelo y del área de trazado. Estas personalizaciones le permiten mejorar el atractivo visual de su gráfico.

```csharp
// Personalizaciones adicionales (opcional)

// Configuración de propiedades de texto de leyendas
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Establecer mostrar leyendas de gráficos sin superponer gráficos
chart.Legend.Overlay = true;

// Trazar la primera serie en el eje de valores secundario (si es necesario)
// Chart.ChartData.Series[0].PlotOnSecondAxis = verdadero;

// Configuración del color de la pared posterior del gráfico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Configuración del color del suelo del gráfico
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Configuración del color del área de trazado
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// guardar la presentación
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Estas personalizaciones adicionales son opcionales y se pueden aplicar según los requisitos específicos de diseño de su gráfico.

## Conclusión

En esta guía paso a paso, exploramos la personalización avanzada de gráficos utilizando Aspose.Slides para .NET. Ha aprendido a crear una presentación, agregar un gráfico y ajustar su apariencia, incluidas las líneas de la cuadrícula, las etiquetas de los ejes y otros elementos visuales. Con las poderosas opciones de personalización proporcionadas por Aspose.Slides, puede crear gráficos que transmitan sus datos de manera efectiva y atraigan a su audiencia.

 Si tiene alguna pregunta o encuentra algún desafío mientras trabaja con Aspose.Slides para .NET, no dude en explorar la documentación.[aquí](https://reference.aspose.com/slides/net/) o busque ayuda en Aspose.Slides[foro](https://forum.aspose.com/).

## Preguntas frecuentes

### ¿Qué versiones de .NET son compatibles con Aspose.Slides para .NET?
Aspose.Slides para .NET admite varias versiones de .NET, incluidos .NET Framework y .NET Core. Puede consultar la documentación para obtener la lista completa de versiones compatibles.

### ¿Puedo crear gráficos a partir de fuentes de datos como archivos de Excel usando Aspose.Slides para .NET?
Sí, Aspose.Slides para .NET le permite crear gráficos a partir de fuentes de datos externas como hojas de cálculo de Excel. Puede explorar la documentación para ver ejemplos detallados.

### ¿Cómo puedo agregar etiquetas de datos personalizadas a mi serie de gráficos?
 Para agregar etiquetas de datos personalizadas a su serie de gráficos, puede acceder al`DataLabels` propiedad de la serie y personalizar las etiquetas según sea necesario. Consulte la documentación para obtener ejemplos y ejemplos de código.

### ¿Es posible exportar el gráfico a diferentes formatos de archivo, como PDF o formatos de imagen?
Sí, Aspose.Slides para .NET ofrece opciones para exportar su presentación con gráficos a varios formatos, incluidos PDF y formatos de imagen. Puede utilizar la biblioteca para guardar su trabajo en el formato de salida deseado.

### ¿Dónde puedo encontrar más tutoriales y ejemplos de Aspose.Slides para .NET?
 Puede encontrar una gran cantidad de tutoriales, ejemplos de código y documentación en Aspose.Slides.[sitio web](https://reference.aspose.com/slides/net/).