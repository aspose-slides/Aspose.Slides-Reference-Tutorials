---
title: Vytváření radarových grafů v Java Slides
linktitle: Vytváření radarových grafů v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet radarové grafy v prezentacích Java PowerPoint pomocí Aspose.Slides for Java API.
type: docs
weight: 10
url: /cs/java/chart-creation/radar-chart-creating-java-slides/
---

## Úvod do vytváření radarového grafu v Java Slides

V tomto tutoriálu vás provedeme procesem vytváření radarového grafu pomocí Aspose.Slides for Java API. Radarové grafy jsou užitečné pro vizualizaci dat v kruhovém vzoru, což usnadňuje porovnání více datových řad. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem Java.

## Předpoklady

 Než začneme, ujistěte se, že máte knihovnu Aspose.Slides for Java integrovanou do vašeho projektu. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavení prezentace

Začněme nastavením nové PowerPointové prezentace a přidáním snímku do ní.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Krok 2: Přidání radarové mapy

Dále do snímku přidáme radarovou mapu. Upřesníme polohu a rozměry grafu.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Krok 3: Nastavení dat grafu

Nyní nastavíme data grafu. To zahrnuje vytvoření datového sešitu, přidání kategorií a přidání řad.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Nastavte název grafu
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Smazat výchozí vygenerované série a kategorie
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Přidávání nových kategorií
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Přidávání nové série
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Krok 4: Vyplnění dat řady

Nyní vyplníme sériová data pro naši radarovou mapu.

```java
// Vyplňte data série pro sérii 1
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

// Vyplňte data série pro sérii 2
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

## Krok 5: Přizpůsobení osy a legend

Upravme osu a legendy pro náš radarový graf.

```java
// Nastavte pozici legendy
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Nastavení vlastností textu osy kategorie
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Nastavení vlastností textu legend
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

// Nastavení formátu čísla osy hodnot
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

A je to! Úspěšně jste vytvořili radarový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Nyní můžete tento příklad dále upravit tak, aby vyhovoval vašim konkrétním potřebám.

## Kompletní zdrojový kód pro vytváření radarových grafů v Java Slides

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide sld = pres.getSlides().get_Item(0);
	// Přidat radarový graf
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Nastavení indexu datového listu grafu
	int defaultWorksheetIndex = 0;
	// Získání dat grafu Pracovní list
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Nastavte název grafu
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Smazat výchozí vygenerované série a kategorie
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Přidávání nových kategorií
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Přidávání nové série
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Nyní se vyplňují data série
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
	// Nyní se vyplňují data další řady
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
	// Nastavte pozici legendy
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Nastavení vlastností textu osy kategorie
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Nastavení vlastností textu legend
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
	// Nastavení formátu čísla osy hodnot
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

V tomto tutoriálu jste se naučili, jak vytvořit radarový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Tyto koncepty můžete použít k efektivní vizualizaci a prezentaci vašich dat ve vašich aplikacích Java.

## FAQ

### Jak mohu změnit název grafu?

Chcete-li změnit název grafu, upravte následující řádek:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Mohu do radarové mapy přidat další datové řady?

Ano, můžete přidat další datové řady podle kroků v „Kroku 3“ a „Kroku 4“ pro každou další řadu, kterou chcete zahrnout.

### Jak přizpůsobím barvy grafu?

 Barvy řady můžete přizpůsobit úpravou čar, které nastavují`SolidFillColor` vlastnost pro každou řadu. Například:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Jak mohu změnit popisky os a formátování?

Viz "Krok 5" pro přizpůsobení štítků os a formátování, včetně velikosti a barvy písma.

### Jak uložím graf do jiného formátu souboru?

 Výstupní formát můžete změnit úpravou přípony souboru v`outPath` proměnné a pomocí příslušného`SaveFormat` . Chcete-li například uložit jako PDF, použijte`SaveFormat.Pdf`.