---
title: Video aus Folie extrahieren
linktitle: Video aus Folie extrahieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Meistern Sie die Videoextraktion aus PowerPoint-Folien mit Aspose.Slides für .NET. Folgen Sie unserem Leitfaden mit Codebeispielen.
type: docs
weight: 14
url: /de/net/audio-and-video-extraction/extract-video/
---

## Einführung

In der heutigen digitalen Welt sind multimediale Präsentationen zu einem wesentlichen Bestandteil der Kommunikation geworden. PowerPoint-Präsentationen enthalten oft eine Mischung aus Text, Bildern und Videos, um Informationen effektiv zu vermitteln. Es kann jedoch vorkommen, dass Sie ein Video aus einer Folie für verschiedene Zwecke extrahieren müssen, beispielsweise zum Archivieren, Teilen oder zur weiteren Bearbeitung. Hier kommt Aspose.Slides für .NET ins Spiel.

## Voraussetzungen

Bevor wir uns mit der Schritt-für-Schritt-Anleitung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Grundkenntnisse in C# und .NET Framework
- Visual Studio installiert
-  Aspose.Slides für .NET-Bibliothek (Download von[Hier](https://releases.aspose.com/slides/net)

## Schritt für Schritt Anleitung

Lassen Sie uns den Prozess des Extrahierens eines Videos aus einer Folie mit Aspose.Slides für .NET durchgehen:

### Schritt 1: Installation

1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“.
3. Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Schritt 2: Präsentation laden

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("your-presentation.pptx");
```

 Ersetzen`"your-presentation.pptx"` mit dem tatsächlichen Pfad zu Ihrer PowerPoint-Präsentationsdatei.

### Schritt 3: Video extrahieren

```csharp
// Holen Sie sich die erste Folie
var slide = presentation.Slides[0];

// Durchlaufen Sie Folienformen
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Extrahieren Sie das Video aus dem Videoframe
        var video = videoFrame.EmbeddedVideo;
        // Eine weitere Bearbeitung kann mit dem Videoobjekt erfolgen
    }
}
```

### Schritt 4: Video speichern

```csharp
// Speichern Sie das extrahierte Video
video.WriteToFile("extracted-video.mp4");
```

 Ersetzen`"extracted-video.mp4"` mit dem gewünschten Namen und Pfad für die extrahierte Videodatei.

## Abschluss

Aspose.Slides für .NET vereinfacht das Extrahieren von Videos aus PowerPoint-Präsentationen. Mit nur wenigen Codezeilen können Sie in Folien eingebettete Videos abrufen und als separate Videodateien speichern. Unabhängig davon, ob Sie Inhalte wiederverwenden oder Zusammenstellungen erstellen möchten, bietet diese Bibliothek eine nahtlose Lösung.

## FAQs

### Wie kann ich auf die Aspose.Slides-Dokumentation zugreifen?

 Weitere Informationen finden Sie in der Dokumentation zu Aspose.Slides für .NET unter[Hier](https://reference.aspose.com/slides/net/).

### Ist Aspose.Slides für andere Programmiersprachen verfügbar?

Ja, Aspose.Slides ist für mehrere Programmiersprachen verfügbar, einschließlich Java. Die entsprechenden Bibliotheken finden Sie auf der Aspose-Website.

### Kann ich Audio auf die gleiche Weise extrahieren?

Nein, das bereitgestellte Beispiel dient speziell zum Extrahieren von Videos. Um Audio zu extrahieren, müssten Sie den Code ändern, um mit Audio-Frames zu arbeiten.

### Fallen für die Nutzung von Aspose.Slides Lizenzgebühren an?

Ja, Aspose.Slides ist ein kommerzielles Produkt. Detaillierte Informationen zu Lizenzierung und Preisen finden Sie auf der Aspose-Website.

### Wie greife ich auf die Eigenschaften des extrahierten Videos zu?

 Der`EmbeddedVideo` Objekt erhalten aus dem`IVideoFrame` Bietet Zugriff auf verschiedene Eigenschaften des Videos, wie Dauer, Auflösung und mehr.