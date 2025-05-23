---
"description": "Erfahren Sie, wie Sie Diagramme in Aspose.Slides für .NET formatieren und animieren und Ihre Präsentationen mit fesselnden visuellen Elementen verbessern."
"linktitle": "Diagrammformatierung und Animation in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Diagrammformatierung und Animation in Aspose.Slides"
"url": "/de/net/chart-formatting-and-animation/chart-formatting-and-animation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagrammformatierung und Animation in Aspose.Slides


Überzeugende Präsentationen mit dynamischen Diagrammen und Animationen können die Wirkung Ihrer Botschaft deutlich steigern. Aspose.Slides für .NET ermöglicht Ihnen genau das. In diesem Tutorial führen wir Sie durch die Animation und Formatierung von Diagrammen mit Aspose.Slides für .NET. Wir unterteilen die Schritte in überschaubare Abschnitte, damit Sie das Konzept gründlich verstehen.

## Voraussetzungen

Bevor Sie mit Aspose.Slides in die Diagrammformatierung und -animation eintauchen, benötigen Sie Folgendes:

1. Aspose.Slides für .NET: Stellen Sie sicher, dass Sie Aspose.Slides für .NET installiert haben. Falls noch nicht geschehen, können Sie [Laden Sie es hier herunter](https://releases.aspose.com/slides/net/).

2. Vorhandene Präsentation: Sie verfügen über eine vorhandene Präsentation, die ein Diagramm enthält, das Sie formatieren und animieren möchten.

3. Grundlegende C#-Kenntnisse: Kenntnisse in C# sind bei der Implementierung der Schritte hilfreich.

Nun, fangen wir an.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces importieren, um auf die Aspose.Slides-Funktionen zugreifen zu können. Fügen Sie in Ihrem C#-Projekt Folgendes hinzu:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Animieren von Kategorienelementen im Diagramm

### Schritt 1: Laden Sie die Präsentation und greifen Sie auf das Diagramm zu

Laden Sie zunächst Ihre vorhandene Präsentation und rufen Sie das Diagramm auf, das Sie animieren möchten. In diesem Beispiel wird davon ausgegangen, dass sich das Diagramm auf der ersten Folie Ihrer Präsentation befindet.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Schritt 2: Animation zu den Elementen der Kategorien hinzufügen

Fügen wir nun den Elementen der Kategorien eine Animation hinzu. In diesem Beispiel verwenden wir einen Einblendeffekt.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Schritt 3: Speichern Sie die Präsentation

Speichern Sie abschließend die geänderte Präsentation auf der Festplatte.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## Animieren von Reihen im Diagramm

### Schritt 1: Laden Sie die Präsentation und greifen Sie auf das Diagramm zu

Ähnlich wie im vorherigen Beispiel laden Sie die Präsentation und greifen auf das Diagramm zu.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Schritt 2: Animation zur Serie hinzufügen

Fügen wir nun der Diagrammreihe eine Animation hinzu. Auch hier verwenden wir einen Einblendeffekt.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Schritt 3: Speichern Sie die Präsentation

Speichern Sie die geänderte Präsentation mit der Zeichentrickserie.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Animieren von Serienelementen im Diagramm

### Schritt 1: Laden Sie die Präsentation und greifen Sie auf das Diagramm zu

Laden Sie wie zuvor die Präsentation und rufen Sie das Diagramm auf.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Schritt 2: Animation zu Serienelementen hinzufügen

In diesem Schritt fügen Sie den Serienelementen Animationen hinzu und erzeugen so einen eindrucksvollen visuellen Effekt.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### Schritt 3: Speichern Sie die Präsentation

Vergessen Sie nicht, die Präsentation mit den Elementen der Zeichentrickserie zu speichern.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie Diagramme in Aspose.Slides für .NET formatieren und animieren. Diese Techniken können Ihre Präsentationen ansprechender und informativer gestalten.

## Abschluss

Aspose.Slides für .NET bietet leistungsstarke Tools zur Diagrammformatierung und -animation. So erstellen Sie optisch ansprechende Präsentationen, die Ihr Publikum fesseln. Mit dieser Schritt-für-Schritt-Anleitung meistern Sie die Kunst der Diagrammanimation und verbessern Ihre Präsentationen.

## FAQs

### 1. Wo finde ich die Dokumentation für Aspose.Slides für .NET?

Sie können auf die Dokumentation zugreifen unter [https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. Wie lade ich Aspose.Slides für .NET herunter?

Sie können Aspose.Slides für .NET herunterladen von [https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. Gibt es eine kostenlose Testversion?

Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten unter [https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?

Ja, Sie können eine temporäre Lizenz erwerben bei [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Wo kann ich Support erhalten oder Fragen zu Aspose.Slides für .NET stellen?

Für Support und Fragen besuchen Sie das Aspose.Slides-Forum unter [https://forum.aspose.com/](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}