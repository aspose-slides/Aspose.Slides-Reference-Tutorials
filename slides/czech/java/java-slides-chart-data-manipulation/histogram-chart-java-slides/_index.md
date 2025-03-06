---
title: Histogram Chart v Java Slides
linktitle: Histogram Chart v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet histogramové grafy v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Podrobný průvodce se zdrojovým kódem pro vizualizaci dat.
weight: 19
url: /cs/java/chart-data-manipulation/histogram-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do Histogram Chart v Java Slides pomocí Aspose.Slides

V tomto tutoriálu vás provedeme procesem vytváření histogramového grafu v prezentaci PowerPoint pomocí rozhraní Aspose.Slides for Java API. Histogram Chart se používá k reprezentaci rozložení dat v nepřetržitém intervalu.

## Předpoklady

 Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializujte svůj projekt

Vytvořte projekt Java a zahrňte knihovnu Aspose.Slides do závislostí svého projektu.

## Krok 2: Importujte potřebné knihovny

```java
import com.aspose.slides.*;
```

## Krok 3: Načtěte existující prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k vašemu PowerPoint dokumentu.

## Krok 4: Vytvořte histogram

Nyní vytvoříme histogram na snímku prezentace.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Přidejte datové body do řady
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Nastavte typ agregace vodorovné osy na Automaticky
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Uložte prezentaci
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 V tomto kódu nejprve vymažeme všechny existující kategorie a řady z grafu. Poté přidáme datové body do řady pomocí`getDataPoints().addDataPointForHistogramSeries` metoda. Nakonec nastavíme typ agregace vodorovné osy na Automaticky a prezentaci uložíme.

## Kompletní zdrojový kód pro histogramový graf v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

tomto tutoriálu jsme prozkoumali, jak vytvořit histogramový graf v prezentaci PowerPoint pomocí Aspose.Slides for Java API. Histogramové grafy jsou cennými nástroji pro vizualizaci distribuce dat v nepřetržitém intervalu a mohou být účinným doplňkem vašich prezentací, zejména při práci se statistickým nebo analytickým obsahem.

## FAQ

### Jak nainstaluji Aspose.Slides for Java?

 Knihovnu Aspose.Slides for Java si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/). Postupujte podle pokynů k instalaci uvedených na jejich webových stránkách.

### K čemu slouží histogram?

Histogram Chart se používá k vizualizaci rozložení dat v nepřetržitém intervalu. Běžně se používá ve statistikách k reprezentaci rozdělení frekvencí.

### Mohu upravit vzhled histogramového grafu?

Ano, vzhled grafu, včetně jeho barev, štítků a os, můžete upravit pomocí rozhraní Aspose.Slides API.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
