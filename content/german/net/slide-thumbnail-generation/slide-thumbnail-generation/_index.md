---
title: Folien-Thumbnail-Generierung in Aspose.Slides
linktitle: Folien-Thumbnail-Generierung in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie Miniaturansichten von Folien in Aspose.Slides für .NET mit einer Schritt-für-Schritt-Anleitung und Codebeispielen. Passen Sie das Erscheinungsbild an und speichern Sie Miniaturansichten. Verbessern Sie die Präsentationsvorschau.
type: docs
weight: 10
url: /de/net/slide-thumbnail-generation/slide-thumbnail-generation/
---

Im Bereich der Präsentationsmanipulation ist Aspose.Slides ein leistungsstarkes Tool, mit dem Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, ändern und verwalten können. Eine der wesentlichen Funktionen, die es bietet, ist die Erstellung von Folien-Miniaturansichten. Dieser Artikel befasst sich mit dem Prozess der Generierung von Folienminiaturansichten mit Aspose.Slides für .NET und bietet eine Schritt-für-Schritt-Anleitung und Codebeispiele, um Entwicklern die Fähigkeiten zu vermitteln, diese Funktionalität nahtlos zu implementieren.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass Folgendes vorhanden ist:

- Visual Studio mit installiertem .NET Framework.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einführung in die Erstellung von Folien-Miniaturansichten

Miniaturansichten von Folien spielen in Präsentationen eine zentrale Rolle und bieten eine schnelle Vorschau auf den Inhalt jeder Folie. Aspose.Slides vereinfacht diesen Prozess, indem es einen unkomplizierten Mechanismus zum programmgesteuerten Generieren dieser Miniaturansichten bereitstellt.

## Einrichten des Projekts

1. Erstellen Sie ein neues Projekt in Visual Studio.
2. Fügen Sie Verweise auf die erforderlichen Aspose.Slides-Assemblys hinzu.

## Laden einer Präsentation

Laden Sie die PowerPoint-Präsentation mit dem folgenden Code:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
Presentation presentation = new Presentation("path_to_presentation.pptx");
```

## Erzeugen von Folien-Miniaturansichten

Miniaturansichten für alle Folien in der Präsentation erstellen:

```csharp
// ThumbnailOptions initialisieren
ThumbnailOptions thumbnailOptions = new ThumbnailOptions();

// Erstellen Sie Miniaturansichten für alle Folien
foreach (ISlide slide in presentation.Slides)
{
    using (MemoryStream thumbnailStream = new MemoryStream())
    {
        slide.GetThumbnail(thumbnailStream, thumbnailOptions);
        // Verarbeiten oder speichern Sie die Miniaturansicht nach Bedarf
    }
}
```

## Anpassen der Darstellung der Miniaturansichten

 Sie können das Erscheinungsbild der Miniaturansicht anpassen, indem Sie die ändern`thumbnailOptions`. Sie können beispielsweise Abmessungen, Hintergrundfarbe und mehr festlegen.

```csharp
thumbnailOptions.SlideSize = SlideSizeType.Screen;
thumbnailOptions.BackgroundColor = Color.White;
```

## Miniaturansichten speichern

Speichern Sie die generierten Miniaturansichten auf der Festplatte:

```csharp
using (FileStream fileStream = new FileStream("slide_thumbnail.png", FileMode.Create))
{
    thumbnailStream.Seek(0, SeekOrigin.Begin);
    thumbnailStream.CopyTo(fileStream);
}
```

## Abschluss

Mit Aspose.Slides für .NET können Entwickler mühelos Miniaturansichten von Folien erstellen und so die Präsentationsvorschau verbessern. Durch Befolgen der in diesem Artikel beschriebenen Schritte haben Sie das Wissen erworben, die Erstellung von Folienminiaturansichten in Ihre Anwendungen zu integrieren.

## FAQs

### Wie kann ich die Abmessungen der generierten Miniaturansichten anpassen?

 Um die Abmessungen der generierten Miniaturansichten anzupassen, ändern Sie die`thumbnailOptions.SlideSize` Eigentum. Sie können aus verschiedenen vordefinierten Größen wählen, z`SlideSizeType.Screen`, `SlideSizeType.A4Paper`, usw.

### Kann ich die Hintergrundfarbe von Miniaturansichten ändern?

 Sicherlich! Verstelle die`thumbnailOptions.BackgroundColor` -Eigenschaft, um die gewünschte Hintergrundfarbe für die generierten Miniaturansichten festzulegen.

### Ist es möglich, Miniaturansichten nur für bestimmte Folien zu erstellen?

Ja, Sie können Miniaturansichten für bestimmte Folien erstellen, indem Sie die gewünschten Folien anstelle aller Folien in der Präsentation durchlaufen.

### Sind die generierten Miniaturansichten von hoher Qualität?

 Standardmäßig sind die generierten Miniaturansichten von guter Qualität und für Vorschauzwecke geeignet. Sie können Parameter wie anpassen`thumbnailOptions.Quality`um die Qualität der Miniaturansichten weiter zu kontrollieren.

### Wie wirkt sich die Generierung von Folienminiaturansichten auf die Leistung aus?

Die Erstellung von Folienminiaturansichten ist auf Leistung optimiert. Die Erstellung von Miniaturansichten für eine große Anzahl von Folien oder die Verwendung hoher Qualitätseinstellungen kann sich jedoch auf die Verarbeitungszeit auswirken.

Die Implementierung der Miniaturbildgenerierung für Folien mit Aspose.Slides eröffnet eine Welt voller Möglichkeiten zur Verbesserung Ihrer präsentationsbezogenen Anwendungen. Ob für schnelle Vorschauen oder benutzerdefinierte Anzeigen – diese Funktion bietet wertvolle Funktionen, die Entwickler effektiv nutzen können. Also legen Sie los, integrieren Sie die Erstellung von Folien-Miniaturansichten in Ihre Projekte und verbessern Sie das Benutzererlebnis Ihrer Präsentationsanwendungen!