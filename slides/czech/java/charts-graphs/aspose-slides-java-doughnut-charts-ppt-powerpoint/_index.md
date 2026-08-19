---
date: '2026-07-08'
description: Naučte se, jak použít Aspose k vytvoření doughnut chart v PowerPointu
  pomocí Javy. Tento krok za krokem průvodce ukazuje, jak programově přidávat datové
  body do grafu, přizpůsobovat popisky a ukládat PPTX s vysokou věrností.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Jak použít Aspose vám umožní vytvořit doughnut chart v PowerPointu
  pomocí Javy. Postupujte podle tohoto tutoriálu a přidejte datové body, přizpůsobte
  popisky a uložte PPTX s vysokou věrností.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Jak použít Aspose: Vytvořit doughnut chart v PowerPointu (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Jak použít Aspose k vytvoření doughnut chart v PowerPointu (Java)
url: /cs/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak použít Aspose k vytvoření prstencového grafu v PowerPointu (Java)

## Úvod
Vytváření působivých prezentací často vyžaduje více než jen text a obrázky; grafy mohou výrazně zlepšit vyprávění tím, že efektivně vizualizují data. **Jak použít Aspose** pro generování grafů vám poskytuje programovou kontrolu, aniž byste museli otevírat PowerPoint. Tento tutoriál vás provede tvorbou prstencového grafu, nastavením jeho datových bodů a uložením vysoce kvalitního PPTX. Budete potřebovat jen základní znalosti Javy a pár minut na nastavení.

`Aspose.Slides for Java` je Java knihovna, která umožňuje vytvářet, upravovat a konvertovat soubory PowerPointu bez Microsoft Office.

## Rychlé odpovědi
- **Která knihovna vytváří prstencový graf v PowerPointu?** Aspose.Slides for Java  
- **Mohu přidávat datové body do grafu programově?** Ano, pomocí grafového API  
- **Potřebuji licenci pro produkční nasazení?** Vyžaduje se platná licence Aspose.Slides  
- **Jaké verze Javy jsou podporovány?** Java 8 a novější (ukázán klasifikátor JDK 16)  
- **Kolik sérií mohu přidat?** Příklad přidává až 15 sérií, ale můžete upravit podle potřeby  

## Co je prstencový graf v PowerPointu?
Prstencový graf je kruhový graf podobný koláčovému grafu, ale s dutým středem, což umožňuje zobrazit více sérií současně. Zdůrazňuje vztahy část‑celku a přitom zůstává vizuálně kompaktní a snadno čitelný.

## Proč použít Aspose.Slides for Java k vytváření prstencových grafů?
Aspose.Slides for Java podporuje více než 50 vstupních a výstupních formátů a dokáže generovat prezentace až do 500 MB, aniž by načítal celý soubor do paměti. Poskytuje plnou programovou kontrolu nad vzhledem grafu, daty a rozložením na jakékoli platformě Java, eliminuje COM interoperabilitu a dokáže vykreslit 100 slidů bohatých na grafy za méně než dvě sekundy na typickém serveru.

## Požadavky
- Základní znalost programování v Javě.  
- IDE, např. IntelliJ IDEA nebo Eclipse.  
- Maven nebo Gradle pro správu závislostí.  
- Platná licence Aspose.Slides for Java (k dispozici bezplatná zkušební verze).

## Nastavení Aspose.Slides for Java
Vyberte správce závislostí, který vyhovuje vašemu projektu.

**Maven**  
Do souboru `pom.xml` přidejte následující závislost (nahraďte verzi nejnovějším vydáním):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Do souboru `build.gradle` přidejte tento řádek:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Pokud raději stahujete přímo, navštivte stránku [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Pro delší používání zakupte licenci nebo požádejte o dočasnou licenci na [Aspose's website](https://purchase.aspose.com/temporary-license/). Postupujte podle pokynů pro nastavení prostředí a inicializaci Aspose.Slides ve vaší aplikaci.

## Jak vytvořit prstencový graf v PowerPointu pomocí Aspose.Slides for Java
Pro vytvoření prstencového grafu načtěte nebo vytvořte `Presentation`, přidejte grafový tvar typu `ChartType.Doughnut`, vymažte výchozí sérii, nastavte velikost díry a poté naplňte sešit grafu názvy kategorií a číselnými hodnotami. Nakonec upravte formátování popisků a uložte PPTX.

### Krok 1: Inicializace prezentace
Vytvořte novou prezentaci nebo otevřete existující soubor a získejte kolekci snímků.

`Presentation` je hlavní třída, která představuje soubor PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Krok 2: Přidání prstencového grafu na snímek
Vložte grafový tvar, odstraňte výchozí série/kategorie a nakonfigurujte základní vizuální nastavení, jako je velikost díry prstence.

`Chart` (nebo grafový tvar) představuje objekt grafu umístěný na snímku.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Krok 3: Přidání datových bodů do grafu a přizpůsobení popisků
Naplněte názvy kategorií, přidejte datové body pro každou sérii a doladěte formátování popisků (písmo, barva, pozice). Tento krok demonstruje schopnost „přidávat datové body do grafu“.

`Workbook` poskytuje přístup k podkladovým tabulkovým datům grafu, kde jsou buňky naplněny.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Krok 4: Uložení aktualizované prezentace
Uložte změny do nového souboru PPTX na disku.

`save` zapíše prezentaci do souboru ve zvoleném formátu.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Praktické aplikace
Prstencové grafy jsou ideální pro:
- **Finanční zprávy:** Vizualizace rozdělení rozpočtu nebo výdajů.  
- **Analýzu trhu:** Zobrazení podílu na trhu mezi konkurenty.  
- **Výsledky průzkumů:** Prezentace kategoriálních dat z průzkumu v kompaktní formě.  
- **Generování dashboardů:** Kombinace s databázovými dotazy pro tvorbu živě aktualizovaných slidů.

## Úvahy o výkonu
- **Uvolňování zdrojů:** Po uložení zavolejte `pres.dispose()`, aby se uvolnila nativní paměť.  
- **Omezení počtu grafů:** Přidání stovek grafů může zvýšit spotřebu paměti; v případě potřeby zpracovávejte dávky.  
- **Použití streamování:** Pro obrovské datové sady naplňujte sešit přímo ze streamů místo paměťových polí.  

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Graf se zobrazuje prázdně** | Buňky dat nejsou správně naplněny | Ověřte, že `workBook.getCell(...)` odkazuje na správné řádky/sloupce. |
| **Popisky se překrývají** | Příliš mnoho kategorií v omezeném prostoru | Zvyšte `DoughnutHoleSize` nebo upravte `FirstSliceAngle`. |
| **OutOfMemoryError** | Velké prezentace bez uvolnění zdrojů | Po uložení zavolejte `pres.dispose()` a zvažte zvýšení velikosti haldy JVM. |

## Často kladené otázky

**Q: Mohu používat Aspose.Slides for Java v komerčních aplikacích?**  
A: Ano, ale potřebujete platnou komerční licenci. Bezplatná zkušební verze je k dispozici pro vyhodnocení.

**Q: Jak přidat více než 15 sérií?**  
A: Zvyšte limit smyčky v kroku „Add Doughnut Chart“ a ujistěte se, že váš sešit obsahuje dostatek řádků.

**Q: Je možné změnit velikost díry prstence po vytvoření?**  
A: Ano, před uložením zavolejte `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`.

**Q: Můžu exportovat graf jako obrázek místo PPTX?**  
A: Rozhodně. Použijte `chart.getImage()` a uložte vrácený `java.awt.image.BufferedImage` v požadovaném formátu.

**Q: Podporuje Aspose.Slides animované grafy?**  
A: Animaci lze přidat pomocí API `ISlide.getTimeline()`, i když to přesahuje rozsah tohoto tutoriálu.

## Závěr
Nyní máte kompletní, připravenou metodu pro **vytvoření prstencového grafu v PowerPointu** s Aspose.Slides for Java, včetně toho, jak **přidávat datové body do grafu**, přizpůsobit popisky a řešit výkonnostní úvahy. Experimentujte s různými barvami, zdroji dat a typy grafů, aby vaše prezentace opravdu vynikly.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Související tutoriály

- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides for Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak upravit data grafu v PowerPointu pomocí Aspose.Slides for Java: Kompletní průvodce](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animovat grafy v PowerPointu pomocí Aspose.Slides for Java – Průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}