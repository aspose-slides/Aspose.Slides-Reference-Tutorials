---
title: Animar series de gráficos con Aspose.Slides para .NET
linktitle: Serie animada en gráfico
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a animar series de gráficos con Aspose.Slides para .NET. Involucre a su audiencia con presentaciones dinámicas. ¡Empieza ahora!
weight: 12
url: /es/net/chart-formatting-and-animation/animating-series/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


¿Está buscando agregar algo de dinamismo a sus presentaciones con gráficos animados? Aspose.Slides para .NET está aquí para hacer que sus gráficos cobren vida. En esta guía paso a paso, le mostraremos cómo animar series en un gráfico usando Aspose.Slides para .NET. Pero antes de sumergirnos en la acción, cubramos los requisitos previos.

## Requisitos previos

Para animar con éxito series en un gráfico usando Aspose.Slides para .NET, necesitará lo siguiente:

### 1. Aspose.Slides para la biblioteca .NET

 Asegúrese de tener instalada la biblioteca Aspose.Slides para .NET. Si aún no lo has hecho, puedes descargarlo desde[Aspose.Slides para el sitio web .NET](https://releases.aspose.com/slides/net/).

### 2. Presentación existente con un gráfico

Prepare una presentación de PowerPoint (PPTX) con un gráfico existente que desee animar.

Ahora que tenemos cubiertos los requisitos previos, dividamos el proceso en una serie de pasos para animar la serie de gráficos.


## Paso 1: importar los espacios de nombres necesarios

Necesitará importar los espacios de nombres requeridos en su código C# para trabajar con Aspose.Slides para .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Paso 2: cargue la presentación existente

En este paso, cargue su presentación de PowerPoint (PPTX) existente que contiene el gráfico que desea animar.

```csharp
// Ruta al directorio de documentos
string dataDir = "Your Document Directory";

// Crear una instancia de la clase de presentación que representa un archivo de presentación
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Tu código va aquí
}
```

## Paso 3: obtener referencia del objeto del gráfico

Para trabajar con el gráfico en su presentación, necesitará obtener una referencia al objeto del gráfico:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Paso 4: anima la serie

Ahora es el momento de agregar efectos de animación a su serie de gráficos. Agregaremos un efecto de aparición gradual a todo el gráfico y haremos que cada serie aparezca una por una.

```csharp
// animar el gráfico
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Añade animación a cada serie.
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Paso 5: guarde la presentación modificada

Una vez que haya agregado los efectos de animación a su gráfico, guarde la presentación modificada en el disco.

```csharp
//Guardar la presentación modificada
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Has animado con éxito series en un gráfico usando Aspose.Slides para .NET.

## Conclusión

En este tutorial, lo guiamos a través del proceso de animación de series en un gráfico usando Aspose.Slides para .NET. Con esta poderosa biblioteca, puede crear presentaciones atractivas y dinámicas que cautiven a su audiencia.

 Si tiene alguna pregunta o necesita más ayuda, no dude en comunicarse con la comunidad Aspose.Slides en su[Foro de soporte](https://forum.aspose.com/).

## Preguntas frecuentes

### ¿Puedo animar otros elementos del gráfico además de las series usando Aspose.Slides para .NET?
Sí, puede animar varios elementos del gráfico, incluidos puntos de datos, ejes y leyendas, utilizando Aspose.Slides para .NET.

### ¿Aspose.Slides para .NET es compatible con las últimas versiones de PowerPoint?
Aspose.Slides para .NET admite varias versiones de PowerPoint, incluido PowerPoint 2007 y posteriores, lo que garantiza la compatibilidad con las versiones más recientes.

### ¿Puedo personalizar los efectos de animación para cada serie de gráficos individualmente?
Sí, puedes personalizar los efectos de animación de cada serie de gráficos para crear presentaciones únicas y atractivas.

### ¿Existe una versión de prueba disponible para Aspose.Slides para .NET?
 Sí, puedes probar la biblioteca con una prueba gratuita desde[Aspose.Slides para el sitio web .NET](https://releases.aspose.com/).

### ¿Dónde puedo comprar una licencia de Aspose.Slides para .NET?
 Puede adquirir una licencia de Aspose.Slides para .NET desde la página de compra[aquí](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
