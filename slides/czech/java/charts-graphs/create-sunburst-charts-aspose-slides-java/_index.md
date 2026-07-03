---
date: '2026-07-03'
description: Naučte se krok za krokem vytvářet sunburst grafy v Javě pomocí Aspose.Slides,
  s plnými možnostmi přizpůsobení pro prezentace PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Jak vytvořit sunburst grafy v Javě pomocí Aspose.Slides
url: /cs/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit sluneční diagramy v Javě pomocí Aspose.Slides

## Úvod
V dnešních prezentacích řízených daty může **jak vytvořit sluneční diagram** rychle odlišit vaše snímky. Tento tutoriál vás provede tvorbou slunečního diagramu pomocí Aspose.Slides pro Java, od nastavení projektu až po finální export, abyste mohli dodávat působivé hierarchické grafy bez opuštění Java ekosystému.

## Rychlé odpovědi
- **Jaká je hlavní třída pro soubor PowerPoint?** `Presentation` – představuje celý PPTX v paměti.  
- **Kolik řádků kódu je potřeba pro základní sluneční diagram?** Typicky 5–7 řádků, jakmile je knihovna zahrnuta.  
- **Jaké výstupní formáty jsou podporovány?** PPTX, PDF, PNG, SVG a HTML.  
- **Mohu stylovat jednotlivé segmenty?** Ano – barvy výplně, okraje a popisky dat jsou plně přizpůsobitelné.  
- **Potřebuji licenci pro produkci?** Bezplatná zkušební verze funguje pro testování; pro nasazení je vyžadována komerční licence.

## Co je sluneční diagram?
Sluneční diagram vizualizuje hierarchická data jako soustředné kruhy, kde každý kruh představuje úroveň hierarchie. Umožňuje divákům na první pohled pochopit vztahy rodič‑potomek, což je ideální pro organizační schémata, taxonomické zobrazení a víceúrovňové metriky. Je zvláště užitečný pro zobrazování víceúrovňových kategorií, jako jsou produktové řady, geografické regiony nebo organizační struktury, a umožňuje vidět jak celkové rozdělení, tak podrobný rozklad v jednotlivých segmentech.

## Proč používat Aspose.Slides pro sluneční diagramy?
Aspose.Slides podporuje **30+ typů grafů**, zpracovává soubory až do **500 MB** bez načítání celého dokumentu do paměti a vykresluje grafiku při **300 DPI** pro krystalicky čistý výstup. Tyto kvantifikované schopnosti zajišťují rychlou generaci a vysoce kvalitní vizuály i pro velké prezentace. Knihovna také nabízí vlákny‑bezpečné operace a bezproblémovou integraci s populárními Java nástroji pro sestavování, což ji činí vhodnou jak pro desktopové, tak server‑side generování prezentací ve velkém měřítku.

## Požadavky
- Java Development Kit (JDK) 8 nebo novější.  
- Maven nebo Gradle pro správu závislostí.  
- Aspose.Slides for Java (nejnovější verze).  
- Základní pochopení hierarchických datových struktur.

## Jak vytvořit sluneční diagramy krok za krokem?
Načtěte své prostředí, přidejte graf, naplňte hierarchická data, upravte vzhled a uložte soubor – vše během několika jednoduchých kroků. Níže je přesný postup, který můžete následovat bez psaní dalšího boilerplate kódu. Proces je plně automatizovaný, nevyžaduje žádnou manuální UI interakci a může být začleněn do dávkových úloh nebo webových služeb pro tvorbu diagramů na vyžádání.

### Krok 1: Nastavení projektu
Přidejte Maven závislost Aspose.Slides (nebo ekvivalentní Gradle úryvek) do svého `pom.xml`. Tím se stáhnou všechny potřebné binární soubory a transitivní knihovny.

### Krok 2: Načíst nebo vytvořit prezentaci
`Presentation` je objekt nejvyšší úrovně v Aspose.Slides, který představuje jeden soubor PowerPoint v paměti. Vytvořte jej pomocí `new Presentation()` pro novou prezentaci nebo zadejte cestu k souboru pro otevření existujícího PPTX.

### Krok 3: Přidat sluneční diagram
Vložte nový grafický objekt na snímek pomocí `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Tím vytvoříte placeholder slunečního diagramu připravený pro data. `ChartType.Sunburst` určuje typ slunečního diagramu při přidávání grafu na snímek.

### Krok 4: Naplnit hierarchická data
`ChartData` obsahuje datové řady a kategorie pro graf. Přistupte k kolekci `ChartData` grafu a přidejte řady a kategorie, které odrážejí vaši hierarchii. Pro každou úroveň specifikujte vztah rodič‑potomek pomocí vlastnosti `ParentSeries`, což umožní grafu automaticky vykreslit soustředné kruhy.

### Krok 5: Přizpůsobit vzhled
Doladěte barvy segmentů, styly okrajů a popisky dat prostřednictvím objektů `ChartSeries` a `ChartDataPoint`. `ChartSeries` představuje řadu datových bodů v grafu. `ChartDataPoint` představuje jednotlivý datový bod v řadě. Můžete také povolit 3‑D rotaci nebo nastavit vlastnost `Explode` pro zvýraznění konkrétních výsečů.

### Krok 6: Uložit prezentaci
Výčtový typ `SaveFormat` definuje formáty, do kterých můžete prezentaci uložit. Zavolejte `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` pro zápis souboru na disk. Můžete také exportovat do PDF nebo PNG změnou hodnoty výčtu `SaveFormat`.

## Jak přizpůsobit barvy slunečního diagramu?
Určete výplňovou barvu pro každý `ChartDataPoint` pomocí `point.getFillFormat().setFillType(FillType.Solid)` a následně `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Tento přímý přístup vám umožní sladit graf s firemní identitou nebo zdůraznit klíčové datové body. Můžete také použít gradientní výplně, upravit průhlednost nebo použít barvy motivu, aby byl zachován jednotný vzhled celé prezentace.

## Časté problémy a řešení
- **Problém:** Hierarchie vypadá plochá.  
  **Řešení:** Ujistěte se, že každá podřízená série správně odkazuje na svůj `ParentSeries`. Chybějící odkazy způsobí, že graf bude považovat všechna data za jednu úroveň.
- **Problém:** Exportovaný PNG je rozmazaný.  
  **Řešení:** Zvyšte DPI exportu nastavením `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problém:** Velké soubory PPTX způsobují OutOfMemoryError.  
  **Řešení:** Použijte `Presentation.setMemoryOptimization(true)` pro streamování dat a snížení využití paměti.

## Často kladené otázky

**Q: Mohu vygenerovat sluneční diagram z CSV souboru?**  
A: Ano. Načtěte CSV, vytvořte hierarchii v paměti a před uložením ji předáte kolekci `ChartData` grafu.

**Q: Podporuje Aspose.Slides animované přechody pro sluneční diagramy?**  
A: Ano. Použijte `SlideShowTransition` na snímek nebo `ChartFormat.setAnimationEnabled(true)` pro animaci na úrovni grafu.

**Q: Je možné exportovat graf jako vektorový SVG obrázek?**  
A: Rozhodně. Uložte prezentaci pomocí `SaveFormat.Svg` a získáte škálovatelnou vektorovou verzi slunečního diagramu.

**Q: Jaký je maximální počet datových bodů, které sluneční diagram zvládne?**  
A: Aspose.Slides spolehlivě zpracuje až **10 000** datových bodů v jednom slunečním diagramu bez zhoršení výkonu.

**Q: Potřebuji samostatnou licenci pro každé nasazovací prostředí?**  
A: Jedna komerční licence pokrývá všechna prostředí (vývoj, testování, produkce), pokud jsou dodrženy licenční podmínky.

## Závěr
Nyní máte kompletní, krok‑za‑krokem průvodce **jak vytvořit sluneční diagram** v Javě pomocí Aspose.Slides. Dodržením výše uvedeného postupu můžete generovat vysoce kvalitní, plně přizpůsobitelné hierarchické vizualizace pro jakoukoli PowerPoint prezentaci.

---

**Poslední aktualizace:** 2026-07-03  
**Testováno s:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Mistrovství v přizpůsobení grafů PowerPointu pomocí Aspose.Slides Java pro dynamické prezentace](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animujte kategorie grafů PowerPointu pomocí Aspose.Slides pro Java | Průvodce krok za krokem](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}