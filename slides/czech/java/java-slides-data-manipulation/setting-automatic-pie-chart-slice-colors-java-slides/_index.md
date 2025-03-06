---
title: Nastavení automatických barev výsečového grafu v Java Slides
linktitle: Nastavení automatických barev výsečového grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet dynamické výsečové grafy s automatickými barvami řezů v prezentacích Java PowerPoint pomocí Aspose.Slides for Java. Průvodce krok za krokem se zdrojovým kódem.
weight: 24
url: /cs/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení automatických barev výsečového grafu v Java Slides


## Úvod do nastavení automatických barev výsečového grafu v Java Slides

V tomto tutoriálu prozkoumáme, jak vytvořit výsečový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java a nastavit automatické barvy řezů pro graf. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z webu Aspose:[Stáhněte si Aspose.Slides pro Java](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované balíčky

Nejprve musíte importovat potřebné balíčky z Aspose.Slides for Java:

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

 Vytvořte instanci`Presentation` třídy k vytvoření nové prezentace PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 3: Přidejte snímek

Otevřete první snímek prezentace a přidejte do něj graf s výchozími daty:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Krok 4: Nastavte název grafu

Nastavte název grafu:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 5: Konfigurace dat grafu

Nastavte graf tak, aby zobrazoval hodnoty pro první řadu a nakonfigurujte data grafu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 6: Přidejte kategorie a série

Přidejte do grafu nové kategorie a série:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Krok 7: Vyplňte data série

Vyplňte data řady pro výsečový graf:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Krok 8: Povolte různé barvy řezů

Povolit různé barvy řezů pro výsečový graf:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Krok 9: Uložte prezentaci

Nakonec uložte prezentaci do souboru PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení automatických barev výsečového grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Třída okamžité prezentace, která představuje soubor PPTX
Presentation presentation = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slides = presentation.getSlides().get_Item(0);
	// Přidat graf s výchozími daty
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Nastavení názvu grafu
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Nastavte první sérii na Zobrazit hodnoty
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání listu dat grafu
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Smazat výchozí vygenerované série a kategorie
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Přidávání nových kategorií
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Přidávání nové série
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Nyní se vyplňují data série
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

Úspěšně jste vytvořili výsečový graf v prezentaci PowerPoint pomocí Aspose.Slides for Java a nakonfigurovali jste jej tak, aby měl automatické barvy řezů. Tento podrobný průvodce vám poskytne potřebný zdrojový kód, abyste toho dosáhli. Graf a prezentaci můžete dále upravit podle potřeby.

## FAQ

### Jak mohu přizpůsobit barvy jednotlivých řezů v koláčovém grafu?

 Chcete-li přizpůsobit barvy jednotlivých řezů ve výsečovém grafu, můžete použít`getAutomaticSeriesColors` metodu pro načtení výchozího barevného schématu a následné úpravy barev podle potřeby. Zde je příklad:

```java
//Získejte výchozí barevné schéma
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Upravte barvy podle potřeby
colors.get_Item(0).setColor(Color.RED); // Nastavte barvu prvního plátku na červenou
colors.get_Item(1).setColor(Color.BLUE); // Nastavte barvu druhého plátku na modrou
// Podle potřeby přidejte další barevné úpravy
```

### Jak mohu přidat legendu do koláčového grafu?

 Chcete-li přidat legendu do výsečového grafu, můžete použít`getLegend` metodu a nakonfigurujte ji následovně:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Nastavte polohu legendy
legend.setOverlay(true); // Zobrazte legendu nad grafem
```

### Mohu změnit písmo a styl nadpisu?

Ano, můžete změnit písmo a styl nadpisu. K nastavení písma a stylu nadpisu použijte následující kód:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Nastavte velikost písma
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Označte nadpis tučně
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Udělejte nadpis kurzívou
```

Podle potřeby můžete upravit velikost písma, tučné písmo a styl kurzívy.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
