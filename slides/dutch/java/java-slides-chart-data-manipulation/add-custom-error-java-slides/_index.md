---
title: Aangepaste fout toevoegen in Java-dia's
linktitle: Aangepaste fout toevoegen in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u aangepaste foutbalken kunt toevoegen aan PowerPoint-diagrammen in Java Slides met behulp van Aspose.Slides. Stapsgewijze handleiding met broncode voor nauwkeurige datavisualisatie.
weight: 11
url: /nl/java/chart-data-manipulation/add-custom-error-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot het toevoegen van aangepaste foutbalken in Java-dia's met behulp van Aspose.Slides

In deze zelfstudie leert u hoe u aangepaste foutbalken kunt toevoegen aan een diagram in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java. Foutbalken zijn handig voor het weergeven van variabiliteit of onzekerheid in gegevenspunten in een diagram.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Aspose.Slides voor Java-bibliotheek geïnstalleerd en geconfigureerd in uw project.
- Er is een Java-ontwikkelomgeving opgezet.

## Stap 1: Maak een lege presentatie

Maak eerst een lege PowerPoint-presentatie.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een bellendiagram toe

Vervolgens voegen we een bellendiagram toe aan de presentatie.

```java
// Een bellendiagram maken
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Stap 3: aangepaste foutbalken toevoegen

Laten we nu aangepaste foutbalken toevoegen aan de diagramreeks.

```java
// Aangepaste foutbalken toevoegen en hun formaat instellen
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Stap 4: Foutbalkgegevens instellen

In deze stap hebben we toegang tot de gegevenspunten van de diagramserie en stellen we de aangepaste foutbalkwaarden voor elk punt in.

```java
// Toegang krijgen tot gegevenspunten uit diagramreeksen en foutbalkwaarden instellen voor individuele punten
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Foutbalken instellen voor kaartreekspunten
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie op met de aangepaste foutbalken.

```java
// Presentatie opslaan
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes aangepaste foutbalken toegevoegd aan een diagram in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het toevoegen van aangepaste fouten in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
try
{
	// Een bellendiagram maken
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Aangepaste foutbalken toevoegen en het formaat ervan instellen
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Toegang krijgen tot gegevenspunten uit diagramseries en foutbalkwaarden instellen voor individuele punten
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Foutbalken instellen voor kaartreekspunten
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Presentatie opslaan
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze uitgebreide zelfstudie hebt u geleerd hoe u uw PowerPoint-presentaties kunt verbeteren door aangepaste foutbalken aan diagrammen toe te voegen met behulp van Aspose.Slides voor Java. Foutbalken bieden waardevolle inzichten in de variabiliteit en onzekerheid van gegevens, waardoor uw diagrammen informatiever en visueel aantrekkelijker worden.

## Veelgestelde vragen

### Hoe pas ik het uiterlijk van foutbalken aan?

 U kunt het uiterlijk van foutbalken aanpassen door de eigenschappen van het`IErrorBarsFormat` object, zoals lijnstijl, lijnkleur en foutbalkbreedte.

### Kan ik foutbalken toevoegen aan andere diagramtypen?

Ja, u kunt foutbalken toevoegen aan verschillende diagramtypen die worden ondersteund door Aspose.Slides voor Java, inclusief staafdiagrammen, lijndiagrammen en spreidingsdiagrammen.

### Hoe stel ik verschillende foutbalkwaarden in voor elk gegevenspunt?

kunt de gegevenspunten doorlopen en voor elk punt aangepaste foutbalkwaarden instellen, zoals weergegeven in de bovenstaande code.

### Is het mogelijk om foutbalken voor specifieke gegevenspunten te verbergen?

 Ja, u kunt de zichtbaarheid van foutbalken voor individuele gegevenspunten bepalen door de`setVisible` eigendom van de`IErrorBarsFormat` voorwerp.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
