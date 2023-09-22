---
title: Konvertieren Sie Folien mit Notizen in Java Slides in PDF
linktitle: Konvertieren Sie Folien mit Notizen in Java Slides in PDF
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java PowerPoint-Folien mit Notizen in Java in PDF konvertieren. Schritt-für-Schritt-Anleitung für Java-Entwickler. Verbessern Sie das Teilen Ihrer Präsentation.
type: docs
weight: 19
url: /de/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Einführung in die Konvertierung von Folien in PDF mit Notizen in Java

In der Welt der digitalen Präsentationen ist die Möglichkeit, Folien mit begleitenden Notizen in PDF zu konvertieren, eine wertvolle Funktion. Java-Entwickler können dies mithilfe der Aspose.Slides for Java-Bibliothek erreichen, die einen robusten Satz an Tools für die programmgesteuerte Arbeit mit PowerPoint-Präsentationen bereitstellt. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Java und Aspose.Slides für Java Folien mit Notizen in PDF konvertieren.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/java/).

Nachdem wir nun unsere Gliederung haben, gehen wir Schritt für Schritt in die Umsetzung ein.
## Schritt 1: Einrichten des Projekts

Erstellen Sie zunächst ein Java-Projekt und fügen Sie die Aspose.Slides for Java-Bibliothek zu den Abhängigkeiten Ihres Projekts hinzu.

## Schritt 2: Laden der Präsentation

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Schritt 3: Erstellen einer neuen Präsentation

```java
Presentation auxPresentation = new Presentation();
```

## Schritt 4: Folien kopieren

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Schritt 5: Anpassen der Foliengröße

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Schritt 6: PDF-Optionen konfigurieren

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Schritt 7: Als PDF speichern

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Vollständiger Quellcode zum Konvertieren von Folien in PDF mit Notizen in Java Slides

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Festlegen von Folientyp und -größe
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), Presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java Folien mit Notizen in Java in PDF konvertiert. Wir haben das Einrichten des Projekts, das Laden der Präsentation, das Erstellen einer neuen Präsentation, das Kopieren von Folien, das Anpassen der Foliengröße, das Konfigurieren von PDF-Optionen und schließlich das Speichern der Präsentation als PDF mit Notizen behandelt.

## FAQs

### Wie installiere ich Aspose.Slides für Java?

Um Aspose.Slides für Java zu installieren, gehen Sie folgendermaßen vor:
1.  Laden Sie die Bibliothek herunter von[Hier](https://releases.aspose.com/slides/java/).
2. Fügen Sie die JAR-Datei zum Klassenpfad Ihres Java-Projekts hinzu.

### Kann ich die Position der Notizen im generierten PDF anpassen?

 Ja, Sie können die Position der Notizen anpassen, indem Sie die ändern`NotesPositions` enum in den PDF-Optionen. In diesem Tutorial haben wir es auf eingestellt`BottomFull`, aber Sie können auch andere Optionen erkunden.

### Gibt es Lizenzanforderungen für die Verwendung von Aspose.Slides für Java?

Ja, Aspose.Slides für Java ist eine kommerzielle Bibliothek und Sie müssen möglicherweise eine Lizenz erwerben, um sie in der Produktion verwenden zu können. Einzelheiten zur Lizenzierung finden Sie auf der Aspose-Website.

### Kann ich mehrere Folien gleichzeitig konvertieren?

Sicherlich! Sie können die Folien in Ihrer Präsentation in einer Schleife durchlaufen und sie in die neue Präsentation klonen, sodass Sie mehrere Folien auf einmal in PDF mit Notizen konvertieren können.

### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?

 Eine ausführliche Dokumentation zu Aspose.Slides für Java finden Sie auf der Website:[Aspose.Slides für Java API-Referenz](https://reference.aspose.com/slides/java/).