---
title: Konvertieren Sie eine HTML-Präsentation mit eingebetteten Bildern
linktitle: Konvertieren Sie eine HTML-Präsentation mit eingebetteten Bildern
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Konvertieren Sie HTML-Präsentationen mit eingebetteten Bildern mühelos mit Aspose.Slides für .NET. Erstellen, anpassen und speichern Sie PowerPoint-Dateien nahtlos.
type: docs
weight: 11
url: /de/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---
## Einführung in die Konvertierung von HTML-Präsentationen mit eingebetteten Bildern 

In dieser Anleitung werden wir den Prozess der Konvertierung einer HTML-Präsentation mit eingebetteten Bildern in das PowerPoint-Präsentationsformat (PPTX) mithilfe von Aspose.Slides für .NET Schritt für Schritt durchführen. Aspose.Slides ist eine leistungsstarke Bibliothek, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. 

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:
- Visual Studio oder eine andere .NET-Entwicklungsumgebung installiert.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://downloads.aspose.com/slides/net).
- Grundkenntnisse in C#- und .NET-Entwicklung.

## Schritte

1. Erstellen Sie ein neues C#-Projekt:
   Öffnen Sie Ihr Visual Studio und erstellen Sie ein neues C#-Projekt.

2. Installieren Sie Aspose.Slides für .NET:
   Installieren Sie die Aspose.Slides für .NET-Bibliothek in Ihrem Projekt mit NuGet Package Manager oder indem Sie einen Verweis auf die heruntergeladene DLL hinzufügen.

3. Beziehen Sie die erforderlichen Namespaces ein:
   Fügen Sie in Ihre Codedatei die erforderlichen Namespaces ein:
   ```csharp
   using Aspose.Slides;
   using Aspose.Slides.Export;
   using System.IO;
   ```

4. HTML-Inhalt laden:
   Laden Sie den HTML-Inhalt der Präsentation in eine Zeichenfolge. Sie können den HTML-Code aus einer Datei oder einer Webquelle abrufen.
   ```csharp
   string htmlContent = File.ReadAllText("path_to_your_html_file.html");
   ```

5. Erstellen Sie eine neue Präsentation:
    Erstellen Sie eine neue Instanz von`Presentation` Klasse.
   ```csharp
   using Presentation presentation = new Presentation();
   ```

6. Fügen Sie Folien mit HTML-Inhalt hinzu:
   Fügen Sie der Präsentation Folien hinzu und legen Sie den HTML-Inhalt für jede Folie fest.
   ```csharp
   ISlideCollection slides = presentation.Slides;

   // Erstellen Sie eine Folie
   ISlide slide = slides.AddEmptySlide();

   // Fügen Sie der Folie HTML-Inhalte hinzu
   IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
   textShape.TextFrame.Text = htmlContent;
   ```

7. Speichern Sie die Präsentation:
   Speichern Sie die Präsentation im PPTX-Format.
   ```csharp
   presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
   ```

8. Führen Sie die Anwendung aus:
   Erstellen Sie Ihre Anwendung und führen Sie sie aus. Die HTML-Präsentation mit eingebetteten Bildern wird in eine PowerPoint-Präsentation konvertiert.

## Beispielcode

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using System.IO;

namespace HTMLToPPTConversion
{
    class Program
    {
        static void Main(string[] args)
        {
            // Laden Sie HTML-Inhalte aus einer Datei
            string htmlContent = File.ReadAllText("path_to_your_html_file.html");

            // Erstellen Sie eine neue Präsentation
            using Presentation presentation = new Presentation();

            // Fügen Sie eine Folie mit HTML-Inhalt hinzu
            ISlide slide = presentation.Slides.AddEmptySlide();
            IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
            textShape.TextFrame.Text = htmlContent;

            // Speichern Sie die Präsentation im PPTX-Format
            presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Abschluss

Das Konvertieren von HTML-Präsentationen mit eingebetteten Bildern in PowerPoint wird mit Aspose.Slides für .NET zum Kinderspiel. Diese Bibliothek rationalisiert den Prozess und bietet umfangreiche Tools für die präzise Verwaltung der Konvertierung.

## FAQs

### Wie kann ich externe Bilder in die HTML-Präsentation einbinden?

Wenn Ihre HTML-Präsentation externe Bilder enthält, stellen Sie sicher, dass Sie die richtigen URLs für die Bilder angeben. Aspose.Slides übernimmt automatisch die Einbettung dieser Bilder, wenn Sie den HTML-Inhalt zur Folie hinzufügen.

### Kann ich das Erscheinungsbild der konvertierten Folien anpassen?

Ja, Sie können das Erscheinungsbild der konvertierten Folien mithilfe verschiedener Eigenschaften und Methoden anpassen, die von der Aspose.Slides-Bibliothek bereitgestellt werden. Sie können Schriftarten, Farben, Stile und mehr ändern.

### Wo finde ich die vollständige Dokumentation für Aspose.Slides für .NET?

Sie finden die vollständige Dokumentation und API-Referenz für Aspose.Slides für .NET[Hier](https://reference.aspose.com/slides/net).

### Wo kann ich die neueste Version von Aspose.Slides für .NET herunterladen?

 Sie können die neueste Version von Aspose.Slides für .NET von der Aspose-Release-Seite herunterladen:[Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net).