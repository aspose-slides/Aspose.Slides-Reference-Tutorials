---
"date": "2025-04-17"
"description": "Naučte se vytvářet profesionální prezentace pomocí Aspose.Slides pro Javu. Tato příručka se zabývá nastavením prostředí, přidáváním skládaných sloupcových grafů a jejich přizpůsobením pro lepší přehlednost."
"title": "Zvládněte skládané sloupcové grafy v Javě s Aspose.Slides – Komplexní průvodce"
"url": "/cs/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Zvládněte skládané sloupcové grafy v Javě s Aspose.Slides: Komplexní průvodce

## Zavedení

Pozdvihněte úroveň svých prezentací začleněním užitečných vizualizací dat s využitím Aspose.Slides pro Javu. Vytváření profesionálně vypadajících snímků se skládanými sloupcovými grafy je snadné, ať už připravujete obchodní zprávy nebo prezentujete statistiky projektu.

V tomto tutoriálu se podíváme na to, jak pomocí Aspose.Slides pro Javu vytvářet dynamické prezentace a přidávat vizuálně atraktivní skládané sloupcové grafy. Po absolvování tohoto průvodce budete vybaveni dovednostmi potřebnými k:
- Nastavte si prostředí pro použití Aspose.Slides
- Vytvořte prezentaci od nuly
- Přidání a přizpůsobení procentuálně vrstvených sloupcových grafů
- Pro přehlednost formátujte osy grafu a popisky dat

Pojďme se ponořit do tvorby prezentací, které zaujmou vaše publikum.

## Předpoklady
Než začneme, ujistěte se, že máte následující:
- **Vývojová sada pro Javu (JDK):** Verze 8 nebo vyšší.
- **Rozhraní vývoje (IDE):** Jakékoli integrované vývojové prostředí, jako je IntelliJ IDEA nebo Eclipse.
- **Maven/Gradle:** Pro správu závislostí (volitelné, ale doporučené).
- **Základní znalost Javy:** Znalost konceptů programování v Javě.

## Nastavení Aspose.Slides pro Javu
Chcete-li začít, musíte do svého projektu zahrnout knihovnu Aspose.Slides. Postupujte takto:

**Znalec:**
Přidejte tuto závislost do svého `pom.xml` soubor:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Zahrňte toto do svého `build.gradle` soubor:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Přímé stažení:**
Nebo si stáhněte nejnovější JAR soubor z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Chcete-li odstranit omezení hodnocení, zvažte pořízení dočasné nebo zakoupené licence.
- **Bezplatná zkušební verze:** Získejte přístup k omezeným funkcím bez okamžitých nákladů.
- **Dočasná licence:** Žádost prostřednictvím [Asposeův web](https://purchase.aspose.com/temporary-license/).
- **Nákup:** Pro plný přístup navštivte stránku nákupu.

### Základní inicializace
Zde je návod, jak inicializovat Aspose.Slides ve vaší aplikaci Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Vytvoření instance třídy Presentation
        Presentation presentation = new Presentation();
        
        // Provádět operace s objektem prezentace
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Průvodce implementací

### Vytvoření prezentace a přidání snímku
**Přehled:**
Začněte vytvořením jednoduché prezentace s úvodním snímkem. To je základ pro další vylepšení.

#### Krok 1: Inicializace prezentačního objektu
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Vytvořit novou instanci prezentace
        Presentation presentation = new Presentation();
        
        // Odkaz na první snímek (automaticky vytvořený)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Krok 2: Uložení prezentace
```java
// Uložit prezentaci do souboru
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Přidání procentuálního skládaného sloupcového grafu na snímek
**Přehled:**
Vylepšete svůj snímek přidáním procentuálně vrstveného sloupcového grafu, který umožní snadné porovnání dat.

#### Krok 1: Inicializace a přístup k snímku
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // V dalším kroku pokračujte k přidání grafu.
    }
}
```

#### Krok 2: Přidání grafu na snímek
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Přizpůsobení formátu čísel os grafu
**Přehled:**
Pro lepší čitelnost si upravte formát čísel na svislé ose grafu.

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

#### Krok 2: Nastavení vlastního formátu čísla
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Přidávání řad a datových bodů do grafu
**Přehled:**
Naplňte svůj graf datovými řadami, čímž jej učiníte informativním a vizuálně atraktivním.

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
// Vymazat existující série a přidat nové
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// V případě potřeby přidejte další datové body
```

### Barva výplně formátovací řady
**Přehled:**
Vylepšete estetiku grafu formátováním barvy výplně každé série.

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

// Opakujte pro další série s jinými barvami.
```

### Formátování popisků dat
**Přehled:**
Usnadněte si čitelnost datových popisků přizpůsobením jejich formátu.

#### Krok 1: Přístup k řadám grafů a datovým bodům
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

#### Krok 2: Úprava popisků dat
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

## Závěr
Dodržováním tohoto návodu jste se naučili, jak nastavit Aspose.Slides pro Javu a vytvářet dynamické prezentace s procentuálně vrstvenými sloupcovými grafy. Grafy si můžete dále přizpůsobit úpravou barev a popisků podle svých potřeb.

Šťastné kódování!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}