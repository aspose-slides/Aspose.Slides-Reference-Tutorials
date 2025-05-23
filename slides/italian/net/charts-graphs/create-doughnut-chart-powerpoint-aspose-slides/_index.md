---
"date": "2025-04-15"
"description": "Scopri come creare grafici a ciambella dinamici e visivamente accattivanti nelle presentazioni PowerPoint utilizzando la potente libreria Aspose.Slides per .NET."
"title": "Come creare un grafico a ciambella in PowerPoint utilizzando Aspose.Slides per .NET"
"url": "/it/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a ciambella in PowerPoint utilizzando Aspose.Slides per .NET
Creare grafici visivamente accattivanti è essenziale per una presentazione efficace dei dati. I grafici ad anello sono perfetti per illustrare parti di un insieme, rendendoli ideali per la visualizzazione di dati basata su percentuali. Questo tutorial vi guiderà nella creazione di un grafico ad anello dinamico in PowerPoint utilizzando la potente libreria Aspose.Slides per .NET.

## Introduzione
Le presentazioni spesso richiedono rappresentazioni visive di set di dati complessi, laddove i tradizionali grafici a barre o a linee potrebbero rivelarsi inadeguati. Il grafico a ciambella si rivela uno strumento versatile per comunicare efficacemente dati percentuali con stile e chiarezza. In questo tutorial, esploreremo come Aspose.Slides per .NET semplifica il processo di creazione di questi grafici direttamente in PowerPoint.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per .NET
- Istruzioni passo passo per creare un grafico a ciambella
- Aggiungere serie e categorie al grafico
- Configurazione delle etichette dati per una maggiore chiarezza
- Salvataggio della presentazione finale

Scopriamo insieme come sfruttare Aspose.Slides per .NET per migliorare le tue presentazioni con grafici a ciambella personalizzati.

## Prerequisiti
Prima di iniziare, assicurati di avere a disposizione quanto segue:
- **Aspose.Slides per la libreria .NET**: Disponibile tramite NuGet o download diretto.
- **Ambiente di sviluppo**Visual Studio è consigliato per i progetti .NET.
- Conoscenza di base di C# e familiarità con la struttura di PowerPoint.

## Impostazione di Aspose.Slides per .NET
Per iniziare a creare grafici, devi prima configurare la libreria Aspose.Slides nel tuo progetto. Ecco diversi modi per installarla:

**Utilizzo della CLI .NET:**

```bash
dotnet add package Aspose.Slides
```

**Utilizzo della console di Package Manager:**

```powershell
Install-Package Aspose.Slides
```

**Tramite l'interfaccia utente di NuGet Package Manager:**
Cerca "Aspose.Slides" e installa la versione più recente.

Una volta installato, puoi iniziare a configurare il tuo progetto. Se non hai mai usato Aspose.Slides, potresti valutare l'acquisto di una licenza temporanea o di una prova gratuita per esplorare tutte le sue funzionalità senza limitazioni.

### Inizializza il tuo progetto
Ecco come puoi inizializzare Aspose.Slides nella tua applicazione:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Crea un'istanza della classe Presentazione
        Presentation presentation = new Presentation();
        
        // Il tuo codice per manipolare la presentazione va qui
        
        // Salva la presentazione
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Guida all'implementazione
### Creazione di un grafico a ciambella
#### Panoramica
Per prima cosa, creeremo un grafico a ciambella vuoto in una diapositiva di PowerPoint. Questo servirà da base per aggiungere dati e personalizzarne l'aspetto.

**Passaggio 1: aggiungere un grafico ad anello**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Aggiungere un grafico a ciambella alla prima diapositiva nella posizione (10, 10) con dimensione (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Cancella serie e categorie esistenti
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Disattiva la legenda per un aspetto più pulito
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Spiegazione:**
- **aggiungiGrafico**: Inserisce un nuovo grafico a ciambella nella diapositiva.
- **getChartDataWorkbook**: Fornisce accesso alle celle dati nel grafico per la manipolazione.

### Aggiunta di serie e categorie
#### Panoramica
Successivamente, popoleremo il tuo grafico con dati significativi aggiungendo serie e categorie.

**Passaggio 2: aggiungere serie di dati**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Aggiungi serie
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Personalizzazione del foro della ciambella e dell'angolo di partenza
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Aggiungi categorie
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formattazione del riempimento e della linea del punto dati
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Spiegazione:**
- **aggiungere**: Inserisce nuove serie e categorie nel grafico.
- **impostaDimensioneForoCiambella**Configura la dimensione del buco della ciambella, migliorandone l'aspetto visivo.

### Configurazione delle etichette dati
#### Panoramica
Le etichette dati forniscono contesto ai dati del grafico. Miglioriamo la leggibilità personalizzandole.

**Passaggio 3: personalizzare le etichette dati**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Personalizzazione delle etichette dati
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Spiegazione:**
- **Etichetta dati IData**: Personalizza le etichette dei dati per maggiore chiarezza e presentazione.
- **impostaCenterText**, **mostraPercentuale**: Migliora la leggibilità delle etichette centrando il testo e mostrando le percentuali.

## Conclusione
Seguendo questa guida, hai imparato a creare un grafico a ciambella dinamico in PowerPoint utilizzando Aspose.Slides per .NET. Questa potente libreria consente un'ampia personalizzazione, consentendoti di adattare i grafici alle tue esigenze di presentazione.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}