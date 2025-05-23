---
"description": "Scopri come creare grafici a dispersione in Java utilizzando Aspose.Slides. Guida passo passo con codice sorgente Java per la visualizzazione dei dati nelle presentazioni."
"linktitle": "Grafico sparso in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico sparso in Java Slides"
"url": "/it/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico sparso in Java Slides


## Introduzione ai grafici sparsi in Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a dispersione utilizzando Aspose.Slides per Java. I grafici a dispersione sono utili per visualizzare punti dati su un piano bidimensionale. Forniremo istruzioni dettagliate e includeremo il codice sorgente Java per la tua comodità.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. [Aspose.Slides per Java](https://products.aspose.com/slides/java) installato.
2. È stato configurato un ambiente di sviluppo Java.

## Passaggio 1: inizializzare la presentazione

Per prima cosa, importa le librerie necessarie e crea una nuova presentazione.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Crea una nuova presentazione
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere una diapositiva e creare il grafico a dispersione

Successivamente, aggiungi una diapositiva e crea il grafico a dispersione su di essa. Useremo il `ScatterWithSmoothLines` tipo di grafico in questo esempio.

```java
// Ottieni la prima diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Creazione del grafico a dispersione
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Passaggio 3: preparare i dati del grafico

Ora prepariamo i dati per il nostro grafico a dispersione. Aggiungeremo due serie, ciascuna con più punti dati.

```java
// Ottenere l'indice predefinito del foglio di lavoro dei dati del grafico
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Elimina la serie demo
chart.getChartData().getSeries().clear();

// Aggiungi la prima serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aggiungere punti dati alla prima serie
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Modifica il tipo di serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Cambia dimensione del marcatore
series.getMarker().setSymbol(MarkerStyleType.Star); // Cambia il simbolo del marcatore

// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Aggiungere punti dati alla seconda serie
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

Ecco fatto! Hai creato con successo un grafico a dispersione utilizzando Aspose.Slides per Java. Ora puoi personalizzare ulteriormente questo esempio per adattarlo ai tuoi specifici requisiti di dati e design.

## Codice sorgente completo per grafici sparsi in Java Slides
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Creazione del grafico predefinito
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Ottenere l'indice predefinito del foglio di lavoro dei dati del grafico
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina la serie demo
chart.getChartData().getSeries().clear();
// Aggiungi nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Aggiungere un nuovo punto (1:3) qui.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Aggiungi nuovo punto (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Modifica il tipo di serie
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Modifica del marcatore della serie del grafico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Aggiungere un nuovo punto (5:2) qui.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Aggiungi nuovo punto (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Aggiungi nuovo punto (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Aggiungi nuovo punto (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Modifica del marcatore della serie del grafico
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, ti abbiamo illustrato il processo di creazione di un grafico a dispersione utilizzando Aspose.Slides per Java. I grafici a dispersione sono potenti strumenti per visualizzare punti dati in uno spazio bidimensionale, semplificando l'analisi e la comprensione di relazioni complesse tra i dati.

## Domande frequenti

### Come posso cambiare il tipo di grafico?

Per cambiare il tipo di grafico, utilizzare `setType` metodo sulla serie di grafici e fornire il tipo di grafico desiderato. Ad esempio, `series.setType(ChartType.Line)` trasformerebbe la serie in un grafico a linee.

### Come posso personalizzare le dimensioni e lo stile del pennarello?

È possibile modificare la dimensione e lo stile del marcatore utilizzando `getMarker` metodo sulla serie e quindi imposta le proprietà dimensione e simbolo. Ad esempio:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Sentiti libero di esplorare ulteriori opzioni di personalizzazione nella documentazione di Aspose.Slides per Java.

Ricordati di sostituire `"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}