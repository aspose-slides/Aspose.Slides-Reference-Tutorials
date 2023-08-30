---
title: Hinzufügen von Videobildern aus einer Webquelle in Präsentationsfolien mit Aspose.Slides
linktitle: Hinzufügen von Videobildern aus einer Webquelle in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationsfolien verbessern, indem Sie mit Aspose.Slides für .NET Videobilder aus Webquellen hinzufügen. Erstellen Sie ansprechende Multimedia-Präsentationen mit Schritt-für-Schritt-Anleitungen und Quellcode-Beispielen.
type: docs
weight: 20
url: /de/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

In der heutigen dynamischen Welt haben sich Präsentationen über statische Folien hinaus entwickelt. Die Integration multimedialer Elemente wie Videos in Ihre Präsentation kann das Engagement deutlich steigern und Informationen effektiver vermitteln. Mit Aspose.Slides für .NET können Entwickler Videobilder aus Webquellen nahtlos in ihre Präsentationsfolien integrieren. Dieser Leitfaden führt Sie Schritt für Schritt durch den Prozess und demonstriert die Leistungsfähigkeit von Aspose.Slides.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine kompatible IDE installiert
- Aspose.Slides für .NET-Bibliothek
- Grundkenntnisse der C#-Programmierung

## Schritt 1: Einrichten Ihres Projekts

Erstellen Sie zunächst ein neues Projekt in Ihrer bevorzugten IDE und fügen Sie die Bibliothek Aspose.Slides für .NET hinzu. Sie können die Bibliothek entweder von der Website herunterladen oder mit dem NuGet Package Manager installieren.

## Schritt 2: Hinzufügen eines Videobilds zu einer Folie

1.  Erstellen Sie eine neue Instanz von`Presentation` mit Aspose.Slides.
2.  Fügen Sie der Präsentation mithilfe von eine neue Folie hinzu`Slides` Sammlung.
3. Definieren Sie die Position und Abmessungen des Videorahmens auf der Folie.
4.  Benutzen Sie die`EmbedWebVideoFrame` Methode zum Hinzufügen des Videobilds zur Folie.

```csharp
// Erstellen Sie eine neue Präsentation
using (Presentation presentation = new Presentation())
{
    // Fügen Sie eine neue Folie hinzu
    ISlide slide = presentation.Slides.AddEmptySlide();

    // Definieren Sie Position und Abmessungen des Videobilds
    int x = 100; // X-Koordinate
    int y = 100; // Y-Koordinate
    int width = 480; // Breite
    int height = 270; // Höhe

    // Fügen Sie der Folie einen Videorahmen hinzu
    slide.EmbedWebVideoFrame(x, y, width, height, new Uri("https://example.com/video.mp4"));
    
    // Speichern Sie die Präsentation
    presentation.Save("output.pptx", SaveFormat.Pptx);
}
```

## Schritt 3: Anpassen der Videowiedergabe

Aspose.Slides bietet verschiedene Optionen zum Anpassen der Videowiedergabe in Ihrer Präsentation. Sie können Aspekte wie automatische Wiedergabe, Schleife und Stummschaltungseinstellungen für das eingebettete Video steuern.

```csharp
// Holen Sie sich den Videorahmen auf die Folie
IVideoFrame videoFrame = (IVideoFrame)slide.Shapes[0];

//Aktivieren Sie Autoplay
videoFrame.PlayMode = VideoPlayModePreset.Auto;

// Schleife aktivieren
videoFrame.PlayLoopMode = VideoPlayLoopMode.Loop;

// Schalten Sie das Video stumm
videoFrame.Volume = AudioVolumeMode.Mute;
```

## FAQs

### Wie kann ich die Quelle des eingebetteten Videos ändern?

 Um die Quelle des eingebetteten Videos zu ändern, aktualisieren Sie einfach den im bereitgestellten URI`EmbedWebVideoFrame` Methode, um auf die neue Webquelle zu verweisen.

### Kann ich das Erscheinungsbild des Videorahmens anpassen?

Ja, Sie können das Erscheinungsbild des Videobilds mithilfe von Eigenschaften wie Position, Größe und Formformatierung anpassen.

### Kann man steuern, wann das Video abgespielt wird?

 Absolut! Sie können die Startzeit der Wiedergabe steuern, indem Sie die anpassen`videoFrame.StartTime` Eigentum.

### Welche Videoformate werden zum Einbetten unterstützt?

Aspose.Slides unterstützt das Einbetten von Videobildern aus verschiedenen Webquellen, einschließlich beliebter Formate wie MP4, YouTube-Links und mehr.

### Wie kann ich die plattformübergreifende Kompatibilität des eingebetteten Videos sicherstellen?

Die eingebetteten Videobilder werden in modernen Versionen von Microsoft PowerPoint und anderer kompatibler Präsentationssoftware unterstützt.

## Abschluss

Durch die Integration von Videobildern aus Webquellen in Ihre Präsentationsfolien mit Aspose.Slides für .NET können Sie Ihre Präsentationen in ansprechende Multimedia-Erlebnisse verwandeln. Diese Schritt-für-Schritt-Anleitung zeigt, wie Sie Videobilder nahtlos einbetten, die Wiedergabe anpassen und häufige Fragen beantworten. Werten Sie Ihre Präsentationen mit dynamischen Videoinhalten auf und fesseln Sie Ihr Publikum wie nie zuvor!