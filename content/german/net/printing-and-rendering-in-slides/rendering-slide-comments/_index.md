---
title: Rendern von Folienkommentaren in Aspose.Slides
linktitle: Rendern von Folienkommentaren in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Folienkommentare in PowerPoint-Präsentationen mit Aspose.Slides für .NET rendern. Diese Schritt-für-Schritt-Anleitung enthält Quellcodebeispiele für den programmgesteuerten Zugriff, die Anpassung und die Anzeige von Kommentaren.
type: docs
weight: 12
url: /de/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

## Einführung

Folienkommentare bieten wertvolle Einblicke, Erklärungen und Diskussionen zu bestimmten Folien in einer Präsentation. Das programmgesteuerte Rendern dieser Kommentare kann den Überprüfungs- und Zusammenarbeitsprozess optimieren. Aspose.Slides für .NET vereinfacht diese Aufgabe, indem es einen umfassenden Satz von APIs zum Verwalten und Rendern von Folienkommentaren bereitstellt.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio ist auf Ihrem Computer installiert.
- Grundlegendes Verständnis der C#- und .NET-Entwicklung.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten des Projekts

1. Erstellen Sie ein neues C#-Projekt in Visual Studio.

2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides for .NET-Bibliothek hinzu.

## Laden einer Präsentation

Laden wir zunächst eine PowerPoint-Präsentation mit Folienkommentaren:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("presentation.pptx");
```

## Zugriff auf Folienkommentare

Als Nächstes gehen wir die Folien in der Präsentation durch und greifen auf die Kommentare zu jeder Folie zu:

```csharp
// Durchlaufen Sie die Folien
foreach (var slide in presentation.Slides)
{
    // Greifen Sie auf Folienkommentare zu
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Zugriff auf Kommentareigenschaften
        var author = comment.Author;
        var text = comment.Text;
        
        // Verarbeiten Sie den Kommentar nach Bedarf
    }
}
```

## Kommentare zu Folien rendern

Lassen Sie uns nun die Kommentare auf den Folien rendern. Wir fügen die Kommentare als Textfelder unter jeder Folie hinzu:

```csharp
foreach (var slide in presentation.Slides)
{
    // Greifen Sie auf Folienkommentare zu
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Erstellen Sie ein Textfeld für den Kommentar
        var textBox = slide.Shapes.AddTextFrame("");
        var textFrame = textBox.TextFrame;
        
        // Legen Sie Kommentareigenschaften als Text fest
        textFrame.Text = $"{comment.Author}: {comment.Text}";
        
        // Positionieren Sie das Textfeld unter der Folie
        textBox.Left = slide.SlideSize.Size.Width / 2;
        textBox.Top = slide.SlideSize.Size.Height + 20;
        
        // Passen Sie bei Bedarf das Erscheinungsbild des Textfelds an
        
        // Verarbeiten Sie den Kommentar nach Bedarf
    }
}
```

## Anpassen der Kommentardarstellung

Sie können das Erscheinungsbild der gerenderten Kommentare weiter anpassen, z. B. Schriftgröße, Farbe und Position. Dadurch können Sie die Kommentare an den Stil Ihrer Präsentation anpassen:

```csharp
// Passen Sie das Erscheinungsbild des Textfelds an
var fontHeight = 12;
var fontColor = Color.Black;
var margin = 20;

foreach (var slide in presentation.Slides)
{
    // ...
    foreach (var comment in comments)
    {
        // ...
        
        // Passen Sie das Erscheinungsbild des Textfelds an
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = fontHeight;
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FillFormat.SolidFillColor.Color = fontColor;
        
        //Passen Sie die Position des Textfelds an
        textBox.Top = slide.SlideSize.Size.Height - margin;
        margin += 30; // Erhöhen Sie den Rand für den nächsten Kommentar
    }
}
```

## Speichern der gerenderten Präsentation

Nachdem Sie die Kommentare zu den Folien gerendert haben, können Sie die geänderte Präsentation speichern:

```csharp
// Speichern Sie die geänderte Präsentation
presentation.Save("rendered_presentation.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Folienkommentare in PowerPoint-Präsentationen mit Aspose.Slides für .NET rendern. Indem Sie die oben beschriebenen Schritte befolgen, können Sie programmgesteuert auf Kommentare zugreifen und diese anzeigen und so die Zusammenarbeit und Kommunikation innerhalb Ihrer Foliendecks verbessern.

## FAQs

### Wie kann ich Aspose.Slides für .NET installieren?

 Sie können die Aspose.Slides für .NET-Bibliothek unter herunterladen[dieser Link](https://releases.aspose.com/slides/net/). Nach dem Herunterladen können Sie es als Referenz in Ihr Visual Studio-Projekt einfügen.

### Kann ich das Erscheinungsbild der gerenderten Kommentare anpassen?

Ja, Sie können das Erscheinungsbild der gerenderten Kommentare anpassen, einschließlich Schriftgröße, Farbe und Position. Dadurch können Sie die Kommentare an den Stil Ihrer Präsentation anpassen.

### Wie greife ich auf einzelne Kommentareigenschaften zu?

 Sie können über auf Kommentareigenschaften wie den Autor und den Text zugreifen`Author` Und`Text` Eigenschaften des Kommentarobjekts.

### Kann ich Kommentare als Callouts anstelle von Textfeldern rendern?

Ja, Sie können Kommentare als Beschriftungen rendern, indem Sie benutzerdefinierte Formen erstellen und ihnen Text hinzufügen. Sie müssen die Position und das Erscheinungsbild der Beschriftungen entsprechend anpassen.

### Ist Aspose.Slides für .NET für andere PowerPoint-bezogene Aufgaben geeignet?

Absolut! Aspose.Slides für .NET bietet eine breite Palette von APIs für die Arbeit mit PowerPoint-Präsentationen. Sie können verschiedene Aspekte von Präsentationen programmgesteuert erstellen, ändern, konvertieren und manipulieren.