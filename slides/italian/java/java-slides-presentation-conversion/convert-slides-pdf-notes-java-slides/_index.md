---
title: Converti diapositive in PDF con le note in Diapositive Java
linktitle: Converti diapositive in PDF con le note in Diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come convertire le diapositive di PowerPoint in PDF con note in Java utilizzando Aspose.Slides per Java. Guida passo passo per gli sviluppatori Java. Migliora la condivisione della tua presentazione.
weight: 19
url: /it/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione alla conversione di diapositive in PDF con note in Java

Nel mondo delle presentazioni digitali, la possibilità di convertire diapositive in PDF con note di accompagnamento è una caratteristica preziosa. Gli sviluppatori Java possono raggiungere questo obiettivo utilizzando la libreria Aspose.Slides per Java, che fornisce un robusto set di strumenti per lavorare con le presentazioni PowerPoint a livello di codice. In questa guida passo passo, esploreremo come convertire le diapositive in PDF con note utilizzando Java e Aspose.Slides per Java.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

Ora che abbiamo il nostro schema, tuffiamoci nell'implementazione passo dopo passo.
## Passaggio 1: impostazione del progetto

Innanzitutto, crea un progetto Java e aggiungi la libreria Aspose.Slides per Java alle dipendenze del tuo progetto.

## Passaggio 2: caricamento della presentazione

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Passaggio 3: creazione di una nuova presentazione

```java
Presentation auxPresentation = new Presentation();
```

## Passaggio 4: copia delle diapositive

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Passaggio 5: regolazione delle dimensioni della diapositiva

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Passaggio 6: configurazione delle opzioni PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Passaggio 7: salvataggio in formato PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Codice sorgente completo per convertire diapositive in PDF con note in diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza di un oggetto Presentation che rappresenta un file di presentazione
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Impostazione del tipo e delle dimensioni della diapositiva
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

## Conclusione

In questo tutorial, abbiamo imparato come convertire le diapositive in PDF con note in Java utilizzando Aspose.Slides per Java. Abbiamo trattato l'impostazione del progetto, il caricamento della presentazione, la creazione di una nuova presentazione, la copia delle diapositive, la regolazione delle dimensioni della diapositiva, la configurazione delle opzioni PDF e, infine, il salvataggio della presentazione come PDF con note.

## Domande frequenti

### Come installo Aspose.Slides per Java?

Per installare Aspose.Slides per Java, attenersi alla seguente procedura:
1.  Scarica la libreria da[Qui](https://releases.aspose.com/slides/java/).
2. Aggiungi il file JAR al classpath del tuo progetto Java.

### Posso personalizzare la posizione delle note nel PDF generato?

 Sì, puoi personalizzare la posizione delle note modificando il file`NotesPositions` enum nelle opzioni PDF. In questo tutorial lo impostiamo su`BottomFull`, ma puoi esplorare anche altre opzioni.

### Esistono requisiti di licenza per l'utilizzo di Aspose.Slides per Java?

Sì, Aspose.Slides per Java è una libreria commerciale e potrebbe essere necessario acquisire una licenza per utilizzarla in produzione. Visitare il sito Web Aspose per i dettagli sulla licenza.

### Posso convertire più diapositive contemporaneamente?

Certamente! Puoi scorrere le diapositive della presentazione e clonarle nella nuova presentazione, consentendoti di convertire più diapositive in PDF con note in una volta sola.

### Dove posso trovare ulteriore documentazione per Aspose.Slides per Java?

 È possibile trovare la documentazione dettagliata per Aspose.Slides per Java sul sito:[Aspose.Slides per riferimento API Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
