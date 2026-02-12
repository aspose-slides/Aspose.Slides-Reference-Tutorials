---
date: '2026-02-12'
description: Naučte se, jak vytvářet grafy a spravovat grafy pomocí Aspose.Slides
  pro Javu. Tento tutoriál ukazuje, jak vytvořit seskupený sloupcový graf, pracovat
  s datovými řadami a přizpůsobit vizualizaci.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Jak vytvořit graf v Javě pomocí Aspose.Slides: komplexní průvodce'
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit graf v Javě s Aspose.Slides

## Jak vytvořit graf v Javě: Úvod
Vytváření dynamických prezentací často zahrnuje vizualizaci dat pomocí grafů. S **Aspose.Slides for Java** můžete snadno **jak vytvořit graf** objekty, zvýšit přehlednost a udělat silnější dojem na své publikum. Tento tutoriál vás provede nastavením knihovny, přidáním **vytvoření seskupeného sloupcového grafu**, správou sérií a podmíněným převracením záporných datových bodů.

**Co se naučíte**
- Jak nastavit Aspose.Slides for Java.
- Kroky k **vytvoření seskupeného sloupcového grafu** ve vaší prezentaci.
- Techniky pro správu sérií grafu a datových bodů.
- Metody pro podmíněné převracení záporných datových bodů pro lepší vizualizaci.
- Jak bezpečně uložit prezentaci.

### Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Slides for Java.
- **Jaký typ grafu je předveden?** Seskupený sloupcový graf.
- **Mohu převrátit záporné hodnoty?** Ano, pomocí `invertIfNegative`.
- **Jaká verze Javy je požadována?** JDK 16 nebo novější.
- **Je pro produkci potřeba licence?** Ano, platná licence Aspose.

## Co je seskupený sloupcový graf?
Seskupený sloupcový graf zobrazuje více datových sérií vedle sebe pro každou kategorii, což usnadňuje porovnání hodnot mezi skupinami. Je ideální pro finanční zprávy, prodejní dashboardy a jakýkoli scénář, kde potřebujete kontrastovat několik metrik.

## Proč použít Aspose.Slides pro tvorbu grafů?
- **Plná kontrola** nad vzhledem grafu bez nutnosti spoléhat se na UI PowerPointu.
- **Programová generace** umožňuje automatizované reportingové pipeline.
- **Cross‑platform** podpora zajišťuje, že váš kód běží na jakémkoli Java‑kompatibilním systému.
- **Bohaté API** pro detailní přizpůsobení (barvy, datové popisky, inverze atd.).

## Požadavky
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
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace pomocí Gradle
Add the following line to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
- **Free Trial:** Prozkoumejte funkce bez licence.
- **Temporary License:** Použijte během hodnocení.
- **Full License:** Zakupte pro produkční nasazení.

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Průvodce krok za krokem

### Krok 1: Vytvořte prezentaci a přidejte seskupený sloupcový graf
V tomto kroku **jak vytvořit graf** objekty a umístíme **vytvoření seskupeného sloupcového grafu** na první snímek.

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
Nyní vymažeme všechny výchozí série, přidáme novou a naplníme ji jak kladnými, tak zápornými hodnotami.

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

### Krok 3: Podmíněné převracení záporných datových bodů
Ve výchozím nastavení Aspose.Slides nepřevrací záporné hodnoty. Povolení inverze aktivujeme pouze pro ty body, které to vyžadují.

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

### Časté úskalí a tipy
- **Zapomněli jste uvolnit objekt `Presentation`?** Vždy zavolejte `dispose()` v bloku `finally`, aby se uvolnily nativní zdroje.
- **Záporné hodnoty se neukazují jako převrácené?** Ujistěte se, že voláte `invertIfNegative(true)` **po** přidání datového bodu.
- **Problémy s velikostí grafu:** Souřadnice (X, Y) a rozměry (šířka, výška) jsou v bodech; upravte je tak, aby vyhovovaly rozvržení snímku.

## Často kladené otázky

**Q: Mohu vytvořit jiné typy grafů stejným přístupem?**  
A: Ano, stačí nahradit `ChartType.ClusteredColumn` libovolnou jinou hodnotou výčtu `ChartType` (např. `Line`, `Pie`).

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Dočasná nebo evaluační licence je vyžadována pro plný přístup k funkcím; jinak knihovna funguje v režimu zkušební verze s omezeními vodoznaku.

**Q: Jak exportovat prezentaci do PDF po přidání grafů?**  
A: Použijte `pres.save("output.pdf", SaveFormat.Pdf);` po dokončení manipulace s grafem.

**Q: Je možné stylovat jednotlivé sloupce (barva, okraj)?**  
A: Ano, každý `IChartDataPoint` poskytuje možnosti formátování jako `getFillFormat().setFillType(FillType.Solid)` a `getLineFormat()`.

**Q: Co když potřebuji aktualizovat data grafu po uložení prezentace?**  
A: Načtěte prezentaci znovu pomocí `new Presentation("file.pptx")`, upravte data grafu a znovu uložte.

---

**Poslední aktualizace:** 2026-02-12  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}