---
title: Animieren Sie Diagrammreihen mit Aspose.Slides für .NET
linktitle: Animieren von Reihen im Diagramm
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Diagrammreihen mit Aspose.Slides für .NET animieren. Begeistern Sie Ihr Publikum mit dynamischen Präsentationen. Jetzt loslegen!
type: docs
weight: 12
url: /de/net/chart-formatting-and-animation/animating-series/
---

Möchten Sie Ihren Präsentationen mit animierten Diagrammen etwas Schwung verleihen? Aspose.Slides für .NET erweckt Ihre Diagramme zum Leben. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Slides für .NET Reihen in einem Diagramm animieren. Doch bevor wir uns in die Action stürzen, klären wir die Voraussetzungen.

## Voraussetzungen

Um Serien in einem Diagramm mit Aspose.Slides für .NET erfolgreich zu animieren, benötigen Sie Folgendes:

### 1. Aspose.Slides für .NET-Bibliothek

 Stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für .NET installiert haben. Wenn Sie dies noch nicht getan haben, können Sie sie von der[Aspose.Slides für .NET-Website](https://releases.aspose.com/slides/net/).

### 2. Vorhandene Präsentation mit Diagramm

Bereiten Sie eine PowerPoint-Präsentation (PPTX) mit einem vorhandenen Diagramm vor, das Sie animieren möchten.

Nachdem wir nun die Voraussetzungen erfüllt haben, unterteilen wir den Vorgang in eine Reihe von Schritten, um die Diagrammreihe zu animieren.


## Schritt 1: Erforderliche Namespaces importieren

Sie müssen die erforderlichen Namespaces in Ihren C#-Code importieren, um mit Aspose.Slides für .NET zu arbeiten:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Schritt 2: Laden Sie die vorhandene Präsentation

Laden Sie in diesem Schritt Ihre vorhandene PowerPoint-Präsentation (PPTX), die das Diagramm enthält, das Sie animieren möchten.

```csharp
// Pfad zum Dokumentverzeichnis
string dataDir = "Your Document Directory";

// Instanziieren Sie die Präsentationsklasse, die eine Präsentationsdatei darstellt
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Ihr Code kommt hier rein
}
```

## Schritt 3: Referenz des Diagrammobjekts abrufen

Um mit dem Diagramm in Ihrer Präsentation arbeiten zu können, müssen Sie einen Verweis auf das Diagrammobjekt erhalten:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Schritt 4: Animieren Sie die Serie

Jetzt ist es an der Zeit, Ihrer Diagrammreihe Animationseffekte hinzuzufügen. Wir fügen dem gesamten Diagramm einen Einblendeffekt hinzu und lassen jede Reihe einzeln erscheinen.

```csharp
// Animieren des Diagramms
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Fügen Sie jeder Serie eine Animation hinzu
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Schritt 5: Speichern der geänderten Präsentation

Nachdem Sie Ihrem Diagramm die Animationseffekte hinzugefügt haben, speichern Sie die geänderte Präsentation auf der Festplatte.

```csharp
//Speichern der geänderten Präsentation
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich Serien in einem Diagramm animiert.

## Abschluss

In diesem Tutorial haben wir Sie durch den Prozess der Animation von Reihen in einem Diagramm mit Aspose.Slides für .NET geführt. Mit dieser leistungsstarken Bibliothek können Sie ansprechende und dynamische Präsentationen erstellen, die Ihr Publikum fesseln.

 Wenn Sie Fragen haben oder weitere Hilfe benötigen, wenden Sie sich bitte an die Aspose.Slides-Community unter[Hilfeforum](https://forum.aspose.com/).

## FAQs

### Kann ich mit Aspose.Slides für .NET außer Serien auch andere Diagrammelemente animieren?
Ja, Sie können mit Aspose.Slides für .NET verschiedene Diagrammelemente animieren, darunter Datenpunkte, Achsen und Legenden.

### Ist Aspose.Slides für .NET mit den neuesten Versionen von PowerPoint kompatibel?
Aspose.Slides für .NET unterstützt verschiedene PowerPoint-Versionen, einschließlich PowerPoint 2007 und höher, und gewährleistet so die Kompatibilität mit den meisten aktuellen Versionen.

### Kann ich die Animationseffekte für jede Diagrammreihe einzeln anpassen?
Ja, Sie können die Animationseffekte für jede Diagrammreihe anpassen, um einzigartige und ansprechende Präsentationen zu erstellen.

### Gibt es eine Testversion für Aspose.Slides für .NET?
 Ja, Sie können die Bibliothek mit einer kostenlosen Testversion testen von der[Aspose.Slides für .NET-Website](https://releases.aspose.com/).

### Wo kann ich eine Lizenz für Aspose.Slides für .NET erwerben?
 Sie können eine Lizenz für Aspose.Slides für .NET auf der Kaufseite erwerben[Hier](https://purchase.aspose.com/buy).