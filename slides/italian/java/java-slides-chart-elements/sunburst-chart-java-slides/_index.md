---
"description": "Crea splendidi grafici a raggiera in Java Slides con Aspose.Slides. Impara passo dopo passo come creare grafici e manipolare i dati."
"linktitle": "Grafico a raggiera in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a raggiera in Java Slides"
"url": "/it/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a raggiera in Java Slides


## Introduzione al grafico a raggiera in Java Slides con Aspose.Slides

In questo tutorial imparerai a creare un grafico a raggiera in una presentazione PowerPoint utilizzando l'API Aspose.Slides per Java. Un grafico a raggiera è un grafico radiale utilizzato per rappresentare dati gerarchici. Forniremo istruzioni dettagliate insieme al codice sorgente.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: importare le librerie richieste

Per prima cosa, importa le librerie necessarie per lavorare con Aspose.Slides e crea un grafico Sunburst nella tua applicazione Java.

```java
import com.aspose.slides.*;
```

## Passaggio 2: inizializzare la presentazione

Inizializza una presentazione PowerPoint e specifica la directory in cui verrà salvato il file della presentazione.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Passaggio 3: creare il grafico a raggiera

Creiamo un grafico a raggiera su una diapositiva. Specifichiamo la posizione (X, Y) e le dimensioni (larghezza, altezza) del grafico.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Passaggio 4: preparare i dati del grafico

Cancellare dal grafico tutte le categorie e le serie di dati esistenti e creare una cartella di lavoro dati per il grafico.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Passaggio 5: definire la gerarchia del grafico

Definisci la struttura gerarchica del grafico Sunburst. Puoi aggiungere rami, steli e foglie come categorie.

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

## Passaggio 6: aggiungere dati al grafico

Aggiungere punti dati alla serie di grafici Sunburst.

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

## Passaggio 7: Salva la presentazione

Infine, salva la presentazione con il grafico Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per il grafico a raggiera in Java Slides

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

In questo tutorial, hai imparato a creare un grafico Sunburst in una presentazione di PowerPoint utilizzando l'API Aspose.Slides per Java. Hai visto come inizializzare la presentazione, creare il grafico, definire la gerarchia dei grafici, aggiungere punti dati e salvare la presentazione. Ora puoi utilizzare queste conoscenze per creare grafici Sunburst interattivi e informativi nelle tue applicazioni Java.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico Sunburst?

È possibile personalizzare l'aspetto del grafico Sunburst modificando proprietà come colori, etichette e stili. Consultare la documentazione di Aspose.Slides per informazioni dettagliate sulle opzioni di personalizzazione.

### Posso aggiungere altri punti dati al grafico?

Sì, puoi aggiungere più punti dati al grafico utilizzando `series.getDataPoints().addDataPointForSunburstSeries()` metodo per ogni punto dati che vuoi includere.

### Come posso aggiungere suggerimenti al grafico Sunburst?

Per aggiungere suggerimenti al grafico Sunburst, è possibile impostare il formato dell'etichetta dati in modo da visualizzare informazioni aggiuntive, come valori o descrizioni, quando si passa il mouse sui segmenti del grafico.

### È possibile creare grafici Sunburst interattivi con collegamenti ipertestuali?

Sì, è possibile creare grafici Sunburst interattivi con collegamenti ipertestuali aggiungendoli a specifici elementi o segmenti del grafico. Consultare la documentazione di Aspose.Slides per dettagli sull'aggiunta di collegamenti ipertestuali.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}