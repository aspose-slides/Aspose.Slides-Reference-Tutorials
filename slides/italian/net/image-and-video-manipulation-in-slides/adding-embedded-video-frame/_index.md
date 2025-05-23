---
"description": "Migliora le tue presentazioni con video incorporati utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per un'integrazione perfetta."
"linktitle": "Aspose.Slides - Aggiunta di video incorporati nelle presentazioni .NET"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Aggiunta di video incorporati nelle presentazioni .NET"
"url": "/it/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Aggiunta di video incorporati nelle presentazioni .NET

## Introduzione
Nel dinamico mondo delle presentazioni, l'integrazione di elementi multimediali può migliorare significativamente il coinvolgimento. Aspose.Slides per .NET offre una soluzione potente per integrare fotogrammi video nelle diapositive delle presentazioni. Questo tutorial vi guiderà attraverso il processo, analizzando ogni passaggio per garantire un'esperienza fluida.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Aspose.Slides per la libreria .NET: scarica e installa la libreria da [pagina di rilascio](https://releases.aspose.com/slides/net/).
- Contenuto multimediale: disponi di un file video (ad esempio "Wildlife.mp4") che desideri incorporare nella tua presentazione.
## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nel tuo progetto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Passaggio 1: impostare le directory
Assicurati che il tuo progetto abbia le directory richieste per i file di documenti e multimediali:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Creare la directory se non è già presente.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Passaggio 2: creare un'istanza della classe di presentazione
Creare un'istanza della classe Presentation per rappresentare il file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Ottieni la prima diapositiva
    ISlide sld = pres.Slides[0];
```
## Passaggio 3: incorporare il video nella presentazione
Utilizza il seguente codice per incorporare un video all'interno della presentazione:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Passaggio 4: aggiungere un fotogramma video
Ora aggiungiamo un fotogramma video alla diapositiva:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Passaggio 5: imposta le proprietà video
Imposta il video sul fotogramma video e configura la modalità di riproduzione e il volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Passaggio 6: Salva la presentazione
Infine, salva il file PPTX sul disco:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Ripeti questi passaggi per ogni video che desideri incorporare nella presentazione.
## Conclusione
Congratulazioni! Hai aggiunto con successo un fotogramma video incorporato alla tua presentazione utilizzando Aspose.Slides per .NET. Questa funzionalità dinamica può portare le tue presentazioni a nuovi livelli, catturando l'attenzione del pubblico con elementi multimediali perfettamente integrati nelle diapositive.
## Domande frequenti
### Posso incorporare video in qualsiasi diapositiva della presentazione?
Sì, puoi scegliere qualsiasi diapositiva modificando l'indice in `pres.Slides[index]`.
### Quali formati video sono supportati?
Aspose.Slides supporta vari formati video, tra cui MP4, AVI e WMV.
### Posso personalizzare le dimensioni e la posizione del fotogramma video?
Assolutamente! Regola i parametri in `AddVideoFrame(x, y, width, height, video)` secondo necessità.
### C'è un limite al numero di video che posso incorporare?
Il numero di video incorporati è solitamente limitato dalla capacità del software di presentazione.
### Come posso ottenere ulteriore assistenza o condividere la mia esperienza?
Visita il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}