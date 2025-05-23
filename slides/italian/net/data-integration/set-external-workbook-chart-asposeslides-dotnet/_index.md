---
"date": "2025-04-15"
"description": "Scopri come migliorare le tue presentazioni collegando dati Excel esterni con Aspose.Slides per .NET. Questa guida ti guiderà nella configurazione, impostazione e implementazione di grafici dinamici."
"title": "Come impostare una cartella di lavoro esterna per un grafico in Aspose.Slides .NET&#58; una guida passo passo"
"url": "/it/net/data-integration/set-external-workbook-chart-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare una cartella di lavoro esterna per un grafico in Aspose.Slides .NET: una guida passo passo

## Introduzione

Incorporare dati direttamente da fonti esterne nelle presentazioni può aumentarne notevolmente il valore. Con Aspose.Slides per .NET, è possibile impostare senza problemi una cartella di lavoro esterna per i grafici all'interno delle diapositive, consentendo visualizzazioni dinamiche e aggiornate. Questo tutorial vi guiderà attraverso il processo di collegamento di un file Excel in rete a un grafico nella vostra presentazione.

**Cosa imparerai:**
- Configurazione di un ambiente Aspose.Slides .NET.
- Impostazione di una cartella di lavoro esterna da una posizione di rete per i grafici.
- Implementazione di un gestore personalizzato per il caricamento delle risorse in C#.
- Applicazioni pratiche dell'integrazione di fonti dati esterne con le presentazioni.

Cominciamo!

## Prerequisiti

Prima di iniziare a programmare, assicurati di soddisfare i seguenti requisiti:

- **Librerie e dipendenze richieste**: Installa Aspose.Slides per .NET nel tuo progetto.
- **Requisiti di configurazione dell'ambiente**: Impostare un ambiente di sviluppo C# (ad esempio, Visual Studio).
- **Prerequisiti di conoscenza**: Avere una conoscenza di base della programmazione C# e familiarità con Aspose.Slides.

## Impostazione di Aspose.Slides per .NET

Inizia installando la libreria Aspose.Slides nel tuo progetto. Puoi usare uno qualsiasi di questi metodi:

**Interfaccia a riga di comando .NET**
```bash
dotnet add package Aspose.Slides
```

**Console del gestore dei pacchetti**
```bash
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet**: Cerca "Aspose.Slides" e installa la versione più recente.

### Acquisizione della licenza

Per utilizzare Aspose.Slides, inizia con una prova gratuita o richiedi una licenza temporanea. Per un utilizzo a lungo termine, valuta l'acquisto di una licenza completa dal sito ufficiale.

### Inizializzazione di base

Ecco come inizializzare Aspose.Slides nella tua applicazione:
```csharp
using Aspose.Slides;

// Inizializza l'oggetto Presentazione
Presentation pres = new Presentation();
```

## Guida all'implementazione

Analizziamo l'implementazione nelle sue caratteristiche principali.

### Impostazione della cartella di lavoro esterna dalla rete

Questa funzionalità consente di collegare un file Excel basato sulla rete come cartella di lavoro esterna per un grafico nella presentazione.

#### Passaggio 1: specificare il percorso della cartella di lavoro esterna
Specificare il percorso della cartella di lavoro esterna che si trova su un'unità di rete:
```csharp
string externalWbPath = "http://LA_TUA_DIRECTORY_DOCUMENTI/stili/2.xlsx";
```
Sostituire `YOUR_DOCUMENT_DIRECTORY` con la directory effettiva in cui è ospitato il file Excel.

#### Passaggio 2: configurare le opzioni di caricamento
Imposta le opzioni di caricamento e specifica un callback personalizzato per il caricamento delle risorse:
```csharp
LoadOptions opts = new LoadOptions();
opts.ResourceLoadingCallback = new WorkbookLoadingHandler();
```

#### Passaggio 3: creare la presentazione e aggiungere il grafico
Crea un'istanza di presentazione e aggiungi un grafico alla prima diapositiva:
```csharp
using (Presentation pres = new Presentation(opts))
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
    IChartData chartData = chart.ChartData;
    
    // Imposta il percorso della cartella di lavoro esterna per i dati del grafico
    (chartData as ChartData).SetExternalWorkbook(externalWbPath);
}
```

### Gestore di caricamento della cartella di lavoro

Questa funzionalità comporta la creazione di un gestore di caricamento delle risorse personalizzato per recuperare il file Excel dal percorso di rete specificato.

#### Passaggio 1: implementare il callback di caricamento delle risorse
Crea una classe che implementa `IResourceLoadingCallback`:
```csharp
class WorkbookLoadingHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(IResourceLoadingArgs args)
    {
        string workbookPath = args.OriginalUri;
        
        // Controlla se il percorso è una posizione di rete (non un percorso di file locale)
        if (workbookPath.IndexOf(':') > 1 && !workbookPath.StartsWith("file:///"))
        {
            try
            {
                WebRequest request = WebRequest.Create(workbookPath);
                request.Credentials = new NetworkCredential("testuser", "testuser");
                
                using (WebResponse response = request.GetResponse())
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Fornire i dati recuperati ad Aspose.Slides
                    return ResourceLoadingAction.UserProvided;
                }
            }
            catch (Exception ex)
            {
                throw new InvalidOperationException(ex.ToString());
            }
        }
        else
        {
            return ResourceLoadingAction.Default;
        }
    }
}
```

## Applicazioni pratiche

Ecco alcuni casi d'uso concreti per l'integrazione di fonti dati esterne nelle presentazioni Aspose.Slides:
1. **Reporting dinamico**: Aggiorna automaticamente i grafici nei report finanziari o sulle prestazioni in base ai dati di rete più recenti.
2. **Dashboard aziendali**: Crea dashboard interattive che estraggono dati in tempo reale da database aziendali o server remoti.
3. **Contenuto educativo**: Sviluppare materiali didattici con dati statistici aggiornati per materie come economia o demografia.

## Considerazioni sulle prestazioni

Quando si lavora con cartelle di lavoro esterne, tenere presente questi suggerimenti sulle prestazioni:
- **Ottimizza le richieste di rete**: Ridurre al minimo la frequenza delle richieste di rete per diminuire la latenza e l'utilizzo della larghezza di banda.
- **Gestione delle risorse**Garantire un utilizzo efficiente della memoria rilasciando tempestivamente i flussi non appena non sono più necessari.
- **Gestione degli errori**: Implementare una gestione solida degli errori per i problemi di rete per garantire il corretto funzionamento dell'applicazione.

## Conclusione

A questo punto, dovresti avere una solida conoscenza di come impostare una cartella di lavoro esterna da una posizione di rete utilizzando Aspose.Slides per .NET. Questa funzionalità può migliorare significativamente l'interattività e la pertinenza dei dati della tua presentazione. Per ulteriori approfondimenti, valuta l'integrazione di altre librerie Aspose o esplora altri tipi di grafici supportati da Aspose.Slides. Prova a implementare questa soluzione in uno dei tuoi progetti per constatarne i vantaggi in prima persona!

## Sezione FAQ

**1. Che cos'è Aspose.Slides per .NET?**
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire le presentazioni di PowerPoint a livello di programmazione.

**2. Posso usare Aspose.Slides con altri linguaggi di programmazione?**
Sì, Aspose fornisce librerie simili per Java, C++, Python e altro ancora.

**3. Come gestisco gli errori di rete quando carico una cartella di lavoro esterna?**
Implementa una gestione robusta delle eccezioni all'interno del tuo `WorkbookLoadingHandler` per gestire con eleganza eventuali problemi di rete.

**4. È possibile utilizzare file locali anziché percorsi di rete?**
Sì, puoi modificare il percorso in `externalWbPath` per puntare a un file locale, se necessario.

**5. Posso aggiornare automaticamente i grafici con nuovi dati?**
Sì, recuperando e impostando periodicamente la cartella di lavoro esterna, i grafici rifletteranno tutti gli aggiornamenti apportati ai dati di origine.

## Risorse
- **Documentazione**: [Documentazione di Aspose.Slides .NET](https://reference.aspose.com/slides/net/)
- **Scaricamento**: [Versioni di Aspose.Slides per .NET](https://releases.aspose.com/slides/net/)
- **Acquistare**: [Acquista Aspose.Slides](https://purchase.aspose.com/buy)
- **Prova gratuita**: [Prova gratuita di Aspose.Slides](https://releases.aspose.com/slides/net/)
- **Licenza temporanea**: [Ottieni una licenza temporanea per Aspose.Slides](https://purchase.aspose.com/temporary-license/)
- **Supporto**: [Forum di supporto Aspose](https://forum.aspose.com/c/slides/11)

Con queste risorse, sarai pronto a sfruttare appieno il potenziale di Aspose.Slides nei tuoi progetti .NET. Buona programmazione!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}