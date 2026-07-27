---
date: '2026-07-27'
description: Jak přizpůsobit graf pomocí Aspose.Slides pro Java. Naučte se vytvořit
  graf v PowerPointu, stylizovat rozptylové řady a efektivně ukládat prezentace.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Jak přizpůsobit graf s Aspose.Slides pro Java. Tento průvodce ukazuje,
  jak vytvořit graf v PowerPointu, stylizovat rozptylové body a exportovat prezentace.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Jak přizpůsobit graf: rozptylový graf Aspose v Javě'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Jak přizpůsobit graf: rozptylový graf Aspose v Javě'
url: /cs/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Přizpůsobení rozptylového grafu Aspose v Javě

V tomto tutoriálu objevíte **jak přizpůsobit graf** — konkrétně rozptylový graf — pomocí výkonné knihovny Aspose.Slides pro Javu. Provedeme vás nastavením projektu, vytvořením rozptylového grafu, úpravou typů sérií a značek a nakonec uložením prezentace. Na konci budete schopni programově generovat profesionálně vypadající rozptylové grafy a přizpůsobit každý vizuální detail tak, aby odpovídal vaší značce nebo požadavkům na reportování.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Slides for Java (v25.4+).  
- **Která verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Mohu změnit tvary značek?** Ano – použijte `MarkerStyleType` k výběru hvězd, kruhů atd.  
- **Jak soubor uložit?** Zavolejte `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Je licence vyžadována?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je potřeba komerční licence.

## Jak přizpůsobit graf v Javě pomocí Aspose.Slides?
`Presentation` je třída Aspose.Slides, která představuje celý soubor PowerPoint v paměti. Načtěte novou `Presentation`, přidejte rozptylový graf na první snímek, nakonfigurujte série a styly značek a poté zavolejte `save`. Tento jednorázový postup vytvoří plně stylizovaný graf během několika řádků Java kódu, připravený k zařazení do jakékoli PowerPoint prezentace.

## Co znamená „přizpůsobit rozptylový graf aspose“?
Přizpůsobení rozptylového grafu pomocí Aspose znamená programově definovat data grafu, jeho vzhled a chování — vše od souřadnic bodů po symboly značek — bez ručního otevírání PowerPointu. Tento přístup je ideální pro automatizované reportování, prezentace řízené daty nebo jakýkoli scénář, kde potřebujete opakovatelnou vizualizaci vysoké kvality.

## Proč přizpůsobovat rozptylové grafy pomocí Aspose.Slides?
Aspose.Slides poskytuje vývojářům plnou programovou kontrolu nad vzhledem grafu, což umožňuje automatické vytváření vizualizací vysoké kvality, bezproblémovou integraci do reportovacích pipeline a možnost přizpůsobit každý vizuální prvek bez ručního otevírání PowerPointu, což šetří čas a zajišťuje konzistenci napříč prezentacemi.

- **Plná kontrola** – upravujte typy sérií, styly značek, barvy a další pomocí Java kódu.  
- **Automatizace** – generujte během běhu desítky grafů pro dashboardy nebo hromadné reporty.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu, bez nutnosti instalace Office.  
- **Výkon** – lehké API, které zpracovává **150+ typů grafů** a zvládá prezentace s stovkami stránek, aniž by načítalo celý soubor do paměti.

## Předpoklady

Abyste mohli postupovat, ujistěte se, že máte:

- **Aspose.Slides for Java** (v25.4 nebo novější).  
- **Java Development Kit (JDK)** 8 + nainstalovaný.  
- Maven nebo Gradle pro správu závislostí (nebo můžete JAR stáhnout ručně).  
- Základní znalost Javy a obeznámení s vaším zvoleným nástrojem pro sestavení.

## Nastavení Aspose.Slides pro Javu

Integrujte knihovnu do svého projektu pomocí jedné z níže uvedených metod.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Nebo si stáhněte nejnovější verzi z [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Získání licence
- **Free Trial** – 30‑denní zkušební verze.  
- **Temporary License** – prodloužené testovací období.  
- **Full License** – použití v produkci s prémiovou podporou.

## Průvodce krok za krokem pro přizpůsobení rozptylového grafu Aspose

### 1️⃣ Připravte složku pro soubory prezentace
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Proč je to důležité:* Zajištění existence výstupní složky zabraňuje `FileNotFoundException` při pozdějším ukládání PPTX.

### 2️⃣ Vytvořte novou prezentaci a získejte první snímek
`Presentation` představuje dokument PowerPoint a poskytuje přístup ke snímkům a tvarům. Třída `Presentation` představuje celý soubor PowerPoint v paměti.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Přidejte rozptylový graf s hladkými čarami
`ChartType.ScatterWithSmoothLines` vytvoří rozptylový graf, kde jsou body spojeny hladkými čarami.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Vymažte výchozí série a přidejte vlastní
`IChartSeries` představuje datovou sérii v grafu.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Naplňte první sérii datovými body
`addDataPointForScatterSeries` přidá jeden X‑Y bod do rozptylové série.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Přizpůsobte typ série a vzhled značky
`Marker` řídí vizuální symbol používaný pro každý datový bod v sérii grafu.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Uložte prezentaci
`save` zapíše prezentaci do souboru ve specifikovaném formátu.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Běžné případy použití přizpůsobených rozptylových grafů
- **Finanční dashboardy** – vykreslete cenu akcie vůči objemu.  
- **Vědecký výzkum** – zobrazte experimentální měření s chybovými značkami.  
- **Projektové řízení** – porovnejte plánovaný a skutečný úsilí napříč úkoly.

## Tipy pro výkon
- Zavolejte `pres.dispose()` po uložení pro uvolnění nativní paměti.  
- Pro velké datové sady nejprve naplňte sešit a poté svázat sérii, aby se předešlo opakovaným obnovám UI.  
- Znovu použijte jedinou instanci `IChartDataWorkbook` při přidávání mnoha sérií, aby se udržovala nízká spotřeba paměti.

## Často kladené otázky

**Q: Jak změním barvu značek?**  
A: Použijte `series.getMarker().getFillFormat().setFillColor(Color)`, kde `Color` je instance `java.awt.Color`, např. `Color.RED`.

**Q: Můžu přidat více než dvě série do rozptylového grafu?**  
A: Ano. Zavolejte `chart.getChartData().getSeries().add(...)` pro každou další sérii a podle toho naplňte její body.

**Q: Je možné nastavit vlastní legendu pro každou sérii?**  
A: Rozhodně. Po vytvoření série zavolejte `series.getLegend().setText("Your Legend Text")` pro přepsání výchozího názvu.

**Q: Jak mohu exportovat graf jako obrázek místo PPTX?**  
A: Zavolejte `chart.getImage().save("chart.png", ImageFormat.Png)` po konfiguraci grafu. Tím vznikne samostatný PNG soubor.

**Q: Co když potřebuji animovat rozptylové body?**  
A: Aspose.Slides podporuje animační efekty. Použijte `chart.getTimeline().getMainSequence().addEffect(...)` pro přidání vstupních nebo zdůrazňovacích animací do grafu nebo jednotlivých sérií.

---

**Poslední aktualizace:** 2026-07-27  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit a přizpůsobit PowerPoint grafy v Javě pomocí Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Jak vytvořit bublinový graf v PowerPointu pomocí Aspose.Slides pro Javu (Tutoriál)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Vytvořit a přizpůsobit grafy s trendovými čarami v Aspose.Slides pro Javu](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}