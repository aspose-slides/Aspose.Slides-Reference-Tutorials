---
title: Impostazione dei colori delle sezioni del grafico a torta automatico nelle diapositive Java
linktitle: Impostazione dei colori delle sezioni del grafico a torta automatico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare grafici a torta dinamici con colori delle sezioni automatici nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con il codice sorgente.
type: docs
weight: 24
url: /it/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Introduzione all'impostazione dei colori delle sezioni del grafico a torta automatico nelle diapositive Java

In questo tutorial esploreremo come creare un grafico a torta in una presentazione di PowerPoint utilizzando Aspose.Slides per Java e impostare i colori delle sezioni automatiche per il grafico. Forniremo una guida passo passo insieme al codice sorgente.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria dal sito Web Aspose:[Scarica Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

## Passaggio 1: importa i pacchetti richiesti

Innanzitutto, devi importare i pacchetti necessari da Aspose.Slides per Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Passaggio 2: crea una presentazione PowerPoint

 Istanziare il`Presentation` classe per creare una nuova presentazione di PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Passaggio 3: aggiungi una diapositiva

Accedi alla prima diapositiva della presentazione e aggiungi un grafico con i dati predefiniti:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Passaggio 4: imposta il titolo del grafico

Imposta un titolo per il grafico:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Passaggio 5: configura i dati del grafico

Imposta il grafico per mostrare i valori per la prima serie e configura i dati del grafico:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Passaggio 6: aggiungi categorie e serie

Aggiungi nuove categorie e serie al grafico:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Passaggio 7: popolare i dati della serie

Compilare i dati della serie per il grafico a torta:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Passaggio 8: attiva i colori delle sezioni diverse

Abilita vari colori delle sezioni per il grafico a torta:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Passaggio 9: salva la presentazione

Infine, salva la presentazione in un file PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per l'impostazione dei colori delle sezioni del grafico a torta automatico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
try
{
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
	//Ora popolano i dati delle serie
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai creato con successo un grafico a torta in una presentazione di PowerPoint utilizzando Aspose.Slides per Java e configurato per avere colori di sezione automatici. Questa guida passo passo fornisce il codice sorgente necessario per raggiungere questo obiettivo. È possibile personalizzare ulteriormente il grafico e la presentazione secondo necessità.

## Domande frequenti

### Come posso personalizzare i colori delle singole sezioni nel grafico a torta?

 Per personalizzare i colori delle singole fette nel grafico a torta, puoi utilizzare il`getAutomaticSeriesColors` metodo per recuperare la combinazione di colori predefinita e quindi modificare i colori secondo necessità. Ecco un esempio:

```java
//Ottieni la combinazione di colori predefinita
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modificare i colori secondo necessità
colors.get_Item(0).setColor(Color.RED); // Imposta il colore della prima fetta su rosso
colors.get_Item(1).setColor(Color.BLUE); // Imposta il colore della seconda fetta su blu
// Aggiungi ulteriori modifiche al colore come richiesto
```

### Come posso aggiungere una legenda al grafico a torta?

 Per aggiungere una legenda al grafico a torta, puoi utilizzare il file`getLegend` metodo e configurarlo come segue:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Imposta la posizione della legenda
legend.setOverlay(true); // Visualizza la legenda sul grafico
```

### Posso cambiare il carattere e lo stile del titolo?

Sì, puoi modificare il carattere e lo stile del titolo. Utilizza il codice seguente per impostare il carattere e lo stile del titolo:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Imposta la dimensione del carattere
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Rendi il titolo in grassetto
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Rendi il titolo in corsivo
```

Puoi regolare la dimensione del carattere, il grassetto e lo stile corsivo secondo necessità.