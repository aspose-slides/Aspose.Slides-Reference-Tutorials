---
"description": "Scopri come collegare video alle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida dettagliata include codice sorgente e suggerimenti per creare presentazioni interattive e coinvolgenti con video collegati."
"linktitle": "Collegamento video tramite controllo ActiveX"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Collegamento di video tramite controllo ActiveX in PowerPoint"
"url": "/it/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Collegamento di video tramite controllo ActiveX in PowerPoint

Collegamento di un video tramite controllo ActiveX in una presentazione utilizzando Aspose.Slides per .NET

In Aspose.Slides per .NET, è possibile collegare un video a una diapositiva di una presentazione tramite codice utilizzando il controllo ActiveX. Questo permette di creare presentazioni interattive in cui il contenuto video può essere riprodotto direttamente all'interno della diapositiva. In questa guida dettagliata, vi guideremo attraverso il processo di collegamento di un video a una diapositiva di una presentazione utilizzando Aspose.Slides per .NET.

## Prerequisiti:
- Visual Studio (o qualsiasi altro ambiente di sviluppo .NET)
- Libreria Aspose.Slides per .NET. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/net/).

## Passaggio 1: creare un nuovo progetto
Crea un nuovo progetto nel tuo ambiente di sviluppo .NET preferito (ad esempio Visual Studio) e aggiungi riferimenti alla libreria Aspose.Slides per .NET.

## Passaggio 2: importare gli spazi dei nomi necessari
Nel tuo progetto, importa gli spazi dei nomi necessari per lavorare con Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Passaggio 3: carica la presentazione
Carica la presentazione PowerPoint in cui desideri aggiungere il video collegato:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Il tuo codice per aggiungere il video collegato andrà qui
}
```

## Passaggio 4: aggiungere il controllo ActiveX
Crea un'istanza di `IOleObjectFrame` interfaccia per aggiungere il controllo ActiveX alla diapositiva:

```csharp
ISlide slide = presentation.Slides[0]; // Seleziona la diapositiva in cui desideri aggiungere il video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Nel codice sopra, aggiungiamo alla diapositiva un frame di controllo ActiveX di dimensioni 640x480. Specifichiamo il ProgID per il controllo ActiveX ShockwaveFlash, comunemente utilizzato per l'incorporamento di video.

## Passaggio 5: impostare le proprietà del controllo ActiveX
Imposta le proprietà del controllo ActiveX per specificare la sorgente video collegata:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Sostituisci con il percorso effettivo del file video
oleObjectFrame.AlternativeText = "Linked Video";
```

Sostituire `"YourVideoPathHere"` con il percorso effettivo del file video. Il `AlternativeText` La proprietà fornisce una descrizione per il video collegato.

## Passaggio 6: Salva la presentazione
Salva la presentazione modificata:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Domande frequenti:

### Come posso specificare le dimensioni e la posizione del video collegato sulla diapositiva?
È possibile regolare le dimensioni e la posizione della cornice del controllo ActiveX utilizzando i parametri del `AddOleObjectFrame` metodo. I quattro argomenti numerici rappresentano rispettivamente le coordinate X e Y dell'angolo in alto a sinistra e la larghezza e l'altezza della cornice.

### Posso collegare video di formati diversi utilizzando questo approccio?
Sì, è possibile collegare video di vari formati, purché sia disponibile il controllo ActiveX appropriato per quel formato. Ad esempio, il controllo ActiveX ShockwaveFlash utilizzato in questa guida è adatto per i video Flash (SWF). Per altri formati, potrebbe essere necessario utilizzare ProgID diversi.

### C'è un limite alla dimensione del video collegato?
Le dimensioni del video collegato potrebbero influire sulle dimensioni complessive e sulle prestazioni della presentazione. Si consiglia di ottimizzare i video per la riproduzione sul web prima di collegarli alla presentazione.

### Conclusione:
Seguendo i passaggi descritti in questa guida, è possibile collegare facilmente un video tramite controllo ActiveX a una presentazione utilizzando Aspose.Slides per .NET. Questa funzionalità consente di creare presentazioni coinvolgenti e interattive che integrano perfettamente contenuti multimediali.

Per maggiori dettagli e opzioni avanzate, puoi fare riferimento a [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}