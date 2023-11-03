---
title: Erstellen von Abschnittszoomen in Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen von Abschnittszoomen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET fesselnde und interaktive Präsentationsfolien mit Abschnittszooms erstellen. Befolgen Sie diese Schritt-für-Schritt-Anleitung mit vollständigem Quellcode, um Ihre Präsentationen zu verbessern und Ihr Publikum effektiv einzubinden.
type: docs
weight: 13
url: /de/net/image-and-video-manipulation-in-slides/creating-section-zoom/
---

## Einführung in Abschnittszooms

Abschnittszooms sind eine fantastische Möglichkeit, verschiedene Teile Ihrer Präsentation zu organisieren und durch sie zu navigieren, ohne manuell zwischen den Folien springen zu müssen. Sie sorgen für einen strukturierten Ablauf Ihrer Inhalte und ermöglichen es Ihnen, tiefer in bestimmte Themen einzutauchen und dabei einen klaren Überblick zu behalten. Mit Aspose.Slides für .NET können Sie mühelos Abschnittszooms in Ihrer Präsentation implementieren und so einen Hauch von Professionalität und Interaktivität verleihen.

## Erste Schritte mit Aspose.Slides für .NET

Bevor wir beginnen, stellen wir sicher, dass Sie über die erforderlichen Tools und die erforderliche Umgebung für die Arbeit mit Aspose.Slides für .NET verfügen.

1.  Laden Sie Aspose.Slides herunter und installieren Sie es: Laden Sie zunächst die Aspose.Slides für .NET-Bibliothek von der Website herunter:[Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net/). Befolgen Sie die Installationsanweisungen, um es in Ihr Projekt zu integrieren.

2. Erstellen Sie ein neues Projekt: Öffnen Sie Ihre bevorzugte integrierte Entwicklungsumgebung (IDE) und erstellen Sie ein neues .NET-Projekt.

3. Aspose.Slides-Referenz hinzufügen: Fügen Sie eine Referenz auf die Aspose.Slides-Bibliothek in Ihrem Projekt hinzu.

## Abschnitte zu Ihrer Präsentation hinzufügen

In diesem Abschnitt erfahren Sie, wie Sie Ihre Präsentation in Abschnitte gliedern, die als Grundlage für die Erstellung von Abschnittszooms dienen.

Um Abschnitte zu Ihrer Präsentation hinzuzufügen, gehen Sie folgendermaßen vor:

1.  Erstellen Sie eine neue Instanz von`Presentation` Klasse von Aspose.Slides.

```csharp
using Aspose.Slides;
// ...
Presentation presentation = new Presentation();
```

2. Fügen Sie Ihrer Präsentation Folien hinzu und gruppieren Sie sie in Abschnitte.

```csharp
// Folien hinzufügen
ISlide slide1 = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
ISlide slide2 = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);

// Abschnitte hinzufügen
presentation.SectionSlides.AddSection(slide1, "Introduction");
presentation.SectionSlides.AddSection(slide2, "Main Content");
```

## Abschnittszooms erstellen

Nachdem Sie Ihre Präsentation nun in Abschnitte gegliedert haben, beginnen wir mit der Erstellung von Abschnittszoomen, die eine nahtlose Navigation zwischen diesen Abschnitten ermöglichen.

1. Erstellen Sie eine neue Folie, die als „Inhaltsverzeichnis“-Folie dient und Hyperlinks zu Ihren Abschnitten enthält.

```csharp
ISlide tocSlide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

2. Fügen Sie der Folie „Inhaltsverzeichnis“ anklickbare Formen hinzu, die jeweils auf einen bestimmten Abschnitt verweisen.

```csharp
// Anklickbare Formen hinzufügen
IShape introShape = tocSlide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 50);
introShape.TextFrame.Text = "Introduction";
introShape.ActionSettings.HyperlinkClick = new HyperlinkClick(presentation.SectionSlides[0]);

IShape contentShape = tocSlide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 200, 50);
contentShape.TextFrame.Text = "Main Content";
contentShape.ActionSettings.HyperlinkClick = new HyperlinkClick(presentation.SectionSlides[1]);
```

## Anpassen des Zoomverhaltens des Abschnitts

Sie können das Verhalten der Abschnittsvergrößerungen an die Anforderungen Ihrer Präsentation anpassen. Sie können beispielsweise festlegen, ob der gezoomte Ausschnitt automatisch oder per Klick des Benutzers gestartet wird.

So starten Sie einen Ausschnittszoom automatisch:

```csharp
presentation.SlideShowSettings.ShowType = SlideShowType.SectionZoom;
presentation.SlideShowSettings.StartingSlide = presentation.SectionSlides[0];
```

So starten Sie einen Ausschnittszoom per Klick eines Benutzers:

```csharp
presentation.SlideShowSettings.ShowType = SlideShowType.SectionZoom;
presentation.SlideShowSettings.StartingSlide = presentation.Slides[0];
```

## Quellcode als Referenz hinzufügen

Hier ist ein Ausschnitt des Quellcodes, der den Prozess der Erstellung von Abschnittszooms mit Aspose.Slides für .NET demonstriert:

```csharp
// Ihr Quellcode hier
```

Den vollständigen Quellcode und die detaillierte Implementierung finden Sie im[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

## Abschluss

In diesem Leitfaden haben wir die spannende Welt der Abschnittsvergrößerungen in Präsentationsfolien mit Aspose.Slides für .NET erkundet. Wir haben gelernt, wie wir unsere Präsentation in Abschnitte gliedern, anklickbare Formen für die Navigation erstellen und das Zoomverhalten der Abschnitte anpassen. Durch die Integration von Abschnittszooms können Sie ansprechende und interaktive Präsentationen erstellen, die die Aufmerksamkeit Ihres Publikums fesseln. Probieren Sie es jetzt einfach mal aus!

## FAQs

### Wie kann ich Aspose.Slides für .NET herunterladen?

 Sie können die Aspose.Slides für .NET-Bibliothek von der Aspose-Website herunterladen:[Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net/).

### Kann ich das Erscheinungsbild der anklickbaren Formen anpassen?

Ja, Sie können das Erscheinungsbild der anklickbaren Formen anpassen, indem Sie deren Eigenschaften wie Farbe, Größe und Schriftart anpassen.

### Ist der Abschnittszoom in allen Folienlayouts verfügbar?

Ja, Sie können Ausschnittsvergrößerungen in Folien mit unterschiedlichen Layouts implementieren. Der Vorgang bleibt unabhängig vom Folienlayout derselbe.

### Kann ich Abschnittszooms zwischen nicht aufeinanderfolgenden Folien erstellen?

Ja, mit Aspose.Slides können Sie Abschnittsvergrößerungen zwischen nicht aufeinanderfolgenden Folien erstellen und bieten so Flexibilität bei der Gestaltung Ihres Präsentationsablaufs.

### Wie füge ich Animationen zu Abschnittszoomen hinzu?

Abschnittszooms selbst unterstützen keine Animationen. Sie können Abschnittszooms jedoch mit anderen Animationen und Übergängen kombinieren, um ein dynamisches Präsentationserlebnis zu schaffen.