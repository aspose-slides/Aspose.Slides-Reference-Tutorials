---
title: Aggiunta dell'offset allungamento a sinistra per la cornice in Aspose.Slides
linktitle: Aggiunta dell'offset allungamento a sinistra per la cornice in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere l'offset allungato a sinistra per una cornice in PowerPoint utilizzando Aspose.Slides per .NET. Guida passo passo con esempio di codice sorgente completo.
type: docs
weight: 14
url: /it/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una libreria completa che consente agli sviluppatori .NET di lavorare con presentazioni PowerPoint senza la necessità di Microsoft Office. Fornisce un'ampia gamma di funzionalità, tra cui la creazione, la modifica e la manipolazione di diapositive, forme, testo, immagini e altro ancora.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio installato sul tuo computer.
2. Conoscenza di base di C# e .NET framework.
3.  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Impostazione del progetto

Iniziamo configurando un nuovo progetto C# in Visual Studio:

1. Apri VisualStudio.
2. Fare clic su "Crea un nuovo progetto".
3. Seleziona "App console (.NET Framework/Core)".
4. Scegli un nome e una posizione adatti per il tuo progetto.
5. Fai clic su "Crea".

Successivamente, aggiungi un riferimento alla libreria Aspose.Slides per .NET nel tuo progetto. Fare clic con il pulsante destro del mouse su "Riferimenti" in Esplora soluzioni, scegliere "Gestisci pacchetti NuGet", cercare "Aspose.Slides" e installare il pacchetto.

## Aggiunta dell'offset allungamento a sinistra per la cornice immagine

Per aggiungere un offset di stiramento a sinistra per una cornice utilizzando Aspose.Slides per .NET, attenersi alla seguente procedura:

1.  Caricare il file di presentazione utilizzando`Presentation` classe.
2. Individua la diapositiva contenente la cornice che desideri modificare.
3. Accedi alla forma della cornice scorrendo le forme sulla diapositiva.
4.  Applicare l'offset di stiramento a sinistra utilizzando`PictureFrame` classe.

## Codice di esempio

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Carica la presentazione
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // Ottieni la prima diapositiva
                ISlide slide = presentation.Slides[0];

                // Scorri le forme sulla diapositiva
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // Applicare l'offset di stiramento a sinistra
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // Salva la presentazione modificata
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

In questo esempio, carichiamo una presentazione, iteriamo tra le forme sulla prima diapositiva e, se troviamo la forma di una cornice, applichiamo un offset di allungamento di -10 a sinistra.

## Testare l'applicazione

Per testare l'applicazione, attenersi alla seguente procedura:

1. Assicurati di avere una presentazione PowerPoint di esempio (`sample.pptx`) con almeno una cornice.
2. Eseguire l'applicazione.
3.  La presentazione modificata con l'offset di stiramento aggiunto verrà salvata con nome`output.pptx`.

## Conclusione

In questo tutorial, hai imparato come aggiungere un offset di stiramento a sinistra per una cornice in Aspose.Slides utilizzando .NET. Aspose.Slides per .NET fornisce un potente set di strumenti per la manipolazione a livello di codice delle presentazioni PowerPoint, consentendo agli sviluppatori di creare presentazioni dinamiche e personalizzate senza problemi.

## Domande frequenti

### Come posso installare Aspose.Slides per .NET?

 È possibile scaricare Aspose.Slides per .NET dal sito Web[Qui](https://releases.aspose.com/slides/net/).

### Posso utilizzare Aspose.Slides per altre attività di manipolazione di PowerPoint?

Assolutamente! Aspose.Slides per .NET offre un'ampia gamma di funzionalità, tra cui la creazione, la modifica e la conversione di presentazioni PowerPoint. Puoi esplorare la sua documentazione per maggiori dettagli ed esempi.

### Aspose.Slides è compatibile con diversi formati PowerPoint?

Sì, Aspose.Slides supporta vari formati PowerPoint, inclusi PPTX, PPT, POTX e altri. Supporta anche la conversione tra diversi formati.

### Come posso personalizzare altre proprietà delle forme in una presentazione?

Puoi accedere e modificare varie proprietà delle forme, inclusi testo, posizione, dimensione, formattazione e altro, utilizzando la libreria Aspose.Slides. Consulta la documentazione per informazioni complete ed esempi.

### Posso utilizzare Aspose.Slides con altri linguaggi di programmazione?

Sì, Aspose.Slides fornisce librerie per vari linguaggi di programmazione, tra cui Java, Python e altri. Puoi scegliere quello più adatto al tuo ambiente di sviluppo.