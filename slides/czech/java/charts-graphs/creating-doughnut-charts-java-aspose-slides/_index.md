---
date: '2026-07-27'
description: Naučte se, jak vytvořit doughnut chart v java pomocí Aspose.Slides –
  rychlý průvodce nastavením library, přidáním přizpůsobitelného doughnut chart, úpravou
  hole size a uložením presentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Naučte se, jak vytvořit doughnut chart v java pomocí Aspose.Slides
  – rychlý průvodce nastavením library, přidáním přizpůsobitelného doughnut chart,
  úpravou hole size a uložením presentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Vytvořte Doughnut Chart v Java – krok za krokem s Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Vytvořte Doughnut Chart v Java – krok za krokem s Aspose.Slides
url: /cs/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit prstencové grafy v Javě pomocí Aspose.Slides pro prezentace

## Úvod
Creating visually appealing presentations is essential for effectively conveying information. **Create doughnut chart java** is a common requirement when you need to illustrate proportional data with a modern look. In this tutorial you’ll learn how to set up Aspose.Slides for Java, build a doughnut chart, customize its hole size and colors, and finally save the presentation file. By the end you’ll have a reusable pattern you can drop into any Java project that generates PowerPoint decks automatically.

**Co se naučíte:**
- Nastavení Aspose.Slides pro Java
- Vytváření a konfigurace prstencových grafů v prezentacích
- Úprava vzhledu grafu, například velikosti díry
- Uložení prezentace s novým grafem

Let's begin by setting up our environment!

## Rychlé odpovědi
- **Která knihovna vytváří prstencový graf v Javě?** Aspose.Slides for Java.
- **Kolik řádků kódu je potřeba pro základní prstencový graf?** Přibližně 8–10 řádků po vytvoření instance prezentace.
- **Mohu změnit velikost díry?** Ano, metoda `setHoleSize(double)` přijímá hodnoty od 0 % do 100 %.
- **Jaké výstupní formáty jsou podporovány?** PPTX, PDF, XPS, PNG, JPEG a několik dalších (více než 50 celkem).
- **Potřebuji licenci pro produkci?** Pro neomezené používání je vyžadována komerční licence; pro hodnocení stačí bezplatná zkušební verze.

## Co je Aspose.Slides pro Java?
**Aspose.Slides for Java** is a fully managed API that enables developers to create, modify, convert, and render PowerPoint files without Microsoft Office. It supports more than 50 file formats and can handle presentations with thousands of slides while keeping memory usage low.

## Proč používat prstencové grafy v prezentacích?
Doughnut charts display part‑to‑whole relationships while freeing space in the centre for labels or images. Aspose.Slides can render doughnut charts up to **500 slides per minute** on a typical 2.5 GHz server, and it processes **multi‑hundred‑page presentations** without loading the entire file into memory, making it ideal for large‑scale reporting solutions.

## Požadavky
Before starting, ensure you have covered these prerequisites:

### Požadované knihovny a verze
To work with Aspose.Slides for Java, include it in your project via Maven or Gradle, or download directly.

#### Požadavky na nastavení prostředí
- A working Java Development Kit (JDK), preferably version 8 or higher.
- An Integrated Development Environment (IDE) like IntelliJ IDEA or Eclipse.

### Požadavky na znalosti
Familiarity with Java and basic programming concepts is beneficial. Basic knowledge of Maven or Gradle will help streamline the setup process.

## Nastavení Aspose.Slides pro Java
Incorporating Aspose.Slides into your project can be done in several ways:

**Maven:**  
Add this dependency to your `pom.xml` file:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Include this in your `build.gradle` file:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Přímé stažení:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
- **Bezplatná zkušební verze:** Start by downloading a trial version to explore Aspose.Slides features.  
- **Dočasná licence:** Obtain a temporary license for extended functionality without limitations.  
- **Nákup:** For ongoing use, purchasing a license is required.

Once you have the library set up and your environment ready, let's move on to implementing our doughnut chart.

## Jak vytvořit prstencový graf v Javě?
Load a new `Presentation` object, add a doughnut chart to a slide, set the hole size, and save the file – all in a handful of straightforward API calls. This approach gives you full control over chart data, appearance, and export format, and it works without needing Microsoft PowerPoint installed on the server.

### Inicializace objektu Presentation
The `Presentation` class is Aspose.Slides' top‑level object that represents a PowerPoint file in memory.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
This step creates an empty presentation where you can add slides, shapes, and charts.

### Přidání prstencového grafu na snímek
`ISlide` is the interface for a single slide; you can retrieve the first slide or add a new one.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
The method `addChart` creates a doughnut chart; the parameters define its position (X, Y) and size (width, height) on the slide.

### Nastavení velikosti díry prstencového grafu
`Chart` exposes `setHoleSize(double)` to control the inner radius as a percentage of the chart radius.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Setting the hole size to 90 % makes the chart appear almost as a full circle, which is useful when you want to emphasize the outer segments.

### Uložení prezentace
`presentation.save(String, SaveFormat)` writes the file to disk in the chosen format.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
The example saves the result as `DoughnutHoleSize_out.pptx`, but you could also choose PDF, PNG, or any of the 50+ supported formats.

### Vyčištění prostředků
Calling `presentation.dispose()` releases native resources and prevents memory leaks, especially important in long‑running server applications.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Praktické aplikace
1. **Rozdělení rozpočtu:** Display how a budget is distributed across departments.  
2. **Výsledky průzkumu:** Visualize responses to questions with multiple‑choice answers.  
3. **Zdroje návštěvnosti webu:** Show the percentage of traffic coming from different channels (organic, paid, referral, etc.).

## Úvahy o výkonu
When working with Aspose.Slides, consider these tips for optimal performance:
- Dispose of `Presentation` objects as soon as you’re done to free native memory.  
- Use streams (`FileInputStream`, `ByteArrayOutputStream`) for large data sets to avoid loading entire files into RAM.  
- Reuse chart objects when generating many slides in a loop to reduce object‑creation overhead.

## Časté problémy a řešení
- **Chyba při ukládání:** Verify the output directory exists and the application has write permissions.  
- **Chybějící data grafu:** Ensure you populate the chart’s `ChartData` collection before calling `setHoleSize`.  
- **Nárazová spotřeba paměti:** For presentations with thousands of slides, enable `Presentation.setSlideSize` to a smaller size and dispose of intermediate slides promptly.

## Často kladené otázky

**Q: Mohu upravit barvy segmentů mého prstencového grafu?**  
A: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` and then specify the desired RGB color.

**Q: Jak přidám datové popisky do mého grafu?**  
A: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` to display the value inside each segment.

**Q: Je možné uložit grafy v jiných formátech než PPTX?**  
A: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many other formats—over 50 in total.

**Q: Co mám dělat, pokud narazím na výjimku při načítání velké prezentace?**  
A: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)` to stream the file and reduce memory consumption.

**Q: Mohu automatizovat aktualizace grafů pomocí živých zdrojů dat?**  
A: Yes. Retrieve data from a database or REST API, update the `ChartData` collection, and call `chart.refresh()` before saving the presentation.

## Zdroje
- **Dokumentace:** Explore detailed API references at [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Stažení:** Get the latest library version from [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Nákup:** For full access, purchase a license at [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Bezplatná zkušební verze:** Test drive Aspose.Slides with a free trial available on their download page.  
- **Dočasná licence:** Obtain a temporary license for extended testing without limitations.  
- **Podpora:** Have questions? Visit the [Aspose Forum](https://forum.aspose.com/c/slides/11) for assistance.

---

**Poslední aktualizace:** 2026-07-27  
**Testováno s:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak vytvořit graf v Javě s Aspose.Slides: Komplexní průvodce](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}