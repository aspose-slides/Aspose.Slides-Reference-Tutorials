---
"description": "Scopri come creare grafici a torta spettacolari nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per sviluppatori Java."
"linktitle": "Grafico a torta in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a torta in Java Slides"
"url": "/it/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a torta in Java Slides


## Introduzione alla creazione di un grafico a torta in Java Slides utilizzando Aspose.Slides

In questo tutorial, mostreremo come creare un grafico a torta in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Ti forniremo istruzioni dettagliate e il codice sorgente Java per aiutarti a iniziare. Questa guida presuppone che tu abbia già configurato il tuo ambiente di sviluppo con Aspose.Slides per Java.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: importare le librerie richieste

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Assicurati di importare le classi necessarie dalla libreria Aspose.Slides.

## Passaggio 2: inizializzare la presentazione

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
```

Crea un nuovo oggetto Presentazione per rappresentare il tuo file PowerPoint. Sostituisci `"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.

## Passaggio 3: aggiungere una diapositiva

```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

Prendi la prima diapositiva della presentazione in cui vuoi aggiungere il grafico a torta.

## Passaggio 4: aggiungere un grafico a torta

```java
// Aggiungi un grafico a torta con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Aggiungere un grafico a torta alla diapositiva nella posizione e nelle dimensioni specificate.

## Passaggio 5: imposta il titolo del grafico

```java
// Imposta il titolo del grafico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Imposta un titolo per il grafico a torta. Puoi personalizzare il titolo a seconda delle tue esigenze.

## Passaggio 6: personalizzare i dati del grafico

```java
// Imposta la prima serie per mostrare i valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Elimina le serie e le categorie generate di default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Aggiunta di nuove serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Popolamento dei dati della serie
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personalizza i dati del grafico aggiungendo categorie e serie e impostandone i valori. In questo esempio, abbiamo tre categorie e una serie con i relativi punti dati.

## Passaggio 7: personalizzare i settori del grafico a torta

```java
// Imposta i colori del settore
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personalizza l'aspetto di ogni settore
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Personalizza il bordo del settore
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Personalizza altri settori in modo simile
```

Personalizza l'aspetto di ogni settore del grafico a torta. Puoi modificare i colori, gli stili dei bordi e altre proprietà visive.

## Passaggio 8: personalizzare le etichette dati

```java
// Personalizza le etichette dei dati
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personalizzare le etichette dati per altri punti dati in modo simile
```

Personalizza le etichette dati per ogni punto dati nel grafico a torta. Puoi controllare quali valori vengono visualizzati sul grafico.

## Passaggio 9: Mostra le linee guida

```java
// Mostra le linee guida per il grafico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Abilita le linee guida per collegare le etichette dati ai settori corrispondenti.

## Passaggio 10: imposta l'angolo di rotazione del grafico a torta

```java
// Imposta l'angolo di rotazione per i settori del grafico a torta
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Imposta l'angolo di rotazione per i settori del grafico a torta. In questo esempio, lo impostiamo a 180 gradi.

## Passaggio 11: Salva la presentazione

```java
// Salva la presentazione con il grafico a torta
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Salvare la presentazione con il grafico a torta nella directory specificata.

## Codice sorgente completo per grafico a torta in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
// Accedi alla prima diapositiva
ISlide slides = presentation.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Titolo del grafico di impostazione
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Impostazione dell'indice del foglio dati del grafico
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro dei dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina le serie e le categorie generate di default
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Aggiunta di nuove serie
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Ora popolamento dei dati della serie
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Non funziona nella nuova versione
// Aggiunta di nuovi punti e impostazione del colore del settore
// serie.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Impostazione del confine del settore
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Impostazione del confine del settore
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Impostazione del confine del settore
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Crea etichette personalizzate per ciascuna categoria per la nuova serie
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Visualizzazione delle linee guida per il grafico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Impostazione dell'angolo di rotazione per i settori del grafico a torta
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Salva la presentazione con il grafico
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

Hai creato con successo un grafico a torta in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare l'aspetto del grafico e le etichette dei dati in base alle tue esigenze specifiche. Questo tutorial fornisce un esempio di base, che puoi ulteriormente migliorare e personalizzare in base alle tue esigenze.

## Domande frequenti

### Come posso cambiare i colori dei singoli settori nel grafico a torta?

Per modificare i colori dei singoli settori nel grafico a torta, è possibile personalizzare il colore di riempimento per ogni punto dati. Nell'esempio di codice fornito, abbiamo mostrato come impostare il colore di riempimento per ogni settore utilizzando `getSolidFillColor().setColor()` metodo. È possibile modificare i valori del colore per ottenere l'aspetto desiderato.

### Posso aggiungere altre categorie e serie di dati al grafico a torta?

Sì, puoi aggiungere ulteriori categorie e serie di dati al grafico a torta. Per farlo, puoi utilizzare `getChartData().getCategories().add()` E `getChartData().getSeries().add()` metodi, come mostrato nell'esempio. Basta fornire i dati e le etichette appropriati per le nuove categorie e serie per espandere il grafico.

### Come posso personalizzare l'aspetto delle etichette dati?

È possibile personalizzare l'aspetto delle etichette dati utilizzando `getDataLabelFormat()` sull'etichetta di ogni punto dati. Nell'esempio, abbiamo dimostrato come mostrare il valore sulle etichette dati utilizzando `getDataLabelFormat().setShowValue(true)`È possibile personalizzare ulteriormente le etichette dati controllando quali valori vengono visualizzati, mostrando le legende e regolando altre opzioni di formattazione.

### Posso cambiare il titolo del grafico a torta?

Sì, puoi cambiare il titolo del grafico a torta. Nel codice fornito, abbiamo impostato il titolo del grafico usando `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`Puoi sostituire `"Sample Title"` con il testo del titolo desiderato.

### Come posso salvare la presentazione generata con il grafico a torta?

Per salvare la presentazione con il grafico a torta, utilizzare `presentation.save()` Metodo. Specifica il percorso e il nome del file desiderati, insieme al formato in cui desideri salvare la presentazione. Ad esempio:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Assicuratevi di specificare il percorso e il formato corretti del file.

### Posso creare altri tipi di grafici utilizzando Aspose.Slides per Java?

Sì, Aspose.Slides per Java supporta vari tipi di grafici, inclusi grafici a barre, grafici a linee e altri ancora. È possibile creare diversi tipi di grafici modificando `ChartType` quando si aggiunge un grafico. Consultare la documentazione di Aspose.Slides per maggiori dettagli sulla creazione di diversi tipi di grafici.

### Come posso trovare maggiori informazioni ed esempi su come lavorare con Aspose.Slides per Java?

Per ulteriori informazioni, documentazione dettagliata ed esempi aggiuntivi, è possibile visitare il sito [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/)Fornisce risorse complete per aiutarti a utilizzare la biblioteca in modo efficace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}