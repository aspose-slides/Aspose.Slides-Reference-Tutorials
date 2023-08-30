---
title: Hinzufügen eingebetteter Videobilder in Präsentationsfolien mithilfe von Aspose.Slides
linktitle: Hinzufügen eingebetteter Videobilder in Präsentationsfolien mithilfe von Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationsfolien verbessern, indem Sie mit Aspose.Slides für .NET eingebettete Videobilder hinzufügen. Befolgen Sie diese Schritt-für-Schritt-Anleitung mit vollständigem Quellcode, um Videos nahtlos zu integrieren, die Wiedergabe anzupassen und fesselnde Präsentationen zu erstellen.
type: docs
weight: 19
url: /de/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine vielseitige und funktionsreiche Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine breite Palette an Funktionen, darunter das Erstellen, Bearbeiten, Konvertieren und Bearbeiten von Präsentationen. In diesem Leitfaden konzentrieren wir uns auf den Prozess der Einbettung von Videobildern in Präsentationsfolien.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio (oder eine andere .NET-Entwicklungsumgebung)
- Grundkenntnisse der Programmiersprache C#
- Aspose.Slides für .NET-Bibliothek

## Aspose.Slides für .NET installieren

Um zu beginnen, müssen Sie die Aspose.Slides für .NET-Bibliothek installieren. Sie können die Bibliothek von der Website herunterladen oder einen Paketmanager wie NuGet verwenden. So können Sie es mit NuGet installieren:

```csharp
Install-Package Aspose.Slides
```

## Erstellen einer neuen Präsentation

Beginnen wir mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides. Hier ist ein einfacher Codeausschnitt zum Erstellen einer Präsentation:

```csharp
using Aspose.Slides;

// Erstellen Sie eine neue Präsentation
Presentation presentation = new Presentation();
```

## Hinzufügen einer Folie

Als Nächstes fügen wir der Präsentation eine neue Folie hinzu. Folien werden beginnend bei Null indiziert. So können Sie eine Folie hinzufügen:

```csharp
//Fügen Sie der Präsentation eine neue Folie hinzu
ISlide slide = presentation.Slides.AddEmptySlide(SlideLayout.Blank);
```

## Einbetten eines Videos

Jetzt kommt der spannende Teil – das Einbetten eines Videos in die Folie. Sie benötigen den Pfad oder die URL der Videodatei, um fortfahren zu können. So können Sie ein Video in die Folie einbetten:

```csharp
// Pfad zur Videodatei
string videoPath = "path_to_your_video.mp4";

// Fügen Sie das Video zur Folie hinzu
IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 480, 270, videoPath);
```

## Anpassen des Videorahmens

Sie können verschiedene Aspekte des Videobilds anpassen, z. B. seine Größe, Position und Wiedergabeoptionen. Hier ist ein Beispiel, wie Sie den Wiedergabemodus so einstellen, dass er automatisch startet:

```csharp
// Stellen Sie den Videowiedergabemodus so ein, dass er automatisch startet
videoFrame.PlayMode = VideoPlayMode.Auto;
```

## Speichern und Exportieren der Präsentation

Sobald Sie den Videorahmen hinzugefügt und nach Ihren Wünschen angepasst haben, ist es an der Zeit, die Präsentation zu speichern. Sie können es in verschiedenen Formaten speichern, beispielsweise PPTX oder PDF. So speichern Sie es als PPTX-Datei:

```csharp
// Speichern Sie die Präsentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Ihre Präsentationsfolien durch das Hinzufügen eingebetteter Videobilder mit Aspose.Slides für .NET verbessern können. Mit dieser leistungsstarken Bibliothek können Sie dynamische und ansprechende Präsentationen erstellen, die bei Ihrem Publikum einen bleibenden Eindruck hinterlassen. Wenn Sie die in diesem Leitfaden beschriebenen Schritte befolgen, können Sie Multimedia-Inhalte nahtlos in Ihre Folien integrieren und fesselnde Präsentationen erstellen.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

 Sie können Aspose.Slides für .NET mit dem NuGet-Paketmanager installieren. Führen Sie einfach den folgenden Befehl in Ihrer NuGet Package Manager-Konsole aus:`Install-Package Aspose.Slides`

### Kann ich das Erscheinungsbild des Videorahmens anpassen?

Ja, Sie können die Größe, Position und Wiedergabeoptionen des Videobilds mithilfe der von der Aspose.Slides-Bibliothek bereitgestellten Eigenschaften anpassen.

### Welche Videoformate werden zum Einbetten unterstützt?

Aspose.Slides unterstützt das Einbetten von Videos in verschiedenen Formaten, einschließlich MP4, AVI und WMV.

### Kann ich steuern, wann das Video abgespielt wird?

Absolut! Sie können den Wiedergabemodus des Videobilds je nach Ihren Vorlieben so einstellen, dass es automatisch oder manuell startet.

### Ist Aspose.Slides nur zum Hinzufügen von Videos gedacht?

Nein, Aspose.Slides bietet eine breite Palette an Funktionalitäten, die über das Hinzufügen von Videos hinausgehen. Es ermöglicht Ihnen, PowerPoint-Präsentationen programmgesteuert zu erstellen, zu bearbeiten, zu konvertieren und zu manipulieren.