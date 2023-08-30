---
title: Creazione di forme di gruppo nelle diapositive di presentazione con Aspose.Slides
linktitle: Creazione di forme di gruppo nelle diapositive di presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare accattivanti diapositive di presentazione con forme di gruppo utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo e l'esempio di codice sorgente per aggiungere, raggruppare e trasformare facilmente le forme, migliorando le tue presentazioni.
type: docs
weight: 11
url: /it/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una libreria completa e ricca di funzionalità che consente agli sviluppatori di manipolare le presentazioni di PowerPoint a livello di codice. Sia che tu voglia creare, modificare o convertire file di presentazione, Aspose.Slides offre un'ampia gamma di strumenti e funzionalità per semplificare il processo.

## Prerequisiti

Prima di iniziare a lavorare con Aspose.Slides per .NET, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio: installa Visual Studio sul tuo computer.
-  Libreria Aspose.Slides: scarica e fai riferimento alla libreria Aspose.Slides nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Aggiunta di Aspose.Slides al tuo progetto

1. Scarica la libreria Aspose.Slides dal collegamento fornito.
2. Crea un nuovo progetto in Visual Studio o aprine uno esistente.
3. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e seleziona "Gestisci pacchetti NuGet".
4. Scegli la scheda "Sfoglia" e cerca "Aspose.Slides".
5. Installa il pacchetto Aspose.Slides nel tuo progetto.

## Creazione di una nuova presentazione

Iniziamo creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides:

```csharp
using Aspose.Slides;

// Crea una nuova presentazione
Presentation presentation = new Presentation();
```

## Aggiunta di forme alla diapositiva

Successivamente, aggiungiamo alcune forme alla diapositiva. In questo esempio, aggiungeremo due rettangoli:

```csharp
// Accedi alla prima diapositiva
ISlide slide = presentation.Slides[0];

// Aggiungi rettangoli alla diapositiva
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Raggruppamento di forme insieme

Ora raggruppiamo le forme per gestirle collettivamente:

```csharp
// Forme di gruppo
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Applicazione di trasformazioni a forme raggruppate

Puoi applicare varie trasformazioni alle forme raggruppate. Ad esempio, ruotiamo le forme raggruppate di 45 gradi:

```csharp
// Ruota il gruppo di 45 gradi
groupShape.Rotation = 45;
```

## Esempio di codice sorgente

Ecco l'esempio di codice sorgente completo della creazione di forme di gruppo utilizzando Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Crea una nuova presentazione
            Presentation presentation = new Presentation();

            // Accedi alla prima diapositiva
            ISlide slide = presentation.Slides[0];

            // Aggiungi rettangoli alla diapositiva
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Forme di gruppo
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Ruota il gruppo di 45 gradi
            groupShape.Rotation = 45;

            // Salva la presentazione
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusione

In questo tutorial hai imparato come creare forme di gruppo nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. La libreria fornisce un modo semplice per aggiungere forme, raggrupparle e applicare trasformazioni per migliorare dinamicamente le tue presentazioni.

## Domande frequenti

### Come installo Aspose.Slides per .NET?

 È possibile scaricare la libreria Aspose.Slides dal collegamento fornito:[Qui](https://releases.aspose.com/slides/net/). Una volta scaricato, puoi aggiungerlo al tuo progetto utilizzando i pacchetti NuGet.

### Posso applicare trasformazioni diverse alle forme raggruppate?

Sì, puoi applicare varie trasformazioni come rotazione, ridimensionamento e posizionamento alle forme raggruppate, consentendoti di personalizzare l'aspetto visivo delle tue diapositive.

### Aspose.Slides è adatto sia per creare che per modificare presentazioni?

Assolutamente! Aspose.Slides per .NET è una libreria versatile che supporta la creazione, la modifica e la conversione di file di presentazione. Fornisce una vasta gamma di funzionalità per soddisfare le diverse esigenze.

### Posso raggruppare insieme forme di tipo diverso?

 Sì, puoi raggruppare insieme forme di diverso tipo, come rettangoli, cerchi e caselle di testo, utilizzando il comando`GroupShapes` metodo. Ciò ti consente di gestirli e manipolarli collettivamente.

### Aspose.Slides è adatto solo per applicazioni .NET?

Sì, Aspose.Slides è progettato specificamente per le applicazioni .NET. Tuttavia, sono disponibili anche versioni per altri linguaggi di programmazione, come Java.