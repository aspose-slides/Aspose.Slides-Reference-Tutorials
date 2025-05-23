---
"description": "Leer hoe u de werkelijke positie van diagramgegevenslabels in Java Slides kunt bepalen met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "De werkelijke positie van het gegevenslabel van een grafiek in Java-dia's weergeven"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "De werkelijke positie van het gegevenslabel van een grafiek in Java-dia's weergeven"
"url": "/nl/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# De werkelijke positie van het gegevenslabel van een grafiek in Java-dia's weergeven


## Inleiding tot het verkrijgen van de werkelijke positie van het gegevenslabel van een grafiek in Java-dia's

In deze tutorial leer je hoe je de werkelijke positie van diagramgegevenslabels kunt ophalen met Aspose.Slides voor Java. We maken een Java-programma dat een PowerPoint-presentatie met een diagram genereert, de gegevenslabels aanpast en vervolgens vormen toevoegt die de posities van deze gegevenslabels weergeven.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u de Aspose.Slides voor Java-bibliotheek in uw Java-project hebt ingesteld.

## Stap 1: Maak een PowerPoint-presentatie

Laten we eerst een nieuwe PowerPoint-presentatie maken en er een grafiek aan toevoegen. Later in deze tutorial passen we de gegevenslabels van de grafiek aan.

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
Laten we nu de gegevenslabels voor de grafiekreeks aanpassen. We stellen hun positie in en tonen de waarden.

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

## Stap 3: De werkelijke positie van de gegevenslabels verkrijgen
In deze stap itereren we door de datapunten van de grafiekreeks en halen we de werkelijke positie op van gegevenslabels met een waarde groter dan 4. Vervolgens voegen we ellipsen toe om deze posities weer te geven.

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

## Volledige broncode voor het verkrijgen van de werkelijke positie van het gegevenslabel van een grafiek in Java-dia's

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//TODO
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

In deze tutorial heb je geleerd hoe je de werkelijke positie van diagramgegevenslabels in Java Slides kunt ophalen met Aspose.Slides voor Java. Je kunt deze kennis nu gebruiken om je PowerPoint-presentaties te verbeteren met aangepaste gegevenslabels en visuele weergaven van hun posities.

## Veelgestelde vragen

### Hoe kan ik gegevenslabels in een grafiek aanpassen?

Om gegevenslabels in een grafiek aan te passen, kunt u de `setDefaultDataLabelFormat` Methode op de grafiekreeks en stel eigenschappen zoals positie en zichtbaarheid in. Bijvoorbeeld:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Hoe kan ik vormen toevoegen om de posities van gegevenslabels weer te geven?

U kunt door de datapunten van een grafiekreeks itereren en de `getActualX`, `getActualY`, `getActualWidth`, En `getActualHeight` methoden van het gegevenslabel om de positie ervan te bepalen. Vervolgens kunt u vormen toevoegen met behulp van de `addAutoShape` methode. Hier is een voorbeeld:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Hoe kan ik de gegenereerde presentatie opslaan?

U kunt de gegenereerde presentatie opslaan met behulp van de `save` methode. Geef het gewenste bestandspad en de `SaveFormat` als parameters. Bijvoorbeeld:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}