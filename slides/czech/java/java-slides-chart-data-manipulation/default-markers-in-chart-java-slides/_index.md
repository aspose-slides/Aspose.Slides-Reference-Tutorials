---
title: Výchozí značky v grafu v Java Slides
linktitle: Výchozí značky v grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet snímky Java s výchozími značkami v grafech pomocí Aspose.Slides for Java. Průvodce krok za krokem se zdrojovým kódem.
weight: 16
url: /cs/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Výchozí značky v grafu v Java Slides


## Úvod do výchozích značek v grafu v Java Slides

V tomto tutoriálu prozkoumáme, jak vytvořit graf s výchozími značkami pomocí Aspose.Slides pro Java. Výchozí značky jsou symboly nebo tvary přidané k datovým bodům v grafu za účelem jejich zvýraznění. Vytvoříme spojnicový graf se značkami pro vizualizaci dat.

## Předpoklady

Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Vytvořte prezentaci

Nejprve vytvoříme prezentaci a přidáme k ní snímek. Poté na snímek přidáme graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Krok 2: Přidejte spojnicový graf se značkami

Nyní přidáme na snímek spojnicový graf se značkami. Z grafu také vymažeme všechna výchozí data.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 3: Vyplňte data grafu

Graf naplníme ukázkovými daty. V tomto příkladu vytvoříme dvě řady s datovými body a kategoriemi.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Série 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Série 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Vyplňování řad dat
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Krok 4: Přizpůsobte graf

Graf můžete dále přizpůsobit, například přidat legendu a upravit jeho vzhled.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s grafem na požadované místo.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

A je to! Pomocí Aspose.Slides for Java jste vytvořili spojnicový graf s výchozími značkami.

## Kompletní zdrojový kód pro výchozí značky v grafu v Java Slides

```java
        // Cesta k adresáři dokumentů.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Vezměte druhou řadu grafů
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Nyní se vyplňují data série
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Závěr

V tomto obsáhlém tutoriálu jste se naučili, jak vytvořit snímky Java s výchozími značkami v grafech pomocí Aspose.Slides for Java. Pokryli jsme celý proces, od nastavení prezentace až po přizpůsobení vzhledu grafu a uložení výsledku.

## FAQ

### Jak mohu změnit symboly značek?

Symboly značek můžete přizpůsobit nastavením stylu značek pro každý datový bod. Použití`IDataPoint.setMarkerStyle()` pro změnu symbolu značky.

### Jak upravím barvy grafu?

 Chcete-li upravit barvy grafu, můžete použít`IChartSeriesFormat` a`IShapeFillFormat` rozhraní pro nastavení vlastností výplně a čáry.

### Mohu k datovým bodům přidat štítky?

 Ano, k datovým bodům můžete přidávat štítky pomocí`IDataPoint.getLabel()` metodu a upravte je podle potřeby.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
