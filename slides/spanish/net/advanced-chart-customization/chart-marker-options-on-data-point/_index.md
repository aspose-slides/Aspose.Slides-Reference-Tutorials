---
title: Uso de las opciones de marcador de gráfico en un punto de datos en Aspose.Slides .NET
linktitle: Opciones de marcador de gráfico en punto de datos
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo mejorar sus gráficos de PowerPoint usando Aspose.Slides para .NET. Personalice marcadores de puntos de datos con imágenes. Crea presentaciones atractivas.
type: docs
weight: 11
url: /es/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Cuando se trabaja con presentaciones y visualización de datos, Aspose.Slides para .NET ofrece una amplia gama de potentes funciones para crear, personalizar y manipular gráficos. En este tutorial, exploraremos cómo utilizar las opciones de marcadores de gráficos en puntos de datos para mejorar las presentaciones de sus gráficos. Esta guía paso a paso lo guiará a través del proceso, desde los requisitos previos y la importación de espacios de nombres, hasta dividir cada ejemplo en varios pasos.

## Requisitos previos

Antes de sumergirnos en el uso de las opciones de marcador de gráfico en puntos de datos, asegúrese de tener implementados los siguientes requisitos previos:

-  Aspose.Slides para .NET: asegúrese de tener instalado Aspose.Slides para .NET. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/slides/net/).

- Presentación de muestra: para este tutorial, usaremos una presentación de muestra llamada "Test.pptx". Deberías tener esta presentación en tu directorio de documentos.

Ahora, comencemos importando los espacios de nombres necesarios.

## Importar espacios de nombres

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importamos los espacios de nombres requeridos e inicializamos nuestra presentación. Ahora, procedamos a utilizar las opciones de marcador de gráfico en puntos de datos.

## Paso 1: crear el gráfico predeterminado

```csharp

// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Creando el gráfico predeterminado
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Creamos un gráfico predeterminado de tipo "LineWithMarkers" en la diapositiva en una ubicación y tamaño específicos.

## Paso 2: Obtener el índice de la hoja de trabajo de datos del gráfico predeterminado

```csharp
// Obtener el índice predeterminado de la hoja de cálculo de datos del gráfico
int defaultWorksheetIndex = 0;
```

Aquí obtenemos el índice de la hoja de trabajo de datos del gráfico predeterminada.

## Paso 3: Obtener la hoja de trabajo de datos del gráfico

```csharp
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Recuperamos el libro de datos del gráfico para trabajar con datos del gráfico.

## Paso 4: Modificar la serie de gráficos

```csharp
// Eliminar serie de demostración
chart.ChartData.Series.Clear();

// Agregar nueva serie
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

En este paso, eliminamos cualquier serie de demostración existente y agregamos una nueva serie denominada "Serie 1" al gráfico.

## Paso 5: configurar el relleno de imagen para puntos de datos

```csharp
// Establecer la imagen para los marcadores.
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Tome la primera serie de gráficos.
IChartSeries series = chart.ChartData.Series[0];

// Agregar nuevos puntos de datos con relleno de imagen
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Configuramos marcadores de imágenes para puntos de datos, lo que le permite personalizar cómo aparece cada punto de datos en el gráfico.

## Paso 6: cambiar el tamaño del marcador de la serie de gráficos

```csharp
// Cambiar el tamaño del marcador de serie de gráficos
series.Marker.Size = 15;
```

Aquí, ajustamos el tamaño del marcador de la serie del gráfico para hacerlo visualmente atractivo.

## Paso 7: guardar la presentación

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Finalmente guardamos la presentación con la nueva configuración del gráfico.

## Conclusión

Aspose.Slides para .NET le permite crear impresionantes presentaciones de gráficos con varias opciones de personalización. En este tutorial, nos centramos en el uso de opciones de marcadores de gráficos en puntos de datos para mejorar la representación visual de sus datos. Con Aspose.Slides para .NET, puede llevar sus presentaciones al siguiente nivel, haciéndolas más atractivas e informativas.

Si tiene alguna pregunta o necesita ayuda con Aspose.Slides para .NET, no dude en visitar el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) o comunicarse con el[comunidad aspose](https://forum.aspose.com/) para soporte.

## Preguntas frecuentes (FAQ)

### ¿Puedo usar imágenes personalizadas como marcadores para puntos de datos en Aspose.Slides para .NET?
Sí, puede utilizar imágenes personalizadas como marcadores para puntos de datos en Aspose.Slides para .NET, como se demuestra en este tutorial.

### ¿Cómo puedo cambiar el tipo de gráfico en Aspose.Slides para .NET?
 Puede cambiar el tipo de gráfico especificando otro`ChartType` al crear el gráfico, como "barra", "circular" o "área".

### ¿Aspose.Slides para .NET es compatible con las últimas versiones de PowerPoint?
Aspose.Slides para .NET está diseñado para funcionar con varios formatos de PowerPoint y se actualiza periódicamente para mantener la compatibilidad con las últimas versiones de PowerPoint.

### ¿Dónde puedo encontrar más tutoriales y recursos para Aspose.Slides para .NET?
 Puede explorar tutoriales y recursos adicionales en el[Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/).

### ¿Existe una versión de prueba de Aspose.Slides para .NET disponible?
 Sí, puedes probar Aspose.Slides para .NET descargando una versión de prueba gratuita desde[aquí](https://releases.aspose.com/).