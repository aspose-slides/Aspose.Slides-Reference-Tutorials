---
title: Gestisci il controllo ActiveX in PowerPoint
linktitle: Gestisci il controllo ActiveX in PowerPoint
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le presentazioni di PowerPoint con i controlli ActiveX utilizzando Aspose.Slides per .NET. La nostra guida passo passo copre l'inserimento, la manipolazione, la personalizzazione, la gestione degli eventi e altro ancora.
weight: 13
url: /it/net/slide-view-and-layout-manipulation/manage-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

controlli ActiveX sono elementi potenti che possono migliorare la funzionalità e l'interattività delle presentazioni PowerPoint. Questi controlli ti consentono di incorporare e manipolare oggetti come lettori multimediali, moduli di immissione dati e altro direttamente all'interno delle diapositive. In questo articolo esploreremo come gestire i controlli ActiveX in PowerPoint utilizzando Aspose.Slides per .NET, una libreria versatile che consente una perfetta integrazione e manipolazione dei file PowerPoint nelle applicazioni .NET.

## Aggiunta di controlli ActiveX alle diapositive di PowerPoint

Per iniziare a incorporare i controlli ActiveX nelle presentazioni di PowerPoint, attenersi alla seguente procedura:

1.  Crea una nuova presentazione di PowerPoint: innanzitutto crea una nuova presentazione di PowerPoint utilizzando Aspose.Slides per .NET. Puoi fare riferimento a[Aspose.Slides per riferimento all'API .NET](https://reference.aspose.com/slides/net/) per indicazioni su come lavorare con le presentazioni.

2. Aggiungi una diapositiva: utilizza la libreria per aggiungere una nuova diapositiva alla presentazione. Questa sarà la diapositiva in cui desideri inserire il controllo ActiveX.

3. Inserisci il controllo ActiveX: ora è il momento di inserire il controllo ActiveX nella diapositiva. È possibile ottenere ciò seguendo il codice di esempio riportato di seguito:

```csharp
// Carica la presentazione
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Ottieni la diapositiva in cui desideri inserire il controllo ActiveX
ISlide slide = presentation.Slides[0];

// Definire le proprietà del controllo ActiveX
int left = 100; // Specificare la posizione a sinistra
int top = 100; // Specificare la posizione superiore
int width = 200; // Specificare la larghezza
int height = 100; // Specificare l'altezza
string progId = "YourActiveXControl.ProgID"; // Specificare il ProgID del controllo ActiveX

// Aggiungi il controllo ActiveX alla diapositiva
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Assicurati di sostituire`"YourActiveXControl.ProgID"` con l'effettivo ProgID del controllo ActiveX che si desidera inserire.

4. Salva la presentazione: dopo aver inserito il controllo ActiveX, salva la presentazione utilizzando il seguente codice:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Manipolazione dei controlli ActiveX a livello di codice

Dopo aver aggiunto il controllo ActiveX alla diapositiva, potresti voler manipolarlo a livello di codice. Ecco come puoi farlo:

1. Accedi al controllo ActiveX: per accedere alle proprietà e ai metodi del controllo ActiveX, dovrai ottenere un riferimento ad esso. Utilizza il codice seguente per ottenere il controllo dalla diapositiva:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Metodi di richiamo: è possibile richiamare metodi del controllo ActiveX utilizzando il riferimento ottenuto. Ad esempio, se il controllo ActiveX ha un metodo chiamato "Riproduci", puoi chiamarlo in questo modo:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Imposta proprietà: è inoltre possibile impostare le proprietà del controllo ActiveX a livello di codice. Ad esempio, se il controllo ha una proprietà chiamata "Volume", puoi impostarla in questo modo:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Personalizzazione delle proprietà del controllo ActiveX

La personalizzazione delle proprietà del controllo ActiveX può migliorare notevolmente l'esperienza utente della presentazione. Ecco come personalizzare queste proprietà:

1.  Proprietà di accesso: come accennato in precedenza, è possibile accedere alle proprietà del controllo ActiveX utilizzando il file`IOleObjectFrame` riferimento.

2.  Imposta proprietà: utilizza il file`SetProperty`metodo per impostare varie proprietà del controllo ActiveX. Ad esempio, puoi cambiare il colore dello sfondo in questo modo:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Gestione degli eventi associati ai controlli ActiveX

Ai controlli ActiveX sono spesso associati eventi che possono attivare azioni in base alle interazioni dell'utente. Ecco come puoi gestire questi eventi:

1. Iscriviti agli eventi: innanzitutto iscriviti all'evento desiderato del controllo ActiveX. Ad esempio, se il controllo ha un evento "Clicked", puoi iscriverti ad esso in questo modo:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Il tuo codice di gestione degli eventi qui
};
```

## Eliminazione dei controlli ActiveX dalle diapositive

Se desideri rimuovere un controllo ActiveX da una diapositiva, procedi nel seguente modo:

1.  Accedi al controllo: ottieni un riferimento al controllo ActiveX utilizzando il file`IOleObjectFrame` riferimento come mostrato in precedenza.

2. Rimuovere il controllo: utilizzare il codice seguente per rimuovere il controllo dalla diapositiva:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Salvataggio ed esportazione della presentazione modificata

Dopo aver apportato tutte le modifiche necessarie alla presentazione, puoi salvarla ed esportarla utilizzando il seguente codice:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Vantaggi dell'utilizzo di Aspose.Slides per .NET

Aspose.Slides per .NET semplifica il processo di lavoro con i controlli ActiveX nelle presentazioni di PowerPoint fornendo un'API intuitiva che consente di integrare e manipolare perfettamente questi controlli. Alcuni vantaggi dell'utilizzo di Aspose.Slides per .NET includono:

- Facile inserimento dei controlli ActiveX sulle diapositive.
- Metodi completi per l'interazione a livello di codice con i controlli.
- Personalizzazione semplificata delle proprietà di controllo.
- Gestione efficiente degli eventi per presentazioni interattive.
- Rimozione semplificata dei controlli dalle diapositive.

## Conclusione

Incorporare i controlli ActiveX nelle presentazioni PowerPoint può aumentare il livello di interattività e coinvolgimento del tuo pubblico. Con Aspose.Slides per .NET, hai a tua disposizione un potente strumento per gestire senza problemi i controlli ActiveX, consentendoti di creare presentazioni dinamiche e accattivanti che lasciano un'impressione duratura.

## Domande frequenti

### Come posso aggiungere un controllo ActiveX a una diapositiva specifica?

 Per aggiungere un controllo ActiveX a una diapositiva specifica, puoi utilizzare il file`AddOleObjectFrame` metodo fornito da Aspose.Slides per .NET. Questo metodo consente di specificare la posizione, la dimensione e il ProgID del controllo ActiveX che si desidera inserire.

### Posso manipolare i controlli ActiveX a livello di codice?

 Sì, puoi manipolare i controlli ActiveX a livello di codice utilizzando Aspose.Slides per .NET. Ottenendo un riferimento al`IOleObjectFrame` che rappresenta il controllo, è possibile richiamare metodi e impostare proprietà per interagire dinamicamente con il controllo.

### Come gestisco gli eventi

 attivato dai controlli ActiveX?

È possibile gestire gli eventi attivati dai controlli ActiveX iscrivendosi agli eventi corrispondenti utilizzando il file`EventClick` (o simile) gestore di eventi. Ciò consente di eseguire azioni specifiche in risposta alle interazioni dell'utente con il controllo.

### È possibile personalizzare l'aspetto dei controlli ActiveX?

 Assolutamente, puoi personalizzare l'aspetto dei controlli ActiveX utilizzando il file`SetProperty` metodo fornito da Aspose.Slides per .NET. Questo metodo ti consente di modificare varie proprietà, come il colore di sfondo, lo stile del carattere e altro.

### Posso rimuovere un controllo ActiveX da una diapositiva?

 Sì, puoi rimuovere un controllo ActiveX da una diapositiva utilizzando il file`Remove` metodo del`Shapes` collezione. Passa il riferimento a`IOleObjectFrame` che rappresenta il controllo come argomento per il`Remove` metodo e il controllo verrà rimosso dalla diapositiva.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
