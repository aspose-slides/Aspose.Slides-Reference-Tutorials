---
"description": "Aprenda a animar series de gráficos con Aspose.Slides para .NET. Involucre a su audiencia con presentaciones dinámicas. ¡Empiece ya!"
"linktitle": "Serie animada en gráfico"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Animar series de gráficos con Aspose.Slides para .NET"
"url": "/es/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animar series de gráficos con Aspose.Slides para .NET


¿Quieres darle un toque especial a tus presentaciones con gráficos animados? Aspose.Slides para .NET está aquí para darles vida. En esta guía paso a paso, te mostraremos cómo animar series en un gráfico usando Aspose.Slides para .NET. Pero antes de empezar, veamos los requisitos previos.

## Prerrequisitos

Para animar con éxito una serie en un gráfico utilizando Aspose.Slides para .NET, necesitará lo siguiente:

### 1. Biblioteca Aspose.Slides para .NET

Asegúrate de tener instalada la biblioteca Aspose.Slides para .NET. Si aún no la tienes, puedes descargarla desde [Aspose.Slides para sitios web .NET](https://releases.aspose.com/slides/net/).

### 2. Presentación existente con un gráfico

Prepare una presentación de PowerPoint (PPTX) con un gráfico existente que desee animar.

Ahora que cubrimos los requisitos previos, dividamos el proceso en una serie de pasos para animar la serie de gráficos.


## Paso 1: Importar los espacios de nombres necesarios

Necesitará importar los espacios de nombres necesarios en su código C# para trabajar con Aspose.Slides para .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Paso 2: Cargar la presentación existente

En este paso, cargue su presentación de PowerPoint (PPTX) existente que contiene el gráfico que desea animar.

```csharp
// Ruta al directorio de documentos
string dataDir = "Your Document Directory";

// Crear una instancia de la clase Presentation que representa un archivo de presentación 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Tu código va aquí
}
```

## Paso 3: Obtener la referencia del objeto gráfico

Para trabajar con el gráfico en su presentación, necesitará obtener una referencia al objeto del gráfico:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Paso 4: Animar la serie

Ahora es el momento de añadir efectos de animación a tu serie de gráficos. Añadiremos un efecto de fundido de entrada a todo el gráfico y haremos que cada serie aparezca una por una.

```csharp
// Animar el gráfico
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Añade animación a cada serie
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Paso 5: Guardar la presentación modificada

Una vez que haya agregado los efectos de animación a su gráfico, guarde la presentación modificada en el disco.

```csharp
// Guardar la presentación modificada
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has animado series en un gráfico con éxito usando Aspose.Slides para .NET.

## Conclusión

En este tutorial, te explicamos el proceso de animación de series en un gráfico con Aspose.Slides para .NET. Con esta potente biblioteca, puedes crear presentaciones atractivas y dinámicas que cautivarán a tu audiencia.

Si tiene alguna pregunta o necesita más ayuda, no dude en comunicarse con la comunidad de Aspose.Slides en su [foro de soporte](https://forum.aspose.com/).

## Preguntas frecuentes

### ¿Puedo animar otros elementos del gráfico además de las series usando Aspose.Slides para .NET?
Sí, puede animar varios elementos de gráficos, incluidos puntos de datos, ejes y leyendas, utilizando Aspose.Slides para .NET.

### ¿Aspose.Slides para .NET es compatible con las últimas versiones de PowerPoint?
Aspose.Slides para .NET admite varias versiones de PowerPoint, incluidas PowerPoint 2007 y posteriores, lo que garantiza la compatibilidad con las versiones más recientes.

### ¿Puedo personalizar los efectos de animación para cada serie de gráficos individualmente?
Sí, puedes adaptar los efectos de animación para cada serie de gráficos para crear presentaciones únicas y atractivas.

### ¿Hay una versión de prueba disponible para Aspose.Slides para .NET?
Sí, puedes probar la biblioteca con una prueba gratuita desde [Aspose.Slides para sitios web .NET](https://releases.aspose.com/).

### ¿Dónde puedo comprar una licencia de Aspose.Slides para .NET?
Puede adquirir una licencia para Aspose.Slides para .NET desde la página de compra [aquí](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}