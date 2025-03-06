---
title: Grafico sparso nelle diapositive Java
linktitle: Grafico sparso nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare grafici a dispersione in Java utilizzando Aspose.Slides. Guida passo passo con codice sorgente Java per la visualizzazione dei dati nelle presentazioni.
weight: 11
url: /it/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Grafico sparso nelle diapositive Java


## Introduzione al grafico sparso in Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a dispersione utilizzando Aspose.Slides per Java. I grafici a dispersione sono utili per visualizzare i punti dati su un piano bidimensionale. Forniremo istruzioni dettagliate e includeremo il codice sorgente Java per tua comodità.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. [Aspose.Slides per Java](https://products.aspose.com/slides/java) installato.
2. Predisposizione di un ambiente di sviluppo Java.

## Passaggio 1: inizializzare la presentazione

Innanzitutto, importa le librerie necessarie e crea una nuova presentazione.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Crea una nuova presentazione
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi una diapositiva e crea il grafico a dispersione

 Successivamente, aggiungi una diapositiva e crea il grafico a dispersione su di essa. Utilizzeremo il`ScatterWithSmoothLines`tipo di grafico in questo esempio.

```java
// Ottieni la prima diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Creazione del grafico a dispersione
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Passaggio 3: preparare i dati del grafico

Ora prepariamo i dati per il nostro grafico a dispersione. Aggiungeremo due serie, ciascuna con più punti dati.

```java
// Ottenere l'indice del foglio di lavoro dei dati del grafico predefinito
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Elimina la serie demo
chart.getChartData().getSeries().clear();

// Aggiungi la prima serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aggiungi punti dati alla prima serie
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Modifica il tipo di serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Modifica la dimensione del marcatore
series.getMarker().setSymbol(MarkerStyleType.Star); // Cambia il simbolo del marcatore

// Prendiamo la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Aggiungi punti dati alla seconda serie
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Cambia lo stile del marcatore per la seconda serie
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Passaggio 4: salva la presentazione

Infine, salva la presentazione con il grafico a dispersione in un file PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai creato con successo un grafico a dispersione utilizzando Aspose.Slides per Java. Ora puoi personalizzare ulteriormente questo esempio per adattarlo ai tuoi dati specifici e ai requisiti di progettazione.

## Codice sorgente completo per il grafico sparso nelle diapositive Java
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Creazione del grafico predefinito
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Ottenere l'indice del foglio di lavoro dei dati del grafico predefinito
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina la serie demo
chart.getChartData().getSeries().clear();
// Aggiungi nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Aggiungi un nuovo punto (1:3) lì.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Aggiungi nuovo punto (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Modifica il tipo di serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Modifica dell'indicatore della serie di grafici
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Aggiungi un nuovo punto (5:2) lì.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Aggiungi nuovo punto (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Aggiungi nuovo punto (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Aggiungi nuovo punto (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Modifica dell'indicatore della serie di grafici
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, ti abbiamo guidato attraverso il processo di creazione di un grafico a dispersione utilizzando Aspose.Slides per Java. I grafici a dispersione sono strumenti potenti per visualizzare i punti dati in uno spazio bidimensionale, semplificando l'analisi e la comprensione delle relazioni complesse tra dati.

## Domande frequenti

### Come posso cambiare il tipo di grafico?

 Per modificare il tipo di grafico, utilizzare il file`setType` metodo sulla serie di grafici e fornire il tipo di grafico desiderato. Per esempio,`series.setType(ChartType.Line)` cambierebbe la serie in un grafico a linee.

### Come posso personalizzare la dimensione e lo stile del pennarello?

 Puoi modificare la dimensione e lo stile del marcatore utilizzando il comando`getMarker` metodo sulla serie e quindi impostare le proprietà della dimensione e del simbolo. Per esempio:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Sentiti libero di esplorare ulteriori opzioni di personalizzazione nella documentazione Aspose.Slides per Java.

 Ricordarsi di sostituire`"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
