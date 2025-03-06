---
title: Inverti se negativo per le singole serie nelle diapositive Java
linktitle: Inverti se negativo per le singole serie nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come utilizzare la funzione Inverti se negativo in Aspose.Slides per Java per migliorare le immagini dei grafici nelle presentazioni di PowerPoint.
weight: 11
url: /it/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Inverti se negativo per le singole serie nelle diapositive Java


## Introduzione a Inverti se negativo per le singole serie nelle diapositive Java

Aspose.Slides per Java fornisce potenti strumenti per lavorare con le presentazioni e una caratteristica interessante è la capacità di controllare il modo in cui le serie di dati vengono visualizzate sui grafici. In questo articolo esploreremo come utilizzare la funzione "Inverti se negativo" per le singole serie in Java Slides. Questa funzionalità ti consente di distinguere visivamente i punti dati negativi in un grafico, rendendo le tue presentazioni più informative e coinvolgenti.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Impostazione del tuo progetto

Per iniziare, crea un nuovo progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Una volta impostato il progetto, segui questi passaggi per implementare la funzione "Inverti se negativo" per le singole serie in Java Slides.

## Passaggio 1: includi la libreria Aspose.Slides

Innanzitutto, devi includere la libreria Aspose.Slides nel tuo progetto. Puoi farlo aggiungendo il file JAR della libreria al classpath del tuo progetto. Questo passaggio garantisce l'accesso a tutte le classi e i metodi necessari per lavorare con le presentazioni di PowerPoint.

```java
import com.aspose.slides.*;
```

## Passaggio 2: crea una presentazione

 Ora creiamo una nuova presentazione di PowerPoint utilizzando Aspose.Slides. Puoi definire la directory in cui desideri salvare la presentazione utilizzando il file`dataDir` variabile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 3: aggiungi un grafico

In questo passaggio, aggiungeremo un grafico alla presentazione. Utilizzeremo un istogramma a colonne raggruppate come esempio. Puoi scegliere diversi tipi di grafici in base alle tue esigenze.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Passaggio 4: configurare la serie di dati del grafico

Successivamente, configureremo le serie di dati del grafico. Per dimostrare la funzionalità "Inverti se negativo", creeremo un set di dati di esempio con valori sia positivi che negativi.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Aggiunta di punti dati alla serie
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Passaggio 5: applicare "Inverti se negativo"

Ora applicheremo la funzione "Inverti se negativo" a uno dei punti dati. Ciò invertirà visivamente il colore di quel punto dati specifico quando è negativo.

```java
series.get_Item(0).setInvertIfNegative(false); // Non invertire per impostazione predefinita
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Invertire il colore per il terzo punto dati
```

## Passaggio 6: salva la presentazione

Infine, salva la presentazione nella directory specificata.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per Inverti se negativo per le singole serie nelle diapositive Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare la funzione "Inverti se negativo" per le singole serie in Diapositive Java utilizzando Aspose.Slides per Java. Questa funzione ti consente di evidenziare i punti dati negativi nei tuoi grafici, rendendo le tue presentazioni visivamente più accattivanti e informative.

## Domande frequenti

### Qual è lo scopo della funzione "Inverti se negativo" in Aspose.Slides per Java?

La funzione "Inverti se negativo" in Aspose.Slides per Java consente di distinguere visivamente i punti dati negativi nei grafici. Aiuta a rendere le tue presentazioni più informative e coinvolgenti evidenziando punti dati specifici.

### Come posso includere la libreria Aspose.Slides nel mio progetto Java?

Per includere la libreria Aspose.Slides nel tuo progetto Java, devi aggiungere il file JAR della libreria al classpath del tuo progetto. Ciò ti consente di accedere a tutte le classi e i metodi necessari per lavorare con le presentazioni di PowerPoint.

### Posso utilizzare tipi di grafici diversi con la funzione "Inverti se negativo"?

Sì, puoi utilizzare diversi tipi di grafici con la funzione "Inverti se negativo". In questo tutorial abbiamo utilizzato come esempio un istogramma a colonne raggruppate, ma puoi applicare la funzionalità a vari tipi di grafici in base alle tue esigenze.

### È possibile personalizzare l'aspetto dei punti dati invertiti?

Sì, puoi personalizzare l'aspetto dei punti dati invertiti. Aspose.Slides per Java fornisce opzioni per controllare il colore e lo stile dei punti dati quando vengono invertiti a causa dell'impostazione "Inverti se negativo".

### Dove posso accedere alla documentazione Aspose.Slides per Java?

È possibile accedere alla documentazione per Aspose.Slides per Java all'indirizzo[Qui](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
