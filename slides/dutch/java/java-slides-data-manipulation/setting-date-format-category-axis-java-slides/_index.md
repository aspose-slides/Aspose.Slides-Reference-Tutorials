---
title: Datumnotatie instellen voor categorie-as in Java-dia's
linktitle: Datumnotatie instellen voor categorie-as in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u een datumnotatie instelt voor de categorie-as in een PowerPoint-diagram met Aspose.Slides voor Java. Stap-voor-stap handleiding met broncode.
type: docs
weight: 26
url: /nl/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Inleiding tot het instellen van het datumformaat voor de categorie-as in Java-dia's

In deze zelfstudie leren we hoe u een datumnotatie voor de categorie-as in een PowerPoint-grafiek kunt instellen met behulp van Aspose.Slides voor Java. Aspose.Slides voor Java is een krachtige bibliotheek waarmee u PowerPoint-presentaties programmatisch kunt maken, manipuleren en beheren.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Aspose.Slides voor Java-bibliotheek (u kunt deze downloaden van[hier](https://releases.aspose.com/slides/java/).
2. Java-ontwikkelomgeving opgezet.

## Stap 1: Maak een PowerPoint-presentatie

Eerst moeten we een PowerPoint-presentatie maken waarin we een diagram toevoegen. Zorg ervoor dat u de benodigde Aspose.Slides-klassen hebt geïmporteerd.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Voeg een diagram toe aan de dia

Laten we nu een diagram aan de PowerPoint-dia toevoegen. In dit voorbeeld gebruiken we een vlakdiagram.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Stap 3: Bereid grafiekgegevens voor

We zullen de grafiekgegevens en categorieën instellen. In dit voorbeeld gebruiken we datumcategorieën.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Datumcategorieën toevoegen
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Gegevensreeksen toevoegen
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Stap 4: Categorie-as aanpassen
Laten we nu de categorie-as aanpassen om datums in een specifiek formaat weer te geven (bijvoorbeeld jjjj).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Stap 5: Sla de presentatie op
Sla ten slotte de PowerPoint-presentatie op.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes een datumnotatie voor de categorie-as in een PowerPoint-grafiek ingesteld met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het instellen van het datumformaat voor de categorie-as in Java-dia's

```java
	// Het pad naar de documentenmap.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Conclusie

hebt met succes de datumnotatie voor de categorie-as in een Java Slides-diagram aangepast met Aspose.Slides voor Java. Hierdoor kunt u datumwaarden in het gewenste formaat in uw diagrammen presenteren. Voel je vrij om verdere aanpassingsopties te verkennen op basis van jouw specifieke vereisten.

## Veelgestelde vragen

### Hoe wijzig ik de datumnotatie voor de categorie-as?

 Om de datumnotatie voor de categorie-as te wijzigen, gebruikt u de`setNumberFormat` methode op de categorie-as en geef het gewenste datumnotatiepatroon op, zoals "jjjj-MM-dd" of "MM/jjjj". Zorg ervoor dat u dit instelt`setNumberFormatLinkedToSource(false)` om het standaardformaat te overschrijven.

### Kan ik verschillende datumnotaties gebruiken voor verschillende diagrammen in dezelfde presentatie?

Ja, u kunt binnen dezelfde presentatie verschillende datumnotaties instellen voor categorie-assen in verschillende diagrammen. Pas indien nodig eenvoudig de categorie-as voor elk diagram aan.

### Hoe voeg ik meer gegevenspunten toe aan het diagram?

 Als u meer gegevenspunten aan het diagram wilt toevoegen, gebruikt u de`getDataPoints().addDataPointForLineSeries`methode op de gegevensreeksen en geef de gegevenswaarden op.