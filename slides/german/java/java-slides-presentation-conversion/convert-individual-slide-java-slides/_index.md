---
title: Einzelne Folien in Java-Folien konvertieren
linktitle: Einzelne Folien in Java-Folien konvertieren
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie anhand von Codebeispielen, wie Sie mit Aspose.Slides für Java einzelne PowerPoint-Folien Schritt für Schritt in HTML konvertieren.
weight: 12
url: /de/java/presentation-conversion/convert-individual-slide-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung zum Konvertieren einzelner Folien in Java-Folien

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einzelner Folien einer PowerPoint-Präsentation in HTML mithilfe von Aspose.Slides für Java. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Erklärungen, die Ihnen bei der Erledigung dieser Aufgabe helfen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Aspose.Slides für Java-Bibliothek installiert.
- Eine PowerPoint-Präsentationsdatei (`Individual-Slide.pptx`), die Sie konvertieren möchten.
- Java-Entwicklungsumgebung eingerichtet.

## Schritt 1: Einrichten des Projekts

1. Erstellen Sie ein Java-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie Ihrem Projekt die Bibliothek Aspose.Slides für Java hinzu.

## Schritt 2: Importieren Sie die erforderlichen Klassen

Importieren Sie in Ihre Java-Klasse die erforderlichen Klassen und richten Sie die Erstkonfiguration ein.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## Schritt 3: Definieren Sie die Hauptkonvertierungsmethode

 Erstellen Sie eine Methode zur Konvertierung einzelner Folien. Ersetzen Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Datei speichern
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Schritt 4: Implementieren des CustomFormattingController

 Erstellen Sie die`CustomFormattingController` Klasse zur Handhabung der benutzerdefinierten Formatierung während der Konvertierung.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## Schritt 5: Konvertierung durchführen

 Rufen Sie schließlich die`convertIndividualSlides` Methode zum Ausführen des Konvertierungsprozesses.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Vollständiger Quellcode zum Konvertieren einzelner Folien in Java-Folien

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Datei speichern
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## Abschluss

Sie haben erfolgreich einzelne Folien einer PowerPoint-Präsentation mit Aspose.Slides für Java in HTML konvertiert. Dieses Tutorial hat Ihnen den erforderlichen Code und die Schritte zur Erledigung dieser Aufgabe bereitgestellt. Sie können die Ausgabe und Formatierung nach Bedarf an Ihre spezifischen Anforderungen anpassen.

## Häufig gestellte Fragen

### Wie kann ich die HTML-Ausgabe weiter anpassen?

 Sie können die HTML-Ausgabe anpassen, indem Sie die`CustomFormattingController` Klasse. Passen Sie die`writeSlideStart` Und`writeSlideEnd` Methoden zum Ändern der HTML-Struktur und des Stils der Folie.

### Kann ich mehrere PowerPoint-Präsentationen auf einmal konvertieren?

 Ja, Sie können den Code so ändern, dass er mehrere Präsentationsdateien durchläuft und diese einzeln konvertiert, indem Sie den`convertIndividualSlides` Methode für jede Präsentation.

### Wie gehe ich mit zusätzlicher Formatierung für Formen und Text in Folien um?

 Sie können die`CustomFormattingController` Klasse zur Handhabung formspezifischer Formatierungen durch Implementierung der`writeShapeStart` Und`writeShapeEnd` Methoden und Anwenden einer benutzerdefinierten Formatierungslogik darin.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
