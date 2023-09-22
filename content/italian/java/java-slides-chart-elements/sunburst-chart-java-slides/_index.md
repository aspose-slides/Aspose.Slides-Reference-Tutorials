---
title: Grafico Sunburst nelle diapositive Java
linktitle: Grafico Sunburst nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea splendidi grafici Sunburst nelle diapositive Java con Aspose.Slides. Impara la creazione di grafici passo dopo passo e la manipolazione dei dati.
type: docs
weight: 16
url: /it/java/chart-elements/sunburst-chart-java-slides/
---

## Introduzione al grafico Sunburst in Java Slides con Aspose.Slides

In questo tutorial imparerai come creare un grafico Sunburst in una presentazione di PowerPoint utilizzando l'API Aspose.Slides per Java. Un grafico Sunburst è un grafico radiale utilizzato per rappresentare dati gerarchici. Forniremo istruzioni dettagliate insieme al codice sorgente.

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: importa le librerie richieste

Innanzitutto, importa le librerie necessarie per lavorare con Aspose.Slides e crea un grafico Sunburst nella tua applicazione Java.

```java
import com.aspose.slides.*;
```

## Passaggio 2: inizializzare la presentazione

Inizializza una presentazione PowerPoint e specifica la directory in cui verrà salvato il file di presentazione.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Passaggio 3: crea il grafico Sunburst

Crea un grafico Sunburst su una diapositiva. Specifichiamo la posizione (X, Y) e le dimensioni (larghezza, altezza) del grafico.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Passaggio 4: preparare i dati del grafico

Cancella tutte le categorie e i dati delle serie esistenti dal grafico e crea una cartella di lavoro dei dati per il grafico.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Passaggio 5: definire la gerarchia dei grafici

Definire la struttura gerarchica del grafico Sunburst. Puoi aggiungere rami, steli e foglie come categorie.

```java
// Ramo 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Ramo 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Passaggio 6: aggiungi dati al grafico

Aggiungi punti dati alla serie di grafici Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Passaggio 7: salva la presentazione

Infine, salva la presentazione con il grafico Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per il grafico Sunburst nelle diapositive Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//ramo 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//ramo 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come creare un grafico Sunburst in una presentazione di PowerPoint utilizzando l'API Aspose.Slides per Java. Hai visto come inizializzare la presentazione, creare il grafico, definire la gerarchia del grafico, aggiungere punti dati e salvare la presentazione. Ora puoi utilizzare queste conoscenze per creare grafici Sunburst interattivi e informativi nelle tue applicazioni Java.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico Sunburst?

È possibile personalizzare l'aspetto del grafico Sunburst modificando proprietà quali colori, etichette e stili. Fare riferimento alla documentazione di Aspose.Slides per le opzioni di personalizzazione dettagliate.

### Posso aggiungere più punti dati al grafico?

 Sì, puoi aggiungere più punti dati al grafico utilizzando il file`series.getDataPoints().addDataPointForSunburstSeries()` metodo per ciascun punto dati che desideri includere.

### Come posso aggiungere suggerimenti al grafico Sunburst?

Per aggiungere descrizioni comando al grafico Sunburst, puoi impostare il formato dell'etichetta dati per visualizzare informazioni aggiuntive, come valori o descrizioni, quando si passa con il mouse sui segmenti del grafico.

### È possibile creare grafici Sunburst interattivi con collegamenti ipertestuali?

Sì, puoi creare grafici Sunburst interattivi con collegamenti ipertestuali aggiungendo collegamenti ipertestuali a specifici elementi o segmenti del grafico. Fare riferimento alla documentazione di Aspose.Slides per i dettagli sull'aggiunta di collegamenti ipertestuali.