---
"description": "Scopri come aggiungere diverse linee di tendenza a Java Slides utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per una visualizzazione efficace dei dati."
"linktitle": "Linee di tendenza del grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Linee di tendenza del grafico in Java Slides"
"url": "/it/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Linee di tendenza del grafico in Java Slides


## Introduzione alle linee di tendenza dei grafici in Java Slides: una guida passo passo

In questa guida completa, esploreremo come creare grafici con linee di tendenza in Java Slides utilizzando Aspose.Slides per Java. Le linee di tendenza nei grafici possono essere un'aggiunta preziosa alle vostre presentazioni, aiutandovi a visualizzare e analizzare efficacemente le tendenze dei dati. Vi guideremo attraverso il processo con spiegazioni chiare ed esempi di codice.

## Prerequisiti

Prima di addentrarci nella creazione delle linee di tendenza del grafico, assicurati di avere i seguenti prerequisiti:

- Ambiente di sviluppo Java
- Libreria Aspose.Slides per Java
- Un editor di codice a tua scelta

## Fase 1: Iniziare

Iniziamo impostando l'ambiente necessario e creando una nuova presentazione:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Creazione di una presentazione vuota
Presentation pres = new Presentation();
```

Abbiamo inizializzato la nostra presentazione e ora siamo pronti ad aggiungere un grafico a colonne raggruppate:

```java
// Creazione di un grafico a colonne raggruppate
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Passaggio 2: aggiunta della linea di tendenza esponenziale

Iniziamo aggiungendo una linea di tendenza esponenziale alla nostra serie di grafici:

```java
// Aggiunta di una linea di tendenza esponenziale per la serie di grafici 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Passaggio 3: aggiunta della linea di tendenza lineare

Successivamente, aggiungeremo una linea di tendenza lineare alla nostra serie di grafici:

```java
// Aggiunta di una linea di tendenza lineare per la serie di grafici 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Passaggio 4: aggiunta della linea di tendenza logaritmica

Ora aggiungiamo una linea di tendenza logaritmica a una serie di grafici diversa:

```java
// Aggiunta di una linea di tendenza logaritmica per la serie di grafici 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Passaggio 5: aggiunta della linea di tendenza della media mobile

Possiamo anche aggiungere una linea di tendenza media mobile:

```java
// Aggiunta della linea di tendenza della media mobile per la serie di grafici 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Passaggio 6: aggiunta della linea di tendenza polinomiale

Aggiunta di una linea di tendenza polinomiale:

```java
// Aggiunta di una linea di tendenza polinomiale per la serie di grafici 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Fase 7: Aggiunta della linea di tendenza della potenza

Infine, aggiungiamo una linea di tendenza di potenza:

```java
// Aggiunta di una linea di tendenza di potenza per la serie di grafici 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Passaggio 8: salvataggio della presentazione

Ora che abbiamo aggiunto varie linee di tendenza al nostro grafico, salviamo la presentazione:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai creato con successo una presentazione con diversi tipi di linee di tendenza in Java Slides utilizzando Aspose.Slides per Java.

## Codice sorgente completo per le linee di tendenza dei grafici in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Creazione di una presentazione vuota
Presentation pres = new Presentation();
// Creazione di un grafico a colonne raggruppate
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Aggiunta di una linea di tendenza potenziale per la serie di grafici 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Aggiunta di una linea di tendenza lineare per la serie di grafici 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Aggiunta di una linea di tendenza logaritmica per la serie di grafici 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Aggiunta della linea di tendenza della media mobile per la serie di grafici 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Aggiunta di una linea di tendenza polinomiale per la serie di grafici 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Aggiunta della linea di tendenza di potenza per la serie di grafici 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Salvataggio della presentazione
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial abbiamo imparato come aggiungere diversi tipi di linee di tendenza ai grafici in Java Slides utilizzando la libreria Aspose.Slides per Java. Che si lavori sull'analisi dei dati o si creino presentazioni informative, la possibilità di visualizzare le tendenze può essere uno strumento potente.

## Domande frequenti

### Come posso cambiare il colore di una linea di tendenza in Aspose.Slides per Java?

Per cambiare il colore di una linea di tendenza, puoi usare `getSolidFillColor().setColor(Color)` metodo, come mostrato nell'esempio per l'aggiunta di una linea di tendenza lineare.

### Posso aggiungere più linee di tendenza a una singola serie di grafici?

Sì, puoi aggiungere più linee di tendenza a una singola serie di grafici. Basta chiamare il `getTrendLines().add()` metodo per ogni linea di tendenza che vuoi aggiungere.

### Come faccio a rimuovere una linea di tendenza da un grafico in Aspose.Slides per Java?

Per rimuovere una linea di tendenza da un grafico, puoi utilizzare `removeAt(int index)` metodo, specificando l'indice della linea di tendenza che si desidera rimuovere.

### È possibile personalizzare la visualizzazione dell'equazione della linea di tendenza?

Sì, puoi personalizzare la visualizzazione dell'equazione della linea di tendenza utilizzando `setDisplayEquation(boolean)` metodo, come dimostrato nell'esempio.

### Come posso accedere a più risorse ed esempi per Aspose.Slides per Java?

È possibile accedere a risorse aggiuntive, documentazione ed esempi per Aspose.Slides per Java su [Sito web di Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}