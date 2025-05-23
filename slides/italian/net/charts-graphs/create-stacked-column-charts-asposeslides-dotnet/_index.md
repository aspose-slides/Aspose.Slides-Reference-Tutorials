---
"date": "2025-04-15"
"description": "Scopri come creare grafici a colonne impilate basati su percentuali visivamente accattivanti utilizzando Aspose.Slides per .NET. Segui questa guida passo passo per una visualizzazione chiara dei dati."
"title": "Come creare grafici a colonne impilate basati su percentuali in .NET utilizzando Aspose.Slides"
"url": "/it/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a colonne in pila basato sulla percentuale utilizzando Aspose.Slides per .NET

## Introduzione

Nell'ambito della visualizzazione dei dati, presentare le informazioni in modo chiaro ed efficace è fondamentale per un processo decisionale efficace. Per visualizzare in modo intuitivo set di dati complessi, i grafici a colonne impilate basati su percentuali sono ideali. Questa guida vi guiderà nella creazione di questi grafici utilizzando Aspose.Slides per .NET, una solida libreria progettata per la manipolazione di file di presentazione.

Seguendo questo tutorial imparerai:
- Impostazione dei dati del grafico e configurazione dei formati numerici.
- Aggiungere serie e personalizzarne l'aspetto.
- Formattazione delle etichette per migliorarne la leggibilità.

Pronti a tuffarvi? Iniziamo con i prerequisiti necessari!

## Prerequisiti

Prima di creare i grafici a colonne impilate basati su percentuali, assicurati che l'ambiente sia configurato correttamente. Avrai bisogno di:

### Librerie, versioni e dipendenze richieste
- **Aspose.Slides per .NET**: Assicurati che questa libreria sia installata.

### Requisiti di configurazione dell'ambiente
- Un ambiente di sviluppo con .NET SDK installato.
- Visual Studio o qualsiasi IDE compatibile per l'esecuzione del codice C#.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione C#.
- Familiarità con la configurazione di progetti .NET e la gestione dei pacchetti.

## Impostazione di Aspose.Slides per .NET

Per iniziare a creare grafici con Aspose.Slides, installa prima la libreria utilizzando uno di questi metodi:

**Interfaccia a riga di comando .NET**
```bash
dotnet add package Aspose.Slides
```

**Gestore dei pacchetti**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet**
- Cerca "Aspose.Slides" e installa la versione più recente.

### Fasi di acquisizione della licenza

Inizia con una prova gratuita scaricando una licenza temporanea da [Il sito web di Aspose](https://purchase.aspose.com/temporary-license/)Per un utilizzo continuato, si consiglia di acquistare una licenza completa. 

Una volta configurato, avvia Aspose.Slides nel tuo progetto:
```csharp
using Aspose.Slides;
```

## Guida all'implementazione

Con l'ambiente pronto, scomponiamo in passaggi la creazione di un grafico a colonne impilate basato su percentuali.

### Creazione e configurazione del grafico

#### Panoramica
Crea un'istanza di `Presentation` classe, essenziale per lavorare con le diapositive. Quindi, aggiungi e configura un grafico a colonne in pila sulla tua diapositiva.

#### Aggiunta di un grafico a colonne impilate
```csharp
// Crea un'istanza della classe Presentazione
document = new Presentation();

// Ottieni il riferimento alla prima diapositiva
slide = document.Slides[0];

// Aggiungi grafico PercentsStackedColumn alla posizione (20, 20) con dimensione (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Configurazione del formato numerico
Assicurati che i tuoi dati siano visualizzati in percentuale:
```csharp
// Configura il formato numerico per l'asse verticale
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Imposta il formato numerico in percentuale
```

#### Aggiunta di serie di dati e punti
Cancella i dati delle serie esistenti e aggiungine di nuovi:
```csharp
// Cancella tutti i dati di serie esistenti
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Cartella di lavoro dei dati del grafico di Access
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Aggiungi una nuova serie di dati "Rossi"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Imposta il colore di riempimento per la serie su Rosso
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Configurare le proprietà del formato dell'etichetta per la serie "Rossi"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Imposta il formato percentuale
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Aggiungi un'altra serie "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Imposta il colore di riempimento per la serie su Blu
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Imposta il formato percentuale
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Salvataggio della presentazione
Salva la presentazione in un file:
```csharp
// Salva la presentazione in formato PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Suggerimenti per la risoluzione dei problemi
- Assicurarsi che tutti gli spazi dei nomi siano importati correttamente.
- Controllare eventuali errori di battitura nei nomi delle proprietà e nelle chiamate ai metodi.
- Verifica che i percorsi per il salvataggio dei file esistano e che dispongano delle autorizzazioni corrette.

## Applicazioni pratiche

Ecco alcuni scenari in cui i grafici a colonne impilate basati su percentuali possono rivelarsi utili:
1. **Analisi delle vendite**: Visualizza le prestazioni del prodotto nelle diverse regioni in percentuale sulle vendite totali.
2. **Assegnazione del bilancio**: Mostra come i reparti allocano il loro budget in relazione alla spesa complessiva dell'azienda.
3. **Ricerca di mercato**: Confrontare le preferenze dei consumatori per varie categorie di prodotti nel tempo.
4. **Dati educativi**: Visualizza la distribuzione dei voti degli studenti nelle diverse materie.
5. **Statistiche sanitarie**: Rappresentano i dati demografici dei pazienti in diverse condizioni di salute.

## Considerazioni sulle prestazioni

Per prestazioni ottimali, considerare:
- Limitare il numero di punti dati a quanto necessario.
- Precaricamento dei dati per ridurre al minimo l'elaborazione in fase di esecuzione.
- Utilizzo di pratiche efficienti di gestione della memoria con Aspose.Slides per .NET.

## Conclusione

Congratulazioni! Hai imparato a creare un grafico a colonne in pila basato su percentuali utilizzando Aspose.Slides per .NET. Questo strumento migliora le presentazioni rendendo i dati complessi più comprensibili e visivamente accattivanti.

Prossimi passi? Esplora altri tipi di grafici disponibili in Aspose.Slides o integra questa funzionalità in applicazioni più grandi. Buona programmazione!

## Sezione FAQ

**D1: Posso utilizzare Aspose.Slides gratuitamente?**
R1: Sì, puoi iniziare con una prova gratuita per testare le funzionalità di Aspose.Slides.

**D2: Quali tipi di grafici sono supportati da Aspose.Slides per .NET?**
A2: Supporta vari tipi di grafici, come grafici a torta, a barre, a colonne, a linee e altro ancora.

**D3: Come posso iniziare a usare Aspose.Slides per .NET?**
A3: Installa la libreria utilizzando NuGet o .NET CLI come descritto sopra. Segui la nostra documentazione per creare il tuo primo grafico.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}