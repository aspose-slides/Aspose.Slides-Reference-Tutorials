---
date: '2026-07-17'
description: Naučte se, jak přidat Sunburst charts v PowerPointu pomocí Aspose Slides
  for Java. Praktický návod krok za krokem pokrývá nastavení, vytvoření grafu, přizpůsobení
  a reálné příklady použití.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Jak přidat Sunburst charts v PowerPointu pomocí Aspose Slides for
  Java. Postupujte podle tohoto tutoriálu k nastavení library, vytvoření grafu, přizpůsobení
  data points a jejich použití v reálných projektech.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Jak přidat Sunburst charts v PowerPointu s Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Jak přidat Sunburst charts v PowerPointu s Aspose (Java)
url: /cs/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak přidat Sunburst chart do PowerPointu pomocí Aspose (Java)

## Úvod

Přidání Sunburst chartu do prezentace PowerPoint může okamžitě proměnit plochou datovou tabulku v poutavou vizuální hierarchii. V tomto tutoriálu se naučíte **jak přidat Sunburst chart** do PowerPointu pomocí Aspose.Slides pro Java, od nastavení prostředí až po doladění barev a popisků. Ať už vytváříte prodejní dashboard, rozpis úkolů projektu nebo vzdělávací sadu snímků, níže uvedené kroky vám poskytnou řešení připravené do produkce.

**Co se naučíte**
- Jak nakonfigurovat Aspose.Slides v projektu Maven nebo Gradle  
- Jak vytvořit novou prezentaci a vložit Sunburst chart  
- Jak přizpůsobit datové body, popisky a výplňové barvy  
- Reálné scénáře, kde Sunburst chart vyniká  

Pojďme začít a ukázat, jak snadno lze surová hierarchická data proměnit v elegantní vizuál v PowerPointu.

## Rychlé odpovědi
- **Primární knihovna?** Aspose.Slides pro Java  
- **Podporovaný typ grafu?** Sunburst (radiální hierarchický)  
- **Minimální verze Javy?** JDK 16  
- **Typický čas implementace?** 10‑15 minut pro základní graf  
- **Licence potřebná pro produkci?** Ano, platná licence Aspose  

## Co je Sunburst chart?
Sunburst chart je radiální diagram, který vizualizuje hierarchická data vnořením kruhových prstenců od centrálního bodu ven. Je ideální pro zobrazení víceúrovňových vztahů, jako jsou organizační struktury, produktové kategorie nebo strom souborového systému. Každý soustředný prstenec představuje úroveň hierarchie a velikost každého segmentu odráží jeho kvantitativní hodnotu, což divákům umožňuje rychle pochopit jak strukturu, tak rozsah.

## Proč použít Aspose.Slides pro Java?
Aspose.Slides podporuje **více než 50 typů grafů** a může manipulovat s prezentacemi až s **10 000 snímky** bez načítání celého souboru do paměti, což poskytuje vysoký výkon pro podnikovou reporting. Funguje napříč platformami, nabízí rozsáhlé API a obsahuje robustní licenční možnosti, které odstraňují omezení evaluace, což z něj činí ideální volbu pro produkční prostředí.

## Předpoklady
- **Java Development Kit (JDK)** 16 nebo novější  
- **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli editor kompatibilní s Javou  
- Základní znalost syntaxe Javy a nástrojů Maven/Gradle  

## Nastavení Aspose.Slides pro Java

### Maven závislost
Přidejte artefakt Aspose.Slides do svého `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle závislost
Pokud dáváte přednost Gradlu, zahrňte následující řádek do `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Nejnovější JAR můžete také stáhnout přímo ze stránky oficiálních vydání: [vydání Aspose.Slides pro Java](https://releases.aspose.com/slides/java/).

### Získání licence
Pro provoz bez omezení evaluace si pořiďte licenci:
- **Bezplatná zkušební verze** – dočasná licence pro rychlé vyzkoušení.  
- **Dočasná licence** – požádejte o ni na [webu Aspose](https://purchase.aspose.com/temporary-license).  
- **Plná licence** – zakupte předplatné pro neomezené používání v produkci.

### Základní inicializace
Třída `Presentation` je vstupním bodem pro vytváření nebo otevírání souborů PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Průvodce implementací

### Jak přidat Sunburst chart do prezentace PowerPoint pomocí Aspose.Slides pro Java?

Načtěte novou `Presentation`, přidejte snímek, vložte `IChart` typu `ChartType.Sunburst` a zavolejte `save`. Tento stručný tříkrokový vzor vytvoří plně funkční Sunburst chart připravený k dalším úpravám.

#### Krok 1: Inicializace prezentace
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Krok 2: Přidání Sunburst chartu
Rozhraní `IChart` definuje objekt grafu, který lze umístit na libovolný snímek. Zde přidáváme Sunburst chart na souřadnice (100, 100) s velikostí 450 × 400 bodů.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Krok 3: Uložení prezentace
Vždy uložte změny voláním `save`. Můžete zvolit PPTX, PDF nebo kterýkoli z více než 50 podporovaných výstupních formátů.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Úprava datových bodů v grafu

#### Přehled
Můžete přizpůsobit každý výsek Sunburst chartu – popisky, barvy i viditelnost – prostřednictvím kolekce datových bodů grafu.

#### Krok 1: Přístup ke kolekci datových bodů
První řada grafu obsahuje kolekci objektů `IChartDataPoint`, které představují jednotlivé výseky.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Krok 2: Zobrazení hodnoty pro konkrétní datový bod
Nastavte `IsValueShown` na `true` u požadovaného datového bodu, aby se jeho číselná hodnota zobrazila přímo na výseku.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Krok 3: Úprava formátů popisků
Upravte viditelnost popisků, barvu písma a pozadí pro lepší čitelnost.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Krok 4: Nastavení výplňové barvy pro datové body
Přizpůsobte výplňovou barvu jednotlivých výseků tak, aby odpovídala vaší firemní paletě nebo zvýraznila klíčové segmenty.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Krok 5: Uložení upravené prezentace
Uložte přizpůsobený graf opětovným uložením prezentace.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktické aplikace

1. **Obchodní analytika** – Vizualizujte prodeje podle regionu → produktové řady → SKU v jedné radiální podobě.  
2. **Projektové řízení** – Zobrazte strukturu rozdělení práce, od fází po úkoly a podúkoly.  
3. **Vzdělávání** – Mapujte hierarchii učebních plánů, např. fakulty → kurzy → moduly.  

## Úvahy o výkonu

- **Efektivita paměti:** Aspose.Slides streamuje data, takže i 500‑stránková prezentace s více grafy zůstane pod 200 MB RAM.  
- **Garbage Collection:** Uvolňujte objekty snímků (`slide.dispose()`), když již nejsou potřeba, aby nedocházelo k únikům paměti.  

## Často kladené otázky

**Q: Co je Sunburst chart?**  
A: Sunburst chart vizualizuje hierarchická data v soustředných prstencích, přičemž každý prstenec představuje úroveň hierarchie.

**Q: Jak nainstaluji Aspose.Slides pro Java pomocí Maven?**  
A: Přidejte Maven závislost uvedenou v sekci „Maven závislost“ do svého `pom.xml` a spusťte `mvn clean install`.

**Q: Mohu přizpůsobit i jiné typy grafů pomocí Aspose.Slides?**  
A: Ano, knihovna podporuje více než 50 typů grafů, včetně sloupcových, čárových, koláčových a radarových grafů.

**Q: Moje prezentace se neukládá – co mám zkontrolovat?**  
A: Ověřte, že cesta k souboru je správná, adresář existuje a máte oprávnění k zápisu. Také se ujistěte, že je volána metoda `Presentation.save()`.

**Q: Kde mohu získat další pomoc nebo příklady?**  
A: Navštivte [Aspose fórum](https://forum.aspose.com/c/slides/11) nebo si prostudujte oficiální [Aspose.Slides reference](https://reference.aspose.com/slides/java/).

## Zdroje
- **Dokumentace:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Reference (malými písmeny):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Komunitní fórum:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Stahování:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Poslední aktualizace:** 2026-07-17  
**Testováno s:** Aspose.Slides pro Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak přidat grafy do PowerPointu pomocí Aspose.Slides pro Java: krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animace grafů v PowerPointu pomocí Aspose.Slides pro Java – průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Vytvoření grafu v Javě s Aspose.Slides – přidání a validace grafů](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}