---
title: Come estrarre video dalla diapositiva utilizzando Aspose.Slides per .NET
linktitle: Estrai video dalla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come estrarre video dalle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida passo passo semplifica il processo per te.
type: docs
weight: 14
url: /it/net/audio-and-video-extraction/extract-video/
---

Aspose.Slides per .NET è una potente libreria che ti consente di lavorare con presentazioni PowerPoint in un ambiente .NET. Una delle funzionalità utili che offre è la possibilità di estrarre video dalle diapositive. In questa guida passo passo, ti mostreremo come estrarre un video da una diapositiva di PowerPoint utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

-  Aspose.Slides per .NET: è necessario che sia installato Aspose.Slides per .NET. Puoi ottenerlo da[sito web](https://purchase.aspose.com/buy).

- Una presentazione PowerPoint: prepara una presentazione PowerPoint (ad esempio, Video.pptx) che contiene il video che desideri estrarre.

## Importa spazi dei nomi

È necessario importare gli spazi dei nomi necessari per lavorare con Aspose.Slides per .NET. Ecco come puoi farlo:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Ora suddividiamo il processo di estrazione di un video da una diapositiva in più passaggi.

## Passaggio 1: impostare la directory dei documenti

```csharp
string dataDir = "Your Document Directory";
```

 Sostituire`"Your Document Directory"` con il percorso della directory in cui si trova la presentazione di PowerPoint.

## Passaggio 2: carica la presentazione

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Questo codice inizializza un oggetto Presentation, che rappresenta il file di presentazione di PowerPoint.

## Passaggio 3: scorrere diapositive e forme

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Qui, eseguiamo il ciclo di ciascuna diapositiva nella presentazione e quindi iteriamo attraverso le forme nella prima diapositiva (modifica secondo necessità).

## Passaggio 4: controlla se la forma è un fotogramma video

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Questo passaggio controlla se la forma sulla diapositiva è un fotogramma video.

## Passaggio 5: estrarre i dati video

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Questo codice estrae informazioni sul video, inclusi il tipo di contenuto e i dati binari.

## Passaggio 6: salva il video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Infine, questo passaggio salva il video in un nuovo file nella directory specificata.

Una volta completati questi passaggi, avrai estratto con successo un video da una diapositiva di PowerPoint utilizzando Aspose.Slides per .NET.

## Conclusione

Aspose.Slides per .NET semplifica il processo di lavoro con le presentazioni PowerPoint, consentendoti di eseguire attività come l'estrazione di video dalle diapositive con facilità. Seguendo questa guida passo passo e utilizzando la libreria Aspose.Slides, puoi migliorare le tue applicazioni .NET con potenti funzionalità di PowerPoint.

## Domande frequenti (FAQ)

### Cos'è Aspose.Slides per .NET?
Aspose.Slides per .NET è una libreria che consente alle applicazioni .NET di funzionare con presentazioni PowerPoint, inclusa la creazione, la modifica e l'estrazione di contenuti.

### Dove posso trovare la documentazione per Aspose.Slides per .NET?
 Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/net/).

### Aspose.Slides per .NET è disponibile per una prova gratuita?
 Sì, puoi ottenere una versione di prova gratuita da[Qui](https://releases.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?
 È possibile richiedere una licenza temporanea da[questo link](https://purchase.aspose.com/temporary-license/).

### Dove posso ottenere supporto per Aspose.Slides per .NET?
 Puoi trovare supporto su[Forum Aspose.Slides](https://forum.aspose.com/).