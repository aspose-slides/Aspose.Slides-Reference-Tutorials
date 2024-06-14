---
title: Converteer individuele dia's in Java-dia's
linktitle: Converteer individuele dia's in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer stap voor stap hoe u afzonderlijke PowerPoint-dia's naar HTML kunt converteren met codevoorbeelden met behulp van Aspose.Slides voor Java.
type: docs
weight: 12
url: /nl/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Inleiding tot het converteren van individuele dia's in Java-dia's

In deze zelfstudie doorlopen we het proces van het converteren van afzonderlijke dia's van een PowerPoint-presentatie naar HTML met behulp van Aspose.Slides voor Java. Deze stapsgewijze handleiding biedt u de broncode en uitleg om u te helpen deze taak te volbrengen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

- Aspose.Slides voor Java-bibliotheek geïnstalleerd.
- Een PowerPoint-presentatiebestand (`Individual-Slide.pptx`) die u wilt converteren.
- Java-ontwikkelomgeving opgezet.

## Stap 1: Stel het project in

1. Creëer een Java-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg de Aspose.Slides voor Java-bibliotheek toe aan uw project.

## Stap 2: importeer de benodigde klassen

Importeer in uw Java-klasse de vereiste klassen en stel de initiële configuratie in.

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

## Stap 3: Definieer de hoofdconversiemethode

 Creëer een methode om de conversie van individuele dia's uit te voeren. Zorg ervoor dat u vervangt`"Your Document Directory"` met het daadwerkelijke pad naar uw documentmap.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Bestand opslaan
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Stap 4: Implementeer de CustomFormattingController

 Maak de`CustomFormattingController` class om aangepaste opmaak tijdens de conversie af te handelen.

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

## Stap 5: Voer de conversie uit

 Bel ten slotte de`convertIndividualSlides` methode om het conversieproces uit te voeren.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Volledige broncode voor het converteren van individuele dia's in Java-dia's

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Bestand opslaan
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

## Conclusie

hebt met succes afzonderlijke dia's van een PowerPoint-presentatie naar HTML geconverteerd met Aspose.Slides voor Java. Deze tutorial heeft u voorzien van de benodigde code en stappen om deze taak te volbrengen. U kunt de uitvoer en opmaak naar wens aanpassen aan uw specifieke vereisten.

## Veelgestelde vragen

### Hoe kan ik de HTML-uitvoer verder aanpassen?

 U kunt de HTML-uitvoer aanpassen door het`CustomFormattingController` klas. Pas de .... aan`writeSlideStart` En`writeSlideEnd` methoden om de HTML-structuur en -stijl van de dia te wijzigen.

### Kan ik meerdere PowerPoint-presentaties in één keer converteren?

 Ja, u kunt de code wijzigen om meerdere presentatiebestanden te doorlopen en deze afzonderlijk te converteren door de`convertIndividualSlides` methode voor elke presentatie.

### Hoe ga ik om met extra opmaak voor vormen en tekst in dia's?

 Je kunt de`CustomFormattingController` klasse om vormspecifieke opmaak af te handelen door het implementeren van de`writeShapeStart` En`writeShapeEnd` methoden en het toepassen van aangepaste opmaaklogica daarin.