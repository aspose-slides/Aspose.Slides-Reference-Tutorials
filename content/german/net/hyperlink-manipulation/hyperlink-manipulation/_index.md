---
title: Hyperlink-Manipulation in Aspose.Slides
linktitle: Hyperlink-Manipulation in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Hyperlinks in Aspose.Slides für .NET hinzufügen und entfernen. Erweitern Sie Ihre Präsentationen ganz einfach mit interaktiven Links.
type: docs
weight: 10
url: /de/net/hyperlink-manipulation/hyperlink-manipulation/
---

Hyperlinks sind wesentliche Elemente in Präsentationen, da sie eine bequeme Möglichkeit bieten, zwischen Folien zu navigieren oder auf externe Ressourcen zuzugreifen. Aspose.Slides für .NET bietet leistungsstarke Funktionen zum Hinzufügen und Entfernen von Hyperlinks in Ihren Präsentationsfolien. In diesem Tutorial führen wir Sie durch den Prozess der Hyperlink-Manipulation mit Aspose.Slides für .NET. Wir behandeln das Hinzufügen von Hyperlinks zu einer Folie und das Entfernen von Hyperlinks von einer Folie. Also, lasst uns eintauchen!

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für .NET: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert und eingerichtet haben. Die Dokumentation finden Sie hier[Hier](https://reference.aspose.com/slides/net/) und laden Sie es herunter von[dieser Link](https://releases.aspose.com/slides/net/).

2. Ihr Dokumentenverzeichnis: Sie benötigen ein Verzeichnis, in dem Sie Ihre Präsentationsdateien speichern. Stellen Sie sicher, dass Sie in Ihrem Code den Pfad zu diesem Verzeichnis angeben.

3. Grundkenntnisse in C#: In diesem Tutorial wird davon ausgegangen, dass Sie über grundlegende Kenntnisse der C#-Programmierung verfügen.

Nachdem Sie nun alle Voraussetzungen geschaffen haben, fahren wir mit der Schritt-für-Schritt-Anleitung zur Hyperlink-Manipulation mit Aspose.Slides für .NET fort.

## Hinzufügen von Hyperlinks zu einer Folie

### Schritt 1: Präsentation initialisieren

Um zu beginnen, müssen Sie eine Präsentation mit Aspose.Slides initialisieren. Sie können dies mit dem folgenden Code tun:

```csharp
using (Presentation presentation = new Presentation())
{
    // Ihr Code hier
}
```

### Schritt 2: Textrahmen hinzufügen

Fügen wir nun einer Folie einen Textrahmen hinzu. Dieser Code erstellt eine rechteckige Form mit Text:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Schritt 3: Hyperlink hinzufügen

Als Nächstes fügen Sie einen Hyperlink zum Text in der von Ihnen erstellten Form hinzu. So können Sie es machen:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Schritt 4: Präsentation speichern

Speichern Sie abschließend Ihre Präsentation mit dem hinzugefügten Hyperlink:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich einen Hyperlink zu einer Folie hinzugefügt.

## Entfernen von Hyperlinks aus einer Folie

### Schritt 1: Präsentation initialisieren

Um Hyperlinks von einer Folie zu entfernen, müssen Sie eine vorhandene Präsentation öffnen:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Schritt 2: Hyperlinks entfernen

Entfernen Sie nun alle Hyperlinks aus der Präsentation mit dem folgenden Code:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Schritt 3: Präsentation speichern

Speichern Sie die Präsentation, nachdem Sie die Hyperlinks entfernt haben:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Und das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich Hyperlinks von einer Folie entfernt.

Zusammenfassend lässt sich sagen, dass Aspose.Slides für .NET eine effiziente Möglichkeit bietet, Hyperlinks in Ihren Präsentationen zu bearbeiten und so interaktive und ansprechende Folien zu erstellen. Unabhängig davon, ob Sie Hyperlinks zu externen Ressourcen hinzufügen oder diese entfernen möchten, vereinfacht Aspose.Slides den Prozess und verbessert Ihre Möglichkeiten zur Präsentationserstellung.

 Vielen Dank, dass Sie an diesem Tutorial zur Hyperlink-Manipulation in Aspose.Slides für .NET teilgenommen haben. Wenn Sie Fragen haben oder weitere Hilfe benötigen, schauen Sie sich gerne um[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die Aspose-Community unter[Hilfeforum](https://forum.aspose.com/).

---

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Hyperlinks in Präsentationen mit Aspose.Slides für .NET manipuliert. Wir haben sowohl das Hinzufügen als auch das Entfernen von Hyperlinks behandelt, sodass Sie dynamische und interaktive Präsentationen erstellen können. Aspose.Slides vereinfacht den Prozess und macht es einfach, Ihre Folien mit Hyperlinks zu externen Ressourcen zu erweitern.

Haben Sie weitere Fragen zur Arbeit mit Aspose.Slides oder zu anderen Aspekten der Präsentationsgestaltung? Weitere Informationen finden Sie in den FAQs unten.

## FAQs (häufig gestellte Fragen)

### Was sind die Hauptvorteile der Verwendung von Aspose.Slides für .NET?
Aspose.Slides für .NET bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Konvertieren von Präsentationen. Es bietet einen umfassenden Satz an Tools zum Hinzufügen von Inhalten, Animationen und Interaktionen zu Ihren Folien.

### Kann ich in Aspose.Slides Hyperlinks zu anderen Objekten als Text hinzufügen?
Ja, Aspose.Slides ermöglicht Ihnen das Hinzufügen von Hyperlinks zu verschiedenen Objekten, einschließlich Formen, Bildern und Text, und gibt Ihnen so Flexibilität bei der Erstellung interaktiver Präsentationen.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Dateiformaten kompatibel?
Absolut. Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPT, PPTX, PPS und mehr. Es gewährleistet die Kompatibilität mit verschiedenen Versionen von Microsoft PowerPoint.

### Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Slides?
Ausführliche Dokumentation und Community-Unterstützung finden Sie unter[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) und das[Aspose-Supportforum](https://forum.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Wenn Sie eine temporäre Lizenz für Aspose.Slides benötigen, können Sie eine erwerben[Hier](https://purchase.aspose.com/temporary-license/).