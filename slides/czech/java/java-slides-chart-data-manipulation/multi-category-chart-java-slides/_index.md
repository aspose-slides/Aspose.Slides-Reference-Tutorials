---
"description": "Vytvářejte grafy s více kategoriemi v Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro působivou vizualizaci dat v prezentacích."
"linktitle": "Vícekategorický graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vícekategorický graf v Javě Slides"
"url": "/cs/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vícekategorický graf v Javě Slides


## Úvod do vícekategorizačních grafů v Javě - Slides s Aspose.Slides

V tomto tutoriálu se naučíme, jak vytvořit graf s více kategoriemi v Javě pomocí rozhraní Aspose.Slides pro Java API. Tato příručka poskytne podrobné pokyny spolu se zdrojovým kódem, které vám pomohou vytvořit seskupený sloupcový graf s více kategoriemi a řadami.

## Předpoklady
Než začneme, ujistěte se, že máte ve svém vývojovém prostředí Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Nastavení prostředí
Nejprve importujte potřebné třídy a vytvořte nový objekt Presentation pro práci se snímky.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání snímku a grafu
Dále vytvořte snímek a přidejte do něj seskupený sloupcový graf.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Krok 3: Vymazání existujících dat
Vymažte všechna existující data z grafu.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Krok 4: Nastavení kategorií dat
Nyní si nastavíme kategorie dat pro graf. Vytvoříme více kategorií a seskupíme je.

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
Nyní přidejme do grafu řadu spolu s datovými body.

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
Nakonec prezentaci s grafem uložte.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili graf s více kategoriemi v snímku v Javě pomocí Aspose.Slides. Tento graf si můžete dále přizpůsobit svým specifickým požadavkům.

## Kompletní zdrojový kód pro vícekategorický graf v Javě Slides

```java
// Cesta k adresáři s dokumenty.
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
//            Přidávání sérií
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

tomto tutoriálu jsme se naučili, jak vytvořit graf s více kategoriemi v Javě pomocí rozhraní Aspose.Slides pro Java API. Prošli jsme si podrobný návod se zdrojovým kódem pro vytvoření klastrovaného sloupcového grafu s více kategoriemi a řadami.

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled grafu?

Vzhled grafu si můžete přizpůsobit úpravou vlastností, jako jsou barvy, písma a styly. Podrobné možnosti přizpůsobení naleznete v dokumentaci k Aspose.Slides.

### Mohu do grafu přidat další série?

Ano, do grafu můžete přidat další řady podobným způsobem, jaký je znázorněn v kroku 5.

### Jak změním typ grafu?

Chcete-li změnit typ grafu, nahraďte `ChartType.ClusteredColumn` s požadovaným typem grafu při přidávání grafu v kroku 2.

### Jak mohu přidat název grafu?

Název grafu můžete přidat pomocí `ch.getChartTitle().getTextFrame().setText("Chart Title");` metoda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}