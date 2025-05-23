---
"description": "Scopri come impostare colori di riempimento invertiti per i grafici Java Slides utilizzando Aspose.Slides. Migliora le visualizzazioni dei tuoi grafici con questa guida passo passo e il codice sorgente."
"linktitle": "Imposta il grafico dei colori di riempimento invertito nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta il grafico dei colori di riempimento invertito nelle diapositive Java"
"url": "/it/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il grafico dei colori di riempimento invertito nelle diapositive Java


## Introduzione al grafico dei colori di riempimento invertito in Java Slides

In questo tutorial, mostreremo come impostare il colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java. L'inversione del colore di riempimento è una funzionalità utile quando si desidera evidenziare i valori negativi in un grafico con un colore specifico. Forniremo istruzioni dettagliate e il codice sorgente per ottenere questo risultato.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Libreria Aspose.Slides per Java installata.
2. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: creare una presentazione

Per prima cosa, dobbiamo creare una presentazione a cui aggiungere il nostro grafico. Puoi usare il seguente codice per creare una presentazione:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico

Successivamente, aggiungeremo un grafico a colonne raggruppate alla presentazione. Ecco come fare:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Passaggio 3: impostare i dati del grafico

Ora impostiamo i dati del grafico, incluse le serie e le categorie:

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

Adesso, popoliamo i dati della serie per il grafico:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Passaggio 5: imposta il colore di riempimento invertito

Per impostare il colore di riempimento invertito per la serie di grafici, puoi utilizzare il seguente codice:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Nel codice sopra, impostiamo la serie per invertire il colore di riempimento per i valori negativi e specifichiamo il colore per il riempimento invertito.

## Passaggio 6: Salva la presentazione

Infine, salva la presentazione con il grafico:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per il grafico dei colori di riempimento invertito in Java Slides

```java
// Percorso verso la directory dei documenti.
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
// Prendiamo prima la serie di grafici e i dati della serie di popolamento.
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

In questo tutorial, vi abbiamo mostrato come impostare il colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java. Questa funzione vi permette di evidenziare i valori negativi nei grafici con un colore specifico, rendendo i dati visivamente più informativi.

## Domande frequenti

In questa sezione risponderemo ad alcune domande comuni relative all'impostazione del colore di riempimento invertito per un grafico in Java Slides utilizzando Aspose.Slides per Java.

### Come faccio a installare Aspose.Slides per Java?

Puoi installare Aspose.Slides per Java includendo i file JAR di Aspose.Slides nel tuo progetto Java. Puoi scaricare la libreria da [Pagina di download di Aspose.Slides per Java](https://releases.aspose.com/slides/java/)Seguire le istruzioni di installazione fornite nella documentazione relativa al proprio specifico ambiente di sviluppo.

### Posso personalizzare il colore per il riempimento invertito nella serie di grafici?

Sì, puoi personalizzare il colore del riempimento invertito nella serie di grafici. Nell'esempio di codice fornito, `series.getInvertedSolidFillColor().setColor(Color.RED)` la linea imposta il colore rosso per il riempimento invertito. Puoi sostituire `Color.RED` con qualsiasi altro colore a tua scelta.

### Come posso modificare il tipo di grafico in Aspose.Slides per Java?

È possibile modificare il tipo di grafico modificando il `ChartType` parametro quando si aggiunge un grafico alla presentazione. Nell'esempio di codice, abbiamo usato `ChartType.ClusteredColumn`È possibile esplorare altri tipi di grafici come grafici a linee, grafici a barre, grafici a torta, ecc., specificando l'appropriato `ChartType` valore enum.

### Come faccio ad aggiungere più serie di dati a un grafico?

Per aggiungere più serie di dati a un grafico, puoi utilizzare `chart.getChartData().getSeries().add(...)` metodo per ogni serie che desideri aggiungere. Assicurati di fornire i punti dati e le etichette appropriati per ogni serie per popolare il grafico con più serie.

### C'è un modo per personalizzare altri aspetti dell'aspetto del grafico?

Sì, puoi personalizzare vari aspetti dell'aspetto del grafico, tra cui etichette degli assi, titoli, legende e altro ancora, utilizzando Aspose.Slides per Java. Consulta la documentazione per istruzioni dettagliate sulla personalizzazione degli elementi e dell'aspetto del grafico.

### Posso salvare il grafico in formati diversi?

Sì, puoi salvare il grafico in diversi formati utilizzando Aspose.Slides per Java. Nell'esempio di codice fornito, abbiamo salvato la presentazione come file PPTX. Puoi utilizzare diversi formati. `SaveFormat` opzioni per salvarlo in altri formati come PDF, PNG o SVG, a seconda delle tue esigenze.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}