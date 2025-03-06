---
title: Colore automatico della serie di grafici nelle diapositive Java
linktitle: Colore automatico della serie di grafici nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare grafici dinamici con colori di serie automatici nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Migliora le visualizzazioni dei tuoi dati senza sforzo.
weight: 14
url: /it/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Colore automatico della serie di grafici nelle diapositive Java


## Introduzione al colore automatico delle serie di grafici in Aspose.Slides per Java

In questo tutorial esploreremo come creare una presentazione PowerPoint con un grafico utilizzando Aspose.Slides per Java e impostare i colori di riempimento automatico per le serie di grafici. I colori di riempimento automatico possono rendere i tuoi grafici visivamente più accattivanti e farti risparmiare tempo consentendo alla libreria di scegliere i colori per te.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: crea una nuova presentazione

Per prima cosa creeremo una nuova presentazione PowerPoint e vi aggiungeremo una diapositiva.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi un grafico alla diapositiva

Successivamente, aggiungeremo un istogramma in cluster alla diapositiva. Imposteremo anche la prima serie in modo che mostri i valori.

```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Passaggio 3: popolare i dati del grafico

Ora popoleremo il grafico con i dati. Inizieremo eliminando le serie e le categorie generate predefinite, quindi aggiungeremo nuove serie e categorie.

```java
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

## Passaggio 4: popolare i dati della serie

Popoleremo i dati della serie sia per la Serie 1 che per la Serie 2.

```java
// Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Prendi la seconda serie di grafici
series = chart.getChartData().getSeries().get_Item(1);
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Passaggio 5: imposta il colore di riempimento automatico per le serie

Ora impostiamo i colori di riempimento automatico per le serie di grafici. Questo farà sì che la biblioteca scelga i colori per noi.

```java
// Impostazione del colore di riempimento automatico per le serie
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Passaggio 6: salva la presentazione

Infine, salveremo la presentazione con il grafico in un file PowerPoint.

```java
// Salva la presentazione con il grafico
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per il colore della serie di grafici automatici nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
try
{
	// Accedi alla prima diapositiva
	ISlide slide = presentation.getSlides().get_Item(0);
	// Aggiungi grafico con dati predefiniti
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Ora popolano i dati delle serie
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Impostazione del colore di riempimento automatico per le serie
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Prendi la seconda serie di grafici
	series = chart.getChartData().getSeries().get_Item(1);
	// Ora popolano i dati delle serie
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Impostazione del colore di riempimento per le serie
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Salva la presentazione con il grafico
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato come creare una presentazione PowerPoint con un grafico utilizzando Aspose.Slides per Java e impostare i colori di riempimento automatico per le serie di grafici. I colori automatici possono migliorare l'attrattiva visiva dei tuoi grafici e rendere le tue presentazioni più coinvolgenti. È possibile personalizzare ulteriormente il grafico in base alle esigenze specifiche.

## Domande frequenti

### Come posso impostare i colori di riempimento automatico per le serie di grafici in Aspose.Slides per Java?

Per impostare i colori di riempimento automatico per le serie di grafici in Aspose.Slides per Java, utilizzare il seguente codice:

```java
// Impostazione del colore di riempimento automatico per le serie
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Questo codice consentirà alla libreria di scegliere automaticamente i colori per le serie di grafici.

### Posso personalizzare i colori del grafico, se necessario?

 Sì, puoi personalizzare i colori del grafico secondo necessità. Nell'esempio fornito abbiamo utilizzato i colori di riempimento automatici, ma puoi impostare colori specifici modificando il file`FillType` E`SolidFillColor` proprietà del formato della serie.

### Come posso aggiungere ulteriori serie o categorie al grafico?

 Per aggiungere ulteriori serie o categorie al grafico, utilizzare il file`getSeries()` E`getCategories()` metodi del grafico`ChartData` oggetto. Puoi aggiungere nuove serie e categorie specificandone i dati e le etichette.

### È possibile formattare ulteriormente il grafico e le etichette?

Sì, puoi formattare ulteriormente il grafico, le serie e le etichette secondo necessità. Aspose.Slides per Java offre ampie opzioni di formattazione per i grafici, inclusi caratteri, colori, stili e altro. Puoi esplorare la documentazione per maggiori dettagli sulle opzioni di formattazione.

### Dove posso trovare ulteriori informazioni su come lavorare con Aspose.Slides per Java?

 Per ulteriori informazioni e documentazione dettagliata su Aspose.Slides per Java, è possibile visitare la documentazione di riferimento[Qui](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
