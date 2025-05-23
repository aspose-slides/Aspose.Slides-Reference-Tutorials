---
"description": "Scopri come aggiungere collegamenti ipertestuali alle diapositive di PowerPoint con Aspose.Slides per .NET. Arricchisci le tue presentazioni con elementi interattivi."
"linktitle": "Aggiungi collegamento ipertestuale alla diapositiva"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aggiunta di collegamenti ipertestuali alle diapositive in .NET utilizzando Aspose.Slides"
"url": "/it/net/hyperlink-manipulation/add-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiunta di collegamenti ipertestuali alle diapositive in .NET utilizzando Aspose.Slides


Nel mondo delle presentazioni digitali, l'interattività è fondamentale. L'aggiunta di collegamenti ipertestuali alle diapositive può rendere la presentazione più coinvolgente e informativa. Aspose.Slides per .NET è una potente libreria che consente di creare, modificare e manipolare le presentazioni di PowerPoint a livello di codice. In questo tutorial, vi mostreremo come aggiungere collegamenti ipertestuali alle diapositive utilizzando Aspose.Slides per .NET. 

## Prerequisiti

Prima di addentrarci nell'aggiunta di collegamenti ipertestuali alle diapositive, assicurati di avere i seguenti prerequisiti:

1. Visual Studio: per scrivere ed eseguire il codice .NET è necessario che Visual Studio sia installato sul computer.

2. Aspose.Slides per .NET: è necessario che la libreria Aspose.Slides per .NET sia installata. È possibile scaricarla da [Qui](https://releases.aspose.com/slides/net/).

3. Conoscenza di base del linguaggio C#: sarà utile avere familiarità con la programmazione C#.

## Importa spazi dei nomi

Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto C#. In questo caso, avrai bisogno dei seguenti spazi dei nomi dalla libreria Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Ora scomponiamo il processo di aggiunta di collegamenti ipertestuali alle diapositive in più passaggi.

## Passaggio 1: inizializzare la presentazione

Per prima cosa, crea una nuova presentazione usando Aspose.Slides. Ecco come fare:

```csharp
using (Presentation presentation = new Presentation())
{
    // Il tuo codice va qui
}
```

Questo codice inizializza una nuova presentazione PowerPoint.

## Passaggio 2: aggiungere la cornice di testo

Ora aggiungiamo una cornice di testo alla diapositiva. Questa cornice di testo fungerà da elemento cliccabile nella diapositiva. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Il codice sopra crea una forma automatica rettangolare e aggiunge una cornice di testo con il testo "Aspose: API del formato file".

## Passaggio 3: aggiungere collegamento ipertestuale

Ora aggiungiamo un collegamento ipertestuale alla cornice di testo che hai creato. Questo renderà il testo cliccabile.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

In questa fase, impostiamo l'URL del collegamento ipertestuale su "https://www.aspose.com/" e forniamo un suggerimento per informazioni aggiuntive. È anche possibile formattare l'aspetto del collegamento ipertestuale, come mostrato sopra.

## Passaggio 4: Salva la presentazione

Infine, salva la presentazione con il collegamento ipertestuale aggiunto.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Questo codice salva la presentazione come "presentation-out.pptx".

Ora hai aggiunto correttamente un collegamento ipertestuale a una diapositiva utilizzando Aspose.Slides per .NET.

## Conclusione

In questo tutorial abbiamo spiegato come aggiungere collegamenti ipertestuali alle diapositive delle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Seguendo questi passaggi, puoi rendere le tue presentazioni più interattive e coinvolgenti, fornendo preziosi link a risorse o informazioni aggiuntive.

Per informazioni e documentazione più dettagliate, visitare il sito [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/).

## Domande frequenti

### 1. Posso aggiungere collegamenti ipertestuali ad altre forme oltre alle cornici di testo?

Sì, puoi aggiungere collegamenti ipertestuali a varie forme, come rettangoli, immagini e altro ancora, utilizzando Aspose.Slides per .NET.

### 2. Come posso rimuovere un collegamento ipertestuale da una forma in una diapositiva di PowerPoint?

È possibile rimuovere un collegamento ipertestuale da una forma impostando `HyperlinkClick` proprietà a `null`.

### 3. Posso modificare dinamicamente l'URL del collegamento ipertestuale nel mio codice?

Assolutamente! Puoi aggiornare l'URL di un collegamento ipertestuale in qualsiasi punto del codice modificando `Hyperlink` proprietà.

### 4. Quali altri elementi interattivi posso aggiungere alle diapositive di PowerPoint utilizzando Aspose.Slides?

Aspose.Slides offre un'ampia gamma di funzionalità interattive, tra cui pulsanti di azione, elementi multimediali e animazioni.

### 5. Aspose.Slides è disponibile per altri linguaggi di programmazione?

Sì, Aspose.Slides è disponibile per vari linguaggi di programmazione, tra cui Java e Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}