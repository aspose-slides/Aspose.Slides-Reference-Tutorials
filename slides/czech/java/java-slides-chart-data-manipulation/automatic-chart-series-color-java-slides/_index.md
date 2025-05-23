---
"description": "Naučte se, jak vytvářet dynamické grafy s automatickým barevným řazením v prezentacích PowerPoint pomocí Aspose.Slides pro Javu. Vylepšete své vizualizace dat bez námahy."
"linktitle": "Automatické vybarvení sérií grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Automatické vybarvení sérií grafů v Javě Slides"
"url": "/cs/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatické vybarvení sérií grafů v Javě Slides


## Úvod do automatického vybarvování sérií grafů v Aspose.Slides pro Javu

V tomto tutoriálu se podíváme na to, jak vytvořit prezentaci v PowerPointu s grafem pomocí Aspose.Slides pro Javu a jak nastavit automatické barvy výplně pro série grafů. Automatické barvy výplně mohou vaše grafy vizuálně zatraktivnit a ušetřit vám čas tím, že nechají knihovnu vybrat barvy za vás.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu nainstalovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci

Nejprve si vytvoříme novou prezentaci v PowerPointu a přidáme do ní snímek.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidání grafu do snímku

Dále na snímek přidáme klastrovaný sloupcový graf. Také nastavíme první řadu tak, aby zobrazovala hodnoty.

```java
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Nastavit první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Krok 3: Naplnění grafu daty

Nyní naplníme graf daty. Začneme odstraněním výchozích generovaných řad a kategorií a poté přidáme nové řady a kategorie.

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat výchozí generované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nových sérií
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Krok 4: Naplnění dat série

Naplníme data série pro sérii 1 i sérii 2.

```java
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vezměte si druhou sérii grafů
series = chart.getChartData().getSeries().get_Item(1);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Krok 5: Nastavení automatické barvy výplně pro sérii

Nyní nastavme automatické barvy výplně pro sérii grafů. Díky tomu knihovna vybere barvy za nás.

```java
// Nastavení automatické barvy výplně pro série
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Krok 6: Uložte prezentaci

Nakonec uložíme prezentaci s grafem do souboru PowerPointu.

```java
// Uložit prezentaci s grafem
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro automatické vybarvení sérií grafů v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slide = presentation.getSlides().get_Item(0);
	// Přidat graf s výchozími daty
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Nastavit první sérii na Zobrazit hodnoty
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání pracovního listu s daty grafu
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Smazat výchozí generované série a kategorie
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Přidávání nových sérií
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Přidávání nových kategorií
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Vezměte si první sérii grafů
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Nyní se naplňují data série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Nastavení automatické barvy výplně pro série
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Vezměte si druhou sérii grafů
	series = chart.getChartData().getSeries().get_Item(1);
	// Nyní se naplňují data série
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

tomto tutoriálu jsme se naučili, jak vytvořit prezentaci v PowerPointu s grafem pomocí Aspose.Slides pro Javu a nastavit automatické barvy výplně pro série grafů. Automatické barvy mohou vylepšit vizuální atraktivitu vašich grafů a učinit vaše prezentace poutavějšími. Graf si můžete dále přizpůsobit podle potřeby a specifických požadavků.

## Často kladené otázky

### Jak nastavím automatické barvy výplně pro série grafů v Aspose.Slides pro Javu?

Chcete-li nastavit automatické barvy výplně pro série grafů v Aspose.Slides pro Javu, použijte následující kód:

```java
// Nastavení automatické barvy výplně pro série
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Tento kód umožní knihovně automaticky vybrat barvy pro sérii grafů.

### Mohu si v případě potřeby upravit barvy grafu?

Ano, barvy grafu si můžete upravit podle potřeby. V uvedeném příkladu jsme použili automatické barvy výplně, ale můžete nastavit konkrétní barvy úpravou `FillType` a `SolidFillColor` vlastnosti formátu seriálu.

### Jak mohu do grafu přidat další řady nebo kategorie?

Chcete-li do grafu přidat další řady nebo kategorie, použijte `getSeries()` a `getCategories()` metody grafu `ChartData` objekt. Nové série a kategorie můžete přidat zadáním jejich dat a popisků.

### Je možné graf a popisky dále formátovat?

Ano, graf, sérii a popisky můžete dále formátovat dle potřeby. Aspose.Slides pro Javu nabízí rozsáhlé možnosti formátování grafů, včetně písem, barev, stylů a dalších. Další podrobnosti o možnostech formátování naleznete v dokumentaci.

### Kde najdu více informací o práci s Aspose.Slides pro Javu?

Pro více informací a podrobnou dokumentaci k Aspose.Slides pro Javu můžete navštívit referenční dokumentaci. [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}