---
date: '2026-06-03'
description: Zjistěte, jak vytvářet grafy v .NET prezentacích a přidat graf do snímku
  pomocí Aspose.Slides for Java. Postupujte podle tohoto step‑by‑step průvodce pro
  vizualizaci dat.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Vytvářejte grafy v .NET pomocí Aspose.Slides for Java
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvořte grafy v .NET pomocí Aspose.Slides pro Java

## Úvod
Vytváření působivých prezentací často zahrnuje integraci vizuálních datových reprezentací, jako jsou grafy, které zvyšují pochopení a zapojení publika. **Pokud chcete vytvářet grafy v .NET**, Aspose.Slides for Java vám poskytuje výkonné, jazykově nezávislé API, které funguje bez problémů uvnitř .NET aplikací. V tomto tutoriálu se naučíte, jak inicializovat prezentaci, přidat různé typy grafů, spravovat sešit dat grafu a formátovat data řad — včetně zpracování záporných hodnot. Na konci budete schopni programově generovat grafy v souborech prezentací a přidat graf do snímku pomocí několika řádků kódu.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Vytvářet grafy v .NET prezentacích pomocí Aspose.Slides for Java.  
- **Jaká verze knihovny je vyžadována?** Aspose.Slides for Java 25.4 nebo novější.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu použít Maven nebo Gradle?** Ano — oba systémy sestavení jsou podporovány.  
- **Jaké typy grafů jsou k dispozici?** Seskupený sloupcový, čárový, koláčový, pruhový, plošný a další.

## Jak vytvořit grafy v .NET prezentacích pomocí Aspose.Slides for Java?
Třída `Presentation` představuje soubor PowerPoint a poskytuje metody pro manipulaci s jeho snímky. Načtěte nový objekt `Presentation`, zavolejte `slides.addEmptySlide()` pro získání snímku a poté použijte `slide.getShapes().addChart()` k vložení požadovaného typu grafu na zadané souřadnice. Po přidání grafu naplňte jeho datový sešit řadami a kategoriemi, aplikujte libovolné formátování (například barvy pro záporné hodnoty) a nakonec uložte prezentaci do souboru .pptx. Tento postup vám umožní **vytvářet grafy v .NET** pomocí stručné sady volání API.

## Co je Aspose.Slides for Java?
Aspose.Slides for Java je multiplatformní API, které umožňuje vývojářům vytvářet, upravovat a renderovat soubory PowerPoint bez Microsoft Office. Podporuje **více než 50 vstupních a výstupních formátů** a dokáže zpracovat prezentace s tisíci snímky při zachování využití paměti pod 200 MB.

## Proč použít Aspose.Slides for Java v .NET projektu?
Aspose.Slides for Java běží na Java Virtual Machine a může být voláno z .NET prostřednictvím nativního wrapperu, což .NET vývojářům poskytuje přístup k vyspělému grafickému enginu, vysoce výkonnému zpracování velkých datových sad a plnou kompatibilitu s existujícím Java kódem bez nutnosti přepisovat logiku.

## Požadavky
Než se pustíte do vytváření grafů pomocí Aspose.Slides for Java, uveďme, co potřebujete:

### Požadované knihovny a verze
- **Aspose.Slides for Java**: Verze 25.4 nebo novější.

### Požadavky na nastavení prostředí
- Vývojové prostředí podporující .NET aplikace.  
- Základní pochopení konceptů programování v Javě.

### Předpoklady znalostí
- Znalost vytváření prezentací v kontextu .NET aplikací.  
- Porozumění závislostem Java a jejich správě (Maven/Gradle).

## Nastavení Aspose.Slides for Java
Chcete‑li začít používat Aspose.Slides, musíte jej zahrnout jako závislost do svého projektu. Zde je návod, jak na to:

### Maven
Úryvek Maven závislosti přidá Aspose.Slides for Java do vašeho projektu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Přidejte tento řádek do souboru `build.gradle`, aby se knihovna stáhla z Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně můžete stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroky získání licence
- **Free Trial**: Začněte s dočasnou licencí pro vyzkoušení funkcí.  
- **Purchase**: Zakupte licenci pro neomezené používání v produkci.

#### Základní inicializace a nastavení
Inicializace `Slides` vyžaduje nastavení licence a vytvoření instance `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Toto nastavení zajišťuje efektivní správu zdrojů.

## Průvodce implementací
Provedeme vás implementací funkcí krok za krokem.

### Inicializace prezentace
**Přehled:**  
Vytvoření instance prezentace připraví podmínky pro všechny následné operace. Tato funkce ukazuje, jak začít od nuly pomocí Aspose.Slides.

#### Krok 1: Importujte potřebné balíčky
`Presentation` a související třídy jsou součástí jmenného prostoru `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Krok 2: Vytvořte nový objekt Presentation
Vytvořte instanci objektu `Presentation` a zabalte ji do bloku try‑with‑resources, aby byla zaručena uvolnění prostředků.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*This ensures that the presentation object is properly disposed of after use, preventing memory leaks.*  
*Tím se zajistí, že objekt prezentace je po použití řádně uvolněn, což zabraňuje únikům paměti.*

### Přidání grafu do snímku
**Přehled:**  
Přidání grafu do snímku může učinit vizualizaci dat efektivnější a poutavější.

#### Krok 1: Importujte potřebné balíčky
Třída `Chart` představuje tvar grafu, který může být umístěn na snímek a přizpůsoben.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Krok 2: Inicializujte prezentaci a přidejte graf
Vytvořte snímek, poté zavolejte `addChart` s `ChartType.ClusteredColumn` a požadovanou pozicí a velikostí.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Zde přidáváme seskupený sloupcový graf na první snímek na zadaných souřadnicích a rozměrech.*

### Správa sešitu dat grafu
**Přehled:**  
Efektivní správa sešitu dat vašeho grafu vám umožní plynule manipulovat s řadami a kategoriemi.

#### Krok 1: Importujte potřebné balíčky
`IChartDataWorkbook` poskytuje přístup k podkladovému sešitu podobnému Excelu, který grafy používají.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Krok 2: Přístup a vymazání sešitu dat
Získejte sešit z grafu a vymažte veškerá existující data, abyste mohli začít s čistým listem.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Vymazání sešitu je klíčové pro začátek s čistým listem při přidávání nových řad a kategorií.*

### Přidání řad a kategorií do grafu
**Přehled:**  
Tato funkce ukazuje, jak můžete přidávat smysluplné datové body pomocí správy řad a kategorií.

#### Krok 1: Přidejte řady a kategorie
Použijte `chart.getChartData().getSeries().add()` a `chart.getChartData().getCategories().add()` k definování struktury.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Přidání řad a kategorií umožňuje lépe uspořádanou prezentaci dat.*

### Naplnění dat řad a formátování
**Přehled:**  
Naplněte svůj graf datovými body a formátujte vzhled pro zvýšení čitelnosti, zejména při práci se zápornými hodnotami.

#### Krok 1: Naplňte data řad
Přiřaďte číselné hodnoty každé buňce v sešitu a použijte červené vyplnění pro záporná čísla.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Tato část ukazuje, jak naplnit data a aplikovat barevné formátování pro lepší vizualizaci.*

## Časté problémy a řešení
- **LicenseNotFoundException** – Ujistěte se, že cesta k souboru licence je správná a soubor je přístupný za běhu.  
- **NullPointerException on chart data** – Vždy vymažte sešit před přidáním nových řad, aby nedošlo k zbytkovým datům.  
- **Chart not rendering in .NET** – Ověřte, že používáte verzi Aspose.Slides JAR kompatibilní s .NET a že Java runtime je správně nakonfigurován ve vašem .NET projektu.

## Často kladené otázky

**Q: Mohu generovat graf v souborech prezentací bez GUI?**  
A: Ano, Aspose.Slides for Java je zcela headless a funguje na serverech bez jakýchkoli grafických komponent.

**Q: Jaké verze .NET jsou podporovány?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 a .NET 6 jsou všechny podporovány.

**Q: Kolik typů grafů mohu přidat?**  
A: K dispozici je více než 20 typů grafů, včetně sloupcových, čárových, koláčových, plošných a radarových grafů.

**Q: Je možné stylovat jednotlivé datové body?**  
A: Rozhodně – můžete nastavit barvy výplně, okraje a značky pro každý datový bod pomocí API `IDataPoint`.

**Q: Musím ručně převádět objekty Java na typy .NET?**  
A: Ne, .NET wrapper Aspose.Slides for Java automaticky provádí konverzi typů.

---

**Poslední aktualizace:** 2026-06-03  
**Testováno s:** Aspose.Slides for Java 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vložit grafy do .NET prezentací pomocí Aspose.Slides pro efektivní vizualizaci dat](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Jak získat typ zdroje dat grafu pomocí Aspose.Slides pro .NET – Grafy a diagramy](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Mistrovské vytvoření a manipulace sérií grafu s Aspose.Slides .NET pro efektivní vizualizaci dat](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}