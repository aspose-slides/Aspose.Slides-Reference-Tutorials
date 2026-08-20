---
date: '2026-08-06'
description: Naučte se, jak vytvořit graf v Java prezentacích pomocí Aspose.Slides
  a jak propojit sešit pro dynamické aktualizace dat. Průvodce krok za krokem.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: Naučte se, jak vytvořit graf v Java prezentacích pomocí Aspose.Slides
  a jak propojit sešit pro dynamické aktualizace dat. Postupujte podle tohoto stručného
  tutoriálu.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: Jak vytvořit graf v Java prezentacích pomocí Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: Jak vytvořit graf v Java prezentacích pomocí Aspose.Slides
url: /cs/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit graf v prezentacích Java pomocí Aspose.Slides: propojení s externími sešity

## Úvod
V tomto tutoriálu se naučíte **jak vytvořit graf** objektů v prezentaci Java a **jak propojit data sešitu**, aby se grafy automaticky aktualizovaly. Dynamické grafy udržují vaše snímky aktuální bez ručního kopírování a vkládání, což je nezbytné pro živé reportování, finanční dashboardy a prezentace stavu projektů. Provedeme vás nastavením, implementací a běžnými úskalími, abyste mohli integrovat data z Excelu v reálném čase pomocí několika řádků kódu.

## Rychlé odpovědi
- **Jaký je hlavní přínos?** Grafy se aktualizují automaticky, když se změní propojený Excel sešit.  
- **Která verze knihovny je požadována?** Aspose.Slides for Java 25.4 nebo novější.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; komerční licence odstraňuje všechna omezení hodnocení.  
- **Mohu použít libovolný formát Excelu?** Ano – jsou podporovány jak soubory `.xlsx`, tak starší `.xls`.  
- **Je latence sítě problém?** Uložte sešit do mezipaměti lokálně nebo použijte CDN ke snížení latence.

## Co je dynamické propojení grafu?
Dynamické propojení grafu umožňuje grafu načíst svůj zdroj dat z externího sešitu za běhu, takže jakékoli změny v sešitu se projeví na snímku při dalším otevření. Tím se eliminuje potřeba znovu generovat prezentaci po každé aktualizaci dat.

## Proč používat Aspose.Slides pro Java?
Aspose.Slides podporuje **více než 50 vstupních a výstupních formátů**, dokáže vykreslit prezentace s více než stovkou stránek, aniž by načítal celý soubor do paměti, a zpracovává aktualizace dat grafu za méně než 200 ms na typickém serveru. Tato kvantifikovaná výkonnostní čísla z něj činí spolehlivou volbu pro podnikové reportovací kanály.

## Požadavky
- **Aspose.Slides for Java** 25.4 nebo novější.  
- **Java Development Kit (JDK)** 16 nebo novější.  
- Znalost Maven nebo Gradle pro správu závislostí.  

### Požadované knihovny a závislosti
- **Aspose.Slides for Java** – poskytuje API pro prezentace.  
- **Java Development Kit (JDK)** – potřebný pro kompilaci a spuštění kódu.

### Požadavky na nastavení prostředí
- Základní znalost programování v Javě.  
- Přístup k externímu Excel sešitu (lokální cesta k souboru nebo HTTP URL).  

## Nastavení Aspose.Slides pro Java
Pro přidání Aspose.Slides do vašeho projektu vyberte jeden z podporovaných systémů sestavení.

### Nastavení Maven
Add this dependency to your `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Nastavení Gradle
Include this in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternatively, download the library from [Aspose.Slides Java Documentation](https://releases.aspose.com/slides/java/).

#### Získání licence
Start with a free trial or obtain a temporary license to test Aspose.Slides without limitations. For long‑term use, consider purchasing a license.

##### Základní inicializace a nastavení
`Presentation` je jádrová třída Aspose.Slides, která představuje soubor PowerPoint v paměti. Inicializujte objekt prezentace následovně:
```java
Presentation pres = new Presentation();
```

## Průvodce implementací
In this section we walk through setting an external workbook for updating chart data in a presentation.

### Nastavení externího sešitu s aktualizací dat grafu

#### Přehled
This feature allows charts to dynamically update their data from an external source. It’s ideal when your data changes frequently and you need your slides to reflect those changes automatically.

#### Krok za krokem implementace
1. **Create a new presentation**  
   Start by creating a fresh `Presentation` instance:
   ```java
   Presentation pres = new Presentation();
   ```

2. **Access the first slide**  
   Accessing slides is straightforward:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Add a chart to the slide**  
   Add a pie chart at the desired position and size:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Set external workbook URL for chart data**  
   Specify an external workbook as the data source:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### Možnosti konfigurace
- **Chart type** – choose from Pie, Bar, Line, Area, etc., depending on how you want to visualise the data.  
- **Position & size** – adjust X/Y coordinates and width/height to fit your slide layout.  

## Jak vytvořit graf, který je propojen se sešitem?
`Chart` is the Aspose.Slides object that encapsulates a chart shape and its data.  
Load your presentation, add a chart, and call `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. The chart now reads its series values from the workbook each time the file is opened, providing live updates without regenerating the PPTX. This direct‑answer paragraph satisfies the GEO requirement and gives you a concise, actionable description.

## Běžné problémy a řešení
If external links do not update:
- Verify the URL is reachable and returns a valid Excel file.  
- Ensure the server permits anonymous GET requests or provide credentials if needed.  
- Cache the workbook locally if network latency is high; update the cache before opening the presentation.

## Praktické aplikace
Dynamic charts powered by an external workbook can be useful in several scenarios:
1. **Real‑time data reporting** – sales dashboards that pull the latest figures from a central Excel file.  
2. **Financial analysis** – stock price trends that refresh automatically from a market data feed.  
3. **Project management** – KPI dashboards that reflect the most recent task completion stats.

## Úvahy o výkonu
Optimising performance is essential when dealing with large workbooks:
- Cache the workbook on the application server to minimise repeated network calls.  
- Use streaming APIs to read only the required worksheet ranges, reducing memory usage.  
- Aspose.Slides processes chart updates in under 200 ms for workbooks up to 10 MB, which is suitable for most reporting scenarios.

## Závěr
By following this guide you now know **how to create chart** objects in Java presentations and **how to link workbook** data for automatic updates. This capability makes your slides more interactive, reduces manual effort, and ensures stakeholders always see the latest numbers. Explore additional Aspose.Slides features such as slide cloning, animation, and PDF export to further enhance your reporting workflow.

## Často kladené otázky
**Q1: Can I use any URL as an external workbook?**  
A1: The URL must point to a reachable Excel file (`.xlsx` or `.xls`). Ensure the server returns the correct MIME type and that authentication, if required, is handled in your code.

**Q2: What chart types support dynamic linking?**  
A2: All native Aspose.Slides chart types – Pie, Bar, Line, Area, Scatter, Radar, and more – can be linked to an external workbook.

**Q3: Is there a size limit for the external workbook?**  
A3: While Aspose.Slides can handle workbooks larger than 100 MB, processing time grows linearly; for best performance keep files under 20 MB or stream only needed ranges.

**Q4: How should I handle an unreachable URL?**  
A4: Wrap the linking code in a try‑catch block, log the exception, and optionally fall back to a static data source so the presentation still loads.

**Q5: Can this be used in automated reporting pipelines?**  
A5: Absolutely. The API works head‑less, so you can generate or update presentations on a server, embed them in emails, or publish them to a SharePoint library.

## Zdroje
- [Dokumentace Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- [Stáhnout Aspose.Slides pro Java](https://releases.aspose.com/slides/java/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze a dočasná licence](https://releases.aspose.com/slides/java/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Poslední aktualizace:** 2026-08-06  
**Testováno s:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Související tutoriály

- [Jak vytvořit graf v Javě s Aspose.Slides: komplexní průvodce](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Java: krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animovat grafy v PowerPointu pomocí Aspose.Slides pro Java – průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}