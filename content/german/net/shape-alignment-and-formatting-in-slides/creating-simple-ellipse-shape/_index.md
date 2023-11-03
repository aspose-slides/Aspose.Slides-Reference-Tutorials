---
title: Erstellen einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET eine einfache Ellipsenform in Präsentationsfolien erstellen. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Anweisungen zum Hinzufügen, Anpassen und Speichern von Ellipsenformen.
type: docs
weight: 11
url: /de/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Einführung in die Erstellung einer einfachen Ellipsenform in Präsentationsfolien

Wenn Sie Ihre Präsentationsfolien durch das Hinzufügen optisch ansprechender Formen verbessern möchten, bietet Aspose.Slides für .NET eine leistungsstarke Lösung, um dies zu erreichen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Erstellung einer einfachen Ellipsenform in Ihren Präsentationsfolien mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine andere .NET-Entwicklungsumgebung installiert.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten Ihres Projekts

1. Erstellen Sie ein neues Visual Studio-Projekt oder öffnen Sie ein vorhandenes.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides for .NET-Bibliothek hinzu.

## Erstellen einer Präsentation

Erstellen wir zunächst eine neue Präsentation, in der wir unsere Ellipsenform hinzufügen.

```csharp
using Aspose.Slides;

// Erstellen Sie eine neue Präsentation
Presentation presentation = new Presentation();
```

## Hinzufügen einer Ellipsenform

Nachdem wir nun unsere Präsentation fertig haben, fügen wir einer Folie eine Ellipsenform hinzu.

```csharp
// Greifen Sie auf die erste Folie der Präsentation zu
ISlide slide = presentation.Slides[0];

// Definieren Sie die Abmessungen und die Position der Ellipse
float x = 100;   // X-Koordinate
float y = 100;   // Y-Koordinate
float width = 200;  // Breite
float height = 100; // Höhe

// Fügen Sie der Folie die Ellipsenform hinzu
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Anpassen der Ellipse

Sie können das Erscheinungsbild der Ellipsenform mithilfe verschiedener Eigenschaften anpassen.

```csharp
// Legen Sie die Füllfarbe der Ellipse fest
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

//Legen Sie die Umrissfarbe und -breite fest
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Fügen Sie der Ellipse einen Textrahmen hinzu
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Speichern der Präsentation

Nachdem Sie die Ellipsenform hinzugefügt und angepasst haben, ist es an der Zeit, die Präsentation zu speichern.

```csharp
// Speichern Sie die Präsentation
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine einfache Ellipsenform in Ihren Präsentationsfolien erstellt. In diesem Leitfaden wird der Prozess des Einrichtens Ihres Projekts, des Erstellens einer Präsentation, des Hinzufügens einer Ellipsenform, des Anpassens des Erscheinungsbilds und des Speicherns der endgültigen Präsentation behandelt.

## FAQs

### Wie kann ich die Position der Ellipsenform ändern?

 Sie können die ändern`x` Und`y` Geben Sie beim Hinzufügen der Ellipsenform Koordinaten ein, um deren Position auf der Folie anzupassen.

### Kann ich die Farbe des Ellipsenumrisses ändern?

 Ja, Sie können die Umrissfarbe mit festlegen`LineFormat.FillFormat.SolidFillColor.Color` Eigentum.

### Ist es möglich, Text innerhalb der Ellipse hinzuzufügen?

 Absolut! Mit können Sie der Ellipsenform Text hinzufügen`TextFrame.Text` Eigentum.

### Welche anderen Formen kann ich mit Aspose.Slides für .NET erstellen?

Aspose.Slides für .NET unterstützt verschiedene Formen, darunter Rechtecke, Linien, Pfeile und mehr.

### Wo finde ich weitere Informationen zu Aspose.Slides für .NET?

Ausführliche Dokumentation und Beispiele finden Sie im[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).