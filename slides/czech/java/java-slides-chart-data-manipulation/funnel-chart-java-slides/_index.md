---
"description": "Naučte se vytvářet trychtýřové grafy v prezentacích v PowerPointu s Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro efektivní vizualizaci dat."
"linktitle": "Trychtýřový graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Trychtýřový graf v Javě Slides"
"url": "/cs/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Trychtýřový graf v Javě Slides


## Úvod do vytváření trychtýřového grafu v Aspose.Slides pro Javu

tomto tutoriálu vás provedeme procesem vytvoření trychtýřového grafu v prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Trychtýřové grafy jsou užitečné pro vizualizaci dat, která se postupně zužují nebo „procházejí“ různými fázemi nebo kategoriemi. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, které vám s tím pomohou.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Knihovna Aspose.Slides pro Javu je nainstalována a nastavena ve vašem projektu.
- Soubor prezentace PowerPoint (PPTX), kam chcete vložit trychtýřový graf.

## Krok 1: Import Aspose.Slides pro Javu

Nejprve je třeba importovat knihovnu Aspose.Slides pro Javu do vašeho projektu v Javě. Ujistěte se, že jste do konfigurace sestavení přidali potřebné závislosti.

```java
import com.aspose.slides.*;
```

## Krok 2: Inicializace prezentace a grafu

V tomto kroku inicializujeme prezentaci a přidáme na snímek trychtýřový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Přidejte trychtýřový graf na první snímek na souřadnicích (50, 50) s rozměry (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Krok 3: Definování dat grafu

Dále definujeme data pro náš trychtýřový graf. Kategorie a datové body si můžete přizpůsobit podle svých požadavků.

```java
// Vymazat existující data grafu.
wb.clear(0);

// Definujte kategorie pro graf.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Přidejte datové body pro sérii trychtýřových grafů.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Krok 4: Uložte prezentaci

Nakonec uložíme prezentaci s trychtýřovým grafem do zadaného souboru.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili trychtýřový graf pomocí Aspose.Slides pro Javu a vložili ho do prezentace v PowerPointu.

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

V tomto podrobném návodu jsme si ukázali, jak vytvořit trychtýřový graf v prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Trychtýřové grafy jsou cenným nástrojem pro vizualizaci dat, která sledují postupný nebo zužující se vzorec, což usnadňuje efektivní sdělování informací. 

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled trychtýřového grafu?

Vzhled trychtýřového grafu si můžete přizpůsobit úpravou různých vlastností grafu, jako jsou barvy, popisky a styly. Podrobné informace o možnostech přizpůsobení grafu naleznete v dokumentaci k Aspose.Slides.

### Mohu do trychtýřového grafu přidat další datové body nebo kategorie?

Ano, do trychtýřového grafu můžete přidat další datové body a kategorie rozšířením kódu uvedeného v kroku 3. V případě potřeby jednoduše přidejte další popisky kategorií a datové body.

### Jak mohu změnit umístění a velikost trychtýřového grafu na snímku?

Polohu a velikost trychtýřového grafu můžete upravit úpravou souřadnic a rozměrů zadaných při přidávání grafu na snímek v kroku 2. Hodnoty (50, 50, 500, 400) odpovídajícím způsobem aktualizujte.

### Mohu exportovat graf do různých formátů, například PDF nebo obrázku?

Ano, Aspose.Slides pro Javu umožňuje exportovat prezentaci s trychtýřovým grafem do různých formátů, včetně PDF, obrazových formátů a dalších. Můžete použít `SaveFormat` možnosti pro určení požadovaného výstupního formátu při ukládání prezentace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}