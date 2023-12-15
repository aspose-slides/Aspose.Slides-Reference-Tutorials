---
title: Erstellen einer zusammenfassenden Vergrößerung von Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen einer zusammenfassenden Vergrößerung von Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET fesselnde Präsentationsfolien mit Zusammenfassungszoom erstellen. Unsere Schritt-für-Schritt-Anleitung bietet Quellcode und Anpassungstipps zur Verbesserung der Interaktivität.
type: docs
weight: 16
url: /de/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine Vielzahl von Funktionen, darunter das Erstellen, Bearbeiten und Bearbeiten von Folien, Formen, Text, Bildern und mehr. In diesem Leitfaden konzentrieren wir uns auf die Verwendung von Aspose.Slides für .NET zum Erstellen zusammenfassender Zoomfolien in Präsentationsdecks.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio installiert.
- .NET Framework oder .NET Core installiert.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten der Entwicklungsumgebung

1. Erstellen Sie ein neues .NET-Projekt in Visual Studio.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides-Bibliothek hinzu.

## Laden einer Präsentation

Laden wir zunächst eine vorhandene PowerPoint-Präsentation:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## Hinzufügen von Folien zum Zusammenfassungszoom

Mit zusammenfassenden Zoomfolien können Sie einen Überblick über mehrere Folien auf einer einzigen Folie geben. Fügen wir Folien hinzu, die wir zusammenfassen möchten:

```csharp
// Fügen Sie Folien zur Zusammenfassung hinzu
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## Erstellen von Zusammenfassungs-Zoomfolien

Erstellen wir nun die eigentliche Zusammenfassungs-Zoomfolie, die die Übersicht der zuvor hinzugefügten Folien anzeigt:

```csharp
// Erstellen Sie eine zusammenfassende Zoomfolie
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## Anpassen des Zusammenfassungszoomverhaltens

Sie können das Verhalten des Zusammenfassungszooms anpassen, beispielsweise das Layout und das Erscheinungsbild:

```csharp
// Passen Sie die Zoomeinstellungen für die Zusammenfassung an
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // Titel ausblenden
    zoomFrame.Nodes[1].IsHidden = true; // Verstecken Sie den Inhalt
}
```

## Quellcode als Referenz hinzufügen

Der Einfachheit halber finden Sie hier den vollständigen Quellcode zum Erstellen zusammenfassender Zoomfolien:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Aspose.Slides für .NET verwenden, um zusammenfassende Zoomfolien in Präsentationsdecks zu erstellen. Diese leistungsstarke Funktion kann die Interaktivität und das Engagement Ihrer Präsentationen verbessern und Ihren Inhalten eine professionelle Note verleihen.

## FAQs

### Wie kann ich Aspose.Slides für .NET herunterladen?

 Sie können Aspose.Slides für .NET von herunterladen[Aspose.Slides-Website](https://releases.aspose.com/slides/net/).

### Kann ich das Erscheinungsbild der Zusammenfassungs-Zoomfolien anpassen?

Ja, Sie können das Erscheinungsbild der zusammenfassenden Zoomfolien mithilfe verschiedener Eigenschaften anpassen, die von der Aspose.Slides-Bibliothek bereitgestellt werden.

### Ist Aspose.Slides sowohl mit .NET Framework als auch .NET Core kompatibel?

Ja, Aspose.Slides unterstützt sowohl .NET Framework als auch .NET Core und gibt Ihnen so Flexibilität bei der Auswahl Ihrer Entwicklungsplattform.

### Kann ich zusammenfassende Zoomfolien für bestimmte Folienbereiche erstellen?

Absolut! Sie können die Folien, die Sie in den Zusammenfassungszoom einbeziehen möchten, anhand ihrer Folienindizes auswählen.

### Wie kann ich den Titel und den Inhalt auf der Zusammenfassungs-Zoomfolie ausblenden?

 Du kannst den ... benutzen`IsHidden` Eigenschaft der SmartArt-Knoten, um den Titel und den Inhalt auf der Zusammenfassungs-Zoomfolie auszublenden.