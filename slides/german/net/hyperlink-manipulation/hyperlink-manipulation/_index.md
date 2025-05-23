---
"description": "Erfahren Sie, wie Sie in Aspose.Slides für .NET Hyperlinks hinzufügen und entfernen. Optimieren Sie Ihre Präsentationen ganz einfach mit interaktiven Links."
"linktitle": "Hyperlink-Manipulation in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Hyperlink-Manipulation in Aspose.Slides"
"url": "/de/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hyperlink-Manipulation in Aspose.Slides


Hyperlinks sind essenzielle Elemente in Präsentationen, da sie eine bequeme Möglichkeit bieten, zwischen Folien zu navigieren oder auf externe Ressourcen zuzugreifen. Aspose.Slides für .NET bietet leistungsstarke Funktionen zum Hinzufügen und Entfernen von Hyperlinks in Ihren Präsentationsfolien. In diesem Tutorial führen wir Sie durch die Hyperlink-Manipulation mit Aspose.Slides für .NET. Wir behandeln das Hinzufügen und Entfernen von Hyperlinks zu einer Folie. Los geht’s!

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für .NET: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert und eingerichtet haben. Die Dokumentation finden Sie [Hier](https://reference.aspose.com/slides/net/) und laden Sie es herunter von [dieser Link](https://releases.aspose.com/slides/net/).

2. Ihr Dokumentverzeichnis: Sie benötigen ein Verzeichnis, in dem Sie Ihre Präsentationsdateien speichern. Geben Sie den Pfad zu diesem Verzeichnis unbedingt im Code an.

3. Grundkenntnisse in C#: Dieses Tutorial setzt voraus, dass Sie über grundlegende Kenntnisse der C#-Programmierung verfügen.

Nachdem Sie nun alle Voraussetzungen erfüllt haben, fahren wir mit der Schritt-für-Schritt-Anleitung zur Hyperlink-Manipulation mit Aspose.Slides für .NET fort.

## Hinzufügen von Hyperlinks zu einer Folie

### Schritt 1: Präsentation initialisieren

Um zu beginnen, müssen Sie eine Präsentation mit Aspose.Slides initialisieren. Dies können Sie mit dem folgenden Code tun:

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

Als Nächstes fügen Sie dem Text in der von Ihnen erstellten Form einen Hyperlink hinzu. So geht's:

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

Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich einen Hyperlink zu einer Folie hinzugefügt.

## Entfernen von Hyperlinks aus einer Folie

### Schritt 1: Präsentation initialisieren

Um Hyperlinks aus einer Folie zu entfernen, müssen Sie eine vorhandene Präsentation öffnen:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Schritt 2: Hyperlinks entfernen

Entfernen Sie nun mit dem folgenden Code alle Hyperlinks aus der Präsentation:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Schritt 3: Präsentation speichern

Speichern Sie die Präsentation, nachdem Sie die Hyperlinks entfernt haben:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Und das war's! Sie haben mit Aspose.Slides für .NET erfolgreich Hyperlinks aus einer Folie entfernt.

Zusammenfassend lässt sich sagen, dass Aspose.Slides für .NET eine effiziente Möglichkeit bietet, Hyperlinks in Ihren Präsentationen zu bearbeiten und so interaktive und ansprechende Folien zu erstellen. Ob Sie Hyperlinks zu externen Ressourcen hinzufügen oder entfernen möchten – Aspose.Slides vereinfacht den Prozess und erweitert Ihre Möglichkeiten zur Präsentationserstellung.

Vielen Dank, dass Sie an diesem Tutorial zur Hyperlink-Manipulation in Aspose.Slides für .NET teilgenommen haben. Wenn Sie Fragen haben oder weitere Unterstützung benötigen, können Sie gerne die [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die Aspose-Community auf der [Support-Forum](https://forum.aspose.com/).

---

## Abschluss

In diesem Tutorial haben wir gelernt, wie man Hyperlinks in Präsentationen mit Aspose.Slides für .NET bearbeitet. Wir haben sowohl das Hinzufügen als auch das Entfernen von Hyperlinks behandelt, sodass Sie dynamische und interaktive Präsentationen erstellen können. Aspose.Slides vereinfacht den Prozess und ermöglicht es Ihnen, Ihre Folien ganz einfach mit Hyperlinks zu externen Ressourcen zu erweitern.

Haben Sie weitere Fragen zur Arbeit mit Aspose.Slides oder anderen Aspekten des Präsentationsdesigns? Weitere Informationen finden Sie in den FAQs unten.

## FAQs (Häufig gestellte Fragen)

### Was sind die wichtigsten Vorteile der Verwendung von Aspose.Slides für .NET?
Aspose.Slides für .NET bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Konvertieren von Präsentationen. Es bietet umfassende Tools zum Hinzufügen von Inhalten, Animationen und Interaktionen zu Ihren Folien.

### Kann ich in Aspose.Slides Hyperlinks zu anderen Objekten als Text hinzufügen?
Ja, mit Aspose.Slides können Sie Hyperlinks zu verschiedenen Objekten hinzufügen, darunter Formen, Bilder und Text, und so flexible interaktive Präsentationen erstellen.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Dateiformaten kompatibel?
Absolut. Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPT, PPTX, PPS und mehr. Es gewährleistet die Kompatibilität mit verschiedenen Versionen von Microsoft PowerPoint.

### Wo finde ich zusätzliche Ressourcen und Support für Aspose.Slides?
Ausführliche Dokumentation und Community-Support finden Sie unter [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) und die [Aspose-Supportforum](https://forum.aspose.com/).

### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
Wenn Sie eine temporäre Lizenz für Aspose.Slides benötigen, können Sie eine erhalten [Hier](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}