---
title: Conservazione dei caratteri originali converti la presentazione in HTML
linktitle: Conservazione dei caratteri originali converti la presentazione in HTML
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come preservare i caratteri originali durante la conversione delle presentazioni in HTML utilizzando Aspose.Slides per .NET. Garantisci la coerenza dei caratteri e l'impatto visivo senza sforzo.
type: docs
weight: 14
url: /it/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

In questa guida completa, ti guideremo attraverso il processo di conservazione dei caratteri originali durante la conversione di una presentazione in HTML utilizzando Aspose.Slides per .NET. Ti forniremo il codice sorgente C# necessario e spiegheremo ogni passaggio in dettaglio. Alla fine di questo tutorial sarai in grado di assicurarti che i caratteri nel tuo documento HTML convertito rimangano fedeli alla presentazione originale.

## 1. Introduzione

Quando si convertono le presentazioni PowerPoint in HTML, è fondamentale mantenere i caratteri originali per garantire la coerenza visiva dei contenuti. Aspose.Slides per .NET fornisce una potente soluzione per raggiungere questo obiettivo. In questo tutorial ti guideremo attraverso i passaggi necessari per preservare i caratteri originali durante il processo di conversione.

## 2. Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio installato sul tuo computer.
- Libreria Aspose.Slides per .NET aggiunta al tuo progetto.

## 3. Impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi la libreria Aspose.Slides per .NET come riferimento.

## 4. Caricamento della presentazione

Utilizza il codice seguente per caricare la presentazione di PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Il tuo codice qui
}
```

 Sostituire`"Your Document Directory"` con il percorso del file di presentazione.

## 5. Esclusione dei caratteri predefiniti

Per escludere caratteri predefiniti come Calibri e Arial, utilizzare il seguente codice:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

È possibile personalizzare questo elenco secondo necessità.

## 6. Incorporamento di tutti i caratteri

Successivamente, incorporeremo tutti i caratteri nel documento HTML. Ciò garantisce che i caratteri originali vengano preservati. Utilizza il seguente codice:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Salvataggio in formato HTML

Ora salva la presentazione come documento HTML con caratteri incorporati:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Sostituire`"output.html"` con il nome del file di output desiderato.

## 8. Conclusione

In questo tutorial, abbiamo dimostrato come preservare i caratteri originali durante la conversione di una presentazione PowerPoint in HTML utilizzando Aspose.Slides per .NET. Seguendo questi passaggi puoi assicurarti che il tuo documento HTML convertito mantenga l'integrità visiva della presentazione originale.

## 9. Domande frequenti

### Q1: Posso personalizzare l'elenco dei caratteri esclusi?

 Si, puoi. Modifica il`fontNameExcludeList` array per includere o escludere caratteri specifici in base alle proprie esigenze.

### Q2: Cosa succede se non voglio incorporare tutti i caratteri?

Se desideri incorporare solo caratteri specifici, puoi modificare il codice di conseguenza. Consultare la documentazione Aspose.Slides per .NET per ulteriori dettagli.

### Q3: Esistono requisiti di licenza per l'utilizzo di Aspose.Slides per .NET?

Sì, potresti aver bisogno di una licenza valida per utilizzare Aspose.Slides per .NET nei tuoi progetti. Fare riferimento al sito Web Aspose per informazioni sulla licenza.

### Q4: Posso convertire altri formati di file in HTML utilizzando Aspose.Slides per .NET?

Aspose.Slides per .NET si concentra principalmente sulle presentazioni PowerPoint. Per convertire altri formati di file in HTML, potrebbe essere necessario esplorare altri prodotti Aspose su misura per tali formati.

### Q5: Dove posso accedere a risorse e supporto aggiuntivi?

 È possibile trovare ulteriore documentazione, tutorial e supporto sul sito Web Aspose. Visita[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
