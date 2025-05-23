---
"description": "Naučte se, jak vytvářet radarové grafy v prezentacích v PowerPointu v Javě pomocí rozhraní Aspose.Slides pro Java API."
"linktitle": "Vytváření radarových grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vytváření radarových grafů v Javě Slides"
"url": "/cs/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytváření radarových grafů v Javě Slides


## Úvod do vytváření radarového grafu v Javě – Slides

tomto tutoriálu vás provedeme procesem vytvoření radarového grafu pomocí rozhraní Aspose.Slides pro Java API. Radarové grafy jsou užitečné pro vizualizaci dat v kruhovém vzoru, což usnadňuje porovnávání více datových řad. Poskytneme podrobné pokyny spolu se zdrojovým kódem Javy.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu integrovanou knihovnu Aspose.Slides pro Javu. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Příprava prezentace

Začněme tím, že si vytvoříme novou prezentaci v PowerPointu a přidáme do ní snímek.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Krok 2: Přidání radarového grafu

Dále na snímek přidáme radarový graf. Určíme jeho polohu a rozměry.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Krok 3: Nastavení dat grafu

Nyní nastavíme data grafu. To zahrnuje vytvoření datového sešitu, přidání kategorií a přidání řad.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Nastavit název grafu
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Smazat výchozí generované série a kategorie
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Přidávání nových kategorií
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Přidávání nových sérií
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Krok 4: Naplnění dat série

Nyní naplníme data série pro náš radarový graf.

```java
// Naplnění dat série pro sérii 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Nastavit barvu série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Naplnění dat série pro sérii 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Nastavit barvu série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Krok 5: Úprava os a legend

Pojďme si přizpůsobit osu a legendy pro náš radarový graf.

```java
// Nastavení pozice legendy
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Nastavení vlastností textu osy kategorií
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Nastavení vlastností textu legendy
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Nastavení vlastností textu osy hodnot
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Nastavení formátu čísel osy hodnot
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Nastavení hodnoty hlavní jednotky v grafu
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Krok 6: Uložení prezentace

Nakonec uložte vygenerovanou prezentaci s radarovým grafem

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili radarový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Nyní můžete tento příklad dále přizpůsobit svým specifickým potřebám.

## Kompletní zdrojový kód pro vytváření radarových grafů v Javě Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide sld = pres.getSlides().get_Item(0);
	// Přidat radarový graf
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání dat grafu z pracovního listu
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Nastavit název grafu
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Smazat výchozí generované série a kategorie
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Přidávání nových kategorií
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Přidávání nových sérií
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Nyní se naplňují data série
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Nastavit barvu série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Nyní se naplňují další sériová data
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Nastavit barvu série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Nastavení pozice legendy
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Nastavení vlastností textu osy kategorií
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Nastavení vlastností textu legendy
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Nastavení vlastností textu osy hodnot
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Nastavení formátu čísel osy hodnot
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Nastavení hodnoty hlavní jednotky v grafu
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Uložit vygenerovanou prezentaci
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit radarový graf v prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Tyto koncepty můžete použít k efektivní vizualizaci a prezentaci dat ve vašich aplikacích v Javě.

## Často kladené otázky

### Jak mohu změnit název grafu?

Chcete-li změnit název grafu, upravte následující řádek:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Mohu do radarového grafu přidat další datové řady?

Ano, můžete přidat další datové řady podle kroků v „kroku 3“ a „kroku 4“ pro každou další řadu, kterou chcete zahrnout.

### Jak si mohu přizpůsobit barvy grafu?

Barvy série můžete přizpůsobit úpravou čar, které určují `SolidFillColor` vlastnost pro každou sérii. Například:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Jak mohu změnit popisky a formátování os?

Pro úpravu popisků os a formátování, včetně velikosti a barvy písma, se řiďte pokyny v kroku 5.

### Jak uložím graf do jiného formátu souboru?

Výstupní formát můžete změnit úpravou přípony souboru v `outPath` proměnné a s použitím vhodné `SaveFormat`Například pro uložení jako PDF použijte `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}