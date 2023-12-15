---
title: Hinzufügen von Hyperlinks zu Folien in .NET mithilfe von Aspose.Slides
linktitle: Hyperlink zur Folie hinzufügen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Hyperlinks zu PowerPoint-Folien hinzufügen. Bereichern Sie Ihre Präsentationen mit interaktiven Elementen.
type: docs
weight: 12
url: /de/net/hyperlink-manipulation/add-hyperlink/
---

In der Welt der digitalen Präsentationen ist Interaktivität der Schlüssel. Durch das Hinzufügen von Hyperlinks zu Ihren Folien kann Ihre Präsentation ansprechender und informativer werden. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen programmgesteuert erstellen, ändern und bearbeiten können. In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Slides für .NET Hyperlinks zu Ihren Folien hinzufügen. 

## Voraussetzungen

Bevor wir uns mit dem Hinzufügen von Hyperlinks zu Folien befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio: Sie sollten Visual Studio auf Ihrem Computer installiert haben, um den .NET-Code schreiben und ausführen zu können.

2. Aspose.Slides für .NET: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

3. Grundlegende C#-Kenntnisse: Vertrautheit mit der C#-Programmierung ist von Vorteil.

## Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. In diesem Fall benötigen Sie die folgenden Namespaces aus der Aspose.Slides-Bibliothek:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Lassen Sie uns nun den Prozess des Hinzufügens von Hyperlinks zu Folien in mehrere Schritte unterteilen.

## Schritt 1: Präsentation initialisieren

Erstellen Sie zunächst eine neue Präsentation mit Aspose.Slides. So können Sie es machen:

```csharp
using (Presentation presentation = new Presentation())
{
    // Ihr Code kommt hierher
}
```

Dieser Code initialisiert eine neue PowerPoint-Präsentation.

## Schritt 2: Textrahmen hinzufügen

Jetzt fügen wir Ihrer Folie einen Textrahmen hinzu. Dieser Textrahmen dient als anklickbares Element in Ihrer Folie. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Der obige Code erstellt eine rechteckige automatische Form und fügt einen Textrahmen mit dem Text „Aspose: File Format APIs“ hinzu.

## Schritt 3: Hyperlink hinzufügen

Als Nächstes fügen wir dem von Ihnen erstellten Textrahmen einen Hyperlink hinzu. Dadurch wird der Text anklickbar.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

In diesem Schritt setzen wir die Hyperlink-URL auf „https://www.aspose.com/“ und stellen einen Tooltip für zusätzliche Informationen bereit. Sie können auch das Erscheinungsbild des Hyperlinks formatieren, wie oben gezeigt.

## Schritt 4: Präsentation speichern

Speichern Sie abschließend Ihre Präsentation mit dem hinzugefügten Hyperlink.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Dieser Code speichert die Präsentation als „presentation-out.pptx“.

Jetzt haben Sie mit Aspose.Slides für .NET erfolgreich einen Hyperlink zu einer Folie hinzugefügt.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mithilfe von Aspose.Slides für .NET Hyperlinks zu Folien in PowerPoint-Präsentationen hinzufügen. Wenn Sie diese Schritte befolgen, können Sie Ihre Präsentationen interaktiver und ansprechender gestalten und wertvolle Links zu zusätzlichen Ressourcen oder Informationen bereitstellen.

 Ausführlichere Informationen und Dokumentation finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

## FAQs

### 1. Kann ich neben Textrahmen auch Hyperlinks zu anderen Formen hinzufügen?

Ja, Sie können mit Aspose.Slides für .NET Hyperlinks zu verschiedenen Formen wie Rechtecken, Bildern und mehr hinzufügen.

### 2. Wie kann ich einen Hyperlink von einer Form in einer PowerPoint-Folie entfernen?

 Sie können einen Hyperlink aus einer Form entfernen, indem Sie Folgendes festlegen`HyperlinkClick` Eigentum zu`null`.

### 3. Kann ich die Hyperlink-URL in meinem Code dynamisch ändern?

 Absolut! Sie können die URL eines Hyperlinks an jeder Stelle in Ihrem Code aktualisieren, indem Sie die URL ändern`Hyperlink` Eigentum.

### 4. Welche anderen interaktiven Elemente kann ich mit Aspose.Slides zu PowerPoint-Folien hinzufügen?

Aspose.Slides bietet eine breite Palette interaktiver Funktionen, darunter Aktionsschaltflächen, Multimedia-Elemente und Animationen.

### 5. Ist Aspose.Slides für andere Programmiersprachen verfügbar?

Ja, Aspose.Slides ist für verschiedene Programmiersprachen verfügbar, darunter Java und Python.