---
"description": "Naučte se, jak nastavit formát data pro osu kategorií v grafu PowerPoint pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem."
"linktitle": "Nastavení formátu data pro osu kategorií v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení formátu data pro osu kategorií v Java Slides"
"url": "/cs/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení formátu data pro osu kategorií v Java Slides


## Úvod do nastavení formátu data pro osu kategorií v aplikaci Java Slides

tomto tutoriálu se naučíme, jak nastavit formát data pro osu kategorií v grafu PowerPoint pomocí knihovny Aspose.Slides pro Javu. Aspose.Slides pro Javu je výkonná knihovna, která umožňuje programově vytvářet, manipulovat a spravovat prezentace v PowerPointu.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Knihovna Aspose.Slides pro Javu (můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).
2. Nastavení vývojového prostředí v Javě.

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve musíme vytvořit prezentaci v PowerPointu, do které přidáme graf. Ujistěte se, že jste importovali potřebné třídy Aspose.Slides.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu do snímku

Nyní přidejme do snímku PowerPointu graf. V tomto příkladu použijeme plošný graf.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Krok 3: Příprava dat grafu

Nastavíme data a kategorie grafu. V tomto příkladu použijeme kategorie data.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Přidávání kategorií dat
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

## Krok 4: Úprava osy kategorií
Nyní si upravme osu kategorií tak, aby zobrazovala data v určitém formátu (např. rrrr).

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

To je vše! Úspěšně jste nastavili formát data pro osu kategorií v grafu PowerPoint pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro nastavení formátu data pro osu kategorií v Java Slides

```java
	// Cesta k adresáři s dokumenty.
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

##Závěr

Úspěšně jste upravili formát data pro osu kategorií v grafu Java Slides pomocí Aspose.Slides pro Javu. To vám umožní prezentovat hodnoty data v požadovaném formátu v grafech. Neváhejte a prozkoumejte další možnosti přizpůsobení na základě vašich specifických požadavků.

## Často kladené otázky

### Jak změním formát data pro osu kategorií?

Chcete-li změnit formát data pro osu kategorií, použijte `setNumberFormat` metodu na ose kategorií a zadejte požadovaný formát data, například „rrrr-MM-dd“ nebo „MM/rrrr“. Ujistěte se, že jste nastavili `setNumberFormatLinkedToSource(false)` přepsat výchozí formát.

### Mohu v jedné prezentaci použít různé formáty data pro různé grafy?

Ano, v rámci jedné prezentace můžete nastavit různé formáty data pro osy kategorií v různých grafech. Jednoduše si osu kategorií pro každý graf přizpůsobte podle potřeby.

### Jak mohu do grafu přidat další datové body?

Chcete-li do grafu přidat další datové body, použijte `getDataPoints().addDataPointForLineSeries` metodu na datové řadě a poskytněte datové hodnoty.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}