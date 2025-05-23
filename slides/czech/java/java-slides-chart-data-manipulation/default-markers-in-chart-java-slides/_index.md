---
"description": "Naučte se, jak vytvářet slidy v Javě s výchozími značkami v grafech pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem."
"linktitle": "Výchozí značky v grafu v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Výchozí značky v grafu v Javě Slides"
"url": "/cs/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Výchozí značky v grafu v Javě Slides


## Úvod do výchozích značek v grafu v Javě - Slides

V tomto tutoriálu se podíváme na to, jak vytvořit graf s výchozími značkami pomocí Aspose.Slides pro Javu. Výchozí značky jsou symboly nebo tvary přidané k datovým bodům v grafu za účelem jejich zvýraznění. Vytvoříme spojnicový graf se značkami pro vizualizaci dat.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Vytvořte prezentaci

Nejprve si vytvořme prezentaci a přidáme do ní snímek. Poté na snímek přidáme graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Krok 2: Přidání spojnicového grafu se značkami

Nyní přidáme na snímek spojnicový graf se značkami. Také z grafu vymažeme veškerá výchozí data.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 3: Naplnění grafu daty

Graf naplníme vzorovými daty. V tomto příkladu vytvoříme dvě řady s datovými body a kategoriemi.

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

// Naplňování dat série
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Krok 4: Přizpůsobení grafu

Graf si můžete dále přizpůsobit, například přidat legendu a upravit jeho vzhled.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s grafem na požadované místo.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

To je vše! Vytvořili jste spojnicový graf s výchozími značkami pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro výchozí značky v grafu v Javě Slides

```java
        // Cesta k adresáři s dokumenty.
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
            //Vezměte si druhou sérii grafů
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Nyní se naplňují data série
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

tomto komplexním tutoriálu jste se naučili, jak vytvářet slidy v Javě s výchozími značkami v grafech pomocí Aspose.Slides pro Javu. Probrali jsme celý proces, od nastavení prezentace až po přizpůsobení vzhledu grafu a uložení výsledku.

## Často kladené otázky

### Jak mohu změnit symboly značek?

Symboly značek můžete přizpůsobit nastavením stylu značky pro každý datový bod. Použijte `IDataPoint.setMarkerStyle()` pro změnu symbolu značky.

### Jak upravím barvy grafu?

Chcete-li upravit barvy grafu, můžete použít `IChartSeriesFormat` a `IShapeFillFormat` rozhraní pro nastavení vlastností výplně a čáry.

### Mohu k datovým bodům přidat popisky?

Ano, k datovým bodům můžete přidat popisky pomocí `IDataPoint.getLabel()` metodu a přizpůsobit je podle potřeby.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}