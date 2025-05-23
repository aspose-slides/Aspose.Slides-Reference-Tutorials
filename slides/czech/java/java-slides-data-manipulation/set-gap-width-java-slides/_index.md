---
"description": "Naučte se, jak nastavit šířku mezery v Javě pomocí Aspose.Slides pro Javu. Vylepšete vizuální prvky grafů pro vaše prezentace v PowerPointu."
"linktitle": "Nastavení šířky mezery v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení šířky mezery v Javě Slides"
"url": "/cs/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení šířky mezery v Javě Slides


## Úvod do nastavení šířky mezery v Aspose.Slides pro Javu

V tomto tutoriálu vás provedeme procesem nastavení šířky mezery pro graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Šířka mezery určuje rozteč mezi sloupci nebo pruhy v grafu, což vám umožňuje ovládat vizuální vzhled grafu.

## Předpoklady

Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z webových stránek Aspose. [zde](https://releases.aspose.com/slides/java/).

## Podrobný průvodce

Chcete-li nastavit šířku mezery v grafu pomocí Aspose.Slides pro Javu, postupujte takto:

### 1. Vytvořte prázdnou prezentaci

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření prázdné prezentace 
Presentation presentation = new Presentation();
```

### 2. Přístup k prvnímu snímku

```java
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Přidání grafu s výchozími daty

```java
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Nastavení indexu datového listu grafu

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
```

### 5. Získejte sešit s daty grafů

```java
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Přidání série do grafu

```java
// Přidání série do grafu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Přidání kategorií do grafu

```java
// Přidání kategorií do grafu
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Naplnění dat série

```java
// Naplnění dat série
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Naplnění datových bodů řady
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Nastavení šířky mezery

```java
// Nastavení hodnoty šířky mezery
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Uložte prezentaci

```java
// Uložte prezentaci s grafem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení šířky mezery v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření prázdné prezentace 
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Přidat sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Přidat kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vezměte si druhou sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavit hodnotu GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Uložit prezentaci s grafem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jste se naučili, jak nastavit šířku mezery v grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Úprava šířky mezery umožňuje ovládat rozteč mezi sloupci nebo pruhy v grafu a vylepšit tak vizuální reprezentaci dat.

## Často kladené otázky

### Jak změním hodnotu šířky mezery?

Chcete-li změnit šířku mezery, použijte `setGapWidth` metoda na `ParentSeriesGroup` série grafů. V uvedeném příkladu jsme nastavili šířku mezery na 50, ale tuto hodnotu můžete upravit na požadovanou rozteč.

### Mohu si přizpůsobit další vlastnosti grafu?

Ano, Aspose.Slides pro Javu nabízí rozsáhlé možnosti pro přizpůsobení grafů. Můžete upravovat různé vlastnosti grafu, jako jsou barvy, popisky, názvy a další. Podrobné informace o možnostech přizpůsobení grafů naleznete v referenční příručce API.

### Kde najdu další zdroje a dokumentaci?

Komplexní dokumentaci a další zdroje k Aspose.Slides pro Javu naleznete na [Webové stránky Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}