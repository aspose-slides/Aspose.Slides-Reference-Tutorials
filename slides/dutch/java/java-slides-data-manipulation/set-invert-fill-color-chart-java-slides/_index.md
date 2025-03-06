---
title: Stel de kleurenkaart omkeren in in Java-dia's
linktitle: Stel de kleurenkaart omkeren in in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de omgekeerde opvulkleuren voor Java Slides-diagrammen kunt instellen met Aspose.Slides. Verbeter uw diagramvisualisaties met deze stapsgewijze handleiding en broncode.
weight: 22
url: /nl/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot het instellen van de kleurengrafiek Omkeren in Java-dia's

In deze zelfstudie laten we zien hoe u de omgekeerde vulkleur voor een diagram in Java Slides kunt instellen met Aspose.Slides voor Java. Het omkeren van de vulkleur is een handige functie als u negatieve waarden in een diagram met een specifieke kleur wilt markeren. We zullen stapsgewijze instructies en broncode verstrekken om dit te bereiken.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Aspose.Slides voor Java-bibliotheek geïnstalleerd.
2. Java-ontwikkelomgeving opgezet.

## Stap 1: Maak een presentatie

Eerst moeten we een presentatie maken waaraan we ons diagram kunnen toevoegen. U kunt de volgende code gebruiken om een presentatie te maken:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Voeg een diagram toe

Vervolgens voegen we een geclusterd kolomdiagram toe aan de presentatie. Hier ziet u hoe u het kunt doen:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Stap 3: Grafiekgegevens instellen

Laten we nu de diagramgegevens instellen, inclusief series en categorieën:

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

## Stap 4: Reeksgegevens invullen

Laten we nu de reeksgegevens voor het diagram invullen:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Stap 5: Stel de vulkleur omkeren in

Om de omgekeerde vulkleur voor de diagramserie in te stellen, kunt u de volgende code gebruiken:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

In de bovenstaande code stellen we de reeks zo in dat de vulkleur wordt omgekeerd voor negatieve waarden en specificeren we de kleur voor de omgekeerde vulling.

## Stap 6: Sla de presentatie op

Sla ten slotte de presentatie op met het diagram:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor het instellen van de omgekeerde vulkleurenkaart in Java-dia's

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
// Neem de eerste grafiekreeks en vul de reeksgegevens in.
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

In deze zelfstudie hebben we u laten zien hoe u de omgekeerde vulkleur voor een diagram in Java Slides instelt met behulp van Aspose.Slides voor Java. Met deze functie kunt u negatieve waarden in uw diagrammen markeren met een specifieke kleur, waardoor uw gegevens visueel informatiever worden.

## Veelgestelde vragen

In deze sectie behandelen we enkele veelgestelde vragen met betrekking tot het instellen van de omgekeerde vulkleur voor een diagram in Java Slides met behulp van Aspose.Slides voor Java.

### Hoe installeer ik Aspose.Slides voor Java?

 U kunt Aspose.Slides voor Java installeren door de Aspose.Slides JAR-bestanden in uw Java-project op te nemen. U kunt de bibliotheek downloaden via de[Aspose.Slides voor Java-downloadpagina](https://releases.aspose.com/slides/java/). Volg de installatie-instructies in de documentatie voor uw specifieke ontwikkelomgeving.

### Kan ik de kleur voor omgekeerde vulling in de diagramserie aanpassen?

Ja, u kunt de kleur voor de omgekeerde vulling in de diagramserie aanpassen. In het gegeven codevoorbeeld is de`series.getInvertedSolidFillColor().setColor(Color.RED)` lijn stelt de kleur in op rood voor de omgekeerde vulling. Je kunt vervangen`Color.RED` met een andere kleur naar keuze.

### Hoe kan ik het diagramtype in Aspose.Slides voor Java wijzigen?

 U kunt het diagramtype wijzigen door de`ChartType` parameter bij het toevoegen van een diagram aan de presentatie. In het codevoorbeeld gebruikten we`ChartType.ClusteredColumn` . U kunt andere diagramtypen verkennen, zoals lijndiagrammen, staafdiagrammen, cirkeldiagrammen, enz., door de juiste`ChartType` enum-waarde.

### Hoe voeg ik meerdere gegevensreeksen toe aan een diagram?

 Als u meerdere gegevensreeksen aan een diagram wilt toevoegen, kunt u de`chart.getChartData().getSeries().add(...)` methode voor elke serie die u wilt toevoegen. Zorg ervoor dat u voor elke reeks de juiste gegevenspunten en labels opgeeft, zodat uw diagram met meerdere reeksen kan worden gevuld.

### Is er een manier om andere aspecten van de weergave van het diagram aan te passen?

Ja, u kunt verschillende aspecten van de weergave van het diagram aanpassen, inclusief aslabels, titels, legenda's en meer met behulp van Aspose.Slides voor Java. Raadpleeg de documentatie voor gedetailleerde richtlijnen over het aanpassen van kaartelementen en het uiterlijk.

### Kan ik het diagram in verschillende formaten opslaan?

 Ja, u kunt het diagram in verschillende formaten opslaan met Aspose.Slides voor Java. In het meegeleverde codevoorbeeld hebben we de presentatie opgeslagen als een PPTX-bestand. Je kunt verschillende gebruiken`SaveFormat` opties om het op te slaan in andere formaten zoals PDF, PNG of SVG, afhankelijk van uw vereisten.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
