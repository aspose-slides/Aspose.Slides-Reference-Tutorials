---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Videos aus PowerPoint-Folien extrahieren. Diese Schritt-für-Schritt-Anleitung vereinfacht den Vorgang."
"linktitle": "Video aus Folie extrahieren"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "So extrahieren Sie Videos aus Folien mit Aspose.Slides für .NET"
"url": "/de/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# So extrahieren Sie Videos aus Folien mit Aspose.Slides für .NET


Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die Ihnen die Arbeit mit PowerPoint-Präsentationen in einer .NET-Umgebung ermöglicht. Eine der nützlichen Funktionen ist die Möglichkeit, Videos aus Folien zu extrahieren. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Slides für .NET ein Video aus einer PowerPoint-Folie extrahieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Slides für .NET: Sie benötigen Aspose.Slides für .NET. Sie erhalten es von der [Webseite](https://purchase.aspose.com/buy).

- Eine PowerPoint-Präsentation: Bereiten Sie eine PowerPoint-Präsentation (z. B. Video.pptx) vor, die das Video enthält, das Sie extrahieren möchten.

## Namespaces importieren

Sie müssen die erforderlichen Namespaces importieren, um mit Aspose.Slides für .NET zu arbeiten. So geht's:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Lassen Sie uns nun den Vorgang des Extrahierens eines Videos aus einer Folie in mehrere Schritte unterteilen.

## Schritt 1: Dokumentverzeichnis festlegen

```csharp
string dataDir = "Your Document Directory";
```

Ersetzen `"Your Document Directory"` durch den Pfad zum Verzeichnis, in dem sich Ihre PowerPoint-Präsentation befindet.

## Schritt 2: Laden Sie die Präsentation

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Dieser Code initialisiert ein Präsentationsobjekt, das Ihre PowerPoint-Präsentationsdatei darstellt.

## Schritt 3: Durch Folien und Formen iterieren

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Hier durchlaufen wir jede Folie in der Präsentation und iterieren dann durch die Formen in der ersten Folie (und nehmen bei Bedarf Änderungen vor).

## Schritt 4: Überprüfen Sie, ob die Form ein Videobild ist

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

In diesem Schritt wird überprüft, ob es sich bei der Form auf der Folie um ein Videobild handelt.

## Schritt 5: Videodaten extrahieren

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Dieser Code extrahiert Informationen über das Video, einschließlich Inhaltstyp und Binärdaten.

## Schritt 6: Speichern Sie das Video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Schließlich speichert dieser Schritt das Video in einer neuen Datei im angegebenen Verzeichnis.

Sobald Sie diese Schritte abgeschlossen haben, haben Sie mit Aspose.Slides für .NET erfolgreich ein Video aus einer PowerPoint-Folie extrahiert.

## Abschluss

Aspose.Slides für .NET vereinfacht die Arbeit mit PowerPoint-Präsentationen und ermöglicht Ihnen das einfache Extrahieren von Videos aus Folien. Mit dieser Schritt-für-Schritt-Anleitung und der Aspose.Slides-Bibliothek können Sie Ihre .NET-Anwendungen mit leistungsstarken PowerPoint-Funktionen erweitern.

## Häufig gestellte Fragen (FAQs)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine Bibliothek, die es .NET-Anwendungen ermöglicht, mit PowerPoint-Präsentationen zu arbeiten, einschließlich der Erstellung, Bearbeitung und Extraktion von Inhalten.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
Die Dokumentation finden Sie [Hier](https://reference.aspose.com/slides/net/).

### Ist Aspose.Slides für .NET als kostenlose Testversion verfügbar?
Ja, Sie können eine kostenlose Testversion erhalten von [Hier](https://releases.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
Sie können eine temporäre Lizenz anfordern bei [dieser Link](https://purchase.aspose.com/temporary-license/).

### Wo erhalte ich Support für Aspose.Slides für .NET?
Unterstützung finden Sie auf der [Aspose.Slides-Forum](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}