---
title: Aggiunta di fotogrammi video dalla sorgente Web nelle diapositive della presentazione con Aspose.Slides
linktitle: Aggiunta di fotogrammi video dalla sorgente Web nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le diapositive della tua presentazione aggiungendo fotogrammi video da fonti Web utilizzando Aspose.Slides per .NET. Crea presentazioni multimediali accattivanti con istruzioni dettagliate ed esempi di codice sorgente.
type: docs
weight: 20
url: /it/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

Nel mondo dinamico di oggi, le presentazioni si sono evolute oltre le diapositive statiche. L'integrazione di elementi multimediali come i video nella tua presentazione può aumentare significativamente il coinvolgimento e trasmettere le informazioni in modo più efficace. Aspose.Slides per .NET consente agli sviluppatori di incorporare perfettamente fotogrammi video da fonti Web nelle diapositive di presentazione. Questa guida ti guida attraverso il processo passo dopo passo, dimostrando la potenza di Aspose.Slides.

## Prerequisiti

Prima di approfondire l'implementazione, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio o qualsiasi IDE compatibile installato
- Aspose.Slides per la libreria .NET
- Conoscenza base della programmazione C#

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto nel tuo IDE preferito e includi la libreria Aspose.Slides per .NET. È possibile scaricare la libreria dal sito Web o installarla utilizzando NuGet Package Manager.

## Passaggio 2: aggiunta di un fotogramma video a una diapositiva

1.  Crea una nuova istanza di`Presentation` utilizzando Aspose.Slides.
2.  Aggiungi una nuova diapositiva alla presentazione utilizzando il file`Slides` collezione.
3. Definire la posizione e le dimensioni del fotogramma video sulla diapositiva.
4.  Usa il`EmbedWebVideoFrame` metodo per aggiungere il fotogramma video alla diapositiva.

```csharp
// Crea una nuova presentazione
using (Presentation presentation = new Presentation())
{
    // Aggiungi una nuova diapositiva
    ISlide slide = presentation.Slides.AddEmptySlide();

    // Definire la posizione e le dimensioni del fotogramma video
    int x = 100; // Coordinata X
    int y = 100; // Coordinata Y
    int width = 480; // Larghezza
    int height = 270; // Altezza

    // Aggiungi un fotogramma video alla diapositiva
    slide.EmbedWebVideoFrame(x, y, width, height, new Uri("https://esempio.com/video.mp4"));
    
    // Salva la presentazione
    presentation.Save("output.pptx", SaveFormat.Pptx);
}
```

## Passaggio 3: personalizzazione della riproduzione video

Aspose.Slides offre varie opzioni per personalizzare l'esperienza di riproduzione video nella presentazione. Puoi controllare aspetti come la riproduzione automatica, il loop e le impostazioni di disattivazione dell'audio per il video incorporato.

```csharp
// Ottieni il fotogramma video sulla diapositiva
IVideoFrame videoFrame = (IVideoFrame)slide.Shapes[0];

//Abilita la riproduzione automatica
videoFrame.PlayMode = VideoPlayModePreset.Auto;

// Abilita ciclo
videoFrame.PlayLoopMode = VideoPlayLoopMode.Loop;

// Disattiva l'audio del video
videoFrame.Volume = AudioVolumeMode.Mute;
```

## Domande frequenti

### Come posso modificare la sorgente del video incorporato?

 Per modificare la fonte del video incorporato, aggiorna semplicemente l'URI fornito nel file`EmbedWebVideoFrame` metodo per puntare alla nuova origine web.

### Posso personalizzare l'aspetto del fotogramma video?

Sì, puoi personalizzare l'aspetto del fotogramma video utilizzando proprietà come posizione, dimensione e formattazione della forma.

### È possibile controllare quando inizia la riproduzione del video?

 Assolutamente! È possibile controllare l'ora di inizio della riproduzione regolando il`videoFrame.StartTime` proprietà.

### Quali formati video sono supportati per l'incorporamento?

Aspose.Slides supporta l'incorporamento di fotogrammi video da varie fonti Web, inclusi formati popolari come MP4, collegamenti YouTube e altro.

### Come posso garantire la compatibilità multipiattaforma per il video incorporato?

I fotogrammi video incorporati sono supportati nelle versioni moderne di Microsoft PowerPoint e altri software di presentazione compatibili.

## Conclusione

Incorporando fotogrammi video da fonti Web nelle diapositive della presentazione utilizzando Aspose.Slides per .NET puoi trasformare le tue presentazioni in esperienze multimediali coinvolgenti. Questa guida passo passo ha dimostrato come incorporare facilmente fotogrammi video, personalizzare la riproduzione e rispondere a domande comuni. Migliora le tue presentazioni con contenuti video dinamici e affascina il tuo pubblico come mai prima d'ora!