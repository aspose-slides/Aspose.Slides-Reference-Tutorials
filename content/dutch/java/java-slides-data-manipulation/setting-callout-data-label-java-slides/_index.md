---
title: Bijschrift voor gegevenslabel instellen in Java-dia's
linktitle: Bijschrift voor gegevenslabel instellen in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u toelichtingen voor gegevenslabels in Aspose.Slides voor Java instelt. Stap-voor-stap handleiding met broncode.
type: docs
weight: 25
url: /nl/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Inleiding tot het instellen van bijschrift voor gegevenslabel in Aspose.Slides voor Java

In deze zelfstudie laten we zien hoe u callouts voor gegevenslabels in een diagram instelt met behulp van Aspose.Slides voor Java. Toelichtingen kunnen handig zijn om specifieke gegevenspunten in uw diagram te markeren. We lopen stap voor stap door de code en zorgen voor de benodigde broncode.

## Vereisten

- Aspose.Slides voor Java zou geïnstalleerd moeten zijn.
- Maak een Java-project en voeg de Aspose.Slides-bibliotheek toe aan uw project.

## Stap 1: Maak een presentatie en voeg een diagram toe

 Eerst moeten we een presentatie maken en een diagram aan een dia toevoegen. Zorg ervoor dat u vervangt`"Your Document Directory"` met het daadwerkelijke pad naar uw documentmap.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Stap 2: Configureer de grafiek

Vervolgens configureren we het diagram door eigenschappen in te stellen, zoals legenda, reeksen en categorieën.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Series en categorieën configureren (u kunt het aantal series en categorieën aanpassen)
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
        // Voeg hier gegevenspunten toe
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Stap 3: Gegevenslabels aanpassen

Nu gaan we de gegevenslabels aanpassen, inclusief het instellen van highlights voor de laatste serie.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Pas de opmaak van gegevenspunten aan (opvulling, lijn, enz.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Pas de labelopmaak aan (lettertype, vulling, enz.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Schakel highlights in
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie op met het geconfigureerde diagram.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Nu hebt u met succes highlights voor gegevenslabels in een diagram ingesteld met behulp van Aspose.Slides voor Java. Pas de code aan volgens uw specifieke diagram- en gegevensvereisten.

## Volledige broncode voor het instellen van toelichting voor gegevenslabel in Java-dia's

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

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u highlights voor gegevenslabels in een diagram kunt instellen met behulp van Aspose.Slides voor Java. Toelichtingen zijn waardevolle hulpmiddelen om specifieke gegevenspunten in uw diagrammen en presentaties te benadrukken. We hebben samen met de broncode een stapsgewijze handleiding verstrekt om u te helpen deze aanpassing te realiseren.

## Veelgestelde vragen

### Hoe pas ik het uiterlijk van gegevenslabels aan?

Om het uiterlijk van gegevenslabels aan te passen, kunt u eigenschappen zoals lettertype, vulling en lijnstijlen wijzigen. Bijvoorbeeld:

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

### Hoe kan ik highlights voor gegevenslabels in- of uitschakelen?

 Om bijschriften voor gegevenslabels in of uit te schakelen, gebruikt u de`setShowLabelAsDataCallout` methode. Stel het in`true` om toelichtingen in te schakelen en`false` om ze uit te schakelen.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Schakel highlights in
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Schakel highlights uit
```

### Kan ik de aanhaallijnen voor gegevenslabels aanpassen?

Ja, u kunt de aanhaallijnen voor gegevenslabels aanpassen met eigenschappen als lijnstijl, kleur en breedte. Bijvoorbeeld:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Schakel aanhaallijnen in
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Dit zijn enkele veelgebruikte aanpassingsopties voor gegevenslabels en bijschriften in Aspose.Slides voor Java. U kunt de uitstraling verder afstemmen op uw specifieke wensen.