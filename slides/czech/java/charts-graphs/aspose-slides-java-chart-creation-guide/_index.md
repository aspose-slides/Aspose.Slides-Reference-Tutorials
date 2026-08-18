---
date: '2026-06-03'
description: Naučte se, jak vytvořit seskupený sloupcový graf v Javě pomocí Aspose.Slides.
  Tento průvodce zahrnuje Maven závislost, kroky tvorby grafu a práci s daty.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Vytvořte seskupený sloupcový graf v Javě s Aspose.Slides
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvoření seskupeného sloupcového grafu v Javě s Aspose.Slides

## Jak vytvořit graf v Javě: Úvod
Vytváření dynamických prezentací často zahrnuje vizualizaci dat pomocí grafů. S **Aspose.Slides for Java** můžete snadno **vytvořit seskupený sloupcový graf** objektů, zvýšit přehlednost a udělat silnější dojem na vaše publikum. Tento tutoriál vás provede nastavením knihovny, přidáním seskupeného sloupcového grafu, správou sérií a podmíněným převrácením záporných datových bodů.

**Co se naučíte**
- Jak nastavit Aspose.Slides for Java.
- Kroky k **vytvoření seskupeného sloupcového grafu** ve vaší prezentaci.
- Techniky pro správu sérií grafu a datových bodů.
- Metody pro podmíněné převrácení záporných datových bodů pro lepší vizualizaci.
- Jak bezpečně uložit prezentaci.

## Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Slides for Java.  
- **Jaký typ grafu je předveden?** Seskupený sloupcový graf.  
- **Mohu převrátit záporné hodnoty?** Ano, pomocí `invertIfNegative`.  
- **Jaká verze Javy je požadována?** JDK 16 nebo novější.  
- **Je licence potřebná pro produkci?** Ano, platná licence Aspose.

## Co je seskupený sloupcový graf?
Seskupený sloupcový graf je vizuální reprezentace, která umisťuje více datových sérií vedle sebe pro každou kategorii, což umožňuje rychlé srovnání napříč skupinami. Je ideální pro finanční zprávy, prodejní dashboardy a jakýkoli scénář, kde potřebujete najednou porovnat několik metrik.

## Proč použít Aspose.Slides pro tvorbu grafů?
Aspose.Slides vám umožňuje generovat a plně přizpůsobovat grafy programově, čímž eliminuje potřebu ruční úpravy PowerPointu. Podporuje **více než 70 vstupních a výstupních formátů** a může zpracovávat prezentace s **až 10 000 snímky** bez načítání celého souboru do paměti, což zajišťuje vysoký výkon pro rozsáhlé reportování.

## Předpoklady
1. **Požadované knihovny**  
   - Aspose.Slides for Java (verze 25.4 nebo novější).  

2. **Prostředí**  
   - JDK 16 nebo novější.  
   - Maven nebo Gradle pro správu závislostí.  

3. **Znalosti**  
   - Základní programování v Javě.  
   - Znalost nástrojů pro sestavení (Maven/Gradle).  

## Nastavení Aspose.Slides pro Java
### Instalace pomocí Maven
Přidejte následující závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace pomocí Gradle
Přidejte následující řádek do souboru `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně stáhněte nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
- **Bezplatná zkušební verze:** Prozkoumejte funkce bez licence.  
- **Dočasná licence:** Použijte během hodnocení.  
- **Plná licence:** Zakupte pro produkční nasazení.

### Základní inicializace
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Jak přidat seskupený sloupcový graf na snímek?
`Presentation` je hlavní třída představující soubor PowerPoint. Načtěte novou `Presentation`, přidejte snímek a zavolejte `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Tento jediný volání vytvoří plně funkční seskupený sloupcový graf umístěný na zadaných souřadnicích. Poté můžete přistupovat k objektu grafu a upravovat série, datové body a vizuální styly.

## Průvodce krok za krokem

### Krok 1: Vytvořte prezentaci a přidejte seskupený sloupcový graf
Třída `Presentation` představuje dokument PowerPoint a umožňuje vytvářet snímky.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Krok 2: Správa sérií grafu
Nyní vymažeme jakékoli výchozí série, přidáme novou a naplníme ji jak kladnými, tak zápornými hodnotami.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Krok 3: Podmíněně převrátit záporné datové body
`invertIfNegative` metoda umožňuje převrácení záporných hodnot v sérii grafu.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Časté úskalí a tipy
- **Zapomněli jste uvolnit objekt `Presentation`?** Vždy zavolejte `dispose()` v bloku `finally`, aby se uvolnily nativní zdroje.  
- **Záporné hodnoty se neukazují jako převrácené?** Ujistěte se, že voláte `invertIfNegative(true)` **po** přidání datového bodu.  
- **Problémy s velikostí grafu:** Souřadnice (X, Y) a rozměry (šířka, výška) jsou v bodech; upravte je tak, aby odpovídaly rozvržení vašeho snímku.  

## Často kladené otázky

**Q:** Může​m vytvořit jiné typy grafů stejným přístupem?  
A: Ano, jednoduše nahraďte `ChartType.ClusteredColumn` libovolnou jinou hodnotou enumu `ChartType` (např. `Line`, `Pie`).  

**Q:** Potřebuji licenci pro vývojové sestavení?  
A: Dočasná nebo evaluační licence je vyžadována pro plný přístup k funkcím; jinak knihovna funguje v režimu zkušební verze s omezeními vodoznaku.  

**Q:** Jak exportovat prezentaci do PDF po přidání grafů?  
A: `SaveFormat.Pdf` určuje PDF jako výstupní formát pro uložení prezentace. Použijte `pres.save("output.pdf", SaveFormat.Pdf);` po dokončení úprav grafu.  

**Q:** Je možné stylovat jednotlivé sloupce (barva, okraj)?  
A: `IChartDataPoint` představuje jeden datový bod v grafu a umožňuje formátování. Každý `IChartDataPoint` poskytuje možnosti jako `getFillFormat().setFillType(FillType.Solid)` a `getLineFormat()`.  

**Q:** Co když potřebuji aktualizovat data grafu po uložení prezentace?  
A: Načtěte prezentaci znovu pomocí `new Presentation("file.pptx")`, upravte data grafu a znovu uložte.

---

**Poslední aktualizace:** 2026-06-03  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit vrstvený sloupcový graf v Javě s Aspose.Slides – Kompletní průvodce](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Jak vytvořit graf v Javě s Aspose.Slides – Ovládání tvorby grafů a validace](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Vytvoření a formátování grafů v Javě pomocí Aspose.Slides: Kompletní průvodce](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}