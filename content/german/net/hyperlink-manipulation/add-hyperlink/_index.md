---
title: Hyperlink zur Folie hinzufügen
linktitle: Hyperlink zur Folie hinzufügen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Hyperlinks zu Folien in PowerPoint hinzufügen. Werten Sie Präsentationen mit interaktiven Inhalten auf.
type: docs
weight: 12
url: /de/net/hyperlink-manipulation/add-hyperlink/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen zu erstellen, zu ändern und zu bearbeiten, ohne auf Microsoft Office angewiesen zu sein. Es bietet eine Vielzahl von Funktionen, einschließlich des Hinzufügens und Verwaltens von Hyperlinks in Folien.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio ist auf Ihrem System installiert.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://downloads.aspose.com/slides/net).

## Hinzufügen eines Hyperlinks zu einem Text in einer Folie

1. Erstellen Sie ein neues C#-Projekt in Visual Studio.
2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides-DLL hinzu.
3. Verwenden Sie den folgenden Code, um einen Hyperlink zu einem Text in einer Folie hinzuzufügen:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
Presentation presentation = new Presentation("presentation.pptx");

// Greifen Sie auf eine Folie zu
ISlide slide = presentation.Slides[0];

// Auf ein Textfeld zugreifen
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Fügen Sie einen Textabschnitt mit einem Hyperlink hinzu
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Hinzufügen eines Hyperlinks zu einer Form in einer Folie

1. Führen Sie die obigen Schritte aus, um ein neues C#-Projekt zu erstellen und die Aspose.Slides-Referenz hinzuzufügen.
2. Verwenden Sie den folgenden Code, um einen Hyperlink zu einer Form in einer Folie hinzuzufügen:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
Presentation presentation = new Presentation("presentation.pptx");

// Greifen Sie auf eine Folie zu
ISlide slide = presentation.Slides[0];

// Greifen Sie auf eine Form zu
IShape shape = slide.Shapes[1];

// Fügen Sie der Form einen Hyperlink hinzu
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Hinzufügen eines Hyperlinks zu einer Folie

1. Befolgen Sie die ersten Schritte, um Ihr C#-Projekt einzurichten und auf die Aspose.Slides-Bibliothek zu verweisen.
2. Verwenden Sie den folgenden Code, um einer Folie einen Hyperlink hinzuzufügen:

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
Presentation presentation = new Presentation("presentation.pptx");

// Greifen Sie auf eine Folie zu
ISlide slide = presentation.Slides[2];

// Fügen Sie der Folie einen Hyperlink hinzu
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Externe Hyperlinks hinzufügen

Neben internen Hyperlinks können Sie Ihren Folien auch externe Hyperlinks hinzufügen. Verwenden Sie den gleichen Ansatz wie oben, geben Sie jedoch die externe URL als Hyperlink-Ziel an.

## Ändern und Entfernen von Hyperlinks

Um einen vorhandenen Hyperlink zu ändern oder zu entfernen, können Sie auf die Hyperlink-Eigenschaften des jeweiligen Folienelements zugreifen und die erforderlichen Änderungen vornehmen.

## Abschluss

Das Hinzufügen von Hyperlinks zu Folien mit Aspose.Slides für .NET ist ein unkomplizierter Vorgang, der die Interaktivität Ihrer Präsentationen erheblich verbessern kann. Unabhängig davon, ob Sie auf externe Ressourcen verlinken oder eine Navigation innerhalb Ihrer Folien erstellen möchten, bietet Aspose.Slides die Tools, die Sie benötigen, um diese Aufgaben effizient zu erledigen.

## FAQs

### Wie entferne ich einen Hyperlink aus einem Textabschnitt?

 Um einen Hyperlink aus einem Textabschnitt zu entfernen, können Sie einfach den festlegen`HyperlinkClick` Eigentum zu`null` für diesen Teil.

### Kann ich Hyperlinks zu anderen Formen als Textfeldern hinzufügen?

Ja, Sie können mithilfe von Hyperlinks zu verschiedenen Formen hinzufügen, einschließlich Bildern und benutzerdefinierten Formen`HyperlinkClick` Eigentum.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Formaten kompatibel?

Ja, Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPTX, PPT und mehr.

### Wie kann ich die Hyperlinks in meiner Präsentation testen?

Sie können die Präsentation in einem PowerPoint-Viewer oder -Editor ausführen, um die Funktionalität der Hyperlinks zu testen.

### Wo kann ich die Aspose.Slides für .NET-Bibliothek herunterladen?

 Sie können die Aspose.Slides für .NET-Bibliothek von der Aspose-Website herunterladen:[Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net).