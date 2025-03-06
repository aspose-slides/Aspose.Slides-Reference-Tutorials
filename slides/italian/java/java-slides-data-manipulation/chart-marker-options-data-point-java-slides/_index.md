---
title: Opzioni degli indicatori di grafico sul punto dati nelle diapositive Java
linktitle: Opzioni degli indicatori di grafico sul punto dati nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Ottimizza le tue diapositive Java con le opzioni dei marcatori di grafici personalizzati. Impara a migliorare visivamente i punti dati utilizzando Aspose.Slides per Java. Esplora la guida passo passo e le domande frequenti.
weight: 14
url: /it/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione alle opzioni degli indicatori di grafico sul punto dati nelle diapositive Java

Quando si tratta di creare presentazioni di grande impatto, la possibilità di personalizzare e manipolare gli indicatori del grafico sui punti dati può fare la differenza. Con Aspose.Slides per Java, hai il potere di trasformare i tuoi grafici in elementi dinamici e visivamente accattivanti.

## Prerequisiti

Prima di immergerci nella parte di codifica, assicurati di avere i seguenti prerequisiti:

- Ambiente di sviluppo Java
- Aspose.Slides per la libreria Java
- Un ambiente di sviluppo integrato Java (IDE)
- Documento di presentazione di esempio (ad esempio, "Test.pptx")

## Passaggio 1: impostazione dell'ambiente

Innanzitutto, assicurati di avere gli strumenti necessari installati e pronti. Crea un progetto Java nel tuo IDE e importa la libreria Aspose.Slides per Java.

## Passaggio 2: caricamento della presentazione

Per iniziare, carica il documento di presentazione di esempio. Nel codice fornito, presupponiamo che il documento sia denominato "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Passaggio 3: creazione di un grafico

Ora creiamo un grafico nella presentazione. In questo esempio utilizzeremo un grafico a linee con indicatori.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Passaggio 4: lavorare con i dati del grafico

Per manipolare i dati del grafico, dobbiamo accedere alla cartella di lavoro dei dati del grafico e preparare le serie di dati. Cancelleremo la serie predefinita e aggiungeremo i nostri dati personalizzati.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Passaggio 5: aggiunta di marcatori personalizzati

Ecco la parte entusiasmante: personalizzare gli indicatori sui punti dati. Utilizzeremo le immagini come marcatori in questo esempio.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aggiunta di marcatori personalizzati ai punti dati
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Ripetere per altri punti dati
// ...

// Modifica delle dimensioni dell'indicatore delle serie di grafici
series.getMarker().setSize(15);
```

## Passaggio 6: salvataggio della presentazione

Dopo aver personalizzato gli indicatori del grafico, salva la presentazione per vedere le modifiche in azione.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per le opzioni degli indicatori di grafico sul punto dati nelle diapositive Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Creazione del grafico predefinito
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Ottenere l'indice del foglio di lavoro dei dati del grafico predefinito
int defaultWorksheetIndex = 0;
//Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Elimina la serie demo
chart.getChartData().getSeries().clear();
//Aggiungi nuova serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Imposta l'immagine
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Imposta l'immagine
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Prendi la prima serie di grafici
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Aggiungi un nuovo punto (1:3) lì.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Modifica dell'indicatore della serie di grafici
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusione

Con Aspose.Slides per Java, puoi migliorare le tue presentazioni personalizzando gli indicatori del grafico sui punti dati. Ciò ti consente di creare diapositive visivamente sorprendenti e informative che affascinano il tuo pubblico.

## Domande frequenti

### Come posso modificare la dimensione dell'indicatore per i punti dati?

 Per modificare la dimensione dell'indicatore per i punti dati, utilizzare il comando`series.getMarker().setSize()` metodo e fornire la dimensione desiderata come argomento.

### Posso utilizzare le immagini come marcatori personalizzati?

 Sì, puoi utilizzare le immagini come indicatori personalizzati per i punti dati. Imposta il tipo di riempimento su`FillType.Picture` e fornisci l'immagine che desideri utilizzare.

### Aspose.Slides per Java è adatto per creare grafici dinamici?

Assolutamente! Aspose.Slides per Java offre ampie funzionalità per la creazione di grafici dinamici e interattivi nelle tue presentazioni.

### Posso personalizzare altri aspetti del grafico utilizzando Aspose.Slides?

Sì, puoi personalizzare vari aspetti del grafico, inclusi titoli, assi, etichette dati e altro, utilizzando Aspose.Slides per Java.

### Dove posso accedere alla documentazione e ai download di Aspose.Slides per Java?

 Puoi trovare la documentazione su[Qui](https://reference.aspose.com/slides/java/) e scarica la libreria su[Qui](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
