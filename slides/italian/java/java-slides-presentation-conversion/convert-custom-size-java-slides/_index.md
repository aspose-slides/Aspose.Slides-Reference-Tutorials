---
"description": "Scopri come convertire le presentazioni PowerPoint in immagini TIFF con dimensioni personalizzate utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per sviluppatori."
"linktitle": "Converti con dimensioni personalizzate in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Converti con dimensioni personalizzate in Java Slides"
"url": "/it/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converti con dimensioni personalizzate in Java Slides


## Introduzione alla conversione con dimensioni personalizzate in Java Slides

In questo articolo, esploreremo come convertire le presentazioni di PowerPoint in immagini TIFF con dimensioni personalizzate utilizzando l'API Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di lavorare con i file di PowerPoint a livello di codice. Procederemo passo dopo passo e vi forniremo il codice Java necessario per eseguire questa operazione.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato
- Libreria Aspose.Slides per Java

È possibile scaricare la libreria Aspose.Slides per Java dal sito web: [Scarica Aspose.Slides per Java](https://releases.aspose.com/slides/java/)

## Passaggio 1: importare la libreria Aspose.Slides

Per iniziare, devi importare la libreria Aspose.Slides nel tuo progetto Java. Ecco come fare:

```java
// Aggiungere l'istruzione di importazione necessaria
import com.aspose.slides.*;
```

## Passaggio 2: caricare la presentazione di PowerPoint

Successivamente, dovrai caricare la presentazione PowerPoint che desideri convertire in un'immagine TIFF. Sostituisci `"Your Document Directory"` con il percorso effettivo del file della presentazione.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza di un oggetto Presentation che rappresenta un file Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Passaggio 3: impostare le opzioni di conversione TIFF

Ora impostiamo le opzioni per la conversione TIFF. Specifichiamo il tipo di compressione, i DPI (punti per pollice), le dimensioni dell'immagine e la posizione delle note. Puoi personalizzare queste opzioni in base alle tue esigenze.

```java
// Istanziare la classe TiffOptions
TiffOptions opts = new TiffOptions();

// Impostazione del tipo di compressione
opts.setCompressionType(TiffCompressionTypes.Default);

// Impostazione DPI dell'immagine
opts.setDpiX(200);
opts.setDpiY(100);

// Imposta dimensione immagine
opts.setImageSize(new Dimension(1728, 1078));

// Imposta la posizione delle note
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Passaggio 4: Salva come TIFF

Dopo aver configurato tutte le opzioni, è ora possibile salvare la presentazione come immagine TIFF con le impostazioni specificate.

```java
// Salva la presentazione in TIFF con la dimensione dell'immagine specificata
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Codice sorgente completo per la conversione con dimensioni personalizzate in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza di un oggetto Presentation che rappresenta un file Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Istanziare la classe TiffOptions
	TiffOptions opts = new TiffOptions();
	// Impostazione del tipo di compressione
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Tipi di compressione
	// Predefinito: specifica lo schema di compressione predefinito (LZW).
	// Nessuno: non specifica alcuna compressione.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// La profondità dipende dal tipo di compressione e non può essere impostata manualmente.
	// L'unità di risoluzione è sempre uguale a "2" (punti per pollice)
	// Impostazione DPI dell'immagine
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Imposta dimensione immagine
	opts.setImageSize(new Dimension(1728, 1078));
	// Salva la presentazione in TIFF con la dimensione dell'immagine specificata
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

Congratulazioni! Hai convertito con successo una presentazione PowerPoint in un'immagine TIFF con dimensioni personalizzate utilizzando Aspose.Slides per Java. Questa può essere una funzionalità preziosa quando devi generare immagini di alta qualità dalle tue presentazioni per vari scopi.

## Domande frequenti

### Come posso cambiare il tipo di compressione per l'immagine TIFF?

È possibile modificare il tipo di compressione modificando `setCompressionType` metodo nel `TiffOptions` classe. Sono disponibili diversi tipi di compressione, come Default, None, CCITT3, CCITT4, LZW e RLE.

### Posso regolare i DPI (punti per pollice) dell'immagine TIFF?

Sì, puoi regolare i DPI utilizzando `setDpiX` E `setDpiY` metodi nel `TiffOptions` classe. Basta impostare i valori desiderati per controllare la risoluzione dell'immagine.

### Quali sono le opzioni disponibili per la posizione delle note nell'immagine TIFF?

La posizione delle note nell'immagine TIFF può essere configurata utilizzando `setNotesPosition` Metodo con opzioni come BottomFull, BottomTruncated e SlideOnly. Scegli quello più adatto alle tue esigenze.

### È possibile specificare una dimensione immagine personalizzata per la conversione TIFF?

Assolutamente! Puoi impostare una dimensione immagine personalizzata utilizzando `setImageSize` metodo nel `TiffOptions` classe. Specifica le dimensioni (larghezza e altezza) desiderate per l'immagine di output.

### Dove posso trovare maggiori informazioni su Aspose.Slides per Java?

Per una documentazione dettagliata e ulteriori informazioni su Aspose.Slides per Java, visitare la documentazione: [Riferimento API Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}