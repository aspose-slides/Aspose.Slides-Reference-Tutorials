---
title: Tutorial sull'incorporamento di fotogrammi video con Aspose.Slides per .NET
linktitle: Aggiunta di fotogrammi video dalla sorgente Web nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come incorporare perfettamente fotogrammi video nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Migliora le presentazioni con contenuti multimediali senza sforzo.
type: docs
weight: 20
url: /it/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---
## introduzione
Nel dinamico mondo delle presentazioni, l’integrazione di elementi multimediali può aumentare significativamente il coinvolgimento e trasmettere messaggi di grande impatto. Un modo efficace per raggiungere questo obiettivo è incorporare fotogrammi video nelle diapositive della presentazione. In questo tutorial, esploreremo come ottenere questo risultato senza problemi utilizzando Aspose.Slides per .NET. Aspose.Slides è una solida libreria che consente agli sviluppatori di manipolare le presentazioni PowerPoint a livello di codice, fornendo ampie funzionalità per creare, modificare e migliorare le diapositive.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere a disposizione quanto segue:
1.  Aspose.Slides per .NET Library: scarica e installa la libreria da[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).
2. File video di esempio: prepara un file video che desideri incorporare nella presentazione. Puoi utilizzare l'esempio fornito con un video denominato "Wildlife.mp4".
## Importa spazi dei nomi
Nel tuo progetto .NET, includi gli spazi dei nomi necessari per sfruttare le funzionalità di Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Analizziamo il processo di incorporamento di fotogrammi video nelle diapositive di presentazione utilizzando Aspose.Slides per .NET in passaggi gestibili:
## Passaggio 1: impostare le directory
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Crea directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assicurati di sostituire "La tua directory dei documenti" e "La tua directory dei media" con i percorsi appropriati nel tuo progetto.
## Passaggio 2: crea un oggetto di presentazione
```csharp
using (Presentation pres = new Presentation())
{
    // Ottieni la prima diapositiva
    ISlide sld = pres.Slides[0];
```
Inizializza una nuova presentazione e accedi alla prima diapositiva per incorporare il fotogramma video.
## Passaggio 3: incorpora il video nella presentazione
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Utilizza il`AddVideo` metodo per incorporare il video nella presentazione, specificando il percorso del file e il comportamento di caricamento.
## Passaggio 4: aggiungi fotogramma video
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Crea un fotogramma video sulla diapositiva, definendone la posizione e le dimensioni.
## Passaggio 5: configura le impostazioni video
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Associa il fotogramma video al video incorporato, imposta la modalità di riproduzione e regola il volume in base alle tue preferenze.
## Passaggio 6: salva la presentazione
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Salva la presentazione modificata con il fotogramma video incorporato.
## Conclusione
Congratulazioni! Hai imparato con successo come incorporare fotogrammi video nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Questa funzionalità apre interessanti possibilità per creare presentazioni dinamiche e coinvolgenti che affascinano il tuo pubblico.
## Domande frequenti
### Posso incorporare video di formati diversi utilizzando Aspose.Slides?
Sì, Aspose.Slides supporta una varietà di formati video, garantendo flessibilità nelle tue presentazioni.
### Come posso controllare le impostazioni di riproduzione del video incorporato?
 Aggiusta il`PlayMode` E`Volume` proprietà del fotogramma video per personalizzare il comportamento di riproduzione.
### Aspose.Slides è compatibile con le ultime versioni di .NET?
Aspose.Slides viene regolarmente aggiornato per mantenere la compatibilità con gli ultimi framework .NET.
### Posso incorporare più video in una singola diapositiva utilizzando Aspose.Slides?
Sì, puoi incorporare più video aggiungendo ulteriori fotogrammi video a una diapositiva.
### Dove posso trovare supporto per le query relative ad Aspose.Slides?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.