---
"description": "Impara a creare grafici a imbuto nelle presentazioni PowerPoint con Aspose.Slides per Java. Guida passo passo con codice sorgente per una visualizzazione efficace dei dati."
"linktitle": "Grafico a imbuto in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a imbuto in Java Slides"
"url": "/it/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a imbuto in Java Slides


## Introduzione alla creazione di un grafico a imbuto in Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico a imbuto in una presentazione PowerPoint utilizzando Aspose.Slides per Java. I grafici a imbuto sono utili per visualizzare i dati che si restringono progressivamente, o "imbuti", attraverso diverse fasi o categorie. Forniremo istruzioni dettagliate e il codice sorgente per aiutarti a raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Libreria Aspose.Slides per Java installata e configurata nel progetto.
- Un file di presentazione PowerPoint (PPTX) in cui si desidera inserire il grafico a imbuto.

## Passaggio 1: importare Aspose.Slides per Java

Per prima cosa, devi importare la libreria Aspose.Slides per Java nel tuo progetto Java. Assicurati di aver aggiunto le dipendenze necessarie alla configurazione della build.

```java
import com.aspose.slides.*;
```

## Passaggio 2: inizializzare la presentazione e il grafico

In questa fase inizializziamo una presentazione e aggiungiamo un grafico a imbuto a una diapositiva.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Aggiungere un grafico a imbuto alla prima diapositiva alle coordinate (50, 50) con dimensioni (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Passaggio 3: definire i dati del grafico

Successivamente, definiamo i dati per il nostro grafico a imbuto. Puoi personalizzare le categorie e i punti dati in base alle tue esigenze.

```java
// Cancella i dati esistenti del grafico.
wb.clear(0);

// Definisci le categorie per il grafico.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Aggiungere punti dati per la serie di grafici a imbuto.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Passaggio 4: salva la presentazione

Infine, salviamo la presentazione con il grafico a imbuto in un file specificato.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai creato con successo un grafico a imbuto utilizzando Aspose.Slides per Java e lo hai inserito in una presentazione PowerPoint.

## Codice sorgente completo per il grafico a imbuto in Java Slides

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusione

In questa guida passo passo, abbiamo illustrato come creare un grafico a imbuto in una presentazione PowerPoint utilizzando Aspose.Slides per Java. I grafici a imbuto sono uno strumento prezioso per visualizzare i dati che seguono uno schema progressivo o restringente, semplificando la trasmissione efficace delle informazioni. 

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico a imbuto?

È possibile personalizzare l'aspetto del grafico a imbuto modificando diverse proprietà del grafico, come colori, etichette e stili. Consultare la documentazione di Aspose.Slides per informazioni dettagliate sulle opzioni di personalizzazione dei grafici.

### Posso aggiungere altri punti dati o categorie al grafico a imbuto?

Sì, puoi aggiungere ulteriori punti dati e categorie al grafico a imbuto estendendo il codice fornito nel passaggio 3. Aggiungi semplicemente altre etichette di categoria e punti dati in base alle tue esigenze.

### Come posso modificare la posizione e le dimensioni del grafico a imbuto sulla diapositiva?

È possibile regolare la posizione e le dimensioni del grafico a imbuto modificando le coordinate e le dimensioni specificate quando si aggiunge il grafico alla diapositiva nel passaggio 2. Aggiornare i valori (50, 50, 500, 400) di conseguenza.

### Posso esportare il grafico in formati diversi, come PDF o immagine?

Sì, Aspose.Slides per Java consente di esportare la presentazione con il grafico a imbuto in vari formati, tra cui PDF, formati immagine e altro ancora. È possibile utilizzare `SaveFormat` opzioni per specificare il formato di output desiderato durante il salvataggio della presentazione.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}