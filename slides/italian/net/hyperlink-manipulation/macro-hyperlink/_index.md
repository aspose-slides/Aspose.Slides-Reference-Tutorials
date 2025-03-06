---
title: Come impostare il collegamento ipertestuale macro Fare clic su Aspose.Slides per .NET
linktitle: Gestione dei collegamenti ipertestuali tramite macro
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come impostare collegamenti ipertestuali macro nelle tue presentazioni con Aspose.Slides per .NET. Migliora l'interattività e coinvolgi il tuo pubblico.
weight: 13
url: /it/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Nel mondo dello sviluppo software moderno, la creazione di presentazioni dinamiche e interattive è un aspetto fondamentale. Aspose.Slides per .NET è una potente libreria che ti consente di lavorare con le presentazioni in modo fluido. Che tu stia creando una presentazione aziendale o una presentazione didattica, la possibilità di impostare clic su macro collegamenti ipertestuali può migliorare notevolmente l'esperienza dell'utente. In questa guida passo passo, ti guideremo attraverso il processo di impostazione di un clic sul collegamento ipertestuale macro utilizzando Aspose.Slides per .NET. 

## Prerequisiti

Prima di immergerci nel tutorial passo passo, ci sono alcuni prerequisiti che dovresti avere:

1.Visual Studio: assicurati di avere Visual Studio installato sul tuo computer, poiché questo sarà il nostro ambiente di sviluppo.

 2.Aspose.Slides per .NET: sarà necessario avere installato la libreria Aspose.Slides per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

3.Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale da seguire insieme a questo tutorial.

## Importa spazi dei nomi

Nel primo passaggio, importiamo gli spazi dei nomi necessari per lavorare con Aspose.Slides:

### Passaggio 1: importa gli spazi dei nomi

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Abbiamo importato il file`Aspose.Slides` namespace, che è lo spazio dei nomi principale per lavorare con le presentazioni, e il file`Aspose.Slides.Export` spazio dei nomi.

## Impostazione del clic sul collegamento ipertestuale macro

Passiamo ora alla parte principale di questo tutorial: impostare un clic sul collegamento ipertestuale macro nella presentazione.

### Passaggio 2: inizializza la presentazione

Per prima cosa dobbiamo inizializzare una nuova presentazione.

```csharp
using (Presentation presentation = new Presentation())
{
    // Il tuo codice andrà qui.
}
```

All'interno di questa istruzione using, crei un nuovo oggetto di presentazione ed esegui tutte le operazioni al suo interno.

### Passaggio 3: aggiungi una forma automatica

Per impostare un clic su un collegamento ipertestuale macro, avrai bisogno di un oggetto su cui l'utente può fare clic. In questo esempio utilizzeremo una forma come elemento selezionabile.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Qui creiamo una forma automatica con il tipo "BlankButton" a coordinate specifiche (20, 20) e con dimensioni di 80x30. Puoi personalizzare questi valori per adattarli al layout della tua presentazione.

### Passaggio 4: impostare il clic sul collegamento ipertestuale macro

Ora arriva la parte in cui imposti il clic del collegamento ipertestuale della macro. Dovrai fornire un nome macro come parametro.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In questo esempio, abbiamo impostato il clic sul collegamento ipertestuale della macro su "TestMacro". Quando l'utente fa clic sulla forma, verrà attivata questa macro.

### Passaggio 5: recuperare le informazioni

Puoi anche recuperare informazioni sul collegamento ipertestuale che hai impostato.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Queste righe di codice consentono di stampare l'URL esterno e il tipo di azione del collegamento ipertestuale.

E questo è tutto! Hai impostato correttamente un clic sul collegamento ipertestuale macro nella presentazione utilizzando Aspose.Slides per .NET.

## Conclusione

In questo tutorial, abbiamo imparato come impostare un clic sul collegamento ipertestuale macro nella presentazione utilizzando Aspose.Slides per .NET. Questa può essere una funzionalità preziosa per creare presentazioni interattive e dinamiche che coinvolgano il tuo pubblico. Con Aspose.Slides per .NET, hai un potente strumento a tua disposizione per portare lo sviluppo della tua presentazione al livello successivo.

 Ora è il momento di sperimentare e creare presentazioni accattivanti con collegamenti ipertestuali macro personalizzati. Sentiti libero di esplorare il[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/) per informazioni e possibilità più approfondite.

## FAQ (domande frequenti)

### Posso utilizzare Aspose.Slides per .NET con altri linguaggi di programmazione?
Aspose.Slides è progettato principalmente per .NET, ma Aspose offre librerie simili per altri linguaggi di programmazione, come Java.

### Aspose.Slides per .NET è una libreria gratuita?
Aspose.Slides per .NET è una libreria commerciale con una versione di prova gratuita disponibile. Puoi scaricarlo da[Qui](https://releases.aspose.com/).

### Esistono limitazioni all'utilizzo delle macro nelle presentazioni create con Aspose.Slides per .NET?
Aspose.Slides per .NET ti consente di lavorare con le macro, ma dovresti essere consapevole delle considerazioni sulla sicurezza e sulla compatibilità quando usi le macro nelle presentazioni.

### È possibile personalizzare l'aspetto della forma utilizzata per il collegamento ipertestuale?
Sì, puoi personalizzare l'aspetto della forma modificandone le proprietà, ad esempio dimensione, colore e carattere.

### Dove posso ottenere aiuto o supporto per Aspose.Slides per .NET?
 Se riscontri problemi o hai domande, puoi cercare aiuto nel forum di supporto Aspose[Qui](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
