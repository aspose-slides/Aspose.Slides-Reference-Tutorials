---
"description": "Scopri come personalizzare i grafici in Java Slides utilizzando Aspose.Slides per Java. Esplora le opzioni del secondo grafico e migliora le tue presentazioni."
"linktitle": "Opzioni del secondo grafico per i grafici in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Opzioni del secondo grafico per i grafici in Java Slides"
"url": "/it/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opzioni del secondo grafico per i grafici in Java Slides


## Introduzione alle opzioni del secondo grafico per i grafici in Java Slides

In questo tutorial, esploreremo come aggiungere opzioni di secondo grafico ai grafici utilizzando Aspose.Slides per Java. Le opzioni di secondo grafico consentono di personalizzare l'aspetto e il comportamento dei grafici, in particolare in scenari come i grafici a torta. Forniremo istruzioni dettagliate ed esempi di codice sorgente per raggiungere questo obiettivo. 

## Prerequisiti
Prima di iniziare, assicurati di aver installato e configurato Aspose.Slides per Java nel tuo progetto Java.

## Passaggio 1: creare una presentazione
Iniziamo creando una nuova presentazione:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungere un grafico a una diapositiva
Successivamente, aggiungeremo un grafico a una diapositiva. In questo esempio, creeremo un grafico a torta:

```java
// Aggiungi grafico alla diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Passaggio 3: personalizzare le proprietà del grafico
Ora impostiamo diverse proprietà per il grafico, incluse le opzioni del secondo grafico:

```java
// Mostra le etichette dei dati per la prima serie
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Imposta la dimensione della seconda torta (in percentuale)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Dividi la torta in percentuale
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Imposta la posizione della divisione
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Passaggio 4: salva la presentazione
Infine, salva la presentazione con le opzioni del grafico e del secondo grafico:

```java
// Scrivi la presentazione su disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per le opzioni del secondo grafico

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
// Aggiungi grafico alla diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Imposta proprietà diverse
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Scrivi la presentazione su disco
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere opzioni di secondo grafico ai grafici in Java Slides utilizzando Aspose.Slides per Java. Puoi personalizzare diverse proprietà per migliorare l'aspetto e la funzionalità dei tuoi grafici, rendendo le tue presentazioni più informative e visivamente accattivanti.

## Domande frequenti

### Come posso modificare la dimensione della seconda torta in un grafico a torta?

Per modificare la dimensione della seconda torta in un grafico a torta, utilizzare `setSecondPieSize` metodo come mostrato nell'esempio di codice sopra. Modifica il valore per specificare la dimensione in percentuale.

### Cosa fa? `PieSplitBy` controllo in un grafico a torta?

IL `PieSplitBy` La proprietà controlla come viene suddiviso il grafico a torta. Puoi impostarla su `PieSplitType.ByPercentage` O `PieSplitType.ByValue` per dividere il grafico rispettivamente in base alla percentuale o a un valore specifico.

### Come si imposta la posizione della divisione in un grafico a torta?

È possibile impostare la posizione della divisione in un grafico a torta utilizzando `setPieSplitPosition` metodo. Regola il valore per specificare la posizione desiderata.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}