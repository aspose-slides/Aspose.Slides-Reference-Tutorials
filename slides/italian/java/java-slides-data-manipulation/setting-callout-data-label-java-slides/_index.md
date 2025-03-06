---
title: Impostazione del callout per l'etichetta dati nelle diapositive Java
linktitle: Impostazione del callout per l'etichetta dati nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare i callout per le etichette dati in Aspose.Slides per Java. Guida passo passo con il codice sorgente.
weight: 25
url: /it/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'impostazione del callout per l'etichetta dati in Aspose.Slides per Java

In questo tutorial, dimostreremo come impostare i callout per le etichette dei dati in un grafico utilizzando Aspose.Slides per Java. I callout possono essere utili per evidenziare punti dati specifici nel grafico. Esamineremo il codice passo dopo passo e forniremo il codice sorgente necessario.

## Prerequisiti

- Dovresti avere Aspose.Slides per Java installato.
- Crea un progetto Java e aggiungi la libreria Aspose.Slides al tuo progetto.

## Passaggio 1: crea una presentazione e aggiungi un grafico

 Per prima cosa dobbiamo creare una presentazione e aggiungere un grafico a una diapositiva. Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Passaggio 2: configura il grafico

Successivamente, configureremo il grafico impostando proprietà come legenda, serie e categorie.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configura serie e categorie (puoi regolare il numero di serie e categorie)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Aggiungi punti dati qui
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Passaggio 3: personalizzare le etichette dati

Ora personalizzeremo le etichette dei dati, inclusa l'impostazione dei callout per le ultime serie.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Personalizza la formattazione dei punti dati (riempimento, linea, ecc.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Personalizza la formattazione dell'etichetta (carattere, riempimento, ecc.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Abilita callout
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Passaggio 4: salva la presentazione

Infine, salva la presentazione con il grafico configurato.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Ora hai impostato correttamente i callout per le etichette dati in un grafico utilizzando Aspose.Slides per Java. Personalizza il codice in base ai tuoi requisiti specifici di grafici e dati.

## Codice sorgente completo per l'impostazione del callout per l'etichetta dati nelle diapositive Java

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo esplorato come impostare i callout per le etichette dei dati in un grafico utilizzando Aspose.Slides per Java. I callout sono strumenti preziosi per enfatizzare punti dati specifici nei grafici e nelle presentazioni. Abbiamo fornito una guida passo passo insieme al codice sorgente per aiutarti a ottenere questa personalizzazione.

## Domande frequenti

### Come posso personalizzare l'aspetto delle etichette dati?

Per personalizzare l'aspetto delle etichette dati, è possibile modificare proprietà quali carattere, riempimento e stili di linea. Per esempio:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Come posso abilitare o disabilitare i callout per le etichette dati?

 Per abilitare o disabilitare i callout per le etichette dati, utilizzare il file`setShowLabelAsDataCallout` metodo. Impostalo su`true` per abilitare i callout e`false`per disabilitarli.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Abilita callout
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Disabilita callout
```

### Posso personalizzare le linee guida per le etichette dati?

Sì, puoi personalizzare le linee guida per le etichette dati utilizzando proprietà come stile di linea, colore e larghezza. Per esempio:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Abilita linee guida
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Queste sono alcune opzioni di personalizzazione comuni per le etichette dei dati e i callout in Aspose.Slides per Java. Puoi personalizzare ulteriormente l'aspetto in base alle tue esigenze specifiche.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
