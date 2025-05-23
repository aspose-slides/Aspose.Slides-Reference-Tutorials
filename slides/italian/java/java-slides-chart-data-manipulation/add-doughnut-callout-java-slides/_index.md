---
"description": "Impara ad aggiungere callout a ciambella nelle diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per presentazioni ottimizzate."
"linktitle": "Aggiungi una chiamata a forma di ciambella in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungi una chiamata a forma di ciambella in Java Slides"
"url": "/it/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi una chiamata a forma di ciambella in Java Slides


## Introduzione all'aggiunta di un callout a forma di ciambella in Java Slides utilizzando Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di aggiunta di un Doughnut Callout a una diapositiva in Java utilizzando Aspose.Slides per Java. Un Doughnut Callout è un elemento grafico che può essere utilizzato per evidenziare punti dati specifici in un grafico ad anello. Ti forniremo istruzioni dettagliate e il codice sorgente completo per la tua comodità.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Ambiente di sviluppo Java
2. Libreria Aspose.Slides per Java
3. Ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA
4. Una presentazione di PowerPoint in cui desideri aggiungere il richiamo della ciambella

## Passaggio 1: configura il tuo progetto Java

1. Crea un nuovo progetto Java nell'IDE scelto.
2. Aggiungi la libreria Aspose.Slides per Java al tuo progetto come dipendenza.

## Passaggio 2: inizializzare la presentazione

Per iniziare, devi inizializzare una presentazione PowerPoint e creare una diapositiva in cui desideri aggiungere il callout "ciambella". Ecco il codice per farlo:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Assicurati di sostituire `"Your Document Directory"` con il percorso effettivo del file della presentazione di PowerPoint.

## Passaggio 3: creare un grafico a ciambella

Successivamente, creerai un grafico ad anello nella diapositiva. Puoi personalizzare la posizione e le dimensioni del grafico in base alle tue esigenze. Ecco il codice per aggiungere un grafico ad anello:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Passaggio 4: personalizzare il grafico ad anello

Ora è il momento di personalizzare il grafico ad anello. Imposteremo diverse proprietà, come la rimozione della legenda, la configurazione della dimensione del foro e la regolazione dell'angolo della prima sezione. Ecco il codice:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Questo frammento di codice imposta le proprietà del grafico ad anello. Puoi modificare i valori in base alle tue esigenze specifiche.

## Passaggio 5: aggiungere dati al grafico ad anello

Ora aggiungiamo dati al grafico ad anello. Personalizzeremo anche l'aspetto dei punti dati. Ecco il codice per farlo:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Personalizza qui l'aspetto dei punti dati
        i++;
    }
    categoryIndex++;
}
```

In questo codice, aggiungiamo categorie e punti dati al grafico ad anello. Puoi personalizzare ulteriormente l'aspetto dei punti dati a seconda delle tue esigenze.

## Passaggio 6: Salva la presentazione

Infine, non dimenticare di salvare la presentazione dopo aver aggiunto il callout "ciambella". Ecco il codice per salvare la presentazione:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Assicurati di sostituire `"chart.pptx"` con il nome file desiderato.

Congratulazioni! Hai aggiunto correttamente un grafico a ciambella a una diapositiva Java utilizzando Aspose.Slides per Java. Ora puoi eseguire l'applicazione Java per generare la presentazione PowerPoint con il grafico a ciambella e il callout.

## Codice sorgente completo per aggiungere un richiamo a forma di ciambella in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo illustrato come aggiungere un grafico ad anello a una diapositiva Java utilizzando Aspose.Slides per Java. Hai imparato a creare un grafico ad anello, personalizzarne l'aspetto e aggiungere punti dati. Sentiti libero di migliorare ulteriormente le tue presentazioni con questa potente libreria ed esplorare ulteriori opzioni di creazione di grafici.

## Domande frequenti

### Come posso modificare l'aspetto del Doughnut Callout?

È possibile personalizzare l'aspetto del Callout ad anello modificando le proprietà dei punti dati nel grafico. Nel codice fornito, è possibile vedere come impostare il colore di riempimento, il colore della linea, lo stile del carattere e altri attributi dei punti dati.

### Posso aggiungere altri punti dati al grafico ad anello?

Sì, puoi aggiungere tutti i punti dati necessari al grafico ad anello. È sufficiente estendere i cicli nel codice in cui vengono aggiunte categorie e punti dati e fornire i dati e la formattazione appropriati.

### Come posso regolare la posizione e le dimensioni del grafico ad ciambella sulla diapositiva?

È possibile modificare la posizione e la dimensione del grafico ad anello modificando i parametri nel `addChart` metodo. I quattro numeri in quel metodo corrispondono rispettivamente alle coordinate X e Y dell'angolo in alto a sinistra del grafico e alla sua larghezza e altezza.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}