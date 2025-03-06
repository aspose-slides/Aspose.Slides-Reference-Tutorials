---
title: Aggiunta di collegamenti ipertestuali alle diapositive in .NET utilizzando Aspose.Slides
linktitle: Aggiungi collegamento ipertestuale alla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere collegamenti ipertestuali alle diapositive di PowerPoint con Aspose.Slides per .NET. Migliora le tue presentazioni con elementi interattivi.
type: docs
weight: 12
url: /it/net/hyperlink-manipulation/add-hyperlink/
---

Nel mondo delle presentazioni digitali, l’interattività è fondamentale. L'aggiunta di collegamenti ipertestuali alle diapositive può rendere la presentazione più coinvolgente e informativa. Aspose.Slides per .NET è una potente libreria che ti consente di creare, modificare e manipolare presentazioni PowerPoint a livello di codice. In questo tutorial, ti mostreremo come aggiungere collegamenti ipertestuali alle tue diapositive utilizzando Aspose.Slides per .NET. 

## Prerequisiti

Prima di approfondire l'aggiunta di collegamenti ipertestuali alle diapositive, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio: dovresti avere Visual Studio installato sul tuo computer per scrivere ed eseguire il codice .NET.

2. Aspose.Slides per .NET: è necessario che sia installata la libreria Aspose.Slides per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

3. Conoscenza di base di C#: la familiarità con la programmazione C# sarà utile.

## Importa spazi dei nomi

Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto C#. In questo caso, avrai bisogno dei seguenti spazi dei nomi dalla libreria Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Ora suddividiamo il processo di aggiunta di collegamenti ipertestuali alle diapositive in più passaggi.

## Passaggio 1: inizializza la presentazione

Innanzitutto, crea una nuova presentazione utilizzando Aspose.Slides. Ecco come puoi farlo:

```csharp
using (Presentation presentation = new Presentation())
{
    // Il tuo codice va qui
}
```

Questo codice inizializza una nuova presentazione di PowerPoint.

## Passaggio 2: aggiungi cornice di testo

Ora aggiungiamo una cornice di testo alla diapositiva. Questa cornice di testo fungerà da elemento cliccabile nella diapositiva. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Il codice sopra crea una forma automatica rettangolare e aggiunge una cornice di testo con il testo "Aspose: File Format APIs".

## Passaggio 3: aggiungi il collegamento ipertestuale

Successivamente, aggiungiamo un collegamento ipertestuale alla cornice di testo che hai creato. Ciò renderà il testo cliccabile.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

In questo passaggio, impostiamo l'URL del collegamento ipertestuale su "https://www.aspose.com/" e forniamo una descrizione comando per ulteriori informazioni. Puoi anche formattare l'aspetto del collegamento ipertestuale, come mostrato sopra.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione con il collegamento ipertestuale aggiunto.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Questo codice salva la presentazione come "presentation-out.pptx".

Ora hai aggiunto con successo un collegamento ipertestuale a una diapositiva utilizzando Aspose.Slides per .NET.

## Conclusione

In questo tutorial, abbiamo esplorato come aggiungere collegamenti ipertestuali alle diapositive nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Seguendo questi passaggi puoi rendere le tue presentazioni più interattive e coinvolgenti, fornendo preziosi collegamenti a risorse o informazioni aggiuntive.

 Per informazioni e documentazione più dettagliate, visitare il[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).

## Domande frequenti

### 1. Posso aggiungere collegamenti ipertestuali ad altre forme oltre alle cornici di testo?

Sì, puoi aggiungere collegamenti ipertestuali a varie forme come rettangoli, immagini e altro utilizzando Aspose.Slides per .NET.

### 2. Come posso rimuovere un collegamento ipertestuale da una forma in una diapositiva di PowerPoint?

 È possibile rimuovere un collegamento ipertestuale da una forma impostando il file`HyperlinkClick` proprietà a`null`.

### 3. Posso modificare dinamicamente l'URL del collegamento ipertestuale nel mio codice?

 Assolutamente! Puoi aggiornare l'URL di un collegamento ipertestuale in qualsiasi punto del codice modificando il file`Hyperlink` proprietà.

### 4. Quali altri elementi interattivi posso aggiungere alle diapositive di PowerPoint utilizzando Aspose.Slides?

Aspose.Slides offre una vasta gamma di funzionalità interattive, inclusi pulsanti di azione, elementi multimediali e animazioni.

### 5. Aspose.Slides è disponibile per altri linguaggi di programmazione?

Sì, Aspose.Slides è disponibile per vari linguaggi di programmazione, inclusi Java e Python.