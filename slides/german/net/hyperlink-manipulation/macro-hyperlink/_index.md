---
title: So legen Sie einen Makro-Hyperlink-Klick in Aspose.Slides für .NET fest
linktitle: Hyperlink-Verwaltung mit Makros
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Makro-Hyperlinks in Ihre Präsentationen einfügen. Steigern Sie die Interaktivität und fesseln Sie Ihr Publikum.
weight: 13
url: /de/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So legen Sie einen Makro-Hyperlink-Klick in Aspose.Slides für .NET fest


In der Welt der modernen Softwareentwicklung ist die Erstellung dynamischer und interaktiver Präsentationen ein zentraler Aspekt. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie nahtlos mit Präsentationen arbeiten können. Egal, ob Sie eine Geschäftspräsentation oder eine Bildungs-Diashow erstellen, die Möglichkeit, Makro-Hyperlink-Klicks festzulegen, kann das Benutzererlebnis erheblich verbessern. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess zum Festlegen eines Makro-Hyperlink-Klicks mit Aspose.Slides für .NET. 

## Voraussetzungen

Bevor wir uns in das Schritt-für-Schritt-Tutorial stürzen, sollten einige Voraussetzungen erfüllt sein:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist, da dies unsere Entwicklungsumgebung sein wird.

 2.Aspose.Slides für .NET: Sie müssen die Bibliothek Aspose.Slides für .NET installiert haben. Sie können sie herunterladen von[Hier](https://releases.aspose.com/slides/net/).

3. Grundkenntnisse in C#: Um diesem Tutorial folgen zu können, sind Kenntnisse der Programmiersprache C# unbedingt erforderlich.

## Namespaces importieren

Importieren wir im ersten Schritt die erforderlichen Namespaces für die Arbeit mit Aspose.Slides:

### Schritt 1: Namespaces importieren

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Wir haben importiert die`Aspose.Slides` Namespace, der den Kern-Namespace für die Arbeit mit Präsentationen darstellt, und der`Aspose.Slides.Export` Namespace.

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

Um einen Makro-Hyperlink-Klick festzulegen, benötigen Sie ein Objekt, auf das der Benutzer klicken kann. In diesem Beispiel verwenden wir eine AutoForm als anklickbares Element.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Hier erstellen wir eine AutoForm mit dem Typ „BlankButton“ an bestimmten Koordinaten (20, 20) und mit den Abmessungen 80 x 30. Sie können diese Werte an das Layout Ihrer Präsentation anpassen.

### Schritt 4: Makro-Hyperlink festlegen Klicken

Jetzt kommt der Teil, in dem Sie den Makro-Hyperlink-Klick festlegen. Sie müssen einen Makronamen als Parameter angeben.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In diesem Beispiel haben wir den Makro-Hyperlink-Klick auf „Testmakro“ eingestellt. Wenn der Benutzer auf die AutoForm klickt, wird dieses Makro ausgelöst.

### Schritt 5: Informationen abrufen

Darüber hinaus können Sie Informationen zu dem von Ihnen gesetzten Hyperlink abrufen.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Mit diesen Codezeilen können Sie die externe URL und den Aktionstyp des Hyperlinks ausgeben.

Und das war’s! Sie haben mit Aspose.Slides für .NET erfolgreich einen Makro-Hyperlink-Klick in Ihrer Präsentation festgelegt.

## Abschluss

In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Slides für .NET einen Makro-Hyperlink-Klick in Ihrer Präsentation festlegen. Dies kann eine wertvolle Funktion sein, um interaktive und dynamische Präsentationen zu erstellen, die Ihr Publikum fesseln. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur Verfügung, mit dem Sie Ihre Präsentationsentwicklung auf die nächste Ebene bringen können.

 Jetzt ist es an der Zeit, zu experimentieren und fesselnde Präsentationen mit benutzerdefinierten Makro-Hyperlinks zu erstellen. Erkunden Sie die[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) für ausführlichere Informationen und Möglichkeiten.

## FAQs (Häufig gestellte Fragen)

### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides ist in erster Linie für .NET konzipiert, aber Aspose bietet ähnliche Bibliotheken für andere Programmiersprachen wie Java.

### Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
Aspose.Slides für .NET ist eine kommerzielle Bibliothek mit einer kostenlosen Testversion. Sie können sie herunterladen von[Hier](https://releases.aspose.com/).

### Gibt es Einschränkungen bei der Verwendung von Makros in Präsentationen, die mit Aspose.Slides für .NET erstellt wurden?
Aspose.Slides für .NET ermöglicht Ihnen die Arbeit mit Makros, Sie sollten sich jedoch bei der Verwendung von Makros in Präsentationen der Sicherheits- und Kompatibilitätsaspekte bewusst sein.

### Kann ich das Erscheinungsbild der für den Hyperlink verwendeten AutoForm anpassen?
Ja, Sie können das Erscheinungsbild der AutoForm anpassen, indem Sie ihre Eigenschaften wie Größe, Farbe und Schriftart ändern.

### Wo kann ich Hilfe oder Support für Aspose.Slides für .NET erhalten?
 Wenn Sie auf Probleme stoßen oder Fragen haben, können Sie im Aspose-Supportforum Hilfe suchen.[Hier](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
