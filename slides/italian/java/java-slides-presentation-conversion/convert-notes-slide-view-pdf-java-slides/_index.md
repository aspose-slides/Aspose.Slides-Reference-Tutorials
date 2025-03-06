---
title: Converti la visualizzazione diapositive di Notes in PDF in Diapositive Java
linktitle: Converti la visualizzazione diapositive di Notes in PDF in Diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come convertire presentazioni PowerPoint con note in PDF utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo con il codice sorgente.
weight: 16
url: /it/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione alla conversione della visualizzazione diapositive di Notes in PDF in Diapositive Java

In questo tutorial, ti guideremo attraverso il processo di conversione di una presentazione PowerPoint con la visualizzazione delle diapositive delle note in un PDF utilizzando la libreria Aspose.Slides per Java. Questa libreria fornisce potenti funzionalità per lavorare con presentazioni PowerPoint in Java.

## Prerequisiti
1. Kit di sviluppo Java (JDK) installato.
2. Libreria Aspose.Slides per Java aggiunta al tuo progetto.

## Passaggio 1: importa le classi necessarie
Per iniziare, dovrai importare le classi necessarie dalla libreria Aspose.Slides. Ecco il codice per farlo:

```java
import com.aspose.slides.*;
```

## Passaggio 2: carica la presentazione di PowerPoint
 Dovresti avere il file di presentazione di PowerPoint pronto. Sostituire`"Your Document Directory"` con il percorso della directory in cui si trova il file di presentazione. Ecco il codice per caricare la presentazione:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Passaggio 3: configura le opzioni PDF
Ora configuriamo le opzioni di esportazione PDF. Nello specifico, imposteremo la posizione delle note su "BottomFull" per includere le note sotto le diapositive nel PDF. Ecco il codice:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Puoi personalizzare altre opzioni PDF in base alle tue esigenze.

## Passaggio 4: salva la presentazione come PDF con note
 Infine, salviamo la presentazione come file PDF, comprese le note. È possibile specificare il nome del file di output (ad esempio,`"Pdf_Notes_out.pdf"`) e scegli il formato (`SaveFormat.Pdf`). Ecco il codice per farlo:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Passaggio 5: ripulire le risorse
Non dimenticare di rilasciare le risorse una volta terminata la presentazione:

```java
if (presentation != null) presentation.dispose();
```

## Codice sorgente completo per convertire la visualizzazione delle diapositive delle note in PDF nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza di un oggetto Presentation che rappresenta un file di presentazione
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Salvataggio della presentazione in note PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come convertire presentazioni PowerPoint con visualizzazioni di diapositive di note in PDF utilizzando la libreria Aspose.Slides per Java. Abbiamo seguito una guida passo passo con il codice sorgente per ottenere questa conversione. Ecco i punti salienti:

## Domande frequenti

### Come posso modificare la posizione delle note nel PDF?

 È possibile modificare la posizione delle note nel PDF modificando il file`setNotesPosition` argomento del metodo. Ad esempio, puoi impostarlo su`NotesPositions.RightFull` per posizionare le note sul lato destro delle diapositive.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Posso personalizzare ulteriormente l'esportazione in PDF?

 Sì, puoi personalizzare l'esportazione in PDF regolando varie opzioni nel file`PdfOptions` oggetto. Ad esempio, puoi impostare la qualità, la compressione e altri parametri in base alle tue esigenze.

### Come posso ottenere Aspose.Slides per Java?

 È possibile scaricare Aspose.Slides per Java dal sito Web all'indirizzo[Qui](https://releases.aspose.com/slides/java/).

### Esistono requisiti di licenza per l'utilizzo di Aspose.Slides?

Sì, Aspose.Slides richiede una licenza valida per uso commerciale. È possibile ottenere una licenza dal sito Web Aspose.

### Dove posso trovare ulteriore documentazione ed esempi?

 È possibile trovare documentazione completa ed esempi per Aspose.Slides per Java all'indirizzo[Qui](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
