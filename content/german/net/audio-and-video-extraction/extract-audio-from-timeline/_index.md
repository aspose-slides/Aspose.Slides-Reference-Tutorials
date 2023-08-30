---
title: Extrahieren Sie Audio aus der Timeline
linktitle: Extrahieren Sie Audio aus der Timeline
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Audio aus PowerPoint-Zeitleisten extrahieren. Eine Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 13
url: /de/net/audio-and-video-extraction/extract-audio-from-timeline/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen zu erstellen, zu bearbeiten, zu konvertieren und zu manipulieren, ohne dass Microsoft Office installiert sein muss. Es unterstützt eine Vielzahl von Funktionen, einschließlich des Zugriffs auf Präsentationselemente wie Folien, Formen, Text, Bilder und sogar Audio. In diesem Leitfaden konzentrieren wir uns auf das Extrahieren von Audio aus der Zeitleiste einer Präsentation.

## Die Zeitleiste in PowerPoint-Präsentationen verstehen

Die Zeitleiste in einer PowerPoint-Präsentation stellt die Abfolge von Ereignissen, Animationen und Multimedia-Elementen dar. Dazu gehören Audiospuren, die mit den Folien synchronisiert sind. Mit Aspose.Slides können Sie programmgesteuert auf diese Audiospuren zugreifen und diese extrahieren.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine kompatible .NET-Entwicklungsumgebung
-  Aspose.Slides-Bibliothek. Sie können es herunterladen unter[Hier](https://downloads.aspose.com/slides/net)

## Schritt 1: Installation der Aspose.Slides-Bibliothek

1. Laden Sie die Aspose.Slides-Bibliothek über den bereitgestellten Link herunter.
2. Installieren Sie die Bibliothek in Ihrem .NET-Projekt, indem Sie den Verweis auf die Aspose.Slides-Assembly hinzufügen.

## Schritt 2: Laden der Präsentation

Um Audio aus einer Präsentation zu extrahieren, müssen Sie zunächst die PowerPoint-Datei laden. So können Sie es machen:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("presentation.pptx");
```

## Schritt 3: Zugriff auf die Timeline

Nach dem Laden der Präsentation können Sie auf die Timeline und die zugehörigen Audiospuren zugreifen:

```csharp
// Greifen Sie auf die erste Folie zu
var slide = presentation.Slides[0];

//Greifen Sie auf die Zeitleiste der Folie zu
var timeline = slide.Timeline;
```

## Schritt 4: Audio aus der Timeline extrahieren

Da Sie nun Zugriff auf die Timeline haben, können Sie das Audio extrahieren:

```csharp
foreach (var timeLineShape in timeline.Shapes)
{
    if (timeLineShape.MediaType == MediaType.Audio)
    {
        var audio = (IAudioFrame)timeLineShape;
        // Extrahieren Sie hier den Audioverarbeitungscode
    }
}
```

## Schritt 5: Speichern des extrahierten Audios

Sobald Sie das Audio extrahiert haben, können Sie es im gewünschten Format speichern:

```csharp
audio.AudioData.WriteToFile("extracted_audio.mp3");
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für .NET Audio aus der Zeitleiste einer PowerPoint-Präsentation extrahieren. Wir haben die Schritte vom Laden der Präsentation über den Zugriff auf die Timeline bis hin zum Extrahieren des Audios behandelt. Aspose.Slides vereinfacht diesen Prozess und erleichtert die programmgesteuerte Arbeit mit verschiedenen Multimedia-Elementen in PowerPoint-Präsentationen.

## FAQs

### Wie kann ich die Aspose.Slides-Bibliothek installieren?

 Sie können die Aspose.Slides-Bibliothek unter herunterladen[Hier](https://downloads.aspose.com/slides/net). Fügen Sie nach dem Herunterladen einen Verweis auf die Aspose.Slides-Assembly in Ihrem .NET-Projekt hinzu.

### Kann ich Audio von jeder Folie in der Präsentation extrahieren?


Ja, Sie können mit Aspose.Slides für .NET Audio aus der Zeitleiste jeder Folie in der Präsentation extrahieren.

### In welchen Formaten kann ich das extrahierte Audio speichern?

Mit Aspose.Slides können Sie das extrahierte Audio in verschiedenen Formaten wie MP3, WAV und mehr speichern.

### Muss Microsoft Office installiert sein, um Aspose.Slides verwenden zu können?

Nein, Microsoft Office muss nicht installiert sein. Aspose.Slides für .NET bietet alle notwendigen Funktionen, um programmgesteuert mit PowerPoint-Präsentationen zu arbeiten.

### Ist Aspose.Slides für kommerzielle Projekte geeignet?

Ja, Aspose.Slides eignet sich sowohl für persönliche als auch für kommerzielle Projekte. Es bietet eine breite Palette von Funktionen zur programmgesteuerten Verwaltung von PowerPoint-Präsentationen.