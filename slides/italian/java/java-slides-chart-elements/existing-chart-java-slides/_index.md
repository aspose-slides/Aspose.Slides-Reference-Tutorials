---
title: Grafico esistente nelle diapositive Java
linktitle: Grafico esistente nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Migliora le tue presentazioni PowerPoint con Aspose.Slides per Java. Impara a modificare i grafici esistenti a livello di codice. Guida passo passo con codice sorgente per la personalizzazione del grafico.
weight: 12
url: /it/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Grafico esistente nelle diapositive Java


## Introduzione al grafico esistente nelle diapositive Java utilizzando Aspose.Slides per Java

In questo tutorial, dimostreremo come modificare un grafico esistente in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Seguiremo i passaggi per modificare i dati del grafico, i nomi delle categorie, i nomi delle serie e aggiungere una nuova serie al grafico. Assicurati di avere Aspose.Slides per Java impostato nel tuo progetto.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Aspose.Slides per la libreria Java inclusa nel tuo progetto.
2. Una presentazione PowerPoint esistente con un grafico che desideri modificare.
3. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: caricare la presentazione

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Passaggio 2: accedi alla diapositiva e al grafico

```java
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);

// Accedi al grafico sulla diapositiva
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Passaggio 3: modifica i dati del grafico e i nomi delle categorie

```java
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Modifica i nomi delle categorie del grafico
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
// Prendiamo la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);

// Aggiorna il nome della serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Aggiorna i dati della serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Passaggio 6: aggiungi una nuova serie al grafico

```java
// Aggiunta di una nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Prendi la terza serie di grafici
series = chart.getChartData().getSeries().get_Item(2);

// Popolare i dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Passaggio 7: modifica il tipo di grafico

```java
//Modificare il tipo di grafico in Cilindro cluster
chart.setType(ChartType.ClusteredCylinder);
```

## Passaggio 8: salva la presentazione modificata

```java
// Salva la presentazione con il grafico modificato
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Congratulazioni! Hai modificato con successo un grafico esistente in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. È ora possibile utilizzare questo codice per personalizzare i grafici nelle presentazioni di PowerPoint a livello di codice.

## Codice sorgente completo per il grafico esistente nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Istanzia la classe di presentazione che rappresenta il file PPTX// Istanzia la classe di presentazione che rappresenta il file PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Accedi al primo slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Modifica del nome della categoria del grafico
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ora aggiorniamo i dati della serie
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modifica del nome della serie
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Ora aggiorniamo i dati della serie
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modifica del nome della serie
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Ora, aggiunta di una nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Prendi la terza serie di grafici
series = chart.getChartData().getSeries().get_Item(2);
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Salva la presentazione con il grafico
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusione

In questo tutorial completo, abbiamo imparato come modificare un grafico esistente in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Seguendo la guida passo passo e utilizzando esempi di codice sorgente, puoi personalizzare e aggiornare facilmente i grafici per soddisfare le tue esigenze specifiche. Ecco un riepilogo di ciò che abbiamo trattato:

## Domande frequenti

### Come posso cambiare il tipo di grafico?

 È possibile modificare il tipo di grafico utilizzando il file`chart.setType(ChartType.ChartTypeHere)` metodo. Sostituire`ChartTypeHere` con il tipo di grafico desiderato, ad esempio`ChartType.ClusteredCylinder` nel nostro esempio.

### Posso aggiungere più punti dati a una serie?

 Sì, puoi aggiungere più punti dati a una serie utilizzando il file`series.getDataPoints().addDataPointForBarSeries(cell)` metodo. Assicurati di fornire i dati della cella appropriati.

### Come faccio ad aggiornare i nomi delle categorie?

 È possibile aggiornare i nomi delle categorie utilizzando`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` per impostare i nuovi nomi di categoria.

### Come posso modificare i nomi delle serie?

 Per modificare i nomi delle serie, utilizzare`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` per impostare i nomi delle nuove serie.

### C'è un modo per rimuovere una serie dal grafico?

 Sì, puoi rimuovere una serie dal grafico utilizzando il comando`chart.getChartData().getSeries().removeAt(index)` metodo, dove`index`è l'indice della serie che vuoi rimuovere.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
