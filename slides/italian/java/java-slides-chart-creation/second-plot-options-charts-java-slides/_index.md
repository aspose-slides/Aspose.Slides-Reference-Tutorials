---
title: Opzioni di seconda trama per i grafici nelle diapositive Java
linktitle: Opzioni di seconda trama per i grafici nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come personalizzare i grafici in Diapositive Java utilizzando Aspose.Slides per Java. Esplora le opzioni della seconda trama e migliora le tue presentazioni.
weight: 12
url: /it/java/chart-creation/second-plot-options-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione alle opzioni del secondo grafico per i grafici nelle diapositive Java

In questo tutorial, esploreremo come aggiungere le opzioni del secondo grafico ai grafici utilizzando Aspose.Slides per Java. Le opzioni del secondo grafico consentono di personalizzare l'aspetto e il comportamento dei grafici, in particolare in scenari come i grafici a torta. Forniremo istruzioni dettagliate ed esempi di codice sorgente per raggiungere questo obiettivo. 

## Prerequisiti
Prima di iniziare, assicurati di avere Aspose.Slides per Java installato e configurato nel tuo progetto Java.

## Passaggio 1: crea una presentazione
Iniziamo creando una nuova presentazione:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi un grafico a una diapositiva
Successivamente, aggiungeremo un grafico a una diapositiva. In questo esempio, creeremo un grafico a torta:

```java
// Aggiungi grafico alla diapositiva
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Passaggio 3: personalizzare le proprietà del grafico
Ora impostiamo diverse proprietà per il grafico, incluse le opzioni del secondo grafico:

```java
// Mostra le etichette dati per la prima serie
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

## Codice sorgente completo per le opzioni della seconda trama

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
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

In questo tutorial, abbiamo imparato come aggiungere opzioni di secondo grafico ai grafici in Java Slides utilizzando Aspose.Slides per Java. Puoi personalizzare varie proprietà per migliorare l'aspetto e la funzionalità dei tuoi grafici, rendendo le tue presentazioni più informative e visivamente accattivanti.

## Domande frequenti

### Come posso modificare la dimensione della seconda torta in un grafico a torta?

Per modificare la dimensione della seconda torta in un grafico a torta, utilizzare il comando`setSecondPieSize` metodo come mostrato nell'esempio di codice precedente. Regola il valore per specificare la dimensione in percentuale.

###  Cosa fa`PieSplitBy` control in a Pie of Pie chart?

 IL`PieSplitBy` La proprietà controlla il modo in cui viene suddiviso il grafico a torta. Puoi impostarlo su entrambi`PieSplitType.ByPercentage` O`PieSplitType.ByValue` per dividere il grafico rispettivamente in percentuale o in base a un valore specifico.

### Come posso impostare la posizione della divisione in un grafico a torta?

 È possibile impostare la posizione della suddivisione in un grafico a torta utilizzando il comando`setPieSplitPosition` metodo. Regolare il valore per specificare la posizione desiderata.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
