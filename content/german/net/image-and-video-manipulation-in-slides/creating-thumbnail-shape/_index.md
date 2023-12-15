---
title: Erstellen einer Miniaturansicht für eine Form in Aspose.Slides
linktitle: Erstellen einer Miniaturansicht für eine Form in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Miniaturansichten für Formen in PowerPoint-Präsentationen erstellen. Diese Schritt-für-Schritt-Anleitung bietet praktische Codebeispiele, vom Laden von Präsentationen bis zum Erstellen und Speichern von Miniaturansichten.
type: docs
weight: 14
url: /de/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

## Einführung

Aspose.Slides für .NET ist eine funktionsreiche Bibliothek, die Entwicklern die nahtlose Arbeit mit PowerPoint-Präsentationen ermöglicht. Eine häufige Anforderung ist die Erstellung von Miniaturansichten für bestimmte Formen in Folien. Dies kann besonders nützlich sein, wenn Sie in Ihrer Anwendung eine schnelle Vorschau oder Darstellung einer Form bereitstellen möchten.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine andere geeignete .NET-Entwicklungsumgebung.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Installation

1. Laden Sie die Aspose.Slides für .NET-Bibliothek über den bereitgestellten Link herunter.
2. Installieren Sie die Bibliothek in Ihrem .NET-Projekt, indem Sie einen Verweis auf die heruntergeladene DLL hinzufügen.

## Laden einer Präsentation

Beginnen wir mit dem Laden einer PowerPoint-Präsentation mit Aspose.Slides. Der folgende Code zeigt, wie eine Präsentation aus einer Datei geladen wird:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("sample.pptx");
```

 Ersetzen`"sample.pptx"` mit dem tatsächlichen Pfad Ihrer PowerPoint-Präsentation.

## Auf Formen zugreifen

Sobald die Präsentation geladen ist, können Sie auf die Formen in jeder Folie zugreifen. In diesem Beispiel konzentrieren wir uns auf die Erstellung einer Miniaturansicht für eine bestimmte Form auf einer bestimmten Folie. So können Sie auf eine Form zugreifen:

```csharp
// Zugriff auf eine Folie nach Index (0-basiert)
var slide = presentation.Slides[0];

// Auf eine Form über den Index zugreifen (0-basiert)
var shape = slide.Shapes[0];
```

Ändern Sie die Folien- und Formindizes entsprechend der Struktur Ihrer Präsentation.

## Miniaturansichten erstellen

Jetzt kommt der spannende Teil – das Erstellen einer Miniaturansicht für die ausgewählte Form. Mit Aspose.Slides können Sie dies erreichen, indem Sie die nutzen`GetThumbnail` Methode. So können Sie eine Miniaturansicht für eine Form erstellen:

```csharp
// Definieren Sie die Miniaturbildabmessungen
int thumbnailWidth = 200;
int thumbnailHeight = 150;

// Erstellen Sie eine Miniaturansicht für die Form
var thumbnail = shape.GetThumbnail(thumbnailWidth, thumbnailHeight);
```

 Verstelle die`thumbnailWidth` Und`thumbnailHeight` Variablen, um die gewünschten Abmessungen für Ihr Miniaturbild festzulegen.

## Miniaturansichten speichern

Nachdem Sie das Miniaturbild erstellt haben, möchten Sie es möglicherweise als Bilddatei speichern. So können Sie die Miniaturansicht als PNG-Bild speichern:

```csharp
// Speichern Sie die Miniaturansicht als Bild
thumbnail.Save("shape_thumbnail.png", ImageFormat.Png);
```

Passen Sie den Dateinamen und das Format an Ihre Anforderungen an.

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie mit Aspose.Slides für .NET Miniaturansichten für Formen in PowerPoint-Präsentationen erstellen. Sie haben gelernt, wie Sie eine Präsentation laden, auf Formen zugreifen, Miniaturansichten erstellen und diese als Bilddateien speichern. Diese Funktionalität kann das Benutzererlebnis in Anwendungen, die PowerPoint-Präsentationen beinhalten, erheblich verbessern.

## FAQs

### Wie kann ich unterschiedliche Miniaturbildabmessungen angeben?

 Sie können die anpassen`thumbnailWidth` Und`thumbnailHeight` Variablen im Code, um die Abmessungen anzugeben, die Sie für die generierte Miniaturansicht benötigen.

### Kann ich Miniaturansichten für mehrere Formen gleichzeitig erstellen?

Ja, Sie können alle Formen auf einer Folie durchlaufen und mithilfe einer Schleife Miniaturansichten für jede Form erstellen.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Formaten kompatibel?

Ja, Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPTX, PPT und mehr.

### Kann ich das Erscheinungsbild des generierten Miniaturbilds anpassen?

 Während`GetThumbnail` Die Methode bietet eine schnelle Möglichkeit zum Generieren von Miniaturansichten. Sie können das Miniaturbild mithilfe von Standardbildverarbeitungsbibliotheken in .NET weiter bearbeiten.

### Ist Aspose.Slides für andere PowerPoint-bezogene Aufgaben geeignet?

Absolut, Aspose.Slides bietet eine breite Palette von Funktionen für die Arbeit mit PowerPoint-Präsentationen, darunter das Erstellen, Bearbeiten, Konvertieren und Rendern von Folien.