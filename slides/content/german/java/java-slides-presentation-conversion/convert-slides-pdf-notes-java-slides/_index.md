---
title: Folien mit Notizen in Java Slides in PDF konvertieren
linktitle: Folien mit Notizen in Java Slides in PDF konvertieren
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Folien mit Notizen in Java mit Aspose.Slides für Java in PDF konvertieren. Schritt-für-Schritt-Anleitung für Java-Entwickler. Verbessern Sie die Freigabe Ihrer Präsentation.
type: docs
weight: 19
url: /de/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Einführung zum Konvertieren von Folien in PDF mit Notizen in Java

In der Welt der digitalen Präsentationen ist die Möglichkeit, Folien mit begleitenden Notizen in PDF zu konvertieren, eine wertvolle Funktion. Java-Entwickler können dies mithilfe der Bibliothek Aspose.Slides für Java erreichen, die einen robusten Satz von Tools für die programmgesteuerte Arbeit mit PowerPoint-Präsentationen bietet. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie Folien mit Notizen mithilfe von Java und Aspose.Slides für Java in PDF konvertieren.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).

Nachdem wir nun unsere Gliederung haben, stürzen wir uns Schritt für Schritt in die Umsetzung.
## Schritt 1: Einrichten des Projekts

Erstellen Sie zunächst ein Java-Projekt und fügen Sie die Bibliothek Aspose.Slides für Java zu den Abhängigkeiten Ihres Projekts hinzu.

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

## Schritt 5: Foliengröße anpassen

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

## Vollständiger Quellcode zum Konvertieren von Folien in PDF mit Notizen in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
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
		// Folientyp und -größe festlegen
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
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

In diesem Tutorial haben wir gelernt, wie man Folien mit Aspose.Slides für Java in Java in PDF mit Notizen konvertiert. Wir haben das Einrichten des Projekts, das Laden der Präsentation, das Erstellen einer neuen Präsentation, das Kopieren von Folien, das Anpassen der Foliengröße, das Konfigurieren von PDF-Optionen und schließlich das Speichern der Präsentation als PDF mit Notizen behandelt.

## Häufig gestellte Fragen

### Wie installiere ich Aspose.Slides für Java?

Um Aspose.Slides für Java zu installieren, folgen Sie diesen Schritten:
1.  Laden Sie die Bibliothek herunter von[Hier](https://releases.aspose.com/slides/java/).
2. Fügen Sie die JAR-Datei zum Klassenpfad Ihres Java-Projekts hinzu.

### Kann ich die Position der Notizen im generierten PDF anpassen?

 Ja, Sie können die Position der Notizen anpassen, indem Sie die`NotesPositions` enum in den PDF-Optionen. In diesem Tutorial setzen wir es auf`BottomFull`, Sie können aber auch andere Optionen erkunden.

### Gibt es Lizenzanforderungen für die Verwendung von Aspose.Slides für Java?

Ja, Aspose.Slides für Java ist eine kommerzielle Bibliothek und Sie müssen möglicherweise eine Lizenz erwerben, um sie in der Produktion zu verwenden. Weitere Informationen zur Lizenzierung finden Sie auf der Aspose-Website.

### Kann ich mehrere Folien gleichzeitig konvertieren?

Natürlich! Sie können die Folien Ihrer Präsentation durchlaufen und in die neue Präsentation klonen. So können Sie mehrere Folien in einem Rutsch mit Notizen ins PDF-Format konvertieren.

### Wo finde ich weitere Dokumentation für Aspose.Slides für Java?

 Eine ausführliche Dokumentation zu Aspose.Slides für Java finden Sie auf der Website:[Aspose.Slides für Java API-Referenz](https://reference.aspose.com/slides/java/).