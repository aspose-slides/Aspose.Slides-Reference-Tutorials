---
"date": "2025-04-15"
"description": "Scopri come creare grafici a ciambella dinamici utilizzando Aspose.Slides per .NET. Segui questa guida per istruzioni dettagliate, incluse la configurazione e le funzionalità avanzate."
"title": "Guida passo passo&#58; creare un grafico a ciambella con Aspose.Slides .NET | Grafici e diagrammi"
"url": "/it/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Guida passo passo: creare un grafico a ciambella con Aspose.Slides .NET

## Introduzione

Immagina di dover presentare i risultati di un'analisi dati al tuo team o ai tuoi clienti e di aver bisogno di un modo coinvolgente per visualizzare le informazioni. Ecco che entra in gioco il grafico a ciambella: uno strumento versatile in grado di trasformare numeri grezzi in informazioni facilmente fruibili. Con Aspose.Slides per .NET, creare un grafico a ciambella personalizzato nelle diapositive della tua presentazione è semplice ed efficiente. Questa guida ti guiderà nell'utilizzo di Aspose.Slides per creare un grafico a ciambella visivamente accattivante, completo di configurazioni di serie personalizzate.

**Cosa imparerai:**
- Configurazione dell'ambiente di sviluppo con Aspose.Slides per .NET
- Creazione e personalizzazione di grafici a ciambella nelle presentazioni
- Implementazione di funzionalità avanzate come nomi di categoria e linee guida
- Ottimizzazione delle prestazioni per grandi set di dati

Analizziamo ora i prerequisiti necessari per iniziare.

## Prerequisiti

Prima di implementare questa funzionalità, assicurati che l'ambiente di sviluppo sia configurato correttamente. Questo tutorial presuppone una conoscenza di base della programmazione .NET e familiarità con Visual Studio o un IDE simile.

### Librerie e versioni richieste
- **Aspose.Slides per .NET**: Assicurare la compatibilità con la versione più recente controllandone la [documentazione ufficiale](https://reference.aspose.com/slides/net/).

### Requisiti di configurazione dell'ambiente
- Un ambiente .NET funzionante.
- Accesso a un editor di codice, come Visual Studio.

### Prerequisiti di conoscenza
- Conoscenza di base di C# e del framework .NET.
- Familiarità con i concetti dei software di presentazione (facoltativa ma utile).

## Impostazione di Aspose.Slides per .NET

Per iniziare a utilizzare Aspose.Slides nel tuo progetto, devi installarlo tramite NuGet. Ecco i metodi disponibili:

**Utilizzo della CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Utilizzo del Gestore Pacchetti:**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet:**
Cerca "Aspose.Slides" e installa la versione più recente.

### Fasi di acquisizione della licenza

1. **Prova gratuita**: Inizia con un [prova gratuita](https://releases.aspose.com/slides/net/) per esplorare le funzionalità di base.
2. **Licenza temporanea**: Ottieni una licenza temporanea se hai bisogno di accedere a tutte le funzionalità per scopi di valutazione visitando [Qui](https://purchase.aspose.com/temporary-license/).
3. **Acquistare**: Per uso commerciale, acquistare una licenza da [Sito web di Aspose](https://purchase.aspose.com/buy).

Una volta installato e ottenuto il diritto di licenza, inizializza Aspose.Slides nel tuo progetto:
```csharp
using Aspose.Slides;

// Inizializza Aspose.Slides per .NET
var presentation = new Presentation();
```

## Guida all'implementazione

### Creazione di una nuova presentazione e aggiunta di un grafico a ciambella

#### Panoramica
Inizieremo creando una nuova presentazione e aggiungendo un grafico a ciambella alla prima diapositiva. Questa sezione illustra come caricare una presentazione esistente, accedere alle diapositive e inserire grafici.

**Passaggio 1: caricare o creare una presentazione**
Per prima cosa, specifica la directory dei documenti e carica una presentazione esistente:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Se non hai un file esistente, creane uno nuovo con `new Presentation()`.

**Passaggio 2: accedi alla prima diapositiva**
Accedi alla prima diapositiva in cui aggiungeremo il nostro grafico:
```csharp
ISlide slide = pres.Slides[0];
```

**Passaggio 3: aggiungere un grafico ad anello**
Aggiungi un grafico a ciambella con coordinate e dimensioni specificate:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurazione della cartella di lavoro dati

#### Panoramica
In questa sezione viene spiegato come configurare la cartella di lavoro dati associata al grafico a ciambella.

**Passaggio 4: accesso e cancellazione dei dati esistenti**
Accedi alla cartella di lavoro dei dati del grafico. Quindi cancella tutte le serie o categorie esistenti:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Passaggio 5: disabilitare la legenda e aggiungere serie**
Disattiva la legenda per mantenere pulito il grafico, quindi aggiungi fino a 15 serie con configurazioni personalizzate:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Aggiunta di categorie e punti dati

#### Panoramica
Adesso, popoliamo il grafico con categorie e punti dati per ogni serie.

**Passaggio 6: aggiungere categorie**
Esegui un ciclo per aggiungere 15 categorie:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Passaggio 7: popolare i punti dati**
Aggiungi punti dati per ogni serie all'interno della categoria corrente:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Personalizza l'aspetto
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Configura il formato dell'etichetta per l'ultima serie
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Configurare la visualizzazione dell'etichetta
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Salvataggio della presentazione

**Passaggio 8: salvare il file**
Infine, salva la presentazione in una directory specificata:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}