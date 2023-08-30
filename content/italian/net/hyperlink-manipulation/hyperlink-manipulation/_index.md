---
title: Manipolazione dei collegamenti ipertestuali in Aspose.Slides
linktitle: Manipolazione dei collegamenti ipertestuali in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le presentazioni di PowerPoint con collegamenti ipertestuali utilizzando Aspose.Slides per .NET. Crea, modifica e gestisci contenuti interattivi senza problemi.
type: docs
weight: 10
url: /it/net/hyperlink-manipulation/hyperlink-manipulation/
---

## Introduzione alla manipolazione dei collegamenti ipertestuali

collegamenti ipertestuali arricchiscono le presentazioni collegando diapositive, documenti, pagine Web e altro ancora. Forniscono un'esperienza interattiva, migliorando il coinvolgimento del pubblico. Aspose.Slides per .NET offre funzionalità complete per gestire i collegamenti ipertestuali a livello di codice, offrendoti il pieno controllo sulla navigazione della presentazione.

## Impostazione dei collegamenti ipertestuali nelle diapositive

 Per creare collegamenti ipertestuali, è possibile utilizzare Aspose.Slides per .NET`HyperlinkManager` classe. Questa classe ti consente di aggiungere vari tipi di collegamenti ipertestuali a forme o testo specifici nelle diapositive.

```csharp
// Esempio di codice per aggiungere un collegamento ipertestuale a una forma
HyperlinkManager.AddHyperlinkToShape(shape, "https://www.example.com", "Visita il nostro sito web");
```

## Modifica dei collegamenti ipertestuali

È possibile modificare facilmente i collegamenti ipertestuali esistenti utilizzando Aspose.Slides per .NET. Ciò è utile quando è necessario aggiornare l'URL di destinazione o modificare il testo del collegamento ipertestuale.

```csharp
// Esempio di codice per modificare l'URL di un collegamento ipertestuale
HyperlinkManager.ModifyHyperlinkUrl(shape, "https://nuovourl.com");
```

## Rimozione dei collegamenti ipertestuali

Se desideri rimuovere un collegamento ipertestuale da una forma, Aspose.Slides per .NET fornisce un metodo semplice per farlo.

```csharp
// Esempio di codice per rimuovere un collegamento ipertestuale da una forma
HyperlinkManager.RemoveHyperlink(shape);
```

## Lavorare con i punti di ancoraggio

I punti di ancoraggio sono cruciali quando si ha a che fare con i collegamenti ipertestuali all'interno delle diapositive. Determinano la posizione a cui punta il collegamento ipertestuale all'interno della diapositiva di destinazione.

```csharp
// Esempio di codice per impostare un punto di ancoraggio per un collegamento ipertestuale
HyperlinkManager.SetHyperlinkAnchor(shape, targetSlide, anchorX, anchorY);
```

## Gestione di diversi tipi di collegamenti ipertestuali

Aspose.Slides per .NET supporta vari tipi di collegamenti ipertestuali, inclusi collegamenti URL, collegamenti a documenti interni, collegamenti a indirizzi e-mail e altro.

```csharp
// Esempio di codice per aggiungere un collegamento ipertestuale di posta elettronica
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");
```

## Aggiunta di descrizioni comandi ai collegamenti ipertestuali

Le descrizioni comandi forniscono informazioni aggiuntive quando gli utenti passano il mouse sui collegamenti ipertestuali. Aspose.Slides per .NET ti consente di impostare descrizioni comandi per i tuoi collegamenti ipertestuali.

```csharp
// Esempio di codice per aggiungere una descrizione comando a un collegamento ipertestuale
HyperlinkManager.AddHyperlinkWithTooltip(shape, "https://www.example.com", "Visita il nostro sito web", "Fai clic per esplorare");
```

## Gestione dei collegamenti ipertestuali esterni

Puoi anche gestire collegamenti ipertestuali esterni utilizzando Aspose.Slides per .NET, assicurandoti che le tue presentazioni rimangano connesse alle risorse online pertinenti.

```csharp
// Esempio di codice per aprire un collegamento ipertestuale in un browser Web
HyperlinkManager.OpenHyperlinkInBrowser(shape);
```

## Collegamenti ipertestuali nelle diapositive master

Le diapositive master spesso contengono elementi ricorrenti. Aspose.Slides per .NET ti consente di applicare collegamenti ipertestuali alle diapositive master, garantendo coerenza nella presentazione.

```csharp
// Esempio di codice per impostare un collegamento ipertestuale in una diapositiva master
HyperlinkManager.SetHyperlinkInMasterSlide(masterSlide, "https://www.example.com", "Visita il nostro sito web");
```

## Estrazione delle informazioni sui collegamenti ipertestuali

È possibile estrarre informazioni da collegamenti ipertestuali esistenti utilizzando Aspose.Slides per .NET, che può essere utile per scopi di analisi o reporting.

```csharp
// Esempio di codice per estrarre informazioni sul collegamento ipertestuale
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

## Aggiunta di collegamenti ipertestuali a immagini e forme

I collegamenti ipertestuali possono essere aggiunti non solo al testo ma anche a immagini e forme all'interno delle diapositive.

```csharp
// Esempio di codice per aggiungere un collegamento ipertestuale a un'immagine
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Fai clic sull'immagine per saperne di più");
```

## Collegamento a indirizzi e-mail e numeri di telefono

Aspose.Slides per .NET consente di creare collegamenti ipertestuali che attivano la composizione di e-mail o avviano chiamate telefoniche quando vengono cliccati.

```csharp
// Esempio di codice per creare un collegamento ipertestuale di posta elettronica
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");

// Esempio di codice per creare un collegamento ipertestuale al numero di telefono
HyperlinkManager.AddPhoneHyperlink(shape, "+1234567890", "Call our support");
```

## Formattazione del collegamento ipertestuale

Puoi applicare la formattazione ai collegamenti ipertestuali per renderli visivamente distinti dal testo o dalle forme normali.

```csharp
// Esempio di codice per formattare l'aspetto di un collegamento ipertestuale
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

## Aggiunta di collegamenti ipertestuali tramite API

Aspose.Slides per .NET fornisce un'API robusta per la manipolazione dei collegamenti ipertestuali. Puoi integrare queste funzionalità perfettamente nelle tue applicazioni.

```csharp
// Esempio di codice per aggiungere un collegamento ipertestuale tramite l'API
HyperlinkManager.AddHyperlink(shape, HyperlinkType.Url, "https://www.esempio.com");
```

## Conclusione

La manipolazione dei collegamenti ipertestuali utilizzando Aspose.Slides per .NET offre un kit di strumenti completo per migliorare l'interattività e il coinvolgimento delle presentazioni PowerPoint. Con la possibilità di creare, modificare e gestire i collegamenti ipertestuali, puoi creare presentazioni dinamiche e informative che affascinano il tuo pubblico.

## Domande frequenti

### Come rimuovo un collegamento ipertestuale da una forma?

Per rimuovere un collegamento ipertestuale da una forma, è possibile utilizzare il codice seguente:

```csharp
HyperlinkManager.RemoveHyperlink(shape);
```

### Posso applicare collegamenti ipertestuali alle immagini nelle mie diapositive?

Sì, puoi aggiungere collegamenti ipertestuali a immagini e forme all'interno delle tue diapositive utilizzando Aspose.Slides per .NET. Per esempio:

```csharp
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com", "Fai clic sull'immagine per saperne di più");
```

### È possibile formattare l'aspetto di un collegamento ipertestuale?

Certamente! È possibile formattare l'aspetto di un collegamento ipertestuale utilizzando Aspose.Slides per .NET. Ecco un esempio:

```csharp
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

### Come posso estrarre informazioni da un collegamento ipertestuale esistente?

È possibile estrarre informazioni da un collegamento ipertestuale esistente utilizzando il seguente approccio:

```csharp
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

### Dove posso accedere a una documentazione più dettagliata su Aspose.Slides per .NET?

Per informazioni più dettagliate ed esempi di codice, è possibile fare riferimento a[documentazione](https://reference.aspose.com/slides/net/) per Aspose.Slides per .NET.