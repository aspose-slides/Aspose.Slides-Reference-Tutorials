---
"description": "Crea grafici normali in Java Slides con Aspose.Slides per Java. Guida passo passo e codice sorgente per creare, personalizzare e salvare grafici nelle presentazioni PowerPoint."
"linktitle": "Grafici normali in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafici normali in Java Slides"
"url": "/it/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafici normali in Java Slides


## Introduzione ai grafici normali in Java Slides

In questo tutorial, illustreremo il processo di creazione di grafici standard in Java Slides utilizzando l'API Aspose.Slides per Java. Utilizzeremo istruzioni dettagliate e il codice sorgente per illustrare come creare un grafico a colonne raggruppate in una presentazione di PowerPoint.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Installata l'API Aspose.Slides per Java.
2. È stato configurato un ambiente di sviluppo Java.
3. Conoscenza di base della programmazione Java.

## Fase 1: Impostazione del progetto

Assicurati di avere una directory per il tuo progetto. Chiamiamola "Directory dei tuoi documenti", come indicato nel codice. Puoi sostituirla con il percorso effettivo della directory del tuo progetto.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Passaggio 2: creazione di una presentazione

Ora creiamo una presentazione PowerPoint e accediamo alla sua prima diapositiva.

```java
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation pres = new Presentation();
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```

## Passaggio 3: aggiunta di un grafico

Aggiungeremo un grafico a colonne raggruppate alla diapositiva e ne imposteremo il titolo.

```java
// Aggiungi grafico con dati predefiniti
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titolo del grafico di impostazione
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Passaggio 4: impostazione dei dati del grafico

Ora imposteremo i dati del grafico definendo serie e categorie.

```java
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Elimina le serie e le categorie generate di default
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

## Passaggio 5: Popolamento dei dati della serie

Adesso, popoliamo i punti dati della serie per il grafico.

```java
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Popolamento dei dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Impostazione del colore di riempimento per la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Popolamento dei dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Impostazione del colore di riempimento per la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Passaggio 6: personalizzazione delle etichette

Personalizziamo le etichette dati per la serie di grafici.

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

Infine, salva la presentazione con il grafico nella directory del progetto.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai creato con successo un grafico a colonne raggruppate in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente questo grafico in base alle tue esigenze.

## Codice sorgente completo per grafici normali in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation pres = new Presentation();
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titolo del grafico di impostazione
// Chart.getChartTitle().getTextFrameForOverriding().setText("Titolo di esempio");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina le serie e le categorie generate di default
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
// Ora popolamento dei dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Impostazione del colore di riempimento per la serie
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Ora popolamento dei dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Impostazione del colore di riempimento per la serie
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

In questo tutorial abbiamo imparato a creare grafici normali in Java Slides utilizzando l'API Aspose.Slides per Java. Abbiamo seguito una guida passo passo con codice sorgente per creare un grafico a colonne cluster in una presentazione PowerPoint.

## Domande frequenti

### Come posso cambiare il tipo di grafico?

Per cambiare il tipo di grafico, modificare il `ChartType` parametro quando si aggiunge il grafico utilizzando `sld.getShapes().addChart()`Puoi scegliere tra i vari tipi di grafici disponibili in Aspose.Slides.

### Posso cambiare i colori delle serie di grafici?

Sì, puoi modificare i colori delle serie di grafici impostando il colore di riempimento per ciascuna serie utilizzando `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Come posso aggiungere altre categorie o serie al grafico?

È possibile aggiungere più categorie o serie al grafico aggiungendo nuovi punti dati ed etichette utilizzando `chart.getChartData().getCategories().add()` E `chart.getChartData().getSeries().add()` metodi.

### Come posso personalizzare ulteriormente il titolo del grafico?

È possibile personalizzare ulteriormente il titolo del grafico modificandone le proprietà `chart.getChartTitle()` come l'allineamento del testo, la dimensione del carattere e il colore.

### Come posso salvare il grafico in un formato di file diverso?

Per salvare il grafico in un formato di file diverso, modificare il `SaveFormat` parametro nel `pres.save()` metodo nel formato desiderato (ad esempio, PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}