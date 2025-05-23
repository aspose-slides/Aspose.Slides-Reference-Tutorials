---
"description": "Naučte se, jak vytvářet krabicové grafy v prezentacích v Javě pomocí Aspose.Slides. Součástí je podrobný návod a zdrojový kód pro efektivní vizualizaci dat."
"linktitle": "Krabicový graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Krabicový graf v Javě Slides"
"url": "/cs/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Krabicový graf v Javě Slides


## Úvod do rámečkového grafu v Aspose.Slides pro Javu

tomto tutoriálu vás provedeme procesem vytvoření krabicového grafu pomocí Aspose.Slides pro Javu. Krabicové grafy jsou užitečné pro vizualizaci statistických dat s různými kvartily a odlehlými hodnotami. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, které vám pomohou začít.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Knihovna Aspose.Slides pro Javu nainstalována a nakonfigurována.
- Nastavení vývojového prostředí v Javě.

## Krok 1: Inicializace prezentace

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

V tomto kroku inicializujeme objekt prezentace pomocí cesty k existujícímu souboru PowerPointu (v tomto příkladu „test.pptx“).

## Krok 2: Vytvořte krabicový graf

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

V tomto kroku vytvoříme na prvním snímku prezentace tvar rámečkového grafu. Také z grafu odstraníme všechny existující kategorie a řady.

## Krok 3: Definování kategorií

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

V tomto kroku definujeme kategorie pro krabicový graf. Použijeme `IChartDataWorkbook` přidat kategorie a odpovídajícím způsobem je označit.

## Krok 4: Vytvořte sérii

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Zde pro graf vytvoříme řadu BoxAndWhisker a nakonfigurujeme různé možnosti, jako je kvartilová metoda, průměrná čára, značky průměru, vnitřní body a odlehlé body.

## Krok 5: Přidání datových bodů

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

V tomto kroku přidáme datové body do řady BoxAndWhisker. Tyto datové body představují statistická data pro graf.

## Krok 6: Uložte prezentaci

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Nakonec uložíme prezentaci s krabicovým grafem do nového souboru PowerPointu s názvem „BoxAndWhisker.pptx“.

Gratulujeme! Úspěšně jste vytvořili krabicový graf pomocí Aspose.Slides pro Javu. Graf si můžete dále přizpůsobit úpravou různých vlastností a přidáním dalších datových bodů dle potřeby.

## Kompletní zdrojový kód pro krabicový graf v Javě Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit krabicový graf pomocí Aspose.Slides pro Javu. Krabicové grafy jsou cenné nástroje pro vizualizaci statistických dat, včetně kvartilů a odlehlých hodnot. Poskytli jsme podrobný návod spolu se zdrojovým kódem, který vám pomůže začít s vytvářením krabicových grafů ve vašich aplikacích v Javě.

## Často kladené otázky

### Jak mohu změnit vzhled krabicového grafu?

Vzhled krabicového grafu si můžete přizpůsobit úpravou vlastností, jako jsou styly čar, barvy a písma. Podrobnosti o přizpůsobení grafu naleznete v dokumentaci k Aspose.Slides pro Javu.

### Mohu do krabicového grafu přidat další datové řady?

Ano, do krabicového grafu můžete přidat více datových řad vytvořením dalších `IChartSeries` objekty a přidávání datových bodů k nim.

### Co znamená QuartileMethodType.Exclusive?

Ten/Ta/To `QuartileMethodType.Exclusive` Nastavení určuje, že výpočty kvartilů by měly být provedeny pomocí exkluzivní metody. V závislosti na vašich datech a požadavcích si můžete zvolit různé metody výpočtu kvartilů.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}