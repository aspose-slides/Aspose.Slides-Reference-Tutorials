---
title: Aggiungi collegamento ipertestuale alla diapositiva
linktitle: Aggiungi collegamento ipertestuale alla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere collegamenti ipertestuali alle diapositive in PowerPoint utilizzando Aspose.Slides per .NET. Migliora le presentazioni con contenuti interattivi.
type: docs
weight: 12
url: /it/net/hyperlink-manipulation/add-hyperlink/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una libreria completa che consente agli sviluppatori di creare, modificare e manipolare presentazioni PowerPoint senza fare affidamento su Microsoft Office. Fornisce un'ampia gamma di funzionalità, inclusa l'aggiunta e la gestione dei collegamenti ipertestuali nelle diapositive.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio installato nel sistema.
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://downloads.aspose.com/slides/net).

## Aggiunta di un collegamento ipertestuale a un testo in una diapositiva

1. Creare un nuovo progetto C# in Visual Studio.
2. Aggiungi un riferimento alla DLL Aspose.Slides nel tuo progetto.
3. Utilizza il codice seguente per aggiungere un collegamento ipertestuale a un testo in una diapositiva:

```csharp
using Aspose.Slides;

// Carica la presentazione
Presentation presentation = new Presentation("presentation.pptx");

// Accedi a una diapositiva
ISlide slide = presentation.Slides[0];

// Accedi a una casella di testo
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Aggiungi una porzione di testo con un collegamento ipertestuale
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.esempio.com", HyperlinkAction.MouseClick);
```

## Aggiunta di un collegamento ipertestuale a una forma in una diapositiva

1. Segui i passaggi precedenti per creare un nuovo progetto C# e aggiungere il riferimento Aspose.Slides.
2. Utilizzare il codice seguente per aggiungere un collegamento ipertestuale a una forma in una diapositiva:

```csharp
using Aspose.Slides;

// Carica la presentazione
Presentation presentation = new Presentation("presentation.pptx");

// Accedi a una diapositiva
ISlide slide = presentation.Slides[0];

// Accedere a una forma
IShape shape = slide.Shapes[1];

// Aggiungere un collegamento ipertestuale alla forma
shape.HyperlinkClick = new HyperlinkInfo("https://www.esempio.com", HyperlinkAction.MouseClick);
```

## Aggiunta di un collegamento ipertestuale a una diapositiva

1. Segui i passaggi iniziali per configurare il tuo progetto C# e fare riferimento alla libreria Aspose.Slides.
2. Utilizza il codice seguente per aggiungere un collegamento ipertestuale a una diapositiva:

```csharp
using Aspose.Slides;

// Carica la presentazione
Presentation presentation = new Presentation("presentation.pptx");

// Accedi a una diapositiva
ISlide slide = presentation.Slides[2];

// Aggiungi un collegamento ipertestuale alla diapositiva
slide.HyperlinkClick = new HyperlinkInfo("https://www.esempio.com", HyperlinkAction.MouseClick);
```

## Aggiunta di collegamenti ipertestuali esterni

Oltre ai collegamenti ipertestuali interni, puoi anche aggiungere collegamenti ipertestuali esterni alle tue diapositive. Utilizza lo stesso approccio di cui sopra, ma fornisci l'URL esterno come destinazione del collegamento ipertestuale.

## Modifica e rimozione dei collegamenti ipertestuali

Per modificare un collegamento ipertestuale esistente o rimuoverlo, è possibile accedere alle proprietà del collegamento ipertestuale del rispettivo elemento della diapositiva e apportare le modifiche necessarie.

## Conclusione

L'aggiunta di collegamenti ipertestuali alle diapositive utilizzando Aspose.Slides per .NET è un processo semplice che può migliorare notevolmente l'interattività delle tue presentazioni. Sia che tu voglia collegarti a risorse esterne o creare una navigazione all'interno delle tue diapositive, Aspose.Slides fornisce gli strumenti necessari per svolgere queste attività in modo efficiente.

## Domande frequenti

### Come rimuovo un collegamento ipertestuale da una porzione di testo?

 Per rimuovere un collegamento ipertestuale da una porzione di testo è sufficiente impostare il file`HyperlinkClick` proprietà a`null` per quella porzione.

### Posso aggiungere collegamenti ipertestuali a forme diverse dalle caselle di testo?

Sì, puoi aggiungere collegamenti ipertestuali a varie forme, incluse immagini e forme personalizzate, utilizzando il file`HyperlinkClick` proprietà.

### Aspose.Slides è compatibile con diversi formati PowerPoint?

Sì, Aspose.Slides supporta vari formati PowerPoint, inclusi PPTX, PPT e altri.

### Come posso testare i collegamenti ipertestuali nella mia presentazione?

È possibile eseguire la presentazione in un visualizzatore o editor di PowerPoint per testare la funzionalità dei collegamenti ipertestuali.

### Dove posso scaricare la libreria Aspose.Slides per .NET?

 È possibile scaricare la libreria Aspose.Slides per .NET dal sito Web Aspose:[Scarica Aspose.Slides per .NET](https://releases.aspose.com/slides/net).