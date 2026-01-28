---
date: '2026-01-17'
description: Naučte se, jak přidat řady do grafu a přizpůsobit sloupcové grafy se
  zásobníkem v .NET prezentacích pomocí Aspose.Slides pro Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Přidat řadu do grafu pomocí Aspose.Slides pro Java v .NET
url: /cs/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mistrovství přizpůsobení grafů v .NET prezentacích pomocí Aspose.Slides pro Java

## Úvod
V oblasti prezentací řízených dat jsou grafy nepostradatelnými nástroji, které proměňují surová čísla v poutavé vizuální příběhy. Když potřebujete **add series to chart** programově, zejména v souborech .NET prezentací, může se úkol zdát ohromující. Naštěstí **Aspose.Slides for Java** poskytuje výkonné jazykově nezávislé API, které vytváří a přizpůsobení grafů – i když je vaším cílovým formátem .NETPPTX.

V tomto tutoriálu se dozvíte, jak **add series to chart**, jak **how to add chart** typu sloupcového zásobníku a jak upravit vizuální aspekty, jako je šířka mezer. Na konci budete schopni generovat dynamické, daty bohaté snímky, které vypadají profesionálně a elegantně.

**Co se naučíte**
- Jak vytvořit prázdnou prezentaci pomocí Aspose.Slides
- Jak **přidat skládaný sloupcový graf** do snímku
- Jak **d series to chart** a definovat kategorii
- Jak naplnit datové tělo a upravit vizuální nastavení

Pojďme si připravit vaše vývojové prostředí.

## Rychlé odpovědi
- **Jaká je primární třída pro zahájení prezentace?** `Prezentace`
- **Která metoda přidá graf na snímek?** `slide.getShapes().addChart(...)`
- **Jak přidáte novou sérii?** `chart.getChartData().getSeries().add(...)`
- **Můžete změnit šířku mezery mezi pruhy?** Ano, pomocí `setGapWidth()` ve skupině sérií
- **Potřebuji licenci pro produkci?** Ano, je vyžadována platná licence Aspose.Slides for Java

## Co je to „přidat řadu do grafu“?
Přidání série do grafu znamená vložení nové kolekce dat, kterou graf vykreslí jako samostatný vizuální prvek (např. nový sloupec, čára nebo výseč). Každá série může mít vlastní sadu hodnot, barev a formátování, což vám umožní porovnávat více datových sad vedle sebe.

## Proč používat Aspose.Slides pro Javu k úpravě prezentací .NET?
- **Cross‑platform**: Napište Java kód jednou a cílové soubory PPTX použijí .NET aplikaci.
- **Žádné závislosti COM nebo Office**: Funguje na serverech, v CI pipelinech i v kontejnerech.
- **Rich chart API**: Podporuje více než 50 typů grafů, včetně vrstvených sloupcových grafů.

## Předpoklady
1. **Aspose.Slides for Java** knihovna (verze25.4 nebo novější).
2. Maven nebo Gradle build tool, nebo ruční stažení JAR souboru.
3. Základní znalost Javy a povědomí o struktuře PPTX.

## Nastavení Aspose.Slides pro Java
### Instalace Maven
Přidejte do souboru `pom.xml` následující závislost:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace Gradle
Do souboru `build.gradle` vložte tento řádek:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Případně si stáhněte nejnovější JAR soubor z oficiální stránky vydání: [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

**Získání licence**
Začněte s bezplatnou zkušební verzí stažením dočasné licence z [zde](https://purchase.aspose.com/temporary-license/). Pro produkční použití si zakupte plnou licenci, abyste odemkli všechny funkce.

## Podrobný návod k implementaci
Pod každým krokem najdete stručný úryvek kódu (nezměněný oproti původnímu tutoriálu) následovaný vysvětlením jeho funkce.

### Krok 1: Vytvoření prázdné prezentace
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*We start with a clean PPTX file, which gives us a canvas for adding charts.*

### Krok 2: Přidání skládaného sloupcového grafu na snímek
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*The `addChart` method creates a **add stacked column chart** and places it at the top‑left corner of the slide.*

### Krok 3: Přidání sérií do grafu (primární cíl)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Here we **add series to chart** – each call creates a new data series that will appear as a separate column group.*

### Krok 4: Přidání kategorií do grafu
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Categories act as the X‑axis labels, giving meaning to each column.*

### Krok 5: Naplnění dat sérií
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Data points give each series its numeric values, which the chart will render as bar heights.*

### Krok 6: Nastavení šířky mezery pro skupinu sérií grafu
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Adjusting the gap width improves readability, especially when many categories are present.*

## Běžné případy použití
- **Finanční reporting** – porovnání čtvrtletních příjmů napříč obchodními jednotkami.
- **Projektové dashboardy** – zobrazení procent dokončení úkolů na tým.
- **Marketingová analytika** – vizualizace výkonu kampaně vedle sebe.

## Tipy pro výkon
- **Opětovné použití objektu `Presentation`** při vytváření více grafů pro snížení režijních nákladů paměti.
- **Omezení počtu datových bodů** pouze na ty, které jsou potřeba pro vizuální příběh.
- **Odstranění objektů** (`presentation.dispose()`) po uložení do volných zdrojů.

## Často kladené otázky
**Otázka: Mohu přidat jiné typy grafů než skládaný sloupcový?**
Odpověď: Ano, Aspose.Slides podporuje čárové, koláčové, plošné a mnoho dalších typů grafů.

**Otázka: Potřebuji samostatnou licenci pro výstup .NET?**
Odpověď: Ne, stejná licence Java funguje pro všechny výstupní formáty, včetně souborů .NET PPTX.

**Otázka: Jak změním barevnou paletu grafu?**
Odpověď: Použijte `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` a nastavte požadovanou `Color`.

**Otázka: Je možné programově přidávat popisky dat?**
Odpověď: Rozhodně. Pro zobrazení hodnot volejte `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`.

**Otázka: Co když potřebuji aktualizovat existující prezentaci?**
Odpověď: Načtěte soubor s `new Presentation("existing.pptx")`, upravte graf a uložte jej zpět.

## Závěr
Nyní máte kompletního a komplexního průvodce, jak **přidat série do grafu**, vytvořit **skládaný sloupcový graf** a doladit jeho vzhled v prezentacích .NET pomocí Aspose.Slides pro Javu. Experimentujte s různými typy grafů, barvami a zdroji dat a vytvářejte poutavé vizuální zprávy, které zaujmou zúčastněné strany.

---

**Poslední aktualizace:** 17. 1. 2026
**Testováno s:** Aspose.Slides pro Javu 25.4 (jdk16)
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
