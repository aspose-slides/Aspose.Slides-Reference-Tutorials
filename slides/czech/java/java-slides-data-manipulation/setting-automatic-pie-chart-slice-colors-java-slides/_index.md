---
"description": "Naučte se, jak vytvářet dynamické koláčové grafy s automatickými barvami řezů v prezentacích v PowerPointu v Javě pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem."
"linktitle": "Nastavení automatických barev výsečů koláčového grafu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení automatických barev výsečů koláčového grafu v Java Slides"
"url": "/cs/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení automatických barev výsečů koláčového grafu v Java Slides


## Úvod do automatického nastavení barev výsečů koláčového grafu v Java Slides

V tomto tutoriálu se podíváme na to, jak vytvořit koláčový graf v prezentaci v PowerPointu pomocí Aspose.Slides pro Javu a nastavit automatické barvy řezů pro graf. Poskytneme podrobný návod spolu se zdrojovým kódem.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z webových stránek Aspose: [Stáhněte si Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované balíčky

Nejprve je třeba importovat potřebné balíčky z Aspose.Slides pro Javu:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Krok 2: Vytvořte prezentaci v PowerPointu

Vytvořte instanci `Presentation` třída pro vytvoření nové prezentace v PowerPointu:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 3: Přidání snímku

Otevřete první snímek prezentace a přidejte do něj graf s výchozími daty:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Krok 4: Nastavení názvu grafu

Nastavte název grafu:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 5: Konfigurace dat grafu

Nastavte graf tak, aby zobrazoval hodnoty pro první sérii, a nakonfigurujte data grafu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 6: Přidání kategorií a sérií

Přidejte do grafu nové kategorie a série:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Krok 7: Naplnění dat série

Naplňte data řady pro koláčový graf:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Krok 8: Povolte různé barvy řezů

Povolit různé barvy řezů pro koláčový graf:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Krok 9: Uložte prezentaci

Nakonec uložte prezentaci do souboru PowerPointu:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro automatické nastavení barev výsečů koláčového grafu v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation presentation = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slides = presentation.getSlides().get_Item(0);
	// Přidat graf s výchozími daty
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Název grafu nastavení
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Nastavit první sérii na Zobrazit hodnoty
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání pracovního listu s daty grafu
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Smazat výchozí generované série a kategorie
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Přidávání nových kategorií
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Přidávání nových sérií
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Nyní se naplňují data série
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

Úspěšně jste vytvořili koláčový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu a nakonfigurovali jste jej tak, aby měl automatické barvy řezů. Tato podrobná příručka vám poskytne potřebný zdrojový kód k dosažení tohoto cíle. Graf a prezentaci si můžete dále přizpůsobit dle potřeby.

## Často kladené otázky

### Jak mohu přizpůsobit barvy jednotlivých výsečí v koláčovém grafu?

Chcete-li přizpůsobit barvy jednotlivých výsečí v koláčovém grafu, můžete použít `getAutomaticSeriesColors` metoda pro načtení výchozího barevného schématu a následnou úpravu barev podle potřeby. Zde je příklad:

```java
// Získejte výchozí barevné schéma
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Upravte barvy dle potřeby
colors.get_Item(0).setColor(Color.RED); // Nastavte barvu prvního řezu na červenou
colors.get_Item(1).setColor(Color.BLUE); // Nastavte barvu druhého řezu na modrou
// V případě potřeby přidejte další barevné úpravy
```

### Jak mohu přidat legendu do koláčového grafu?

Chcete-li do koláčového grafu přidat legendu, můžete použít `getLegend` metodu a nakonfigurujte ji takto:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Nastavení pozice legendy
legend.setOverlay(true); // Zobrazit legendu nad grafem
```

### Mohu změnit písmo a styl titulku?

Ano, písmo a styl názvu můžete změnit. Pro nastavení písma a stylu názvu použijte následující kód:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Nastavit velikost písma
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Zvýrazněte název tučně
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Změnit název na kurzívu
```

Velikost písma, tučnost a kurzívu můžete upravit dle potřeby.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}