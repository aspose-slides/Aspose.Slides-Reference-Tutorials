---
"description": "Lär dig hur du ställer in ett datumformat för kategoriaxeln i ett PowerPoint-diagram med Aspose.Slides för Java. Steg-för-steg-guide med källkod."
"linktitle": "Ställa in datumformat för kategoriaxeln i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställa in datumformat för kategoriaxeln i Java Slides"
"url": "/sv/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställa in datumformat för kategoriaxeln i Java Slides


## Introduktion till att ställa in datumformat för kategoriaxeln i Java-bilder

den här handledningen lär vi oss hur man ställer in ett datumformat för kategoriaxeln i ett PowerPoint-diagram med hjälp av Aspose.Slides för Java. Aspose.Slides för Java är ett kraftfullt bibliotek som låter dig skapa, manipulera och hantera PowerPoint-presentationer programmatiskt.

## Förkunskapskrav

Innan du börjar, se till att du har följande:

1. Aspose.Slides för Java-biblioteket (du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).
2. Java-utvecklingsmiljö konfigurerad.

## Steg 1: Skapa en PowerPoint-presentation

Först behöver vi skapa en PowerPoint-presentation där vi lägger till ett diagram. Se till att du har importerat de nödvändiga Aspose.Slides-klasserna.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett diagram i bilden

Nu ska vi lägga till ett diagram i PowerPoint-bilden. Vi använder ett ytdiagram i det här exemplet.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Steg 3: Förbered diagramdata

Vi kommer att ställa in diagramdata och kategorier. I det här exemplet använder vi datumkategorier.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Lägga till datumkategorier
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Lägga till dataserier
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Steg 4: Anpassa kategoriaxeln
Nu ska vi anpassa kategoriaxeln för att visa datum i ett specifikt format (t.ex. åååå).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Steg 5: Spara presentationen
Spara slutligen PowerPoint-presentationen.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Det var allt! Du har framgångsrikt ställt in ett datumformat för kategoriaxeln i ett PowerPoint-diagram med hjälp av Aspose.Slides för Java.

## Komplett källkod för att ställa in datumformat för kategoriaxeln i Java Slides

```java
	// Sökvägen till dokumentkatalogen.
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

##Slutsats

Du har framgångsrikt anpassat datumformatet för kategoriaxeln i ett Java Slides-diagram med hjälp av Aspose.Slides för Java. Detta gör att du kan presentera datumvärden i önskat format i dina diagram. Utforska gärna ytterligare anpassningsalternativ baserat på dina specifika krav.

## Vanliga frågor

### Hur ändrar jag datumformatet för kategoriaxeln?

För att ändra datumformatet för kategoriaxeln, använd `setNumberFormat` metoden på kategoriaxeln och ange önskat datumformatmönster, till exempel "åååå-MM-dd" eller "MM/åååå". Se till att ställa in `setNumberFormatLinkedToSource(false)` för att åsidosätta standardformatet.

### Kan jag använda olika datumformat för olika diagram i samma presentation?

Ja, du kan ställa in olika datumformat för kategoriaxlar i olika diagram inom samma presentation. Anpassa helt enkelt kategoriaxeln för varje diagram efter behov.

### Hur lägger jag till fler datapunkter i diagrammet?

För att lägga till fler datapunkter i diagrammet, använd `getDataPoints().addDataPointForLineSeries` metoden på dataserien och ange datavärdena.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}