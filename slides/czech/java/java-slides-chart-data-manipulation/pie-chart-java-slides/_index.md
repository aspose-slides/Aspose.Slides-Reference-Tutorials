---
title: Koláčový graf v Java Slides
linktitle: Koláčový graf v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet úžasné koláčové grafy v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Podrobný průvodce se zdrojovým kódem pro vývojáře v jazyce Java.
weight: 23
url: /cs/java/chart-data-manipulation/pie-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do vytváření výsečového grafu v Java Slides pomocí Aspose.Slides

tomto tutoriálu si ukážeme, jak vytvořit výsečový graf v powerpointové prezentaci pomocí Aspose.Slides for Java. Poskytneme vám podrobné pokyny a zdrojový kód Java, které vám pomohou začít. Tato příručka předpokládá, že jste již nastavili své vývojové prostředí s Aspose.Slides for Java.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Ujistěte se, že jste importovali potřebné třídy z knihovny Aspose.Slides.

## Krok 2: Inicializujte prezentaci

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Třída okamžité prezentace, která představuje soubor PPTX
Presentation presentation = new Presentation();
```

 Vytvořte nový objekt prezentace, který bude reprezentovat váš soubor PowerPoint. Nahradit`"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.

## Krok 3: Přidejte snímek

```java
// Otevřete první snímek
ISlide slide = presentation.getSlides().get_Item(0);
```

Získejte první snímek prezentace, kam chcete přidat výsečový graf.

## Krok 4: Přidejte výsečový graf

```java
// Přidejte výsečový graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Přidejte na snímek výsečový graf v určené poloze a velikosti.

## Krok 5: Nastavte název grafu

```java
// Nastavte název grafu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Nastavte název výsečového grafu. Titul si můžete upravit podle potřeby.

## Krok 6: Přizpůsobte data grafu

```java
//Nastavte první řadu tak, aby zobrazovala hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;

// Získání listu dat grafu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Smazat výchozí vygenerované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nových kategorií
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Přidávání nové série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Vyplňování řad dat
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Přizpůsobte data grafu přidáním kategorií a řad a nastavením jejich hodnot. V tomto příkladu máme tři kategorie a jednu řadu s odpovídajícími datovými body.

## Krok 7: Přizpůsobte sektory výsečového grafu

```java
// Nastavte barvy sektorů
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Přizpůsobte vzhled každého sektoru
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Přizpůsobte hranici sektoru
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Podobným způsobem přizpůsobte další sektory
```

Přizpůsobte vzhled každého sektoru v koláčovém grafu. Můžete změnit barvy, styly ohraničení a další vizuální vlastnosti.

## Krok 8: Přizpůsobte štítky dat

```java
// Přizpůsobte štítky dat
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Přizpůsobte štítky dat pro jiné datové body podobným způsobem
```

Přizpůsobte popisky dat pro každý datový bod ve výsečovém grafu. Můžete ovládat, které hodnoty se zobrazí v grafu.

## Krok 9: Zobrazte vodicí čáry

```java
// Zobrazit vodicí čáry pro graf
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Povolte odkazové čáry pro připojení datových štítků k jejich odpovídajícím sektorům.

## Krok 10: Nastavte úhel otočení koláčového grafu

```java
// Nastavte úhel otočení pro sektory koláčového grafu
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Nastavte úhel otočení pro sektory koláčového grafu. V tomto příkladu jsme jej nastavili na 180 stupňů.

## Krok 11: Uložte prezentaci

```java
// Uložte prezentaci pomocí výsečového grafu
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Uložte prezentaci s výsečovým grafem do určeného adresáře.

## Kompletní zdrojový kód pro koláčový graf v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Třída okamžité prezentace, která představuje soubor PPTX
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slides = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Nastavení názvu grafu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Nastavte první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat výchozí vygenerované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Přidávání nové série
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// V nové verzi nefunguje
// Přidávání nových bodů a nastavení barvy sektoru
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Nastavení hranice sektoru
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Nastavení hranice sektoru
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Nastavení hranice sektoru
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Vytvořte vlastní štítky pro každou z kategorií pro nové série
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
// Zobrazení vůdčích čar pro graf
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Nastavení úhlu rotace pro sektory koláčového grafu
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Uložit prezentaci s grafem
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Závěr

Úspěšně jste vytvořili výsečový graf v prezentaci aplikace PowerPoint pomocí Aspose.Slides for Java. Vzhled grafu a popisky dat můžete přizpůsobit svým konkrétním požadavkům. Tento výukový program poskytuje základní příklad a své grafy můžete dále vylepšovat a přizpůsobovat podle potřeby.

## FAQ

### Jak mohu změnit barvy jednotlivých sektorů v koláčovém grafu?

 Chcete-li změnit barvy jednotlivých sektorů ve výsečovém grafu, můžete upravit barvu výplně pro každý datový bod. V poskytnutém příkladu kódu jsme ukázali, jak nastavit barvu výplně pro každý sektor pomocí`getSolidFillColor().setColor()` metoda. Hodnoty barev můžete upravit, abyste dosáhli požadovaného vzhledu.

### Mohu do výsečového grafu přidat další kategorie a datové řady?

 Ano, do výsečového grafu můžete přidat další kategorie a datové řady. Chcete-li to provést, můžete použít`getChartData().getCategories().add()` a`getChartData().getSeries().add()` metody, jak je ukázáno v příkladu. Jednoduše zadejte příslušná data a štítky pro nové kategorie a série, abyste rozšířili svůj graf.

### Jak přizpůsobím vzhled datových štítků?

 Vzhled datových štítků můžete upravit pomocí`getDataLabelFormat()` metoda na štítku každého datového bodu. V příkladu jsme si ukázali, jak pomocí datových štítků zobrazit hodnotu`getDataLabelFormat().setShowValue(true)`. Popisky dat můžete dále přizpůsobit ovládáním zobrazených hodnot, zobrazením klíčů legend a úpravou dalších možností formátování.

### Mohu změnit název koláčového grafu?

 Ano, můžete změnit název koláčového grafu. V poskytnutém kódu nastavíme název grafu pomocí`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Můžete vyměnit`"Sample Title"` s požadovaným textem nadpisu.

### Jak uložím vygenerovanou prezentaci pomocí koláčového grafu?

 Chcete-li uložit prezentaci s výsečovým grafem, použijte`presentation.save()` metoda. Zadejte požadovanou cestu k souboru a název spolu s formátem, ve kterém chcete prezentaci uložit. Například:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Ujistěte se, že jste zadali správnou cestu a formát souboru.

### Mohu pomocí Aspose.Slides for Java vytvářet jiné typy grafů?

Ano, Aspose.Slides for Java podporuje různé typy grafů, včetně sloupcových grafů, spojnicových grafů a dalších. Můžete vytvářet různé typy grafů změnou`ChartType` při přidávání grafu. Další podrobnosti o vytváření různých typů grafů naleznete v dokumentaci Aspose.Slides.

### Jak najdu další informace a příklady pro práci s Aspose.Slides for Java?

 Další informace, podrobnou dokumentaci a další příklady naleznete na adrese[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/). Poskytuje komplexní zdroje, které vám pomohou efektivně využívat knihovnu.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
