---
"description": "Scopri come creare grafici a torta dinamici con colori automatici per le sezioni nelle presentazioni PowerPoint in Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente."
"linktitle": "Impostazione automatica dei colori delle sezioni del grafico a torta in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Impostazione automatica dei colori delle sezioni del grafico a torta in Java Slides"
"url": "/it/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione automatica dei colori delle sezioni del grafico a torta in Java Slides


## Introduzione all'impostazione automatica dei colori delle sezioni del grafico a torta in Java Slides

In questo tutorial, esploreremo come creare un grafico a torta in una presentazione PowerPoint utilizzando Aspose.Slides per Java e impostare automaticamente i colori delle sezioni del grafico. Forniremo una guida passo passo insieme al codice sorgente.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria dal sito web di Aspose: [Scarica Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

## Passaggio 1: importare i pacchetti richiesti

Per prima cosa, devi importare i pacchetti necessari da Aspose.Slides per Java:

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

## Passaggio 2: creare una presentazione PowerPoint

Istanziare il `Presentation` classe per creare una nuova presentazione PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Passaggio 3: aggiungere una diapositiva

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

## Passaggio 5: configurare i dati del grafico

Imposta il grafico in modo che mostri i valori per la prima serie e configura i dati del grafico:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Passaggio 6: aggiungere categorie e serie

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

## Passaggio 8: abilitare i colori delle sezioni variabili

Abilita i colori delle sezioni diversi per il grafico a torta:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Passaggio 9: Salva la presentazione

Infine, salva la presentazione in un file PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per l'impostazione automatica dei colori delle sezioni del grafico a torta in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
try
{
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
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Hai creato con successo un grafico a torta in una presentazione di PowerPoint utilizzando Aspose.Slides per Java e lo hai configurato per impostare automaticamente i colori delle sezioni. Questa guida passo passo fornisce il codice sorgente necessario per ottenere questo risultato. Puoi personalizzare ulteriormente il grafico e la presentazione in base alle tue esigenze.

## Domande frequenti

### Come posso personalizzare i colori delle singole sezioni nel grafico a torta?

Per personalizzare i colori delle singole sezioni nel grafico a torta, puoi utilizzare `getAutomaticSeriesColors` Metodo per recuperare lo schema di colori predefinito e quindi modificarlo a seconda delle esigenze. Ecco un esempio:

```java
// Ottieni la combinazione di colori predefinita
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modificare i colori secondo necessità
colors.get_Item(0).setColor(Color.RED); // Imposta il colore della prima fetta su rosso
colors.get_Item(1).setColor(Color.BLUE); // Imposta il colore della seconda fetta su blu
// Aggiungere ulteriori modifiche di colore secondo necessità
```

### Come posso aggiungere una legenda al grafico a torta?

Per aggiungere una legenda al grafico a torta, puoi utilizzare `getLegend` metodo e configurarlo come segue:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Imposta la posizione della legenda
legend.setOverlay(true); // Visualizza la legenda sul grafico
```

### Posso cambiare il carattere e lo stile del titolo?

Sì, puoi cambiare il carattere e lo stile del titolo. Usa il seguente codice per impostarli:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Imposta la dimensione del carattere
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Rendi il titolo in grassetto
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Rendi il titolo in corsivo
```

È possibile regolare la dimensione del carattere, il grassetto e lo stile corsivo a seconda delle proprie esigenze.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}