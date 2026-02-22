---
date: '2026-02-22'
description: Naučte se, jak vytvořit zásobní sloupcový graf v Javě pomocí Aspose.Slides.
  Tento tutoriál pokrývá závislost Aspose Slides Maven, přidání procentuálního zásobního
  grafu, formátování popisků dat v grafu a uložení prezentace jako PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Jak vytvořit skládaný sloupcový graf v Javě s Aspose.Slides – komplexní průvodce
url: /cs/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit sloupcový graf se zásobníkem v Javě s Aspose.Slides – Kompletní průvodce

## Úvod

Pozvedněte své prezentace začleněním podrobných vizualizací dat s pomocí Aspose.Slides pro Java. V tomto průvodci **vytvoříte sloupcový graf se zásobníkem** snímky, které vypadají profesionálně, ať už připravujete obchodní zprávy nebo představujete statistiky projektů. Na konci tohoto tutoriálu budete schopni:

- Nastavit své prostředí pomocí Maven závislosti Aspose Slides
- Vytvořit prezentaci od nuly
- **Přidat procentuální zásobníkový graf** a přizpůsobit jeho vzhled
- **Formátovat popisky dat v grafu** a **změnit formát svislé osy**
- **Uložit prezentaci jako PPTX** jedním řádkem kódu

Projděme si jednotlivé kroky, abyste mohli okamžitě začít vytvářet působivé prezentace.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** `aspose-slides` Maven/Gradle závislost (viz „aspose slides maven dependency“ níže)  
- **Jaký typ grafu se používá?** `ChartType.PercentsStackedColumn` pro procentuální zásobníkový sloupcový graf  
- **Jak změním formát čísel osy?** Použijte `IAxis.setNumberFormat()` a zakažte propojení se zdrojem  
- **Mohu přizpůsobit popisky dat?** Ano – projděte objekty `IChartDataPoint` a nastavte vlastní `ITextFrame`  
- **Jak uložit soubor?** Zavolejte `presentation.save("output.pptx", SaveFormat.Pptx)`

## Co je sloupcový graf se zásobníkem?
Sloupcový graf se zásobníkem vizualizuje více datových řad naskládaných na sebe ve svislých sloupcích. Když použijete variantu **procentuálního zásobníku**, každý sloupec vždy dosahuje celkem 100 %, což usnadňuje porovnání podílových příspěvků napříč kategoriemi.

## Proč používat Aspose.Slides pro Java?
Aspose.Slides poskytuje čisté Java API, které funguje na jakékoli platformě bez nainstalovaného Microsoft Office. Nabízí detailní kontrolu nad objekty grafů, podporuje širokou škálu formátů a umožňuje programově generovat prezentace – ideální pro automatizované reportování nebo generování dokumentů na serveru.

## Požadavky
- **Java Development Kit (JDK):** 8 nebo vyšší  
- **IDE:** IntelliJ IDEA, Eclipse nebo jakýkoli Java‑kompatibilní editor  
- **Nástroj pro sestavení:** Maven nebo Gradle (volitelné, ale doporučené)  
- **Základní znalost Javy** – měli byste být obeznámeni s třídami a metodami  

## Nastavení Aspose.Slides pro Java
Pro začátek přidejte knihovnu Aspose.Slides do svého projektu.

### Aspose Slides Maven závislost
Přidejte následující do svého `pom.xml` (toto je **aspose slides maven dependency**, kterou potřebujete):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa pro Gradle
Pokud dáváte přednost Gradle, zahrňte tento řádek do `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně stáhněte nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Pro odstranění omezení hodnocení zvažte získání dočasné nebo zakoupené licence.

- **Bezplatná zkušební verze:** Přístup k omezeným funkcím bez okamžitých nákladů.  
- **Dočasná licence:** Požádejte přes [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Zakoupení:** Navštivte stránku nákupu pro plný přístup.

### Základní inicializace
Zde je minimální úryvek, který ukazuje, jak vytvořit objekt `Presentation`:

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

### Přidání procentuálního zásobníkového sloupcového grafu na snímek
**Přehled:**  
Nyní umístíme **procentuální zásobníkový graf** na první snímek.

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
**Přehled:**  
Pro lepší čitelnost **změníme formát svislé osy** tak, aby zobrazoval procenta.

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

### Přidání řad a datových bodů do grafu
**Přehled:**  
Naplníme graf ukázkovými datovými řadami.

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

#### Krok 2: Přidání datových řad
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formátování barvy výplně řad
**Přehled:**  
Dejte každé řadě odlišnou barvu, aby byl graf snáze čitelný.

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

#### Krok 2: Nastavení barev výplně
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formátování popisků dat
**Přehled:**  
Nyní **naformátujeme popisky dat v grafu**, aby zobrazovaly vlastní text.

#### Krok 1: Přístup k řadám grafu a datovým bodům
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
- **Graf je prázdný:** Ujistěte se, že jste před uložením přidali alespoň jednu datovou řadu a datový bod.  
- **Čísla osy neukazují procenta:** Nezapomeňte nastavit `verticalAxis.setNumberFormatLinkedToSource(false)`; jinak bude vlastní formát ignorován.  
- **Zpráva o hodnocení licence:** Použijte platný licenční soubor před vytvořením objektu `Presentation`, aby se potlačil evaluační banner.

## Často kladené otázky

**Q: Mohu použít tento kód s Java 11 nebo novější?**  
A: Ano. Knihovna podporuje JDK 8+; stačí použít odpovídající klasifikátor (např. `jdk16` pro JDK 16 nebo novější).

**Q: Jak exportovat graf jako obrázek místo PPTX?**  
A: Použijte `chart.getImage().save("chart.png", ImageFormat.Png);` po přidání grafu na snímek.

**Q: Je možné přidat legendu ke sloupcovému grafu se zásobníkem?**  
A: Rozhodně. Zavolejte `chart.getChartTitle().addTextFrameForOverriding("My Chart");` a podle potřeby nakonfigurujte `chart.getLegend()`.

**Q: Co když potřebuji aktualizovat data po vygenerování prezentace?**  
A: Můžete upravit buňky `ChartDataWorkbook` a poté zavolat `chart.refresh();`, aby se změny projevily.

**Q: Funguje Aspose.Slides na Linuxových serverech?**  
A: Ano. Knihovna je čistě Java a běží na jakémkoli OS s kompatibilní JRE.

## Závěr
Podle tohoto průvodce jste se naučili, jak **vytvořit sloupcový graf se zásobníkem** v prezentacích s Aspose.Slides pro Java, od nastavení prostředí až po detailní vizuální úpravy. Experimentujte s různými datovými sadami, barvami a formáty popisků, aby vaše zprávy skutečně vynikly.

---

**Poslední aktualizace:** 2026-02-22  
**Testováno s:** Aspose.Slides 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}