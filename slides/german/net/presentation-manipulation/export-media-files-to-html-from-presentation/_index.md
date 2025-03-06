---
title: Exportieren von Mediendateien aus Präsentationen in HTML
linktitle: Exportieren von Mediendateien aus Präsentationen in HTML
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Optimieren Sie das Teilen Ihrer Präsentation mit Aspose.Slides für .NET! In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie Mediendateien aus Ihrer Präsentation in HTML exportieren.
weight: 15
url: /de/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


In diesem Tutorial führen wir Sie durch den Prozess des Exportierens von Mediendateien aus einer Präsentation in HTML mithilfe von Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke API, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. Am Ende dieses Leitfadens können Sie Ihre Präsentationen problemlos in das HTML-Format konvertieren. Also, legen wir los!

## 1. Einleitung

PowerPoint-Präsentationen enthalten häufig Multimedia-Elemente wie Videos und Sie müssen diese Präsentationen möglicherweise in das HTML-Format exportieren, um Webkompatibilität zu gewährleisten. Aspose.Slides für .NET bietet eine praktische Möglichkeit, diese Aufgabe programmgesteuert auszuführen.

## 2. Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Sie sollten die Bibliothek Aspose.Slides für .NET installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/net/).

## 3. Laden einer Präsentation

Zu Beginn müssen Sie die PowerPoint-Präsentation laden, die Sie in HTML konvertieren möchten. Sie müssen auch das Ausgabeverzeichnis angeben, in dem die HTML-Datei gespeichert wird. Hier ist der Code zum Laden einer Präsentation:

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

Jetzt richten wir die HTML-Optionen für die Konvertierung ein. Wir konfigurieren einen HTML-Controller, einen HTML-Formatierer und ein Folienbildformat. Dieser Code stellt sicher, dass Ihre HTML-Datei die erforderlichen Komponenten zum Anzeigen von Multimediaelementen enthält.

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

 Nachdem Sie die HTML-Optionen konfiguriert haben, können Sie die HTML-Datei speichern.`Save` Methode des Präsentationsobjekts generiert die HTML-Datei mit eingebetteten Multimedia-Elementen.

```csharp
// Speichern der Datei
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Fazit

Herzlichen Glückwunsch! Sie haben erfolgreich Mediendateien aus einer PowerPoint-Präsentation mit Aspose.Slides für .NET in HTML exportiert. So können Sie Ihre Präsentationen problemlos online teilen und sicherstellen, dass Multimedia-Elemente richtig angezeigt werden.

## 7. Häufig gestellte Fragen

### F1: Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
 A1: Aspose.Slides für .NET ist eine kommerzielle Bibliothek, aber Sie können eine kostenlose Testversion erhalten von[Hier](https://releases.aspose.com/) um es auszuprobieren.

### F2: Kann ich die HTML-Ausgabe weiter anpassen?
A2: Ja, Sie können die HTML-Ausgabe anpassen, indem Sie die HTML-Optionen im Code ändern.

### F3: Unterstützt Aspose.Slides für .NET andere Exportformate?
A3: Ja, Aspose.Slides für .NET unterstützt verschiedene Exportformate, darunter PDF, Bildformate und mehr.

### F4: Wo erhalte ich Support für Aspose.Slides für .NET?
 A4: Sie können Unterstützung finden und Fragen in den Aspose-Foren stellen[Hier](https://forum.aspose.com/).

### F5: Wie erwerbe ich eine Lizenz für Aspose.Slides für .NET?
 A5: Sie können eine Lizenz erwerben bei[dieser Link](https://purchase.aspose.com/buy).

Nachdem Sie dieses Tutorial abgeschlossen haben, können Sie Mediendateien aus PowerPoint-Präsentationen mit Aspose.Slides für .NET in HTML exportieren. Viel Spaß beim Teilen Ihrer multimedialen Präsentationen online!
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
