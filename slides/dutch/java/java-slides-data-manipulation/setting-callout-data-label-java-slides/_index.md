---
"description": "Leer hoe u callouts voor gegevenslabels instelt in Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "Een callout instellen voor een gegevenslabel in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Een callout instellen voor een gegevenslabel in Java-dia's"
"url": "/nl/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Een callout instellen voor een gegevenslabel in Java-dia's


## Inleiding tot het instellen van een callout voor een gegevenslabel in Aspose.Slides voor Java

In deze tutorial laten we zien hoe je callouts voor gegevenslabels in een grafiek instelt met Aspose.Slides voor Java. Callouts kunnen handig zijn om specifieke datapunten in je grafiek te markeren. We doorlopen de code stap voor stap en bieden de benodigde broncode.

## Vereisten

- U moet Aspose.Slides voor Java geïnstalleerd hebben.
- Maak een Java-project en voeg de Aspose.Slides-bibliotheek toe aan uw project.

## Stap 1: Maak een presentatie en voeg een grafiek toe

Eerst moeten we een presentatie maken en een grafiek aan een dia toevoegen. Zorg ervoor dat je `"Your Document Directory"` met het werkelijke pad naar uw documentenmap.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Stap 2: Configureer de grafiek

Vervolgens configureren we de grafiek door eigenschappen als legenda, reeksen en categorieën in te stellen.

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
        // Voeg hier datapunten toe
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Stap 3: Gegevenslabels aanpassen

Nu gaan we de gegevenslabels aanpassen, waarbij we onder andere de callouts voor de laatste reeks instellen.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Pas de opmaak van gegevenspunten aan (opvullen, lijn, enz.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Pas de opmaak van labels aan (lettertype, opvulling, enz.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Callouts inschakelen
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Stap 4: Sla de presentatie op

Sla ten slotte de presentatie met de geconfigureerde grafiek op.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Je hebt nu succesvol callouts voor gegevenslabels in een grafiek ingesteld met Aspose.Slides voor Java. Pas de code aan op basis van je specifieke grafiek- en gegevensvereisten.

## Volledige broncode voor het instellen van een callout voor een gegevenslabel in Java-dia's

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

In deze tutorial hebben we onderzocht hoe je callouts voor gegevenslabels in een grafiek kunt instellen met Aspose.Slides voor Java. Callouts zijn waardevolle tools om specifieke datapunten in je grafieken en presentaties te benadrukken. We hebben een stapsgewijze handleiding en broncode toegevoegd om je te helpen bij deze aanpassing.

## Veelgestelde vragen

### Hoe pas ik het uiterlijk van gegevenslabels aan?

Om de weergave van gegevenslabels aan te passen, kunt u eigenschappen zoals lettertype, opvulling en lijnstijlen wijzigen. Bijvoorbeeld:

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

### Hoe kan ik callouts voor gegevenslabels in- of uitschakelen?

Om callouts voor gegevenslabels in of uit te schakelen, gebruikt u de `setShowLabelAsDataCallout` methode. Stel het in op `true` om callouts in te schakelen en `false` om ze uit te schakelen.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Callouts inschakelen
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Callouts uitschakelen
```

### Kan ik de leiderlijnen voor gegevenslabels aanpassen?

Ja, u kunt de aanlooplijnen voor gegevenslabels aanpassen met eigenschappen zoals lijnstijl, kleur en breedte. Bijvoorbeeld:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Leidlijnen inschakelen
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Dit zijn enkele veelvoorkomende aanpassingsopties voor gegevenslabels en callouts in Aspose.Slides voor Java. U kunt het uiterlijk verder aanpassen aan uw specifieke behoeften.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}