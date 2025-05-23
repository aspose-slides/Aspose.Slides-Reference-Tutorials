---
"description": "Scopri come convertire le presentazioni PowerPoint in PDF con diapositive nascoste utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo con codice sorgente per una generazione PDF impeccabile."
"linktitle": "Converti in PDF con diapositive nascoste in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Converti in PDF con diapositive nascoste in Java Slides"
"url": "/it/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converti in PDF con diapositive nascoste in Java Slides


## Introduzione alla conversione di presentazioni PowerPoint in PDF con diapositive nascoste utilizzando Aspose.Slides per Java

In questa guida passo passo, imparerai come convertire una presentazione PowerPoint in PDF mantenendo le diapositive nascoste utilizzando Aspose.Slides per Java. Le diapositive nascoste sono quelle che non vengono visualizzate durante una presentazione normale, ma possono essere incluse nell'output PDF. Ti forniremo il codice sorgente e istruzioni dettagliate per eseguire questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Libreria Aspose.Slides per Java: assicurati di aver configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricarla da [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

2. Ambiente di sviluppo Java: sul tuo sistema dovrebbe essere installato un ambiente di sviluppo Java.

## Passaggio 1: importare Aspose.Slides per Java

Per prima cosa, devi importare la libreria Aspose.Slides nel tuo progetto Java. Assicurati di averla aggiunta al build path del progetto.

```java
import com.aspose.slides.*;
```

## Passaggio 2: caricare la presentazione di PowerPoint

Inizierai caricando la presentazione di PowerPoint che desideri convertire in PDF. Sostituisci `"Your Document Directory"` E `"HiddingSlides.pptx"` con il percorso file appropriato.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Passaggio 3: configurare le opzioni PDF

Configura le opzioni PDF per includere le diapositive nascoste nell'output PDF. Puoi farlo impostando `setShowHiddenSlides` proprietà del `PdfOptions` classe a `true`.

```java
// Crea un'istanza della classe PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Specificare che il documento generato deve includere diapositive nascoste
pdfOptions.setShowHiddenSlides(true);
```

## Passaggio 4: salva la presentazione come PDF

Ora salva la presentazione in un file PDF con le opzioni specificate. Sostituisci `"PDFWithHiddenSlides_out.pdf"` con il nome del file di output desiderato.

```java
// Salva la presentazione in PDF con le opzioni specificate
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Fase 5: Pulizia delle risorse

Assicurati di rilasciare le risorse utilizzate dalla presentazione una volta terminata.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Codice sorgente completo per convertire in PDF con diapositive nascoste in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Crea un'istanza della classe PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Specificare che il documento generato deve includere diapositive nascoste
	pdfOptions.setShowHiddenSlides(true);
	// Salva la presentazione in PDF con le opzioni specificate
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questa guida completa, hai imparato come convertire una presentazione PowerPoint in PDF mantenendo le diapositive nascoste utilizzando Aspose.Slides per Java. Ti abbiamo fornito un tutorial passo passo insieme al codice sorgente necessario per eseguire questa operazione senza problemi.

## Domande frequenti

### Come posso nascondere le diapositive in una presentazione di PowerPoint?

Per nascondere una diapositiva in una presentazione di PowerPoint, segui questi passaggi:
1. Seleziona la diapositiva che desideri nascondere nella visualizzazione Ordine diapositive.
2. Fare clic con il tasto destro del mouse sulla diapositiva selezionata.
3. Selezionare "Nascondi diapositiva" dal menu contestuale.

### Posso visualizzare tramite programmazione le diapositive nascoste in Aspose.Slides per Java?

Sì, puoi visualizzare a livello di programmazione le diapositive nascoste in Aspose.Slides per Java impostando `Hidden` proprietà del `Slide` classe a `false`Ecco un esempio:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Sostituisci slideIndex con l'indice della diapositiva nascosta
slide.setHidden(false);
```

### Come posso scaricare Aspose.Slides per Java?

Puoi scaricare Aspose.Slides per Java dal sito web di Aspose. Visita [Pagina di download di Aspose.Slides per Java](https://releases.aspose.com/slides/java/) per ottenere la versione più recente.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}