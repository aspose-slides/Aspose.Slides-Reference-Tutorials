---
date: '2026-09-02'
description: Naučte se, jak vytvořit funnel chart v PowerPointu pomocí Aspose.Slides
  for Java. Tento krok‑za‑krokem průvodce pokrývá nastavení dat grafu, přizpůsobení
  barev a export prezentace.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Naučte se, jak vytvořit funnel chart v PowerPointu pomocí Aspose.Slides
  for Java. Tento průvodce vás provede nastavením dat, přizpůsobením barev a exportem
  finální prezentace.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Vytvořte funnel chart v PowerPointu s Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Vytvořte funnel chart v PowerPointu s Aspose.Slides for Java
url: /cs/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ovládání tvorby trychového grafu v PowerPointu s Aspose.Slides pro Java

## Úvod
Vytváření působivých prezentací je umění, které spojuje vizualizaci dat, design a vyprávění příběhů. Jedním silným vizuálem, který okamžitě objasňuje vícefázový proces, je trychový graf. Ať už potřebujete ilustrovat prodejní pipeline, konverzní tok nebo úzké místo ve výrobě, dobře navržený trychový graf promění surová čísla v intuitivní příběh. V tomto tutoriálu se naučíte, jak **vytvořit trychový graf** v PowerPointu programově pomocí Aspose.Slides pro Java, nakonfigurovat jeho data, přizpůsobit barvu každého segmentu a exportovat hotovou prezentaci.

**Co se naučíte**
- Jak přidat Aspose.Slides pro Java do projektu Maven nebo Gradle
- Jak vytvořit objekt `Presentation` a získat přístup k jeho snímkům
- Jak vložit trychový graf, definovat kategorie a naplnit data řad
- Jak stylovat každý výsek trychového grafu pomocí plných výplní nebo specifických firemních barev
- Jak uložit prezentaci jako soubor PPTX nebo exportovat snímek jako obrázek

## Rychlé odpovědi
- **Jaká je hlavní knihovna pro vizualizaci dat v Javě?** Aspose.Slides for Java.  
- **Jak vytvořit trychový graf v PowerPointu?** Zavolejte `slide.addChart(ChartType.Funnel, …)` na cílovém snímku.  
- **Které API nastavuje zdroj dat grafu?** Použijte `IChartDataWorkbook` spolu s `chart.getChartData()`.  
- **Můžete přizpůsobit barvy pro každý segment trychového grafu?** Ano—nastavte `FillFormat.setFillType(FillType.Solid)` a přiřaďte `java.awt.Color`.  
- **Potřebujete licenci pro produkční použití?** Pro komerční nasazení je vyžadována zakoupená licence Aspose.Slides.

## Co je vizualizace dat v Javě?
Vizualizace dat v Javě je praxe převádění surových dat na grafy, diagramy nebo interaktivní grafiku přímo z Java aplikací. Aspose.Slides pro Java je přední knihovna, která umožňuje vývojářům generovat více než 100 typů grafů – včetně trychových grafů – bez nutnosti ručního spouštění PowerPointu, podporuje prezentace až do 500 snímků a přitom udržuje nízkou spotřebu paměti.

## Proč používat trychové grafy v PowerPointu?
Trychové grafy okamžitě odhalují míru úbytku napříč sekvenčními fázemi, což je činí ideálními pro prodejní pipeline, analýzu konverzí nebo revize efektivity procesů. Aspose.Slides vám poskytuje pixelově přesnou kontrolu nad rozvržením, barvami segmentů a popisky dat, takže můžete zachovat konzistenci značky a vyhnout se ručnímu úsilí při úpravě grafů v uživatelském rozhraní PowerPointu.

## Požadavky (H2)

### Požadované knihovny, verze a závislosti
Pro implementaci Aspose.Slides pro Java ve vašem projektu zahrňte odpovídající Maven nebo Gradle koordináty. Knihovna funguje s Java 8‑21 a nevyžaduje žádné externí nativní závislosti.

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

JAR můžete také stáhnout přímo z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Požadavky na nastavení prostředí
Ujistěte se, že máte nainstalovaný JDK 8 nebo novější a že vaše proměnná `JAVA_HOME` ukazuje na správný adresář JDK. Aspose.Slides běží na jakémkoli OS, který podporuje JDK, včetně Windows, macOS a Linuxu.

### Předpoklady znalostí
Základní znalost syntaxe Javy, objektově orientovaného programování a konceptu souboru prezentace pomůže, ale úryvky kódu jsou plně vysvětleny pro vývojáře jakékoli úrovně zkušeností.

## Nastavení Aspose.Slides pro Java (H2)

1. **Přidejte závislost** – Použijte výše uvedený Maven nebo Gradle úryvek.  
2. **Získejte licenci** –  
   - **Free trial** – Stáhněte si dočasnou licenci z [Aspose's website](https://purchase.aspose.com/temporary-license/) pro hodnocení.  
   - **Full license** – Zakupte produkční licenci prostřednictvím [purchase page](https://purchase.aspose.com/buy).  
3. **Základní inicializace** –  

`Presentation` je jádrová třída Aspose.Slides, která představuje soubor PowerPoint v paměti. Poskytuje přístup ke snímkům, tvarům a objektům grafů.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Výše uvedený kód vytvoří novou instanci `Presentation`, připravenou pro manipulaci se snímky, a zajišťuje uvolnění prostředků pomocí `dispose()`.

## Průvodce implementací

Projdeme každou funkci potřebnou k vytvoření kompletního trychového grafu a přidáme krátký vysvětlující text před každý zástupný kód.

### Funkce 1: vytvoření prezentace (H2)

#### Přehled
Začněte vytvořením instance třídy `Presentation`. Tento objekt je vstupním bodem pro všechny následné operace.

`Presentation` je nejvyšší objekt Aspose.Slides, který obsahuje kolekci snímků a globální nastavení dokumentu.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Úryvek otevře prázdnou prezentaci, kterou můžete později uložit jako soubor `.pptx`.

### Funkce 2: přidání trychového grafu na snímek (H2)

#### Přehled
Vložte trychový graf na první snímek, definujte jeho velikost a nastavte typ grafu.

`ChartType.Funnel` říká Aspose.Slides, aby vykreslil vizualizaci ve stylu trychového grafu místo sloupcového nebo čárového grafu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Volání `addChart` vytvoří tvar grafu, umístí jej na souřadnice `(50, 50)` bodů a nastaví šířku na `500` a výšku na `400`.

### Funkce 3: vymazání dat grafu (H2)

#### Přehled
Před naplněním grafu vymažte všechny zástupné kategorie nebo řady, které může šablona obsahovat.

`chart.getChartData().getCategories().clear()` odstraní všechny existující položky kategorií, zatímco `chart.getChartData().getSeries().clear()` odstraní jakékoli předvyplněné řady.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Tím se zajistí čistý základ, aby vaše vlastní data byla zobrazena přesně podle očekávání.

### Funkce 4: nastavení sešitu dat grafu (H2)

#### Přehled
Objekt `IChartDataWorkbook` ukládá surové hodnoty, které pohánějí graf. Jeho inicializace vám umožní zapisovat data přímo do buněk.

`IChartDataWorkbook` je lehký in‑memory tabulkový proces, který Aspose.Slides používá k napájení řad a kategorií grafu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Kód vymaže všechny existující buňky a připraví sešit na nové záznamy.

### Funkce 5: přidání kategorií do grafu (H2)

#### Přehled
Definujte textové štítky, které se zobrazují na levé straně trychového grafu – představují jednotlivé fáze vašeho procesu.

`chart.getChartData().getCategories().add()` vytvoří nový objekt kategorie spojený s konkrétní buňkou sešitu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Zde přidáváme tři fáze: „Potenciální zákazníci“, „Kvalifikované leady“ a „Uzavřené obchody“.

### Funkce 6: přidání datových řad do grafu (H2)

#### Přehled
Naplněte trychový graf číselnými hodnotami a případně přiřaďte každému výseku jedinečnou barvu.

`IDataPoint` představuje jeden datový bod v řadě grafu. `chart.getChartData().getSeries().add()` vytvoří řadu, která obsahuje číselné datové body; každý `IDataPoint` může získat vlastní barvu výplně.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Smyčka ukazuje, jak nastavit plnou výplň pro každý bod, pomocí buď specifických `java.awt.Color` konstant značky, nebo náhodně generovaných barev pro vizuální rozmanitost.

## Běžné případy použití a tipy (H2)

- **Reportování prodejní pipeline** – Zobrazte, kolik leadů přechází z potenciálu do uzavřeného výnosu v každé fázi.  
- **Analýza efektivity procesů** – Vizualizujte ztrátu materiálu nebo časová zpoždění napříč výrobními kroky.  
- **Revize marketingového trychového grafu** – Porovnejte konverzní poměry napříč kampaněmi nebo zdroji provozu.  

**Pro tip:** Místo náhodných barev použijte paletu značky vaší společnosti (např. `new Color(0, 112, 192)`), aby byla prezentace konzistentní s ostatními marketingovými materiály.

## Často kladené otázky (H2)

**Q: Jak změním orientaci trychového grafu?**  
A: Nastavte vlastnost `ChartOrientation` na objektu `IChart` na `ChartOrientation.Vertical` nebo `ChartOrientation.Horizontal`.

**Q: Mohu po přidání grafu exportovat snímek jako obrázek?**  
A: Ano—zavolejte `pres.getSlides().get_Item(0).getThumbnail(1, 1)` a zapište vzniklý `java.awt.image.BufferedImage` do souboru PNG nebo JPEG.

**Q: Co když potřebuji více než tři kategorie?**  
A: Jednoduše přidejte další kategorie pomocí `chart.getChartData().getCategories().add(...)` a poskytněte odpovídající datové body pro každou novou kategorii.

**Q: Existuje způsob, jak skrýt legendu?**  
A: Použijte `chart.getChartTitle().setVisible(false)` a `chart.getLegend().setVisible(false)` k odstranění jak titulku, tak legendy z vizuálu.

**Q: Potřebuji licenci pro vývojové sestavy?**  
A: Dočasná licence stačí pro hodnocení; plná komerční licence je vyžadována pro produkční nasazení.

---

**Poslední aktualizace:** 2026-09-02  
**Testováno s:** Aspose.Slides pro Java 25.4 (jdk16)  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak upravit data grafu v PowerPointu pomocí Aspose.Slides pro Java: Kompletní průvodce](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Přidání animace do grafu v PowerPointu pomocí Aspose.Slides pro Java – Průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}