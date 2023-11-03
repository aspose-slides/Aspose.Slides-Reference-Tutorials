---
title: Collegamento di video tramite controllo ActiveX in PowerPoint
linktitle: Collegamento di video tramite controllo ActiveX
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come collegare video alle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida passo passo include il codice sorgente e suggerimenti per creare presentazioni interattive e coinvolgenti con video collegati.
type: docs
weight: 12
url: /it/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
Collegamento di un video tramite controllo ActiveX in una presentazione utilizzando Aspose.Slides per .NET

In Aspose.Slides per .NET, è possibile collegare a livello di codice un video a una diapositiva di presentazione utilizzando il controllo ActiveX. Ciò consente di creare presentazioni interattive in cui il contenuto video può essere riprodotto direttamente all'interno della diapositiva. In questa guida passo passo, ti guideremo attraverso il processo di collegamento di un video a una diapositiva di presentazione utilizzando Aspose.Slides per .NET.

## Prerequisiti:
- Visual Studio (o qualsiasi altro ambiente di sviluppo .NET)
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Passaggio 1: crea un nuovo progetto
Crea un nuovo progetto nel tuo ambiente di sviluppo .NET preferito (ad esempio, Visual Studio) e aggiungi riferimenti alla libreria Aspose.Slides per .NET.

## Passaggio 2: importa gli spazi dei nomi necessari
Nel tuo progetto, importa gli spazi dei nomi necessari per lavorare con Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Passaggio 3: caricare la presentazione
Carica la presentazione PowerPoint nel punto in cui desideri aggiungere il video collegato:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Il tuo codice per aggiungere il video collegato andrà qui
}
```

## Passaggio 4: aggiungi il controllo ActiveX
 Crea un'istanza di`IOleObjectFrame` interfaccia per aggiungere il controllo ActiveX alla diapositiva:

```csharp
ISlide slide = presentation.Slides[0]; // Scegli la diapositiva in cui desideri aggiungere il video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Nel codice sopra, aggiungiamo alla diapositiva un riquadro di controllo ActiveX di dimensioni 640x480. Stiamo specificando il ProgID per il controllo ActiveX ShockwaveFlash, che viene comunemente utilizzato per incorporare video.

## Passaggio 5: impostare le proprietà del controllo ActiveX
Imposta le proprietà del controllo ActiveX per specificare la sorgente video collegata:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Sostituisci con il percorso effettivo del file video
oleObjectFrame.AlternativeText = "Linked Video";
```

 Sostituire`"YourVideoPathHere"` con il percorso effettivo del file video. IL`AlternativeText` La proprietà fornisce una descrizione per il video collegato.

## Passaggio 6: salva la presentazione
Salva la presentazione modificata:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Domande frequenti:

### Come posso specificare la dimensione e la posizione del video collegato sulla diapositiva?
 È possibile regolare le dimensioni e la posizione del riquadro di controllo ActiveX utilizzando i parametri del`AddOleObjectFrame`metodo. I quattro argomenti numerici rappresentano rispettivamente le coordinate X e Y dell'angolo superiore sinistro e la larghezza e l'altezza della cornice.

### Posso collegare video di formati diversi utilizzando questo approccio?
Sì, puoi collegare video di vari formati purché sia disponibile il controllo ActiveX appropriato per quel formato. Ad esempio, il controllo ActiveX ShockwaveFlash utilizzato in questa guida è adatto per i video Flash (SWF). Per altri formati, potrebbe essere necessario utilizzare ProgID diversi.

### Esiste un limite alla dimensione del video collegato?
La dimensione del video collegato potrebbe influire sulle dimensioni complessive e sulle prestazioni della presentazione. Si consiglia di ottimizzare i video per la riproduzione sul Web prima di collegarli alla presentazione.

### Conclusione:
Seguendo i passaggi descritti in questa guida, puoi facilmente collegare un video tramite il controllo ActiveX in una presentazione utilizzando Aspose.Slides per .NET. Questa funzionalità consente di creare presentazioni accattivanti e interattive che incorporano contenuti multimediali senza problemi.

 Per maggiori dettagli e opzioni avanzate, è possibile fare riferimento a[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).