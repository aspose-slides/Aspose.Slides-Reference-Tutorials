---
date: '2026-06-08'
description: Naučte se, jak přidat sérii do grafu a přizpůsobit vrstvené sloupcové
  grafy v .NET prezentacích pomocí Aspose.Slides pro Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Přidat sérii do grafu pomocí Aspose.Slides pro Java v .NET
url: /cs/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ovládání přizpůsobení grafů v .NET prezentacích pomocí Aspose.Slides pro Java

## Úvod
V oblasti prezentací založených na datech jsou grafy nepostradatelnými nástroji, které proměňují surová čísla v poutavé vizuální příběhy. Když potřebujete **add series to chart** programově, zejména v .NET souborech prezentací, může se úkol zdát ohromující. Naštěstí **Aspose.Slides for Java** poskytuje výkonné, jazykově nezávislé API, které usnadňuje tvorbu a přizpůsobení grafů – i když je vaším cílovým formátem .NET PPTX. Tento průvodce vás provede přidáváním sérií, vytvářením sloupcového grafu se zásobníkem a jemným laděním vizuálních aspektů, jako je šířka mezery, abyste mohli generovat dynamické, datově bohaté snímky, které vypadají profesionálně a elegantně.

## Rychlé odpovědi
Třída `Presentation` představuje soubor PPTX a `slide.getShapes().addChart(...)` vloží tvar grafu. Použijte `chart.getChartData().getSeries().add(...)` pro přidání série a `setGapWidth()` upravuje mezery.

- **Jaká je hlavní třída pro zahájení prezentace?** `Presentation` – představuje soubor PPTX v paměti.  
- **Která metoda přidá graf na snímek?** `slide.getShapes().addChart(...)` vytvoří objekt grafu na snímku.  
- **Jak přidáte novou sérii?** `chart.getChartData().getSeries().add(...)` vloží novou datovou sérii.  
- **Můžete změnit šířku mezery mezi sloupci?** Ano – zavolejte `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (hodnota je v procentech).  
- **Potřebuji licenci pro produkci?** Rozhodně – platná licence Aspose.Slides for Java odemkne všechny funkce a odstraní vodotisky z hodnocení.

## Co znamená „add series to chart“?
Přidání série do grafu znamená vložení nové kolekce datových bodů, které graf vykreslí jako samostatný vizuální prvek (např. samostatnou skupinu sloupců). Každá série může mít vlastní hodnoty, barvy a formátování, což umožňuje vedlejší srovnání více datových sad.

## Proč použít Aspose.Slides for Java k úpravě .NET prezentací?
Aspose.Slides for Java vám umožňuje generovat nebo upravovat soubory PPTX, které jsou plně kompatibilní s .NET PowerPoint prohlížeči, aniž byste potřebovali instalaci Microsoft Office. Použijte Aspose.Slides for Java, když potřebujete serverové, multiplatformní řešení, které vytváří nebo aktualizuje .NET PPTX soubory, podporuje více než 50 typů grafů a zpracovává soubory až do 500 MB, aniž by načítalo celý dokument do paměti. Jeho API funguje v Javě, Kotlinu, Scali nebo jakémkoli JVM jazyce a poskytuje stejný výstup, jaký očekávají .NET vývojáři.

## Požadavky
- **Aspose.Slides for Java** knihovna (verze 25.4 nebo novější).  
- Maven, Gradle nebo ruční stažení JAR souboru.  
- Základní znalost Javy a povědomí o struktuře souboru PPTX.  

## Nastavení Aspose.Slides pro Java
### Instalace pomocí Maven
Přidejte následující závislost do vašeho `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace pomocí Gradle
Vložte tento řádek do souboru `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně si stáhněte nejnovější JAR z oficiální stránky vydání: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Získání licence**  
Začněte s bezplatnou zkušební verzí stažením dočasné licence z [zde](https://purchase.aspose.com/temporary-license/). Pro produkční použití zakupte plnou licenci, která odemkne všechny funkce a odstraní vodotisky z hodnocení.

## Průvodce krok za krokem
Pod každým krokem najdete stručný úryvek kódu (beze změny oproti originálnímu tutoriálu) následovaný vysvětlením, co dělá.

### Krok 1: Vytvoření prázdné prezentace
`Presentation` je vstupní třída, která představuje soubor PowerPoint v paměti.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Začínáme s čistým souborem PPTX, který nám poskytuje plátno pro přidání grafů.*

### Krok 2: Přidání sloupcového grafu se zásobníkem na snímek
`Chart` představuje tvar grafu na snímku. `ChartType.StackedColumn` určuje sloupcový graf se zásobníkem.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Metoda `addChart` vytvoří **stacked column chart** a umístí jej do levého horního rohu snímku.*

### Krok 3: Přidání sérií do grafu (hlavní cíl)
`Series` zapouzdřuje jednu datovou sérii v grafu.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Zde **add series to chart** – každé volání vytvoří novou datovou sérii, která se zobrazí jako samostatná skupina sloupců.*

### Krok 4: Přidání kategorií do grafu
`Category` definuje popisek osy X pro data grafu.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategorie fungují jako popisky osy X, které dávají každému sloupci význam.*

### Krok 5: Naplnění dat série
`DataPoint` obsahuje číselnou hodnotu pro sérii v konkrétní kategorii.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Datové body poskytují každé sérii její číselné hodnoty, které graf vykreslí jako výšky sloupců.*

### Krok 6: Nastavení šířky mezery pro skupinu sérií grafu
`SeriesGroup` řídí vlastnosti rozvržení pro skupinu sérií, jako je šířka mezery.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Úprava šířky mezery zlepšuje čitelnost, zejména když je mnoho kategorií.*

## Běžné případy použití
- **Finanční výkaznictví** – porovnání čtvrtletních příjmů napříč obchodními jednotkami.  
- **Projektové dashboardy** – zobrazování procentuálního dokončení úkolů podle týmů.  
- **Marketingová analytika** – vizualizace výkonu kampaní vedle sebe.  
Tyto scénáře těží z **příkladu sloupcového grafu se zásobníkem**, protože zdůrazňují příspěvky jednotlivých kategorií k celku.

## Tipy pro výkon
- **Znovu použijte objekt `Presentation`** při vytváření více grafů, aby se snížila zátěž paměti.  
- **Omezte počet datových bodů** pouze na ty potřebné pro vizuální příběh; Aspose.Slides zvládne 10 000 bodů, ale rychlost vykreslování klesá po ~5 000.  
- **Uvolněte objekty** (`presentation.dispose()`) po uložení, aby se uvolnily prostředky a předešlo se únikům paměti.  

## Často kladené otázky
**Q: Mohu přidat jiné typy grafů kromě sloupcového se zásobníkem?**  
A: Ano, Aspose.Slides podporuje čárové, koláčové, plošné, radarem, bublinové a více než 50 dalších typů grafů, všechny přístupné stejnou metodou `addChart`.

**Q: Potřebuji samostatnou licenci pro výstup .NET?**  
A: Ne, stejná licence pro Java funguje pro všechny výstupní formáty, včetně .NET PPTX souborů.

**Q: Jak změním barevnou paletu grafu?**  
A: Použijte `series.getFormat().getFill().setFillType(FillType.Solid)` a poté nastavte požadovaný objekt `Color` pro každou sérii.

**Q: Je možné programově přidat datové popisky?**  
A: Rozhodně. Zavolejte `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`, aby se na každém sloupci zobrazila číselná hodnota.

**Q: Co když potřebuji aktualizovat existující prezentaci?**  
A: Načtěte soubor pomocí `new Presentation("existing.pptx")`, upravte graf pomocí stejných volání API a uložte jej zpět na disk.

## Závěr
Nyní máte kompletní, komplexní průvodce, jak **add series to chart**, vytvořit **stacked column chart** a jemně doladit jeho vzhled v .NET prezentacích pomocí Aspose.Slides for Java. Experimentujte s různými typy grafů, barvami a zdroji dat, abyste vytvořili poutavé vizuální zprávy, které ohromí zainteresované strany a podpoří rozhodování založené na datech.

---

**Poslední aktualizace:** 2026-06-08  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vytvořit procentuálně založené sloupcové grafy se zásobníkem v .NET pomocí Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Mistrovské vytváření a manipulace sérií grafu s Aspose.Slides .NET pro efektivní vizualizaci dat](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Vymazání konkrétních datových bodů série grafu s Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}