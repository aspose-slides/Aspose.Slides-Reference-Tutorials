---
title: Impostazione dei numeri di diapositiva per le presentazioni utilizzando Aspose.Slides
linktitle: Impostazione dei numeri di diapositiva per le presentazioni utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere e personalizzare i numeri delle diapositive nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida passo passo fornisce esempi di codice sorgente per impostare il progetto, caricare una presentazione, aggiungere numeri alle diapositive, personalizzarne il formato e regolarne il posizionamento.
type: docs
weight: 16
url: /it/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una libreria versatile che consente agli sviluppatori .NET di creare, modificare e manipolare presentazioni PowerPoint a livello di codice. Fornisce un'ampia gamma di funzionalità per interagire con vari elementi di presentazioni, tra cui diapositive, forme, testo, immagini e altro. In questa guida, ci concentreremo sull'aggiunta e sulla personalizzazione dei numeri delle diapositive utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio (o qualsiasi altro ambiente di sviluppo .NET)
-  Aspose.Slides per la libreria .NET (Scarica da[Qui](https://releases.aspose.com/slides/net/)

## Impostazione del progetto

1. Creare un nuovo progetto di Visual Studio (applicazione console, ad esempio).
2. Aggiungi un riferimento alla libreria Aspose.Slides per .NET.

## Caricamento di una presentazione

Per iniziare, carichiamo una presentazione PowerPoint esistente:

```csharp
using Aspose.Slides;

// Carica la presentazione
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Aggiunta di numeri alle diapositive

Successivamente, aggiungiamo i numeri delle diapositive a ciascuna diapositiva della presentazione:

```csharp
// Abilita i numeri delle diapositive
foreach (ISlide slide in presentation.Slides)
{
    // Aggiungi la forma del numero della diapositiva
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Personalizzazione del formato del numero della diapositiva

Puoi personalizzare l'aspetto dei numeri delle diapositive regolando carattere, colore, dimensione e altro:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Personalizza carattere e colore
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Aggiornamento del posizionamento del numero della diapositiva

Puoi anche regolare la posizione dei numeri di diapositiva su ciascuna diapositiva:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Salvataggio della presentazione modificata

Dopo aver aggiunto e personalizzato i numeri delle diapositive, salva la presentazione modificata:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Conclusione

In questa guida, abbiamo esplorato come migliorare le tue presentazioni aggiungendo e personalizzando i numeri delle diapositive utilizzando Aspose.Slides per .NET. Seguendo i passaggi forniti e gli esempi di codice, puoi automatizzare il processo di aggiunta dei numeri alle diapositive e creare presentazioni dall'aspetto professionale.

## Domande frequenti

### Come installo Aspose.Slides per .NET?

 È possibile scaricare la libreria Aspose.Slides per .NET da[Qui](https://releases.aspose.com/slides/net/). Dopo il download, aggiungi un riferimento alla libreria nel tuo progetto .NET.

### Posso personalizzare l'aspetto dei numeri delle diapositive?

Sì, puoi personalizzare il carattere, il colore, la dimensione e altri attributi dei numeri delle diapositive utilizzando gli esempi di codice forniti.

### Come posso regolare la posizione dei numeri di diapositiva su ciascuna diapositiva?

È possibile regolare la posizione dei numeri delle diapositive modificando le coordinate delle forme dei numeri delle diapositive, come mostrato negli esempi di codice.

### Aspose.Slides per .NET serve solo per aggiungere numeri di diapositiva?

No, Aspose.Slides per .NET offre una vasta gamma di funzionalità oltre all'aggiunta di numeri di diapositiva. Ti consente di creare, modificare e manipolare vari elementi delle presentazioni PowerPoint a livello di codice.

### Le modifiche sono reversibili se desidero rimuovere i numeri delle diapositive in un secondo momento?

Sì, puoi rimuovere facilmente i numeri delle diapositive rimuovendo le forme corrispondenti dalle diapositive utilizzando la libreria Aspose.Slides.