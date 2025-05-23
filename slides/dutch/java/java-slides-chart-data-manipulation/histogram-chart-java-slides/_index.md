---
"description": "Leer hoe u histogrammen maakt in PowerPoint-presentaties met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor datavisualisatie."
"linktitle": "Histogramdiagram in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Histogramdiagram in Java-dia's"
"url": "/nl/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Histogramdiagram in Java-dia's


## Inleiding tot histogrammen in Java-dia's met Aspose.Slides

In deze tutorial begeleiden we je bij het maken van een histogram in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. Een histogram wordt gebruikt om de verdeling van gegevens over een continu interval weer te geven.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd. U kunt deze downloaden van de [Aspose-website](https://releases.aspose.com/slides/java/).

## Stap 1: Initialiseer uw project

Maak een Java-project en neem de Aspose.Slides-bibliotheek op in de afhankelijkheden van uw project.

## Stap 2: Importeer de benodigde bibliotheken

```java
import com.aspose.slides.*;
```

## Stap 3: Een bestaande presentatie laden

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Zorg ervoor dat u vervangt `"Your Document Directory"` met het daadwerkelijke pad naar uw PowerPoint-document.

## Stap 4: Maak een histogram

Laten we nu een histogram maken op een dia in de presentatie.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Voeg datapunten toe aan de reeks
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Stel het horizontale as-aggregatietype in op Automatisch
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Sla de presentatie op
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

In deze code verwijderen we eerst alle bestaande categorieën en reeksen uit de grafiek. Vervolgens voegen we datapunten toe aan de reeks met behulp van de `getDataPoints().addDataPointForHistogramSeries` methode. Ten slotte stellen we het horizontale as-aggregatietype in op Automatisch en slaan we de presentatie op.

## Volledige broncode voor histogramgrafiek in Java-dia's

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial hebben we laten zien hoe je een histogram maakt in een PowerPoint-presentatie met behulp van de Aspose.Slides voor Java API. Histogrammen zijn waardevolle hulpmiddelen voor het visualiseren van de gegevensverdeling over een continu interval en kunnen een krachtige aanvulling zijn op je presentaties, vooral wanneer je statistische of analytische content gebruikt.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

U kunt de Aspose.Slides voor Java-bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/)Volg de installatie-instructies op hun website.

### Waarvoor wordt een histogram gebruikt?

Een histogram wordt gebruikt om de spreiding van gegevens over een continu interval te visualiseren. Het wordt vaak gebruikt in de statistiek om frequentieverdelingen weer te geven.

### Kan ik het uiterlijk van het histogram aanpassen?

Ja, u kunt het uiterlijk van het diagram aanpassen, inclusief de kleuren, labels en assen, met behulp van de Aspose.Slides API.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}