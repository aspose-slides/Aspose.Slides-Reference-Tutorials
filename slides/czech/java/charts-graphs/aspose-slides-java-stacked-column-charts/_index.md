---
date: '2026-07-22'
description: Naučte se používat Aspose Slides Maven Dependency k vytvoření stacked
  column chart v Javě, přidat data labels, změnit formát čísel na vertikální ose a
  exportovat výsledek jako soubor PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency vám umožní vytvořit stacked column
  chart v Javě, přizpůsobit data labels, upravit formát vertikální osy a uložit jako
  PPTX – vše s stručným, připraveným k produkci kódem.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart v Javě'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart v Javě'
url: /cs/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven závislost: Skládaný sloupcový graf v Javě

## Úvod

Pozvedněte své prezentace začleněním podrobných vizualizací dat s pomocí **Aspose.Slides for Java**. V tomto průvodci **vytvoříte skládaný sloupcový graf**, který bude vypadat profesionálně, ať už připravujete obchodní zprávy nebo představujete statistiky projektů. Na konci tohoto tutoriálu budete schopni:

- Nastavit své prostředí pomocí **Aspose Slides Maven závislosti**
- Vytvořit prezentaci od nuly
- **Přidat procentuálně‑skládaný graf** a přizpůsobit jeho vzhled
- **Formátovat popisky dat grafu** a **změnit formát čísel na svislé ose**
- **Uložit prezentaci jako PPTX** jedním řádkem kódu

## Rychlé odpovědi
- **Jakou knihovnu potřebuji?** Přidejte Maven/Gradle závislost `aspose-slides` (viz „Aspose Slides Maven Dependency“ níže).  
- **Který typ grafu vytváří skládaný pohled?** Použijte `ChartType.PercentsStackedColumn` pro procentuálně‑skládaný sloupcový graf.  
- **Jak mohu změnit formát čísel osy?** Zavolejte `IAxis.setNumberFormat()` a nastavte `setNumberFormatLinkedToSource(false)`.  
- **Mohu přizpůsobit popisky dat?** Ano – projděte každé `IChartDataPoint` a přiřaďte vlastní `ITextFrame`.  
- **Jak uložit soubor?** Zavolejte `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Co je skládaný sloupcový graf?
Skládaný sloupcový graf vizualizuje více datových sérií naskládaných vertikálně v každém sloupci kategorie, přičemž varianta **procentuálně‑skládaná** normalizuje každý sloupec na 100 % pro snadné porovnání podílů. Tento formát umožňuje divákům rychle posoudit, jak každý komponent přispívá k celku napříč různými kategoriemi, což okamžitě zviditelní trendy a relativní velikosti.

## Proč použít Aspose.Slides pro Java?
Aspose.Slides pro Java vám umožňuje generovat, upravovat a konvertovat soubory PowerPoint **bez potřeby Microsoft Office** a podporuje **více než 50 výstupních formátů** na Windows, Linuxu a macOS. Knihovna běží kompletně na JRE, což umožňuje automatizaci na straně serveru a vysokokapacitní reportování. Také poskytuje detailní kontrolu nad objekty grafů, rozvržením snímků a vlastnostmi dokumentu, což z ní činí ideální řešení pro tvorbu prezentací na úrovni podniku.

## Požadavky
- **Java Development Kit (JDK):** 8 nebo vyšší  
- **IDE:** IntelliJ IDEA, Eclipse nebo jakýkoli Java‑kompatibilní editor  
- **Nástroj pro sestavení:** Maven nebo Gradle (volitelné, ale doporučené)  
- **Základní znalost Javy** – měli byste být obeznámeni s třídami a metodami  

## Nastavení Aspose.Slides pro Java
Pro začátek přidejte knihovnu Aspose.Slides do svého projektu.

### Aspose Slides Maven závislost
Přidejte následující do svého `pom.xml` (toto je **aspose slides maven závislost**, kterou budete potřebovat):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa pro Gradle
Pokud dáváte přednost Gradlu, zahrňte tento řádek do `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně stáhněte nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Pro odstranění omezení hodnocení zvažte získání dočasné nebo zakoupené licence.

- **Bezplatná zkušební verze:** Přístup k omezeným funkcím bez okamžitých nákladů.  
- **Dočasná licence:** Požádejte přes [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Koupě:** Navštivte stránku nákupu pro plný přístup.

### Základní inicializace
`Presentation` je základní třída Aspose.Slides představující soubor PowerPoint v paměti. Následující minimální úryvek ukazuje, jak vytvořit objekt `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Průvodce implementací

### Vytvoření prezentace a přidání snímku
**Přehled:**  
Nejprve vytvoříme prázdnou prezentaci a ověříme, že snímek existuje.

#### Krok 1: Inicializace objektu Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Krok 2: Uložení prezentace
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Přidání procentuálně‑skládaného sloupcového grafu na snímek
**Přehled:**  
Nyní umístíme **procentuálně‑skládaný graf** na první snímek.

`ChartType.PercentsStackedColumn` určuje typ procentuálně‑skládaného sloupcového grafu.

#### Krok 1: Inicializace a přístup k snímku
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Krok 2: Přidání grafu na snímek
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Přizpůsobení formátu čísel osy grafu
**Přehled:** Pro lepší čitelnost **změníme formát svislé osy** tak, aby zobrazoval procenta.

`IAxis` je rozhraní představující osu grafu, umožňující úpravy formátu a měřítka.

#### Krok 1: Přidání a přístup k grafu
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Krok 2: Nastavení vlastního formátu čísel
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Přidání sérií a datových bodů do grafu
**Přehled:** Naplníme graf ukázkovými datovými sériemi.

#### Krok 1: Inicializace prezentace a grafu
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Krok 2: Přidání datové série
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formátování výplně série
**Přehled:** Každé sérii přiřaďte odlišnou barvu, aby byl graf snadněji čitelný.

#### Krok 1: Inicializace a přístup k grafu
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Krok 2: Nastavení výplňových barev
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formátování popisků dat
**Přehled:** Nyní **naformátujeme popisky dat grafu**, aby zobrazovaly vlastní text.

`IChartDataPoint` představuje jednotlivý datový bod v sérii grafu a `ITextFrame` obsahuje text popisku.

#### Krok 1: Přístup k sériím grafu a datovým bodům
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Krok 2: Přizpůsobení popisků dat
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Časté problémy a řešení
- **Graf je prázdný:** Ujistěte se, že jste před uložením přidali alespoň jednu datovou sérii a datový bod.  
- **Čísla na ose se nezobrazují jako procenta:** Nezapomeňte nastavit `verticalAxis.setNumberFormatLinkedToSource(false)`; jinak je vlastní formát ignorován.  
- **Zpráva o hodnocení licence:** Použijte platný licenční soubor před vytvořením objektu `Presentation`, aby se skryl evaluační banner.

## Často kladené otázky

**Q: Mohu použít tento kód s Java 11 nebo novější?**  
A: Ano. Knihovna podporuje JDK 8+; stačí použít odpovídající klasifikátor (např. `jdk16` pro JDK 16 nebo novější).

**Q: Jak exportovat graf jako obrázek místo PPTX?**  
A: Použijte `chart.getImage().save("chart.png", ImageFormat.Png);` po přidání grafu na snímek.

**Q: Je možné přidat legendu k skládanému sloupcovému grafu?**  
A: Rozhodně. Zavolejte `chart.getChartTitle().addTextFrameForOverriding("My Chart");` a podle potřeby nakonfigurujte `chart.getLegend()`.

**Q: Co když potřebuji po vygenerování prezentace aktualizovat data?**  
A: Můžete upravit buňky `ChartDataWorkbook` a poté zavolat `chart.refresh();`, aby se změny projevily.

**Q: Funguje Aspose.Slides na Linuxových serverech?**  
A: Ano. Knihovna je čistě Java a běží na libovolném OS s kompatibilní JRE.

## Závěr
Podle tohoto průvodce jste se naučili, jak **vytvořit skládaný sloupcový graf** v Javě pomocí **Aspose Slides Maven závislosti**, od nastavení prostředí po jemné vizuální úpravy. Experimentujte s různými datovými sadami, barvami a formáty popisků, aby vaše zprávy opravdu vynikly.

---

**Poslední aktualizace:** 2026-07-22  
**Testováno s:** Aspose.Slides 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vytvořit seskupený sloupcový graf v Javě s Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Jak nastavit formáty čísel v datových bodech grafu pomocí Aspose.Slides pro Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Jak přidat a konfigurovat grafy v prezentacích pomocí Aspose.Slides pro Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}