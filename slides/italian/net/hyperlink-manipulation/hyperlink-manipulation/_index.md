---
"description": "Scopri come aggiungere e rimuovere collegamenti ipertestuali in Aspose.Slides per .NET. Arricchisci facilmente le tue presentazioni con link interattivi."
"linktitle": "Manipolazione dei collegamenti ipertestuali in Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Manipolazione dei collegamenti ipertestuali in Aspose.Slides"
"url": "/it/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipolazione dei collegamenti ipertestuali in Aspose.Slides


I collegamenti ipertestuali sono elementi essenziali nelle presentazioni, poiché consentono di navigare comodamente tra le diapositive o di accedere a risorse esterne. Aspose.Slides per .NET offre potenti funzionalità per aggiungere e rimuovere collegamenti ipertestuali nelle diapositive della presentazione. In questo tutorial, vi guideremo attraverso il processo di manipolazione dei collegamenti ipertestuali utilizzando Aspose.Slides per .NET. Vedremo come aggiungere e rimuovere collegamenti ipertestuali da una diapositiva. Cominciamo subito!

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Aspose.Slides per .NET: è necessario che la libreria Aspose.Slides per .NET sia installata e configurata. È possibile trovare la documentazione. [Qui](https://reference.aspose.com/slides/net/) e scaricalo da [questo collegamento](https://releases.aspose.com/slides/net/).

2. Directory dei documenti: hai bisogno di una directory in cui archiviare i file della presentazione. Assicurati di specificare il percorso di questa directory nel codice.

3. Conoscenza di base di C#: questo tutorial presuppone una conoscenza di base della programmazione C#.

Ora che hai soddisfatto i prerequisiti, passiamo alla guida dettagliata per la manipolazione dei collegamenti ipertestuali utilizzando Aspose.Slides per .NET.

## Aggiungere collegamenti ipertestuali a una diapositiva

### Passaggio 1: inizializzare la presentazione

Per iniziare, è necessario inizializzare una presentazione utilizzando Aspose.Slides. Puoi farlo con il seguente codice:

```csharp
using (Presentation presentation = new Presentation())
{
    // Il tuo codice qui
}
```

### Passaggio 2: aggiungere la cornice di testo

Ora aggiungiamo una cornice di testo a una diapositiva. Questo codice crea una forma rettangolare con testo:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Passaggio 3: aggiungere collegamento ipertestuale

Successivamente, aggiungerai un collegamento ipertestuale al testo nella forma che hai creato. Ecco come fare:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Passaggio 4: Salva la presentazione

Infine, salva la presentazione con il collegamento ipertestuale aggiunto:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai aggiunto correttamente un collegamento ipertestuale a una diapositiva utilizzando Aspose.Slides per .NET.

## Rimozione di collegamenti ipertestuali da una diapositiva

### Passaggio 1: inizializzare la presentazione

Per rimuovere i collegamenti ipertestuali da una diapositiva, è necessario aprire una presentazione esistente:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Passaggio 2: rimuovere i collegamenti ipertestuali

Ora rimuovi tutti i collegamenti ipertestuali dalla presentazione utilizzando il seguente codice:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Passaggio 3: Salva la presentazione

Dopo aver rimosso i collegamenti ipertestuali, salvare la presentazione:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai rimosso con successo i collegamenti ipertestuali da una diapositiva utilizzando Aspose.Slides per .NET.

In conclusione, Aspose.Slides per .NET offre un modo efficiente per gestire i collegamenti ipertestuali nelle presentazioni, consentendo di creare diapositive interattive e coinvolgenti. Che si desideri aggiungere o rimuovere collegamenti ipertestuali a risorse esterne, Aspose.Slides semplifica il processo e migliora le capacità di creazione delle presentazioni.

Grazie per aver partecipato a questo tutorial sulla manipolazione dei collegamenti ipertestuali in Aspose.Slides per .NET. Per qualsiasi domanda o ulteriore assistenza, non esitate a consultare [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/net/) o contatta la community Aspose su [forum di supporto](https://forum.aspose.com/).

---

## Conclusione

In questo tutorial abbiamo imparato a gestire i collegamenti ipertestuali nelle presentazioni utilizzando Aspose.Slides per .NET. Abbiamo trattato sia l'aggiunta che la rimozione dei collegamenti ipertestuali, consentendo di creare presentazioni dinamiche e interattive. Aspose.Slides semplifica il processo, facilitando l'aggiunta di collegamenti ipertestuali a risorse esterne nelle diapositive.

Hai altre domande sull'utilizzo di Aspose.Slides o su altri aspetti della progettazione di presentazioni? Consulta le FAQ qui sotto per ulteriori approfondimenti.

## FAQ (Domande frequenti)

### Quali sono i principali vantaggi dell'utilizzo di Aspose.Slides per .NET?
Aspose.Slides per .NET offre un'ampia gamma di funzionalità per creare, modificare e convertire presentazioni. Offre un set completo di strumenti per aggiungere contenuti, animazioni e interazioni alle diapositive.

### Posso aggiungere collegamenti ipertestuali ad oggetti diversi dal testo in Aspose.Slides?
Sì, Aspose.Slides consente di aggiungere collegamenti ipertestuali a vari oggetti, tra cui forme, immagini e testo, offrendoti flessibilità nella creazione di presentazioni interattive.

### Aspose.Slides è compatibile con diversi formati di file PowerPoint?
Assolutamente sì. Aspose.Slides supporta vari formati PowerPoint, tra cui PPT, PPTX, PPS e altri. Garantisce la compatibilità con diverse versioni di Microsoft PowerPoint.

### Dove posso trovare risorse aggiuntive e supporto per Aspose.Slides?
Per una documentazione approfondita e il supporto della comunità, visita il [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/net/) e il [Forum di supporto di Aspose](https://forum.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Slides?
Se hai bisogno di una licenza temporanea per Aspose.Slides, puoi ottenerne una [Qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}