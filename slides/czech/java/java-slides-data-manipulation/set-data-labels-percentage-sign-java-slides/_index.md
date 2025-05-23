---
"description": "Naučte se, jak nastavit popisky dat pomocí procentuálních znaků v prezentacích v PowerPointu pomocí Aspose.Slides pro Javu. Vytvářejte poutavé grafy s podrobnými pokyny a zdrojovým kódem."
"linktitle": "Nastavení popisků dat Procento Přihlášení v prezentaci Java"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení popisků dat Procento Přihlášení v prezentaci Java"
"url": "/cs/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení popisků dat Procento Přihlášení v prezentaci Java


## Úvod do nastavení popisků dat a procentuálního přihlášení v Aspose.Slides pro Javu

V této příručce vás provedeme procesem nastavení popisků dat se znaménkem procenta pomocí Aspose.Slides pro Javu. Vytvoříme prezentaci v PowerPointu se skládaným sloupcovým grafem a nakonfigurujeme popisky dat pro zobrazení procent.

## Předpoklady

Než začnete, ujistěte se, že máte do projektu přidánu knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci

Nejprve vytvoříme novou prezentaci v PowerPointu pomocí Aspose.Slides.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidání snímku a grafu

Dále do prezentace přidáme snímek a skládaný sloupcový graf.

```java
// Získat odkaz na snímek
ISlide slide = presentation.getSlides().get_Item(0);

// Přidání grafu PercentsStackedColumn na snímek
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Krok 3: Konfigurace formátu čísel os

Pro zobrazení procent je třeba nakonfigurovat formát čísel pro svislou osu grafu.

```java
// Nastavte NumberFormatLinkedToSource na hodnotu false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Krok 4: Přidání dat grafu

Data do grafu přidáváme vytvořením řad a datových bodů. V tomto příkladu přidáváme dvě řady s příslušnými datovými body.

```java
// Získání pracovního listu s daty grafu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Přidat novou sérii
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Přidat novou sérii
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Krok 5: Úprava popisků dat

Nyní si přizpůsobme vzhled popisků dat.

```java
// Nastavení vlastností formátu štítků (LabelFormat)
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Krok 6: Uložte prezentaci

Nakonec prezentaci uložíme do souboru PowerPointu.

```java
// Zapsat prezentaci na disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili prezentaci v PowerPointu se skládaným sloupcovým grafem a nakonfigurovali popisky dat pro zobrazení procent pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro nastavení procentuálního přihlášení k datovým popiskům v Javě

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
// Získat odkaz na snímek
ISlide slide = presentation.getSlides().get_Item(0);
// Přidání grafu PercentsStackedColumn na snímek
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Nastavte NumberFormatLinkedToSource na hodnotu false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Přidat novou sérii
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Nastavení barvy výplně série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Nastavení vlastností formátu štítků (LabelFormat)
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Přidat novou sérii
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Nastavení typu a barvy výplně
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Zapsat prezentaci na disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Závěr

Dodržováním tohoto průvodce jste se naučili, jak vytvářet poutavé prezentace s popisky dat založenými na procentech, což může být obzvláště užitečné pro efektivní sdělování informací v obchodních zprávách, vzdělávacích materiálech a dalších materiálech.

## Často kladené otázky

### Jak mohu změnit barvy série grafů?

Barvu výplně grafové série můžete změnit pomocí `setFill` metodu, jak je znázorněno v příkladu.

### Mohu si přizpůsobit velikost písma popisků dat?

Ano, velikost písma popisků dat si můžete přizpůsobit nastavením `setFontHeight` vlastnost, jak je znázorněno v kódu.

### Jak mohu do grafu přidat další série?

Do grafu můžete přidat další řady pomocí `add` metoda na `IChartSeriesCollection` objekt.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}