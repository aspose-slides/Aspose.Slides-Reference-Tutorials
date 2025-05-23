---
"date": "2025-04-15"
"description": "Scopri come creare e personalizzare grafici utilizzando Aspose.Slides per .NET, inclusa la visualizzazione delle percentuali come etichette dati. Segui questa guida passo passo."
"title": "Come creare e personalizzare grafici con Aspose.Slides .NET - Visualizzare le percentuali come etichette"
"url": "/it/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e personalizzare grafici con Aspose.Slides .NET: visualizzare le percentuali come etichette

## Introduzione

Presentare i dati in modo efficace è fondamentale in molti campi e i grafici svolgono un ruolo fondamentale trasformando informazioni complesse in immagini chiare. Creare il grafico perfetto implica attività di personalizzazione come la visualizzazione delle percentuali sulle etichette, un'attività semplificata da Aspose.Slides per .NET. Questa libreria semplifica il processo di creazione e modifica dei grafici nelle presentazioni di PowerPoint.

In questo tutorial imparerai come utilizzare Aspose.Slides per .NET per creare da zero un grafico a colonne impilate e personalizzarlo visualizzando i valori percentuali come etichette dati. Seguendo questi passaggi, migliorerai le tue diapositive con rappresentazioni dei dati precise e visivamente accattivanti.

**Cosa imparerai:**
- Inizializzazione di Aspose.Slides per .NET
- Creazione di un grafico a colonne impilate
- Calcolo e visualizzazione delle percentuali sulle etichette dati
- Ottimizzazione delle migliori pratiche per le prestazioni dei grafici

Prima di passare all'implementazione, assicuriamoci che tutto sia pronto per iniziare.

## Prerequisiti

Per seguire questo tutorial in modo efficace, assicurati di avere:
- **.NET Core SDK** installato sul tuo computer.
- Conoscenza di base dello sviluppo di applicazioni C# e .NET.
- Visual Studio o un IDE simile per scrivere ed eseguire codice C#.

Per creare grafici è necessario Aspose.Slides per .NET, quindi accertarsi che sia configurato come descritto di seguito.

## Impostazione di Aspose.Slides per .NET

Aspose.Slides per .NET è una potente libreria che permette di lavorare con le presentazioni di PowerPoint a livello di codice. Ecco come aggiungerla al tuo progetto:

### Installazione

**Interfaccia della riga di comando .NET:**
```bash
dotnet add package Aspose.Slides
```

**Console del gestore pacchetti:**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet:** 
- Apri NuGet Package Manager e cerca "Aspose.Slides". Installa la versione più recente.

### Acquisizione della licenza

Per sfruttare appieno Aspose.Slides, inizia con una prova gratuita. Per un utilizzo prolungato, valuta l'acquisto di una licenza temporanea o di una da [Posare](https://purchase.aspose.com/buy)Segui le loro linee guida per impostare la tua licenza nell'ambiente del tuo progetto.

### Inizializzazione di base

Una volta installato, inizializzare il `Presentation` classe per iniziare a creare diapositive:
```csharp
using Aspose.Slides;

// Inizializza l'istanza della classe Presentazione
tPresentation presentation = new Presentation();
```

Passiamo ora all'implementazione della nostra funzionalità di creazione e personalizzazione dei grafici utilizzando Aspose.Slides per .NET.

## Guida all'implementazione

### Creare un grafico a colonne impilate

Il nostro obiettivo è creare un grafico a colonne impilate e personalizzarlo mostrando le percentuali come etichette dati. Ecco come:

#### Inizializza la presentazione

Inizia creando un'istanza di `Presentation`:
```csharp
using Aspose.Slides;

// Inizializza l'istanza della classe Presentazione
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Aggiungere un grafico alla diapositiva

Aggiungi un grafico a colonne impilate alla prima diapositiva con le coordinate e le dimensioni specificate:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Questa linea crea un `StackedColumn` grafico in posizione (20, 20) con larghezza e altezza di 400.

#### Calcola i valori totali per il calcolo percentuale

Per visualizzare le percentuali, calcola il valore totale per ciascuna categoria in tutte le serie:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Sommare i valori di tutte le serie per ogni categoria
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Personalizza le etichette dati per mostrare i valori percentuali

Successivamente, scorrere ogni serie e personalizzare le etichette dei dati:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Calcola la percentuale
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Testo chiaro per evitare sovrapposizioni
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Configura il formato dell'etichetta per nascondere le etichette dati predefinite
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Questa sezione calcola la percentuale per ciascun punto dati e la imposta come etichetta personalizzata, garantendo che non vi siano sovrapposizioni con le etichette predefinite.

#### Salva la presentazione

Infine, salva la presentazione per visualizzare il risultato:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Applicazioni pratiche

Visualizzare le percentuali nei grafici può essere particolarmente utile in scenari come:
1. **Rendicontazione finanziaria:** Mostra le distribuzioni del portafoglio o i rendimenti degli investimenti come percentuali.
2. **Analisi delle vendite:** Rappresenta i dati sulla quota di mercato in percentuale per evidenziare le prestazioni nelle varie regioni.
3. **Risultati del sondaggio:** Visualizza le risposte al sondaggio come percentuali per un migliore confronto visivo.
4. **Gestione del progetto:** Utilizzare grafici a torta con percentuali per illustrare l'allocazione delle risorse.
5. **Istruzione:** Spiega i concetti statistici utilizzando elementi visivi chiari basati sulle percentuali.

L'integrazione di questi grafici personalizzati in sistemi come CRM o ERP può migliorare dashboard e report, agevolando i processi decisionali.

## Considerazioni sulle prestazioni

Quando si lavora con Aspose.Slides per .NET, in particolare con set di dati di grandi dimensioni:
- **Gestione della memoria:** Eliminare correttamente gli oggetti di presentazione per liberare memoria. Utilizzare `using` dichiarazioni ove applicabile.
- **Gestione efficiente dei dati:** Quando possibile, eseguire calcoli al di fuori dei loop per ridurre il sovraccarico computazionale.
- **Bilanciamento del carico:** Per le applicazioni Web, assicurarsi che le risorse del server siano adeguatamente predisposte per le richieste di generazione simultanea di grafici.

## Conclusione

Questo tutorial ha illustrato come creare e personalizzare grafici utilizzando Aspose.Slides per .NET, visualizzando i valori percentuali come etichette. Padroneggiare queste tecniche consente di migliorare le presentazioni con rappresentazioni dei dati dettagliate e visivamente accattivanti.

Come passo successivo, esplora altri tipi di grafici e opzioni di personalizzazione disponibili in Aspose.Slides. Sperimenta con diversi set di dati per trasformarli in elementi visivi efficaci che comunichino informazioni in modo chiaro.

## Sezione FAQ

**D1: Come posso gestire grandi set di dati quando creo grafici con Aspose.Slides per .NET?**
A1: Per set di dati di grandi dimensioni, ottimizzare i calcoli e utilizzare tecniche di gestione della memoria efficienti. Suddividere le attività di elaborazione per evitare il sovraccarico di memoria.

**D2: Posso utilizzare Aspose.Slides per .NET in un'applicazione web?**
R2: Sì, può essere integrato nelle applicazioni ASP.NET. Assicurare la corretta allocazione delle risorse del server per prestazioni ottimali.

**D3: È possibile esportare i grafici creati con Aspose.Slides in altri formati?**
A3: Assolutamente! Puoi esportare le presentazioni contenenti i tuoi grafici personalizzati in vari formati, come PDF e file immagine, utilizzando le funzionalità della libreria.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}