---
date: '2026-02-17'
description: Naučte se, jak vytvořit prstencový graf v PowerPointu pomocí Aspose.Slides
  pro Javu a přidávat datové body grafu programově. Postupujte podle jednoduchých
  kroků a ukázek kódu.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Vytvořte prstencový graf v PowerPointu s Aspose.Slides pro Javu
url: /cs/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvoření prstencového grafu v PowerPointu pomocí Aspose.Slides pro Java

## Úvod
Vytváření poutavých prezentací často vyžaduje více než jen text a obrázky; grafy mohou výrazně zlepšit vyprávění tím, že efektivně vizualizují data. Nicméně mnoho vývojářů má potíže integrovat dynamické funkce grafů do souborů PowerPoint programově. Tento tutoriál ukazuje, jak **vytvořit prstencový graf v PowerPointu** pomocí Aspose.Slides pro Java – výkonného nástroje, který kombinuje flexibilitu a snadné použití.

**Co se naučíte:**
- Jak inicializovat prezentaci pomocí Aspose.Slides pro Java
- Postupný průvodce přidáním prstencového grafu do vašich snímků
- Konfigurace datových bodů a přizpůsobení vlastností popisků
- Uložení upravené prezentace s vysokou věrností

Pojďme prozkoumat, jak můžete využít tyto funkce ke zlepšení svých prezentací. Před začátkem se ujistěte, že máte základní znalosti programování v Javě.

## Rychlé odpovědi
- **Jaká knihovna vytváří prstencový graf v PowerPointu?** Aspose.Slides pro Java
- **Mohu přidávat datové body grafu programově?** Ano, pomocí API grafu
- **Potřebuji licenci pro produkci?** Je vyžadována platná licence Aspose.Slides
- **Které verze Javy jsou podporovány?** Java 8 a novější (zobrazen klasifikátor JDK 16)
- **Kolik sérií mohu přidat?** Příklad přidává až 15 sérií, ale můžete upravit podle potřeby

## Co je prstencový graf v PowerPointu?
Prstencový graf je variací koláčového grafu s dutým středem, který umožňuje zobrazit více datových sérií v kompaktním, vizuálně atraktivním způsobu. Je ideální pro zobrazování vztahů část‑celku při zachování čistého designu.

## Proč použít Aspose.Slides pro Java k vytvoření prstencových grafů?
- **Plná kontrola** nad vzhledem grafu, daty a rozvržením bez otevření PowerPointu
- **Žádná COM interop** – funguje na jakékoli platformě podporující Javu
- **Vysoký výkon** při generování velkých prezentací nebo integraci s webovými službami
- **Bohatá přizpůsobení** jako je výbuch, velikost díry, úhly výsečů a formátování popisků

## Požadavky
- Základní znalost programování v Javě.
- IDE jako IntelliJ IDEA nebo Eclipse.
- Maven nebo Gradle pro správu závislostí.
- Platná licence Aspose.Slides pro Java (k dispozici bezplatná zkušební verze).

## Nastavení Aspose.Slides pro Java
Vyberte správce závislostí, který vyhovuje vašemu projektu.

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

Pokud raději stahujete přímo, navštivte stránku [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Pro delší používání zakupte licenci nebo požádejte o dočasnou na [webu Aspose](https://purchase.aspose.com/temporary-license/). Postupujte podle poskytnutých instrukcí pro nastavení prostředí a inicializaci Aspose.Slides ve vaší aplikaci.

## Jak vytvořit prstencový graf v PowerPointu pomocí Aspose.Slides pro Java
Níže je kompletní, krok za krokem průvodce. Každý blok kódu je vysvětlen těsně před ním, takže přesně víte, co se děje.

### Krok 1: Inicializace prezentace
Nejprve načtěte existující PPTX nebo vytvořte nový. Tím připravíte kolekci snímků pro další úpravy.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Krok 2: Přidání prstencového grafu na snímek
Přidáme tvar grafu, vymažeme jakékoli výchozí série/kategorie a nastavíme základní vizuální vlastnosti.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Krok 3: Přidání datových bodů do grafu a přizpůsobení popisků
Zde naplníme kategorie, přidáme datové body pro každou sérii a doladíme vzhled popisků. Zde vstupuje do hry klíčové slovo **add chart data points**.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Krok 4: Uložení aktualizované prezentace
Nakonec uložte změny do nového souboru PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Praktické aplikace
- **Finanční zprávy:** Vizualizace rozdělení rozpočtu nebo výdajů.
- **Analýza trhu:** Zobrazení podílu na trhu mezi konkurenty.
- **Výsledky průzkumu:** Prezentace kategoriálních dat průzkumu v kompaktní formě.
- **Generování dashboardu:** Kombinace s databázovými dotazy pro tvorbu snímků s živou aktualizací.

## Úvahy o výkonu
- **Uvolnění zdrojů:** Zavolejte `pres.dispose()`, když skončíte, aby se uvolnila nativní paměť.
- **Omezení počtu grafů:** Přidání stovek grafů může zvýšit využití paměti; v případě potřeby zpracovávejte po dávkách.
- **Použití streamování:** Pro obrovské datové sady naplňte sešit přímo ze streamů místo pole v paměti.

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Graf se zobrazuje prázdně** | Buňky dat nejsou správně naplněny | Ověřte, že `workBook.getCell(...)` odkazuje na správné řádky/sloupce. |
| **Popisky se překrývají** | Příliš mnoho kategorií v omezeném prostoru | Zvyšte `DoughnutHoleSize` nebo upravte `FirstSliceAngle`. |
| **OutOfMemoryError** | Velké prezentace bez uvolnění zdrojů | Zavolejte `pres.dispose()` po uložení a zvažte zvýšení velikosti haldy JVM. |

## Často kladené otázky

**Q: Mohu použít Aspose.Slides pro Java v komerčních aplikacích?**  
A: Ano, ale potřebujete platnou komerční licenci. Bezplatná zkušební verze je k dispozici pro vyhodnocení.

**Q: Jak přidat více než 15 sérií?**  
A: Zvyšte limit smyčky v kroku „Add Doughnut Chart“ a ujistěte se, že váš datový sešit má dostatek řádků.

**Q: Je možné změnit velikost díry prstence po vytvoření?**  
A: Ano, zavolejte `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` kdykoli před uložením.

**Q: Mohu exportovat graf jako obrázek místo PPTX?**  
A: Rozhodně. Použijte `chart.getImage()` a uložte vrácený `java.awt.image.BufferedImage` v požadovaném formátu.

**Q: Podporuje Aspose.Slides animované grafy?**  
A: Animaci lze přidat pomocí API `ISlide.getTimeline()`, i když to přesahuje rozsah tohoto tutoriálu.

## Závěr
Nyní máte kompletní, připravenou metodu pro **vytvoření prstencových grafů v PowerPointu** pomocí Aspose.Slides pro Java, včetně toho, jak **přidávat datové body do grafu**, přizpůsobovat popisky a řešit výkonové úvahy. Experimentujte s různými barvami, zdroji dat a typy grafů, aby vaše prezentace skutečně vynikly.

---

**Poslední aktualizace:** 2026-02-17  
**Testováno s:** Aspose.Slides pro Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}