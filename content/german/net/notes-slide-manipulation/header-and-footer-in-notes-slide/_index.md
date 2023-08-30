---
title: Verwalten Sie Kopf- und Fußzeilen in der Notizenfolie
linktitle: Verwalten Sie Kopf- und Fußzeilen in der Notizenfolie
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Kopf- und Fußzeilen in Notizfolien anpassen. Diese Schritt-für-Schritt-Anleitung enthält Beispiele für Quellcode und behandelt den Zugriff auf, die Änderung und das Styling von Elementen.
type: docs
weight: 11
url: /de/net/notes-slide-manipulation/header-and-footer-in-notes-slide/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit Microsoft PowerPoint-Dateien zu arbeiten. Es ermöglicht die Bearbeitung und Erstellung von Präsentationen, Folien, Formen und verschiedenen darin enthaltenen Elementen. In dieser Anleitung konzentrieren wir uns auf die Verwaltung von Kopf- und Fußzeilenelementen in der Notizenfolie mit Aspose.Slides für .NET.

## Hinzufügen einer Notizenfolie zu einer Präsentation

 Stellen Sie zunächst sicher, dass Aspose.Slides für .NET installiert ist. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/slides/net/). Erstellen Sie nach der Installation ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        // Laden Sie die Präsentation
        using (Presentation presentation = new Presentation())
        {
            // Fügen Sie eine neue Folie hinzu
            ISlide slide = presentation.Slides.AddEmptySlide();
            
            // Notizenfolie zur aktuellen Folie hinzufügen
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            
            // Hier finden Sie Ihren Code zum Bearbeiten von Kopf- und Fußzeilenelementen
            
            // Speichern Sie die geänderte Präsentation
            presentation.Save("output.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Auf Kopf- und Fußzeilenelemente zugreifen

Sobald Sie Ihrer Präsentation eine Notizenfolie hinzugefügt haben, können Sie zur Anpassung auf die Kopf- und Fußzeilenelemente zugreifen. Die Kopf- und Fußzeilenelemente können Text, Datum und Foliennummern enthalten. Verwenden Sie den folgenden Code, um auf diese Elemente zuzugreifen:

```csharp
INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

// Auf Kopftext zugreifen
string headerText = headerFooterManager.HeaderText;

// Zugriff auf Fußzeilentext
string footerText = headerFooterManager.FooterText;

// Zugriff auf Datum und Uhrzeit
bool isDateTimeVisible = headerFooterManager.IsDateTimeVisible;

//Zugriff auf die Foliennummer
bool isSlideNumberVisible = headerFooterManager.IsSlideNumberVisible;
```

## Kopf- und Fußzeilentext ändern

Sie können den Kopf- und Fußzeilentext problemlos ändern, um Kontext oder andere notwendige Informationen bereitzustellen. Verwenden Sie den folgenden Code, um den Kopf- und Fußzeilentext zu aktualisieren:

```csharp
headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");
```

## Kopf- und Fußzeilenelemente gestalten

Mit Aspose.Slides für .NET können Sie außerdem die Kopf- und Fußzeilenelemente entsprechend dem Design Ihrer Präsentation gestalten. Sie können Schriftart, Größe, Farbe und Ausrichtung ändern. Hier ist ein Beispiel für die Gestaltung der Elemente:

```csharp
ITextStyle textStyle = presentation.Slides[0].TextStyle;
textStyle.FontHeight = 14;
textStyle.FontColor.Color = Color.Blue;
textStyle.Alignment = TextAlignment.Center;

headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);
```

## Datum und Foliennummer aktualisieren

Um das Datum und die Foliennummer automatisch zu aktualisieren, verwenden Sie den folgenden Code:

```csharp
headerFooterManager.SetDateTimeVisible(true);
headerFooterManager.SetSlideNumberVisible(true);
```

## Speichern der geänderten Präsentation

Nachdem Sie die Kopf- und Fußzeilenelemente in der Notizenfolie angepasst haben, können Sie die geänderte Präsentation in einer Datei speichern:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode

Hier ist der vollständige Quellcode zum Verwalten von Kopf- und Fußzeilenelementen in der Notizenfolie mit Aspose.Slides für .NET:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        using (Presentation presentation = new Presentation())
        {
            ISlide slide = presentation.Slides.AddEmptySlide();
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

            // Passen Sie Kopf- und Fußzeilenelemente an
            headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
            headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");

            ITextStyle textStyle = presentation.Slides[0].TextStyle;
            textStyle.FontHeight = 14;
            textStyle.FontColor.Color = Color.Blue;
            textStyle.Alignment = TextAlignment.Center;

            headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
            headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);

            headerFooterManager.SetDateTimeVisible(true);
            headerFooterManager.SetSlideNumberVisible(true);

            // Speichern Sie die geänderte Präsentation
            presentation.Save("modified.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Aspose.Slides für .NET verwenden, um Kopf- und Fußzeilenelemente in der Notizenfolie einer Präsentation zu verwalten. Sie haben gelernt, wie Sie eine Notizenfolie hinzufügen, auf Kopf- und Fußzeilenelemente zugreifen, Text und Stilelemente ändern sowie Datum und Foliennummern aktualisieren. Diese leistungsstarke Bibliothek ermöglicht eine nahtlose Anpassung und verbessert das gesamte Präsentationserlebnis.

## FAQs

### Wie kann ich auf die Kopf- und Fußzeilenelemente in der Notizenfolie zugreifen?

 Um auf Kopf- und Fußzeilenelemente zuzugreifen, können Sie die verwenden`INotesHeaderFooterManager` Schnittstelle, die von Aspose.Slides für .NET bereitgestellt wird.

### Kann ich den Kopf- und Fußzeilentext formatieren?

 Ja, Sie können den Kopf- und Fußzeilentext mit formatieren`SetTextStyle` Methode. Sie können Schriftgröße, Farbe, Ausrichtung und andere Eigenschaften anpassen.

### Wie aktualisiere ich das Datum und die Foliennummer automatisch?

 Du kannst den ... benutzen`SetDateTimeVisible` Und`SetSlideNumberVisible` Methoden zur automatischen Anzeige des Datums und der Foliennummer in der Kopf- und Fußzeile.

### Ist Aspose.Slides für .NET mit PowerPoint-Dateien kompatibel?

Ja, Aspose.Slides für .NET ist vollständig mit PowerPoint-Dateien kompatibel, sodass Sie Präsentationen programmgesteuert bearbeiten und erstellen können.

### Wo finde ich den vollständigen Quellcode für die Anpassung von Kopf- und Fußzeilen?

Das vollständige Quellcode-Beispiel finden Sie in diesem Handbuch. Den Codeausschnitt finden Sie im Abschnitt „Vollständiger Quellcode“.