---
title: Krijg de werkelijke positie van het diagramgegevenslabel in Java-dia's
linktitle: Krijg de werkelijke positie van het diagramgegevenslabel in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de werkelijke positie van diagramgegevenslabels in Java Slides kunt achterhalen met behulp van Aspose.Slides voor Java. Stap-voor-stap handleiding met broncode.
type: docs
weight: 18
url: /nl/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Inleiding tot het verkrijgen van de werkelijke positie van het diagramgegevenslabel in Java-dia's

In deze zelfstudie leert u hoe u de werkelijke positie van diagramgegevenslabels kunt ophalen met Aspose.Slides voor Java. We gaan een Java-programma maken dat een PowerPoint-presentatie met een diagram genereert, de gegevenslabels aanpast en vervolgens vormen toevoegt die de posities van deze gegevenslabels vertegenwoordigen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw Java-project is ingesteld.

## Stap 1: Maak een PowerPoint-presentatie

Laten we eerst een nieuwe PowerPoint-presentatie maken en er een diagram aan toevoegen. We zullen de gegevenslabels van het diagram later in de zelfstudie aanpassen.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Stap 2: Gegevenslabels aanpassen
Laten we nu de gegevenslabels voor de diagramreeksen aanpassen. We zullen hun positie bepalen en de waarden tonen.

```java
try {
    // ... (vorige code)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (resterende code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Stap 3: Krijg de werkelijke positie van gegevenslabels
In deze stap doorlopen we de gegevenspunten van de diagramreeks en halen we de werkelijke positie op van gegevenslabels die een waarde groter dan 4 hebben. Vervolgens voegen we ellipsen toe om deze posities weer te geven.

```java
try {
    // ... (vorige code)
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
    // ... (resterende code)
} finally {
    if (pres != null) pres.dispose();
}
```

## Stap 4: Sla de presentatie op
Sla ten slotte de gegenereerde presentatie op in een bestand.

```java
try {
    // ... (vorige code)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Volledige broncode voor het verkrijgen van de werkelijke positie van het diagramgegevenslabel in Java-dia's

```java
// Het pad naar de documentenmap.
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//TE DOEN
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

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de werkelijke positie van diagramgegevenslabels in Java Slides kunt ophalen met behulp van Aspose.Slides voor Java. U kunt deze kennis nu gebruiken om uw PowerPoint-presentaties te verbeteren met aangepaste gegevenslabels en visuele weergaven van hun posities.

## Veelgestelde vragen

### Hoe kan ik gegevenslabels in een diagram aanpassen?

 Om gegevenslabels in een diagram aan te passen, kunt u de`setDefaultDataLabelFormat` methode op de kaartreeks en stel eigenschappen in zoals positie en zichtbaarheid. Bijvoorbeeld:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Hoe kan ik vormen toevoegen om de posities van gegevenslabels weer te geven?

 U kunt de gegevenspunten van een diagramreeks doorlopen en de`getActualX`, `getActualY`, `getActualWidth` , En`getActualHeight`methoden van het datalabel om zijn positie te bepalen. Vervolgens kunt u vormen toevoegen met behulp van de`addAutoShape` methode. Hier is een voorbeeld:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Hoe kan ik de gegenereerde presentatie opslaan?

 U kunt de gegenereerde presentatie opslaan met behulp van de`save` methode. Geef het gewenste bestandspad op en de`SaveFormat` als parameters. Bijvoorbeeld:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```