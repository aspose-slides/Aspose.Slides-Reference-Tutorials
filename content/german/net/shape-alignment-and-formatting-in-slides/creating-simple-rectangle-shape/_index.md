---
title: Erstellen einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET eine einfache Rechteckform in PowerPoint-Folien erstellen. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Anweisungen zum programmgesteuerten Hinzufügen, Anpassen und Verbessern Ihrer Präsentationen.
type: docs
weight: 12
url: /de/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine breite Palette von Funktionen zum Erstellen, Bearbeiten und Verwalten von Präsentationselementen, einschließlich Folien, Formen, Text, Bildern und mehr. In diesem Leitfaden konzentrieren wir uns auf die Erstellung einer einfachen Rechteckform innerhalb einer Präsentationsfolie mithilfe der Funktionen von Aspose.Slides für .NET.

## Einrichten der Entwicklungsumgebung

Bevor wir uns mit dem Code befassen, richten wir unsere Entwicklungsumgebung ein. Folge diesen Schritten:

1.  Laden Sie Aspose.Slides für .NET herunter: Besuchen Sie die[Download-Seite](https://releases.aspose.com/slides/net/) und wählen Sie die mit Ihrem Projekt kompatible Version aus.

2. Aspose.Slides installieren: Nach dem Herunterladen installieren Sie Aspose.Slides, indem Sie die DLL-Referenz zu Ihrem Projekt hinzufügen.

3. Erstellen Sie ein neues Projekt: Erstellen Sie ein neues .NET-Projekt mit Ihrer bevorzugten Entwicklungsumgebung (z. B. Visual Studio).

## Erstellen einer neuen Präsentation

Beginnen wir mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für .NET.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Erstellen Sie eine neue Präsentation
        Presentation presentation = new Presentation();

        // Fügen Sie der Präsentation eine leere Folie hinzu
        Slide slide = presentation.Slides.AddEmptySlide();

        // Ihr Code zum Hinzufügen der Rechteckform wird hier angezeigt

        // Speichern Sie die Präsentation
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## Hinzufügen einer Rechteckform zur Folie

Nachdem wir nun unsere Präsentationsfolie fertig haben, fügen wir ihr nun eine rechteckige Form hinzu.

```csharp
// Fügen Sie der Folie eine Rechteckform hinzu
double x = 100; // X-Koordinate der Form
double y = 100; // Y-Koordinate der Form
double width = 200; // Breite der Form
double height = 100; // Höhe der Form

slide.Shapes.AddRectangle(x, y, width, height);
```

## Anpassen der Rechteckform

Sie können verschiedene Aspekte der Rechteckform anpassen, z. B. die Füllfarbe, den Rahmenstil und mehr.

```csharp
// Holen Sie sich die hinzugefügte Form (Rechteck)
IShape rectangle = slide.Shapes[0];

// Passen Sie die Füllfarbe an
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// Rand anpassen
rectangle.LineFormat.Width = 2; // Rahmenbreite
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // Grenzstil
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // Randfarbe
```

## Speichern der Präsentation

Sobald Sie die Rechteckform hinzugefügt und angepasst haben, ist es an der Zeit, die Präsentation zu speichern.

```csharp
// Speichern Sie die Präsentation
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie mit Aspose.Slides für .NET eine einfache Rechteckform innerhalb einer Präsentationsfolie erstellen. Wir haben die grundlegenden Schritte zum Einrichten der Entwicklungsumgebung, zum Erstellen einer neuen Präsentation, zum Hinzufügen einer Rechteckform, zum Anpassen des Erscheinungsbilds und zum Speichern der endgültigen Präsentation behandelt. Mit Aspose.Slides für .NET können Sie Ihre PowerPoint-Präsentationen ganz einfach automatisieren und verbessern und so eine Ebene an Dynamik und Interaktivität hinzufügen.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

Um Aspose.Slides für .NET zu installieren, befolgen Sie diese Schritte:

1.  Besuche den[Download-Seite](https://releases.aspose.com/slides/net/).
2. Wählen Sie die mit Ihrem Projekt kompatible Version.
3. Fügen Sie die Aspose.Slides-DLL-Referenz zu Ihrem .NET-Projekt hinzu.

### Kann ich die Füllfarbe der Rechteckform anpassen?

 Ja, Sie können die Füllfarbe der Rechteckform mithilfe von anpassen`FillFormat` Eigentum. Greifen Sie einfach auf die Formen zu`FillFormat` und stellen Sie das gewünschte ein`SolidFillColor`.

### Wie speichere ich die Präsentation, nachdem ich die Rechteckform hinzugefügt habe?

Sie können die Präsentation mit speichern`Save` Methode der`Presentation` Klasse. Geben Sie den gewünschten Dateinamen und das gewünschte Speicherformat an (z. B`SaveFormat.Pptx`).

### Ist Aspose.Slides für .NET nur für rechteckige Formen geeignet?

Nein, Aspose.Slides für .NET unterstützt eine Vielzahl von Formen und Präsentationselementen. Sie können Formen wie Rechtecke, Kreise, Pfeile und mehr erstellen und bearbeiten.

### Wo finde ich weitere Dokumentation zu Aspose.Slides für .NET?

 Ausführliche Dokumentation und API-Referenzen für Aspose.Slides für .NET finden Sie auf der[Dokumentationsseite](https://reference.aspose.com/slides/net/).