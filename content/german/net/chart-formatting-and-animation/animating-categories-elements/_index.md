---
title: Leistungsstarke Diagrammanimationen mit Aspose.Slides für .NET
linktitle: Animieren von Kategorienelementen im Diagramm
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Diagrammelemente in PowerPoint mit Aspose.Slides für .NET animieren. Schritt-für-Schritt-Anleitung für beeindruckende Präsentationen.
type: docs
weight: 11
url: /de/net/chart-formatting-and-animation/animating-categories-elements/
---

In der Welt der Präsentationen können Animationen Ihre Inhalte zum Leben erwecken, insbesondere wenn es um Diagramme geht. Aspose.Slides für .NET bietet eine Reihe leistungsstarker Funktionen, mit denen Sie beeindruckende Animationen für Ihre Diagramme erstellen können. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Animation von Kategorieelementen in einem Diagramm mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, sollten Sie die folgenden Voraussetzungen erfüllen:

-  Aspose.Slides für .NET: Stellen Sie sicher, dass Aspose.Slides für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn Sie es noch nicht getan haben, können Sie es hier herunterladen[Hier](https://releases.aspose.com/slides/net/).

- Vorhandene Präsentation: Sie sollten eine PowerPoint-Präsentation mit einem Diagramm haben, das Sie animieren möchten. Wenn Sie noch keine haben, erstellen Sie zu Testzwecken eine Beispielpräsentation mit einem Diagramm.

Nachdem Sie nun alles vorbereitet haben, beginnen wir mit der Animation dieser Diagrammelemente!

## Namespaces importieren

Der erste Schritt besteht darin, die erforderlichen Namespaces zu importieren, um auf die Funktionalität von Aspose.Slides zuzugreifen. Fügen Sie Ihrem Projekt die folgenden Namespaces hinzu:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Schritt 1: Laden Sie die Präsentation

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Rufen Sie die Referenz des Diagrammobjekts ab
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

In diesem Schritt laden wir die vorhandene PowerPoint-Präsentation mit dem Diagramm, das Sie animieren möchten. Anschließend greifen wir auf das Diagrammobjekt innerhalb der ersten Folie zu.

## Schritt 2: Animieren Sie die Elemente der Kategorien

```csharp
// Animieren Sie die Elemente der Kategorien
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Dieser Schritt fügt dem gesamten Diagramm einen „Fade“-Animationseffekt hinzu, sodass es nach der vorherigen Animation erscheint.

Als Nächstes fügen wir Animationen zu einzelnen Elementen innerhalb jeder Kategorie des Diagramms hinzu. Hier geschieht die wahre Magie.

## Schritt 3: Einzelne Elemente animieren

Wir unterteilen die Animation einzelner Elemente innerhalb jeder Kategorie in die folgenden Schritte:

### Schritt 3.1: Animieren von Elementen in Kategorie 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Hier animieren wir einzelne Elemente innerhalb der Kategorie 0 des Diagramms, sodass sie nacheinander erscheinen. Für diese Animation wird der Effekt „Erscheinen“ verwendet.

### Schritt 3.2: Elemente in Kategorie 1 animieren

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Der Vorgang wird für Kategorie 1 wiederholt, wobei die einzelnen Elemente mithilfe des „Erscheinen“-Effekts animiert werden.

### Schritt 3.3: Elemente in Kategorie 2 animieren

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Der gleiche Vorgang wird für Kategorie 2 fortgesetzt, wobei die Elemente einzeln animiert werden.

## Schritt 4: Speichern Sie die Präsentation

```csharp
//Schreiben Sie die Präsentationsdatei auf die Festplatte
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Im letzten Schritt speichern wir die Präsentation mit den neu hinzugefügten Animationen. Jetzt werden Ihre Diagrammelemente wunderschön animiert, wenn Sie die Präsentation ausführen.

## Abschluss

Das Animieren von Kategorieelementen in einem Diagramm kann die visuelle Attraktivität Ihrer Präsentationen verbessern. Mit Aspose.Slides für .NET wird dieser Prozess unkompliziert und effizient. Sie haben gelernt, wie Sie Namespaces importieren, eine Präsentation laden und Animationen sowohl zum gesamten Diagramm als auch zu seinen einzelnen Elementen hinzufügen. Werden Sie kreativ und gestalten Sie Ihre Präsentationen ansprechender mit Aspose.Slides für .NET.

## FAQs

### 1. Wie kann ich Aspose.Slides für .NET herunterladen?
 Sie können Aspose.Slides für .NET unter herunterladen[dieser Link](https://releases.aspose.com/slides/net/).

### 2. Benötige ich Programmiererfahrung, um Aspose.Slides für .NET zu verwenden?
Während Programmiererfahrung hilfreich ist, bietet Aspose.Slides für .NET umfangreiche Dokumentation und Beispiele, um Benutzern aller Kenntnisstufen zu helfen.

### 3. Kann ich Aspose.Slides für .NET mit jeder PowerPoint-Version verwenden?
Aspose.Slides für .NET ist für die Verwendung mit verschiedenen PowerPoint-Versionen konzipiert und gewährleistet so die Kompatibilität.

### 4. Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
 Sie können eine temporäre Lizenz für Aspose.Slides für .NET erwerben[Hier](https://purchase.aspose.com/temporary-license/).

### 5. Gibt es ein Community-Forum für Aspose.Slides zur .NET-Unterstützung?
 Ja, Sie können ein unterstützendes Community-Forum für Aspose.Slides für .NET finden[Hier](https://forum.aspose.com/).
