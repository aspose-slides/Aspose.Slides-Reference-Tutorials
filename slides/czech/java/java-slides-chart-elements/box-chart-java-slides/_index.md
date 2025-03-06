---
title: Box Chart v Java Slides
linktitle: Box Chart v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet krabicové grafy v prezentacích Java pomocí Aspose.Slides. Součástí je podrobný průvodce a zdrojový kód pro efektivní vizualizaci dat.
weight: 10
url: /cs/java/chart-elements/box-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do Box Chart v Aspose.Slides pro Javu

tomto tutoriálu vás provedeme procesem vytváření krabicového grafu pomocí Aspose.Slides for Java. Krabicové grafy jsou užitečné pro vizualizaci statistických dat s různými kvartily a odlehlými hodnotami. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, které vám pomohou začít.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Aspose.Slides for Java knihovna nainstalována a nakonfigurována.
- Nastaveno vývojové prostředí Java.

## Krok 1: Inicializujte prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

V tomto kroku inicializujeme objekt prezentace pomocí cesty k existujícímu souboru PowerPoint (v tomto příkladu "test.pptx").

## Krok 2: Vytvořte krabicový graf

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

V tomto kroku vytvoříme na prvním snímku prezentace tvar krabicového grafu. Z grafu také vymažeme všechny existující kategorie a série.

## Krok 3: Definujte kategorie

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

 V tomto kroku definujeme kategorie pro Box Chart. Používáme`IChartDataWorkbook` přidat kategorie a odpovídajícím způsobem je označit.

## Krok 4: Vytvořte sérii

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Zde pro graf vytvoříme sérii BoxAndWhisker a nakonfigurujeme různé možnosti, jako je kvartilová metoda, střední čára, střední značky, vnitřní body a odlehlé body.

## Krok 5: Přidejte datové body

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

Nakonec prezentaci s krabicovým grafem uložíme do nového souboru PowerPoint s názvem "BoxAndWhisker.pptx."

Gratulujeme! Úspěšně jste vytvořili krabicový graf pomocí Aspose.Slides for Java. Graf můžete dále přizpůsobit úpravou různých vlastností a přidáním dalších datových bodů podle potřeby.

## Kompletní zdrojový kód pro krabicový graf v Java Slides

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

tomto tutoriálu jsme se naučili, jak vytvořit krabicový graf pomocí Aspose.Slides pro Java. Krabicové grafy jsou cennými nástroji pro vizualizaci statistických dat, včetně kvartilů a odlehlých hodnot. Poskytli jsme podrobného průvodce spolu se zdrojovým kódem, který vám pomůže začít s vytvářením krabicových grafů ve vašich aplikacích Java.

## FAQ

### Jak mohu změnit vzhled krabicového grafu?

Vzhled krabicového grafu můžete přizpůsobit úpravou vlastností, jako jsou styly čar, barvy a písma. Podrobnosti o přizpůsobení grafu naleznete v dokumentaci Aspose.Slides for Java.

### Mohu do krabicového grafu přidat další datové řady?

 Ano, do krabicového grafu můžete přidat více datových řad vytvořením dalších`IChartSeries` objektů a přidávání datových bodů k nim.

### Co znamená QuartileMethodType.Exclusive?

 The`QuartileMethodType.Exclusive` nastavení určuje, že výpočty kvartilů by měly být prováděny pomocí exkluzivní metody. Můžete si vybrat různé metody výpočtu kvartilů v závislosti na vašich datech a požadavcích.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
