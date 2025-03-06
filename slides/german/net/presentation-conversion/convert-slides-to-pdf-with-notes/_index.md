---
title: Folien mit Notizen in PDF konvertieren
linktitle: Folien mit Notizen in PDF konvertieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Mit Aspose.Slides für .NET können Sie Präsentationsfolien mit Sprechernotizen mühelos in PDF konvertieren. Inhalt und Kontext bleiben nahtlos erhalten.
weight: 18
url: /de/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


# Schreiben Sie eine Schritt-für-Schritt-Anleitung zum Konvertieren von Folien in PDF mit Notizen unter Verwendung von Aspose.Slides für .NET

Suchen Sie nach einer zuverlässigen Möglichkeit, Ihre PowerPoint-Folien in das PDF-Format zu konvertieren und dabei alle wichtigen Notizen beizubehalten? Suchen Sie nicht weiter! In diesem umfassenden Tutorial führen wir Sie Schritt für Schritt durch den Prozess der Verwendung von Aspose.Slides für .NET, um diese Aufgabe zu erledigen.

## 1. Einleitung

Das Konvertieren von PowerPoint-Folien in PDF mit Notizen kann ein wertvolles Tool zum Teilen von Präsentationen sein und gleichzeitig sicherstellen, dass wichtige Kontexte und Kommentare erhalten bleiben. Aspose.Slides für .NET bietet eine leistungsstarke Lösung für diese Aufgabe.

## 2. Einrichten Ihrer Umgebung

Bevor wir uns in den Codierungsprozess stürzen, stellen Sie sicher, dass Sie die erforderliche Umgebung eingerichtet haben. Sie benötigen:

- Visual Studio oder Ihre bevorzugte .NET-Entwicklungsumgebung.
- Aspose.Slides für .NET-Bibliothek installiert.
- Eine PowerPoint-Präsentation mit Notizen, die Sie konvertieren möchten.

## 3. Laden der Präsentation

In Ihrem C#-Code müssen Sie die PowerPoint-Präsentation laden, die Sie konvertieren möchten. So können Sie das tun:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Klonen der Folie

Um sicherzustellen, dass Ihre PDF-Datei alle erforderlichen Folien mit Notizen enthält, können Sie diese aus der Originalpräsentation klonen. So geht's:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Foliengröße anpassen

Möglicherweise möchten Sie die Foliengröße an Ihr PDF anpassen. Mit Aspose.Slides für .NET können Sie dies ganz einfach tun:

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

Abschließend können Sie Ihre Präsentation mit Notizen als PDF speichern:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Fazit

Herzlichen Glückwunsch! Sie haben Ihre PowerPoint-Folien erfolgreich in ein PDF-Format konvertiert und dabei alle wichtigen Notizen beibehalten. Aspose.Slides für .NET macht diesen Vorgang unkompliziert und effizient.

## 9. Häufig gestellte Fragen

### F1: Kann ich das Layout der Notizen im PDF anpassen?

 Ja, Sie können das Layout der Notizen anpassen mit dem`INotesCommentsLayoutingOptions` in den PDF-Optionen.

### F2: Unterstützt Aspose.Slides für .NET andere Ausgabeformate außer PDF?

Ja, Aspose.Slides für .NET unterstützt verschiedene Ausgabeformate, darunter PPTX, DOCX und mehr.

### F3: Gibt es eine Testversion von Aspose.Slides für .NET?

 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten unter[https://releases.aspose.com/](https://releases.aspose.com/).

### F4: Wo erhalte ich Support für Aspose.Slides für .NET?

 Support und Community-Diskussionen finden Sie unter[https://forum.aspose.com/](https://forum.aspose.com/).

### F5: Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?

 Ja, Sie können eine temporäre Lizenz erwerben bei[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Zusammenfassend lässt sich sagen, dass Sie mit Aspose.Slides für .NET PowerPoint-Folien problemlos in das PDF-Format konvertieren können, ohne dass die Notizen verloren gehen. Es ist ein wertvolles Tool für Fachleute, die Präsentationen mit Kollegen und Kunden teilen müssen und dabei sicherstellen müssen, dass kein wichtiger Kontext verloren geht.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
