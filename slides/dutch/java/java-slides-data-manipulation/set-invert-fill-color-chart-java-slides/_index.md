---
"description": "Leer hoe u de opvulkleuren voor Java Slides-diagrammen kunt omkeren met Aspose.Slides. Verbeter uw diagramvisualisaties met deze stapsgewijze handleiding en broncode."
"linktitle": "Omgekeerde vulkleurgrafiek instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Omgekeerde vulkleurgrafiek instellen in Java-dia's"
"url": "/nl/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Omgekeerde vulkleurgrafiek instellen in Java-dia's


## Inleiding tot het instellen van de omgekeerde vulkleurkaart in Java-dia's

In deze tutorial laten we zien hoe je de omgekeerde opvulkleur voor een grafiek in Java Slides instelt met Aspose.Slides voor Java. Het omkeren van de opvulkleur is een handige functie wanneer je negatieve waarden in een grafiek met een specifieke kleur wilt markeren. We bieden stapsgewijze instructies en broncode om dit te doen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

1. Aspose.Slides voor Java-bibliotheek geïnstalleerd.
2. Java-ontwikkelomgeving instellen.

## Stap 1: Een presentatie maken

Eerst moeten we een presentatie maken om onze grafiek aan toe te voegen. Je kunt de volgende code gebruiken om een presentatie te maken:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een grafiek toevoegen

Vervolgens voegen we een geclusterde kolomgrafiek toe aan de presentatie. Zo doe je dat:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Stap 3: Grafiekgegevens instellen

Laten we nu de grafiekgegevens instellen, inclusief reeksen en categorieën:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Nieuwe series en categorieën toevoegen
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Stap 4: Vul reeksgegevens in

Laten we nu de reeksgegevens voor de grafiek invullen:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Stap 5: Omgekeerde vulkleur instellen

Om de omgekeerde vulkleur voor de grafiekreeks in te stellen, kunt u de volgende code gebruiken:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

In de bovenstaande code stellen we de reeks in op het omkeren van de opvulkleur voor negatieve waarden en specificeren we de kleur voor de omgekeerde opvulling.

## Stap 6: Sla de presentatie op

Sla ten slotte de presentatie met de grafiek op:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor de kleurenkaart voor het omkeren van de opvulling in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Nieuwe series en categorieën toevoegen
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Neem de eerste grafiekserie en vul de seriegegevens in.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial hebben we je laten zien hoe je de omgekeerde opvulkleur voor een grafiek in Java Slides instelt met Aspose.Slides voor Java. Met deze functie kun je negatieve waarden in je grafieken markeren met een specifieke kleur, waardoor je gegevens visueel aantrekkelijker worden.

## Veelgestelde vragen

In deze sectie beantwoorden we een aantal veelgestelde vragen over het instellen van de omgekeerde opvulkleur voor een grafiek in Java Slides met behulp van Aspose.Slides voor Java.

### Hoe installeer ik Aspose.Slides voor Java?

U kunt Aspose.Slides voor Java installeren door de Aspose.Slides JAR-bestanden in uw Java-project op te nemen. U kunt de bibliotheek downloaden van de [Aspose.Slides voor Java downloadpagina](https://releases.aspose.com/slides/java/)Volg de installatie-instructies in de documentatie voor uw specifieke ontwikkelomgeving.

### Kan ik de kleur van de omgekeerde vulling in de grafiekserie aanpassen?

Ja, u kunt de kleur van de omgekeerde vulling in de grafiekreeks aanpassen. In het meegeleverde codevoorbeeld: `series.getInvertedSolidFillColor().setColor(Color.RED)` lijn stelt de kleur in op rood voor de omgekeerde vulling. U kunt vervangen `Color.RED` met een andere kleur naar keuze.

### Hoe kan ik het grafiektype in Aspose.Slides voor Java wijzigen?

U kunt het grafiektype wijzigen door de `ChartType` parameter bij het toevoegen van een grafiek aan de presentatie. In het codevoorbeeld gebruikten we `ChartType.ClusteredColumn`U kunt andere grafiektypen verkennen, zoals lijndiagrammen, staafdiagrammen, cirkeldiagrammen, enz., door de juiste `ChartType` enum-waarde.

### Hoe voeg ik meerdere gegevensreeksen toe aan een grafiek?

Om meerdere gegevensreeksen aan een grafiek toe te voegen, kunt u de `chart.getChartData().getSeries().add(...)` Methode voor elke reeks die u wilt toevoegen. Zorg ervoor dat u de juiste datapunten en labels voor elke reeks opgeeft om uw grafiek met meerdere reeksen te vullen.

### Is er een manier om andere aspecten van het uiterlijk van de grafiek aan te passen?

Ja, u kunt verschillende aspecten van de weergave van de grafiek aanpassen, zoals aslabels, titels, legenda's en meer, met Aspose.Slides voor Java. Raadpleeg de documentatie voor gedetailleerde instructies over het aanpassen van grafiekelementen en de weergave.

### Kan ik het diagram in verschillende formaten opslaan?

Ja, u kunt de grafiek in verschillende formaten opslaan met Aspose.Slides voor Java. In het gegeven codevoorbeeld hebben we de presentatie opgeslagen als een PPTX-bestand. U kunt verschillende formaten gebruiken. `SaveFormat` opties om het op te slaan in andere formaten, zoals PDF, PNG of SVG, afhankelijk van uw vereisten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}