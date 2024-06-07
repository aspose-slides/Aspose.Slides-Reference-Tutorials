---
title: Grafici normali nelle diapositive Java
linktitle: Grafici normali nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea grafici normali nelle diapositive Java con Aspose.Slides per Java. Guida passo passo e codice sorgente per creare, personalizzare e salvare grafici nelle presentazioni PowerPoint.
type: docs
weight: 21
url: /it/java/chart-data-manipulation/normal-charts-java-slides/
---

## Introduzione ai grafici normali nelle diapositive Java

In questo tutorial, esamineremo il processo di creazione di grafici normali in Java Slides utilizzando l'API Aspose.Slides per Java. Utilizzeremo istruzioni dettagliate insieme al codice sorgente per dimostrare come creare un istogramma in cluster in una presentazione di PowerPoint.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Aspose.Slides per API Java installata.
2. Predisposizione di un ambiente di sviluppo Java.
3. Conoscenza base della programmazione Java.

## Passaggio 1: impostazione del progetto

Assicurati di avere una directory per il tuo progetto. Chiamiamolo "Directory dei tuoi documenti" come menzionato nel codice. Puoi sostituirlo con il percorso effettivo della directory del progetto.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Passaggio 2: creazione di una presentazione

Ora creiamo una presentazione PowerPoint e accediamo alla sua prima diapositiva.

```java
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation pres = new Presentation();
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```

## Passaggio 3: aggiunta di un grafico

Aggiungeremo un istogramma raggruppato alla diapositiva e ne imposteremo il titolo.

```java
// Aggiungi grafico con dati predefiniti
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titolo del grafico delle impostazioni
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Passaggio 4: impostazione dei dati del grafico

Successivamente, imposteremo i dati del grafico definendo serie e categorie.

```java
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Elimina le serie e le categorie generate predefinite
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Aggiunta di nuove serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Passaggio 5: popolamento dei dati della serie

Ora popoliamo i punti dati della serie per il grafico.

```java
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Popolamento dei dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//Impostazione del colore di riempimento per le serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Popolamento dei dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

//Impostazione del colore di riempimento per le serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Passaggio 6: personalizzazione delle etichette

Personalizziamo le etichette dei dati per le serie di grafici.

```java
// La prima etichetta mostrerà il nome della categoria
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Mostra il valore per la terza etichetta con il nome della serie e il separatore
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Passaggio 7: salvataggio della presentazione

Infine, salva la presentazione con il grafico nella directory del tuo progetto.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai creato con successo un istogramma in cluster in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente questo grafico in base alle tue esigenze.

## Codice sorgente completo per grafici normali in diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation pres = new Presentation();
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titolo del grafico delle impostazioni
// Chart.getChartTitle().getTextFrameForOverriding().setText("Titolo campione");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina le serie e le categorie generate predefinite
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Aggiunta di nuove serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
//Impostazione del colore di riempimento per le serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
//Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//Impostazione del colore di riempimento per le serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// La prima etichetta mostrerà il nome della categoria
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Mostra il valore per la terza etichetta
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Salva la presentazione con il grafico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusione

In questo tutorial, abbiamo imparato come creare grafici normali in Java Slides utilizzando l'API Aspose.Slides per Java. Abbiamo seguito una guida passo passo con il codice sorgente per creare un istogramma in cluster in una presentazione di PowerPoint.

## Domande frequenti

### Come posso cambiare il tipo di grafico?

 Per cambiare il tipo di grafico, modificare il file`ChartType` parametro quando si aggiunge il grafico utilizzando`sld.getShapes().addChart()`. Puoi scegliere tra vari tipi di grafici disponibili in Aspose.Slides.

### Posso cambiare i colori delle serie di grafici?

 Sì, puoi modificare i colori delle serie di grafici impostando il colore di riempimento per ciascuna serie utilizzando`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Come faccio ad aggiungere più categorie o serie al grafico?

 Puoi aggiungere più categorie o serie al grafico aggiungendo nuovi punti dati ed etichette utilizzando`chart.getChartData().getCategories().add()` E`chart.getChartData().getSeries().add()` metodi.

### Come posso personalizzare ulteriormente il titolo del grafico?

 È possibile personalizzare ulteriormente il titolo del grafico modificando le proprietà di`chart.getChartTitle()` come l'allineamento del testo, la dimensione del carattere e il colore.

### Come faccio a salvare il grafico in un formato di file diverso?

 Per salvare il grafico in un formato file diverso, modificare il file`SaveFormat` parametro nel`pres.save()`metodo nel formato desiderato (ad esempio, PDF, PNG, JPEG).