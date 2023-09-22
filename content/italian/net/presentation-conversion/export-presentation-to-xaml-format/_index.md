---
title: Esporta la presentazione in formato XAML
linktitle: Esporta la presentazione in formato XAML
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come esportare presentazioni in formato XAML utilizzando Aspose.Slides per .NET. Crea contenuti interattivi senza sforzo!
type: docs
weight: 27
url: /it/net/presentation-conversion/export-presentation-to-xaml-format/
---

Nel mondo dello sviluppo software è essenziale disporre di strumenti in grado di semplificare attività complesse. Aspose.Slides per .NET è uno di questi strumenti che ti consente di lavorare con le presentazioni di PowerPoint a livello di codice. In questo tutorial passo passo, esploreremo come esportare una presentazione in formato XAML utilizzando Aspose.Slides per .NET. 

## Introduzione ad Aspose.Slides per .NET

Prima di immergerci nel tutorial, presentiamo brevemente Aspose.Slides per .NET. È una potente libreria che consente agli sviluppatori di creare, modificare, convertire e gestire presentazioni PowerPoint senza richiedere Microsoft PowerPoint stesso. Con Aspose.Slides per .NET, puoi automatizzare varie attività relative alle presentazioni PowerPoint, rendendo il processo di sviluppo più efficiente.

## Prerequisiti

Per seguire questo tutorial, avrai bisogno di quanto segue:

1. Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides per .NET installata e pronta per l'uso nel tuo progetto .NET.

2. Presentazione di origine: disponi di una presentazione PowerPoint (PPTX) che desideri esportare in formato XAML. Assicurati di conoscere il percorso di questa presentazione.

3. Directory di output: scegli una directory in cui desideri salvare i file XAML generati.

## Passaggio 1: imposta il tuo progetto

In questo primo passaggio imposteremo il nostro progetto e ci assicureremo di avere pronti tutti i componenti necessari. Assicurati di aver aggiunto un riferimento alla libreria Aspose.Slides per .NET nel tuo progetto.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Percorso alla presentazione dell'origine
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 Sostituire`"Your Document Directory"` con il percorso della directory contenente la presentazione PowerPoint di origine. Inoltre, specifica la directory di output in cui verranno salvati i file XAML generati.

## Passaggio 2: esporta la presentazione in XAML

Ora procediamo con l'esportazione della presentazione PowerPoint in formato XAML. Utilizzeremo Aspose.Slides per .NET per raggiungere questo obiettivo. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Crea opzioni di conversione
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Definisci il tuo servizio di risparmio di output
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Converti diapositive
    pres.Save(xamlOptions);

    // Salva i file XAML in una directory di output
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 In questo frammento di codice carichiamo la presentazione di origine, creiamo opzioni di conversione XAML e definiamo un servizio di salvataggio dell'output personalizzato utilizzando`NewXamlSaver`Salviamo quindi i file XAML nella directory di output specificata.

## Passaggio 3: classe di risparmio XAML personalizzata

 Per implementare il risparmiatore XAML personalizzato, creeremo una classe denominata`NewXamlSaver` che implementa il`IXamlOutputSaver` interfaccia.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Questa classe gestirà il salvataggio dei file XAML nella directory di output.

## Conclusione

Congratulazioni! Hai imparato con successo come esportare una presentazione di PowerPoint in formato XAML utilizzando Aspose.Slides per .NET. Questa può essere un'abilità preziosa quando si lavora su progetti che implicano la manipolazione di presentazioni.

Sentiti libero di esplorare ulteriori funzionalità e capacità di Aspose.Slides per .NET per migliorare le tue attività di automazione di PowerPoint.

## Domande frequenti

1. ### Cos'è Aspose.Slides per .NET?
Aspose.Slides per .NET è una libreria .NET per lavorare con presentazioni PowerPoint a livello di codice.

2. ### Dove posso trovare Aspose.Slides per .NET?
 È possibile scaricare Aspose.Slides per .NET da[Qui](https://purchase.aspose.com/buy).

3. ### È disponibile una prova gratuita?
 Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET[Qui](https://releases.aspose.com/).

4. ### Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

5. ### Dove posso ottenere supporto per Aspose.Slides per .NET?
Puoi trovare supporto e discussioni nella community[Qui](https://forum.aspose.com/).

 Per ulteriori tutorial e risorse, visitare il[Documentazione dell'API Aspose.Slides](https://reference.aspose.com/slides/net/).