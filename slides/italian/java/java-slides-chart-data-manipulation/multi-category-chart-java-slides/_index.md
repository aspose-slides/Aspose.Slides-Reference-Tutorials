---
"description": "Crea grafici multicategoria in Java Slides utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per una visualizzazione dei dati efficace nelle presentazioni."
"linktitle": "Grafico multicategoria in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico multicategoria in Java Slides"
"url": "/it/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico multicategoria in Java Slides


## Introduzione ai grafici multicategoria in Java Slides con Aspose.Slides

In questo tutorial impareremo a creare un grafico multicategoria in Java Slides utilizzando l'API Aspose.Slides per Java. Questa guida fornirà istruzioni dettagliate e il codice sorgente per aiutarti a creare un grafico a colonne cluster con più categorie e serie.

## Prerequisiti
Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo ambiente di sviluppo Java.

## Fase 1: Impostazione dell'ambiente
Per prima cosa, importa le classi necessarie e crea un nuovo oggetto Presentazione per lavorare con le diapositive.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiunta di una diapositiva e di un grafico
Successivamente, crea una diapositiva e aggiungi un grafico a colonne raggruppate.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Passaggio 3: cancellazione dei dati esistenti
Cancella tutti i dati esistenti dal grafico.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Passaggio 4: impostazione delle categorie di dati
Ora impostiamo le categorie di dati per il grafico. Creeremo più categorie e le raggrupperemo.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Aggiungi categorie e raggruppale
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Passaggio 5: aggiunta di serie
Ora aggiungiamo una serie al grafico insieme ai punti dati.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Passaggio 6: salvataggio della presentazione
Infine, salva la presentazione con il grafico.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai creato con successo un grafico multicategoria in una diapositiva Java utilizzando Aspose.Slides. Puoi personalizzare ulteriormente questo grafico in base alle tue esigenze specifiche.

## Codice sorgente completo per grafici multicategoria in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Aggiunta di serie
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Salva la presentazione con il grafico
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial abbiamo imparato a creare un grafico multicategoria in Java Slides utilizzando l'API Aspose.Slides per Java. Abbiamo seguito una guida passo passo con codice sorgente per creare un grafico a colonne cluster con più categorie e serie.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico?

È possibile personalizzare l'aspetto del grafico modificando proprietà come colori, caratteri e stili. Consultare la documentazione di Aspose.Slides per informazioni dettagliate sulle opzioni di personalizzazione.

### Posso aggiungere altre serie al grafico?

Sì, puoi aggiungere altre serie al grafico seguendo una procedura simile a quella mostrata nel passaggio 5.

### Come faccio a cambiare il tipo di grafico?

Per cambiare il tipo di grafico, sostituisci `ChartType.ClusteredColumn` con il tipo di grafico desiderato quando si aggiunge il grafico nel passaggio 2.

### Come posso aggiungere un titolo al grafico?

È possibile aggiungere un titolo al grafico utilizzando `ch.getChartTitle().getTextFrame().setText("Chart Title");` metodo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}