---
"date": "2025-04-17"
"description": "Naučte se, jak vytvářet úžasné prstencové grafy v Javě pomocí Aspose.Slides. Tato komplexní příručka zahrnuje inicializaci, konfiguraci dat a ukládání prezentací."
"title": "Vytváření prstencových grafů v Javě pomocí Aspose.Slides – Komplexní průvodce"
"url": "/cs/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvořte prstencové grafy v Javě pomocí Aspose.Slides: Podrobný návod

## Zavedení

dnešním prostředí založeném na datech je efektivní vizualizace informací klíčem ke zlepšení porozumění a zapojení. I když se vytváření profesionálních grafů programově může zdát náročné, zejména v Javě, tato příručka vás provede používáním Aspose.Slides pro Javu k snadnému vytváření prstencových grafů.

Dodržením těchto kroků získají vývojáři praktické zkušenosti s manipulací se snímky prezentací a bezproblémovou integrací vizualizace dat.

**Klíčové poznatky:**
- Inicializujte objekt Presentation pomocí Aspose.Slides v Javě.
- Konfigurujte data grafu a spravujte existující řady nebo kategorie.
- Přidejte a upravte řady a kategorie pro své grafy.
- Efektivně formátovat a zobrazovat datové body.
- Snadno uložte svou prezentaci v různých formátech.

Než se pustíte do implementace, ujistěte se, že máte vše potřebné k zahájení.

## Předpoklady

Abyste mohli postupovat podle tohoto tutoriálu, ujistěte se, že máte:

- **Požadované knihovny:**
  - Aspose.Slides pro Javu verze 25.4 nebo novější.
  
- **Nastavení prostředí:**
  - JDK 16 nebo vyšší nainstalovaný na vašem systému.
  - IDE jako IntelliJ IDEA, Eclipse nebo NetBeans.

- **Předpoklady znalostí:**
  - Základní znalost konceptů programování v Javě.
  - Znalost správy závislostí v projektech Maven nebo Gradle.

## Nastavení Aspose.Slides pro Javu

Chcete-li integrovat Aspose.Slides do svého projektu, postupujte podle těchto kroků v závislosti na vašem nástroji pro sestavení:

**Nastavení Mavenu:**
Přidejte do svého `pom.xml` soubor:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Nastavení Gradle:**
Zahrňte do svého `build.gradle` soubor:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Přímé stažení:**
Nebo si stáhněte nejnovější verzi přímo z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

### Získání licence

Použití Aspose.Slides bez omezení vyhodnocování:
- **Bezplatná zkušební verze:** Začněte s dočasnou licencí a prozkoumejte všechny funkce.
- **Dočasná licence:** Získejte jeden prostřednictvím [Webové stránky Aspose](https://purchase.aspose.com/temporary-license/).
- **Nákup:** Zvažte nákup pro trvalé používání.

Použijte licenci ve své aplikaci Java pomocí:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Průvodce implementací

### Inicializace prezentace a grafu

#### Přehled
Začněte inicializací prezentačního objektu a přidáním prstencového grafu na první snímek.

**Krok 1: Inicializace prezentace**
Načtěte existující soubor PPTX nebo vytvořte nový:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Krok 2: Přidání prstencového grafu**
Vytvořte graf na prvním snímku na zadaných souřadnicích:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurace sešitu dat grafů a vymazání existujících řad/kategorií

#### Přehled
Nakonfigurujte sešit s daty grafu a odeberte všechny existující řady nebo kategorie.

**Krok 1: Přístup k sešitu s daty grafů**
Načtěte sešit propojený s vaším grafem:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Krok 2: Vymazání existujících sérií a kategorií**
Ujistěte se, že neexistují žádné zbytkové datové body:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Přidání série do grafu

#### Přehled
Naplňte svůj graf více sériemi, z nichž každá má upravený vzhled a chování.

**Krok 1: Iterativní přidání sérií**
Procházejte indexy pro přidání sérií:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Přizpůsobte si sérii
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Přidávání kategorií a datových bodů do grafu

#### Přehled
Nakonfigurujte kategorie a přidejte datové body se specifickým formátováním pro popisky.

**Krok 1: Přidání kategorií**
Procházení indexů pro každou kategorii:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Krok 2: Přidání datových bodů do každé série**
Projděte si každou sérii pro aktuální kategorii:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Nastavení formátu datových bodů
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formátování popisků pro poslední sérii
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

        // Úprava možností zobrazení
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Úprava polohy štítku
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Uložení prezentace

#### Přehled
Jakmile nakonfigurujete graf, uložte prezentaci do zadaného adresáře.

**Krok 1: Uložení prezentace**
Použijte `save` metoda pro zápis změn:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Závěr

Nyní jste se naučili, jak vytvářet a upravovat prstencové grafy v Javě pomocí Aspose.Slides. Tyto kroky poskytují základ pro integraci sofistikovaných vizualizací dat do vašich prezentací.

**Další kroky:**
- Experimentujte s různými typy grafů dostupnými v Aspose.Slides.
- Prozkoumejte další možnosti přizpůsobení, jako jsou barvy, písma a styly, které odpovídají vašim potřebám v oblasti brandingu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}