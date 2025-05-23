---
"description": "Scopri come convertire presentazioni PowerPoint con note in PDF utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo con il codice sorgente."
"linktitle": "Converti la visualizzazione delle diapositive delle note in PDF in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Converti la visualizzazione delle diapositive delle note in PDF in Java Slides"
"url": "/it/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converti la visualizzazione delle diapositive delle note in PDF in Java Slides


## Introduzione alla conversione della visualizzazione diapositiva delle note in PDF in Java Slides

In questo tutorial, ti guideremo attraverso il processo di conversione di una presentazione PowerPoint con visualizzazione diapositive note in un PDF utilizzando la libreria Aspose.Slides per Java. Questa libreria offre potenti funzionalità per lavorare con le presentazioni PowerPoint in Java.

## Prerequisiti
1. Java Development Kit (JDK) installato.
2. Libreria Aspose.Slides per Java aggiunta al tuo progetto.

## Passaggio 1: importare le classi necessarie
Per iniziare, è necessario importare le classi necessarie dalla libreria Aspose.Slides. Ecco il codice per farlo:

```java
import com.aspose.slides.*;
```

## Passaggio 2: caricare la presentazione di PowerPoint
Dovresti avere pronto il file della tua presentazione PowerPoint. Sostituisci `"Your Document Directory"` Con il percorso della directory in cui si trova il file della presentazione. Ecco il codice per caricare la presentazione:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Passaggio 3: configurare le opzioni PDF
Ora configuriamo le opzioni di esportazione PDF. Nello specifico, imposteremo la posizione delle note su "BottomFull" per includere le note sotto le diapositive nel PDF. Ecco il codice:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Puoi personalizzare altre opzioni PDF in base alle tue esigenze.

## Passaggio 4: salva la presentazione come PDF con note
Infine, salviamo la presentazione come file PDF, incluse le note. Puoi specificare il nome del file di output (ad esempio, `"Pdf_Notes_out.pdf"`) e scegli il formato (`SaveFormat.Pdf`). Ecco il codice per farlo:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Passaggio 5: pulizia delle risorse
Non dimenticare di rilasciare le risorse una volta terminata la presentazione:

```java
if (presentation != null) presentation.dispose();
```

## Codice sorgente completo per convertire la visualizzazione delle diapositive delle note in PDF in Java Slides

```java
// Percorso verso la directory dei documenti.
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

In questo tutorial abbiamo esplorato come convertire presentazioni PowerPoint con visualizzazioni di diapositive con note in PDF utilizzando la libreria Aspose.Slides per Java. Abbiamo seguito una guida passo passo con codice sorgente per ottenere questa conversione. Ecco i punti chiave:

## Domande frequenti

### Come posso modificare la posizione delle note nel PDF?

È possibile modificare la posizione delle note nel PDF modificando `setNotesPosition` argomento del metodo. Ad esempio, puoi impostarlo su `NotesPositions.RightFull` per posizionare le note sul lato destro delle diapositive.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Posso personalizzare ulteriormente l'esportazione in PDF?

Sì, puoi personalizzare l'esportazione PDF regolando varie opzioni in `PdfOptions` oggetto. Ad esempio, puoi impostare la qualità, la compressione e altri parametri in base alle tue esigenze.

### Come posso ottenere Aspose.Slides per Java?

Puoi scaricare Aspose.Slides per Java dal sito web all'indirizzo [Qui](https://releases.aspose.com/slides/java/).

### Esistono requisiti di licenza per l'utilizzo di Aspose.Slides?

Sì, Aspose.Slides richiede una licenza valida per uso commerciale. È possibile ottenere una licenza dal sito web di Aspose.

### Dove posso trovare ulteriore documentazione ed esempi?

Puoi trovare documentazione completa ed esempi per Aspose.Slides per Java su [Qui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}