---
title: Imposta Inverti tabella colori di riempimento nelle diapositive Java
linktitle: Imposta Inverti tabella colori di riempimento nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare i colori di riempimento invertiti per i grafici di diapositive Java utilizzando Aspose.Slides. Migliora le tue visualizzazioni dei grafici con questa guida passo passo e il codice sorgente.
weight: 22
url: /it/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'impostazione della tabella dei colori di riempimento invertito nelle diapositive Java

In questo tutorial, dimostreremo come impostare il colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java. L'inversione del colore di riempimento è una funzionalità utile quando desideri evidenziare i valori negativi in un grafico con un colore specifico. Forniremo istruzioni dettagliate e codice sorgente per raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Aspose.Slides per la libreria Java installata.
2. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: crea una presentazione

Innanzitutto, dobbiamo creare una presentazione a cui aggiungere il nostro grafico. È possibile utilizzare il seguente codice per creare una presentazione:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico

Successivamente, aggiungeremo un istogramma in cluster alla presentazione. Ecco come puoi farlo:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Passaggio 3: impostare i dati del grafico

Ora impostiamo i dati del grafico, incluse serie e categorie:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Aggiunta di nuove serie e categorie
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Passaggio 4: popolare i dati della serie

Ora popoliamo i dati della serie per il grafico:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Passaggio 5: imposta Inverti colore di riempimento

Per impostare il colore di riempimento invertito per le serie di grafici, puoi utilizzare il seguente codice:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Nel codice sopra, impostiamo la serie per invertire il colore di riempimento per valori negativi e specifichiamo il colore per il riempimento invertito.

## Passaggio 6: salva la presentazione

Infine, salva la presentazione con il grafico:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per impostare la tabella dei colori di riempimento invertito nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Aggiunta di nuove serie e categorie
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Prendi la prima serie di grafici e popola i dati della serie.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, ti abbiamo mostrato come impostare il colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java. Questa funzione ti consente di evidenziare i valori negativi nei tuoi grafici con un colore specifico, rendendo i tuoi dati visivamente più informativi.

## Domande frequenti

In questa sezione, affronteremo alcune domande comuni relative all'impostazione del colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java.

### Come installo Aspose.Slides per Java?

 È possibile installare Aspose.Slides per Java includendo i file JAR Aspose.Slides nel progetto Java. È possibile scaricare la libreria da[Aspose.Slides per la pagina di download di Java](https://releases.aspose.com/slides/java/). Seguire le istruzioni di installazione fornite nella documentazione per il proprio ambiente di sviluppo specifico.

### Posso personalizzare il colore per il riempimento invertito nelle serie di grafici?

Sì, puoi personalizzare il colore per il riempimento invertito nelle serie di grafici. Nell'esempio di codice fornito, il`series.getInvertedSolidFillColor().setColor(Color.RED)` linea imposta il colore rosso per il riempimento invertito. Puoi sostituire`Color.RED` con qualsiasi altro colore a tua scelta.

### Come posso modificare il tipo di grafico in Aspose.Slides per Java?

 È possibile modificare il tipo di grafico modificando il file`ChartType` parametro quando si aggiunge un grafico alla presentazione. Nell'esempio di codice, abbiamo usato`ChartType.ClusteredColumn` . È possibile esplorare altri tipi di grafici come grafici a linee, grafici a barre, grafici a torta, ecc., specificando l'appropriato`ChartType` valore enum.

### Come faccio ad aggiungere più serie di dati a un grafico?

 Per aggiungere più serie di dati a un grafico, puoi utilizzare il file`chart.getChartData().getSeries().add(...)` per ogni serie che desideri aggiungere. Assicurati di fornire i punti dati e le etichette appropriati per ciascuna serie per popolare il tuo grafico con più serie.

### C'è un modo per personalizzare altri aspetti dell'aspetto del grafico?

Sì, puoi personalizzare vari aspetti dell'aspetto del grafico, incluse etichette degli assi, titoli, legende e altro utilizzando Aspose.Slides per Java. Fare riferimento alla documentazione per indicazioni dettagliate sulla personalizzazione degli elementi e dell'aspetto del grafico.

### Posso salvare il grafico in diversi formati?

 Sì, puoi salvare il grafico in diversi formati utilizzando Aspose.Slides per Java. Nell'esempio di codice fornito, abbiamo salvato la presentazione come file PPTX. Puoi usarne diversi`SaveFormat` opzioni per salvarlo in altri formati come PDF, PNG o SVG, a seconda delle tue esigenze.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
