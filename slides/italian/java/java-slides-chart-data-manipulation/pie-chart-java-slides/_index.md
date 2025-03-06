---
title: Grafico a torta nelle diapositive Java
linktitle: Grafico a torta nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare straordinari grafici a torta nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per sviluppatori Java.
weight: 23
url: /it/java/chart-data-manipulation/pie-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a torta nelle diapositive Java


## Introduzione alla creazione di un grafico a torta in diapositive Java utilizzando Aspose.Slides

In questo tutorial, dimostreremo come creare un grafico a torta in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Ti forniremo istruzioni dettagliate e codice sorgente Java per aiutarti a iniziare. Questa guida presuppone che tu abbia già configurato il tuo ambiente di sviluppo con Aspose.Slides per Java.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: importa le librerie richieste

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Assicurati di importare le classi necessarie dalla libreria Aspose.Slides.

## Passaggio 2: inizializzare la presentazione

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
```

 Crea un nuovo oggetto Presentazione per rappresentare il tuo file PowerPoint. Sostituire`"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.

## Passaggio 3: aggiungi una diapositiva

```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

Ottieni la prima diapositiva della presentazione in cui desideri aggiungere il grafico a torta.

## Passaggio 4: aggiungi un grafico a torta

```java
// Aggiungi un grafico a torta con dati predefiniti
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Aggiungi un grafico a torta alla diapositiva nella posizione e dimensione specificate.

## Passaggio 5: imposta il titolo del grafico

```java
// Imposta il titolo del grafico
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Imposta un titolo per il grafico a torta. Puoi personalizzare il titolo secondo necessità.

## Passaggio 6: personalizzare i dati del grafico

```java
//Imposta la prima serie per mostrare i valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;

// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Elimina le serie e le categorie generate predefinite
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Aggiunta di nuove serie
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Popolamento dei dati delle serie
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personalizza i dati del grafico aggiungendo categorie e serie e impostandone i valori. In questo esempio, abbiamo tre categorie e una serie con punti dati corrispondenti.

## Passaggio 7: personalizzare i settori del grafico a torta

```java
// Imposta i colori del settore
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personalizza l'aspetto di ciascun settore
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

Personalizza l'aspetto di ciascun settore nel grafico a torta. Puoi modificare i colori, gli stili dei bordi e altre proprietà visive.

## Passaggio 8: personalizzare le etichette dati

```java
// Personalizza le etichette dei dati
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personalizza le etichette dati per altri punti dati in modo simile
```

Personalizza le etichette dei dati per ciascun punto dati nel grafico a torta. Puoi controllare quali valori vengono visualizzati sul grafico.

## Passaggio 9: mostra le linee guida

```java
// Mostra le linee guida per il grafico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Abilita le linee guida per collegare le etichette dati ai settori corrispondenti.

## Passaggio 10: impostare l'angolo di rotazione del grafico a torta

```java
// Imposta l'angolo di rotazione per i settori del grafico a torta
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Imposta l'angolo di rotazione per i settori del grafico a torta. In questo esempio lo impostiamo su 180 gradi.

## Passaggio 11: salva la presentazione

```java
// Salva la presentazione con il grafico a torta
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Salva la presentazione con il grafico a torta nella directory specificata.

## Codice sorgente completo per il grafico a torta nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
// Accedi alla prima diapositiva
ISlide slides = presentation.getSlides().get_Item(0);
// Aggiungi grafico con dati predefiniti
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Titolo del grafico delle impostazioni
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Imposta la prima serie su Mostra valori
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Impostazione dell'indice della scheda grafica
int defaultWorksheetIndex = 0;
// Ottenere il foglio di lavoro con i dati del grafico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Elimina le serie e le categorie generate predefinite
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Aggiunta di nuove categorie
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Aggiunta di nuove serie
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Ora popolano i dati delle serie
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Non funziona nella nuova versione
// Aggiunta di nuovi punti e impostazione del colore del settore
// serie.IsColorVaried = vero;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Impostazione del bordo del settore
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Impostazione del bordo del settore
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Impostazione del bordo del settore
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Crea etichette personalizzate per ciascuna delle categorie per le nuove serie
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
// Visualizzazione delle linee direttrici per il grafico
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Impostazione dell'angolo di rotazione per i settori del grafico a torta
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Salva la presentazione con il grafico
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

Hai creato con successo un grafico a torta in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare l'aspetto del grafico e le etichette dei dati in base ai tuoi requisiti specifici. Questo tutorial fornisce un esempio di base e puoi migliorare e personalizzare ulteriormente i tuoi grafici secondo necessità.

## Domande frequenti

### Come posso cambiare i colori dei singoli settori nel grafico a torta?

 Per modificare i colori dei singoli settori nel grafico a torta, puoi personalizzare il colore di riempimento per ciascun punto dati. Nell'esempio di codice fornito, abbiamo dimostrato come impostare il colore di riempimento per ciascun settore utilizzando il comando`getSolidFillColor().setColor()` metodo. È possibile modificare i valori del colore per ottenere l'aspetto desiderato.

### Posso aggiungere più categorie e serie di dati al grafico a torta?

 Sì, puoi aggiungere ulteriori categorie e serie di dati al grafico a torta. Per fare questo, puoi usare il file`getChartData().getCategories().add()` E`getChartData().getSeries().add()` metodi, come mostrato nell'esempio. Fornisci semplicemente i dati e le etichette appropriati per le nuove categorie e serie per espandere il tuo grafico.

### Come posso personalizzare l'aspetto delle etichette dati?

 È possibile personalizzare l'aspetto delle etichette dati utilizzando il file`getDataLabelFormat()` metodo sull'etichetta di ciascun punto dati. Nell'esempio, abbiamo dimostrato come mostrare il valore sulle etichette dati utilizzando`getDataLabelFormat().setShowValue(true)`. Puoi personalizzare ulteriormente le etichette dei dati controllando quali valori vengono visualizzati, mostrando le chiavi della legenda e regolando altre opzioni di formattazione.

### Posso cambiare il titolo del grafico a torta?

 Sì, puoi modificare il titolo del grafico a torta. Nel codice fornito, impostiamo il titolo del grafico utilizzando`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Puoi sostituire`"Sample Title"` con il testo del titolo desiderato.

### Come posso salvare la presentazione generata con il grafico a torta?

 Per salvare la presentazione con il grafico a torta, utilizzare il file`presentation.save()` metodo. Fornisci il percorso e il nome del file desiderati insieme al formato in cui desideri salvare la presentazione. Per esempio:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Assicurati di specificare il percorso e il formato file corretti.

### Posso creare altri tipi di grafici utilizzando Aspose.Slides per Java?

Sì, Aspose.Slides per Java supporta vari tipi di grafici, inclusi grafici a barre, grafici a linee e altro. È possibile creare diversi tipi di grafici modificando il file`ChartType` quando si aggiunge un grafico. Fare riferimento alla documentazione di Aspose.Slides per maggiori dettagli sulla creazione di diversi tipi di grafici.

### Come posso trovare ulteriori informazioni ed esempi per lavorare con Aspose.Slides per Java?

 Per ulteriori informazioni, documentazione dettagliata ed esempi aggiuntivi, è possibile visitare il[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/). Fornisce risorse complete per aiutarti a utilizzare la libreria in modo efficace.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
