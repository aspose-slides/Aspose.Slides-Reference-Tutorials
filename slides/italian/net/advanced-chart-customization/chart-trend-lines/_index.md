---
title: Esplorazione delle linee di tendenza del grafico in Aspose.Slides per .NET
linktitle: Linee di tendenza del grafico
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere varie linee di tendenza ai grafici utilizzando Aspose.Slides per .NET in questa guida passo passo. Migliora le tue capacità di visualizzazione dei dati con facilità!
weight: 12
url: /it/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Nel mondo della visualizzazione e presentazione dei dati, incorporare i grafici può essere un modo potente per trasmettere le informazioni in modo efficace. Aspose.Slides per .NET fornisce un set di strumenti ricco di funzionalità per lavorare con i grafici, inclusa la possibilità di aggiungere linee di tendenza ai grafici. In questo tutorial, approfondiremo il processo di aggiunta di linee di tendenza a un grafico in modo passo passo utilizzando Aspose.Slides per .NET. 

## Prerequisiti

Prima di iniziare a lavorare con Aspose.Slides per .NET, dovrai assicurarti di disporre dei seguenti prerequisiti:

1. Aspose.Slides per .NET: per accedere alla libreria e utilizzarla, è necessario avere Aspose.Slides per .NET installato. È possibile ottenere la libreria da[pagina di download](https://releases.aspose.com/slides/net/).

2. Ambiente di sviluppo: è necessario disporre di un ambiente di sviluppo configurato, preferibilmente utilizzando un ambiente di sviluppo integrato .NET come Visual Studio.

3. Conoscenza di base di C#: una comprensione fondamentale della programmazione C# è utile, poiché utilizzeremo C# per lavorare con Aspose.Slides per .NET.

Ora che abbiamo coperto i prerequisiti, analizziamo passo dopo passo il processo di aggiunta delle linee di tendenza a un grafico.

## Importazione di spazi dei nomi

Innanzitutto, assicurati di importare gli spazi dei nomi necessari nel tuo progetto C#. Questi spazi dei nomi sono essenziali per lavorare con Aspose.Slides per .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Passaggio 1: crea una presentazione

In questo passaggio creiamo una presentazione vuota con cui lavorare.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";

// Crea directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Creazione di una presentazione vuota
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico alla diapositiva

Successivamente, aggiungiamo un istogramma in cluster a una diapositiva.

```csharp
// Creazione di un istogramma a colonne raggruppate
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Passaggio 3: aggiungi linee di tendenza al grafico

Ora aggiungiamo vari tipi di linee di tendenza alla serie di grafici.

### Aggiunta di una linea di tendenza esponenziale

```csharp
// Aggiunta della linea di tendenza esponenziale per la serie di grafici 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Aggiunta di una linea di tendenza lineare

```csharp
// Aggiunta di una linea di tendenza lineare per la serie di grafici 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Aggiunta di una linea di tendenza logaritmica

```csharp
// Aggiunta della linea di tendenza logaritmica per la serie di grafici 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Aggiunta di una linea di tendenza della media mobile

```csharp
// Aggiunta della linea di tendenza della media mobile per la serie di grafici 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Aggiunta di una linea di tendenza polinomiale

```csharp
// Aggiunta della linea di tendenza polinomiale per la serie di grafici 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Aggiunta di una linea di tendenza della potenza

```csharp
// Aggiunta della linea di tendenza della potenza per la serie di grafici 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Passaggio 4: salva la presentazione

Dopo aver aggiunto le linee di tendenza al grafico, salva la presentazione.

```csharp
// Salvataggio della presentazione
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai aggiunto con successo varie linee di tendenza al tuo grafico utilizzando Aspose.Slides per .NET.

## Conclusione

Aspose.Slides per .NET è una libreria versatile che ti consente di creare e manipolare grafici con facilità. Seguendo questa guida passo passo, puoi aggiungere diversi tipi di linee di tendenza ai tuoi grafici, migliorando la rappresentazione visiva dei tuoi dati.

### Domande frequenti

### Dove posso trovare la documentazione per Aspose.Slides per .NET?
 È possibile accedere alla documentazione[Qui](https://reference.aspose.com/slides/net/).

### Come posso scaricare Aspose.Slides per .NET?
 È possibile scaricare Aspose.Slides per .NET dalla pagina di download[Qui](https://releases.aspose.com/slides/net/).

### È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi provare Aspose.Slides per .NET gratuitamente visitando[questo link](https://releases.aspose.com/).

### Dove posso acquistare Aspose.Slides per .NET?
 Per acquistare Aspose.Slides per .NET, visitare la pagina di acquisto[Qui](https://purchase.aspose.com/buy).

### Ho bisogno di una licenza temporanea per Aspose.Slides per .NET?
 È possibile ottenere una licenza temporanea per Aspose.Slides per .NET da[questo link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
