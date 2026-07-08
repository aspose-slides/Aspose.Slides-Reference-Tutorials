---
date: '2026-07-08'
description: Naučte se, jak přidat koláčové grafy do prezentací PowerPoint pomocí
  Aspose.Slides for Java. Postupujte podle tohoto krok‑za‑krokem průvodce a vytvořte
  a přizpůsobte profesionální koláčové grafy.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Přidejte koláčový graf do PowerPointu pomocí Aspose.Slides for Java.
  Tento tutoriál ukazuje, jak programově generovat a přizpůsobovat koláčové grafy,
  ideální pro automatizované zprávy.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Přidání koláčového grafu do PowerPointu s Aspose.Slides for Java – Rychlý
  průvodce
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Jak přidat koláčový graf do PowerPointu pomocí Aspose.Slides for Java
url: /cs/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Přidání koláčového grafu PowerPoint pomocí Aspose.Slides pro Java

## Úvod

Pokud potřebujete **přidat koláčový graf PowerPoint** snímky, aniž byste ručně otevírali PowerPoint, jste na správném místě. V tomto průvodci vás provedeme nastavením Aspose.Slides pro Java, vytvořením koláčového grafu a přizpůsobením jednotlivých výsečů – ideální pro automatizované reportování, dashboardy nebo personalizované prezentace. Na konci budete mít znovupoužitelný Java úryvek, který během několika sekund vygeneruje vylepšený soubor PowerPoint s koláčovým grafem.

### Rychlé odpovědi
- **Která knihovna vytváří graf?** Aspose.Slides for Java (latest release).  
- **Mohu jej spouštět bez grafického rozhraní?** Yes—no Office installation required.  
- **Která verze Javy je optimální?** JDK 16+ for best performance and GC improvements.  
- **Jak rozšířím výseč?** Call `setExplosion` on the `IDataPoint` and set a pixel offset.  
- **Potřebuji licenci pro produkci?** A trial works for development; a permanent license removes all evaluation limits.

## Proč přidávat koláčový graf PowerPoint pomocí Aspose.Slides pro Java?

Můžete generovat aktuální vizuální reporty přímo ze svých backendových služeb, čímž eliminujete chyby při ručním kopírování a vkládání a zaručíte stylování v souladu se značkou. Aspose.Slides podporuje **70+ typů grafů** a dokáže zpracovat prezentace s **10 000+ snímky** bez načítání celého souboru do paměti, což je ideální pro automatizaci ve velkém měřítku.

## Požadavky

- **Aspose.Slides pro Java** – tutoriál odkazuje na verzi 25.4 (nejnovější v době psaní).  
- **Java Development Kit** – doporučuje se JDK 16 nebo novější.  
- **Maven** nebo **Gradle** pro správu závislostí.  

## Nastavení Aspose.Slides pro Java

### Maven
Přidejte tuto závislost do souboru `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Zahrňte následující do souboru `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně si stáhněte nejnovější verzi přímo z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licencování
Pro použití Aspose.Slides bez omezení:

- Začněte s **bezplatnou zkušební verzí** pro vyhodnocení API.  
- Požádejte o **dočasnou licenci** pro rozšířené testování na stránce [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Zakupte plnou předplatnou prostřednictvím [Purchase page](https://purchase.aspose.com/buy).

## Jak přidat koláčový graf PowerPoint pomocí Aspose.Slides pro Java

Načtěte novou prezentaci, vložte koláčový graf a uložte soubor – vše ve třech stručných krocích. Tento vzor funguje pro libovolnou velikost datové sady a lze jej zabalit do smyčky pro automatické generování desítek snímků. Přístup je nenáročný, vyžaduje jen několik řádků kódu a žádné externí zdroje, což jej činí vhodným jak pro malé utility, tak pro velké dávkové úlohy.

### Krok 1: Inicializace prezentace
Třída `Presentation` představuje jeden soubor PowerPoint v paměti. Vytvořením instance získáte čerstvou, prázdnou sadu snímků, se kterou můžete pracovat.
```java
Presentation pres = new Presentation();
```

### Krok 2: Přidání koláčového grafu
Vložte koláčový graf na první snímek. Souřadnice (50, 50) a velikost (600 × 400) odpovídají standardnímu rozložení 16:9 a ponechávají místo pro nadpisy.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Krok 3: Uložení prezentace
Zapište prezentaci na disk. Nahraďte `YOUR_OUTPUT_DIRECTORY` složkou, kam chcete soubor uložit.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Krok 4: Vyčištění prostředků
Uvolněte objekt `Presentation`, aby se uvolnily nativní prostředky a předešlo se únikům paměti.
```java
if (pres != null) pres.dispose();
```

## Jak přizpůsobit rozšíření datového bodu a barvu?

Načtěte graf, najděte cílový datový bod a poté aplikujte offset rozšíření a plnou barvu výplně. To způsobí, že výseč bude vizuálně vystoupávat pro zdůraznění. Tyto úpravy pomáhají upoutat pozornost publika na kritické hodnoty a zlepšují celkovou čitelnost grafu.

### Krok 1: Načtení existující prezentace (nebo opětovné použití té, kterou jste právě vytvořili)
Objekt `Presentation` načte existující soubor PowerPoint do paměti, což vám umožní upravit jeho obsah.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Krok 2: Přístup k grafu a cílovému datovému bodu
Rozhraní `IDataPoint` představuje jednotlivý datový bod (výseč) v sérii grafu.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Krok 3: Aplikace rozšíření a barvy
`setExplosion(int)` nastaví vzdálenost v pixelech, o kterou je výseč posunuta od středu grafu. Vizuelně oddělte výseč pomocí `setExplosion(20)` a změňte její výplň na modrou pomocí `setFillType(FillType.Solid)` a `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Krok 4: Uložení a uvolnění
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktické aplikace
- **Prodejní zprávy:** Zvýrazněte nejprodávanější produkty pomocí rozšířených výsečů.  
- **Analýza rozpočtu:** Přiřaďte oddělením odlišné barvy pro rychlé vizuální srovnání.  
- **Vzdělávací snímky:** Rozdělte složité koncepty na stravitelné segmenty grafu.  

## Úvahy o výkonu
- **Uvolňujte objekty** okamžitě, aby nedocházelo k únikům paměti, zejména při generování mnoha snímků ve smyčce.  
- **Sledujte využití haldy** u velkých prezentací; použijte přetížení `Save`, které přijímá `OutputStream`, pro streamování dat a udržení nízké paměťové stopy.  
- Používejte **JDK 16+** k využití nejnovějších vylepšení garbage‑collection, což může snížit dobu zpracování až o 30 % pro sady 1 000 snímků.

## Závěr
Nyní máte kompletní workflow připravené pro produkci k **přidání koláčového grafu PowerPoint** pomocí Aspose.Slides pro Java. Experimentujte s různými vzdálenostmi rozšíření, barvami a datovými sadami, aby odpovídaly vaší značce. Až budete připraveni, prozkoumejte další typy grafů – sloupcové, čárové nebo rozptylové – a vytvořte kompletní analytický dashboard přímo v PowerPointu.

## Často kladené otázky

**Q: Jaká je největší výhoda používání Aspose.Slides pro Java?**  
A: Umožňuje programově vytvářet, upravovat a renderovat soubory PowerPoint bez nutnosti instalace Microsoft Office, podporuje více než 70 typů grafů a více než 100 + formátů souborů.

**Q: Mohu vygenerovat soubor PowerPoint od nuly?**  
A: Ano, vytvořte objekt `Presentation`, přidejte snímky, grafy nebo tvary a poté zavolejte `save` – vše v čistém Java kódu.

**Q: Jak rozšířím konkrétní koláčovou výseč?**  
A: Získejte `IDataPoint` pro danou výseč a zavolejte `setExplosion(pixelOffset)`. Offset určuje, jak daleko se výseč posune ven.

**Q: Existuje limit na počet snímků, které mohu vytvořit?**  
A: Aspose.Slides zvládne prezentace s až **10 000 snímky** v jednom souboru, pokud výstup streamujete a ne načítáte vše najednou do paměti.

**Q: Kde najdu pokročilejší příklady přizpůsobení grafů?**  
A: Podívejte se na oficiální [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) pro podrobné reference API a ukázkové projekty.

## Zdroje
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animace grafů v PowerPointu pomocí Aspose.Slides pro Java – Průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Vytvoření a ověření rozvržení grafů v PowerPointu pomocí Aspose.Slides pro Java | SEO‑optimalizovaný průvodce](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}