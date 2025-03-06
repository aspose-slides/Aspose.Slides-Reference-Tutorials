---
title: Graf trychtýře v Java Slides
linktitle: Graf trychtýře v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet trychtýřové grafy v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Podrobný průvodce se zdrojovým kódem pro efektivní vizualizaci dat.
weight: 18
url: /cs/java/chart-data-manipulation/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do vytváření diagramu trychtýře v Aspose.Slides pro Java

tomto tutoriálu vás provedeme procesem vytváření trychtýřového grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Grafy trychtýřů jsou užitečné pro vizualizaci dat, která se postupně zužují nebo „cestují“ různými fázemi nebo kategoriemi. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, které vám toho pomohou dosáhnout.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Knihovna Aspose.Slides for Java nainstalována a nastavena ve vašem projektu.
- Soubor prezentace PowerPoint (PPTX), do kterého chcete vložit diagram cesty.

## Krok 1: Import Aspose.Slides pro Java

Nejprve musíte do svého projektu Java importovat knihovnu Aspose.Slides for Java. Ujistěte se, že jste do konfigurace sestavení přidali potřebné závislosti.

```java
import com.aspose.slides.*;
```

## Krok 2: Inicializujte prezentaci a graf

V tomto kroku inicializujeme prezentaci a přidáme na snímek trychtýřový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    //Přidejte diagram cesty na první snímek na souřadnicích (50, 50) s rozměry (500, 400).
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

## Krok 3: Definujte data grafu

Dále definujeme data pro náš diagram cesty. Kategorie a datové body si můžete přizpůsobit podle svých požadavků.

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

// Přidejte datové body pro řadu grafů cesty.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Krok 4: Uložte prezentaci

Nakonec prezentaci s Funnel Chart uložíme do určeného souboru.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste vytvořili trychtýřový graf pomocí Aspose.Slides for Java a vložili jej do prezentace v PowerPointu.

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

V tomto podrobném průvodci jsme si ukázali, jak vytvořit trychtýřový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Trychtýřové grafy jsou cenným nástrojem pro vizualizaci dat, která sledují průběh nebo zužování, což usnadňuje efektivní přenos informací. 

## FAQ

### Jak mohu přizpůsobit vzhled diagramu cesty?

Vzhled grafu cesty můžete přizpůsobit úpravou různých vlastností grafu, jako jsou barvy, štítky a styly. Podrobné informace o možnostech přizpůsobení grafu naleznete v dokumentaci Aspose.Slides.

### Mohu do grafu cesty přidat další datové body nebo kategorie?

Ano, do diagramu cesty můžete přidat další datové body a kategorie rozšířením kódu poskytnutého v kroku 3. Jednoduše přidejte další štítky kategorií a datové body podle potřeby.

### Jak mohu změnit polohu a velikost diagramu cesty na snímku?

Pozici a velikost grafu cesty můžete upravit úpravou souřadnic a rozměrů poskytnutých při přidávání grafu na snímek v kroku 2. Podle toho aktualizujte hodnoty (50, 50, 500, 400).

### Mohu exportovat graf do různých formátů, jako je PDF nebo obrázek?

Ano, Aspose.Slides for Java umožňuje exportovat prezentaci s trychtýřovým grafem do různých formátů, včetně PDF, obrázkových formátů a dalších. Můžete použít`SaveFormat` možnosti určit požadovaný výstupní formát při ukládání prezentace.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
