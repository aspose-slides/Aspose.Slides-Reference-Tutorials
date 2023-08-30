---
title: Agregar barras de error personalizadas al gráfico
linktitle: Agregar barras de error personalizadas al gráfico
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar barras de error personalizadas a los gráficos usando Aspose.Slides para .NET. Cree, diseñe y personalice barras de error para una visualización precisa de los datos.
type: docs
weight: 13
url: /es/net/licensing-and-formatting/add-custom-error/
---

## Introducción a las barras de error personalizadas

Las barras de error son representaciones gráficas que se utilizan para indicar la variabilidad o incertidumbre de los puntos de datos en un gráfico. Pueden ayudar a representar el rango dentro del cual es probable que se encuentre el valor real del punto de datos. Las barras de error personalizadas le permiten definir valores de error específicos para cada punto de datos, lo que proporciona más control sobre cómo se muestra la incertidumbre en su gráfico.

## Configurar el entorno de desarrollo

 Antes de comenzar, asegúrese de tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net). Siga las instrucciones de instalación proporcionadas en la documentación.

## Crear un gráfico de muestra

Comencemos creando un gráfico de muestra usando Aspose.Slides para .NET. Crearemos un gráfico de barras básico con fines de demostración. Asegúrese de haber hecho referencia a la biblioteca en su proyecto.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Crear una instancia del objeto de presentación
using Presentation presentation = new Presentation();

// Agregar una diapositiva
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Agregar un gráfico
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Agregar datos de muestra
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Establecer etiquetas de categoría
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Establecer título del gráfico
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// guardar la presentación
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Este código crea una presentación de PowerPoint con un gráfico de barras de muestra.

## Agregar barras de error al gráfico

Ahora agreguemos barras de error al gráfico. Las barras de error se agregan a puntos de datos específicos de una serie. Agregaremos barras de error al primer punto de datos de nuestro gráfico de muestra.

```csharp
// Accede a la primera serie
IChartSeries firstSeries = chart.ChartData.Series[0];

// Agregar barras de error
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Establecer valor de la barra de error
errorBarsFormat.Value = 5; // Puedes ajustar el valor según tus datos.

// Guarde la presentación actualizada
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Este código agrega barras de error de valor fijo al primer punto de datos del gráfico.

## Personalización de los valores de la barra de error

Puede personalizar los valores de la barra de error para cada punto de datos individualmente. Modifiquemos el código para establecer diferentes valores de error para cada punto de datos.

```csharp
// Establecer valores de error personalizados para cada punto
double[] errorValues = { 3, 6 }; // Valores de error para los dos puntos de datos.

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Guarde la presentación actualizada
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Este código establece valores de error personalizados para cada punto de datos de la serie.

## Aplicar estilo a las barras de error

Puede diseñar barras de error para mejorar su visibilidad y combinarlas con la estética de su gráfico. Personalicemos la apariencia de las barras de error.

```csharp
// Personalizar la apariencia de la barra de errores
errorBarsFormat.LineFormat.Width = 2; // Establecer ancho de línea
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //Establecer color de línea

// Guarde la presentación actualizada
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Este código ajusta el ancho de línea y el color de las barras de error.

## Actualización de los datos del gráfico

Si necesita actualizar los datos del gráfico, puede hacerlo fácilmente utilizando Aspose.Slides para .NET. Reemplacemos los datos con nuevos valores.

```csharp
// Actualizar datos del gráfico
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Guarde la presentación actualizada
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Este código actualiza los valores de los datos del gráfico.

## Barras de error para varias series

Puede agregar barras de error a varias series en un gráfico. Agreguemos barras de error a la segunda serie de nuestro gráfico de muestra.

```csharp
// Accede a la segunda serie.
IChartSeries secondSeries = chart.ChartData.Series[1];

// Agregar barras de error a la segunda serie.
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// Establecer el valor de la barra de error para la segunda serie
secondSeriesErrorBars.Value = 10; // Puedes ajustar el valor.

// Guarde la presentación actualizada
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Este código agrega barras de error a la segunda serie del gráfico.

## Manejo de errores negativos y positivos

Las barras de error pueden representar errores tanto positivos como negativos. Modifiquemos el código para agregar ambos tipos de barras de error.

```csharp
// Agregar barras de error positivas y negativas
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Valor de error positivo
errorBarsFormat.MinusValue = 2; // Valor de error negativo

// Guarde la presentación actualizada
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Este código agrega barras de error positivas y negativas personalizadas al gráfico.

## Guardar y exportar el gráfico

Una vez que haya agregado barras de error y haya personalizado su gráfico, puede guardarlo y exportarlo para su uso posterior.

```csharp
// Guardar el gráfico final
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Este código guarda el gráfico final con barras de error.

## Conclusión

En este tutorial, exploramos cómo agregar barras de error personalizadas a un gráfico usando Aspose.Slides para .NET. Cubrimos la creación de un gráfico de muestra, la adición de barras de error, la personalización de valores de error, el diseño de barras de error, la actualización de datos del gráfico, la adición de barras de error a varias series y el manejo de errores positivos y negativos. Con Aspose.Slides para .NET, tiene la flexibilidad de crear gráficos informativos y visualmente atractivos con barras de error personalizadas que comunican de manera efectiva la variabilidad de sus datos.

## Preguntas frecuentes

### ¿Cómo puedo ajustar el grosor de las barras de error?

 Puede ajustar el grosor de las barras de error modificando el`LineFormat.Width` propiedad de la`ErrorBarsFormat`.

### ¿Puedo utilizar diferentes valores de error para cada punto de datos?

Sí, puede establecer valores de error personalizados para cada punto de datos individualmente usando un bucle y el`Value` propiedad de`ErrorBarsFormat`.

### ¿Es posible agregar barras de error a varias series en un solo gráfico?

Por supuesto, puedes agregar barras de error a varias series en el mismo gráfico. Simplemente acceda a la serie deseada y aplique las barras de error como se muestra en el artículo.

### ¿Puedo eliminar las barras de error después de agregarlas?

 Sí, puedes eliminar las barras de error llamando al`Clear` método en el`ErrorBarsFormat` objeto.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para .NET?

 Puede encontrar documentación detallada y ejemplos de Aspose.Slides para .NET en el[Sitio web de documentación de Aspose](https://reference.aspose.com/slides/net/).