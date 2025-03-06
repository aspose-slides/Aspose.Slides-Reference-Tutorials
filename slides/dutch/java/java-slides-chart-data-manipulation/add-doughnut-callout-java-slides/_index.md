---
title: Donut-toelichting toevoegen aan Java-dia's
linktitle: Donut-toelichting toevoegen aan Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u donut-toelichtingen toevoegt aan Java-dia's met behulp van Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor verbeterde presentaties.
weight: 12
url: /nl/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Donut-toelichting toevoegen aan Java-dia's


## Inleiding tot het toevoegen van een donut-toelichting in Java-dia's met behulp van Aspose.Slides voor Java

In deze zelfstudie begeleiden we u bij het toevoegen van een Donut Callout aan een dia in Java met behulp van Aspose.Slides voor Java. Een ringdiagram is een diagramelement dat kan worden gebruikt om specifieke gegevenspunten in een ringdiagram te markeren. Wij zullen u voor uw gemak voorzien van stapsgewijze instructies en de volledige broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Java-ontwikkelomgeving
2. Aspose.Slides voor Java-bibliotheek
3. Integrated Development Environment (IDE) zoals Eclipse of IntelliJ IDEA
4. Een PowerPoint-presentatie waaraan u de Donut Callout wilt toevoegen

## Stap 1: Stel uw Java-project in

1. Maak een nieuw Java-project in de door u gekozen IDE.
2. Voeg de Aspose.Slides voor Java-bibliotheek als afhankelijkheid toe aan uw project.

## Stap 2: Initialiseer de presentatie

Om aan de slag te gaan, moet u een PowerPoint-presentatie initialiseren en een dia maken waaraan u de Donut Callout wilt toevoegen. Hier is de code om dit te bereiken:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Zorg ervoor dat u vervangt`"Your Document Directory"` met het daadwerkelijke pad naar uw PowerPoint-presentatiebestand.

## Stap 3: Maak een ringdiagram

Vervolgens maakt u een ringdiagram op de dia. U kunt de positie en grootte van het diagram aanpassen aan uw vereisten. Hier is de code om een ringdiagram toe te voegen:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Stap 4: Pas het donutdiagram aan

Nu is het tijd om het donutdiagram aan te passen. We zullen verschillende eigenschappen instellen, zoals het verwijderen van de legenda, het configureren van de gatgrootte en het aanpassen van de eerste segmenthoek. Hier is de code:

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

Met dit codefragment worden de eigenschappen voor het ringdiagram ingesteld. U kunt de waarden aanpassen aan uw specifieke behoeften.

## Stap 5: Voeg gegevens toe aan het ringdiagram

Laten we nu gegevens toevoegen aan het ringdiagram. We passen ook het uiterlijk van de gegevenspunten aan. Hier is de code om dit te bereiken:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Pas hier de weergave van datapunten aan
        i++;
    }
    categoryIndex++;
}
```

In deze code voegen we categorieën en gegevenspunten toe aan het ringdiagram. U kunt de weergave van gegevenspunten indien nodig verder aanpassen.

## Stap 6: Sla de presentatie op

Vergeet ten slotte niet uw presentatie op te slaan nadat u de Donut Callout hebt toegevoegd. Hier is de code om de presentatie op te slaan:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Zorg ervoor dat u vervangt`"chart.pptx"` met uw gewenste bestandsnaam.

Gefeliciteerd! U hebt met succes een Donut Callout aan een Java-dia toegevoegd met behulp van Aspose.Slides voor Java. U kunt nu uw Java-toepassing uitvoeren om de PowerPoint-presentatie te genereren met het ringdiagram en de toelichting.

## Volledige broncode voor het toevoegen van een donut-toelichting in Java-dia's

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

## Conclusie

In deze zelfstudie hebben we het proces besproken van het toevoegen van een Donut Callout aan een Java-dia met behulp van Aspose.Slides voor Java. U hebt geleerd hoe u een ringdiagram maakt, het uiterlijk ervan aanpast en gegevenspunten toevoegt. Voel je vrij om je presentaties verder te verbeteren met deze krachtige bibliotheek en meer diagramopties te verkennen.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van de Donut Callout wijzigen?

U kunt het uiterlijk van de donut-toelichting aanpassen door de eigenschappen van gegevenspunten in het diagram te wijzigen. In de meegeleverde code kunt u zien hoe u de vulkleur, lijnkleur, lettertypestijl en andere kenmerken van gegevenspunten kunt instellen.

### Kan ik meer gegevenspunten toevoegen aan het ringdiagram?

Ja, u kunt zoveel gegevenspunten aan het ringdiagram toevoegen als nodig is. Verleng eenvoudigweg de lussen in de code waar categorieën en datapunten worden toegevoegd, en geef de juiste gegevens en opmaak op.

### Hoe kan ik de positie en grootte van het ringdiagram op de dia aanpassen?

 U kunt de positie en grootte van het ringdiagram wijzigen door de parameters in het`addChart` methode. De vier getallen in die methode komen overeen met respectievelijk de X- en Y-coördinaten van de linkerbovenhoek van het diagram en de breedte en hoogte ervan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
