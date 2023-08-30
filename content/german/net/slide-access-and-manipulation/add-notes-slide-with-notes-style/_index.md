---
title: Fügen Sie eine Notizenfolie mit stilvoller Notizenformatierung hinzu
linktitle: Fügen Sie eine Notizenfolie mit stilvoller Notizenformatierung hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen mit stilvoller Notizformatierung mit Aspose.Slides für .NET verbessern. Diese Schritt-für-Schritt-Anleitung behandelt das Hinzufügen einer Notizenfolie, das Anwenden attraktiver Formatierungen und mehr.
type: docs
weight: 14
url: /de/net/slide-access-and-manipulation/add-notes-slide-with-notes-style/
---

## Einführung in Aspose.Slides für .NET:

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine breite Palette an Funktionen, darunter das Erstellen, Lesen, Schreiben und Bearbeiten von Folien, Formen, Text, Bildern und mehr. In diesem Tutorial konzentrieren wir uns auf das Hinzufügen einer Notizenfolie und das Anwenden einer stilvollen Formatierung auf die Notizen.

## Voraussetzungen:

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine andere .NET-Entwicklungsumgebung.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten des Projekts:

1. Erstellen Sie ein neues .NET-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides for .NET-Bibliothek hinzu.

## Erstellen einer Präsentation:

Beginnen wir mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für .NET. Anschließend werden wir dieser Präsentation eine Notizfolie hinzufügen.

```csharp
using Aspose.Slides;
using System;

namespace NotesSlideTutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            // Erstellen Sie eine neue Präsentation
            Presentation presentation = new Presentation();

            // Speichern Sie die Präsentation
            presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Hinzufügen einer Notizenfolie:

Als Nächstes fügen wir der Präsentation eine Notizenfolie hinzu. Eine Notizenfolie enthält normalerweise zusätzliche Informationen oder Sprechernotizen zum Inhalt der Hauptfolie.

```csharp
// Fügen Sie nach der ersten Folie eine Notizenfolie hinzu
NotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.AddNotesSlide();

// Fügen Sie Inhalte zur Notizenfolie hinzu
notesSlide.NotesTextFrame.Text = "These are the speaker notes for the first slide.";
```

## Stilvolle Formatierung für Notizen:

Um die Notizen optisch ansprechender zu gestalten, können wir mit Aspose.Slides für .NET eine stilvolle Formatierung anwenden. Dazu gehört das Ändern der Schriftart, Farbe, Größe und anderer Formatierungsoptionen.

```csharp
// Greifen Sie auf den Textrahmen der Notizenfolie zu
ITextFrame notesTextFrame = notesSlide.NotesTextFrame;

// Wenden Sie Formatierungen auf den Text an
IParagraph paragraph = notesTextFrame.Paragraphs[0];
IPortion portion = paragraph.Portions[0];

// Ändern Sie Schriftart, Schriftgröße und Farbe
portion.PortionFormat.LatinFont = new FontData("Arial");
portion.PortionFormat.FontHeight = 14;
portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
```

## Abschluss:

In diesem Tutorial haben wir gelernt, wie man Aspose.Slides für .NET verwendet, um einer PowerPoint-Präsentation eine Notizfolie mit stilvoller Formatierung hinzuzufügen. Wir haben das Erstellen einer Präsentation, das Hinzufügen einer Notizfolie und das Anwenden von Formatierungen auf den Notizinhalt behandelt. Aspose.Slides für .NET bietet Entwicklern ein leistungsstarkes Toolkit zur programmgesteuerten Verbesserung ihrer PowerPoint-Präsentationen.

## FAQs

### Wie kann ich die Position der Notizen auf der Notizenfolie ändern?

 Sie können die Position des Notiztextrahmens mithilfe von anpassen`notesSlide.NotesTextFrame.X` Und`notesSlide.NotesTextFrame.Y` Eigenschaften.

### Kann ich der Notizenfolie Bilder hinzufügen?

 Ja, Sie können der Notizenfolie Bilder hinzufügen, indem Sie die verwenden`notesSlide.Shapes.AddPicture()` Methode.

### Ist Aspose.Slides für .NET mit verschiedenen PowerPoint-Formaten kompatibel?

Ja, Aspose.Slides für .NET unterstützt verschiedene PowerPoint-Formate, einschließlich PPTX, PPT und mehr.

### Wie kann ich Formatierungen auf bestimmte Teile des Notiztextes anwenden?

 Sie können auf Abschnitte innerhalb eines Absatzes zugreifen und mithilfe von Formatierungen anwenden`portion.PortionFormat` Eigentum.

### Wo finde ich weitere Informationen zu Aspose.Slides für .NET?

 Eine ausführliche Dokumentation und Beispiele finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).