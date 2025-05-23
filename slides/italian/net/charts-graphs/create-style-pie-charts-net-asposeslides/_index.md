---
"date": "2025-04-15"
"description": "Scopri come automatizzare la creazione di grafici a torta nelle presentazioni .NET con Aspose.Slides, migliorando la visualizzazione dei dati senza sforzo."
"title": "Come creare e personalizzare grafici a torta nelle presentazioni .NET utilizzando Aspose.Slides"
"url": "/it/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e personalizzare grafici a torta nelle presentazioni .NET utilizzando Aspose.Slides

## Introduzione
Creare presentazioni coinvolgenti e informative è fondamentale per una comunicazione efficace, sia che si tratti di presentare dati al lavoro o di presentare i risultati dei propri ultimi progetti. Un modo efficace per visualizzare i dati è attraverso i grafici a torta, che possono rappresentare in modo sintetico le singole parti di un insieme. Tuttavia, creare manualmente questi grafici in software di presentazione come PowerPoint può richiedere molto tempo e potrebbe non avere la flessibilità necessaria per gli aggiornamenti dinamici.

È qui che entra in gioco Aspose.Slides per .NET. Questa libreria completa consente di creare, modificare e personalizzare le presentazioni a livello di codice, rendendola uno strumento prezioso per gli sviluppatori che desiderano automatizzare il flusso di lavoro e garantire la coerenza tra le presentazioni.

In questo tutorial, esploreremo come utilizzare Aspose.Slides per .NET per creare e personalizzare grafici a torta nelle tue presentazioni. Imparerai come:
- **Crea una presentazione e accedi alle diapositive**
- **Aggiungere e configurare grafici a torta**
- **Personalizza i dati e le serie del grafico**
- **Stilizzare i settori del grafico a torta**
- **Aggiungi etichette personalizzate**
- **Configura le proprietà di visualizzazione e salva la presentazione**

Pronti a immergervi nella creazione di fantastici grafici a torta in tutta semplicità? Iniziamo!

## Prerequisiti
Prima di iniziare, assicurati di aver impostato quanto segue:

### Librerie richieste
- Aspose.Slides per .NET (si consiglia la versione 21.11 o successiva)

### Configurazione dell'ambiente
- Un ambiente di sviluppo che esegue .NET Framework o .NET Core/5+/6+
- Un editor di codice come Visual Studio

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione C#
- Familiarità con i concetti orientati agli oggetti

## Impostazione di Aspose.Slides per .NET
Per iniziare, è necessario installare la libreria Aspose.Slides. Puoi farlo utilizzando uno dei seguenti metodi:

**Interfaccia a riga di comando .NET**
```bash
dotnet add package Aspose.Slides
```

**Console del gestore dei pacchetti**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet**
- Apri il progetto in Visual Studio.
- Vai su "Strumenti" > "Gestore pacchetti NuGet" > "Gestisci pacchetti NuGet per la soluzione".
- Cerca "Aspose.Slides" e installa la versione più recente.

### Fasi di acquisizione della licenza
Per utilizzare Aspose.Slides, puoi iniziare con una prova gratuita scaricando una licenza temporanea. Visita [Il sito web di Aspose](https://purchase.aspose.com/temporary-license/) per ottenerlo. Per un utilizzo continuativo, si consiglia di acquistare una licenza completa.

### Inizializzazione e configurazione di base
Una volta installato, inizializza la classe Presentation, che rappresenta il tuo file PPTX:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Guida all'implementazione
Suddivideremo il processo di creazione del grafico a torta in sezioni gestibili. Ogni sezione è progettata per concentrarsi su una funzionalità specifica, consentendoti di ampliare gradualmente le tue conoscenze.

### Crea una presentazione e accedi alle diapositive
**Panoramica:** Inizia creando una nuova presentazione e accedendo alla sua prima diapositiva. Questo prepara il terreno per l'aggiunta di grafici e altri elementi.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Crea un'istanza della classe Presentazione che rappresenta un file PPTX
    Presentation presentation = new Presentation();
    
    // Accedi alla prima diapositiva
    ISlide slides = presentation.Slides[0];
}
```

### Aggiungi e configura grafico a torta
**Panoramica:** Scopri come aggiungere un grafico a torta alla tua diapositiva e impostarne il titolo per il contesto.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Crea un'istanza della classe Presentazione che rappresenta un file PPTX
    Presentation presentation = new Presentation();
    
    // Accedi alla prima diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Aggiungi un grafico con dati predefiniti alla diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Titolo del grafico di impostazione
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Personalizza i dati e le serie del grafico
**Panoramica:** Personalizza le categorie e le serie di dati in base alle tue esigenze specifiche.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Crea un'istanza della classe Presentazione che rappresenta un file PPTX
    Presentation presentation = new Presentation();
    
    // Accedi alla prima diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Aggiungi un grafico con dati predefiniti alla diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Imposta la prima serie su Mostra valori
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Impostazione dell'indice del foglio dati del grafico
    int defaultWorksheetIndex = 0;
    
    // Ottenere il foglio di lavoro dei dati del grafico
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Elimina le serie e le categorie generate di default
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Aggiunta di nuove categorie
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Aggiunta di nuove serie
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Ora popolamento dei dati della serie
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Personalizza gli stili dei settori del grafico a torta
**Panoramica:** Definisci i singoli settori del grafico a torta per migliorarne l'aspetto visivo e mettere in risalto i punti dati chiave.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Crea un'istanza della classe Presentazione che rappresenta un file PPTX
    Presentation presentation = new Presentation();
    
    // Accedi alla prima diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Aggiungi un grafico con dati predefiniti alla diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Ottieni serie dal grafico
    IChartSeries series = chart.ChartData.Series[0];
    
    // Personalizzazione degli stili di settore per ogni punto dati nella serie
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Impostazione del confine del settore
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Impostazione del confine del settore
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Impostazione del confine del settore
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Aggiungi etichette personalizzate al grafico a torta
**Panoramica:** Migliora il tuo grafico a torta aggiungendo etichette personalizzate per una rappresentazione più chiara dei dati.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Regolare la posizione dell'etichetta secondo necessità
    }
}
```

### Conclusione
Ora hai imparato a creare e personalizzare grafici a torta nelle presentazioni .NET utilizzando Aspose.Slides. Questa automazione può migliorare significativamente i tuoi sforzi di visualizzazione dei dati, risparmiando tempo e garantendo la coerenza tra le presentazioni.

Per esplorare ulteriormente le funzionalità di Aspose.Slides per .NET, valuta la possibilità di approfondire funzionalità aggiuntive, come la creazione di altri tipi di grafici o l'integrazione di elementi di progettazione più complessi nelle diapositive.

Buona programmazione!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}