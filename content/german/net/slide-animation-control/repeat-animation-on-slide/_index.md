---
title: Wiederholen Sie die Animation auf der Folie
linktitle: Wiederholen Sie die Animation auf der Folie
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Animationen auf einer Folie mit Aspose.Slides für .NET wiederholen. Diese Schritt-für-Schritt-Anleitung bietet Quellcode und klare Anweisungen zum programmgesteuerten Hinzufügen faszinierender Animationen zu PowerPoint-Präsentationen.
type: docs
weight: 12
url: /de/net/slide-animation-control/repeat-animation-on-slide/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine robuste Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen mithilfe des .NET-Frameworks zu erstellen, zu bearbeiten und zu konvertieren. Es bietet eine breite Palette von Funktionen zum Arbeiten mit Folien, Formen, Text, Bildern, Animationen und mehr.

## Einrichten Ihrer Entwicklungsumgebung

Bevor wir beginnen, müssen Sie Ihre Entwicklungsumgebung einrichten. Folge diesen Schritten:

1. Laden Sie Visual Studio herunter und installieren Sie es[Visual Studio-Downloads](https://visualstudio.microsoft.com/downloads/).
2. Erstellen Sie in Visual Studio ein neues .NET-Projekt (z. B. Konsolenanwendung).

## Laden einer PowerPoint-Präsentation

Um zu beginnen, benötigen Sie eine PowerPoint-Präsentation, mit der Sie arbeiten können. Stellen Sie sicher, dass Sie eine PowerPoint-Datei bereit haben.

```csharp
using Aspose.Slides;

// Laden Sie die PowerPoint-Präsentation
using var presentation = new Presentation("presentation.pptx");
```

## Auf Animationen zugreifen und diese ändern

Nachdem wir nun unsere Präsentation geladen haben, können wir auf die Animationen einer bestimmten Folie zugreifen und diese ändern. Nehmen wir für dieses Beispiel an, dass wir die Animationen auf Folie Nummer 2 wiederholen möchten.

```csharp
// Zugriff auf die Folie nach Index (0-basiert)
var slideIndex = 1;
var slide = presentation.Slides[slideIndex];

// Greifen Sie auf die Animationen der Folie zu
var animations = slide.Timeline.MainSequence;
```

## Wiederholte Animationen auf einer Folie

Um Animationen zu wiederholen, klonen wir die Animationen und fügen sie der Folie erneut hinzu. Dadurch entsteht ein Schleifeneffekt. So können Sie dies erreichen:

```csharp
// Klonen Sie Animationen und fügen Sie sie erneut hinzu
var clonedAnimations = animations.CloneSequence();
animations.AddSequence(clonedAnimations);
```

## Testen und Exportieren der geänderten Präsentation

Nachdem Sie die Animationen geändert haben, ist es an der Zeit, die Präsentation zu testen und zu exportieren. Sie können es in verschiedene Formate wie PPTX, PDF oder Bilder exportieren.

```csharp
// Speichern Sie die geänderte Präsentation
presentation.Save("modified_presentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In dieser Anleitung haben wir untersucht, wie Sie Animationen auf einer Folie mit Aspose.Slides für .NET wiederholen. Wir begannen mit der Einführung der Bibliothek und dem Einrichten der Entwicklungsumgebung. Dann haben wir eine PowerPoint-Präsentation geladen, auf Animationen zugegriffen und diese geändert und schließlich die Funktion zur Wiederholung von Animationen implementiert. Aspose.Slides für .NET ermöglicht Entwicklern die programmatische Erstellung dynamischer und ansprechender Präsentationen.

## FAQs

### Wie kann ich Aspose.Slides für .NET herunterladen?

 Sie können Aspose.Slides für .NET von der Release-Seite herunterladen:[Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net/)

### Kann ich bestimmte Animationen anstelle aller Animationen auf einer Folie wiederholen?

 Ja, Sie können bestimmte Animationen selektiv wiederholen, indem Sie sie mithilfe ihres Index innerhalb des Ziels ansprechen`MainSequence`.

### Ist Aspose.Slides für .NET mit verschiedenen PowerPoint-Formaten kompatibel?

Ja, Aspose.Slides für .NET unterstützt verschiedene PowerPoint-Formate, einschließlich PPT, PPTX und mehr.

### Kann ich mit Aspose.Slides für .NET benutzerdefinierte Animationen erstellen?

Absolut! Aspose.Slides für .NET bietet umfassende APIs zum Erstellen und Anpassen von Animationen entsprechend Ihren Anforderungen.

### Gibt es eine Testversion für Aspose.Slides für .NET?

Ja, Sie können Aspose.Slides für .NET ausprobieren, indem Sie die kostenlose Testversion von der Website herunterladen.