---
"description": "Naučte se, jak vytvářet úžasné koláčové grafy v prezentacích v PowerPointu pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro vývojáře v Javě."
"linktitle": "Koláčový graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Koláčový graf v Javě Slides"
"url": "/cs/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Koláčový graf v Javě Slides


## Úvod do vytváření koláčového grafu v Javě Slides pomocí Aspose.Slides

V tomto tutoriálu si ukážeme, jak vytvořit koláčový graf v prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Poskytneme vám podrobné pokyny a zdrojový kód v Javě, které vám pomohou začít. Tato příručka předpokládá, že jste si již nastavili vývojové prostředí s Aspose.Slides pro Javu.

## Předpoklady

Než začnete, ujistěte se, že máte v projektu nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Nezapomeňte importovat potřebné třídy z knihovny Aspose.Slides.

## Krok 2: Inicializace prezentace

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation presentation = new Presentation();
```

Vytvořte nový objekt Presentation, který bude reprezentovat váš soubor PowerPoint. Nahraďte ho. `"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.

## Krok 3: Přidání snímku

```java
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
```

Získejte první snímek prezentace, kam chcete přidat koláčový graf.

## Krok 4: Přidání koláčového grafu

```java
// Přidání koláčového grafu s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Přidat koláčový graf na snímek na zadané pozici a velikosti.

## Krok 5: Nastavení názvu grafu

```java
// Nastavit název grafu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Nastavte název koláčového grafu. Název si můžete upravit dle potřeby.

## Krok 6: Úprava dat grafu

```java
// Nastavení první série pro zobrazení hodnot
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;

// Získání pracovního listu s daty grafu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Smazat výchozí generované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nových kategorií
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Přidávání nových sérií
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Naplňování dat série
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Přizpůsobte data grafu přidáním kategorií a řad a nastavením jejich hodnot. V tomto příkladu máme tři kategorie a jednu řadu s odpovídajícími datovými body.

## Krok 7: Přizpůsobení sektorů koláčového grafu

```java
// Nastavení barev sektorů
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Přizpůsobte si vzhled každého sektoru
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Přizpůsobení ohraničení sektoru
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Podobným způsobem upravte i další sektory
```

Přizpůsobte si vzhled každého sektoru v koláčovém grafu. Můžete změnit barvy, styly ohraničení a další vizuální vlastnosti.

## Krok 8: Úprava popisků dat

```java
// Přizpůsobení popisků dat
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Podobným způsobem upravte popisky dat pro další datové body
```

Upravte popisky dat pro každý datový bod v koláčovém grafu. Můžete ovládat, které hodnoty se v grafu zobrazují.

## Krok 9: Zobrazení vodicích čar

```java
// Zobrazit vodicí čáry pro graf
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Povolte odkazové čáry pro propojení popisků dat s odpovídajícími sektory.

## Krok 10: Nastavení úhlu natočení koláčového grafu

```java
// Nastavení úhlu natočení pro sektory koláčového grafu
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Nastavte úhel natočení pro sektory koláčového grafu. V tomto příkladu jsme ho nastavili na 180 stupňů.

## Krok 11: Uložte prezentaci

```java
// Uložte prezentaci s koláčovým grafem
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Uložte prezentaci s koláčovým grafem do zadaného adresáře.

## Kompletní zdrojový kód pro koláčový graf v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slides = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Název grafu nastavení
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Nastavit první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat výchozí generované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Přidávání nových sérií
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Nyní se naplňují data série
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Nefunguje v nové verzi
// Přidání nových bodů a nastavení barvy sektoru
// série.JeBarvaRůzná = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Stanovení hranice sektoru
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Stanovení hranice sektoru
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Stanovení hranice sektoru
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Vytvořte vlastní štítky pro každou kategorii pro nové série
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Zobrazení odkazových čar pro graf
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Nastavení úhlu natočení pro sektory koláčového grafu
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Uložit prezentaci s grafem
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Závěr

Úspěšně jste vytvořili koláčový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Vzhled grafu a popisky dat si můžete přizpůsobit podle svých specifických požadavků. Tento tutoriál poskytuje základní příklad a grafy můžete dále vylepšovat a přizpůsobovat dle potřeby.

## Často kladené otázky

### Jak mohu změnit barvy jednotlivých sektorů v koláčovém grafu?

Chcete-li změnit barvy jednotlivých sektorů v koláčovém grafu, můžete si přizpůsobit barvu výplně pro každý datový bod. V uvedeném příkladu kódu jsme ukázali, jak nastavit barvu výplně pro každý sektor pomocí `getSolidFillColor().setColor()` metoda. Hodnoty barev můžete upravit tak, abyste dosáhli požadovaného vzhledu.

### Mohu do koláčového grafu přidat další kategorie a datové řady?

Ano, do koláčového grafu můžete přidat další kategorie a datové řady. K tomu můžete použít `getChartData().getCategories().add()` a `getChartData().getSeries().add()` metody, jak je znázorněno v příkladu. Jednoduše zadejte příslušná data a popisky pro nové kategorie a řady, abyste rozšířili graf.

### Jak si mohu přizpůsobit vzhled popisků dat?

Vzhled popisků dat si můžete přizpůsobit pomocí `getDataLabelFormat()` metodu na popisku každého datového bodu. V příkladu jsme si ukázali, jak zobrazit hodnotu na popiscích dat pomocí `getDataLabelFormat().setShowValue(true)`Popisky dat si můžete dále přizpůsobit ovládáním zobrazených hodnot, zobrazením legendy a úpravou dalších možností formátování.

### Mohu změnit název koláčového grafu?

Ano, název koláčového grafu můžete změnit. V poskytnutém kódu jsme název grafu nastavili pomocí `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`Můžete nahradit `"Sample Title"` s požadovaným textem titulku.

### Jak uložím vygenerovanou prezentaci s koláčovým grafem?

Chcete-li uložit prezentaci s koláčovým grafem, použijte `presentation.save()` metoda. Zadejte požadovanou cestu k souboru a jeho název spolu s formátem, ve kterém chcete prezentaci uložit. Například:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Ujistěte se, že jste zadali správnou cestu k souboru a jeho formát.

### Mohu pomocí Aspose.Slides pro Javu vytvářet i jiné typy grafů?

Ano, Aspose.Slides pro Javu podporuje různé typy grafů, včetně sloupcových grafů, spojnicových grafů a dalších. Různé typy grafů můžete vytvářet změnou `ChartType` při přidávání grafu. Další podrobnosti o vytváření různých typů grafů naleznete v dokumentaci k Aspose.Slides.

### Jak mohu najít více informací a příkladů pro práci s Aspose.Slides pro Javu?

Pro více informací, podrobnou dokumentaci a další příklady můžete navštívit [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/)Poskytuje komplexní zdroje, které vám pomohou efektivně využívat knihovnu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}