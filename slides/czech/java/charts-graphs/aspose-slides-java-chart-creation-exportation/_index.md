---
date: '2026-06-03'
description: Naučte se, jak exportovat graf do Excelu a vytvářet grafy v Javě pomocí
  Aspose.Slides for Java. Ovládněte data visualization, business report slides a workbook
  generation.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Exportovat graf do Excelu a vytvářet grafy pomocí Aspose.Slides
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export grafu do Excelu a vytváření grafů pomocí Aspose.Slides

**Mistrovské techniky vizualizace dat s Aspose.Slides for Java**

V dnešním datově řízeném prostředí je *export chart to excel* programově dovedností, která dokáže proměnit surová čísla v poutavé vizuální příběhy. Ať už vytváříte prezentaci obchodní zprávy nebo interaktivní analytický dashboard, Aspose.Slides for Java vám dává možnost generovat, přizpůsobovat a exportovat grafy přímo z vašeho kódu. V tomto tutoriálu se naučíte, jak vytvořit objekty grafu, exportovat data grafu do Excelu a propojit grafy s externími sešity pro bezproblémovou správu dat.

## Rychlé odpovědi
- **What library is needed?** Aspose.Slides for Java (v25.4+).  
- **Can I export chart data to Excel?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **Which Java version is required?** JDK 16 or higher.  
- **Do I need a license?** A free trial works for evaluation; a permanent license is required for production.  
- **What chart type is demonstrated?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## Co je Aspose.Slides for Java?
Aspose.Slides for Java je čistě Java API, které vývojářům umožňuje vytvářet, upravovat a převádět PowerPoint prezentace bez Microsoft Office. Poskytuje komplexní sadu tříd pro manipulaci se snímky, generování grafů a konverzi formátů, což umožňuje automatizovaná řešení reportování. Podporuje **více než 50 typů grafů**, plné datové vazby a přímý export do Excelu, což z něj činí ideální nástroj pro **data visualization java** projekty.

## Proč použít Aspose.Slides k vytvoření grafu a exportu grafu do Excelu?
Export grafu do Excelu rychle a spolehlivě. Aspose.Slides eliminuje potřebu instalací Office, nabízí **více než 50 vestavěných stylů grafů** a zpracovává prezentace **do 300 MB za méně než 30 sekund** na standardním serverovém hardware. Navíc získáte nativní generování Excel sešitu, což umožňuje analytikům pracovat s čistými čísly bez ručního kopírování‑vkládání.

## Předpoklady
### Požadované knihovny a verze
- **Aspose.Slides for Java** verze 25.4 nebo novější (podporuje JDK 16+)

### Požadavky na nastavení prostředí
- Java Development Kit (JDK) 16 nebo vyšší  
- IDE jako IntelliJ IDEA nebo Eclipse (nebo jakýkoli textový editor, který preferujete)

### Předpoklady znalostí
- Základní dovednosti programování v Javě  
- Znalost nástrojů pro sestavení Maven nebo Gradle

## Nastavení Aspose.Slides pro Java
Přidejte knihovnu do svého projektu pomocí vašeho oblíbeného systému sestavení.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně můžete [stáhnout nejnovější verzi přímo](https://releases.aspose.com/slides/java/).

### Kroky pro získání licence
Aspose.Slides nabízí bezplatnou zkušební licenci k prozkoumání všech funkcí. Můžete také požádat o dočasnou licenci nebo si ji zakoupit pro rozšířené používání. Postupujte podle těchto kroků:

1. Navštivte [Aspose Purchase page](https://purchase.aspose.com/buy) a získejte svou licenci.  
2. Pro bezplatnou zkušební verzi stáhněte z [Releases](https://releases.aspose.com/slides/java/).  
3. Požádejte o dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

Jakmile máte soubor licence, inicializujte jej ve své Java aplikaci:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Průvodce krok za krokem

### Jak vytvořit graf – Načtení prezentace
Načtěte existující PowerPoint soubor, než budete moci přidávat nebo upravovat grafy.  
Třída `Presentation` představuje PowerPoint soubor v paměti a poskytuje přístup k snímkům, tvarům a objektům grafů.  
Načtěte soubor pomocí `new Presentation("input.pptx")` a poté pracujte s prvním snímkem pomocí `presentation.getSlides().get_Item(0)`. Vždy volajte `presentation.dispose()` v bloku `finally`, aby se uvolnily nativní zdroje.

### Jak vytvořit graf – Přidání koláčového grafu na snímek
Vložte koláčový graf, ideální pro zobrazení proporčních dat.  
Rozhraní `IChart` je hlavním vstupním bodem pro manipulaci s grafy; `addChart` vytvoří nový graf na cílovém snímku. Zadejte typ grafu (`ChartType.Pie`), souřadnice X/Y a šířku/výšku. Po vytvoření můžete přizpůsobit názvy, legendu a datové řady pomocí objektu `ChartData`.

### Jak exportovat graf do Excelu – Export dat grafu
Export dat grafu umožňuje analytikům pracovat s čísly v Excelu a získat tak hlubší poznatky.  
`readWorkbookStream()` vrací podkladový Excel sešit grafu jako pole bajtů. Zavolejte `chart.getChartData().readWorkbookStream()` a tento pole uložte do souboru `externalWorkbook1.xlsx` pomocí standardního Java I/O. Výsledný Excel soubor obsahuje přesně data použitá v grafu, připravená k dalšímu zpracování.

### Jak vytvořit graf – Nastavení externího sešitu pro dynamická data
Propojte graf s externím sešitem, aby se data aktualizovala v reálném čase bez nutnosti přestavovat snímek.  
`setExternalWorkbook()` sváže graf s externím Excel souborem pro dynamické aktualizace dat. Použijte `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` k propojení grafu s externím souborem. Když je Excel sešit upraven, graf automaticky odráží změny při dalším otevření prezentace, což podporuje dynamické scénáře reportování.

## Praktické aplikace
Aspose.Slides nabízí univerzální řešení pro různé reálné scénáře:

1. **Business Report Slides:** Automaticky generujte čtvrtletní výkonnostní grafy z vašich datových pipeline.  
2. **Academic Presentations:** Převádějte výzkumná data na přehledné vizualizace bez ručního vytváření grafů.  
3. **Financial Analysis:** Exportujte data grafu do Excelu pro auditory k ověření čísel, čímž snížíte manuální chyby.  
4. **Marketing Analytics:** Vizualizujte metriky kampaní a sdílejte editovatelné sešity se stakeholdery pro spolupráci při rozhodování.  
5. **Automated Dashboard Generation:** Kombinujte API pro tvorbu grafů s naplánovanými úlohami a každé ráno vytvářejte aktuální sady snímků.

## Časté problémy a řešení
- **`FileNotFoundException`** – Ověřte, že `dataDir` ukazuje na existující složku a že výstupní cesta je zapisovatelná.  
- **Memory leaks** – Vždy volajte `presentation.dispose()` v bloku `finally`, aby se uvolnily nativní zdroje.  
- **Chart not appearing** – Ujistěte se, že index snímku (`get_Item(0)`) odpovídá existujícímu snímku a že rozměry grafu jsou v mezích snímku.  
- **Excel export produces empty file** – Potvrďte, že graf skutečně obsahuje datové řady před voláním `readWorkbookStream()`.

## Často kladené otázky

**Q: Can I use a different chart type (e.g., Bar, Line) with the same code?**  
A: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such as `ChartType.Bar` or `ChartType.Line`.

**Q: Is it possible to update the external workbook after the chart is created?**  
A: Absolutely. Modify the Excel file directly; the linked chart will reflect the changes the next time the presentation is opened.

**Q: Do I need a separate license for the Excel export feature?**  
A: No. The Excel export capability is included in the standard Aspose.Slides for Java license.

**Q: Which Java versions are supported?**  
A: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may work but are not officially tested.

**Q: How can I embed the generated Excel workbook inside the PPTX file?**  
A: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook, or keep the external link for dynamic updates.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recover Workbook Data from PowerPoint Charts Using Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}