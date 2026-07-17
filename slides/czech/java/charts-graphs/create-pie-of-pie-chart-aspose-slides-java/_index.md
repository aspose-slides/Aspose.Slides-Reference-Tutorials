---
date: '2026-07-17'
description: Naučte se, jak přidat graf do PowerPointu vytvořením Pie of Pie chart
  pomocí Aspose.Slides for Java. Obsahuje nastavení, kód, přizpůsobení a uložení jako
  PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Přidejte graf do PowerPointu pomocí Aspose.Slides for Java. Tento
  návod ukazuje, jak vytvořit, přizpůsobit a během několika minut uložit Pie of Pie
  chart jako PPTX.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Přidat graf do PowerPointu – Vytvořit Pie of Pie Chart v Javě
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Přidat graf do PowerPointu – Vytvořit Pie of Pie Chart v Javě s Aspose.Slides
url: /cs/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Přidání grafu do PowerPointu – Vytvoření grafu Pie of Pie v Javě s Aspose.Slides

## Grafy a diagramy

### Úvod

V moderních datově řízených prezentacích je **přidání grafu do PowerPointu** často nejrychlejší způsob, jak převést surová čísla na vizuální přehled. Běžný koláčový graf funguje dobře pro několik kategorií, ale když jsou některé výseče velmi malé, stávají se nečitelnými. Graf *Pie of Pie* tento problém řeší tím, že malé výseče vyčlení do sekundárního koláče, čímž hlavní graf zůstane přehledný a detaily jsou přístupné.

V tomto tutoriálu se naučíte, jak **přidat graf do PowerPointu** vytvořením grafu Pie of Pie pomocí Aspose.Slides pro Javu. Provedeme vás nastavením prostředí, vytvořením grafu, přizpůsobením popisků, laděním pozice rozdělení a nakonec uložením prezentace jako souboru PPTX. Na konci budete připraveni vložit sofistikované grafy do jakékoli sady snímků.

## Rychlé odpovědi
V Aspose.Slides `Presentation` představuje soubor PPTX, `ChartType.PieOfPie` vybírá graf Pie of Pie, `setShowValue(true)` zobrazuje hodnoty na popiscích a `save` zapisuje soubor.

- **Jaká je hlavní třída pro manipulaci s PowerPointem?** `Presentation` – představuje celý soubor PPTX v paměti.  
- **Který typ grafu vytváří sekundární koláč pro malé výseče?** `ChartType.PieOfPie`.  
- **Jak zobrazíte hodnoty na každé výseči?** Nastavte `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Můžete soubor uložit přímo jako PPTX?** Ano – zavolejte `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Potřebujete licenci pro vývoj?** Bezplatná 30‑denní zkušební verze funguje pro testování; trvalá licence odstraňuje vodotisk hodnocení.

## Co je graf Pie of Pie?
**Graf Pie of Pie** je dvouúrovňová koláčová vizualizace, která odděluje jednu nebo více malých výsečí do samostatného, propojeného koláče, což usnadňuje jejich čtení. Aspose.Slides tento typ grafu podporuje přímo, což vám umožňuje řídit velikost rozdělení, pozici a formátování popisků.

## Proč přidávat graf do PowerPointu s Aspose.Slides?
Aspose.Slides dokáže generovat, upravovat a vykreslovat soubory PowerPointu bez nainstalovaného Microsoft Office. Podporuje **více než 50 vstupních a výstupních formátů**, zpracovává prezentace s **až 500 snímky** za méně než sekundu na typickém serverovém hardwaru a poskytuje **úplnou kontrolu API** nad stylem grafu, popisky dat a rozvržením – ideální pro automatizované reportingové pipeline.

## Požadavky

- **Java Development Kit (JDK) 16+** nainstalován.  
- IDE, jako je **IntelliJ IDEA**, **Eclipse** nebo **NetBeans**.  
- Maven nebo Gradle pro správu závislostí (viz sekce níže).  
- Základní znalost Javy a zkušenost s tvorbou projektů.

## Nastavení Aspose.Slides pro Javu

### Informace o instalaci

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Přímé stažení:** Nejnovější verzi můžete stáhnout z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroky získání licence

- **Free Trial:** Začněte 30‑denní zkušební verzí a prozkoumejte všechny funkce.  
- **Temporary License:** Požádejte o dočasný klíč pro prodloužené hodnocení.  
- **Purchase:** Získejte trvalou licenci pro produkční použití a odstraňte vodotisky hodnocení.

### Základní inicializace a nastavení

`Presentation` je hlavní objekt pro vytváření souborů PowerPoint a `Chart` představuje tvar grafu na snímku.

```java
Presentation presentation = new Presentation();
```  

Tím se vytvoří prázdná prezentace připravená pro snímky a grafy.

## Průvodce implementací

### Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Javu?

Načtěte novou `Presentation`, přidejte snímek a vložte `Chart` typu `PieOfPie`. Řetězec volání API je stručný: vytvořte graf, naplňte data řady, upravte viditelnost popisků, nakonfigurujte velikost sekundárního koláče a nakonec uložte. Celý proces se obvykle vejde do méně než 20 řádků kódu, což je ideální pro automatizovanou generaci reportů.

### Vytvoření grafu 'Pie of Pie'

#### Přehled
Vytvoříme graf Pie of Pie na prvním snímku, oddělíme nejmenší výseče a označíme každý segment jeho hodnotou.

#### Krok 1: Vytvořit instanci třídy Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Tím se inicializuje kontejner pro všechny následné snímky a grafy.

#### Krok 2: Přidat graf 'Pie of Pie' na první snímek
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Zde specifikujeme `ChartType.PieOfPie` a definujeme pozici grafu (X, Y) a velikost (šířka, výška) na plátně snímku.

#### Krok 3: Nastavit datové popisky tak, aby zobrazovaly hodnoty pro řadu
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Povolení `showValue` způsobí, že každá výseč zobrazí svou číselnou hodnotu, což je nezbytné pro rychlou interpretaci dat.

#### Krok 4: Nakonfigurovat velikost druhého koláče a rozdělení podle procent
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Tyto možnosti vám umožňují rozhodnout, kolik grafu bude přiděleno sekundárnímu koláči a které výseče budou přesunuty na základě prahové hodnoty v procentech.

#### Krok 5: Uložit prezentaci na disk ve formátu PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Použijte absolutní cestu nebo Java `Paths.get()` k vyhnutí se specifickým oddělovačům platformy.

## Časté problémy a řešení

`License` třída načítá licenční soubor k odstranění omezení hodnocení.

- **Missing license warning:** Pokud vidíte na grafu „Evaluation Only“, ujistěte se, že jste použili platný licenční soubor pomocí `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Incorrect slice split:** Ověřte, že vlastnost `splitBy` je nastavena na `SplitBy.Percentage` a že `secondPieSize` má hodnotu mezi 0 a 100.  
- **Data not displaying:** Potvrďte, že řada grafu obsahuje alespoň jeden datový bod; jinak se graf zobrazí prázdný.

## Často kladené otázky

`IChart` představuje objekt grafu, který lze přidat na snímek.

**Q: Mohu v jedné prezentaci generovat více grafů?**  
A: Ano, vytvořte novou instanci `IChart` pro každý snímek nebo umístění; API umožňuje neomezený počet grafových objektů v souboru.

`SaveFormat.Pdf` určuje výstupní formát PDF pro ukládání.

**Q: Podporuje Aspose.Slides také ukládání jako PDF?**  
A: Rozhodně – zavolejte `presentation.save("output.pdf", SaveFormat.Pdf)` pro export stejné sady snímků do PDF.

`IPortion` představuje jednotlivou výseč koláčového grafu.

**Q: Jaký je maximální počet datových bodů, které graf Pie of Pie může zpracovat?**  
A: Knihovna podporuje až **10 000** datových bodů na řadu, omezené pouze dostupnou pamětí.

**Q: Je možné přizpůsobit barvy jednotlivých výsečí?**  
A: Ano, přistupujte k jednotlivým `IPortion` pomocí `chart.getChartData().getSeries().get_Item(0).getPortions()` a nastavte `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Jak vložit vygenerovaný PPTX do webové aplikace?**  
A: Po uložení souboru jej streamujte přímo klientovi pomocí `HttpServletResponse` s `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Závěr

Máte nyní kompletní, připravený recept pro **přidání grafu do PowerPointu** vytvořením grafu Pie of Pie pomocí Aspose.Slides pro Javu. Experimentujte s různými prahy rozdělení, formáty popisků a barevnými schématy, aby odpovídaly vašim firemním směrnicím. Dále prozkoumejte další typy grafů – například vrstvené sloupcové nebo radarové – a ještě více obohaťte své automatizované sady snímků.

---

**Poslední aktualizace:** 2026-07-17  
**Testováno s:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit dynamický graf v Javě – PowerPoint tutoriály grafů pro Aspose.Slides](/slides/java/charts-graphs/)
- [Jak přidat koláčový graf do PowerPointu s Aspose.Slides pro Javu](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Javu: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}