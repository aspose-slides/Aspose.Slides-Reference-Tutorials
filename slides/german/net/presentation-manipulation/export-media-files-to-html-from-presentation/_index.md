---
"description": "Optimieren Sie die Freigabe Ihrer Präsentationen mit Aspose.Slides für .NET! In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie Mediendateien aus Ihrer Präsentation in HTML exportieren."
"linktitle": "Exportieren von Mediendateien aus Präsentationen in HTML"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Exportieren von Mediendateien aus Präsentationen in HTML"
"url": "/de/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Exportieren von Mediendateien aus Präsentationen in HTML


In diesem Tutorial führen wir Sie durch den Export von Mediendateien aus einer Präsentation in HTML mit Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke API, mit der Sie PowerPoint-Präsentationen programmgesteuert bearbeiten können. Nach Abschluss dieser Anleitung können Sie Ihre Präsentationen problemlos ins HTML-Format konvertieren. Los geht‘s!

## 1. Einleitung

PowerPoint-Präsentationen enthalten häufig Multimedia-Elemente wie Videos. Aus Web-Gründen müssen diese Präsentationen möglicherweise ins HTML-Format exportiert werden. Aspose.Slides für .NET bietet eine komfortable Möglichkeit, diese Aufgabe programmgesteuert zu erledigen.

## 2. Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Slides für .NET: Sie sollten die Bibliothek Aspose.Slides für .NET installiert haben. Sie können sie hier herunterladen: [Hier](https://releases.aspose.com/slides/net/).

## 3. Laden einer Präsentation

Laden Sie zunächst die PowerPoint-Präsentation, die Sie in HTML konvertieren möchten. Geben Sie außerdem das Ausgabeverzeichnis an, in dem die HTML-Datei gespeichert werden soll. Hier ist der Code zum Laden einer Präsentation:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Laden einer Präsentation
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Ihr Code hier
}
```

## 4. HTML-Optionen einrichten

Richten wir nun die HTML-Optionen für die Konvertierung ein. Wir konfigurieren einen HTML-Controller, einen HTML-Formatierer und ein Folienbildformat. Dieser Code stellt sicher, dass Ihre HTML-Datei die notwendigen Komponenten für die Anzeige multimedialer Elemente enthält.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Festlegen von HTML-Optionen
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Speichern der HTML-Datei

Nachdem Sie die HTML-Optionen konfiguriert haben, können Sie die HTML-Datei speichern. Die `Save` Methode des Präsentationsobjekts generiert die HTML-Datei mit eingebetteten Multimedia-Elementen.

```csharp
// Speichern der Datei
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Fazit

Herzlichen Glückwunsch! Sie haben Mediendateien aus einer PowerPoint-Präsentation mit Aspose.Slides für .NET erfolgreich in HTML exportiert. So können Sie Ihre Präsentationen problemlos online teilen und sicherstellen, dass Multimedia-Elemente korrekt angezeigt werden.

## 7. FAQs

### F1: Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
A1: Aspose.Slides für .NET ist eine kommerzielle Bibliothek, aber Sie können eine kostenlose Testversion von [Hier](https://releases.aspose.com/) um es auszuprobieren.

### F2: Kann ich die HTML-Ausgabe weiter anpassen?
A2: Ja, Sie können die HTML-Ausgabe anpassen, indem Sie die HTML-Optionen im Code ändern.

### F3: Unterstützt Aspose.Slides für .NET andere Exportformate?
A3: Ja, Aspose.Slides für .NET unterstützt verschiedene Exportformate, darunter PDF, Bildformate und mehr.

### F4: Wo erhalte ich Support für Aspose.Slides für .NET?
A4: Sie können Unterstützung finden und Fragen in den Aspose-Foren stellen [Hier](https://forum.aspose.com/).

### F5: Wie erwerbe ich eine Lizenz für Aspose.Slides für .NET?
A5: Sie können eine Lizenz erwerben bei [dieser Link](https://purchase.aspose.com/buy).

Nach Abschluss dieses Tutorials können Sie Mediendateien aus PowerPoint-Präsentationen mit Aspose.Slides für .NET in HTML exportieren. Viel Spaß beim Teilen Ihrer multimedialen Präsentationen online!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}