---
title: Creando hermosos gráficos con Aspose.Slides para .NET
linktitle: Entidades y formato del gráfico
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a crear gráficos impresionantes con Aspose.Slides para .NET. Mejore su juego de visualización de datos con nuestra guía paso a paso.
weight: 13
url: /es/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creando hermosos gráficos con Aspose.Slides para .NET


En el mundo actual impulsado por los datos, la visualización eficaz de los datos es clave para transmitir información a su audiencia. Aspose.Slides para .NET es una poderosa biblioteca que le permite crear presentaciones y diapositivas impresionantes, incluidos gráficos llamativos. En este tutorial, lo guiaremos a través del proceso de creación de hermosos gráficos usando Aspose.Slides para .NET. Dividiremos cada ejemplo en varios pasos para ayudarle a comprender e implementar las entidades y el formato del gráfico. ¡Entonces empecemos!

## Requisitos previos

Antes de sumergirnos en la creación de gráficos hermosos con Aspose.Slides para .NET, deberá asegurarse de cumplir con los siguientes requisitos previos:

1.  Aspose.Slides para .NET: asegúrese de tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/slides/net/).

2. Entorno de desarrollo: debe tener un entorno de desarrollo funcional con Visual Studio o cualquier otro IDE que admita el desarrollo .NET.

3. Conocimientos básicos de C#: la familiaridad con la programación de C# es esencial para este tutorial.

Ahora que tenemos nuestros requisitos previos ordenados, procedamos a crear hermosos gráficos con Aspose.Slides para .NET.

## Importar espacios de nombres

Primero, necesita importar los espacios de nombres necesarios para trabajar con Aspose.Slides para .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Paso 1: crea una presentación

Comenzamos creando una nueva presentación con la que trabajar. Esta presentación servirá como lienzo para nuestro gráfico.

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

## Paso 2: acceda a la primera diapositiva

Accedamos a la primera diapositiva de la presentación donde colocaremos nuestro gráfico.

```csharp
// Accediendo a la primera diapositiva
ISlide slide = pres.Slides[0];
```

## Paso 3: agregue un gráfico de muestra

Ahora agregaremos un gráfico de muestra a nuestra diapositiva. En este ejemplo, crearemos un gráfico de líneas con marcadores.

```csharp
// Agregar el gráfico de muestra
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Paso 4: establecer el título del gráfico

Le daremos un título a nuestro gráfico, haciéndolo más informativo y visualmente atractivo.

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

## Paso 5: personalizar las líneas de la cuadrícula del eje vertical

En este paso, personalizaremos las líneas de la cuadrícula del eje vertical para que nuestro gráfico sea más atractivo visualmente.

```csharp
// Configuración del formato de líneas de cuadrícula principales para el eje de valores
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Configuración del formato de líneas de cuadrícula menores para el eje de valores
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Configuración del formato del número del eje del valor
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Paso 6: Definir el rango del eje vertical

En este paso, estableceremos los valores máximo, mínimo y unitario para el eje vertical.

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

## Paso 7: Personaliza el texto del eje vertical

Ahora personalizaremos la apariencia del texto en el eje vertical.

```csharp
// Configuración de las propiedades del texto del eje de valor
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

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

## Paso 8: Personalice las líneas de la cuadrícula del eje horizontal

Ahora, personalicemos las líneas de la cuadrícula para el eje horizontal.

```csharp
// Configuración del formato de líneas de cuadrícula principales para el eje de categorías
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Configuración del formato de líneas de cuadrícula menores para el eje de categorías
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Configuración de las propiedades del texto del eje de categorías
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Paso 9: Personaliza las etiquetas del eje horizontal

En este paso, ajustaremos la posición y la rotación de las etiquetas del eje horizontal.

```csharp
// Configuración de la posición de la etiqueta del eje de categoría
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Configuración del ángulo de rotación de la etiqueta del eje de categoría
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Paso 10: personaliza las leyendas

Mejoremos las leyendas de nuestro gráfico para una mejor legibilidad.

```csharp
// Configuración de propiedades de texto de leyendas
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Establecer mostrar leyendas de gráficos sin superponer gráficos
chart.Legend.Overlay = true;
```

## Paso 11: Personaliza el fondo del gráfico

Personalizaremos los colores de fondo del gráfico, la pared posterior y el piso.

```csharp
// Configuración del color de la pared posterior del gráfico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Configuración del color del área de trazado
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Paso 12: guarde la presentación

Finalmente, guardemos nuestra presentación con el gráfico formateado.

```csharp
// Guardar presentación
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusión

Crear gráficos hermosos e informativos en sus presentaciones ahora es más fácil que nunca con Aspose.Slides para .NET. En este tutorial, cubrimos los pasos esenciales para personalizar varios aspectos de un gráfico, haciéndolo visualmente atractivo e informativo. Con estas técnicas, puede crear gráficos impresionantes que transmitan sus datos de manera efectiva a su audiencia.

¡Empiece a experimentar con Aspose.Slides para .NET y lleve su visualización de datos al siguiente nivel!

## Preguntas frecuentes

### 1. ¿Qué es Aspose.Slides para .NET?

Aspose.Slides para .NET es una poderosa biblioteca que permite a los desarrolladores de .NET crear, manipular y convertir presentaciones de Microsoft PowerPoint. Proporciona una amplia gama de funciones para trabajar con diapositivas, formas, gráficos y más.

### 2. ¿Dónde puedo descargar Aspose.Slides para .NET?

 Puede descargar Aspose.Slides para .NET desde el sitio web[aquí](https://releases.aspose.com/slides/net/).

### 3. ¿Existe una prueba gratuita disponible de Aspose.Slides para .NET?

 Sí, puede obtener una prueba gratuita de Aspose.Slides para .NET desde[aquí](https://releases.aspose.com/).

### 4. ¿Cómo puedo obtener una licencia temporal de Aspose.Slides para .NET?

 Si necesita una licencia temporal, puede obtener una de[este enlace](https://purchase.aspose.com/temporary-license/).

### 5. ¿Existe una comunidad o un foro de soporte para Aspose.Slides para .NET?

 Sí, puedes encontrar la comunidad Aspose.Slides y el foro de soporte.[aquí](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
