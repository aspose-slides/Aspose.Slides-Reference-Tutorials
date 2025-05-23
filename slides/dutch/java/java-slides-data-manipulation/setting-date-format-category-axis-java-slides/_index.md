---
"description": "Leer hoe u een datumnotatie instelt voor de categorie-as in een PowerPoint-grafiek met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "Datumnotatie instellen voor categorie-as in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Datumnotatie instellen voor categorie-as in Java-dia's"
"url": "/nl/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Datumnotatie instellen voor categorie-as in Java-dia's


## Inleiding tot het instellen van de datumnotatie voor de categorie-as in Java-dia's

In deze tutorial leren we hoe je een datumnotatie instelt voor de categorie-as in een PowerPoint-grafiek met behulp van Aspose.Slides voor Java. Aspose.Slides voor Java is een krachtige bibliotheek waarmee je PowerPoint-presentaties programmatisch kunt maken, bewerken en beheren.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:

1. Aspose.Slides voor Java-bibliotheek (u kunt deze downloaden van [hier](https://releases.aspose.com/slides/java/).
2. Java-ontwikkelomgeving instellen.

## Stap 1: Maak een PowerPoint-presentatie

Eerst moeten we een PowerPoint-presentatie maken waaraan we een grafiek toevoegen. Zorg ervoor dat je de benodigde Aspose.Slides-klassen hebt geïmporteerd.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Voeg een grafiek toe aan de dia

Laten we nu een grafiek toevoegen aan de PowerPoint-dia. In dit voorbeeld gebruiken we een vlakdiagram.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Stap 3: Grafiekgegevens voorbereiden

We gaan de grafiekgegevens en -categorieën instellen. In dit voorbeeld gebruiken we datumcategorieën.

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

## Stap 4: Pas de categorie-as aan
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

Dat is alles! Je hebt met succes een datumnotatie ingesteld voor de categorie-as in een PowerPoint-grafiek met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het instellen van de datumnotatie voor de categorie-as in Java-dia's

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

U hebt de datumnotatie voor de categorie-as in een Java Slides-diagram succesvol aangepast met Aspose.Slides voor Java. Hiermee kunt u datumwaarden in de gewenste notatie in uw diagrammen weergeven. U kunt gerust verdere aanpassingsopties verkennen op basis van uw specifieke vereisten.

## Veelgestelde vragen

### Hoe wijzig ik de datumnotatie voor de categorie-as?

Om de datumnotatie voor de categorie-as te wijzigen, gebruikt u de `setNumberFormat` methode op de categorie-as en geef het gewenste datumnotatiepatroon op, zoals "jjjj-MM-dd" of "MM/jjjj". Zorg ervoor dat u `setNumberFormatLinkedToSource(false)` om de standaardopmaak te negeren.

### Kan ik verschillende datumnotaties gebruiken voor verschillende grafieken in dezelfde presentatie?

Ja, u kunt verschillende datumnotaties instellen voor categorieassen in verschillende grafieken binnen dezelfde presentatie. Pas de categorieas voor elke grafiek eenvoudig naar wens aan.

### Hoe voeg ik meer datapunten toe aan de grafiek?

Om meer datapunten aan de grafiek toe te voegen, gebruikt u de `getDataPoints().addDataPointForLineSeries` methode op de gegevensreeks en geef de gegevenswaarden op.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}