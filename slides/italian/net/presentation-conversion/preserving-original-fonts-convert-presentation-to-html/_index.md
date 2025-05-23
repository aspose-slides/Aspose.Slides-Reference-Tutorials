---
"description": "Scopri come preservare i font originali durante la conversione delle presentazioni in HTML utilizzando Aspose.Slides per .NET. Garantisci coerenza dei font e impatto visivo senza sforzo."
"linktitle": "Conservazione dei caratteri originali - Convertire la presentazione in HTML"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Conservazione dei caratteri originali - Convertire la presentazione in HTML"
"url": "/it/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conservazione dei caratteri originali - Convertire la presentazione in HTML


In questa guida completa, ti guideremo attraverso il processo di conservazione dei font originali durante la conversione di una presentazione in HTML utilizzando Aspose.Slides per .NET. Ti forniremo il codice sorgente C# necessario e spiegheremo ogni passaggio in dettaglio. Al termine di questo tutorial, sarai in grado di garantire che i font nel tuo documento HTML convertito rimangano fedeli alla presentazione originale.

## 1. Introduzione

Quando si convertono presentazioni PowerPoint in HTML, è fondamentale mantenere i font originali per garantire la coerenza visiva dei contenuti. Aspose.Slides per .NET offre una soluzione potente per raggiungere questo obiettivo. In questo tutorial, vi guideremo attraverso i passaggi necessari per preservare i font originali durante il processo di conversione.

## 2. Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Visual Studio installato sul computer.
- Libreria Aspose.Slides per .NET aggiunta al progetto.

## 3. Impostazione del progetto

Per iniziare, crea un nuovo progetto in Visual Studio e aggiungi la libreria Aspose.Slides per .NET come riferimento.

## 4. Caricamento della presentazione

Utilizza il seguente codice per caricare la tua presentazione PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Il tuo codice qui
}
```

Sostituire `"Your Document Directory"` con il percorso al file della presentazione.

## 5. Esclusione dei font predefiniti

Per escludere i font predefiniti come Calibri e Arial, utilizzare il seguente codice:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Puoi personalizzare questo elenco in base alle tue esigenze.

## 6. Incorporamento di tutti i font

Successivamente, incorporeremo tutti i font nel documento HTML. Questo garantirà che i font originali vengano preservati. Utilizza il seguente codice:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Salvataggio in formato HTML

Ora salva la presentazione come documento HTML con i font incorporati:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Sostituire `"output.html"` con il nome del file di output desiderato.

## 8. Conclusion

In questo tutorial, abbiamo mostrato come preservare i font originali durante la conversione di una presentazione PowerPoint in HTML utilizzando Aspose.Slides per .NET. Seguendo questi passaggi, è possibile garantire che il documento HTML convertito mantenga l'integrità visiva della presentazione originale.

## 9. Domande frequenti

### D1: Posso personalizzare l'elenco dei font esclusi?

Sì, puoi. Modifica il `fontNameExcludeList` array per includere o escludere specifici font in base alle tue esigenze.

### D2: Cosa succede se non voglio incorporare tutti i font?

Se si desidera incorporare solo font specifici, è possibile modificare il codice di conseguenza. Consultare la documentazione di Aspose.Slides per .NET per maggiori dettagli.

### D3: Esistono requisiti di licenza per utilizzare Aspose.Slides per .NET?

Sì, potrebbe essere necessaria una licenza valida per utilizzare Aspose.Slides per .NET nei tuoi progetti. Consulta il sito web di Aspose per informazioni sulle licenze.

### D4: Posso convertire altri formati di file in HTML utilizzando Aspose.Slides per .NET?

Aspose.Slides per .NET si concentra principalmente sulle presentazioni PowerPoint. Per convertire altri formati di file in HTML, potrebbe essere necessario esplorare altri prodotti Aspose specifici per tali formati.

### D5: Dove posso trovare ulteriori risorse e supporto?

Puoi trovare ulteriore documentazione, tutorial e supporto sul sito web di Aspose. Visita [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/) per informazioni dettagliate.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}