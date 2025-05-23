---
"description": "Migliora le tue presentazioni PowerPoint con Aspose.Slides per Java. Impara a modificare i grafici esistenti tramite codice. Guida passo passo con codice sorgente per la personalizzazione dei grafici."
"linktitle": "Grafico esistente in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico esistente in Java Slides"
"url": "/it/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico esistente in Java Slides


## Introduzione ai grafici esistenti in Java Slides utilizzando Aspose.Slides per Java

In questo tutorial, mostreremo come modificare un grafico esistente in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Illustreremo i passaggi per modificare i dati del grafico, i nomi delle categorie e delle serie e aggiungere una nuova serie al grafico. Assicuratevi di aver configurato Aspose.Slides per Java nel vostro progetto.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Libreria Aspose.Slides per Java inclusa nel tuo progetto.
2. Una presentazione PowerPoint esistente con un grafico che desideri modificare.
3. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: caricare la presentazione

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Passaggio 2: accedi alla diapositiva e al grafico

```java
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);

// Accedi al grafico sulla diapositiva
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Passaggio 3: modificare i dati del grafico e i nomi delle categorie

```java
// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Cambia i nomi delle categorie del grafico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Passaggio 4: aggiorna la prima serie di grafici

```java
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aggiorna il nome della serie
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Aggiorna i dati della serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Passaggio 5: aggiorna la seconda serie di grafici

```java
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Aggiorna il nome della serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Aggiorna i dati della serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Passaggio 6: aggiungere una nuova serie al grafico

```java
// Aggiungere una nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Prendiamo la terza serie di grafici
series = chart.getChartData().getSeries().get_Item(2);

// Popola i dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Passaggio 7: modifica il tipo di grafico

```java
// Cambia il tipo di grafico in Cilindro raggruppato
chart.setType(ChartType.ClusteredCylinder);
```

## Passaggio 8: salvare la presentazione modificata

```java
// Salva la presentazione con il grafico modificato
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai modificato con successo un grafico esistente in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Ora puoi utilizzare questo codice per personalizzare i grafici nelle tue presentazioni di PowerPoint a livello di codice.

## Codice sorgente completo per il grafico esistente in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX // Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Accedi al primo slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Modifica del nome della categoria del grafico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Aggiornamento dei dati della serie in corso
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modifica del nome della serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Aggiornamento dei dati della serie in corso
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modifica del nome della serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Ora, aggiungendo una nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Prendi la terza serie di grafici
series = chart.getChartData().getSeries().get_Item(2);
// Ora popolamento dei dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Salva la presentazione con il grafico
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusione

In questo tutorial completo, abbiamo imparato come modificare un grafico esistente in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Seguendo la guida passo passo e utilizzando esempi di codice sorgente, è possibile personalizzare e aggiornare facilmente i grafici in base alle proprie esigenze specifiche. Ecco un riepilogo di ciò che abbiamo trattato:

## Domande frequenti

### Come posso cambiare il tipo di grafico?

È possibile modificare il tipo di grafico utilizzando `chart.setType(ChartType.ChartTypeHere)` metodo. Sostituisci `ChartTypeHere` con il tipo di grafico desiderato, ad esempio `ChartType.ClusteredCylinder` nel nostro esempio.

### Posso aggiungere altri punti dati a una serie?

Sì, puoi aggiungere più punti dati a una serie utilizzando `series.getDataPoints().addDataPointForBarSeries(cell)` metodo. Assicurati di fornire i dati di cella appropriati.

### Come posso aggiornare i nomi delle categorie?

È possibile aggiornare i nomi delle categorie utilizzando `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` per impostare i nuovi nomi delle categorie.

### Come posso modificare i nomi delle serie?

Per modificare i nomi delle serie, utilizzare `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` per impostare i nuovi nomi delle serie.

### C'è un modo per rimuovere una serie dal grafico?

Sì, puoi rimuovere una serie dal grafico utilizzando `chart.getChartData().getSeries().removeAt(index)` metodo, dove `index` è l'indice della serie che vuoi rimuovere.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}