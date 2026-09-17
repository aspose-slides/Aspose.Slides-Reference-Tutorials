---
date: '2026-09-17'
description: Naučte se, jak přidat clustered column chart do prezentace PowerPoint,
  přizpůsobit PowerPoint chart a vložit data series chart pomocí Aspose.Slides pro
  Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Naučte se, jak přidat clustered column chart do prezentace PowerPoint
  pomocí Aspose.Slides pro Java, včetně kroků pro vložení data series, přizpůsobení
  grouping a uložení souboru jako PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Přidejte clustered column chart do PowerPointu pomocí Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Jak přidat clustered column chart v PowerPointu pomocí Aspose.Slides pro Java
url: /cs/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat seskupený sloupcový graf v PowerPointu pomocí Aspose.Slides pro Java

## Úvod

Když potřebujete **přidat seskupený sloupcový graf** do prezentace PowerPoint, přehledná vizualizace může proměnit surová čísla v okamžitě pochopitelný příběh. Provádět to ručně v PowerPointu může být časově náročné, zejména když musíte programově generovat mnoho snímků. **Aspose.Slides for Java** odstraňuje tuto překážku – umožňuje vám vytvořit, přizpůsobit graf v PowerPointu a vložit datové řady grafu pomocí několika řádků kódu.

- Inicializovat novou prezentaci PowerPoint pomocí Aspose.Slides for Java.  
- **Přidat graf na snímek** a nakonfigurovat jej jako seskupený sloupcový graf.  
- **Vytvořit seskupený sloupcový graf** definováním úrovní seskupení pro kategorie.  
- **Vložit datovou řadu do grafu** aby byla data zobrazena správně.  
- Uložit hotovou prezentaci jako soubor PPTX.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `Presentation` z `com.aspose.slides`.  
- **Jaký typ grafu se používá?** `ChartType.ClusteredColumn`.  
- **Potřebuji licenci pro testování?** Bezplatná zkušební verze funguje, ale licence odstraňuje omezení hodnocení.  
- **Jaká verze Javy je podporována?** JDK 16 nebo novější (příklad používá JDK 16).  
- **Jak spustit ukázku?** Přidejte Maven/Gradle závislost, zkompilujte a spusťte metodu `main`.

## Co je „přidání seskupeného sloupcového grafu“?

Seskupený sloupcový graf zobrazuje více datových řad vedle sebe pro každou kategorii, což vám umožňuje porovnávat hodnoty napříč skupinami v jedné vizualizaci. Je ideální pro čtvrtletní prodeje, výsledky průzkumů nebo jakýkoli scénář, kde potřebujete kontrastovat několik datových sad ve stejné kategorii.

## Proč použít Aspose.Slides pro přidání seskupeného sloupcového grafu?

Můžete automaticky vygenerovat desítky snímků, přizpůsobit každý vizuální prvek a spustit kód na libovolném OS, který podporuje Javu – není vyžadována instalace Microsoft Office. Aspose.Slides podporuje **více než 50 typů grafů** a dokáže zpracovat prezentace s **až 500 snímky** bez načítání celého souboru do paměti, což je vhodné pro rozsáhlé reportingové pipeline.

## Požadavky

- Knihovna **Aspose.Slides for Java** (doporučena nejnovější verze).  
- JDK 16 nebo novější.  
- Nástroj pro sestavení Maven nebo Gradle (nebo můžete JAR přidat ručně).  
- IDE nebo textový editor pro spuštění Java kódu.

## Nastavení Aspose.Slides pro Java

Přidejte knihovnu do svého projektu pomocí jednoho z následujících skriptů pro sestavení.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně můžete přímo stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence

Před nasazením do produkce získáte licenci:
- **Bezplatná zkušební verze** – prozkoumejte všechny funkce bez nákupu.  
- **Dočasná licence** – vyzkoušejte rozšířené možnosti na krátkou dobu.  
- **Plná licence** – odemkne neomezené používání. Získejte ji na [Aspose's purchase page](https://purchase.aspose.com/buy).

## Jak přidat seskupený sloupcový graf v PowerPointu pomocí Aspose.Slides pro Java?

Načtěte novou `Presentation`, přidejte snímek, vložte `Chart` typu `ChartType.ClusteredColumn`, naplňte jeho interní sešit kategoriemi a řadami a poté uložte soubor jako PPTX. Tento postup vytvoří plně funkční seskupený sloupcový graf pomocí několika volání API.

### Inicializace prezentace

`Presentation` je třída, která v paměti představuje soubor PowerPoint, což vám umožňuje programově přidávat snímky, tvary a grafy.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Přidání grafu na snímek

`ChartType.ClusteredColumn` říká Aspose.Slides, aby vykreslil seskupený sloupcový graf.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Příprava sešitu s daty grafu

Graf ukládá svá data v interním sešitu. Vymazání poskytne čistý základ pro vlastní data.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Přidání kategorií s úrovněmi seskupení

Seskupování kategorií vytváří efekt seskupeného sloupcového grafu. Každá kategorie může patřit k logické skupině, která se zobrazí v popiscích osy.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Přidání datových řad do grafu

Objekty `Series` představují jednotlivé sloupce v grafu. Přidání více řad vede k sloupcům vedle sebe pro každou kategorii.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Uložení prezentace s grafem

Uložení `Presentation` zapíše standardní soubor PPTX, který lze otevřít v libovolném prohlížeči PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktické aplikace

- **Obchodní zprávy** – porovnat čtvrtletní příjmy napříč regiony.  
- **Akademický výzkum** – zobrazit experimentální výsledky seskupené podle podmínek testu.  
- **Projektové řízení** – vizualizovat míru dokončení úkolů pro více týmů na jednom snímku.

## Úvahy o výkonu

- **Správa paměti** – uvolněte velké sešity po použití.  
- **Dávkové operace** – vyhněte se aktualizaci grafu uvnitř úzkých smyček; nejprve shromážděte data a pak je aplikujte.  
- **Vestavěné optimalizace** – Aspose.Slides poskytuje metody jako `Presentation.optimize()` pro velké soubory, snižující paměťovou náročnost až o **30 %**.

## Časté úskalí a tipy

- **Úskalí:** Zapomenutí vymazat existující řady/kategorie může vést k duplicitním datům.  
  **Tip:** Vždy zavolejte `clear()` před naplněním nových dat.  
- **Úskalí:** Použití špatné adresy buňky (např. `"c2"` místo `"C2"`).  
  **Tip:** Odkazy na buňky nejsou citlivé na velikost písmen, ale udržujte je konzistentní pro čitelnost.  
- **Tip:** Použijte `setGroupingItem` k vytvoření smysluplných štítků skupin; automaticky se zobrazí v legendě grafu.

## Často kladené otázky

**Q1: Jak mohu přidat více řad do mého grafu?**  
A1: Opakovaně zavolejte `ch.getChartData().getSeries().add()`, přičemž zadáte jedinečný název a datové body pro každou řadu.

**Q2: Jaké jsou běžné problémy s grafy Aspose.Slides?**  
A2: Problémy často vznikají z nesouladu datových rozsahů nebo chybějících buněk v sešitu. Ověřte, že každá kategorie a datový bod má odpovídající buňku.

**Q3: Mohu použít Aspose.Slides s jinými programovacími jazyky?**  
A3: Ano, Aspose poskytuje ekvivalentní knihovny pro .NET, C++, Python a další.

**Q4: Jak aktualizovat existující graf v prezentaci?**  
A4: Načtěte prezentaci, najděte graf pomocí `slide.getShapes().get_Item(index)`, a poté upravte jeho řady nebo formátování podle potřeby.

**Q5: Existují omezení typů grafů v Aspose.Slides?**  
A5: Knihovna podporuje více než **50 typů grafů** a neustále přidává nové; vždy si zkontrolujte nejnovější dokumentaci pro aktuální seznam.

## Zdroje

- **Dokumentace:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Stáhnout:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Koupit:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Bezplatná zkušební verze:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Dočasná licence:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Fórum podpory:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Poslední aktualizace:** 2026-09-17  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Související tutoriály

- [Vytvoření průvodce tvorbou grafu v Javě s Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Přidání animace do grafu PowerPoint pomocí Aspose.Slides pro Java – Průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}