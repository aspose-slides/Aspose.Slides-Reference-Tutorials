---
title: Konvertieren Sie einzelne Folien in Java-Folien
linktitle: Konvertieren Sie einzelne Folien in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie anhand von Codebeispielen mit Aspose.Slides für Java Schritt für Schritt, wie Sie einzelne PowerPoint-Folien in HTML konvertieren.
type: docs
weight: 12
url: /de/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Einführung in das Konvertieren einzelner Folien in Java-Folien

In diesem Tutorial führen wir den Prozess der Konvertierung einzelner Folien aus einer PowerPoint-Präsentation in HTML mit Aspose.Slides für Java durch. Diese Schritt-für-Schritt-Anleitung stellt Ihnen Quellcode und Erklärungen zur Verfügung, die Ihnen bei der Bewältigung dieser Aufgabe helfen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.Slides für Java-Bibliothek installiert.
- Eine PowerPoint-Präsentationsdatei (`Individual-Slide.pptx`), die Sie konvertieren möchten.
- Einrichtung einer Java-Entwicklungsumgebung.

## Schritt 1: Richten Sie das Projekt ein

1. Erstellen Sie ein Java-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie Ihrem Projekt die Aspose.Slides for Java-Bibliothek hinzu.

## Schritt 2: Importieren Sie die erforderlichen Klassen

Importieren Sie in Ihrer Java-Klasse die erforderlichen Klassen und richten Sie die Erstkonfiguration ein.

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

 Erstellen Sie eine Methode, um die Konvertierung einzelner Folien durchzuführen. Unbedingt austauschen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

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

## Schritt 4: Implementieren Sie den CustomFormattingController

 Erstellen Sie die`CustomFormattingController` Klasse, um benutzerdefinierte Formatierungen während der Konvertierung zu verarbeiten.

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

## Schritt 5: Führen Sie die Konvertierung aus

 Rufen Sie abschließend die an`convertIndividualSlides` Methode zum Ausführen des Konvertierungsprozesses.

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

Sie haben mit Aspose.Slides für Java erfolgreich einzelne Folien einer PowerPoint-Präsentation in HTML konvertiert. Dieses Tutorial lieferte Ihnen den notwendigen Code und die Schritte, um diese Aufgabe zu erfüllen. Sie können die Ausgabe und Formatierung jederzeit an Ihre spezifischen Anforderungen anpassen.

## FAQs

### Wie kann ich die HTML-Ausgabe weiter anpassen?

 Sie können die HTML-Ausgabe anpassen, indem Sie die ändern`CustomFormattingController` Klasse. Verstelle die`writeSlideStart` Und`writeSlideEnd` Methoden zum Ändern der HTML-Struktur und des Stils der Folie.

### Kann ich mehrere PowerPoint-Präsentationen auf einmal konvertieren?

 Ja, Sie können den Code so ändern, dass er mehrere Präsentationsdateien durchläuft und diese einzeln konvertiert, indem Sie die aufrufen`convertIndividualSlides` Methode für jede Präsentation.

### Wie gehe ich mit zusätzlichen Formatierungen für Formen und Text in Folien um?

Sie können die erweitern`CustomFormattingController` Klasse zur Handhabung formspezifischer Formatierung durch Implementierung von`writeShapeStart` Und`writeShapeEnd` Methoden und die Anwendung benutzerdefinierter Formatierungslogik darin.