---
title: Rendern Sie Notizen beim Konvertieren der Präsentation in HTML
linktitle: Rendern Sie Notizen beim Konvertieren der Präsentation in HTML
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Vortragsnotizen beim Konvertieren einer Präsentation in HTML mit Aspose.Slides für .NET effektiv rendern. Diese Schritt-für-Schritt-Anleitung bietet Beispiele für Quellcodes und Einblicke, die Ihnen dabei helfen, eine nahtlose Konvertierung unter Beibehaltung von Notizen zu erreichen.
type: docs
weight: 28
url: /de/net/presentation-manipulation/render-notes-while-converting-presentation-to-html/
---

## Einführung

Referentennotizen in Präsentationen sind von unschätzbarem Wert, um den Referenten zusätzlichen Kontext und Orientierungshilfen zu bieten. Bei der Konvertierung von Präsentationen in HTML ist es wichtig, diese Notizen beizubehalten, um die Vollständigkeit des Inhalts sicherzustellen. In diesem Leitfaden erfahren Sie, wie Sie während der Konvertierung von Präsentationen in HTML mit der leistungsstarken Aspose.Slides-Bibliothek für .NET Sprechernotizen rendern und bewahren.

## Schritt-für-Schritt-Anleitung zum Rendern von Notizen

Das Konvertieren einer Präsentation in das HTML-Format unter Beibehaltung der Vortragsnotizen erfordert einen sorgfältigen Umgang mit Inhalten und Metadaten. Gehen wir die Schritte durch, um dies mit Aspose.Slides für .NET zu erreichen.

### Schritt 1: Aspose.Slides für .NET installieren

 Bevor wir fortfahren, stellen Sie sicher, dass Aspose.Slides für .NET installiert ist. Wenn nicht, laden Sie es herunter von[Hier](https://releases.aspose.com/slides/net/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

### Schritt 2: Laden der Präsentation

Laden Sie zunächst die Präsentation, die Sie in HTML konvertieren möchten, einschließlich der Vortragsnotizen. Verwenden Sie den folgenden Codeausschnitt:

```csharp
using Aspose.Slides;
// ...
Presentation presentation = new Presentation("your-presentation.pptx");
```

 Ersetzen`"your-presentation.pptx"` mit dem Pfad zu Ihrer Präsentationsdatei.

### Schritt 3: Vortragsnotizen rendern

Mit Aspose.Slides können Sie auf Sprechernotizen zugreifen, die jeder Folie zugeordnet sind. Sie können diese Notizen extrahieren und in die HTML-Ausgabe integrieren. So können Sie es machen:

```csharp
using Aspose.Slides.Export;
// ...
HtmlOptions htmlOptions = new HtmlOptions();
htmlOptions.NotesCommentsLayouting.NotesPosition = NotesPositions.BottomFull;
presentation.Save("output.html", SaveFormat.Html, htmlOptions);
```

 In diesem Code erstellen wir eine Instanz von`HtmlOptions` und Angabe der Position der Sprechernotizen am unteren Rand jeder Folie. Die Präsentation wird dann als HTML-Datei mit dem Namen gespeichert`"output.html"`.

### Schritt 4: Anpassen der HTML-Ausgabe

 Aspose.Slides bietet verschiedene Anpassungsmöglichkeiten für die HTML-Ausgabe. Sie können das Erscheinungsbild von Sprechernotizen, Folienübergängen, Schriftarten und mehr steuern. Siehe die[Aspose.Slides API-Referenz](https://reference.aspose.com/slides/net/) Ausführliche Informationen zu den verfügbaren Optionen finden Sie hier.

## Sprechernotizen bei der HTML-Konvertierung beibehalten

Bei der Konvertierung von Präsentationen in HTML ist die Beibehaltung der Vortragsnotizen von entscheidender Bedeutung, um den Wert der Präsentation zu erhalten. Hier sind einige Überlegungen, um eine erfolgreiche Konservierung sicherzustellen:

### Anmerkungen Position: 
	Choose where the speaker notes should appear in the HTML layout, such as at the bottom of each slide.

### Layoutformatierung: 
	Ensure that the speaker notes are properly formatted and aligned within the HTML output for easy readability.

## Zugänglichkeit von Inhalten: 
	Verify that the converted HTML maintains the accessibility of speaker notes for users who rely on screen readers.

## Häufig gestellte Fragen

### Kann ich Vortragsnotizen mit Aspose.Slides für .NET in HTML konvertieren?

Ja, mit Aspose.Slides für .NET können Sie Präsentationen in das HTML-Format konvertieren und gleichzeitig Vortragsnotizen rendern und beibehalten. Befolgen Sie die in dieser Anleitung beschriebenen Schritte für eine erfolgreiche Konvertierung.

### Wie passe ich das Erscheinungsbild von Sprechernotizen in der HTML-Ausgabe an?

Sie können das Erscheinungsbild von Sprechernotizen anpassen, indem Sie die von Aspose.Slides bereitgestellten HTML-Optionen anpassen. Dazu gehören Positionierungs-, Formatierungs- und Layouteinstellungen.

### Gibt es beim Konvertieren von Notizen in HTML irgendwelche Überlegungen zur Barrierefreiheit?

Absolut. Stellen Sie beim Konvertieren von Vortragsnotizen in HTML sicher, dass der resultierende Inhalt für alle Benutzer zugänglich bleibt, auch für diejenigen, die auf Bildschirmleseprogramme angewiesen sind. Testen Sie die HTML-Ausgabe, um ihre Zugänglichkeit zu bestätigen.

### Kann ich die Position von Sprechernotizen im HTML-Layout anpassen?

Ja, Sie können die Position von Sprechernotizen innerhalb des HTML-Layouts festlegen. Aspose.Slides bietet Optionen zum Positionieren von Notizen oben, unten oder an anderen Stellen jeder Folie.

### Wo finde ich weitere Informationen zu HTML-Konvertierungsoptionen in Aspose.Slides?

 Ausführlichere Informationen zu HTML-Konvertierungsoptionen und anderen Funktionen von Aspose.Slides für .NET finden Sie im[Aspose.Slides API-Referenz](https://reference.aspose.com/slides/net/).

## Abschluss

Durch das Beibehalten der Vortragsnotizen bei der Konvertierung von Präsentationen in HTML wird sichergestellt, dass wertvolle Kontexte und Erkenntnisse erhalten bleiben. Dank Aspose.Slides für .NET kann dieser Prozess nahtlos durchgeführt werden, sodass Präsentatoren während Online-Präsentationen auf wichtige Informationen zugreifen können. Wenn Sie die in dieser Anleitung beschriebenen Schritte befolgen, sind Sie in der Lage, Präsentationen in HTML zu konvertieren und gleichzeitig Vortragsnotizen effektiv wiederzugeben.