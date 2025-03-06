---
title: Grafico multicategoria nelle diapositive Java
linktitle: Grafico multicategoria nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea grafici multicategoria in diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per una straordinaria visualizzazione dei dati nelle presentazioni.
weight: 20
url: /it/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Grafico multicategoria nelle diapositive Java


## Introduzione al grafico multicategoria nelle diapositive Java con Aspose.Slides

In questo tutorial impareremo come creare un grafico multicategoria nelle diapositive Java utilizzando l'API Aspose.Slides per Java. Questa guida fornirà istruzioni dettagliate insieme al codice sorgente per aiutarti a creare un istogramma in cluster con più categorie e serie.

## Prerequisiti
Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo ambiente di sviluppo Java.

## Passaggio 1: impostazione dell'ambiente
Innanzitutto, importa le classi necessarie e crea un nuovo oggetto Presentazione per lavorare con le diapositive.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiunta di una diapositiva e di un grafico
Successivamente, crea una diapositiva e aggiungi un istogramma in cluster.

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

Questo è tutto! Hai creato con successo un grafico multicategoria in una diapositiva Java utilizzando Aspose.Slides. È possibile personalizzare ulteriormente questo grafico per adattarlo alle proprie esigenze specifiche.

## Codice sorgente completo per grafico multicategoria in diapositive Java

```java
// Il percorso della directory dei documenti.
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
// Aggiunta di serie
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

In questo tutorial, abbiamo imparato come creare un grafico multicategoria nelle diapositive Java utilizzando l'API Aspose.Slides per Java. Abbiamo seguito una guida passo passo con il codice sorgente per creare un istogramma in cluster con più categorie e serie.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico?

È possibile personalizzare l'aspetto del grafico modificando proprietà quali colori, caratteri e stili. Fare riferimento alla documentazione di Aspose.Slides per le opzioni di personalizzazione dettagliate.

### Posso aggiungere più serie al grafico?

Sì, puoi aggiungere ulteriori serie al grafico seguendo una procedura simile a quella mostrata nel passaggio 5.

### Come posso cambiare il tipo di grafico?

 Per modificare il tipo di grafico, sostituisci`ChartType.ClusteredColumn` con il tipo di grafico desiderato quando si aggiunge il grafico al passaggio 2.

### Come posso aggiungere un titolo al grafico?

 Puoi aggiungere un titolo al grafico utilizzando il comando`ch.getChartTitle().getTextFrame().setText("Chart Title");` metodo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
