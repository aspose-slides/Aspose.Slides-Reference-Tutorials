---
title: So extrahieren Sie Videos aus einer Folie mit Aspose.Slides für .NET
linktitle: Video aus Folie extrahieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Videos aus PowerPoint-Folien extrahieren. Diese Schritt-für-Schritt-Anleitung vereinfacht den Prozess für Sie.
type: docs
weight: 14
url: /de/net/audio-and-video-extraction/extract-video/
---

Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die Ihnen die Arbeit mit PowerPoint-Präsentationen in einer .NET-Umgebung ermöglicht. Eine der nützlichen Funktionen ist die Möglichkeit, Videos aus Folien zu extrahieren. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Slides für .NET ein Video aus einer PowerPoint-Folie extrahieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Sie müssen Aspose.Slides für .NET installiert haben. Sie können es bei der erhalten[Webseite](https://purchase.aspose.com/buy).

- Eine PowerPoint-Präsentation: Bereiten Sie eine PowerPoint-Präsentation (z. B. Video.pptx) vor, die das Video enthält, das Sie extrahieren möchten.

## Namespaces importieren

Sie müssen die erforderlichen Namespaces importieren, um mit Aspose.Slides für .NET arbeiten zu können. So können Sie es machen:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Lassen Sie uns nun den Prozess des Extrahierens eines Videos aus einer Folie in mehrere Schritte unterteilen.

## Schritt 1: Legen Sie das Dokumentverzeichnis fest

```csharp
string dataDir = "Your Document Directory";
```

 Ersetzen`"Your Document Directory"` mit dem Pfad zu dem Verzeichnis, in dem sich Ihre PowerPoint-Präsentation befindet.

## Schritt 2: Laden Sie die Präsentation

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Dieser Code initialisiert ein Präsentationsobjekt, das Ihre PowerPoint-Präsentationsdatei darstellt.

## Schritt 3: Durchlaufen Sie Folien und Formen

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Hier durchlaufen wir jede Folie in der Präsentation und durchlaufen dann die Formen in der ersten Folie (ändern sie nach Bedarf).

## Schritt 4: Überprüfen Sie, ob es sich bei der Form um einen Videorahmen handelt

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

In diesem Schritt wird überprüft, ob die Form auf der Folie ein Videobild ist.

## Schritt 5: Videodaten extrahieren

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Dieser Code extrahiert Informationen über das Video, einschließlich seines Inhaltstyps und der Binärdaten.

## Schritt 6: Speichern Sie das Video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Schließlich speichert dieser Schritt das Video in einer neuen Datei im angegebenen Verzeichnis.

Sobald Sie diese Schritte ausgeführt haben, haben Sie mit Aspose.Slides für .NET erfolgreich ein Video aus einer PowerPoint-Folie extrahiert.

## Abschluss

Aspose.Slides für .NET vereinfacht die Arbeit mit PowerPoint-Präsentationen und ermöglicht Ihnen die einfache Ausführung von Aufgaben wie dem Extrahieren von Videos aus Folien. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen und die Aspose.Slides-Bibliothek nutzen, können Sie Ihre .NET-Anwendungen mit leistungsstarken PowerPoint-Funktionen erweitern.

## Häufig gestellte Fragen (FAQs)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine Bibliothek, die es .NET-Anwendungen ermöglicht, mit PowerPoint-Präsentationen zu arbeiten, einschließlich der Erstellung, Bearbeitung und Extrahierung von Inhalten.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation finden Sie hier[Hier](https://reference.aspose.com/slides/net/).

### Ist Aspose.Slides für .NET als kostenlose Testversion verfügbar?
 Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
 Eine temporäre Lizenz können Sie bei anfordern[dieser Link](https://purchase.aspose.com/temporary-license/).

### Wo erhalte ich Unterstützung für Aspose.Slides für .NET?
 Unterstützung finden Sie auf der[Aspose.Slides-Forum](https://forum.aspose.com/).