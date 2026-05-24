---
date: '2026-02-24'
description: Naučte se, jak přizpůsobit rozptylový graf pomocí Aspose.Slides pro Javu.
  Tento průvodce vás provede vytvářením, stylizací a ukládáním dynamických rozptylových
  grafů ve vašich prezentacích.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Přizpůsobení rozptylového grafu Aspose v Javě
url: /cs/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Přizpůsobení rozptylového grafu Aspose v Javě

V tomto tutoriálu se naučíte, jak **přizpůsobit rozptylový graf Aspose** pomocí výkonné knihovny Aspose.Slides pro Java. Provedeme vás nastavením projektu, vytvořením rozptylového grafu, úpravou typů řad a značek a nakonec uložením prezentace. Na konci budete schopni programově generovat profesionálně vypadající rozptylové grafy a přizpůsobit každý vizuální detail tak, aby odpovídal vaší značce nebo požadavkům na reportování.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Slides for Java (v25.4+).  
- **Která verze Javy je podporována?** JDK 8 nebo vyšší.  
- **Mohu měnit tvary značek?** Ano – použijte `MarkerStyleType` pro výběr hvězd, kruhů atd.  
- **Jak soubor uložit?** Zavolejte `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Je licence vyžadována?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je potřeba komerční licence.

## Co znamená „přizpůsobit rozptylový graf Aspose“?
Přizpůsobení rozptylového grafu pomocí Aspose znamená programově definovat data grafu, jeho vzhled a chování — vše od souřadnic bodů po symboly značek — bez ručního otevírání PowerPointu. Tento přístup je ideální pro automatizované reportování, prezentace řízené daty nebo jakýkoli scénář, kde potřebujete opakovatelné vizualizace vysoké kvality.

## Proč přizpůsobovat rozptylové grafy pomocí Aspose.Slides?
- **Plná kontrola** – upravujte typy řad, styly značek, barvy a další pomocí Java kódu.  
- **Automatizace** – generujte desítky grafů za běhu pro dashboardy nebo hromadné reporty.  
- **Cross‑platform** – funguje na libovolném OS, který podporuje Javu, bez nutnosti instalace Office.  
- **Výkon** – lehké API, které efektivně zpracovává velké datové sady.

## Předpoklady

Abyste mohli postupovat, ujistěte se, že máte:

- **Aspose.Slides for Java** (v25.4 nebo novější).  
- **Java Development Kit (JDK)** 8 + nainstalovaný.  
- Maven nebo Gradle pro správu závislostí (nebo můžete JAR stáhnout ručně).  
- Základní znalosti Javy a orientaci ve vámi zvoleném nástroji pro sestavování.

## Nastavení Aspose.Slides pro Java

Integrujte knihovnu do svého projektu pomocí jedné z metod níže.

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
- **Free Trial** – 30‑denní zkušební období.  
- **Temporary License** – prodloužené testovací období.  
- **Full License** – produkční použití s prémiovou podporou.

## Průvodce krok za krokem k přizpůsobení rozptylového grafu Aspose

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
*Proč je to důležité:* Zajištění existence výstupní složky zabraňuje `FileNotFoundException` při následném ukládání PPTX.

### 2️⃣ Vytvořte novou prezentaci a získejte první snímek
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Čerstvá `Presentation` vám poskytne čisté plátno; první snímek je místem, kam graf umístíme.

### 3️⃣ Přidejte rozptylový graf s hladkými čarami
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` vytváří rozptylový graf s hladkými čarami, ideální pro vizualizaci trendů.

### 4️⃣ Vymažte výchozí řady a přidejte vlastní
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
Odstranění výchozích řad vám dává plnou kontrolu nad zobrazovanými daty.

### 5️⃣ Naplňte první řadu datovými body
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` přijímá buňku s X‑hodnotou a buňku s Y‑hodnotou a postupně buduje body rozptylového grafu.

### 6️⃣ Přizpůsobte typ řady a vzhled značek
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
Zde **přizpůsobujeme rozptylový graf Aspose** přepnutím na přímé čáry, zvětšením značek a výběrem odlišných symbolů (hvězda vs. kruh) pro lepší čitelnost.

### 7️⃣ Uložte prezentaci
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Uložení jako `Pptx` zachová všechna přizpůsobení grafu a připraví soubor ke sdílení nebo dalším úpravám.

## Běžné případy použití přizpůsobených rozptylových grafů
- **Finanční dashboardy** – vykreslení ceny akcie vůči objemu.  
- **Vědecký výzkum** – zobrazení experimentálních měření s chybovými značkami.  
- **Projektové řízení** – srovnání plánovaného a skutečného úsilí napříč úkoly.  

## Tipy pro výkon
- Po uložení uvolněte objekt `Presentation` (`pres.dispose()`) a tím uvolníte nativní zdroje.  
- U velkých datových sad nejprve naplňte sešit a pak svázat řadu, aby se předešlo opakovaným obnovám UI.  
- Při přidávání mnoha řad znovu použijte jedinou instanci `IChartDataWorkbook`.

## Často kladené otázky

### Jak změnit barvu značek?
Použijte `series.getMarker().getFillFormat().setFillColor(Color)`, kde `Color` je instance `java.awt.Color` (např. `Color.RED`).

### Mohu do rozptylového grafu přidat více než dvě řady?
Ano. Opakujte volání `chart.getChartData().getSeries().add(...)` pro každou další řadu a podle toho naplňte její datové body.

### Je možné nastavit vlastní legendu pro každou řadu?
Ano. Po vytvoření řady zavolejte `series.getLegend().setText("Your Legend Text")` a přepište tak výchozí název.

### Jak mohu exportovat graf jako obrázek místo PPTX?
Zavolejte `chart.getImage().save("chart.png", ImageFormat.Png)` po konfiguraci grafu. Získáte tak samostatný PNG soubor.

### Co když potřebuji animovat body rozptylového grafu?
Aspose.Slides podporuje animační efekty. Použijte `chart.getTimeline().getMainSequence().addEffect(...)` pro přidání vstupních nebo zdůrazňovacích animací k grafu nebo jednotlivým řadám.

---

**Poslední aktualizace:** 2026-02-24  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}