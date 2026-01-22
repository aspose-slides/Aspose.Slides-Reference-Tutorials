---
date: '2026-01-22'
description: Naučte se, jak přizpůsobit barvy koláčových grafů a přidat název grafu
  pomocí Aspose.Slides pro Javu. Zahrnuje nastavení Maven Aspose Slides a postup,
  jak uložit prezentaci ve formátu pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Jak přizpůsobit barvy koláčových grafů v Javě pomocí Aspose.Slides: Kompletní
  průvodce'
url: /cs/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytváření koláčových grafů s Aspose.Slides pro Java: Jak **přizpůsobit barvy koláčového grafu** – Kompletní tutoriál

 můžete **přizpůsobit barvy koláčového grafu** tak, aby odpovídaly vaší značce nebo zvýraznily klíčové hodnoty. V tomto tutoriálu uvidíte přesně, jak vytvořit koláčový graf, přidat název grafu, pracovat s datovými body koláčového grafu a jemně doladit barvy jednotlivých výsečů pomocí Aspose.Slides pro Java. Na konci také budete vědět, jak **ulo**
- Jak vytvořit kolřit koláč) a nastavit Java projekt.
- Kroky k přidání názvu grafu a správě datových bodů koláčového grafu.
- Techniky k **přizpůsobení barvy koláčového grafu** pro maximální vizuální dopad.
- Konfigurace závislosti Maven Aspose Slides.
- Uložení finálního souboru jako PPTX prezentace.

Pojďme začít!

## Rychlé odpovědi
- **Jak přidám název grafu?** Použijte `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **Který nástroj pro sestavení je nejlepší?** Podporovány jsou jak Maven, tak Gradle; Maven Aspose Slides je nejčastější.
- **Mohu změnit barvy výsečů?** Ano—nastavte `setColorVaried(true)` a upravte výplň každého `DataPoint`.
- **V jakém formátu se soubor uloží?** Použijte `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována trvalá licence.

## Požadavky
- **Aspose.Slides pro Java** ≥ 25.4 (doporučena nejnovější verze).
- **JDK 16+** nainstalováno a nakonfigurováno.
- IDE jako IntelliJ IDEA, Eclipse nebo NetBeans.
- Základní znalost Javy a povědomí o Maven nebo Gradle.

## Nastavení Aspose.Slides pro Java
Pro zahájení používání Aspose.Slides přidejte knihovnu do svého projektu.

**Maven** (maven aspose slides)  
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

**Direct Download**  
Pokud raději nepoužíváte nástroj pro sestavení, stáhněte si nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroky získání licence
- **Free Trial** – začněte experimentovat bez licence.
- **Temporary License** – prodlužte dobu zkušební verze.
- **Purchase** – získat plnou licenci pro produkční nasazení.

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Průvodce implementací
Níže je podrobný průvodce krok za krokem, který zachovává kód přesně tak, jak jej originální knihovna očekává.

### Krok 1: Inicializace prezentace a snímku
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Krok 2: Přidání koláčového grafu na snímek
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Krok 3: Přidání názvu grafu
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Krok 4: Zobrazení popisků dat pro první sérii
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Krok 5: Příprava pracovního listu s daty grafu
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Krok 6: Přidání kategorií (datové body koláčového grafu)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Krok 7: Přidání sérií a naplnění datových bodů
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Krok 8: **Přizpůsobení barvy koláčového grafu** – Jádro tohoto tutoriálu
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Krok 9: Konfigurace vlastních popisků dat
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Krok 10: Nastavení úhlu rotace a **uložení prezentace PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Časté problémy a řešení
- **Chybějící barvy po exportu** – Ujistěte se, že `setColorVaried(true)` je zavoláno před úpravou jednotlivých datových bodů.
- **Datové body se nezobrazují** – Ověřte, že kategorie a série jsou vymazány před přidáním nových (viz Krok 5).
- **Licence nebyla použita** – Načtěte soubor licence před vytvořením objektu `Presentation`, aby se předešlo vodoznakům z trial verze.

## Často kladené otázky

**Q: Mohu použít tento kód se staršími verzemi JDK?**  
A: Knihovna vyžaduje JDK 16 nebo vyšší; starší verze nejsou podporovány.

**Q: Jak změním název grafu po vytvoření?**  
A: Zavolejte `chart.getChartTitle().addTextFrameForOverriding("New Title")` a podle potřeby uprového grafu?**  
SlideShow` k přidání přechodů snímků nebo animací tvarů po vytvoření grafu.

**Q: Zahrnuje Maven závislost všechny transitivní knihovny?**  
A: Artefakt Maven Aspose Slides automaticky načte potřebné závislosti; žádné další kroky nejsou potřeba.

## Závěr
Nyní máte kompletní, připravený příklad pro produkci, který ukazuje **jak přizpůsobit barvy koláčového grafu**, přidat název grafu, pracovat s datovými body koláčového grafu a **uložit prezentaci pptx** pomocí Aspose.Slides pro Java. Klidně experimentujte s různými barevnými paletami, datovými sadami a úhly rotace, aby odpovídaly stylu vaší značky.

---

**Poslední aktualizace:** 2026-01-22  
**Testováno s:** Aspose.Slides 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}