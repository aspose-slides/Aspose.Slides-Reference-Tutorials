---
title: Graf trychtýře v Java Slides
linktitle: Graf trychtýře v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Prozkoumejte Aspose.Slides pro Javu pomocí podrobných výukových programů. Vytvářejte úžasné trychtýřové grafy a další.
type: docs
weight: 14
url: /cs/java/chart-elements/funnel-chart-java-slides/
---

## Úvod do grafu trychtýře v aplikaci Java Slides

V tomto tutoriálu si ukážeme, jak vytvořit trychtýřový graf pomocí Aspose.Slides for Java. Trychtýřové grafy jsou užitečné pro vizualizaci sekvenčního procesu s fázemi, které se postupně zužují, jako jsou prodejní konverze nebo akvizice zákazníků.

## Předpoklady

 Než začnete, ujistěte se, že máte knihovnu Aspose.Slides přidanou do svého projektu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializujte prezentaci

Nejprve inicializujeme prezentaci a přidáme k ní snímek, kam umístíme náš trychtýřový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k adresáři vašeho projektu.

## Krok 2: Vytvořte graf cesty

Nyní vytvoříme trychtýřový graf a nastavíme jeho rozměry na snímku.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Ve výše uvedeném kódu přidáme na první snímek trychtýřový graf na souřadnicích (50, 50) o šířce 500 a výšce 400 pixelů.

## Krok 3: Definujte data grafu

Dále definujeme data pro náš trychtýřový graf. Nastavíme kategorie a řady pro graf.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

Zde vymažeme veškerá existující data, přidáme kategorie (v tomto případě fáze cesty) a nastavíme jejich štítky.

## Krok 4: Přidejte datové body

Nyní přidáme datové body do naší řady grafů trychtýře.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

V tomto kroku vytvoříme řadu pro náš graf cesty a přidáme datové body představující hodnoty v každé fázi cesty.

## Krok 5: Uložte prezentaci

Nakonec prezentaci s diagramem trychtýře uložíme do souboru PowerPoint.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Nezapomeňte vyměnit`"Your Document Directory"` s požadovaným umístěním uložení.

## Kompletní zdrojový kód pro graf trychtýře v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme vám ukázali, jak vytvořit trychtýřový graf v Java Slides pomocí Aspose.Slides for Java. Graf můžete dále přizpůsobit úpravou barev, štítků a dalších vlastností tak, aby vyhovovaly vašim konkrétním potřebám.

## FAQ

### Jak mohu přizpůsobit vzhled diagramu cesty?

Vzhled grafu trychtýře můžete přizpůsobit úpravou vlastností grafu, řady a datových bodů. Podrobné možnosti přizpůsobení naleznete v dokumentaci Aspose.Slides.

### Mohu do grafu cesty přidat další kategorie nebo datové body?

Ano, do grafu cesty můžete přidat další kategorie a datové body odpovídajícím rozšířením kódu v kroku 3 a kroku 4.

### Je možné změnit typ grafu na něco jiného než na trychtýř?

 Ano, Aspose.Slides podporuje různé typy grafů. Typ grafu můžete změnit nahrazením`ChartType.Funnel` s požadovaným typem grafu v kroku 2.

### Jak se vypořádám s chybami nebo výjimkami při práci s Aspose.Slides?

Chyby a výjimky můžete zpracovat pomocí standardních mechanismů zpracování výjimek Java. Ujistěte se, že máte ve svém kódu správné zpracování chyb, abyste mohli bez problémů zvládnout neočekávané situace.

### Kde najdu další příklady a dokumentaci k Aspose.Slides pro Javu?

 Další příklady a podrobnou dokumentaci k používání Aspose.Slides pro Javu naleznete v[dokumentace](https://docs.aspose.com/slides/java/).