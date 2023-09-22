---
title: Konvertieren Sie Folien mit Notizen in PDF
linktitle: Konvertieren Sie Folien mit Notizen in PDF
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Konvertieren Sie Präsentationsfolien mit Vortragsnotizen mühelos in PDF mit Aspose.Slides für .NET. Behalten Sie Inhalte und Kontext nahtlos bei.
type: docs
weight: 18
url: /de/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

# Schreiben Sie eine Schritt-für-Schritt-Anleitung zum Konvertieren von Folien in PDF mit Notizen mithilfe von Aspose.Slides für .NET

Suchen Sie nach einer zuverlässigen Möglichkeit, Ihre PowerPoint-Folien in das PDF-Format zu konvertieren und dabei alle wichtigen Notizen beizubehalten? Suchen Sie nicht weiter! In diesem umfassenden Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Verwendung von Aspose.Slides für .NET, um diese Aufgabe zu erfüllen.

## 1. Einleitung

Das Konvertieren von PowerPoint-Folien in PDF mit Notizen kann ein wertvolles Werkzeug zum Teilen von Präsentationen sein und gleichzeitig sicherstellen, dass wichtige Kontexte und Kommentare erhalten bleiben. Aspose.Slides für .NET bietet eine leistungsstarke Lösung für diese Aufgabe.

## 2. Einrichten Ihrer Umgebung

Bevor wir uns mit dem Codierungsprozess befassen, stellen Sie sicher, dass Sie die erforderliche Umgebung eingerichtet haben. Du brauchst:

- Visual Studio oder Ihre bevorzugte .NET-Entwicklungsumgebung.
- Aspose.Slides für .NET-Bibliothek installiert.
- Eine PowerPoint-Präsentation mit Notizen, die Sie konvertieren möchten.

## 3. Laden der Präsentation

In Ihrem C#-Code müssen Sie die PowerPoint-Präsentation laden, die Sie konvertieren möchten. So können Sie es machen:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Klonen der Folie

Um sicherzustellen, dass Ihr PDF alle notwendigen Folien mit Notizen enthält, können Sie diese aus der Originalpräsentation klonen. Hier ist wie:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Anpassen der Foliengröße

Möglicherweise möchten Sie die Foliengröße an Ihre PDF-Datei anpassen. Mit Aspose.Slides für .NET können Sie dies ganz einfach tun:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. PDF-Optionen konfigurieren

Um zu steuern, wie Ihre Notizen im PDF angezeigt werden, können Sie die PDF-Optionen konfigurieren:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Als PDF mit Notizen speichern

Abschließend können Sie Ihre Präsentation als PDF mit Notizen speichern:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Fazit

Glückwunsch! Sie haben Ihre PowerPoint-Folien erfolgreich in ein PDF-Format konvertiert und dabei alle wichtigen Notizen beibehalten. Aspose.Slides für .NET macht diesen Prozess unkompliziert und effizient.

## 9. FAQs

### F1: Kann ich das Layout der Notizen im PDF anpassen?

 Ja, Sie können das Layout der Notizen mithilfe von anpassen`INotesCommentsLayoutingOptions` in den PDF-Optionen.

### F2: Unterstützt Aspose.Slides für .NET neben PDF auch andere Ausgabeformate?

Ja, Aspose.Slides für .NET unterstützt verschiedene Ausgabeformate, einschließlich PPTX, DOCX und mehr.

### F3: Gibt es eine Testversion für Aspose.Slides für .NET?

 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET unter erhalten[https://releases.aspose.com/](https://releases.aspose.com/).

### F4: Wo erhalte ich Unterstützung für Aspose.Slides für .NET?

 Unterstützung und Community-Diskussionen finden Sie unter[https://forum.aspose.com/](https://forum.aspose.com/).

### F5: Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?

 Ja, Sie können eine temporäre Lizenz erwerben unter[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Zusammenfassend lässt sich sagen, dass Sie mit Aspose.Slides für .NET PowerPoint-Folien problemlos in das PDF-Format konvertieren können, wobei die Notizen erhalten bleiben. Es ist ein wertvolles Tool für Fachleute, die Präsentationen mit Kollegen und Kunden teilen und gleichzeitig sicherstellen müssen, dass wichtiger Kontext nicht verloren geht.