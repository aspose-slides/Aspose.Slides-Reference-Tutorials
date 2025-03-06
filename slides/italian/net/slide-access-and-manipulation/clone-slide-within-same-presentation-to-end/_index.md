---
title: Duplica diapositiva alla fine della presentazione esistente
linktitle: Duplica diapositiva alla fine della presentazione esistente
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come duplicare e aggiungere una diapositiva alla fine di una presentazione PowerPoint esistente utilizzando Aspose.Slides per .NET. Questa guida passo passo fornisce esempi di codice sorgente e copre l'installazione, la duplicazione delle diapositive, la modifica e altro ancora.
weight: 22
url: /it/net/slide-access-and-manipulation/clone-slide-within-same-presentation-to-end/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una potente API che consente agli sviluppatori di lavorare con presentazioni PowerPoint in vari modi, inclusa la creazione, la modifica e la manipolazione delle diapositive a livello di codice. Supporta un'ampia gamma di funzionalità, rendendolo una scelta popolare per automatizzare le attività relative alle presentazioni.

## Passaggio 1: impostazione del progetto

 Prima di iniziare, assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarlo da[Link per scaricare](https://releases.aspose.com/slides/net/). Crea un nuovo progetto di Visual Studio e aggiungi un riferimento alla libreria Aspose.Slides scaricata.

## Passaggio 2: caricamento di una presentazione esistente

In questo passaggio, caricheremo una presentazione PowerPoint esistente utilizzando Aspose.Slides per .NET. Puoi utilizzare il seguente snippet di codice come riferimento:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Carica la presentazione esistente
        Presentation presentation = new Presentation("existing-presentation.pptx");
    }
}
```

 Sostituire`"existing-presentation.pptx"`con il percorso del file di presentazione PowerPoint effettivo.

## Passaggio 3: duplicazione di una diapositiva

Per duplicare una diapositiva, dovremo prima selezionare la diapositiva che vogliamo duplicare. Quindi lo cloneremo per creare una copia identica. Ecco come puoi farlo:

```csharp
// Seleziona la diapositiva da duplicare (l'indice parte da 0)
ISlide sourceSlide = presentation.Slides[0];

// Clona la diapositiva selezionata
ISlide duplicatedSlide = presentation.Slides.InsertClone(1, sourceSlide);
```

In questo esempio, stiamo duplicando la prima diapositiva e inserendo la diapositiva duplicata nell'indice 1 (posizione 2).

## Passaggio 4: aggiunta della diapositiva duplicata alla fine

Ora che abbiamo una diapositiva duplicata, aggiungiamola alla fine della presentazione. È possibile utilizzare il seguente codice:

```csharp
// Aggiungi la diapositiva duplicata alla fine della presentazione
presentation.Slides.AddClone(duplicatedSlide);
```

Questo frammento di codice aggiunge la diapositiva duplicata alla fine della presentazione.

## Passaggio 5: salvataggio della presentazione modificata

Dopo aver aggiunto la diapositiva duplicata, dobbiamo salvare la presentazione modificata. Ecco come:

```csharp
//Salva la presentazione modificata
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

 Sostituire`"modified-presentation.pptx"` con il nome desiderato per la presentazione modificata.

## Conclusione

In questa guida, abbiamo esplorato come duplicare una diapositiva e aggiungerla alla fine di una presentazione PowerPoint esistente utilizzando Aspose.Slides per .NET. Questa potente libreria semplifica il processo di lavoro con le presentazioni a livello di codice, offrendo un'ampia gamma di funzionalità per varie attività.

## Domande frequenti

### Come posso ottenere Aspose.Slides per .NET?

 È possibile ottenere la libreria Aspose.Slides per .NET da[Link per scaricare](https://releases.aspose.com/slides/net/). Assicurati di seguire le istruzioni di installazione fornite sul sito web.

### Posso duplicare più diapositive contemporaneamente?

Sì, puoi duplicare più diapositive contemporaneamente scorrendo le diapositive e clonandole secondo necessità. Modifica il codice di conseguenza per soddisfare le tue esigenze.

### Aspose.Slides per .NET è gratuito?

No, Aspose.Slides per .NET è una libreria commerciale che richiede una licenza valida per l'utilizzo. Puoi controllare i dettagli dei prezzi sul sito web di Aspose.

### Aspose.Slides supporta altri formati di file?

Sì, Aspose.Slides supporta vari formati PowerPoint, inclusi PPT, PPTX, PPS e altri. Fare riferimento alla documentazione per un elenco completo dei formati supportati.

### Posso modificare il contenuto della diapositiva utilizzando Aspose.Slides?

Assolutamente! Aspose.Slides ti consente non solo di duplicare le diapositive ma anche di manipolarne il contenuto, come testo, immagini, forme e animazioni, a livello di codice.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
