---
title: Converti diapositive individuali in diapositive Java
linktitle: Converti diapositive individuali in diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come convertire singole diapositive di PowerPoint in HTML passo dopo passo con esempi di codice utilizzando Aspose.Slides per Java.
weight: 12
url: /it/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti diapositive individuali in diapositive Java


## Introduzione alla conversione di singole diapositive in diapositive Java

In questo tutorial, esamineremo il processo di conversione di singole diapositive da una presentazione PowerPoint in HTML utilizzando Aspose.Slides per Java. Questa guida passo passo ti fornirà il codice sorgente e le spiegazioni per aiutarti a raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per la libreria Java installata.
- Un file di presentazione di PowerPoint (`Individual-Slide.pptx`) che desideri convertire.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: impostare il progetto

1. Crea un progetto Java nel tuo ambiente di sviluppo preferito.
2. Aggiungi la libreria Aspose.Slides per Java al tuo progetto.

## Passaggio 2: importa le classi necessarie

Nella tua classe Java, importa le classi richieste e imposta la configurazione iniziale.

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

## Passaggio 3: definire il metodo di conversione principale

 Crea un metodo per eseguire la conversione di singole diapositive. Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Salvataggio del file
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Passaggio 4: implementare CustomFormattingController

 Crea il`CustomFormattingController` classe per gestire la formattazione personalizzata durante la conversione.

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

## Passaggio 5: eseguire la conversione

 Infine, chiama il`convertIndividualSlides` metodo per eseguire il processo di conversione.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Codice sorgente completo per convertire singole diapositive in diapositive Java

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Salvataggio del file
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

## Conclusione

Hai convertito con successo singole diapositive da una presentazione PowerPoint in HTML utilizzando Aspose.Slides per Java. Questo tutorial ti ha fornito il codice e i passaggi necessari per portare a termine questa attività. Sentiti libero di personalizzare l'output e la formattazione in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso personalizzare ulteriormente l'output HTML?

 È possibile personalizzare l'output HTML modificando il file`CustomFormattingController` classe. Aggiusta il`writeSlideStart` E`writeSlideEnd` metodi per modificare la struttura e lo stile HTML della diapositiva.

### Posso convertire più presentazioni PowerPoint in una volta sola?

 Sì, puoi modificare il codice per scorrere più file di presentazione e convertirli individualmente chiamando il file`convertIndividualSlides` metodo per ogni presentazione.

### Come posso gestire la formattazione aggiuntiva per forme e testo all'interno delle diapositive?

 Puoi estendere il`CustomFormattingController` classe per gestire la formattazione specifica della forma implementando il file`writeShapeStart` E`writeShapeEnd` metodi e applicando la logica di formattazione personalizzata al loro interno.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
