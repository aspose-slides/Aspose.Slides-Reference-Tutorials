---
date: '2026-03-07'
description: Naučte se, jak vytvořit prstencový graf v Javě pomocí Aspose.Slides.
  Tento průvodce krok za krokem pokrývá nastavení závislosti Maven Aspose Slides,
  konfiguraci grafu a ukládání prezentací.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Vytvořte prstencový graf v Javě s průvodcem Aspose.Slides
url: /cs/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvoření prstencového grafu v Javě s Aspose.Slides průvodcem

## Úvod

Vytvoření **doughnut chart** programově může proměnit surová čísla v poutavý vizuál, který okamžitě vypráví příběh. V Javě **Aspose.Slides** tento proces zjednodušuje a umožňuje generovat grafy připravené do prezentace, aniž byste museli otevírat PowerPoint. V tomto tutoriálu se naučíte, jak **create doughnut chart java** krok za krokem – od nastavení Maven závislosti Aspose Slides po přizpůsobení sérií, kategorií a nakonec uložení prezentace.

Na konci tohoto průvodce budete schopni vložit dynamické prstencové grafy do libovolného souboru PPTX, ideální pro zprávy, dashboardy nebo automatizované sady snímků.

### Rychlé odpovědi
- **Jaká knihovna se používá?** Aspose.Slides for Java  
- **Hlavní úkol?** Create doughnut chart java v souboru PPTX  
- **Jak přidat knihovnu?** Použijte Maven Aspose Slides dependency (nebo Gradle)  
- **Minimální verze Javy?** JDK 16 nebo vyšší  
- **Mohu přizpůsobit barvy a popisky?** Ano, API poskytuje plnou kontrolu formátování  

## Co je prstencový graf a proč jej používat?

Prstencový graf je variací koláčového grafu s prázdným středem, který umožňuje zobrazit více datových sérií v soustředných kruzích. To jej činí ideálním pro porovnání částí celku napříč několika kategoriemi – například prodeje podle regionu během několika čtvrtletí nebo rozdělení rozpočtu mezi oddělení.

## Proč použít Aspose.Slides pro Java?

- **Není vyžadována instalace Office** – generujte soubory PPTX na jakémkoli serveru.  
- **Bohaté API** – plná kontrola nad typy grafů, datovými body a stylováním.  
- **Vysoký výkon** – optimalizováno pro velké prezentace.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS.

## Požadavky

- **Požadované knihovny:**  
  - Aspose.Slides for Java verze 25.4 nebo novější.  

- **Nastavení prostředí:**  
  - JDK 16 nebo vyšší.  
  - Vaše oblíbené IDE (IntelliJ IDEA, Eclipse, NetBeans, atd.).  

- **Předpoklady znalostí:**  
  - Základy programování v Javě.  
  - Znalost Maven nebo Gradle pro správu závislostí.

## Maven závislost Aspose Slides

Přidejte následující Maven závislost do souboru `pom.xml`. Toto je **maven aspose slides dependency**, kterou potřebujete k načtení knihovny do projektu.

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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Můžete také stáhnout JAR přímo z oficiální stránky vydání:  
[Vydání Aspose.Slides pro Java](https://releases.aspose.com/slides/java/)

### Získání licence

Pro odstranění vodotisku hodnocení a odemčení plného souboru funkcí:

- **Bezplatná zkušební verze** – začněte s dočasnou licencí.  
- **Dočasná licence** – požádejte o ni na [Aspose webu](https://purchase.aspose.com/temporary-license/).  
- **Komerční licence** – zakupte pro produkční použití.

Aplikujte licenci ve svém kódu:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Průvodce implementací

### Inicializace prezentace a přidání prstencového grafu

Nejprve vytvořte nebo načtěte prezentaci a přidejte prstencový graf na první snímek.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurace sešitu dat grafu a vymazání existujících dat

Dále získejte sešit, který podporuje graf, a vymažte všechny výchozí série nebo kategorie.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Přidání sérií do grafu

Nyní přidáme až 15 sérií. Každá série může být přizpůsobena – zde nastavujeme explozi, velikost díry prstence a úhel první výseče.

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

### Přidání kategorií a datových bodů

Vytvoříme 15 kategorií a naplníme každou sérii datovým bodem. Poslední série získá speciální formátování popisků.

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

### Uložení prezentace

Nakonec zapište aktualizovanou prezentaci na disk.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Časté problémy a řešení

- **Licence nebyla nalezena** – Ověřte, že cesta k `license.lic` je správná a soubor je čitelný.  
- **Graf je prázdný** – Ujistěte se, že jste před přidáním nových sérií/kategorií vymazali existující.  
- **Nesprávné barvy** – Zkontrolujte, že `FillType.Solid` je nastaven pro výplň i formát čáry.  
- **Výkon při mnoha sériích** – Omezte počet sérií/kategorií nebo znovu použijte buňky sešitu.

## Často kladené otázky

**Q: Mohu vygenerovat prstencový graf bez předem existujícího souboru PPTX?**  
A: Ano, vytvořte instancí `new Presentation()` a začněte s prázdnou sadou snímků.

**Q: Podporuje Aspose.Slides export do PDF?**  
A: Rozhodně. Po vytvoření grafu zavolejte `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Jak změním velikost díry prstence?**  
A: Použijte `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, kde hodnota je 0‑100.

**Q: Je možné přidat datové popisky ke všem sériím, ne jen k poslední?**  
A: Ano, přesuňte blok formátování popisků mimo podmínku `if (i == ...)` a aplikujte jej na každý `dataPoint`.

**Q: Jaké verze Javy jsou podporovány?**  
A: Aspose.Slides 25.4 podporuje JDK 16 a novější. Starší JDK vyžadují odpovídající klasifikátor.

---

**Poslední aktualizace:** 2026-03-07  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}