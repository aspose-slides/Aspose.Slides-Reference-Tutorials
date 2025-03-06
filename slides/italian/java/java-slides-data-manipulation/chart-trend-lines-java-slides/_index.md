---
title: Linee di tendenza del grafico nelle diapositive Java
linktitle: Linee di tendenza del grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere varie linee di tendenza alle diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per una visualizzazione efficace dei dati.
weight: 15
url: /it/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linee di tendenza del grafico nelle diapositive Java


## Introduzione alle linee di tendenza del grafico nelle diapositive Java: una guida passo passo

In questa guida completa, esploreremo come creare linee di tendenza del grafico in Java Slides utilizzando Aspose.Slides per Java. Le linee di tendenza del grafico possono essere una preziosa aggiunta alle tue presentazioni, aiutando a visualizzare e analizzare le tendenze dei dati in modo efficace. Ti guideremo attraverso il processo con spiegazioni chiare ed esempi di codice.

## Prerequisiti

Prima di immergerci nella creazione delle linee di tendenza del grafico, assicurati di disporre dei seguenti prerequisiti:

- Ambiente di sviluppo Java
- Aspose.Slides per la libreria Java
- Un editor di codice a tua scelta

## Passaggio 1: iniziare

Iniziamo configurando l'ambiente necessario e creando una nuova presentazione:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Creazione di una presentazione vuota
Presentation pres = new Presentation();
```

Abbiamo inizializzato la nostra presentazione e ora siamo pronti per aggiungere un istogramma in cluster:

```java
// Creazione di un istogramma a colonne raggruppate
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Passaggio 2: aggiunta della linea di tendenza esponenziale

Iniziamo aggiungendo una linea di tendenza esponenziale alla nostra serie di grafici:

```java
// Aggiunta della linea di tendenza esponenziale per la serie di grafici 1
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
// Aggiunta della linea di tendenza logaritmica per la serie di grafici 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Passaggio 5: aggiunta della linea di tendenza della media mobile

Possiamo anche aggiungere una linea di tendenza della media mobile:

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
// Aggiunta della linea di tendenza polinomiale per la serie di grafici 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Passaggio 7: aggiunta della linea di tendenza della potenza

Infine, aggiungiamo una linea di tendenza della potenza:

```java
// Aggiunta della linea di tendenza della potenza per la serie di grafici 3
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

## Codice sorgente completo per le linee di tendenza del grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Creazione di una presentazione vuota
Presentation pres = new Presentation();
// Creazione di un istogramma a colonne raggruppate
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Aggiunta della linea di tendenza potenziale per la serie di grafici 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Aggiunta della linea di tendenza lineare per la serie di grafici 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Aggiunta della linea di tendenza logaritmica per la serie di grafici 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Aggiunta della linea di tendenza della media mobile per la serie di grafici 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Aggiunta della linea di tendenza polinomiale per la serie di grafici 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Aggiunta della linea di tendenza della potenza per la serie di grafici 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Salvataggio della presentazione
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere diversi tipi di linee di tendenza ai grafici in Java Slides utilizzando la libreria Aspose.Slides per Java. Che tu stia lavorando all'analisi dei dati o alla creazione di presentazioni informative, la capacità di visualizzare le tendenze può essere uno strumento potente.

## Domande frequenti

### Come posso cambiare il colore di una linea di tendenza in Aspose.Slides per Java?

 Per cambiare il colore di una linea di tendenza, puoi usare il`getSolidFillColor().setColor(Color)` metodo, come mostrato nell'esempio per l'aggiunta di una linea di tendenza lineare.

### Posso aggiungere più linee di tendenza a una singola serie di grafici?

Sì, puoi aggiungere più linee di tendenza a una singola serie di grafici. Chiama semplicemente il`getTrendLines().add()` metodo per ogni linea di tendenza che desideri aggiungere.

### Come rimuovo una linea di tendenza da un grafico in Aspose.Slides per Java?

 Per rimuovere una linea di tendenza da un grafico, puoi utilizzare il comando`removeAt(int index)` metodo, specificando l'indice della linea di tendenza che desideri rimuovere.

### È possibile personalizzare la visualizzazione dell'equazione della linea di tendenza?

 Sì, puoi personalizzare la visualizzazione dell'equazione della linea di tendenza utilizzando`setDisplayEquation(boolean)` metodo, come dimostrato nell'esempio.

### Come posso accedere a più risorse ed esempi per Aspose.Slides per Java?

 È possibile accedere a risorse aggiuntive, documentazione ed esempi per Aspose.Slides per Java su[Sito web Aspose](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
