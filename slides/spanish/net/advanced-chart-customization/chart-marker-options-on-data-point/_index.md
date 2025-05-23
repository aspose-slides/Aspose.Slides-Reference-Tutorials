---
"description": "Aprenda a mejorar sus gráficos de PowerPoint con Aspose.Slides para .NET. Personalice marcadores de puntos de datos con imágenes. Cree presentaciones atractivas."
"linktitle": "Opciones de marcador de gráfico en el punto de datos"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Uso de las opciones de marcador de gráfico en puntos de datos en Aspose.Slides .NET"
"url": "/es/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uso de las opciones de marcador de gráfico en puntos de datos en Aspose.Slides .NET


Al trabajar con presentaciones y visualización de datos, Aspose.Slides para .NET ofrece una amplia gama de potentes funciones para crear, personalizar y manipular gráficos. En este tutorial, exploraremos cómo usar las opciones de marcadores de gráficos en los puntos de datos para mejorar sus presentaciones. Esta guía paso a paso le guiará por el proceso, desde los prerrequisitos y la importación de espacios de nombres hasta el desglose de cada ejemplo en varios pasos.

## Prerrequisitos

Antes de profundizar en el uso de las opciones de marcadores de gráficos en puntos de datos, asegúrese de tener los siguientes requisitos previos:

- Aspose.Slides para .NET: Asegúrate de tener instalado Aspose.Slides para .NET. Puedes descargarlo desde [sitio web](https://releases.aspose.com/slides/net/).

- Presentación de ejemplo: Para este tutorial, usaremos una presentación de ejemplo llamada "Test.pptx". Debería tenerla en su directorio de documentos.

Ahora, comencemos importando los espacios de nombres necesarios.

## Importar espacios de nombres

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Hemos importado los espacios de nombres necesarios e inicializado nuestra presentación. Ahora, procedamos a usar las opciones de marcador de gráfico en los puntos de datos.

## Paso 1: Creación del gráfico predeterminado

```csharp

// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Creando el gráfico predeterminado
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Creamos un gráfico predeterminado de tipo "LineWithMarkers" en la diapositiva en una ubicación y tamaño específicos.

## Paso 2: Obtener el índice de la hoja de cálculo de datos del gráfico predeterminado

```csharp
// Obtener el índice de la hoja de cálculo con datos del gráfico predeterminado
int defaultWorksheetIndex = 0;
```

Aquí obtenemos el índice de la hoja de cálculo de datos del gráfico predeterminado.

## Paso 3: Obtener la hoja de trabajo de datos del gráfico

```csharp
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Buscamos el libro de trabajo de datos de gráficos para trabajar con datos de gráficos.

## Paso 4: Modificar la serie del gráfico

```csharp
// Eliminar la serie de demostración
chart.ChartData.Series.Clear();

// Añadir nueva serie
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

En este paso, eliminamos cualquier serie de demostración existente y agregamos una nueva serie llamada "Serie 1" al gráfico.

## Paso 5: Configuración del relleno de imagen para los puntos de datos

```csharp
// Establezca la imagen para los marcadores
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Tome la primera serie de gráficos
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

Establecemos marcadores de imagen para los puntos de datos, lo que le permite personalizar cómo aparece cada punto de datos en el gráfico.

## Paso 6: Cambiar el tamaño del marcador de la serie del gráfico

```csharp
// Cambiar el tamaño del marcador de la serie del gráfico
series.Marker.Size = 15;
```

Aquí, ajustamos el tamaño del marcador de la serie del gráfico para que sea visualmente atractivo.

## Paso 7: Guardar la presentación

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con la nueva configuración del gráfico.

## Conclusión

Aspose.Slides para .NET te permite crear presentaciones gráficas impactantes con diversas opciones de personalización. En este tutorial, nos centramos en el uso de marcadores de gráficos en puntos de datos para mejorar la representación visual de tus datos. Con Aspose.Slides para .NET, puedes llevar tus presentaciones al siguiente nivel, haciéndolas más atractivas e informativas.

Si tiene alguna pregunta o necesita ayuda con Aspose.Slides para .NET, no dude en visitar el sitio web [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/) o comuníquese con el [Comunidad Aspose](https://forum.aspose.com/) para soporte.

## Preguntas frecuentes (FAQ)

### ¿Puedo usar imágenes personalizadas como marcadores de puntos de datos en Aspose.Slides para .NET?
Sí, puede utilizar imágenes personalizadas como marcadores de puntos de datos en Aspose.Slides para .NET, como se muestra en este tutorial.

### ¿Cómo puedo cambiar el tipo de gráfico en Aspose.Slides para .NET?
Puede cambiar el tipo de gráfico especificando uno diferente. `ChartType` al crear el gráfico, como "Barra", "Circular" o "Área".

### ¿Aspose.Slides para .NET es compatible con las últimas versiones de PowerPoint?
Aspose.Slides para .NET está diseñado para funcionar con varios formatos de PowerPoint y se actualiza periódicamente para mantener la compatibilidad con las últimas versiones de PowerPoint.

### ¿Dónde puedo encontrar más tutoriales y recursos para Aspose.Slides para .NET?
Puede explorar tutoriales y recursos adicionales en el [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/).

### ¿Hay una versión de prueba de Aspose.Slides para .NET disponible?
Sí, puedes probar Aspose.Slides para .NET descargando una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}