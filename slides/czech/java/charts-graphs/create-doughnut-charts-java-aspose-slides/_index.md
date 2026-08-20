---
date: '2026-08-16'
description: Naučte se, jak přidat prstencové grafy v Javě pomocí Aspose.Slides. Tento
  průvodce krok za krokem pokrývá nastavení závislosti Maven, konfiguraci grafu, barvy,
  popisky a uložení PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Jak přidat prstencové grafy v Javě pomocí Aspose.Slides. Postupujte
  podle tohoto průvodce a nastavte Maven, přizpůsobte barvy, popisky a vytvořte soubory
  PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Jak přidat prstencový graf v Javě s Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Jak přidat prstencový graf v Javě s Aspose.Slides
url: /cs/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak přidat prstencový graf v Javě s Aspose.Slides

## Úvod

Vytvoření **doughnut chart** programově může proměnit surová čísla v poutavý vizuál, který okamžitě vypráví příběh. V Javě **Aspose.Slides** tento proces zjednodušuje a umožňuje generovat grafy připravené do prezentace, aniž byste museli otevírat PowerPoint. V tomto tutoriálu se naučíte **jak přidat doughnut** grafy do souboru PPTX krok za krokem – od nastavení Maven závislosti Aspose Slides po přizpůsobení sérií, kategorií, barev a popisků a nakonec uložení prezentace.

Na konci tohoto průvodce budete schopni vložit dynamické doughnut grafy do libovolného souboru PPTX, ideální pro zprávy, dashboardy nebo automatizované sady snímků.

### Rychlé odpovědi
- **What library is used?** Aspose.Slides for Java  
- **Primary task?** Add a doughnut chart in a PPTX file  
- **How to add the library?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java version?** JDK 16 or higher  
- **Can I customize colors and labels?** Yes, the API provides full formatting control  

## Co je doughnut chart a proč jej použít?

Doughnut chart je variací koláčového grafu s prázdným středem, což umožňuje zobrazit více datových sérií jako soustředné kruhy. **Vizualizuje části celku napříč několika kategoriemi a zároveň zachovává prostor pro další informace ve středu.** To jej činí ideálním pro porovnání prodeje podle regionů během několika čtvrtletí, rozdělení rozpočtu mezi odděleními nebo jakýkoli scénář, kde je potřeba zobrazit hierarchická podílová data.

## Proč použít Aspose.Slides pro Javu?

Můžete přidat doughnut chart bez instalace Microsoft Office a knihovna zpracovává **více než 50 + vstupních a výstupních formátů** a zároveň zvládá prezentace přesahující 500 snímků. Aspose.Slides poskytuje **až 3× rychlejší vykreslování** ve srovnání s nativní automatizací Office na stejném hardware a funguje na Windows, Linuxu i macOS. Tyto kvantifikované výhody znamenají, že můžete generovat velké sady snímků na serverech bez grafického rozhraní s předvídatelným výkonem.

## Požadavky

- **Required libraries**  
  - Aspose.Slides for Java 25.4 nebo novější (knihovna, která umožňuje přidávat doughnut grafy).  

- **Environment**  
  - JDK 16 nebo vyšší nainstalovaný na vašem počítači.  
  - IDE jako IntelliJ IDEA, Eclipse nebo NetBeans.  

- **Knowledge**  
  - Základní syntaxe Javy a objektově orientované koncepty.  
  - Znalost Maven nebo Gradle pro správu závislostí.  

## Maven závislost Aspose Slides

Přidejte následující Maven závislost do vašeho `pom.xml`. Toto je **maven aspose slides dependency**, kterou potřebujete pro stažení knihovny do projektu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Pokud dáváte přednost Gradle, použijte níže uvedený ekvivalentní úryvek.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Můžete také stáhnout JAR přímo z oficiální stránky vydání:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Získání licence

Pro odstranění testovacího vodoznaku a odemčení plné sady funkcí:

- **Free trial** – začněte s dočasnou licencí.  
- **Temporary license** – požádejte o ni na [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – zakupte pro produkční použití.

Apply the license in your code:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Průvodce implementací

### Inicializace prezentace a přidání doughnut grafu

Presentation je třída Aspose.Slides, která představuje prezentaci PowerPoint.  
Načtěte existující PPTX nebo vytvořte nový objekt `Presentation`, poté přidejte doughnut graf na první snímek.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Konfigurace pracovního sešitu grafu a vymazání existujících dat

Workbook je interní tabulka, která ukládá data grafu.  
Získejte workbook, který graf podporuje, a poté vymažte všechny výchozí série nebo kategorie, abyste mohli začít s čistým štítem.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Přidání sérií do grafu

Série představuje kolekci datových bodů vykreslených v grafu.  
Můžete přidat až 15 sérií. Každá série může být přizpůsobena – zde nastavujeme explozi, velikost středu doughnut a úhel prvního výseku.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Přidání kategorií a datových bodů

Kategorie jsou popisky pro každý datový bod podél osy grafu.  
Vytvořte 15 kategorií a naplňte každou sérii datovým bodem. Poslední série získá speciální formátování popisků.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Přizpůsobení barev a datových popisků

`FillType.Solid` určuje plnou barvu výplně pro prvky grafu.  
Nastavte plnou barvu výplně pro každou sérii a povolte datové popisky. Pro poslední sérii také měníme barvu písma popisku.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Uložení prezentace

`save` zapíše prezentaci do souboru ve zvoleném formátu.  
Uložte aktualizovanou prezentaci na disk ve formátu PPTX nebo exportujte do PDF, pokud je to potřeba.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Časté problémy a řešení

- **License not found** – Ověřte, že cesta k `license.lic` je správná a soubor je čitelný.  
- **Chart appears blank** – Ujistěte se, že jste před přidáním nových vymazali existující série/kategorie.  
- **Incorrect colors** – Potvrďte, že `FillType.Solid` je nastaven pro výplň i formát čáry.  
- **Performance with many series** – Omezte počet sérií/kategorií nebo znovu použijte buňky workbooku, aby byl paměťový výdej pod kontrolou.  

## Často kladené otázky

**Q: Mohu vygenerovat doughnut chart bez předem existujícího souboru PPTX?**  
A: Ano, vytvořte instancí `new Presentation()` a začněte s prázdnou sadou snímků, poté přidejte graf podle výše uvedeného postupu.

**Q: Podporuje Aspose.Slides export do PDF?**  
A: Rozhodně. Po vytvoření grafu zavolejte `pres.save("output.pdf", SaveFormat.Pdf);` a získáte PDF verzi snímku.

**Q: Jak změním velikost středu doughnut?**  
A: Použijte `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, kde `value` je v rozmezí 0 – 100.

**Q: Je možné přidat datové popisky ke všem sériím, ne jen k poslední?**  
A: Ano, přesuňte blok formátování popisků mimo podmínku `if (i == ...)` a aplikujte jej na každý `dataPoint`.

**Q: Jaké verze Javy jsou podporovány?**  
A: Aspose.Slides 25.4 podporuje JDK 16 a novější. Starší JDK vyžadují odpovídající classifier v Maven závislosti.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Související tutoriály

- [Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak přizpůsobit barvy koláčových grafů v Javě s Aspose.Slides – Kompletní průvodce](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animovat kategorie grafu v PowerPointu pomocí Aspose.Slides pro Java | Průvodce krok za krokem](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}