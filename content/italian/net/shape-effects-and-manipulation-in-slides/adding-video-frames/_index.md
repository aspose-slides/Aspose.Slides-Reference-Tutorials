---
title: Aggiunta di fotogrammi video alle diapositive della presentazione utilizzando Aspose.Slides
linktitle: Aggiunta di fotogrammi video alle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le tue presentazioni aggiungendo fotogrammi video utilizzando Aspose.Slides per .NET. Crea contenuti accattivanti e interattivi senza problemi.
type: docs
weight: 19
url: /it/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Introduzione ad Aspose.Slides e integrazione video

Aspose.Slides è una libreria completa che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint a livello di codice. Integrando fotogrammi video nelle tue diapositive, puoi migliorare le tue presentazioni e renderle più dinamiche e coinvolgenti.

## Prerequisiti per incorporare video

Prima di iniziare, assicurati di avere quanto segue:

- Visual Studio o qualsiasi ambiente di sviluppo .NET preferito
- Aspose.Slides per la libreria .NET installata
- Una presentazione PowerPoint (PPTX) in cui desideri aggiungere fotogrammi video

## Configurazione dell'ambiente di sviluppo

1. Apri Visual Studio e crea un nuovo progetto .NET.
2.  Installa il pacchetto NuGet Aspose.Slides:`Install-Package Aspose.Slides`.

## Caricamento di una presentazione e accesso alle diapositive

Per iniziare, carica la presentazione di PowerPoint utilizzando Aspose.Slides:

```csharp
using Aspose.Slides;

// Carica la presentazione
using Presentation presentation = new Presentation("your-presentation.pptx");

// Accedi alle diapositive
ISlideCollection slides = presentation.Slides;
```

## Aggiunta di file video alla presentazione

1. Inserisci i file video in una cartella all'interno del tuo progetto.
2. Aggiungi riferimenti a questi file nel tuo codice:

```csharp
// Aggiungi file video
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Posizionamento di fotogrammi video sulle diapositive

Scorri le diapositive e aggiungi fotogrammi video:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Personalizzazione delle proprietà dei fotogrammi video

Puoi personalizzare le proprietà del fotogramma video come posizione, dimensione e stile:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Gestione delle opzioni di riproduzione

 Controlla la riproduzione video utilizzando`VideoPlayModePreset` enumerazione:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Salvataggio ed esportazione della presentazione modificata

Salva la presentazione dopo aver aggiunto i fotogrammi video:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Conclusione

Incorporare fotogrammi video nelle diapositive della presentazione utilizzando Aspose.Slides migliora l'impatto visivo dei tuoi contenuti. Hai imparato come integrare perfettamente i video, personalizzare le proprietà dei fotogrammi video e controllare le opzioni di riproduzione. Inizia a creare presentazioni dinamiche e coinvolgenti che affascinano il tuo pubblico.

## Domande frequenti

### Come faccio ad aggiungere più video a una singola diapositiva?

Scorrere i file video e aggiungere fotogrammi video alla diapositiva desiderata utilizzando il codice fornito.

### Posso controllare le impostazioni di riproduzione video?

 Sì, puoi usare il`VideoPlayModePreset` enumerazione per impostare le opzioni di riproduzione come la riproduzione automatica.

### Quali formati video sono supportati?

Aspose.Slides supporta vari formati video, inclusi MP4, AVI, WMV e altri.

### È possibile aggiungere video a livello di codice in C#?

Assolutamente, Aspose.Slides per .NET fornisce un'API intuitiva per aggiungere video alle diapositive a livello di codice utilizzando C#.

### Posso modificare l'aspetto del fotogramma video?

Sì, puoi personalizzare la posizione, le dimensioni e altre proprietà visive del fotogramma video in base alle tue esigenze.