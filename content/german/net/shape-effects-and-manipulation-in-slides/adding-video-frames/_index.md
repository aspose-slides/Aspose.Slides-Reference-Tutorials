---
title: Hinzufügen von Videobildern zu Präsentationsfolien mit Aspose.Slides
linktitle: Hinzufügen von Videobildern zu Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationen durch das Hinzufügen von Videobildern mit Aspose.Slides für .NET verbessern. Erstellen Sie nahtlos ansprechende und interaktive Inhalte.
type: docs
weight: 19
url: /de/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Einführung in Aspose.Slides und Videointegration

Aspose.Slides ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren. Durch die Integration von Videobildern in Ihre Folien können Sie Ihre Präsentationen aufwerten und sie dynamischer und ansprechender gestalten.

## Voraussetzungen für die Einbindung von Videos

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine beliebige bevorzugte .NET-Entwicklungsumgebung
- Aspose.Slides für .NET-Bibliothek installiert
- Eine PowerPoint-Präsentation (PPTX), in der Sie Videobilder hinzufügen möchten

## Einrichten Ihrer Entwicklungsumgebung

1. Öffnen Sie Visual Studio und erstellen Sie ein neues .NET-Projekt.
2.  Installieren Sie das Aspose.Slides NuGet-Paket:`Install-Package Aspose.Slides`.

## Laden einer Präsentation und Zugriff auf Folien

Laden Sie zunächst Ihre PowerPoint-Präsentation mit Aspose.Slides:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using Presentation presentation = new Presentation("your-presentation.pptx");

// Greifen Sie auf Folien zu
ISlideCollection slides = presentation.Slides;
```

## Hinzufügen von Videodateien zur Präsentation

1. Platzieren Sie Ihre Videodateien in einem Ordner innerhalb Ihres Projekts.
2. Fügen Sie in Ihrem Code Verweise auf diese Dateien hinzu:

```csharp
// Videodateien hinzufügen
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Platzieren von Videobildern auf Folien

Durchlaufen Sie die Folien und fügen Sie Videobilder hinzu:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Anpassen der Videobildeigenschaften

Sie können Videobildeigenschaften wie Position, Größe und Stil anpassen:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Umgang mit Wiedergabeoptionen

 Steuern Sie die Videowiedergabe mit`VideoPlayModePreset` Aufzählung:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Speichern und Exportieren der geänderten Präsentation

Speichern Sie Ihre Präsentation, nachdem Sie Videobilder hinzugefügt haben:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Abschluss

Durch die Integration von Videobildern in Ihre Präsentationsfolien mit Aspose.Slides wird die visuelle Wirkung Ihrer Inhalte verbessert. Sie haben gelernt, wie Sie Videos nahtlos integrieren, Videobildeigenschaften anpassen und Wiedergabeoptionen steuern. Beginnen Sie mit der Erstellung dynamischer und ansprechender Präsentationen, die Ihr Publikum fesseln.

## FAQs

### Wie füge ich mehrere Videos zu einer einzelnen Folie hinzu?

Durchlaufen Sie Ihre Videodateien und fügen Sie mithilfe des bereitgestellten Codes Videobilder zur gewünschten Folie hinzu.

### Kann ich die Einstellungen für die Videowiedergabe steuern?

 Ja, Sie können das verwenden`VideoPlayModePreset` Aufzählung zum Festlegen von Wiedergabeoptionen wie der automatischen Wiedergabe.

### Welche Videoformate werden unterstützt?

Aspose.Slides unterstützt verschiedene Videoformate, darunter MP4, AVI, WMV und mehr.

### Ist es möglich, Videos programmgesteuert in C# hinzuzufügen?

Absolut, Aspose.Slides für .NET bietet eine benutzerfreundliche API zum programmgesteuerten Hinzufügen von Videos zu Folien mit C#.

### Kann ich das Erscheinungsbild des Videobilds ändern?

Ja, Sie können die Position, Größe und andere visuelle Eigenschaften des Videorahmens entsprechend Ihren Anforderungen anpassen.