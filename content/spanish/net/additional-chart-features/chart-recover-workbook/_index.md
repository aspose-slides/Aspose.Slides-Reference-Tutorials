---
title: Recuperar libro de trabajo del gráfico
linktitle: Recuperar libro de trabajo del gráfico
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo recuperar un libro de un gráfico usando Aspose.Slides para .NET. Extraiga datos de gráficos y cree libros de Excel mediante programación.
type: docs
weight: 12
url: /es/net/additional-chart-features/chart-recover-workbook/
---

## Introducción

Pueden ocurrir accidentes y es posible que necesite recuperar un libro de trabajo de un gráfico. Aspose.Slides para .NET viene al rescate en tales situaciones. Esta poderosa biblioteca le permite extraer datos de gráficos en presentaciones y convertirlos en un nuevo libro de trabajo. En esta guía paso a paso, lo guiaremos a través del proceso de recuperación de un libro de un gráfico usando Aspose.Slides para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente en su lugar:

- Visual Studio: descargue e instale Visual Studio, que es esencial para el desarrollo de .NET.
-  Aspose.Slides para .NET: puede descargar la biblioteca desde[aquí](https://downloads.aspose.com/slides/net).

## Paso 1: Instale Aspose.Slides para .NET

Si aún no lo ha hecho, descargue e instale Aspose.Slides para .NET. Esta biblioteca proporciona funciones integrales para trabajar con presentaciones de PowerPoint mediante programación.

## Paso 2: cargue la presentación

Para comenzar, cree un nuevo proyecto de C# en Visual Studio. Agregue referencias a los ensamblajes Aspose.Slides necesarios. Cargue la presentación de PowerPoint que contiene el gráfico del que desea recuperar datos.

```csharp
// Cargar la presentación
Presentation presentation = new Presentation("your-presentation.pptx");
```

## Paso 3: identificar el gráfico

 Identifique la diapositiva y el gráfico de los que desea recuperar datos. Puede acceder a las diapositivas utilizando el`presentation.Slides` colección y gráficos utilizando el`slide.Shapes` recopilación.

```csharp
// Obtenga la diapositiva que contiene el gráfico
ISlide slide = presentation.Slides[0];

// Obtener el gráfico
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Paso 4: extraer datos del gráfico

Extraiga los datos del gráfico utilizando la API de Aspose.Slides. Puede recuperar valores de series y categorías de gráficos.

```csharp
// Extraer datos del gráfico
IChartData chartData = chart.ChartData;
```

## Paso 5: cree un nuevo libro de trabajo

Cree un nuevo libro de Excel utilizando una biblioteca como EPPlus o ClosedXML.

```csharp
// Crear un nuevo libro de Excel
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Agregue código aquí para completar los encabezados de la hoja de trabajo
}
```

## Paso 6: llene el libro de trabajo con datos del gráfico

Complete la hoja de cálculo de Excel con los datos extraídos del gráfico.

```csharp
//Complete la hoja de cálculo de Excel con datos del gráfico
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Agregue código aquí para completar la hoja de trabajo con datos de la serie
    rowIndex++;
}
```

## Paso 7: guarde el libro de trabajo

Guarde el libro de Excel con los datos del gráfico recuperados.

```csharp
// Guarde el libro de Excel
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Conclusión

Recuperar un libro de un gráfico es fácil con Aspose.Slides para .NET. Si sigue estos pasos, puede extraer datos de un gráfico en una presentación de PowerPoint mediante programación y crear un nuevo libro de Excel con los datos recuperados. Este proceso puede salvar vidas cuando ocurren accidentes y es necesario recuperar datos.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Slides para .NET?

 Puede descargar Aspose.Slides para .NET desde[aquí](https://downloads.aspose.com/slides/net).

### ¿Puedo recuperar datos de diferentes tipos de gráficos?

Sí, Aspose.Slides para .NET admite varios tipos de gráficos, incluidos gráficos de barras, gráficos de líneas, gráficos circulares y más.

### ¿Aspose.Slides para .NET es adecuado para uso profesional?

¡Absolutamente! Aspose.Slides para .NET es una biblioteca sólida utilizada por los desarrolladores para trabajar con presentaciones de PowerPoint de manera eficiente.

### ¿Existe algún requisito de licencia para utilizar Aspose.Slides para .NET?

 Sí, Aspose.Slides para .NET requiere una licencia válida para uso comercial. Puede encontrar detalles de licencia en el[Aspose sitio web](https://purchase.aspose.com).

### ¿Puedo personalizar la apariencia del libro de Excel recuperado?

Sí, puede personalizar la apariencia y el formato del libro de Excel utilizando bibliotecas como EPPlus o ClosedXML.