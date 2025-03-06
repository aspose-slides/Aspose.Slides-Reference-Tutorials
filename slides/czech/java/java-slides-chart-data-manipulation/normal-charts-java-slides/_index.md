---
title: Normální grafy v Java Slides
linktitle: Normální grafy v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vytvářejte normální grafy v Java Slides pomocí Aspose.Slides pro Java. Podrobný průvodce a zdrojový kód pro vytváření, přizpůsobení a ukládání grafů v prezentacích PowerPoint.
weight: 21
url: /cs/java/chart-data-manipulation/normal-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Normální grafy v Java Slides


## Úvod do normálních grafů v Java Slides

tomto tutoriálu projdeme procesem vytváření normálních grafů v Java Slides pomocí Aspose.Slides for Java API. Použijeme podrobné pokyny spolu se zdrojovým kódem, abychom předvedli, jak vytvořit seskupený sloupcový graf v prezentaci PowerPoint.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Aspose.Slides for Java API nainstalováno.
2. Nastaveno vývojové prostředí Java.
3. Základní znalost programování v Javě.

## Krok 1: Nastavení projektu

Ujistěte se, že máte adresář pro svůj projekt. Říkejme tomu „Adresář vašich dokumentů“, jak je uvedeno v kódu. Toto můžete nahradit skutečnou cestou k adresáři vašeho projektu.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Krok 2: Vytvoření prezentace

Nyní vytvoříme powerpointovou prezentaci a zpřístupníme její první snímek.

```java
// Třída okamžité prezentace, která představuje soubor PPTX
Presentation pres = new Presentation();
// Přístup k prvnímu snímku
ISlide sld = pres.getSlides().get_Item(0);
```

## Krok 3: Přidání grafu

Na snímek přidáme seskupený sloupcový graf a nastavíme jeho název.

```java
// Přidat graf s výchozími daty
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Nastavení názvu grafu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 4: Nastavení dat grafu

Dále nastavíme data grafu definováním řad a kategorií.

```java
// Nastavte první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

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

## Krok 5: Vyplnění dat řady

Nyní vyplníme datové body řady pro graf.

```java
// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Vyplňování řad dat
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);

// Vyplňování řad dat
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 6: Přizpůsobení štítků

Upravme popisky dat pro řadu grafů.

```java
// První štítek bude zobrazovat název kategorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Zobrazit hodnotu pro třetí štítek s názvem série a oddělovačem
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Krok 7: Uložení prezentace

Nakonec uložte prezentaci s grafem do svého projektového adresáře.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste vytvořili seskupený sloupcový graf v prezentaci aplikace PowerPoint pomocí Aspose.Slides for Java. Tento graf můžete dále upravit podle svých požadavků.

## Kompletní zdrojový kód pro normální grafy v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Třída okamžité prezentace, která představuje soubor PPTX
Presentation pres = new Presentation();
// Přístup k prvnímu snímku
ISlide sld = pres.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Nastavení názvu grafu
// Chart.getChartTitle().getTextFrameForOverriding().setText("Ukázkový název");
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
// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// První štítek bude zobrazovat název kategorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Zobrazit hodnotu pro třetí štítek
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Uložit prezentaci s grafem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Závěr

V tomto tutoriálu jsme se naučili, jak vytvořit normální grafy v Java Slides pomocí Aspose.Slides for Java API. Prošli jsme si podrobným průvodcem se zdrojovým kódem k vytvoření seskupeného sloupcového grafu v prezentaci PowerPoint.

## FAQ

### Jak mohu změnit typ grafu?

 Chcete-li změnit typ grafu, upravte`ChartType`parametr při přidávání grafu pomocí`sld.getShapes().addChart()`. Můžete si vybrat z různých typů grafů dostupných v Aspose.Slides.

### Mohu změnit barvy řady grafů?

 Ano, můžete změnit barvy řady grafů nastavením barvy výplně pro každou řadu pomocí`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Jak přidám do grafu další kategorie nebo série?

 Do grafu můžete přidat další kategorie nebo řady přidáním nových datových bodů a štítků pomocí`chart.getChartData().getCategories().add()` a`chart.getChartData().getSeries().add()` metody.

### Jak mohu dále upravit název grafu?

 Titulek grafu můžete dále upravit úpravou vlastností`chart.getChartTitle()` jako je zarovnání textu, velikost písma a barva.

### Jak uložím graf do jiného formátu souboru?

 Chcete-li uložit graf do jiného formátu souboru, změňte`SaveFormat` parametr v`pres.save()` metodou do požadovaného formátu (např. PDF, PNG, JPEG).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
