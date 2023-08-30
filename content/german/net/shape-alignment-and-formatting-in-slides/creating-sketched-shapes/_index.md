---
title: Erstellen skizzierter Formen in Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen skizzierter Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET faszinierende Präsentationsfolien mit skizzierten Formen erstellen. Befolgen Sie diese Schritt-für-Schritt-Anleitung mit vollständigem Quellcode, um Ihren Folien personalisierte und kreative Elemente hinzuzufügen.
type: docs
weight: 13
url: /de/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Einführung in das Erstellen skizzierter Formen in Präsentationsfolien

Präsentationsfolien sind ein leistungsstarkes Werkzeug zur visuellen Vermittlung von Informationen. Manchmal möchten Sie Ihren Folien vielleicht eine persönliche Note verleihen, indem Sie skizzierte Formen einfügen, was Ihre Präsentationen ansprechender und kreativer machen kann. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie dies mit der Aspose.Slides for .NET-Bibliothek erreichen. Am Ende dieses Tutorials werden Sie in der Lage sein, Präsentationsfolien mit skizzierten Formen zu erstellen, die auffallen. Lass uns eintauchen!

## Einrichten des Projekts

 Bevor wir beginnen, stellen Sie sicher, dass die .NET-Entwicklungsumgebung auf Ihrem Computer eingerichtet ist. Sie können die neueste Version von Aspose.Slides von der Website herunterladen[Hier](https://releases.aspose.com/slides/net/). Installieren Sie die Bibliothek nach dem Herunterladen in Ihrem Projekt.

## Erstellen einer neuen Präsentation

Beginnen wir mit der Erstellung einer neuen Präsentation mit Aspose.Slides. So können Sie es machen:

```csharp
using Aspose.Slides;

// Erstellen Sie eine neue Präsentation
Presentation presentation = new Presentation();
```

## Skizzierte Formen hinzufügen

Um Ihren Folien skizzierte Formen hinzuzufügen, können Sie in Aspose.Slides verfügbare Freiformformen verwenden. Diese Formen können so angepasst werden, dass sie handgezeichneten Skizzen ähneln. Hier ist ein Beispiel für das Hinzufügen eines skizzierten Rechtecks zu einer Folie:

```csharp
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.Slides[0];

// Definieren Sie die Punkte für das skizzierte Rechteck
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Fügen Sie der Folie eine Freiformform hinzu
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Passen Sie das Erscheinungsbild der skizzierten Form an
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Anpassen skizzierter Formen

Sie können die skizzierten Formen weiter anpassen, indem Sie ihre Farben, Linienstile und andere Eigenschaften anpassen. Experimentieren Sie mit verschiedenen Einstellungen, um den gewünschten handgezeichneten Effekt zu erzielen.

## Speichern und Exportieren der Präsentation

Sobald Sie Ihrer Präsentation skizzierte Formen hinzugefügt haben, können Sie sie speichern und in verschiedene Formate exportieren, z. B. PPTX oder PDF. So können Sie es machen:

```csharp
// Speichern Sie die Präsentation in einer Datei
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für .NET Präsentationsfolien mit skizzierten Formen erstellen. Durch das Hinzufügen skizzierter Formen zu Ihren Folien können Sie Ihren Präsentationen eine kreative und personalisierte Note verleihen und sie für Ihr Publikum ansprechender machen. Experimentieren Sie ruhig mit verschiedenen Formen und Anpassungsoptionen, um optisch ansprechende Folien zu erstellen, die einen bleibenden Eindruck hinterlassen.

## FAQs

### Wie kann ich Aspose.Slides für .NET herunterladen?

 Sie können die neueste Version von Aspose.Slides für .NET von der Veröffentlichungsseite herunterladen[Hier](https://releases.aspose.com/slides/net/).

### Kann ich das Erscheinungsbild skizzierter Formen anpassen?

Ja, Sie können das Erscheinungsbild skizzierter Formen anpassen, indem Sie deren Farben, Linienstile und andere Eigenschaften mithilfe von Aspose.Slides anpassen.

### Ist Aspose.Slides sowohl für Anfänger als auch für erfahrene Entwickler geeignet?

Ja, Aspose.Slides bietet eine benutzerfreundliche API, die sowohl für Anfänger als auch für erfahrene Entwickler geeignet ist. Es bietet eine umfassende Dokumentation, die Ihnen den Einstieg erleichtert.

### Kann ich meine Präsentation mit skizzierten Formen als PDF exportieren?

Absolut! Mithilfe der Exportoptionen von Aspose.Slides können Sie Ihre Präsentation mit skizzierten Formen in verschiedene Formate, einschließlich PDF, exportieren.

### Wie kann ich andere Arten skizzierter Formen hinzufügen, z. B. Kreise oder Linien?

 Sie können andere Arten skizzierter Formen hinzufügen, z. B. Kreise oder Linien, indem Sie die Punkte und den Formtyp in ändern`AddFreeform` Methode. Experimentieren Sie mit verschiedenen Punktkonfigurationen, um die gewünschten Formen zu erstellen.