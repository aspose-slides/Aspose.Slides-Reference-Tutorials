---
"description": "Scopri come utilizzare la funzionalità Inverti se negativo in Aspose.Slides per Java per migliorare gli elementi visivi dei grafici nelle presentazioni di PowerPoint."
"linktitle": "Inverti se negativo per singole serie in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Inverti se negativo per singole serie in Java Slides"
"url": "/it/java/data-manipulation/invert-if-negative-individual-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Inverti se negativo per singole serie in Java Slides


## Introduzione a Inverti se negativo per singole serie in Java Slides

Aspose.Slides per Java offre potenti strumenti per lavorare con le presentazioni, e una caratteristica interessante è la possibilità di controllare la visualizzazione delle serie di dati nei grafici. In questo articolo, esploreremo come utilizzare la funzione "Inverti se negativo" per singole serie in Java Slides. Questa funzione consente di distinguere visivamente i punti dati negativi in un grafico, rendendo le presentazioni più informative e coinvolgenti.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Impostazione del progetto

Per iniziare, crea un nuovo progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Una volta configurato il progetto, segui questi passaggi per implementare la funzione "Inverti se negativo" per le singole serie in Java Slides.

## Passaggio 1: includere la libreria Aspose.Slides

Per prima cosa, devi includere la libreria Aspose.Slides nel tuo progetto. Puoi farlo aggiungendo il file JAR della libreria al classpath del progetto. Questo passaggio garantisce l'accesso a tutte le classi e i metodi necessari per lavorare con le presentazioni di PowerPoint.

```java
import com.aspose.slides.*;
```

## Passaggio 2: creare una presentazione

Ora creiamo una nuova presentazione PowerPoint utilizzando Aspose.Slides. Puoi definire la directory in cui desideri salvare la presentazione utilizzando `dataDir` variabile.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 3: aggiungere un grafico

In questa fase, aggiungeremo un grafico alla presentazione. Useremo un grafico a colonne raggruppate come esempio. Puoi scegliere diversi tipi di grafico in base alle tue esigenze.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Passaggio 4: configurare la serie di dati del grafico

Successivamente, configureremo la serie di dati del grafico. Per dimostrare la funzione "Inverti se negativo", creeremo un set di dati di esempio con valori sia positivi che negativi.

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

Ora applicheremo la funzione "Inverti se negativo" a uno dei punti dati. Questo invertirà visivamente il colore di quel punto dati specifico quando è negativo.

```java
series.get_Item(0).setInvertIfNegative(false); // Non invertire per impostazione predefinita
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Inverti il colore per il terzo punto dati
```

## Passaggio 6: Salva la presentazione

Infine, salva la presentazione nella directory specificata.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per invertire se negativo per singole serie in Java Slides

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

In questo tutorial, abbiamo imparato a utilizzare la funzione "Inverti se negativo" per singole serie in Java Slides utilizzando Aspose.Slides per Java. Questa funzione consente di evidenziare i punti dati negativi nei grafici, rendendo le presentazioni visivamente più accattivanti e informative.

## Domande frequenti

### Qual è lo scopo della funzionalità "Inverti se negativo" in Aspose.Slides per Java?

La funzionalità "Inverti se negativo" di Aspose.Slides per Java consente di distinguere visivamente i punti dati negativi nei grafici. Contribuisce a rendere le presentazioni più informative e coinvolgenti evidenziando punti dati specifici.

### Come posso includere la libreria Aspose.Slides nel mio progetto Java?

Per includere la libreria Aspose.Slides nel tuo progetto Java, devi aggiungere il file JAR della libreria al classpath del progetto. Questo ti permetterà di accedere a tutte le classi e i metodi necessari per lavorare con le presentazioni di PowerPoint.

### Posso utilizzare diversi tipi di grafico con la funzione "Inverti se negativo"?

Sì, puoi utilizzare diversi tipi di grafico con la funzione "Inverti se negativo". In questo tutorial, abbiamo utilizzato un istogramma a colonne raggruppate come esempio, ma puoi applicare la funzione a diversi tipi di grafico in base alle tue esigenze.

### È possibile personalizzare l'aspetto dei punti dati invertiti?

Sì, è possibile personalizzare l'aspetto dei punti dati invertiti. Aspose.Slides per Java offre opzioni per controllare il colore e lo stile dei punti dati quando sono invertiti grazie all'impostazione "Inverti se negativo".

### Dove posso accedere alla documentazione di Aspose.Slides per Java?

È possibile accedere alla documentazione per Aspose.Slides per Java all'indirizzo [Qui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}