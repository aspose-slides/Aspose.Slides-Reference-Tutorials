---
title: Nastavit štítky dat Procento přihlášení do Java Slides
linktitle: Nastavit štítky dat Procento přihlášení do Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit štítky dat se znaky procenta v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Vytvářejte poutavé grafy s podrobnými pokyny a zdrojovým kódem.
type: docs
weight: 17
url: /cs/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Úvod k nastavení datových štítků Procento přihlášení Aspose.Slides for Java

V této příručce vás provedeme procesem nastavení štítků dat se znakem procenta pomocí Aspose.Slides for Java. Vytvoříme prezentaci v PowerPointu se skládaným sloupcovým grafem a nakonfigurujeme popisky dat pro zobrazení procent.

## Předpoklady

 Než začnete, ujistěte se, že máte do projektu přidánu knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci

Nejprve vytvoříme novou PowerPoint prezentaci pomocí Aspose.Slides.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte snímek a graf

Dále do prezentace přidáme snímek a skládaný sloupcový graf.

```java
// Získejte referenci na snímek
ISlide slide = presentation.getSlides().get_Item(0);

// Přidejte graf PercentsStackedColumn na snímek
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Krok 3: Konfigurace formátu čísla osy

Chcete-li zobrazit procenta, musíme nakonfigurovat formát čísel pro svislou osu grafu.

```java
//Nastavte NumberFormatLinkedToSource na hodnotu false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Krok 4: Přidejte data grafu

Data do grafu přidáváme vytvářením řad a datových bodů. V tomto příkladu přidáme dvě řady s jejich příslušnými datovými body.

```java
// Získání listu dat grafu
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

## Krok 5: Přizpůsobte štítky dat

Nyní přizpůsobíme vzhled štítků dat.

```java
// Nastavení vlastností LabelFormat
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

Nakonec prezentaci uložíme do souboru PowerPoint.

```java
// Zápis prezentace na disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste vytvořili prezentaci aplikace PowerPoint se skládaným sloupcovým grafem a nakonfigurovali popisky dat pro zobrazení procent pomocí Aspose.Slides for Java.

## Úplný zdrojový kód pro sadu štítků dat Procento přihlášení do Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
// Získejte referenci na snímek
ISlide slide = presentation.getSlides().get_Item(0);
// Přidejte graf PercentsStackedColumn na snímek
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//Nastavte NumberFormatLinkedToSource na hodnotu false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Získání listu dat grafu
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
// Nastavení vlastností LabelFormat
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
// Zápis prezentace na disk
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Závěr

Podle této příručky jste se naučili, jak vytvářet poutavé prezentace s datovými štítky založenými na procentech, které mohou být zvláště užitečné pro efektivní předávání informací v obchodních zprávách, vzdělávacích materiálech a dalších.

## FAQ

### Jak mohu změnit barvy řady grafů?

 Barvu výplně řad grafů můžete změnit pomocí`setFill` způsobem, jak je ukázáno v příkladu.

### Mohu přizpůsobit velikost písma datových štítků?

 Ano, velikost písma datových štítků si můžete přizpůsobit nastavením`setFontHeight` vlastnost, jak je uvedeno v kódu.

### Jak mohu do grafu přidat další série?

 Další řady můžete do grafu přidat pomocí`add` metoda na`IChartSeriesCollection` objekt.
