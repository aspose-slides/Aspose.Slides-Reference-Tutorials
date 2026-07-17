---
date: '2026-07-17'
description: Naučte se, jak otočit koláčový graf, přizpůsobit barvy koláčového grafu
  a exportovat snímek do PDF pomocí Aspose.Slides for Java – kompletní průvodce vizualizací
  dat.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Otočte koláčový graf a přizpůsobte barvy koláčového grafu pomocí Aspose.Slides
  pro Java. Naučte se exportovat snímek do PDF a pracovat s chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Otočte koláčový graf a přizpůsobte barvy v Javě – průvodce Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Jak otočit koláčový graf a přizpůsobit barvy v Javě s Aspose.Slides
url: /cs/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytváření koláčových grafů s Aspose.Slides pro Java: Kompletní návod

## Úvod
V tomto průvodci se naučíte, jak **otočit koláčový graf**, přizpůsobit barvu každého výseku a exportovat finální snímek do PDF – vše pomocí Aspose.Slides pro Java. Ať už vytváříte prodejní dashboard, finanční zprávu nebo jakoukoli prezentaci založenou na datech, zvládnutí těchto technik vám umožní předat jasné, poutavé vizuály bez nutnosti používat Microsoft Office. Připravme si nástroje a ponořme se do toho.

## Rychlé odpovědi
- **Která třída zahajuje novou prezentaci?** `Presentation` from `com.aspose.slides`.
- **Které volání API přidá koláčový graf?** `slide.addChart(ChartType.Pie, …)`.
- **Jak můžete každému výseku přiřadit jedinečnou barvu?** Call `series.setColorVaried(true)` and set solid fills per data point.
- **Jaká metoda otáčí graf?** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **Lze snímek exportovat do PDF?** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Co je „přizpůsobení barev koláčového grafu“?
Přizpůsobení barev koláčového grafu znamená přiřazení odlišných výplňových barev každému výseku koláče, což zlepšuje čitelnost a vizuální dopad. V Aspose.Slides toho dosáhnete povolením různých barev a následným nastavením plných výplní pro jednotlivé datové body. Tento přístup zajišťuje, že každý datový segment v prezentaci jasně vynikne.

## Proč používat Aspose.Slides pro Java k vytváření koláčových grafů?
Aspose.Slides podporuje **více než 150 typů grafů** a dokáže vykreslit 300‑stránkovou prezentaci za méně než **5 sekund** na typickém serveru, a to bez nutnosti instalace Microsoft Office. Knihovna běží na Windows, Linuxu i macOS, což vám poskytuje multiplatformní flexibilitu pro jakýkoli projekt vizualizace dat založený na Javě.

## Požadavky
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 nebo novější
- IDE jako IntelliJ IDEA, Eclipse nebo NetBeans
- Základní znalost Javy a znalost Maven nebo Gradle

## Nastavení Aspose.Slides pro Java
Přidejte knihovnu do vaší konfigurační sestavy.

**Maven**  
Přidejte tento úryvek do souboru `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Zahrňte následující do souboru `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Přímé stažení**  
Pokud dáváte přednost manuálnímu přístupu, stáhněte si nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroky získání licence
- **Free Trial** – prozkoumejte všechny funkce zdarma.  
- **Temporary License** – prodlužte zkušební limity na krátkou dobu.  
- **Purchase** – získejte trvalou licenci pro produkční použití.

**Základní inicializace a nastavení**  
Třída `Presentation` představuje soubor PowerPoint v paměti a poskytuje metody pro manipulaci se snímky.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Průvodce implementací
Níže je podrobný průvodce krok za krokem, který pokrývá vše od vytvoření snímku po otočení finálního koláčového grafu.

### Inicializace prezentace a snímku
Vytvořte novou instanci `Presentation` a získejte první snímek, který bude sloužit jako plátno pro graf.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Přidání koláčového grafu na snímek
`addChart` přidá tvar grafu zadaného typu na snímek na daných souřadnicích.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Nastavení názvu grafu
`setTitle` přiřadí textový název grafu a umístí jej do středu.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurace popisků dat pro sérii
`setShowValue(true)` povolí číselné popisky hodnot na každém datovém bodu série.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Příprava pracovního listu dat grafu
`ChartDataWorkbook` ukládá podkladovou datovou tabulku, která napájí série a kategorie grafu.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Přidání kategorií do grafu
`addCategory` vytvoří nový štítek kategorie pro datové série grafu.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Přidání série a naplnění datových bodů
`addSeries` vytvoří datovou sérii a `addDataPointForBarSeries` vloží číselné hodnoty pro každou kategorii.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Přizpůsobení barev a okrajů série
`setColorVaried(true)` povolí různé barvy pro jednotlivé výseky a `setFillFormat` přiřadí plnou výplň každému datovému bodu.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Konfigurace vlastních popisků dat
`setDataLabelFormat` přizpůsobuje vzhled popisku, jeho umístění a písmo pro srozumitelnější anotace grafu.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Nastavení úhlu otočení a uložení prezentace
`setRotationAngle` otáčí celý koláčový graf a `save` zapíše prezentaci do souboru.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Jak otočit koláčový graf?
Načtěte objekt grafu, zavolejte `chart.setRotationAngle(45.0)` (nebo libovolnou hodnotu ve stupních) a poté uložte prezentaci. Otočení koláčového grafu posune počáteční úhel, což vám umožní zvýraznit konkrétní výsek bez změny dat. Toto jediné volání metody funguje pro jakoukoli instanci `Chart` v Aspose.Slides. Můžete také kombinovat otočení s různými barvami výsečů, abyste upoutali pozornost na nejdůležitější datový bod.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Výseky mají všechny stejnou barvu** | `setColorVaried(true)` nebylo zavoláno | Ujistěte se, že jste povolili různé barvy ve skupině sérií. |
| **Popisky dat se nezobrazují** | `showValue` flag disabled | Call `setShowValue(true)` on the label format. |
| **Otočení nemá žádný efekt** | Using an older Aspose.Slides version | Upgrade to version 25.4 or later. |
| **Výjimka licence za běhu** | Missing or invalid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## Často kladené otázky

**Q: Jak získám licenci Aspose.Slides pro Java?**  
A: Požádejte o bezplatnou zkušební verzi na webu Aspose, poté zakupte trvalou licenci. Načtěte ji za běhu, jak je ukázáno v tabulce Častých problémů.

**Q: Mohu použít tento kód se staršími verzemi JDK?**  
A: API vyžaduje JDK 16 nebo vyšší; starší verze nejsou podporovány.

**Q: Je možné exportovat graf jako obrázek místo PPTX?**  
A: Ano—po vykreslení zavolejte `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Co když potřebuji v koláčovém grafu více než jednu sérii?**  
A: Koláčové grafy jsou určeny pro jednu datovou sérii; pro více sérií zvažte použití prstencového grafu.

**Q: Běží Aspose.Slides na Linuxových serverech?**  
A: Ano—Aspose.Slides pro Java je platformově nezávislý a funguje na jakémkoli OS s kompatibilním JDK.

---
**Poslední aktualizace:** 2026-07-17  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak vytvořit koláčové grafy v Java prezentacích pomocí Aspose.Slides: Kompletní průvodce](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Mistrovství koláčových grafů v Javě pomocí Aspose.Slides: Kompletní průvodce](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Otočení textů grafu v Javě s Aspose.Slides: Kompletní průvodce](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}