---
title: So legen Sie einen Makro-Hyperlink fest Klicken Sie in Aspose.Slides für .NET
linktitle: Hyperlink-Management mit Makros
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Makro-Hyperlinks in Ihren Präsentationen festlegen. Verbessern Sie die Interaktivität und binden Sie Ihr Publikum ein.
type: docs
weight: 13
url: /de/net/hyperlink-manipulation/macro-hyperlink/
---

In der Welt der modernen Softwareentwicklung ist die Erstellung dynamischer und interaktiver Präsentationen ein zentraler Aspekt. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie nahtlos mit Präsentationen arbeiten können. Unabhängig davon, ob Sie eine Geschäftspräsentation oder eine lehrreiche Diashow erstellen, kann die Möglichkeit, Makro-Hyperlink-Klicks festzulegen, das Benutzererlebnis erheblich verbessern. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Einrichtung eines Makro-Hyperlink-Klicks mit Aspose.Slides für .NET. 

## Voraussetzungen

Bevor wir uns mit der Schritt-für-Schritt-Anleitung befassen, sollten Sie einige Voraussetzungen erfüllen:

1.Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist, da dies unsere Entwicklungsumgebung ist.

 2.Aspose.Slides für .NET: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

3.Grundkenntnisse von C#: Um dieses Tutorial durchführen zu können, ist es wichtig, mit der Programmiersprache C# vertraut zu sein.

## Namespaces importieren

Im ersten Schritt importieren wir die notwendigen Namespaces, um mit Aspose.Slides zu arbeiten:

### Schritt 1: Namespaces importieren

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Wir haben das importiert`Aspose.Slides` Namespace, der der zentrale Namespace für die Arbeit mit Präsentationen ist, und der`Aspose.Slides.Export` Namensraum.

## Festlegen des Makro-Hyperlink-Klicks

Kommen wir nun zum Hauptteil dieses Tutorials – dem Festlegen eines Makro-Hyperlink-Klicks in Ihrer Präsentation.

### Schritt 2: Präsentation initialisieren

Zuerst müssen wir eine neue Präsentation initialisieren.

```csharp
using (Presentation presentation = new Presentation())
{
    // Ihr Code wird hier angezeigt.
}
```

Innerhalb dieser using-Anweisung erstellen Sie ein neues Präsentationsobjekt und führen darin alle Ihre Operationen aus.

### Schritt 3: Fügen Sie eine AutoForm hinzu

Um einen Makro-Hyperlink-Klick festzulegen, benötigen Sie ein Objekt, auf das der Benutzer klicken kann. In diesem Beispiel verwenden wir eine AutoForm als anklickbares Element.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Hier erstellen wir eine AutoShape mit dem Typ „BlankButton“ an bestimmten Koordinaten (20, 20) und mit den Abmessungen 80x30. Sie können diese Werte an das Layout Ihrer Präsentation anpassen.

### Schritt 4: Makro-Hyperlink-Klick festlegen

Jetzt kommt der Teil, in dem Sie den Makro-Hyperlink-Klick festlegen. Sie müssen einen Makronamen als Parameter angeben.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In diesem Beispiel haben wir den Makro-Hyperlink-Klick auf „TestMacro“ festgelegt. Wenn der Benutzer auf die AutoForm klickt, wird dieses Makro ausgelöst.

### Schritt 5: Informationen abrufen

Sie können auch Informationen zu dem von Ihnen gesetzten Hyperlink abrufen.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Mit diesen Codezeilen können Sie die externe URL und den Aktionstyp des Hyperlinks drucken.

Und das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich einen Makro-Hyperlink-Klick in Ihrer Präsentation festgelegt.

## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Slides für .NET einen Makro-Hyperlink-Klick in Ihrer Präsentation festlegen. Dies kann eine wertvolle Funktion sein, um interaktive und dynamische Präsentationen zu erstellen, die Ihr Publikum ansprechen. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur Verfügung, mit dem Sie Ihre Präsentationsentwicklung auf die nächste Stufe heben können.

 Jetzt ist es an der Zeit, mit benutzerdefinierten Makro-Hyperlinks zu experimentieren und fesselnde Präsentationen zu erstellen. Fühlen Sie sich frei, die zu erkunden[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) für detailliertere Informationen und Möglichkeiten.

## FAQs (häufig gestellte Fragen)

### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides ist in erster Linie für .NET konzipiert, Aspose bietet jedoch ähnliche Bibliotheken für andere Programmiersprachen wie Java.

### Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
Aspose.Slides für .NET ist eine kommerzielle Bibliothek mit einer kostenlosen Testversion. Sie können es herunterladen unter[Hier](https://releases.aspose.com/).

### Gibt es Einschränkungen bei der Verwendung von Makros in Präsentationen, die mit Aspose.Slides für .NET erstellt wurden?
Mit Aspose.Slides für .NET können Sie mit Makros arbeiten. Sie sollten sich jedoch der Sicherheits- und Kompatibilitätsaspekte bewusst sein, wenn Sie Makros in Präsentationen verwenden.

### Kann ich das Erscheinungsbild der für den Hyperlink verwendeten AutoForm anpassen?
Ja, Sie können das Erscheinungsbild der AutoForm anpassen, indem Sie ihre Eigenschaften wie Größe, Farbe und Schriftart anpassen.

### Wo erhalte ich Hilfe oder Support für Aspose.Slides für .NET?
 Wenn Sie auf Probleme stoßen oder Fragen haben, können Sie im Aspose-Supportforum Hilfe suchen[Hier](https://forum.aspose.com/).