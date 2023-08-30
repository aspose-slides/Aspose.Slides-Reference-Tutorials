---
title: Creazione di una miniatura per la forma in Aspose.Slides
linktitle: Creazione di una miniatura per la forma in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare miniature per forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida passo passo fornisce esempi pratici di codice, dal caricamento delle presentazioni alla generazione e al salvataggio delle miniature.
type: docs
weight: 14
url: /it/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

## introduzione

Aspose.Slides per .NET è una libreria ricca di funzionalità che consente agli sviluppatori di lavorare senza problemi con le presentazioni PowerPoint. Un requisito comune è generare miniature per forme specifiche all'interno delle diapositive. Ciò può essere particolarmente utile quando desideri fornire una rapida anteprima o rappresentazione di una forma nella tua applicazione.

## Prerequisiti

Prima di approfondire il codice, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio o qualsiasi altro ambiente di sviluppo .NET adatto.
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Installazione

1. Scarica la libreria Aspose.Slides per .NET dal collegamento fornito.
2. Installa la libreria nel tuo progetto .NET aggiungendo un riferimento alla DLL scaricata.

## Caricamento di una presentazione

Iniziamo caricando una presentazione di PowerPoint utilizzando Aspose.Slides. Il codice seguente mostra come caricare una presentazione da un file:

```csharp
using Aspose.Slides;

// Carica la presentazione
using var presentation = new Presentation("sample.pptx");
```

 Sostituire`"sample.pptx"` con il percorso effettivo della presentazione di PowerPoint.

## Accesso alle forme

Una volta caricata la presentazione, puoi accedere alle forme all'interno di ciascuna diapositiva. In questo esempio, ci concentreremo sulla generazione di una miniatura per una forma specifica su una particolare diapositiva. Ecco come puoi accedere a una forma:

```csharp
// Accedi a una diapositiva tramite indice (in base 0)
var slide = presentation.Slides[0];

// Accedi a una forma tramite indice (in base 0)
var shape = slide.Shapes[0];
```

Modifica gli indici delle diapositive e delle forme in base alla struttura della presentazione.

## Creazione di miniature

 Ora arriva la parte emozionante: creare una miniatura per la forma selezionata. Aspose.Slides ti consente di raggiungere questo obiettivo sfruttando il`GetThumbnail` metodo. Ecco come creare una miniatura per una forma:

```csharp
// Definire le dimensioni delle miniature
int thumbnailWidth = 200;
int thumbnailHeight = 150;

// Genera una miniatura per la forma
var thumbnail = shape.GetThumbnail(thumbnailWidth, thumbnailHeight);
```

 Aggiusta il`thumbnailWidth` E`thumbnailHeight` variabili per impostare le dimensioni desiderate per la miniatura.

## Salvataggio delle miniature

Dopo aver generato la miniatura, potresti volerla salvare come file immagine. Ecco come puoi salvare la miniatura come immagine PNG:

```csharp
// Salva la miniatura come immagine
thumbnail.Save("shape_thumbnail.png", ImageFormat.Png);
```

Personalizza il nome e il formato del file in base alle tue esigenze.

## Conclusione

In questa guida, abbiamo esplorato come creare miniature per forme all'interno di presentazioni PowerPoint utilizzando Aspose.Slides per .NET. Hai imparato come caricare una presentazione, accedere alle forme, generare miniature e salvarle come file di immagine. Questa funzionalità può migliorare notevolmente l'esperienza dell'utente nelle applicazioni che coinvolgono presentazioni PowerPoint.

## Domande frequenti

### Come posso specificare dimensioni diverse delle miniature?

 Puoi regolare il`thumbnailWidth` E`thumbnailHeight` variabili nel codice per specificare le dimensioni necessarie per la miniatura generata.

### Posso creare miniature per più forme contemporaneamente?

Sì, puoi scorrere tutte le forme su una diapositiva e generare miniature per ciascuna forma utilizzando un ciclo.

### Aspose.Slides è compatibile con diversi formati PowerPoint?

Sì, Aspose.Slides supporta vari formati PowerPoint, inclusi PPTX, PPT e altri.

### Posso personalizzare l'aspetto della miniatura generata?

 Mentre il`GetThumbnail` Il metodo fornisce un modo rapido per generare miniature, è possibile manipolare ulteriormente l'immagine in miniatura utilizzando le librerie di elaborazione delle immagini standard in .NET.

### Aspose.Slides è adatto per altre attività relative a PowerPoint?

Assolutamente, Aspose.Slides offre una vasta gamma di funzionalità per lavorare con presentazioni PowerPoint, tra cui la creazione, la modifica, la conversione e il rendering di diapositive.