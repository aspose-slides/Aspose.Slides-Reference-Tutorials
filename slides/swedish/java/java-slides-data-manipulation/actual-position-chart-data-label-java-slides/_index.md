---
title: Få den faktiska positionen för diagramdataetiketten i Java Slides
linktitle: Få den faktiska positionen för diagramdataetiketten i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du får den faktiska positionen för diagramdataetiketter i Java Slides med Aspose.Slides för Java. Steg-för-steg guide med källkod.
weight: 18
url: /sv/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till att få faktisk position för diagramdataetikett i Java Slides

I den här handledningen kommer du att lära dig hur du hämtar den faktiska positionen för kartdataetiketter med Aspose.Slides för Java. Vi kommer att skapa ett Java-program som genererar en PowerPoint-presentation med ett diagram, anpassar dataetiketterna och lägger sedan till former som representerar positionerna för dessa dataetiketter.

## Förutsättningar

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket inställt i ditt Java-projekt.

## Steg 1: Skapa en PowerPoint-presentation

Låt oss först skapa en ny PowerPoint-presentation och lägga till ett diagram till den. Vi kommer att anpassa diagrammets dataetiketter senare i handledningen.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Steg 2: Anpassa dataetiketter
Låt oss nu anpassa dataetiketterna för diagramserien. Vi kommer att ställa in deras position och visa värdena.

```java
try {
    // ... (föregående kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (återstående kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## Steg 3: Få den faktiska positionen för dataetiketter
det här steget kommer vi att iterera genom datapunkterna i diagramserien och hämta den faktiska positionen för dataetiketter som har ett värde större än 4. Vi kommer sedan att lägga till ellipser för att representera dessa positioner.

```java
try {
    // ... (föregående kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (återstående kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## Steg 4: Spara presentationen
Slutligen, spara den genererade presentationen till en fil.

```java
try {
    // ... (föregående kod)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Komplett källkod för att få den faktiska positionen för diagramdataetiketten i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ATT GÖRA
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen har du lärt dig hur du hämtar den faktiska positionen för diagramdataetiketter i Java Slides med Aspose.Slides för Java. Du kan nu använda denna kunskap för att förbättra dina PowerPoint-presentationer med anpassade dataetiketter och visuella representationer av deras positioner.

## FAQ's

### Hur kan jag anpassa dataetiketter i ett diagram?

 För att anpassa dataetiketter i ett diagram kan du använda`setDefaultDataLabelFormat` metod på diagramserien och ställ in egenskaper som position och synlighet. Till exempel:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Hur kan jag lägga till former för att representera dataetikettpositioner?

 Du kan iterera genom datapunkterna i en diagramserie och använda`getActualX`, `getActualY`, `getActualWidth` , och`getActualHeight`metoder för dataetiketten för att få sin position. Sedan kan du lägga till former med hjälp av`addAutoShape` metod. Här är ett exempel:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Hur kan jag spara den genererade presentationen?

 Du kan spara den genererade presentationen med hjälp av`save` metod. Ange önskad filsökväg och`SaveFormat` som parametrar. Till exempel:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
