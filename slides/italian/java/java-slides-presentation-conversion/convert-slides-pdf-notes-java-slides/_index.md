---
"description": "Scopri come convertire le diapositive di PowerPoint in PDF con note in Java utilizzando Aspose.Slides per Java. Guida passo passo per sviluppatori Java. Migliora la condivisione delle tue presentazioni."
"linktitle": "Convertire le diapositive in PDF con le note in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Convertire le diapositive in PDF con le note in Java Slides"
"url": "/it/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertire le diapositive in PDF con le note in Java Slides


## Introduzione alla conversione di diapositive in PDF con note in Java

Nel mondo delle presentazioni digitali, la possibilità di convertire le diapositive in PDF con le relative note è una funzionalità preziosa. Gli sviluppatori Java possono ottenere questo risultato utilizzando la libreria Aspose.Slides per Java, che fornisce un solido set di strumenti per lavorare con le presentazioni PowerPoint a livello di codice. In questa guida passo passo, esploreremo come convertire le diapositive in PDF con le note utilizzando Java e Aspose.Slides per Java.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

Ora che abbiamo una panoramica, passiamo all'implementazione passo dopo passo.
## Fase 1: Impostazione del progetto

Per prima cosa, crea un progetto Java e aggiungi la libreria Aspose.Slides per Java alle dipendenze del progetto.

## Passaggio 2: caricamento della presentazione

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Passaggio 3: creazione di una nuova presentazione

```java
Presentation auxPresentation = new Presentation();
```

## Passaggio 4: Copia delle diapositive

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

## Codice sorgente completo per convertire diapositive in PDF con note in Java Slides

```java
// Percorso verso la directory dei documenti.
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
		// Impostazione del tipo e della dimensione della diapositiva
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

## Conclusione

In questo tutorial abbiamo imparato come convertire le diapositive in PDF con note in Java utilizzando Aspose.Slides per Java. Abbiamo trattato la configurazione del progetto, il caricamento della presentazione, la creazione di una nuova presentazione, la copia delle diapositive, la regolazione delle dimensioni delle diapositive, la configurazione delle opzioni PDF e, infine, il salvataggio della presentazione in PDF con note.

## Domande frequenti

### Come faccio a installare Aspose.Slides per Java?

Per installare Aspose.Slides per Java, segui questi passaggi:
1. Scarica la libreria da [Qui](https://releases.aspose.com/slides/java/).
2. Aggiungi il file JAR al classpath del tuo progetto Java.

### Posso personalizzare la posizione delle note nel PDF generato?

Sì, puoi personalizzare la posizione delle note modificando `NotesPositions` enum nelle opzioni PDF. In questo tutorial, lo impostiamo su `BottomFull`, ma puoi esplorare anche altre opzioni.

### Esistono requisiti di licenza per utilizzare Aspose.Slides per Java?

Sì, Aspose.Slides per Java è una libreria commerciale e potrebbe essere necessario acquistare una licenza per utilizzarla in produzione. Visita il sito web di Aspose per i dettagli sulle licenze.

### Posso convertire più diapositive contemporaneamente?

Certamente! Puoi scorrere le diapositive della tua presentazione e clonarle nella nuova presentazione, convertendo più diapositive in PDF con note in una sola volta.

### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?

Puoi trovare la documentazione dettagliata per Aspose.Slides per Java sul sito: [Riferimento API Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}