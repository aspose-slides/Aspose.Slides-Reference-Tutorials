---
title: Nastavení formátu data pro osu kategorie v Java Slides
linktitle: Nastavení formátu data pro osu kategorie v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit formát data pro osu kategorií v grafu PowerPoint pomocí Aspose.Slides for Java. Průvodce krok za krokem se zdrojovým kódem.
type: docs
weight: 26
url: /cs/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Úvod do nastavení formátu data pro osu kategorií v Java Slides

tomto tutoriálu se naučíme, jak nastavit formát data pro osu kategorií v grafu PowerPoint pomocí Aspose.Slides pro Java. Aspose.Slides for Java je výkonná knihovna, která vám umožňuje programově vytvářet, manipulovat a spravovat prezentace PowerPoint.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1.  Knihovna Aspose.Slides for Java (můžete si ji stáhnout z[tady](https://releases.aspose.com/slides/java/).
2. Nastavení vývojového prostředí Java.

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve si musíme vytvořit powerpointovou prezentaci, kam přidáme graf. Ujistěte se, že jste importovali potřebné třídy Aspose.Slides.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf do snímku

Nyní přidáme graf na snímek aplikace PowerPoint. V tomto příkladu použijeme plošný graf.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Krok 3: Připravte data grafu

Nastavíme data a kategorie grafu. V tomto příkladu použijeme kategorie data.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Přidávání kategorií data
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Přidávání datových řad
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Krok 4: Přizpůsobte osu kategorií
Nyní přizpůsobme osu kategorií tak, aby zobrazovala data v určitém formátu (např. rrrr).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Krok 5: Uložte prezentaci
Nakonec uložte prezentaci v PowerPointu.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

je to! Úspěšně jste nastavili formát data pro osu kategorií v grafu PowerPoint pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro nastavení formátu data pro osu kategorií v Java Slides

```java
	// Cesta k adresáři dokumentů.
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
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
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

##Závěr

Úspěšně jste přizpůsobili formát data pro osu kategorií v grafu Java Slides pomocí Aspose.Slides for Java. To vám umožní prezentovat hodnoty data v požadovaném formátu v grafech. Neváhejte a prozkoumejte další možnosti přizpůsobení na základě vašich konkrétních požadavků.

## FAQ

### Jak změním formát data pro osu kategorií?

 Chcete-li změnit formát data pro osu kategorií, použijte`setNumberFormat` metodu na ose kategorií a zadejte požadovaný vzor formátu data, například "rrrr-MM-dd" nebo "MM/rrrr". Nezapomeňte nastavit`setNumberFormatLinkedToSource(false)` pro přepsání výchozího formátu.

### Mohu použít různé formáty data pro různé grafy ve stejné prezentaci?

Ano, můžete nastavit různé formáty data pro osy kategorií v různých grafech ve stejné prezentaci. Jednoduše přizpůsobte osu kategorií pro každý graf podle potřeby.

### Jak přidám do grafu další datové body?

 Chcete-li do grafu přidat další datové body, použijte`getDataPoints().addDataPointForLineSeries` na datové řadě a poskytnout hodnoty dat.