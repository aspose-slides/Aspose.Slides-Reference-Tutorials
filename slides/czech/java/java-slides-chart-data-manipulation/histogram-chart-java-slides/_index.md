---
"description": "Naučte se, jak vytvářet histogramy v prezentacích v PowerPointu pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro vizualizaci dat."
"linktitle": "Histogram v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Histogram v Javě Slides"
"url": "/cs/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Histogram v Javě Slides


## Úvod do histogramu v Javě s využitím Aspose.Slides

V tomto tutoriálu vás provedeme procesem vytvoření histogramu v prezentaci PowerPoint pomocí rozhraní Aspose.Slides pro Java API. Histogram se používá k znázornění rozložení dat v spojitém intervalu.

## Předpoklady

Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [Webové stránky Aspose](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializace projektu

Vytvořte projekt v Javě a do závislostí projektu zahrňte knihovnu Aspose.Slides.

## Krok 2: Importujte potřebné knihovny

```java
import com.aspose.slides.*;
```

## Krok 3: Načtení existující prezentace

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou k vašemu dokumentu PowerPoint.

## Krok 4: Vytvořte histogram

Nyní si vytvořme histogram na snímku v prezentaci.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Přidání datových bodů do řady
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Nastavit typ agregace vodorovné osy na Automaticky
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Uložit prezentaci
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

V tomto kódu nejprve z grafu vymažeme všechny existující kategorie a řady. Poté do řady přidáme datové body pomocí `getDataPoints().addDataPointForHistogramSeries` metoda. Nakonec nastavíme typ agregace horizontální osy na Automaticky a uložíme prezentaci.

## Kompletní zdrojový kód pro histogram v Javě Slides

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

tomto tutoriálu jsme prozkoumali, jak vytvořit histogram v prezentaci PowerPoint pomocí rozhraní Aspose.Slides pro Java API. Histogramy jsou cennými nástroji pro vizualizaci rozložení dat v nepřetržitém intervalu a mohou být účinným doplňkem vašich prezentací, zejména při práci se statistickým nebo analytickým obsahem.

## Často kladené otázky

### Jak nainstaluji Aspose.Slides pro Javu?

Knihovnu Aspose.Slides pro Javu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/)Postupujte podle pokynů k instalaci uvedených na jejich webových stránkách.

### K čemu se používá histogram?

Histogram se používá k vizualizaci rozložení dat v spojitém intervalu. Ve statistice se běžně používá k reprezentaci frekvenčního rozdělení.

### Mohu si přizpůsobit vzhled histogramu?

Ano, vzhled grafu, včetně jeho barev, popisků a os, si můžete přizpůsobit pomocí rozhraní API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}