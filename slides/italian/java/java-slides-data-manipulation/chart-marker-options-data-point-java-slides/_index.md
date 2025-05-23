---
"description": "Ottimizza le tue diapositive Java con le opzioni di marcatura dei grafici personalizzati. Impara a migliorare visivamente i punti dati utilizzando Aspose.Slides per Java. Esplora la guida passo passo e le FAQ."
"linktitle": "Opzioni dei marcatori del grafico sui punti dati nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Opzioni dei marcatori del grafico sui punti dati nelle diapositive Java"
"url": "/it/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opzioni dei marcatori del grafico sui punti dati nelle diapositive Java


## Introduzione alle opzioni dei marcatori dei grafici sui punti dati nelle diapositive Java

Quando si tratta di creare presentazioni d'impatto, la possibilità di personalizzare e manipolare i marcatori dei grafici sui punti dati può fare la differenza. Con Aspose.Slides per Java, hai la possibilità di trasformare i tuoi grafici in elementi dinamici e visivamente accattivanti.

## Prerequisiti

Prima di addentrarci nella parte di codifica, assicurati di avere i seguenti prerequisiti:

- Ambiente di sviluppo Java
- Libreria Aspose.Slides per Java
- Un ambiente di sviluppo integrato Java (IDE)
- Esempio di documento di presentazione (ad esempio, "Test.pptx")

## Fase 1: Impostazione dell'ambiente

Innanzitutto, assicurati di avere gli strumenti necessari installati e pronti. Crea un progetto Java nel tuo IDE e importa la libreria Aspose.Slides per Java.

## Passaggio 2: caricamento della presentazione

Per iniziare, carica il tuo documento di presentazione di esempio. Nel codice fornito, ipotizziamo che il documento si chiami "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Passaggio 3: creazione di un grafico

Ora creiamo un grafico nella presentazione. In questo esempio useremo un grafico a linee con indicatori.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Passaggio 4: lavorare con i dati del grafico

Per manipolare i dati del grafico, dobbiamo accedere alla cartella di lavoro dei dati del grafico e preparare la serie di dati. Elimineremo la serie predefinita e aggiungeremo i nostri dati personalizzati.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Passaggio 5: aggiunta di marcatori personalizzati

Ora arriva la parte interessante: personalizzare i marcatori sui punti dati. In questo esempio useremo le immagini come marcatori.

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

// Modifica della dimensione del marcatore della serie del grafico
series.getMarker().setSize(15);
```

## Passaggio 6: salvataggio della presentazione

Dopo aver personalizzato i marcatori del grafico, salva la presentazione per vedere i cambiamenti in azione.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per le opzioni dei marcatori dei grafici sui punti dati nelle diapositive Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Creazione del grafico predefinito
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Ottenere l'indice predefinito del foglio di lavoro dei dati del grafico
int defaultWorksheetIndex = 0;
//Ottenere il foglio di lavoro dei dati del grafico
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
//Aggiungere un nuovo punto (1:3) qui.
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
//Modifica del marcatore della serie del grafico
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusione

Con Aspose.Slides per Java, puoi arricchire le tue presentazioni personalizzando i marcatori dei grafici sui punti dati. Questo ti permette di creare slide visivamente accattivanti e informative che catturano l'attenzione del pubblico.

## Domande frequenti

### Come posso modificare la dimensione del marcatore per i punti dati?

Per modificare la dimensione del marcatore per i punti dati, utilizzare `series.getMarker().setSize()` metodo e fornire la dimensione desiderata come argomento.

### Posso usare le immagini come marcatori personalizzati?

Sì, puoi utilizzare le immagini come marcatori personalizzati per i punti dati. Imposta il tipo di riempimento su `FillType.Picture` e fornisci l'immagine che vuoi utilizzare.

### Aspose.Slides per Java è adatto alla creazione di grafici dinamici?

Assolutamente sì! Aspose.Slides per Java offre ampie funzionalità per la creazione di grafici dinamici e interattivi nelle tue presentazioni.

### Posso personalizzare altri aspetti del grafico utilizzando Aspose.Slides?

Sì, puoi personalizzare vari aspetti del grafico, tra cui titoli, assi, etichette dati e altro ancora, utilizzando Aspose.Slides per Java.

### Dove posso accedere alla documentazione e ai download di Aspose.Slides per Java?

Puoi trovare la documentazione su [Qui](https://reference.aspose.com/slides/java/) e scarica la libreria su [Qui](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}