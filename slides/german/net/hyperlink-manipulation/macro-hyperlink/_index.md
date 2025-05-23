---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Makro-Hyperlinks in Ihren Präsentationen einfügen. Steigern Sie die Interaktivität und begeistern Sie Ihr Publikum."
"linktitle": "Hyperlink-Verwaltung mit Makros"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "So legen Sie den Makro-Hyperlink-Klick in Aspose.Slides für .NET fest"
"url": "/de/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# So legen Sie den Makro-Hyperlink-Klick in Aspose.Slides für .NET fest


In der modernen Softwareentwicklung ist die Erstellung dynamischer und interaktiver Präsentationen ein zentraler Aspekt. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die Ihnen die nahtlose Arbeit mit Präsentationen ermöglicht. Ob Sie eine Geschäftspräsentation oder eine Bildungspräsentation erstellen – die Möglichkeit, Makro-Hyperlink-Klicks zu setzen, kann das Benutzererlebnis erheblich verbessern. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Setzens eines Makro-Hyperlink-Klicks mit Aspose.Slides für .NET. 

## Voraussetzungen

Bevor wir mit dem Schritt-für-Schritt-Tutorial beginnen, sollten Sie einige Voraussetzungen erfüllen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist, da dies unsere Entwicklungsumgebung sein wird.

2.Aspose.Slides für .NET: Sie benötigen die Bibliothek Aspose.Slides für .NET. Sie können sie hier herunterladen. [Hier](https://releases.aspose.com/slides/net/).

3. Grundkenntnisse in C#: Um diesem Tutorial folgen zu können, ist die Vertrautheit mit der Programmiersprache C# unerlässlich.

## Namespaces importieren

Im ersten Schritt importieren wir die notwendigen Namespaces für die Arbeit mit Aspose.Slides:

### Schritt 1: Namespaces importieren

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Wir haben importiert die `Aspose.Slides` Namespace, der den Kern-Namespace für die Arbeit mit Präsentationen darstellt, und der `Aspose.Slides.Export` Namespace.

## Festlegen des Makro-Hyperlink-Klicks

Kommen wir nun zum Hauptteil dieses Tutorials: dem Einrichten eines Makro-Hyperlink-Klicks in Ihrer Präsentation.

### Schritt 2: Präsentation initialisieren

Zuerst müssen wir eine neue Präsentation initialisieren.

```csharp
using (Presentation presentation = new Presentation())
{
    // Ihr Code wird hier eingefügt.
}
```

Innerhalb dieser Using-Anweisung erstellen Sie ein neues Präsentationsobjekt und führen alle Ihre Operationen darin aus.

### Schritt 3: Hinzufügen einer AutoForm

Um einen Makro-Hyperlink-Klick einzurichten, benötigen Sie ein Objekt, auf das der Benutzer klicken kann. In diesem Beispiel verwenden wir eine AutoForm als anklickbares Element.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Hier erstellen wir eine AutoForm vom Typ „BlankButton“ an den Koordinaten 20, 20 und mit den Abmessungen 80 x 30. Sie können diese Werte an das Layout Ihrer Präsentation anpassen.

### Schritt 4: Makro-Hyperlink-Klick festlegen

Nun folgt der Teil, in dem Sie den Makro-Hyperlink-Klick festlegen. Sie müssen einen Makronamen als Parameter angeben.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In diesem Beispiel haben wir den Makro-Hyperlink-Klick auf „Testmakro“ eingestellt. Wenn der Benutzer auf die AutoForm klickt, wird dieses Makro ausgelöst.

### Schritt 5: Informationen abrufen

Sie können außerdem Informationen zu dem von Ihnen gesetzten Hyperlink abrufen.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Mit diesen Codezeilen können Sie die externe URL und den Aktionstyp des Hyperlinks drucken.

Und das war's! Sie haben mit Aspose.Slides für .NET erfolgreich einen Makro-Hyperlink-Klick in Ihrer Präsentation eingerichtet.

## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Slides für .NET einen Makro-Hyperlink-Klick in Ihrer Präsentation einrichten. Dies ist eine wertvolle Funktion für die Erstellung interaktiver und dynamischer Präsentationen, die Ihr Publikum fesseln. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur Verfügung, um Ihre Präsentationsentwicklung auf die nächste Stufe zu heben.

Jetzt ist es an der Zeit, mit benutzerdefinierten Makro-Hyperlinks zu experimentieren und fesselnde Präsentationen zu erstellen. Entdecken Sie die [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) für ausführlichere Informationen und Möglichkeiten.

## FAQs (Häufig gestellte Fragen)

### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides ist in erster Linie für .NET konzipiert, aber Aspose bietet ähnliche Bibliotheken für andere Programmiersprachen wie Java.

### Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
Aspose.Slides für .NET ist eine kommerzielle Bibliothek mit einer kostenlosen Testversion. Sie können sie herunterladen von [Hier](https://releases.aspose.com/).

### Gibt es Einschränkungen bei der Verwendung von Makros in Präsentationen, die mit Aspose.Slides für .NET erstellt wurden?
Aspose.Slides für .NET ermöglicht Ihnen die Arbeit mit Makros, Sie sollten sich jedoch bei der Verwendung von Makros in Präsentationen der Sicherheits- und Kompatibilitätsaspekte bewusst sein.

### Kann ich das Erscheinungsbild der für den Hyperlink verwendeten AutoForm anpassen?
Ja, Sie können das Erscheinungsbild der AutoForm anpassen, indem Sie ihre Eigenschaften wie Größe, Farbe und Schriftart anpassen.

### Wo erhalte ich Hilfe oder Support für Aspose.Slides für .NET?
Wenn Sie auf Probleme stoßen oder Fragen haben, können Sie im Aspose-Supportforum Hilfe suchen. [Hier](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}