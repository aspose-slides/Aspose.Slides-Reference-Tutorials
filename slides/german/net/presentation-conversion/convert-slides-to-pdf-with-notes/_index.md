---
"description": "Konvertieren Sie Präsentationsfolien mit Sprechernotizen mühelos in PDF mit Aspose.Slides für .NET. Inhalt und Kontext bleiben nahtlos erhalten."
"linktitle": "Folien mit Notizen in PDF konvertieren"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Folien mit Notizen in PDF konvertieren"
"url": "/de/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Folien mit Notizen in PDF konvertieren


# Schreiben Sie eine Schritt-für-Schritt-Anleitung zum Konvertieren von Folien in PDF mit Notizen mithilfe von Aspose.Slides für .NET

Suchen Sie nach einer zuverlässigen Methode, Ihre PowerPoint-Folien ins PDF-Format zu konvertieren und dabei alle wichtigen Notizen zu erhalten? Dann sind Sie hier richtig! In diesem umfassenden Tutorial führen wir Sie Schritt für Schritt durch die Verwendung von Aspose.Slides für .NET.

## 1. Einleitung

Das Konvertieren von PowerPoint-Folien in PDF mit Notizen kann ein wertvolles Werkzeug für die gemeinsame Nutzung von Präsentationen sein und gleichzeitig sicherstellen, dass wichtige Kontexte und Kommentare erhalten bleiben. Aspose.Slides für .NET bietet hierfür eine leistungsstarke Lösung.

## 2. Einrichten Ihrer Umgebung

Bevor wir mit der Programmierung beginnen, stellen Sie sicher, dass Sie die erforderliche Umgebung eingerichtet haben. Sie benötigen:

- Visual Studio oder Ihre bevorzugte .NET-Entwicklungsumgebung.
- Aspose.Slides für die .NET-Bibliothek installiert.
- Eine PowerPoint-Präsentation mit Notizen, die Sie konvertieren möchten.

## 3. Laden der Präsentation

Laden Sie in Ihrem C#-Code die PowerPoint-Präsentation, die Sie konvertieren möchten. So geht's:

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

Möglicherweise möchten Sie die Foliengröße an Ihr PDF anpassen. Mit Aspose.Slides für .NET ist dies ganz einfach:

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

## 7. Speichern als PDF mit Notizen

Abschließend können Sie Ihre Präsentation mit Notizen als PDF speichern:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Fazit

Herzlichen Glückwunsch! Sie haben Ihre PowerPoint-Folien erfolgreich ins PDF-Format konvertiert und dabei alle wichtigen Notizen beibehalten. Aspose.Slides für .NET macht diesen Prozess unkompliziert und effizient.

## 9. FAQs

### F1: Kann ich das Layout der Notizen im PDF anpassen?

Ja, Sie können das Layout der Notizen anpassen, indem Sie `INotesCommentsLayoutingOptions` in den PDF-Optionen.

### F2: Unterstützt Aspose.Slides für .NET andere Ausgabeformate außer PDF?

Ja, Aspose.Slides für .NET unterstützt verschiedene Ausgabeformate, darunter PPTX, DOCX und mehr.

### F3: Gibt es eine Testversion für Aspose.Slides für .NET?

Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten unter [https://releases.aspose.com/](https://releases.aspose.com/).

### F4: Wo erhalte ich Support für Aspose.Slides für .NET?

Support und Community-Diskussionen finden Sie unter [https://forum.aspose.com/](https://forum.aspose.com/).

### F5: Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?

Ja, Sie können eine temporäre Lizenz erwerben bei [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Zusammenfassend lässt sich sagen, dass Sie mit Aspose.Slides für .NET PowerPoint-Folien problemlos ins PDF-Format konvertieren können, ohne dass Notizen verloren gehen. Es ist ein wertvolles Tool für Fachleute, die Präsentationen mit Kollegen und Kunden teilen und gleichzeitig sicherstellen müssen, dass wichtige Inhalte erhalten bleiben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}