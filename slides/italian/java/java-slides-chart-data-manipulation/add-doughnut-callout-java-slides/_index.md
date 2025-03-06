---
title: Aggiungi il callout alla ciambella nelle diapositive Java
linktitle: Aggiungi il callout alla ciambella nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Impara ad aggiungere callout a ciambella nelle diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per presentazioni migliorate.
weight: 12
url: /it/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'aggiunta di un callout a ciambella nelle diapositive Java utilizzando Aspose.Slides per Java

In questo tutorial, ti guideremo attraverso il processo di aggiunta di un callout ciambella a una diapositiva in Java utilizzando Aspose.Slides per Java. Un callout a ciambella è un elemento del grafico che può essere utilizzato per evidenziare punti dati specifici in un grafico a ciambella. Ti forniremo istruzioni dettagliate e il codice sorgente completo per la tua comodità.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Ambiente di sviluppo Java
2. Aspose.Slides per la libreria Java
3. Ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA
4. Una presentazione PowerPoint in cui desideri aggiungere il callout della ciambella

## Passaggio 1: configura il tuo progetto Java

1. Crea un nuovo progetto Java nell'IDE scelto.
2. Aggiungi la libreria Aspose.Slides per Java al tuo progetto come dipendenza.

## Passaggio 2: inizializzare la presentazione

Per iniziare, dovrai inizializzare una presentazione di PowerPoint e creare una diapositiva in cui desideri aggiungere il callout della ciambella. Ecco il codice per raggiungere questo obiettivo:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo del file di presentazione di PowerPoint.

## Passaggio 3: crea un grafico a ciambella

Successivamente, creerai un grafico a ciambella sulla diapositiva. Puoi personalizzare la posizione e le dimensioni del grafico in base alle tue esigenze. Ecco il codice per aggiungere un grafico a ciambella:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Passaggio 4: personalizza il grafico a ciambella

Ora è il momento di personalizzare il grafico a ciambella. Imposteremo varie proprietà come la rimozione della legenda, la configurazione della dimensione del foro e la regolazione dell'angolo della prima sezione. Ecco il codice:

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

Questo frammento di codice imposta le proprietà per il grafico ad anello. È possibile regolare i valori per soddisfare le proprie esigenze specifiche.

## Passaggio 5: aggiungi dati al grafico a ciambella

Ora aggiungiamo i dati al grafico ad anello. Personalizzeremo anche l'aspetto dei punti dati. Ecco il codice per ottenere questo risultato:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Personalizza l'aspetto del punto dati qui
        i++;
    }
    categoryIndex++;
}
```

In questo codice aggiungeremo categorie e punti dati al grafico a ciambella. È possibile personalizzare ulteriormente l'aspetto dei punti dati secondo necessità.

## Passaggio 6: salva la presentazione

Infine, non dimenticare di salvare la presentazione dopo aver aggiunto il callout ciambella. Ecco il codice per salvare la presentazione:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Assicurati di sostituire`"chart.pptx"` con il nome file desiderato.

Congratulazioni! Hai aggiunto con successo un callout ciambella a una diapositiva Java utilizzando Aspose.Slides per Java. Ora puoi eseguire l'applicazione Java per generare la presentazione PowerPoint con il grafico a ciambella e il callout.

## Codice sorgente completo per aggiungere il callout della ciambella nelle diapositive Java

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

In questo tutorial, abbiamo trattato il processo di aggiunta di un callout a ciambella a una diapositiva Java utilizzando Aspose.Slides per Java. Hai imparato come creare un grafico ad anello, personalizzarne l'aspetto e aggiungere punti dati. Sentiti libero di migliorare ulteriormente le tue presentazioni con questa potente libreria ed esplorare più opzioni di grafici.

## Domande frequenti

### Come posso modificare l'aspetto del callout della ciambella?

È possibile personalizzare l'aspetto del callout a ciambella modificando le proprietà dei punti dati nel grafico. Nel codice fornito puoi vedere come impostare il colore di riempimento, il colore della linea, lo stile del carattere e altri attributi dei punti dati.

### Posso aggiungere più punti dati al grafico ad anello?

Sì, puoi aggiungere tutti i punti dati necessari al grafico a ciambella. Estendi semplicemente i loop nel codice in cui vengono aggiunte categorie e punti dati e fornisci i dati e la formattazione appropriati.

### Come posso regolare la posizione e la dimensione del grafico ad anello sulla diapositiva?

 Puoi cambiare la posizione e la dimensione del grafico ad anello modificando i parametri nel file`addChart` metodo. I quattro numeri in questo metodo corrispondono rispettivamente alle coordinate X e Y dell'angolo in alto a sinistra del grafico e alla sua larghezza e altezza.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
