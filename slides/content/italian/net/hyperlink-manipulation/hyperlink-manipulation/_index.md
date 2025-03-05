---
title: Manipolazione dei collegamenti ipertestuali in Aspose.Slides
linktitle: Manipolazione dei collegamenti ipertestuali in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere e rimuovere collegamenti ipertestuali in Aspose.Slides per .NET. Migliora facilmente le tue presentazioni con collegamenti interattivi.
type: docs
weight: 10
url: /it/net/hyperlink-manipulation/hyperlink-manipulation/
---

collegamenti ipertestuali sono elementi essenziali nelle presentazioni poiché forniscono un modo conveniente per navigare tra le diapositive o accedere a risorse esterne. Aspose.Slides per .NET offre potenti funzionalità per aggiungere e rimuovere collegamenti ipertestuali nelle diapositive della presentazione. In questo tutorial, ti guideremo attraverso il processo di manipolazione dei collegamenti ipertestuali utilizzando Aspose.Slides per .NET. Tratteremo l'aggiunta di collegamenti ipertestuali a una diapositiva e la rimozione di collegamenti ipertestuali da una diapositiva. Quindi tuffiamoci!

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Slides per .NET: è necessario avere la libreria Aspose.Slides per .NET installata e configurata. Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/net/) e scaricarlo da[questo link](https://releases.aspose.com/slides/net/).

2. La tua directory dei documenti: hai bisogno di una directory in cui memorizzerai i file di presentazione. Assicurati di specificare il percorso di questa directory nel codice.

3. Conoscenza di base di C#: questo tutorial presuppone che tu abbia una conoscenza di base della programmazione C#.

Ora che hai i prerequisiti, passiamo alla guida passo passo per la manipolazione dei collegamenti ipertestuali utilizzando Aspose.Slides per .NET.

## Aggiunta di collegamenti ipertestuali a una diapositiva

### Passaggio 1: inizializza la presentazione

Per iniziare, è necessario inizializzare una presentazione utilizzando Aspose.Slides. Puoi farlo con il seguente codice:

```csharp
using (Presentation presentation = new Presentation())
{
    // Il tuo codice qui
}
```

### Passaggio 2: aggiungi cornice di testo

Ora aggiungiamo una cornice di testo a una diapositiva. Questo codice crea una forma rettangolare con testo:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Passaggio 3: aggiungi il collegamento ipertestuale

Successivamente, aggiungerai un collegamento ipertestuale al testo nella forma che hai creato. Ecco come puoi farlo:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Passaggio 4: salva la presentazione

Infine, salva la presentazione con il collegamento ipertestuale aggiunto:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai aggiunto con successo un collegamento ipertestuale a una diapositiva utilizzando Aspose.Slides per .NET.

## Rimozione di collegamenti ipertestuali da una diapositiva

### Passaggio 1: inizializza la presentazione

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

### Passaggio 3: salva la presentazione

Dopo aver rimosso i collegamenti ipertestuali, salva la presentazione:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

E questo è tutto! Hai rimosso con successo i collegamenti ipertestuali da una diapositiva utilizzando Aspose.Slides per .NET.

In conclusione, Aspose.Slides per .NET fornisce un modo efficace per manipolare i collegamenti ipertestuali nelle presentazioni, consentendoti di creare diapositive interattive e coinvolgenti. Sia che tu voglia aggiungere collegamenti ipertestuali a risorse esterne o rimuoverli, Aspose.Slides semplifica il processo e migliora le tue capacità di creazione di presentazioni.

 Grazie per esserti unito a noi in questo tutorial sulla manipolazione dei collegamenti ipertestuali in Aspose.Slides per .NET. Se hai domande o hai bisogno di ulteriore assistenza, non esitare a esplorare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/net/) o contatta la comunità Aspose su[Forum di assistenza](https://forum.aspose.com/).

---

## Conclusione

In questo tutorial, abbiamo imparato come manipolare i collegamenti ipertestuali nelle presentazioni utilizzando Aspose.Slides per .NET. Abbiamo trattato sia l'aggiunta che la rimozione dei collegamenti ipertestuali, consentendoti di creare presentazioni dinamiche e interattive. Aspose.Slides semplifica il processo, facilitando il miglioramento delle diapositive con collegamenti ipertestuali a risorse esterne.

Hai altre domande sul lavoro con Aspose.Slides o su altri aspetti della progettazione della presentazione? Consulta le domande frequenti qui sotto per ulteriori approfondimenti.

## FAQ (domande frequenti)

### Quali sono i principali vantaggi dell'utilizzo di Aspose.Slides per .NET?
Aspose.Slides per .NET offre un'ampia gamma di funzionalità per creare, manipolare e convertire presentazioni. Fornisce un set completo di strumenti per aggiungere contenuti, animazioni e interazioni alle diapositive.

### Posso aggiungere collegamenti ipertestuali a oggetti diversi dal testo in Aspose.Slides?
Sì, Aspose.Slides ti consente di aggiungere collegamenti ipertestuali a vari oggetti, tra cui forme, immagini e testo, offrendoti flessibilità nella creazione di presentazioni interattive.

### Aspose.Slides è compatibile con diversi formati di file PowerPoint?
Assolutamente. Aspose.Slides supporta vari formati PowerPoint, inclusi PPT, PPTX, PPS e altri. Garantisce la compatibilità con diverse versioni di Microsoft PowerPoint.

### Dove posso trovare risorse aggiuntive e supporto per Aspose.Slides?
 Per documentazione approfondita e supporto della community, visitare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/net/) e il[Aspose forum di supporto](https://forum.aspose.com/).

### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Se hai bisogno di una licenza temporanea per Aspose.Slides, puoi ottenerne una[Qui](https://purchase.aspose.com/temporary-license/).