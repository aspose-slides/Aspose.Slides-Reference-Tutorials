---
date: '2026-01-19'
description: Naučte se, jak přidat legendu do grafu v PowerPointu a vytvořit dynamické
  prstencové grafy v PowerPointu pomocí Aspose.Slides pro Javu. Podrobný návod krok
  za krokem s ukázkami kódu.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Přidání legendy do grafu PowerPoint – Vytvořte dynamické prstencové grafy pomocí
  Aspose.Slides pro Javu
url: /cs/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvořte dynamické prstencové grafy v PowerPointu pomocí Aspose.Slides pro Java

## Úvod
Přidání legendy do grafu v PowerPointu může obyčejnou vizualizaci proměnit v pří dílo. V tomto tutoriálu se naučíte **jak přidat legendu do grafu PowerPoint** při tvorbě dynamického prstencového grafu s Aspose.Slides pro Java. Provedeme vás inicializací prezentace, vložením grafu, konfigurací datových bodů, přizpůsobením popisků a nakonecizovat prezentaci pomocí Aspose.Slides pro Java  
- Krok‑za‑krokem průvodce přid do snímků  
- Konfiguraci datových bodů, **přidání popisků do grafu**, a přizpůsobení vlastností legendy  
- Uložení upravené prezentace s vysokou věrností  

Pojďme prozkoumat, jak můžete tyto funkce využít k vylepšení svých prezentací. Než začnete, ujistěte se, že máte základní znalosti syntaxe Java.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.Slides pro Java  
- **Mohu přidat legendu do prstencového grafu?** Ano – použijte nastavení legendy a řady grafDK ** Vzorek iteruje až 15 řad, ale můžete upravit podle potřeby  

## Co je prstencový graf a proč přidávat legendu?
Prstencový graf je varianta koláčového grafu s dutým středem, ideální pro zobrazování vztahů část‑celku při zachování prostoru pro další informace. Přidání legendy pomáhá divákům rychle přiřadit barvy ke kategoriím, čímž zvyšuje čitelnost –ad.

##- IDE, například IntelliJ IDEA nebo Eclipse.  
- Maven nebo Gradle pro správu závislostí.  
- Platná licence Aspose.Slides pro Java (k dispozici bezplatná zkušební verze).

## Nastavení Aspose.Slides pro Java
Zvolte formát závislosti, který odpovídá vašemu nástroji pro sestavování.

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

Pokud raději stáhnete JAR přímo, navštivte stránku [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence
Můžete začít s bezplatnou zkušební verzí a prozkoumat funkce Aspose.Slides. Pro delší používání zakupte licenci nebo požádejte o dočasnou licenci na [webu Aspose](https://purchase.aspose.com/temporary-license/). Postupujte podle poskytnutých instrukcí pro nastavení prostředí a inicializaci Aspose.Slides ve vaší aplikaci.

## Průvodce implementací
Níže je kompletní průchod. Každý blok kódu je předem vysvětlen, takže přesně víte, co se děje.

### Inicializace prezentace
Nejprve načtěte existující PPTX nebo vytvořte nový. Tento krok nastaví objekt prezentace, který bude obsahovat graf.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Přidání prstencového grafu
Nyní přidáme prstencový graf do snímku. `ChartType.Doughnut` vytvoří požadovanou vizualizaci a také vypneme výchozí legendu, protože ji později přizpůsobíme.

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

### Konfigurace datových bodů a popisků
Dále naplníme kategorie, přidáme datové body pro každou řadu a **přidáme popisky do grafu**. Přizpůsobení popisků také ukazuje, jak umístit popis podobný legendě vedle poslední řady v každé kategorii.

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

### Uložení prezentace
Nakonec změny uložíme do nového souboru PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Proč přidávat legendu do prstencového grafu v PowerPointu?
- **Přehlednost:** Legendy přiřazují barvy ke kategoriím, aniž by přeplňovaly oblast grafu.  
- **Škálovatelnost:** Když máte mnoho řad (jako ve výše uvedeném cyklu), legenda udržuje snímek čitelný.  
- ** Vylepšená legenda v kombinaci s vlastním popiskem dat vytváří prezentaci na úrovni korporátního standardu.

## Praktické aplikace
Prstencové grafy s legendou jsou ideální pro:
- **Finanční zprávy:** Zobrazte rozpis výdajů vedle legendy pro každé oddělení.  
- **Analizujte podíl naumů:** Představte odpovědi s výběrem více možností s jasnými názvy kategorií.

Data můžete načíst z databází, CSV souborů nebo webových služeb a předat je do cyklu pro generování grafů za běhu.

## Úvahy o výkonu
- Včas uvolňujte objekty `Presentation` (`pres.dispose()`) v dlouho běžících aplikacích.  
- Omezte počet řad, pokud zaznamenáte tlak na paměť; každá řada přidává režii.  
- Znovu použijte jediný `IChartDataWorkbook` při naplňování velkých datových sad.

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| Legenda není viditelná | `chart.setLegend(false)` ji vypíná. | Nastavte `chart.setLegend(true)` a přizpůsobte pozici. |
| Popisky se překrývají | Výchozí umístění popisků může kolidovat s otvorem prstence. | Upravit `lbl.setX()` / `lbl.setY()`().set.Solidose.Slides pro Java v komerčních aplikacích?**  
A: Ano, ale potřebujete platnou komerční licenci. Bezplatná zkušební verze je k dispozici pro hodnocení.

**Q: Jak povolím legendu poté, co byla vypnuta?**  
A: Zavolejte `chart.setLegend(true);` a volitelně nastavte její pozici pomocí `chart.getLegend().setPosition(LegendPosition.Right);`.

**Q: Je možné změnit stylA: Rozhodně. Použijte `chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(12);` a další vlastnosti písma.

**Q: Můžu svázat graf s daty v reálném čase z databáze?**  
A: Ano. Načtěte data pomocí JDBC, naplňte buňky sešitu uvnitř cyklů a graf bude odrážet aktuální hodnoty.

**Q: Podporuje Aspose.Slides i jiné typy grafů kromě prstencových?**  
A: Ano. Podporuje širokou škálu typů grafů – koláčové, sloupcové, čárové, rozptylové a další. Stačí nahradit `ChartType.Doughnut` požadovaným výčtem.

---

**Poslední aktualizace:** 2026-01-19  
**Testováno s:** Aspose.Slides 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}