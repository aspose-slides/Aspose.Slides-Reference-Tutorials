---
title: Aspose.Slides - Aggiunta di video incorporati nelle presentazioni .NET
linktitle: Aspose.Slides - Aggiunta di video incorporati nelle presentazioni .NET
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Migliora le tue presentazioni con video incorporati utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 19
url: /it/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## introduzione
Nel mondo dinamico delle presentazioni, l'integrazione di elementi multimediali può aumentare significativamente il coinvolgimento. Aspose.Slides per .NET fornisce una potente soluzione per incorporare fotogrammi video incorporati nelle diapositive della presentazione. Questo tutorial ti guiderà attraverso il processo, suddividendo ogni passaggio per garantire un'esperienza senza interruzioni.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
-  Aspose.Slides per .NET Library: scarica e installa la libreria da[pagina di rilascio](https://releases.aspose.com/slides/net/).
- Contenuto multimediale: possiedi un file video (ad esempio "Wildlife.mp4") che desideri incorporare nella presentazione.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Passaggio 1: impostare le directory
Assicurati che il tuo progetto abbia le directory richieste per documenti e file multimediali:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Crea directory se non è già presente.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Passaggio 2: istanziare la lezione di presentazione
Crea un'istanza della classe Presentation per rappresentare il file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Ottieni la prima diapositiva
    ISlide sld = pres.Slides[0];
```
## Passaggio 3: incorpora il video nella presentazione
Utilizza il seguente codice per incorporare un video all'interno della presentazione:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Passaggio 4: aggiungi fotogramma video
Ora aggiungi un fotogramma video alla diapositiva:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Passaggio 5: imposta le proprietà del video
Imposta il video sul fotogramma video e configura la modalità di riproduzione e il volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Passaggio 6: salva la presentazione
Infine, salva il file PPTX su disco:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Ripeti questi passaggi per ogni video che desideri incorporare nella presentazione.
## Conclusione
Congratulazioni! Hai aggiunto con successo un fotogramma video incorporato alla tua presentazione utilizzando Aspose.Slides per .NET. Questa funzionalità dinamica può elevare le tue presentazioni a nuovi livelli, affascinando il tuo pubblico con elementi multimediali perfettamente integrati nelle tue diapositive.
## Domande frequenti
### Posso incorporare video in qualsiasi diapositiva della presentazione?
 Sì, puoi scegliere qualsiasi diapositiva modificando l'indice in`pres.Slides[index]`.
### Quali formati video sono supportati?
Aspose.Slides supporta una varietà di formati video, inclusi MP4, AVI e WMV.
### Posso personalizzare le dimensioni e la posizione del fotogramma video?
 Assolutamente! Regola i parametri in`AddVideoFrame(x, y, width, height, video)` come necessario.
### C'è un limite al numero di video che posso incorporare?
Il numero di video incorporati è generalmente limitato dalla capacità del software di presentazione.
### Come posso chiedere ulteriore assistenza o condividere la mia esperienza?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.