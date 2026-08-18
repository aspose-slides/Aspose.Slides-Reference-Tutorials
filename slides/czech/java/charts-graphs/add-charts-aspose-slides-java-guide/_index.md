---
date: '2026-06-03'
description: Zjistěte, jak přidat grafy pomocí aspose slides maven dependency, konfigurovat
  popisky dat a generovat dynamické grafy v Java prezentacích.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Přidání a konfigurace grafů v prezentacích
  pomocí Aspose.Slides pro Java'
url: /cs/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Přidání a konfigurace grafů v prezentacích pomocí Aspose.Slides pro Java

## Úvod
The **aspose slides maven dependency** umožňuje vývojářům Java programově vytvářet, upravovat a obohacovat soubory PowerPoint, aniž by kdykoliv otevírali samotný PowerPoint. V mnoha obchodních a akademických scénářích je ruční vkládání grafů časově náročné a náchylné k chybám. Tento tutoriál vám krok za krokem ukáže, jak přidat bublinový graf, svázat popisky dat s buňkami listu a výsledek uložit – vše s využitím aspose slides maven dependency v čistém, opakovatelném způsobu.

**Co se naučíte**
- Jak přidávat grafy pomocí aspose slides maven dependency
- Nastavení Java projektu pomocí Maven nebo Gradle
- Načtení existující prezentace a vložení bublinového grafu
- Konfigurace popisků dat pomocí odkazů na buňky (přidání popisků dat do grafu)
- Uložení aktualizovaného souboru pro pozdější distribuci
- Reálné příklady použití, jako je dynamické generování grafů a tvorba pracovních postupů pro grafy v prezentacích

## Rychlé odpovědi
- **Který Maven artefakt přidává možnosti grafů?** `com.aspose:aspose-slides:25.4` (nebo nejnovější)  
- **Mohu svázat popisky dat s buňkami ve stylu Excel?** Ano – použijte `ChartDataLabel` s `setDataLabelFormat` a odkazy na buňky.  
- **Je pro produkci vyžadována licence?** Plná licence odstraňuje vodoznak z hodnocení a odemyká všechny funkce.  
- **Bude to fungovat na Java 11+?** Rozhodně; knihovna je kompatibilní s Java 8 až Java 21.  
- **Kolik typů grafů je podporováno?** Více než 70 různých typů grafů, včetně bublinových, radarových a akciových grafů.

## Co je aspose slides maven dependency?
The **aspose slides maven dependency** je Maven‑kompatibilní balíček, který poskytuje plnohodnotné API pro vytváření a úpravu souborů PowerPoint (PPTX, PPT, ODP) v Javě. Přidáním této závislosti do vašeho `pom.xml` nebo `build.gradle` získáte přístup k více než 70 typům grafů, 150+ rozvržením snímků a možnosti manipulovat s tvary, animacemi a metadaty bez nutnosti instalace Office.

## Proč použít aspose slides maven dependency pro automatizaci grafů?
Aspose.Slides zpracovává tisíce snímků během méně než sekundy na standardním serverovém hardware, podporuje **70+ typů grafů** a může renderovat prezentace až do **10 000 snímků** bez načítání celého souboru do paměti. Tyto kvantifikovatelné schopnosti ho činí ideálním pro podnikovou dynamickou generaci grafů, kde jsou výkon a škálovatelnost nevyjednatelné.

## Předpoklady
- **Java Development Kit (JDK)** 8 nebo novější (doporučeno Java 11+).  
- **Maven** 3.6+ **nebo** **Gradle** 6+.  
- **Aspose.Slides for Java** knihovna (aspose slides maven dependency, verze 25.4 nebo novější).  
- Základní znalost Java kolekcí a souborového I/O.  
- Evaluační nebo plná licenční soubor (`license.json`) pokud plánujete spouštět kód po zkušební období.

## Jak přidat graf do snímku pomocí Aspose.Slides?
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### Krok 1: Přidat aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
These snippets pull the full Aspose.Slides API—including chart support—directly from Maven Central.

### Krok 2: Načíst prezentaci a vložit bublinový graf
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Krok 3: Konfigurace datových sérií a popisků grafu
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Krok 4: Uložit upravenou prezentaci
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Jak konfigurovat popisky dat pomocí odkazů na buňky?
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### Přímá odpověď
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### Krok za krokem
1. Identify the series you wish to label.  
2. Retrieve the `IDataLabel` object for each data point.  
3. Use `setDataLabelFormat` with `DataLabelFormat` configured for `CellReference`.  
4. Optionally customize font, color, and display options.

## Jak uložit upravenou prezentaci?
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### Přímá odpověď
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## Praktické aplikace
1. **Business Reports:** Generate quarterly sales charts automatically from a database dump.  
2. **Academic Lectures:** Pull live research data into lecture slides for each class session.  
3. **Sales Pitches:** Build client‑specific performance dashboards on the fly.  
4. **Project Management:** Visualize Gantt‑style timelines with dynamic data labels.  
5. **Marketing Analytics:** Embed campaign KPIs into presentations that update as new metrics arrive.

## Úvahy o výkonu
- **Memory Management:** Use try‑with‑resources or explicit `presentation.dispose()` to free native memory promptly.  
- **Large Datasets:** When handling more than 10,000 data points, populate chart data via `ChartDataWorkbook` to avoid loading the entire dataset into Java objects.  
- **Thread Safety:** Each thread should work with its own `Presentation` instance; the API is not thread‑safe across shared objects.  

## Časté problémy a řešení
- **Problém:** “License file not found.”  
  **Řešení:** Umístěte `license.json` do classpath a zavolejte `License license = new License(); license.setLicense("license.json");` před jakýmkoli použitím API.  
- **Problém:** Graf se po uložení zobrazuje prázdně.  
  **Řešení:** Ujistěte se, že datový sešit grafu je uložen s prezentací (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problém:** Popisky dat zobrazují chyby “#REF!”.  
  **Řešení:** Ověřte, že řetězec odkazu na buňku odpovídá přesnému názvu listu a adrese a že odkazovaný sešit je připojen k grafu.  

## Často kladené otázky

**Q: Mohu přidat jiné typy grafů kromě bublinového?**  
A: Ano, výčet `ChartType` zahrnuje čárový, sloupcový, koláčový, radarový, akciový a více než 70 dalších typů.

**Q: Funguje aspose slides maven dependency s OpenJDK?**  
A: Rozhodně; je plně kompatibilní s OpenJDK 8‑21 a běží na všech hlavních operačních systémech.

**Q: Jak vložit graf z existujícího souboru Excel?**  
A: Načtěte sešit Excel pomocí `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, poté svázat `ChartDataWorkbook` grafu se sešitem před nastavením odkazů na buňky.

**Q: Existuje limit na počet grafů na snímku?**  
A: Prakticky ne – Aspose.Slides dokáže zvládnout desítky grafů na snímku, omezené jen dostupnou pamětí.

**Q: Do jakých formátů mohu exportovat finální prezentaci?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML a dokonce i obrazové formáty jako PNG a JPEG jsou podporovány.

## Zdroje
- [Aspose.Slides pro Java vydání](https://releases.aspose.com/slides/java/) – stáhněte nejnovější binární knihovny.  
- [Dokumentace Aspose.Slides](https://reference.aspose.com/slides/java/) – komplexní reference API a průvodci.  
- [Stáhnout Aspose.Slides pro Java](https://releases.aspose.com/slides/java/) – přímá stránka ke stažení balíčků Maven/Gradle.  
- [Zakoupit licenci](https://purchase.aspose.com/buy) – získat plnou komerční licenci.  
- [Bezplatná zkušební verze](https://releases.aspose.com/slides/java/) – začněte zkušební verzí k vyzkoušení funkcí.  
- [Dočasná licence](https://purchase.aspose.com/temporary-license/) – požádejte o dočasný klíč pro prodloužené hodnocení.  
- [Fórum podpory Aspose](https://forum.aspose.com/c/slides/11) – získejte pomoc od komunity a inženýrů Aspose.

## Závěr
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**Poslední aktualizace:** 2026-06-03  
**Testováno s:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Související tutoriály

- [Jak vytvořit a konfigurovat prezentace s Aspose.Slides Java: Průvodce krok za krokem](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Vytvořit PPTX v Javě s Aspose.Slides Maven – Průvodce automatizací](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Jak vytvořit graf v Javě s Aspose.Slides: Komplexní průvodce](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}