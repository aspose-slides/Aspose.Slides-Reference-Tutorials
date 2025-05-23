---
"description": "Scopri come impostare cartelle di lavoro esterne in Java Slides utilizzando Aspose.Slides per Java. Crea presentazioni dinamiche con l'integrazione dei dati Excel."
"linktitle": "Imposta cartella di lavoro esterna in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta cartella di lavoro esterna in Java Slides"
"url": "/it/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta cartella di lavoro esterna in Java Slides


## Introduzione all'impostazione di una cartella di lavoro esterna in Java Slides

In questo tutorial, esploreremo come impostare una cartella di lavoro esterna in Java Slides utilizzando Aspose.Slides. Imparerai a creare una presentazione PowerPoint con un grafico che fa riferimento ai dati di una cartella di lavoro Excel esterna. Al termine di questa guida, avrai una chiara comprensione di come integrare dati esterni nelle tue presentazioni Java Slides.

## Prerequisiti

Prima di addentrarci nell'implementazione, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- Libreria Aspose.Slides per Java aggiunta al tuo progetto.
- Una cartella di lavoro Excel con i dati a cui vuoi fare riferimento nella presentazione.

## Passaggio 1: creare una nuova presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Iniziamo creando una nuova presentazione PowerPoint utilizzando Aspose.Slides.

## Passaggio 2: aggiungere un grafico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Successivamente, inseriamo un grafico a torta nella presentazione. È possibile personalizzare il tipo e la posizione del grafico a seconda delle proprie esigenze.

## Passaggio 3: accedi alla cartella di lavoro esterna

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Per accedere alla cartella di lavoro esterna, utilizziamo il `setExternalWorkbook` metodo e fornire il percorso alla cartella di lavoro di Excel contenente i dati.

## Passaggio 4: associare i dati del grafico

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Colleghiamo il grafico ai dati della cartella di lavoro esterna specificando i riferimenti di cella per serie e categorie.

## Passaggio 5: Salva la presentazione

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Infine, salviamo la presentazione con il riferimento alla cartella di lavoro esterna come file PowerPoint.

## Codice sorgente completo per impostare una cartella di lavoro esterna in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial abbiamo imparato come impostare una cartella di lavoro esterna in Java Slides utilizzando Aspose.Slides. Ora puoi creare presentazioni che fanno riferimento dinamico ai dati delle cartelle di lavoro di Excel, migliorando la flessibilità e l'interattività delle tue diapositive.

## Domande frequenti

### Come faccio a installare Aspose.Slides per Java?

Aspose.Slides per Java può essere installato aggiungendo la libreria al proprio progetto Java. È possibile scaricare la libreria dal sito web di Aspose e seguire le istruzioni di installazione fornite nella documentazione.

### Posso utilizzare diversi tipi di grafici con cartelle di lavoro esterne?

Sì, puoi utilizzare diversi tipi di grafico supportati da Aspose.Slides e associarli ai dati di cartelle di lavoro esterne. Il processo può variare leggermente a seconda del tipo di grafico scelto.

### Cosa succede se la struttura dei dati della mia cartella di lavoro esterna cambia?

Se la struttura dei dati della cartella di lavoro esterna cambia, potrebbe essere necessario aggiornare i riferimenti alle celle nel codice Java per garantire che i dati del grafico rimangano accurati.

### Aspose.Slides è compatibile con le ultime versioni di Java?

Aspose.Slides per Java viene aggiornato regolarmente per garantire la compatibilità con le ultime versioni di Java. Assicuratevi di controllare gli aggiornamenti e di utilizzare la versione più recente della libreria per prestazioni e compatibilità ottimali.

### Posso aggiungere più grafici che fanno riferimento alla stessa cartella di lavoro esterna?

Sì, puoi aggiungere più grafici alla tua presentazione, tutti facenti riferimento alla stessa cartella di lavoro esterna. Ripeti semplicemente i passaggi descritti in questo tutorial per ogni grafico che desideri creare.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}