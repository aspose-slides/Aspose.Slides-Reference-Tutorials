---
title: Converti con dimensioni personalizzate nelle diapositive Java
linktitle: Converti con dimensioni personalizzate nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come convertire presentazioni PowerPoint in immagini TIFF con dimensioni personalizzate utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per gli sviluppatori.
type: docs
weight: 31
url: /it/java/presentation-conversion/convert-custom-size-java-slides/
---

## Introduzione alla conversione con dimensioni personalizzate nelle diapositive Java

In questo articolo, esploreremo come convertire le presentazioni PowerPoint in immagini TIFF con dimensioni personalizzate utilizzando l'API Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di lavorare con file PowerPoint a livello di programmazione. Andremo passo dopo passo e ti forniremo il codice Java necessario per eseguire questa attività.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Kit di sviluppo Java (JDK) installato
- Aspose.Slides per la libreria Java

 È possibile scaricare la libreria Aspose.Slides per Java dal sito Web:[Scarica Aspose.Slides per Java](https://releases.aspose.com/slides/java/)

## Passaggio 1: importa la libreria Aspose.Slides

Per iniziare, devi importare la libreria Aspose.Slides nel tuo progetto Java. Ecco come puoi farlo:

```java
// Aggiungi la dichiarazione di importazione necessaria
import com.aspose.slides.*;
```

## Passaggio 2: carica la presentazione di PowerPoint

 Successivamente, dovrai caricare la presentazione PowerPoint che desideri convertire in un'immagine TIFF. Sostituire`"Your Document Directory"` con il percorso effettivo del file di presentazione.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza di un oggetto Presentation che rappresenta un file Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Passaggio 3: imposta le opzioni di conversione TIFF

Ora impostiamo le opzioni per la conversione TIFF. Specificheremo il tipo di compressione, DPI (punti per pollice), dimensione dell'immagine e posizione delle note. Puoi personalizzare queste opzioni secondo le tue esigenze.

```java
// Crea un'istanza della classe TiffOptions
TiffOptions opts = new TiffOptions();

// Impostazione del tipo di compressione
opts.setCompressionType(TiffCompressionTypes.Default);

// Impostazione DPI dell'immagine
opts.setDpiX(200);
opts.setDpiY(100);

// Imposta la dimensione dell'immagine
opts.setImageSize(new Dimension(1728, 1078));

// Imposta la posizione delle note
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Passaggio 4: salva come TIFF

Con tutte le opzioni configurate, ora puoi salvare la presentazione come immagine TIFF con le impostazioni specificate.

```java
// Salva la presentazione in TIFF con la dimensione dell'immagine specificata
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Codice sorgente completo per la conversione con dimensioni personalizzate in diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza di un oggetto Presentation che rappresenta un file Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Crea un'istanza della classe TiffOptions
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
	// L'unità di risoluzione è sempre uguale a “2” (punti per pollice)
	// Impostazione DPI dell'immagine
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Imposta la dimensione dell'immagine
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

Congratulazioni! Hai convertito con successo una presentazione di PowerPoint in un'immagine TIFF con dimensioni personalizzate utilizzando Aspose.Slides per Java. Questa può essere una funzionalità utile quando è necessario generare immagini di alta qualità dalle presentazioni per vari scopi.

## Domande frequenti

### Come posso modificare il tipo di compressione per l'immagine TIFF?

 È possibile modificare il tipo di compressione modificando il file`setCompressionType` metodo nel`TiffOptions` classe. Sono disponibili diversi tipi di compressione, ad esempio Predefinito, Nessuno, CCITT3, CCITT4, LZW e RLE.

### Posso regolare i DPI (punti per pollice) dell'immagine TIFF?

Sì, puoi regolare il DPI utilizzando il`setDpiX` E`setDpiY` metodi in`TiffOptions` classe. Basta impostare i valori desiderati per controllare la risoluzione dell'immagine.

### Quali sono le opzioni disponibili per la posizione delle note nell'immagine TIFF?

 La posizione delle note nell'immagine TIFF può essere configurata utilizzando`setNotesPosition` metodo con opzioni come BottomFull, BottomTruncated e SlideOnly. Scegli quello più adatto alle tue esigenze.

### È possibile specificare una dimensione immagine personalizzata per la conversione TIFF?

 Assolutamente! È possibile impostare una dimensione immagine personalizzata utilizzando il file`setImageSize` metodo nel`TiffOptions` classe. Fornisci le dimensioni (larghezza e altezza) desiderate per l'immagine di output.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per Java?

 Per documentazione dettagliata e informazioni aggiuntive su Aspose.Slides per Java, visitare la documentazione:[Aspose.Slides per riferimento API Java](https://reference.aspose.com/slides/java/).