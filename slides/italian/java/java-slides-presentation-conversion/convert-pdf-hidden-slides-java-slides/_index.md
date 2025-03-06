---
title: Converti in PDF con diapositive nascoste in Java Slides
linktitle: Converti in PDF con diapositive nascoste in Java Slides
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come convertire presentazioni PowerPoint in PDF con diapositive nascoste utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo con il codice sorgente per generare PDF senza problemi.
weight: 27
url: /it/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione alla conversione di presentazioni PowerPoint in PDF con diapositive nascoste utilizzando Aspose.Slides per Java

In questa guida passo passo imparerai come convertire una presentazione PowerPoint in PDF preservando le diapositive nascoste utilizzando Aspose.Slides per Java. Le diapositive nascoste sono quelle che non vengono visualizzate durante una normale presentazione ma che possono essere incluse nell'output PDF. Ti forniremo il codice sorgente e istruzioni dettagliate per eseguire questa attività.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Libreria Aspose.Slides per Java: assicurati di avere la libreria Aspose.Slides per Java impostata nel tuo progetto Java. Puoi scaricarlo da[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).

2. Ambiente di sviluppo Java: dovresti avere un ambiente di sviluppo Java installato sul tuo sistema.

## Passaggio 1: importa Aspose.Slides per Java

Innanzitutto, devi importare la libreria Aspose.Slides nel tuo progetto Java. Assicurati di aver aggiunto la libreria al percorso di compilazione del tuo progetto.

```java
import com.aspose.slides.*;
```

## Passaggio 2: carica la presentazione di PowerPoint

 Inizierai caricando la presentazione PowerPoint che desideri convertire in PDF. Sostituire`"Your Document Directory"` E`"HiddingSlides.pptx"` con il percorso file appropriato.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Passaggio 3: configura le opzioni PDF

Configura le opzioni PDF per includere le diapositive nascoste nell'output PDF. Puoi farlo impostando il file`setShowHiddenSlides` proprietà del`PdfOptions` classe a`true`.

```java
// Crea un'istanza della classe PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Specificare che il documento generato deve includere diapositive nascoste
pdfOptions.setShowHiddenSlides(true);
```

## Passaggio 4: salva la presentazione come PDF

 Ora salva la presentazione in un file PDF con le opzioni specificate. Sostituire`"PDFWithHiddenSlides_out.pdf"` con il nome del file di output desiderato.

```java
// Salva la presentazione in PDF con le opzioni specificate
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Passaggio 5: pulire le risorse

Assicurati di rilasciare le risorse utilizzate dalla presentazione una volta terminata.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Codice sorgente completo per convertire in PDF con diapositive nascoste nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

In questa guida completa, hai imparato come convertire una presentazione PowerPoint in PDF preservando le diapositive nascoste utilizzando Aspose.Slides per Java. Ti abbiamo fornito un tutorial passo passo insieme al codice sorgente necessario per svolgere questa attività senza problemi.

## Domande frequenti

### Come posso nascondere le diapositive in una presentazione di PowerPoint?

Per nascondere una diapositiva in una presentazione di PowerPoint, attenersi alla seguente procedura:
1. Seleziona la diapositiva che desideri nascondere nella visualizzazione Sequenza diapositive.
2. Fare clic con il tasto destro sulla diapositiva selezionata.
3. Scegli "Nascondi diapositiva" dal menu contestuale.

### Posso mostrare a livello di codice le diapositive nascoste in Aspose.Slides per Java?

 Sì, puoi mostrare a livello di codice le diapositive nascoste in Aspose.Slides per Java impostando il file`Hidden` proprietà del`Slide` classe a`false`. Ecco un esempio:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Sostituisci slideIndex con l'indice della diapositiva nascosta
slide.setHidden(false);
```

### Come posso scaricare Aspose.Slides per Java?

 È possibile scaricare Aspose.Slides per Java dal sito Web Aspose. Visitare il[Aspose.Slides per la pagina di download di Java](https://releases.aspose.com/slides/java/) per ottenere la versione più recente.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
