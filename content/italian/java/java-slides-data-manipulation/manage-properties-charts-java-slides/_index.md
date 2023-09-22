---
title: Gestisci i grafici delle proprietà nelle diapositive Java
linktitle: Gestisci i grafici delle proprietà nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Impara a creare grafici straordinari e gestire le proprietà nelle diapositive Java con Aspose.Slides. Guida passo passo con codice sorgente per presentazioni potenti.
type: docs
weight: 13
url: /it/java/data-manipulation/manage-properties-charts-java-slides/
---

## Introduzione alla gestione di proprietà e grafici in Diapositive Java utilizzando Aspose.Slides

In questo tutorial esploreremo come gestire le proprietà e creare grafici nelle diapositive Java utilizzando Aspose.Slides. Aspose.Slides è una potente API Java per lavorare con presentazioni PowerPoint. Esamineremo il processo passo dopo passo, inclusi esempi di codice sorgente.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Aggiunta di un grafico a una diapositiva

Per aggiungere un grafico a una diapositiva, procedi nel seguente modo:

1. Importa le classi necessarie e crea un'istanza della classe Presentation.

```java
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```

2. Accedi alla diapositiva in cui desideri aggiungere il grafico. In questo esempio accediamo alla prima diapositiva.

```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Aggiungi un grafico con dati predefiniti. In questo caso, stiamo aggiungendo un grafico StackedColumn3D.

```java
// Aggiungi grafico con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Impostazione dei dati della mappa

Per impostare i dati del grafico, dobbiamo creare una cartella di lavoro dei dati del grafico e aggiungere serie e categorie. Segui questi passi:

4. Imposta l'indice della scheda grafica.

```java
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
```

5. Ottieni la cartella di lavoro dei dati del grafico.

```java
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Aggiungi serie al grafico. In questo esempio aggiungiamo due serie denominate "Serie 1" e "Serie 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Aggiungi categorie al grafico. Qui aggiungiamo tre categorie.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Impostazione delle proprietà di rotazione 3D

Ora impostiamo le proprietà di rotazione 3D per il grafico:

8. Impostare gli assi ad angolo retto.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Imposta gli angoli di rotazione per gli assi X e Y. In questo esempio ruotiamo X di 40 gradi e Y di 270 gradi.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Imposta la percentuale di profondità su 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Popolamento dei dati delle serie

11. Prendi la seconda serie di grafici e popolala con punti dati.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Popolare i dati della serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Regolazione della sovrapposizione

12. Imposta il valore di sovrapposizione per le serie. Ad esempio, puoi impostarlo su 100 per evitare sovrapposizioni.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Salvataggio della presentazione

Infine, salva la presentazione su disco.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai creato con successo un istogramma in pila 3D con proprietà personalizzate utilizzando Aspose.Slides in Java.

## Codice sorgente completo per gestire i grafici delle proprietà nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Aggiungi serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Aggiungi categorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Imposta le proprietà di rotazione 3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Prendi la seconda serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Imposta il valore di sovrapposizione
series.getParentSeriesGroup().setOverlap((byte) 100);
// Scrivi la presentazione su disco
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo approfondito il mondo della gestione delle proprietà e della creazione di grafici nelle diapositive Java utilizzando Aspose.Slides. Aspose.Slides è una solida API Java che consente agli sviluppatori di lavorare in modo efficiente con le presentazioni PowerPoint. Abbiamo coperto i passaggi essenziali e fornito esempi di codice sorgente per guidarti attraverso il processo.

## Domande frequenti

### Come posso cambiare il tipo di grafico?

 È possibile modificare il tipo di grafico modificando il file`ChartType`parametro quando si aggiunge il grafico. Fare riferimento alla documentazione di Aspose.Slides per i tipi di grafici disponibili.

### Posso personalizzare i colori del grafico?

Sì, puoi personalizzare i colori del grafico impostando le proprietà di riempimento dei punti dati o delle categorie delle serie.

### Come posso aggiungere più punti dati a una serie?

 È possibile aggiungere più punti dati a una serie utilizzando`series.getDataPoints().addDataPointForBarSeries()` metodo e specificando la cella contenente il valore dei dati.

### Come posso impostare un angolo di rotazione diverso?

 Per impostare un angolo di rotazione diverso per gli assi X e Y, utilizzare`chart.getRotation3D().setRotationX()` E`chart.getRotation3D().setRotationY()` con i valori angolari desiderati.

### Quali altre proprietà 3D posso personalizzare?

Puoi esplorare altre proprietà 3D del grafico, come profondità, prospettiva e illuminazione, facendo riferimento alla documentazione Aspose.Slides.