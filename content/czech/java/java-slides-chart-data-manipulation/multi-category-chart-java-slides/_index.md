---
title: Multi-Category Chart v Java Slides
linktitle: Multi-Category Chart v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vytvářejte vícekategorní grafy v Java Slides pomocí Aspose.Slides for Java. Podrobný průvodce se zdrojovým kódem pro působivou vizualizaci dat v prezentacích.
type: docs
weight: 20
url: /cs/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Úvod do Multi-Category Chart v Java Slides s Aspose.Slides

V tomto tutoriálu se naučíme, jak vytvořit vícekategoriální graf na snímcích Java pomocí Aspose.Slides for Java API. Tato příručka poskytne podrobné pokyny spolu se zdrojovým kódem, které vám pomohou vytvořit seskupený sloupcový graf s více kategoriemi a řadami.

## Předpoklady
Než začneme, ujistěte se, že máte knihovnu Aspose.Slides for Java nainstalovanou a nastavenou ve vývojovém prostředí Java.

## Krok 1: Nastavení prostředí
Nejprve importujte potřebné třídy a vytvořte nový objekt Presentation pro práci se snímky.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání snímku a grafu
Dále vytvořte snímek a přidejte k němu seskupený sloupcový graf.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Krok 3: Vymazání existujících dat
Vymažte veškerá existující data z grafu.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Krok 4: Nastavení kategorií dat
Nyní nastavíme kategorie dat pro graf. Vytvoříme více kategorií a seskupíme je.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Přidejte kategorie a seskupte je
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Krok 5: Přidání série
Nyní přidejte do grafu řadu spolu s datovými body.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Krok 6: Uložení prezentace
Nakonec uložte prezentaci s grafem.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste vytvořili graf více kategorií na snímku Java pomocí Aspose.Slides. Tento graf můžete dále upravit tak, aby vyhovoval vašim specifickým požadavkům.

## Kompletní zdrojový kód pro graf více kategorií v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Přidávání série
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Uložit prezentaci s grafem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit vícekategoriální graf na snímcích Java pomocí rozhraní Aspose.Slides for Java API. Prošli jsme krok za krokem průvodce se zdrojovým kódem, abychom vytvořili seskupený sloupcový graf s více kategoriemi a řadami.

## FAQ

### Jak mohu přizpůsobit vzhled grafu?

Vzhled grafu můžete přizpůsobit úpravou vlastností, jako jsou barvy, písma a styly. Podrobné možnosti přizpůsobení naleznete v dokumentaci Aspose.Slides.

### Mohu do grafu přidat další série?

Ano, do grafu můžete přidat další řady podobným postupem jako v kroku 5.

### Jak změním typ grafu?

 Chcete-li změnit typ grafu, nahraďte`ChartType.ClusteredColumn` s požadovaným typem grafu při přidávání grafu v kroku 2.

### Jak mohu přidat název do grafu?

 Do grafu můžete přidat název pomocí`ch.getChartTitle().getTextFrame().setText("Chart Title");` metoda.