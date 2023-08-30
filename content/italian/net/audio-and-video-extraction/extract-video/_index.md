---
title: Estrai video dalla diapositiva
linktitle: Estrai video dalla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Masterizza l'estrazione video da diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Segui la nostra guida con esempi di codice.
type: docs
weight: 14
url: /it/net/audio-and-video-extraction/extract-video/
---

## introduzione

Nel mondo digitale di oggi, le presentazioni multimediali sono diventate una parte essenziale della comunicazione. Le presentazioni PowerPoint spesso includono un mix di testo, immagini e video per trasmettere le informazioni in modo efficace. Tuttavia, in alcuni casi potrebbe essere necessario estrarre un video da una diapositiva per vari scopi, ad esempio archiviazione, condivisione o ulteriore modifica. È qui che entra in gioco Aspose.Slides per .NET.

## Prerequisiti

Prima di immergerci nella guida passo passo, assicurati di disporre dei seguenti prerequisiti:

- Conoscenza base di C# e framework .NET
- Visual Studio installato
-  Aspose.Slides per la libreria .NET (scarica da[Qui](https://releases.aspose.com/slides/net)

## Guida passo passo

Esaminiamo il processo di estrazione di un video da una diapositiva utilizzando Aspose.Slides per .NET:

### Passaggio 1: installazione

1. Apri Visual Studio e crea un nuovo progetto C#.
2. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e seleziona "Gestisci pacchetti NuGet".
3. Cerca "Aspose.Slides" e installa la versione più recente.

### Passaggio 2: caricare la presentazione

```csharp
using Aspose.Slides;

// Carica la presentazione
using var presentation = new Presentation("your-presentation.pptx");
```

 Sostituire`"your-presentation.pptx"` con il percorso effettivo del file di presentazione di PowerPoint.

### Passaggio 3: estrai il video

```csharp
// Ottieni la prima diapositiva
var slide = presentation.Slides[0];

// Scorri le forme delle diapositive
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Estrai il video dal fotogramma video
        var video = videoFrame.EmbeddedVideo;
        // È possibile eseguire un'ulteriore elaborazione con l'oggetto video
    }
}
```

### Passaggio 4: salva il video

```csharp
// Salva il video estratto
video.WriteToFile("extracted-video.mp4");
```

 Sostituire`"extracted-video.mp4"` con il nome e il percorso desiderati per il file video estratto.

## Conclusione

Aspose.Slides per .NET semplifica il compito di estrarre video dalle presentazioni PowerPoint. Con solo poche righe di codice, puoi recuperare i video incorporati nelle diapositive e salvarli come file video separati. Che tu stia cercando di riutilizzare contenuti o creare raccolte, questa libreria fornisce una soluzione perfetta.

## Domande frequenti

### Come posso accedere alla documentazione di Aspose.Slides?

 È possibile fare riferimento alla documentazione di Aspose.Slides per .NET all'indirizzo[Qui](https://reference.aspose.com/slides/net/).

### Aspose.Slides è disponibile per altri linguaggi di programmazione?

Sì, Aspose.Slides è disponibile per più linguaggi di programmazione, incluso Java. È possibile trovare le librerie appropriate sul sito Web Aspose.

### Posso estrarre l'audio utilizzando lo stesso approccio?

No, l'esempio fornito è specifico per l'estrazione di video. Per estrarre l'audio, dovresti modificare il codice per funzionare con i frame audio.

### Sono previsti costi di licenza per l'utilizzo di Aspose.Slides?

Sì, Aspose.Slides è un prodotto commerciale. È possibile trovare informazioni dettagliate su licenze e prezzi sul sito Web Aspose.

### Come accedo alle proprietà del video estratto?

 IL`EmbeddedVideo` oggetto ottenuto da`IVideoFrame` fornisce l'accesso a varie proprietà del video, come durata, risoluzione e altro.