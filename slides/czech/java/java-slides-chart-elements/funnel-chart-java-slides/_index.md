---
"description": "Prozkoumejte Aspose.Slides pro Javu s podrobnými návody. Vytvářejte úžasné trychtýřové grafy a další."
"linktitle": "Trychtýřový graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Trychtýřový graf v Javě Slides"
"url": "/cs/java/chart-elements/funnel-chart-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Trychtýřový graf v Javě Slides


## Úvod do trychtýřového grafu v Javě – Slides

V tomto tutoriálu si ukážeme, jak vytvořit trychtýřový graf pomocí Aspose.Slides pro Javu. Trychtýřové grafy jsou užitečné pro vizualizaci sekvenčního procesu s postupně se zužujícími fázemi, jako jsou například prodejní konverze nebo akvizice zákazníků.

## Předpoklady

Než začnete, ujistěte se, že máte do svého projektu Java přidánu knihovnu Aspose.Slides. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializace prezentace

Nejprve si inicializujeme prezentaci a přidáme do ní snímek, kam umístíme náš trychtýřový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou k adresáři vašeho projektu.

## Krok 2: Vytvořte trychtýřový graf

Nyní si vytvořme trychtýřový graf a nastavíme jeho rozměry na snímku.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Ve výše uvedeném kódu přidáme na první snímek trychtýřový graf na souřadnicích (50, 50) o šířce 500 a výšce 400 pixelů.

## Krok 3: Definování dat grafu

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

Zde vymažeme veškerá existující data, přidáme kategorie (v tomto případě fáze trychtýře) a nastavíme jejich popisky.

## Krok 4: Přidání datových bodů

Nyní přidejme datové body do naší série trychtýřových grafů.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

V tomto kroku vytvoříme sérii pro náš trychtýřový graf a přidáme datové body představující hodnoty v každé fázi trychtýře.

## Krok 5: Uložte prezentaci

Nakonec uložíme prezentaci s trychtýřovým grafem do souboru PowerPointu.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Nezapomeňte vyměnit `"Your Document Directory"` s požadovaným místem uložení.

## Kompletní zdrojový kód pro trychtýřový graf v Javě - Slides

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

V tomto tutoriálu jsme vám ukázali, jak vytvořit trychtýřový graf v Java Slides pomocí Aspose.Slides pro Javu. Graf si můžete dále přizpůsobit úpravou barev, popisků a dalších vlastností tak, aby vyhovoval vašim specifickým potřebám.

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled trychtýřového grafu?

Vzhled trychtýřového grafu si můžete přizpůsobit úpravou vlastností grafu, řady a datových bodů. Podrobné možnosti přizpůsobení naleznete v dokumentaci k Aspose.Slides.

### Mohu do trychtýřového grafu přidat další kategorie nebo datové body?

Ano, do trychtýřového grafu můžete přidat další kategorie a datové body odpovídajícím rozšířením kódu v kroku 3 a kroku 4.

### Je možné změnit typ grafu na jiný než trychtýř?

Ano, Aspose.Slides podporuje různé typy grafů. Typ grafu můžete změnit nahrazením `ChartType.Funnel` s požadovaným typem grafu v kroku 2.

### Jak mám řešit chyby nebo výjimky při práci s Aspose.Slides?

Chyby a výjimky můžete ošetřit pomocí standardních mechanismů pro zpracování výjimek v Javě. Ujistěte se, že máte ve svém kódu správné ošetření chyb, abyste mohli neočekávané situace zvládat elegantně.

### Kde najdu další příklady a dokumentaci k Aspose.Slides pro Javu?

Další příklady a podrobnou dokumentaci k používání Aspose.Slides pro Javu naleznete v [dokumentace](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}