---
title: Automatická barva řady grafů v Java Slides
linktitle: Automatická barva řady grafů v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet dynamické grafy s automatickou barvou řady v prezentacích PowerPoint pomocí Aspose.Slides for Java. Vylepšete své vizualizace dat bez námahy.
type: docs
weight: 14
url: /cs/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Úvod do automatických barev řady grafů v Aspose.Slides pro Javu

tomto tutoriálu prozkoumáme, jak vytvořit prezentaci v PowerPointu s grafem pomocí Aspose.Slides pro Java a nastavit automatické barvy výplně pro řady grafů. Automatické barvy výplně mohou učinit vaše grafy vizuálně přitažlivějšími a ušetřit vám čas tím, že necháte knihovnu, aby barvy vybrala za vás.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu nainstalovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci

Nejprve vytvoříme novou PowerPoint prezentaci a přidáme do ní snímek.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte graf do snímku

Dále na snímek přidáme seskupený sloupcový graf. Nastavíme také první řadu tak, aby zobrazovala hodnoty.

```java
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Nastavte první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Krok 3: Vyplňte data grafu

Nyní graf naplníme daty. Začneme odstraněním výchozích vygenerovaných sérií a kategorií a poté přidáním nových sérií a kategorií.

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat výchozí vygenerované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nové série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Krok 4: Vyplňte data série

Vyplníme data série pro sérii 1 i sérii 2.

```java
// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Krok 5: Nastavte automatickou barvu výplně pro řadu

Nyní nastavíme automatické barvy výplně pro řadu grafů. Díky tomu za nás knihovna vybere barvy.

```java
// Nastavení automatické barvy výplně pro série
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Krok 6: Uložte prezentaci

Nakonec prezentaci s grafem uložíme do souboru PowerPoint.

```java
// Uložit prezentaci s grafem
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro automatické barvy řady grafů v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slide = presentation.getSlides().get_Item(0);
	// Přidat graf s výchozími daty
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Nastavte první sérii na Zobrazit hodnoty
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání listu dat grafu
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Smazat výchozí vygenerované série a kategorie
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Přidávání nové série
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Přidávání nových kategorií
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Vezměte první sérii grafů
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Nyní se vyplňují data série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Nastavení automatické barvy výplně pro série
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Vezměte druhou řadu grafů
	series = chart.getChartData().getSeries().get_Item(1);
	// Nyní se vyplňují data série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Nastavení barvy výplně pro sérii
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Uložit prezentaci s grafem
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak vytvořit prezentaci v PowerPointu s grafem pomocí Aspose.Slides pro Java a nastavit automatické barvy výplně pro řady grafů. Automatické barvy mohou zlepšit vizuální přitažlivost vašich grafů a učinit vaše prezentace poutavější. Graf můžete dále upravit podle potřeby pro vaše specifické požadavky.

## FAQ

### Jak nastavím automatické barvy výplně pro řady grafů v Aspose.Slides pro Java?

Chcete-li nastavit automatické barvy výplně pro řady grafů v Aspose.Slides pro Java, použijte následující kód:

```java
// Nastavení automatické barvy výplně pro série
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Tento kód umožní knihovně automaticky vybrat barvy pro řadu grafů.

### Mohu v případě potřeby upravit barvy grafu?

 Ano, barvy grafu si můžete přizpůsobit podle potřeby. V uvedeném příkladu jsme použili automatické barvy výplně, ale můžete nastavit konkrétní barvy úpravou`FillType` a`SolidFillColor` vlastnosti formátu série.

### Jak mohu do grafu přidat další série nebo kategorie?

 Chcete-li do grafu přidat další série nebo kategorie, použijte`getSeries()` a`getCategories()` metody grafu`ChartData` objekt. Můžete přidat nové série a kategorie zadáním jejich dat a štítků.

### Je možné dále formátovat graf a štítky?

Ano, podle potřeby můžete dále formátovat graf, řadu a štítky. Aspose.Slides for Java poskytuje rozsáhlé možnosti formátování grafů, včetně písem, barev, stylů a dalších. Další podrobnosti o možnostech formátování naleznete v dokumentaci.

### Kde najdu další informace o práci s Aspose.Slides for Java?

 Pro více informací a podrobnou dokumentaci k Aspose.Slides for Java můžete navštívit referenční dokumentaci[tady](https://reference.aspose.com/slides/java/).