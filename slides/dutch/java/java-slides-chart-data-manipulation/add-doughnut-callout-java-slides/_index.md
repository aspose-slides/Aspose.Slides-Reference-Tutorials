---
"description": "Leer hoe je donut-callouts toevoegt aan Java-dia's met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor verbeterde presentaties."
"linktitle": "Voeg een donut-callout toe aan Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Voeg een donut-callout toe aan Java-dia's"
"url": "/nl/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een donut-callout toe aan Java-dia's


## Inleiding tot het toevoegen van een donut-callout in Java-dia's met Aspose.Slides voor Java

In deze tutorial laten we je zien hoe je een donut-callout aan een dia toevoegt in Java met behulp van Aspose.Slides voor Java. Een donut-callout is een grafiekelement dat gebruikt kan worden om specifieke datapunten in een donutdiagram te markeren. We geven je stapsgewijze instructies en de volledige broncode voor je gemak.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

1. Java-ontwikkelomgeving
2. Aspose.Slides voor Java-bibliotheek
3. Geïntegreerde ontwikkelomgeving (IDE) zoals Eclipse of IntelliJ IDEA
4. Een PowerPoint-presentatie waaraan u de donut-toelichting wilt toevoegen

## Stap 1: Stel uw Java-project in

1. Maak een nieuw Java-project in de IDE van uw keuze.
2. Voeg de Aspose.Slides voor Java-bibliotheek als afhankelijkheid toe aan uw project.

## Stap 2: Initialiseer de presentatie

Om te beginnen moet je een PowerPoint-presentatie initialiseren en een dia maken waaraan je de donut-toelichting wilt toevoegen. Hier is de code om dit te bereiken:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Zorg ervoor dat u vervangt `"Your Document Directory"` met het daadwerkelijke pad naar uw PowerPoint-presentatiebestand.

## Stap 3: Maak een donutdiagram

Vervolgens maak je een ringdiagram op de dia. Je kunt de positie en grootte van het diagram naar wens aanpassen. Hier is de code om een ringdiagram toe te voegen:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Stap 4: Pas het donutdiagram aan

Nu is het tijd om het ringdiagram aan te passen. We stellen verschillende eigenschappen in, zoals het verwijderen van de legenda, het configureren van de gatgrootte en het aanpassen van de hoek van de eerste snede. Hier is de code:

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

## Stap 5: Gegevens toevoegen aan het ringdiagram

Laten we nu gegevens toevoegen aan het ringdiagram. We passen ook de weergave van de datapunten aan. Hier is de code om dit te doen:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Pas hier het uiterlijk van het gegevenspunt aan
        i++;
    }
    categoryIndex++;
}
```

In deze code voegen we categorieën en datapunten toe aan het ringdiagram. Je kunt de weergave van de datapunten naar wens aanpassen.

## Stap 6: Sla de presentatie op

Vergeet ten slotte niet je presentatie op te slaan nadat je de donut-callout hebt toegevoegd. Hier is de code om de presentatie op te slaan:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Zorg ervoor dat u vervangt `"chart.pptx"` met de gewenste bestandsnaam.

Gefeliciteerd! U hebt met succes een donut-toelichting toegevoegd aan een Java-dia met Aspose.Slides voor Java. U kunt nu uw Java-applicatie gebruiken om de PowerPoint-presentatie met het donutdiagram en de toelichting te genereren.

## Volledige broncode voor het toevoegen van een donut-callout in Java-dia's

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

In deze tutorial hebben we het proces behandeld van het toevoegen van een donut-callout aan een Java-dia met Aspose.Slides voor Java. Je hebt geleerd hoe je een donutdiagram maakt, de weergave ervan aanpast en datapunten toevoegt. Voel je vrij om je presentaties verder te verbeteren met deze krachtige bibliotheek en meer diagramopties te verkennen.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van de donut-callout veranderen?

kunt de weergave van de donut-toelichting aanpassen door de eigenschappen van de datapunten in de grafiek aan te passen. In de meegeleverde code ziet u hoe u de opvulkleur, lijnkleur, lettertype en andere kenmerken van datapunten instelt.

### Kan ik meer datapunten toevoegen aan het ringdiagram?

Ja, u kunt zoveel datapunten als nodig toevoegen aan het ringdiagram. Breid eenvoudig de lussen in de code uit waar categorieën en datapunten worden toegevoegd en geef de juiste gegevens en opmaak op.

### Hoe kan ik de positie en grootte van het ringdiagram op de dia aanpassen?

U kunt de positie en de grootte van het ringdiagram wijzigen door de parameters in de `addChart` methode. De vier getallen in die methode komen overeen met de X- en Y-coördinaten van de linkerbovenhoek van de grafiek en respectievelijk de breedte en hoogte ervan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}