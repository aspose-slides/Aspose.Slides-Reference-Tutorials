---
date: '2026-09-12'
description: Zjistěte, jak použít Maven Aspose Slides k přidání a přizpůsobení dynamic
  stock charts v PowerPointu s Java. Obsahuje setup, adding data series, formatting
  lines a saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides tutoriál ukazuje, jak vytvořit a přizpůsobit dynamic
  stock charts v PowerPointu pomocí Java, zahrnující data series, line formatting
  a saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides průvodce: vytvořte dynamic stock charts v PowerPointu'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: vytvořte dynamic stock charts v PowerPointu s Java'
url: /cs/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: vytvořte dynamické akciové grafy v PowerPointu pomocí Javy

## Úvod

**Maven Aspose Slides** vám umožňuje programově generovat sofistikované prezentace PowerPoint z Javy. V tomto tutoriálu se naučíte, jak vytvořit dynamické akciové grafy, přidávat a formátovat datové řady, přizpůsobovat čáry grafu a nakonec soubor uložit. Ať už jste finanční analytik připravující čtvrtletní zprávy nebo vývojář budující automatizované sady snímků, níže uvedené kroky vám poskytnou kompletní, připravené pro produkci řešení.

**Co se naučíte**
- Jak nastavit Maven s Aspose.Slides pro Java  
- Jak přidat akciový graf a vymazat výchozí data  
- Jak **přidat datovou řadu grafu** a **formátovat čáry grafu**  
- Jak **přizpůsobit specifické vizuální prvky grafu v Javě**  
- Jak uložit aktualizovanou prezentaci

Připraveni převést surová čísla na poutavé akciové vizualizace? Pojďme začít!

## Rychlé odpovědi
- **Jaký Maven artefakt potřebuji?** `aspose-slides` verze 25.4 (nebo novější).  
- **Mohu to spustit na jakémkoli OS?** Ano – knihovna je čistá Java a funguje na Windows, macOS a Linuxu.  
- **Potřebuji licenci pro vývoj?** Bezplatná dočasná licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Jaké typy grafů jsou podporovány?** Více než 70 vestavěných typů grafů, včetně Stock, Line a Bar grafů.  
- **Jak velkou prezentaci mohu zpracovat?** Aspose.Slides dokáže zpracovat soubory s více než 500 snímky, aniž by načítala celý soubor do paměti.

## Co je Maven Aspose Slides?

`Aspose.Slides for Java` je Java API, které umožňuje vytváření, manipulaci a konverzi souborů PowerPoint bez Microsoft Office. Integrace s Mavenem zjednodušuje správu závislostí a umožňuje stáhnout knihovnu přímo z Maven Central.

## Proč používat Maven Aspose Slides pro akciové grafy?

Aspose.Slides podporuje **více než 70 typů grafů** a dokáže vykreslit prezentace o stovkách stránek za méně než sekundu na typickém serverovém hardware. Jeho funkce **high‑low line** a **up/down bar** vám poskytují přesnou kontrolu nad finančními vizualizacemi, daleko přesahující možnosti UI PowerPointu.

## Požadavky

- **Java Development Kit (JDK)** – verze 11 nebo vyšší.  
- **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor, který preferujete.  
- **Aspose.Slides for Java** – verze 25.4 (nejnovější v době psaní).  

### Nastavení Aspose.Slides pro Java

#### Maven
Pro integraci Aspose.Slides do vašeho projektu pomocí Maven přidejte následující závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Pro uživatele Gradle zahrňte toto do souboru `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direct download
Alternativně stáhněte nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Získání licence** – začněte s bezplatnou zkušební verzí nebo požádejte o dočasnou licenci. Pro komerční použití zakupte plnou licenci.

Pro podrobnou referenci API viz [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Jak vytvořit dynamický akciový graf krok za krokem

Načtěte svou prezentaci, přidejte akciový graf, vymažte výchozí data a poté vložte vlastní řady a kategorie. Přímá odpověď na hlavní otázku je:

> Načtěte existující PPTX pomocí `new Presentation("template.pptx")`, přidejte `Chart` typu `ChartType.Stock`, vymažte jeho výchozí řady a kategorie, poté jej naplňte vlastními datovými body a možnostmi formátování. Nakonec zavolejte `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inicializace prezentace
#### Overview
Začněte načtením existujícího souboru PowerPoint, abyste jej mohli upravit přímo.

#### Step‑by‑step
1. **Import knihovny** – třída `Presentation` je vstupním bodem pro všechny operace se snímky.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Načtěte soubor prezentace** – zadejte cestu k vašemu šablonovému PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání akciového grafu na snímek
#### Overview
Vložte akciový graf na první snímek prezentace.

Třída `Chart` představuje tvar grafu, který lze přidat na snímek.

#### Direct answer
Akciový graf přidáte voláním `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Tím se vytvoří objekt grafu, který můžete okamžitě manipulovat.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Vymazání existujících datových řad a kategorií v grafu
#### Overview
Odstraňte všechny předem naplněné řady nebo kategorie, abyste mohli začít s čistým datovým souborem.

Objekt `ChartData` obsahuje řady a kategorie pro graf.

#### Direct answer
Zavolejte `chart.getChartData().getSeries().clear()` a `chart.getChartData().getCategories().clear()`, abyste vymazali výchozí obsah před přidáním vlastního.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání kategorií do dat grafu
#### Overview
Definujte kategorie osy X (např. data), které seskupují vaše akciové hodnoty.

`ChartCategory` představuje popisek osy X pro graf.

#### Direct answer
Vytvořte nový `ChartCategory` pro každý popisek pomocí `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` a opakujte pro každý měsíc nebo období.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání datových řad do grafu
#### Overview
Přidejte čtyři základní řady: Open, High, Low a Close.

`ChartSeries` obsahuje kolekci datových bodů pro konkrétní řadu v grafu.

#### Direct answer
Pro každou řadu zavolejte `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Tím se řada zaregistruje v datovém sešitu grafu.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání datových bodů do řady
#### Overview
Naplněte každou řadu číselnými hodnotami představujícími ceny akcií.

`DataPoint` představuje jedinou hodnotu v řadě.

#### Direct answer
Projděte svou kolekci dat a použijte `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (nebo vhodnou metodu pro typ řady) k vložení každého bodu.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formátování high‑low line a up/down bar
#### Overview
Upravte vizuální styl high‑low spojnic a výplní up/down bar.

`Marker` definuje vizuální symbol pro datový bod.

#### Direct answer
Nastavte `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` a nakonfigurujte `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)`, abyste ovládali tloušťku a barvu čáry.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Display up/down bars
Použijte metodu grafu `setShowUpDownBars(true)`, aby byly up/down bary viditelné.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Přizpůsobení popisků dat na high‑low line
#### Overview
Zobrazte číselné hodnoty přímo na high‑low line pro rychlou referenci.

`DataLabel` řídí vzhled popisků připojených k datovým bodům.

#### Direct answer
Povolte popisky dat pomocí `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` a upravte jejich styl podle potřeby.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Nastavení barvy výplně up/down bar
#### Overview
Dejte up barům zelenou výplň a down barům červenou výplň, aby intuitivně vyjadřovaly pohyb trhu.

Objekt `UpDownBars` poskytuje přístup k formátování up a down bar.

#### Direct answer
Použijte `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` a nastavte pevnou barvu na `Color.GREEN`; opakujte pro down bar s `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Uložení souboru PowerPoint
#### Overview
Uložte své změny do nového souboru PPTX.

Metoda `save` zapisuje prezentaci na disk ve zvoleném formátu.

#### Direct answer
Zavolejte `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – tím se upravená prezentace zapíše na disk ve standardním formátu PowerPoint.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Časté problémy a řešení

- **Graf se nezobrazuje** – ujistěte se, že souřadnice X/Y a rozměry grafu jsou v mezích snímku.  
- **Chybějící datové body** – ověřte, že indexy buněk datového sešitu odpovídají řadě/řádku, který chcete naplnit.  
- **Výjimka licence** – dočasná zkušební licence vyprší po 30 dnech; nahraďte ji trvalou licencí pro produkční sestavení.  
- **Zpomalení výkonu u velkých souborů** – použijte `Presentation.setCacheSize(0)` k vypnutí cache, pokud zpracováváte tisíce snímků najednou.

## Často kladené otázky

**Q: Mohu tento kód použít ve webové aplikaci?**  
A: Ano. Knihovna je čistá Java, takže ji můžete spustit v jakémkoli servlet kontejneru nebo službě Spring Boot.

**Q: Podporuje Aspose.Slides i jiné typy grafů kromě Stock?**  
A: Rozhodně. Podporuje více než 70 typů grafů, včetně Line, Bar, Pie a Radar grafů.

**Q: Jak programově přidám název grafu?**  
A: Použijte `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` a poté název podle potřeby naformátujte.

**Q: Existuje limit počtu datových bodů na řadu?**  
A: Prakticky můžete přidat desítky tisíc bodů; spotřeba paměti roste lineárně a knihovna streamuje data, aby udržela nízkou paměťovou stopu.

**Q: Jaké Maven koordináty mám použít pro nejnovější verzi?**  
A: Nejnovější verze je vždy k dispozici pod `com.aspose:aspose-slides:25.4` (nebo novější) na Maven Central.

---

**Poslední aktualizace:** 2026-09-12  
**Testováno s:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Související tutoriály

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Create Format Powerpoint Charts Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}