---
title: Festlegen von Foliennummern für Präsentationen mit Aspose.Slides
linktitle: Festlegen von Foliennummern für Präsentationen mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Foliennummern in PowerPoint-Präsentationen hinzufügen und anpassen. Diese Schritt-für-Schritt-Anleitung enthält Quellcodebeispiele zum Einrichten des Projekts, zum Laden einer Präsentation, zum Hinzufügen von Foliennummern, zum Anpassen ihres Formats und zum Anpassen ihrer Platzierung.
type: docs
weight: 16
url: /de/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine vielseitige Bibliothek, die es .NET-Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu erstellen, zu ändern und zu bearbeiten. Es bietet eine breite Palette von Funktionen für die Interaktion mit verschiedenen Elementen von Präsentationen, darunter Folien, Formen, Text, Bilder und mehr. In diesem Leitfaden konzentrieren wir uns auf das Hinzufügen und Anpassen von Foliennummern mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio (oder eine andere .NET-Entwicklungsumgebung)
-  Aspose.Slides für .NET-Bibliothek (Download von[Hier](https://releases.aspose.com/slides/net/)

## Einrichten des Projekts

1. Erstellen Sie ein neues Visual Studio-Projekt (z. B. Konsolenanwendung).
2. Fügen Sie einen Verweis auf die Aspose.Slides for .NET-Bibliothek hinzu.

## Laden einer Präsentation

Laden wir zunächst eine vorhandene PowerPoint-Präsentation:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Foliennummern hinzufügen

Als Nächstes fügen wir jeder Folie in der Präsentation Foliennummern hinzu:

```csharp
// Foliennummern aktivieren
foreach (ISlide slide in presentation.Slides)
{
    // Foliennummernform hinzufügen
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Anpassen des Foliennummernformats

Sie können das Erscheinungsbild der Foliennummern anpassen, indem Sie Schriftart, Farbe, Größe und mehr anpassen:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Passen Sie Schriftart und Farbe an
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Aktualisierung der Platzierung der Foliennummern

Sie können auch die Position der Foliennummern auf jeder Folie anpassen:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Speichern der geänderten Präsentation

Nachdem Sie die Foliennummern hinzugefügt und angepasst haben, speichern Sie die geänderte Präsentation:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Ihre Präsentationen durch Hinzufügen und Anpassen von Foliennummern mit Aspose.Slides für .NET verbessern können. Indem Sie die bereitgestellten Schritte und Codebeispiele befolgen, können Sie das Hinzufügen von Foliennummern automatisieren und professionell aussehende Präsentationen erstellen.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

 Sie können die Aspose.Slides für .NET-Bibliothek unter herunterladen[Hier](https://releases.aspose.com/slides/net/). Fügen Sie nach dem Herunterladen einen Verweis auf die Bibliothek in Ihrem .NET-Projekt hinzu.

### Kann ich das Erscheinungsbild von Foliennummern anpassen?

Ja, Sie können Schriftart, Farbe, Größe und andere Attribute der Foliennummern mithilfe der bereitgestellten Codebeispiele anpassen.

### Wie kann ich die Position der Foliennummern auf jeder Folie anpassen?

Sie können die Position der Foliennummern anpassen, indem Sie die Koordinaten der Foliennummernformen ändern, wie in den Codebeispielen gezeigt.

### Ist Aspose.Slides für .NET nur zum Hinzufügen von Foliennummern gedacht?

Nein, Aspose.Slides für .NET bietet eine breite Palette an Funktionen, die über das Hinzufügen von Foliennummern hinausgehen. Es ermöglicht Ihnen, verschiedene Elemente von PowerPoint-Präsentationen programmgesteuert zu erstellen, zu ändern und zu bearbeiten.

### Sind die Änderungen rückgängig zu machen, wenn ich die Foliennummern später entfernen möchte?

Ja, Sie können die Foliennummern einfach entfernen, indem Sie mithilfe der Aspose.Slides-Bibliothek die entsprechenden Formen aus den Folien entfernen.