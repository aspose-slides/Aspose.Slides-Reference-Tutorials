---
title: Erstellen einer Miniaturansicht mit Grenzen für die Form in Aspose.Slides
linktitle: Erstellen einer Miniaturansicht mit Grenzen für die Form in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Miniaturansichten für Formen in PowerPoint-Präsentationen erstellen. Diese Schritt-für-Schritt-Anleitung enthält Beispiele für Quellcode und behandelt das Laden von Präsentationen, den Zugriff auf Formen, das Definieren von Miniaturbildgrenzen, das Rendern, Speichern und mehr.
type: docs
weight: 10
url: /de/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---

## Einführung in das Erstellen von Miniaturansichten mit Grenzen für die Form

Wenn es um die Arbeit mit Präsentationen geht, bietet Aspose.Slides für .NET eine Reihe leistungsstarker Tools, mit denen Entwickler verschiedene Aspekte von Folien, Formen und Inhalten bearbeiten können. Eine häufige Aufgabe besteht darin, Miniaturansichten mit bestimmten Grenzen für Formen innerhalb von Folien zu erstellen. Diese Schritt-für-Schritt-Anleitung führt Sie durch den Prozess, wie Sie dies mit Aspose.Slides für .NET erreichen. Lass uns eintauchen!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine kompatible IDE
- Aspose.Slides für .NET-Bibliothek
- Grundkenntnisse in C# und .NET

## Einrichten des Projekts

1. Erstellen Sie ein neues C#-Projekt in Ihrer IDE.
2.  Laden Sie die Aspose.Slides für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/slides/net/).
3. Fügen Sie Verweise auf die Aspose.Slides-DLLs in Ihrem Projekt hinzu.

## Laden einer Präsentation

Zunächst müssen Sie die PowerPoint-Präsentation laden, die die Folie mit der Form enthält, für die Sie eine Miniaturansicht erstellen möchten. So können Sie es machen:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Auf Formen zugreifen

Sobald die Präsentation geladen ist, müssen Sie auf die spezifische Form zugreifen, für die Sie eine Miniaturansicht erstellen möchten. Sie können dies tun, indem Sie die Folien und Formen durchlaufen:

```csharp
// Holen Sie sich die erste Folie
ISlide slide = presentation.Slides[0];

// Ermitteln Sie die Form anhand ihres Index (0-basiert).
IShape shape = slide.Shapes[0];
```

## Miniaturansichten mit Grenzen erstellen

Jetzt kommt der Teil, in dem Sie eine Miniaturansicht der Form mit bestimmten Grenzen erstellen. Dies umfasst einige Schritte:

1. Erstellen Sie eine Bitmap mit den gewünschten Abmessungen.
2.  Rendern Sie die Form mithilfe von auf die Bitmap`RenderToGraphics` Methode.

So wird es gemacht:

```csharp
using System.Drawing;

// Definieren Sie die Grenzen für die Miniaturansicht
Rectangle bounds = new Rectangle(0, 0, 200, 150);

// Erstellen Sie eine Bitmap mit den angegebenen Grenzen
using Bitmap thumbnailBitmap = new Bitmap(bounds.Width, bounds.Height);

// Rendern Sie die Form auf der Bitmap
using Graphics graphics = Graphics.FromImage(thumbnailBitmap);
shape.RenderToGraphics(graphics, bounds);
```

## Speichern der Ausgabe

Nachdem Sie das Miniaturbild erstellt haben, möchten Sie es möglicherweise in einer Datei speichern. Sie können dies mit dem folgenden Code tun:

```csharp
// Speichern Sie die Miniaturansicht in einer Datei
thumbnailBitmap.Save("thumbnail.png", ImageFormat.Png);
```

## Abschluss

In diesem Leitfaden haben wir den Prozess der Erstellung einer Miniaturansicht mit bestimmten Grenzen für eine Form in einer PowerPoint-Präsentation mit Aspose.Slides für .NET durchlaufen. Diese Bibliothek bietet eine nahtlose Möglichkeit, Präsentationen programmgesteuert zu bearbeiten und Aufgaben auszuführen, die Ihren Arbeitsablauf optimieren.

## FAQs

### Wie kann ich Aspose.Slides für .NET installieren?

 Um Aspose.Slides für .NET zu installieren, können Sie die Bibliothek von der Release-Seite herunterladen:[Hier](https://releases.aspose.com/slides/net/).

### Kann ich Miniaturansichten für mehrere Formen erstellen?

Ja, Sie können die Formen auf einer Folie durchlaufen und den Miniaturbild-Erstellungsprozess für jede Form einzeln wiederholen.

### Welche Bildformate werden zum Speichern von Miniaturansichten unterstützt?

Aspose.Slides für .NET unterstützt verschiedene Bildformate zum Speichern von Miniaturansichten, darunter PNG, JPEG, GIF und BMP.

### Ist Aspose.Slides sowohl für Desktop- als auch für Webanwendungen geeignet?

Ja, Aspose.Slides für .NET ist vielseitig und kann sowohl in Desktop- als auch in Webanwendungen verwendet werden, um programmgesteuert mit PowerPoint-Präsentationen zu arbeiten.

### Wie kann ich mehr über Aspose.Slides für .NET erfahren?

Ausführlichere Informationen, Tutorials und Dokumentation finden Sie unter[Aspose.Slides für .NET-Referenz](https://reference.aspose.com/slides/net/).