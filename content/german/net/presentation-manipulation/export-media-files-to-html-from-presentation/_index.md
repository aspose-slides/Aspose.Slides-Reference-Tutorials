---
title: Exportieren Sie Mediendateien aus der Präsentation in HTML
linktitle: Exportieren Sie Mediendateien aus der Präsentation in HTML
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Optimieren Sie Ihre Präsentationsfreigabe mit Aspose.Slides für .NET! Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Mediendateien aus Ihrer Präsentation in HTML exportieren.
type: docs
weight: 15
url: /de/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

In diesem Tutorial führen wir Sie durch den Prozess des Exportierens von Mediendateien aus einer Präsentation in HTML mit Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke API, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. Am Ende dieser Anleitung werden Sie in der Lage sein, Ihre Präsentationen problemlos in das HTML-Format zu konvertieren. Also lasst uns anfangen!

## 1. Einleitung

PowerPoint-Präsentationen enthalten häufig Multimedia-Elemente wie Videos. Aus Gründen der Webkompatibilität müssen Sie diese Präsentationen möglicherweise in das HTML-Format exportieren. Aspose.Slides für .NET bietet eine praktische Möglichkeit, diese Aufgabe programmgesteuert auszuführen.

## 2. Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Sie sollten die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## 3. Laden einer Präsentation

Zunächst müssen Sie die PowerPoint-Präsentation laden, die Sie in HTML konvertieren möchten. Sie müssen außerdem das Ausgabeverzeichnis angeben, in dem die HTML-Datei gespeichert wird. Hier ist der Code zum Laden einer Präsentation:

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

Nun richten wir die HTML-Optionen für die Konvertierung ein. Wir konfigurieren einen HTML-Controller, einen HTML-Formatierer und ein Folienbildformat. Dieser Code stellt sicher, dass Ihre HTML-Datei die notwendigen Komponenten für die Anzeige von Multimedia-Elementen enthält.

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

 Nachdem Sie die HTML-Optionen konfiguriert haben, können Sie die HTML-Datei nun speichern. Der`Save` Die Methode des Präsentationsobjekts generiert die HTML-Datei mit eingebetteten Multimedia-Elementen.

```csharp
// Speichern der Datei
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Fazit

Glückwunsch! Sie haben Mediendateien aus einer PowerPoint-Präsentation mit Aspose.Slides für .NET erfolgreich in HTML exportiert. Dadurch können Sie Ihre Präsentationen ganz einfach online teilen und sicherstellen, dass Multimedia-Elemente richtig angezeigt werden.

## 7. FAQs

### F1: Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
 A1: Aspose.Slides für .NET ist eine kommerzielle Bibliothek, Sie können jedoch eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/) um es auszuprobieren.

### F2: Kann ich die HTML-Ausgabe weiter anpassen?
A2: Ja, Sie können die HTML-Ausgabe anpassen, indem Sie die HTML-Optionen im Code ändern.

### F3: Unterstützt Aspose.Slides für .NET andere Exportformate?
A3: Ja, Aspose.Slides für .NET unterstützt verschiedene Exportformate, darunter PDF, Bildformate und mehr.

### F4: Wo erhalte ich Unterstützung für Aspose.Slides für .NET?
 A4: In den Aspose-Foren finden Sie Unterstützung und können Fragen stellen[Hier](https://forum.aspose.com/).

### F5: Wie kaufe ich eine Lizenz für Aspose.Slides für .NET?
 A5: Sie können eine Lizenz erwerben bei[dieser Link](https://purchase.aspose.com/buy).

Nachdem Sie dieses Tutorial abgeschlossen haben, verfügen Sie nun über die Fähigkeiten, Mediendateien aus PowerPoint-Präsentationen mit Aspose.Slides für .NET in HTML zu exportieren. Viel Spaß beim Teilen Ihrer multimedialen Präsentationen online!