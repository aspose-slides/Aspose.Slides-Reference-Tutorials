---
title: Miniaturansicht aus Folie generieren
linktitle: Miniaturansicht aus Folie generieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Miniaturbilder aus PowerPoint-Folien generieren. Schritt-für-Schritt-Anleitung mit Quellcode. Verbessern Sie das Benutzererlebnis mit Folienvorschauen.
type: docs
weight: 11
url: /de/net/slide-thumbnail-generation/generate-thumbnail-from-slide/
---

Haben Sie sich jemals gefragt, wie Sie Miniaturbilder aus Folien in Ihren PowerPoint-Präsentationen erstellen können? Die Erstellung von Miniaturansichten ist eine wertvolle Funktion, wenn Sie eine schnelle Vorschau Ihrer Folien bereitstellen möchten, ohne die gesamte Präsentation anzeigen zu müssen. In diesem Artikel führen wir Sie durch den Prozess der Generierung von Miniaturansichten aus Folien mithilfe der Aspose.Slides-API für .NET. Egal, ob Sie Entwickler oder neugieriger Lernender sind, diese Schritt-für-Schritt-Anleitung hilft Ihnen dabei, die Leistungsfähigkeit von Aspose.Slides zu nutzen, um Ihre Anwendungen zu verbessern.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine andere .NET-Entwicklungsumgebung.
- Grundlegendes Verständnis von C# und .NET Framework.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einführung in die Miniaturbildgenerierung

Bei der Erstellung von Miniaturansichten werden kleinere Versionen von Bildern erstellt, um eine schnelle visuelle Vorschau zu ermöglichen. Im Rahmen von PowerPoint-Präsentationen können Benutzer so einen Blick auf den Folieninhalt werfen, ohne die gesamte Präsentation öffnen zu müssen.

## Einrichten Ihres Projekts

1. Erstellen Sie ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.Slides for .NET-Bibliothek hinzu.

## Laden einer PowerPoint-Präsentation

Laden Sie zunächst die PowerPoint-Präsentation, die die Folien enthält, aus denen Sie Miniaturansichten erstellen möchten.

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("your-presentation.pptx");
```

## Miniaturansichten erstellen

Lassen Sie uns nun Miniaturansichten für die Folien in der Präsentation erstellen.

```csharp
// Durchlaufen Sie jede Folie und erstellen Sie eine Miniaturansicht
foreach (var slide in presentation.Slides)
{
    // Erzeugen Sie das Miniaturbild
    var thumbnail = slide.GetThumbnail();
    
    // Weiterverarbeitung oder Anzeige
}
```

## Anpassen der Darstellung der Miniaturansichten

Sie können das Erscheinungsbild der Miniaturansichten Ihren Anforderungen entsprechend anpassen. Dazu gehört das Anpassen der Größe, Hintergrundfarbe und mehr.

```csharp
// Passen Sie die Miniaturbildeinstellungen an
var options = new ThumbnailOptions
{
    Size = new Size(320, 240),
    BackgroundColor = Color.White
};

// Erstellen Sie Miniaturansichten mit benutzerdefinierten Einstellungen
foreach (var slide in presentation.Slides)
{
    var thumbnail = slide.GetThumbnail(options);
    // ...
}
```

## Miniaturansichten speichern

Nachdem Sie die Miniaturansichten erstellt und angepasst haben, möchten Sie sie möglicherweise an einem bestimmten Ort speichern.

```csharp
foreach (var slide in presentation.Slides)
{
    var thumbnail = slide.GetThumbnail(options);
    
    // Speichern Sie die Miniaturansicht
    var thumbnailPath = $"thumbnail_slide_{slide.SlideNumber}.png";
    thumbnail.Save(thumbnailPath, ImageFormat.Png);
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mithilfe der Aspose.Slides-API für .NET Miniaturansichten aus Folien generiert. Sie haben gelernt, wie Sie Ihr Projekt einrichten, eine Präsentation laden, Miniaturansichten erstellen, deren Erscheinungsbild anpassen und sie an einem gewünschten Ort speichern. Durch die Integration der Miniaturbildgenerierung in Ihre Anwendungen können Sie das Benutzererlebnis verbessern und die Inhaltsvorschau optimieren.

## FAQs

### Wie kann ich die Größe der generierten Miniaturansichten ändern?

 Sie können die Größe der Miniaturansichten ändern, indem Sie anpassen`Size` Eigentum in der`ThumbnailOptions` Klasse.

### Kann ich Miniaturansichten nur für bestimmte Folien erstellen?

Ja, Sie können Miniaturansichten für bestimmte Folien erstellen, indem Sie diese Folien in der Präsentation durchlaufen.

### Ist es möglich, die Hintergrundfarbe der Miniaturansichten zu ändern?

 Absolut! Sie können die Hintergrundfarbe ändern, indem Sie festlegen`BackgroundColor` Eigentum in der`ThumbnailOptions` Klasse.

### Sind die generierten Miniaturansichten von hoher Qualität?

Ja, die Qualität der generierten Miniaturansichten ist ausgezeichnet und gewährleistet eine klare und genaue Darstellung des Folieninhalts.

### Wo finde ich weitere Informationen zu Aspose.Slides für .NET?

 Ausführlichere Dokumentation und Beispiele finden Sie unter[Aspose.Slides API-Referenz](https://reference.aspose.com/slides/net/).