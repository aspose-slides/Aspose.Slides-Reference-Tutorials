---
title: Imposta la larghezza dello spazio nelle diapositive Java
linktitle: Imposta la larghezza dello spazio nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare la larghezza del gap nelle diapositive Java con Aspose.Slides per Java. Migliora la grafica dei grafici per le tue presentazioni PowerPoint.
weight: 21
url: /it/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la larghezza dello spazio nelle diapositive Java


## Introduzione all'impostazione della larghezza del gap in Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di impostazione della larghezza del gap per un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. La larghezza dello spazio determina la spaziatura tra le colonne o le barre in un grafico, consentendoti di controllare l'aspetto visivo del grafico.

## Prerequisiti

 Prima di iniziare, assicurati di aver installato la libreria Aspose.Slides per Java. Puoi scaricarlo dal sito Aspose[Qui](https://releases.aspose.com/slides/java/).

## Guida passo passo

Seguire questi passaggi per impostare la larghezza del gap in un grafico utilizzando Aspose.Slides per Java:

### 1. Crea una presentazione vuota

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
```

### 2. Accedi alla prima diapositiva

```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Aggiungi un grafico con dati predefiniti

```java
// Aggiungi un grafico con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Impostare l'indice del foglio dati del grafico

```java
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
```

### 5. Ottieni la cartella di lavoro dei dati del grafico

```java
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Aggiungi serie al grafico

```java
// Aggiungi serie al grafico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Aggiungi categorie al grafico

```java
// Aggiungi categorie al grafico
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Popolare i dati della serie

```java
// Popolare i dati della serie
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Popolamento dei punti dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Impostare la larghezza dello spazio

```java
// Imposta il valore della larghezza dello spazio
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Salva la presentazione

```java
// Salva la presentazione con il grafico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per impostare la larghezza dello spazio nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Aggiungi serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Aggiungi categorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Prendi la seconda serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Imposta il valore GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Salva la presentazione con il grafico
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, hai imparato come impostare la larghezza del gap per un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. La regolazione della larghezza dello spazio ti consente di controllare la spaziatura tra colonne o barre nel grafico, migliorando la rappresentazione visiva dei tuoi dati.

## Domande frequenti

### Come posso modificare il valore della larghezza dello spazio?

 Per modificare la larghezza dello spazio, utilizzare`setGapWidth` metodo sul`ParentSeriesGroup`della serie di grafici. Nell'esempio fornito, impostiamo la larghezza dello spazio su 50, ma puoi regolare questo valore in base alla spaziatura desiderata.

### Posso personalizzare altre proprietà del grafico?

Sì, Aspose.Slides per Java offre ampie funzionalità per la personalizzazione dei grafici. Puoi modificare varie proprietà del grafico, come colori, etichette, titoli e altro. Controlla il riferimento API per informazioni dettagliate sulle opzioni di personalizzazione del grafico.

### Dove posso trovare ulteriori risorse e documentazione?

 È possibile trovare documentazione completa e risorse aggiuntive su Aspose.Slides per Java nel[Sito web Aspose](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
