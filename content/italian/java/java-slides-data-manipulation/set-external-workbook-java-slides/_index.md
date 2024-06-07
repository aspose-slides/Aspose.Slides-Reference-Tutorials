---
title: Imposta la cartella di lavoro esterna nelle diapositive Java
linktitle: Imposta la cartella di lavoro esterna nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare cartelle di lavoro esterne in Java Slides utilizzando Aspose.Slides per Java. Crea presentazioni dinamiche con l'integrazione dei dati Excel.
type: docs
weight: 19
url: /it/java/data-manipulation/set-external-workbook-java-slides/
---

## Introduzione all'impostazione della cartella di lavoro esterna nelle diapositive Java

In questo tutorial esploreremo come impostare una cartella di lavoro esterna in Java Slides utilizzando Aspose.Slides. Imparerai come creare una presentazione PowerPoint con un grafico che fa riferimento ai dati di una cartella di lavoro Excel esterna. Al termine di questa guida avrai una chiara comprensione di come integrare i dati esterni nelle presentazioni di Presentazioni Java.

## Prerequisiti

Prima di approfondire l'implementazione, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
- Libreria Aspose.Slides per Java aggiunta al tuo progetto.
- Una cartella di lavoro di Excel con i dati a cui vuoi fare riferimento nella presentazione.

## Passaggio 1: crea una nuova presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Iniziamo creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides.

## Passaggio 2: aggiungi un grafico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Successivamente, inseriamo un grafico a torta nella presentazione. È possibile personalizzare il tipo e la posizione del grafico secondo necessità.

## Passaggio 3: accedere alla cartella di lavoro esterna

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Per accedere alla cartella di lavoro esterna, utilizziamo il file`setExternalWorkbook` metodo e fornire il percorso della cartella di lavoro di Excel contenente i dati.

## Passaggio 4: associa i dati del grafico

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Associamo il grafico ai dati della cartella di lavoro esterna specificando i riferimenti di cella per serie e categorie.

## Passaggio 5: salva la presentazione

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Infine, salviamo la presentazione con il riferimento alla cartella di lavoro esterna come file PowerPoint.

## Codice sorgente completo per impostare la cartella di lavoro esterna nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

In questo tutorial, abbiamo imparato come impostare una cartella di lavoro esterna in Java Slides utilizzando Aspose.Slides. Ora puoi creare presentazioni che fanno riferimento dinamicamente ai dati delle cartelle di lavoro di Excel, migliorando la flessibilità e l'interattività delle tue diapositive.

## Domande frequenti

### Come installo Aspose.Slides per Java?

Aspose.Slides per Java può essere installato aggiungendo la libreria al tuo progetto Java. È possibile scaricare la libreria dal sito Web Aspose e seguire le istruzioni di installazione fornite nella documentazione.

### Posso utilizzare tipi di grafici diversi con cartelle di lavoro esterne?

Sì, puoi utilizzare vari tipi di grafici supportati da Aspose.Slides e associarli ai dati di cartelle di lavoro esterne. Il processo può variare leggermente a seconda del tipo di grafico scelto.

### Cosa succede se la struttura dei dati della mia cartella di lavoro esterna cambia?

Se la struttura dei dati della cartella di lavoro esterna cambia, potrebbe essere necessario aggiornare i riferimenti di cella nel codice Java per garantire che i dati del grafico rimangano accurati.

### Aspose.Slides è compatibile con le ultime versioni Java?

Aspose.Slides per Java viene regolarmente aggiornato per garantire la compatibilità con le ultime versioni Java. Assicurati di controllare gli aggiornamenti e di utilizzare la versione più recente della libreria per prestazioni e compatibilità ottimali.

### Posso aggiungere più grafici che fanno riferimento alla stessa cartella di lavoro esterna?

Sì, puoi aggiungere più grafici alla tua presentazione, tutti facendo riferimento alla stessa cartella di lavoro esterna. Ripeti semplicemente i passaggi descritti in questo tutorial per ogni grafico che desideri creare.