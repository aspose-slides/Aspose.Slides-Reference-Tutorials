---
title: Nastavte šířku mezery v Java Slides
linktitle: Nastavte šířku mezery v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit Gap Width v Java Slides pomocí Aspose.Slides pro Java. Vylepšete vizuály grafů pro prezentace v PowerPointu.
type: docs
weight: 21
url: /cs/java/data-manipulation/set-gap-width-java-slides/
---

## Úvod do nastavení šířky mezery v Aspose.Slides pro Javu

V tomto tutoriálu vás provedeme procesem nastavení šířky mezery pro graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Šířka mezery určuje mezery mezi sloupci nebo pruhy v grafu, což vám umožňuje ovládat vizuální vzhled grafu.

## Předpoklady

 Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z webu Aspose[tady](https://releases.aspose.com/slides/java/).

## Průvodce krok za krokem

Chcete-li nastavit šířku mezery v grafu pomocí Aspose.Slides for Java, postupujte takto:

### 1. Vytvořte prázdnou prezentaci

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Vytvoření prázdné prezentace
Presentation presentation = new Presentation();
```

### 2. Otevřete první snímek

```java
// Otevřete první snímek
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Přidejte graf s výchozími daty

```java
// Přidejte graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Nastavte Index datového listu grafu

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
```

### 5. Získejte sešit dat grafu

```java
//Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Přidejte do grafu řady

```java
// Přidejte řadu do grafu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Přidejte do grafu kategorie

```java
// Přidejte do grafu kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Vyplňte data série

```java
// Vyplňte data série
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Vyplňování sériových datových bodů
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Nastavte šířku mezery

```java
// Nastavte hodnotu Gap Width
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Uložte prezentaci

```java
// Uložte prezentaci s grafem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení šířky mezery v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytváření prázdné prezentace
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
//Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Přidat sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Přidat kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vezměte druhou řadu grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavte hodnotu GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Uložit prezentaci s grafem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jste se naučili, jak nastavit šířku mezery pro graf v prezentaci PowerPoint pomocí Aspose.Slides for Java. Úpravou šířky mezery můžete ovládat mezery mezi sloupci nebo pruhy v grafu a zlepšit tak vizuální reprezentaci vašich dat.

## FAQ

### Jak změním hodnotu Gap Width?

 Chcete-li změnit šířku mezery, použijte`setGapWidth` metoda na`ParentSeriesGroup` řady grafů. V uvedeném příkladu jsme nastavili šířku mezery na 50, ale tuto hodnotu můžete upravit na požadovanou vzdálenost.

### Mohu přizpůsobit další vlastnosti grafu?

Ano, Aspose.Slides for Java poskytuje rozsáhlé možnosti pro přizpůsobení grafů. Můžete upravit různé vlastnosti grafu, jako jsou barvy, štítky, názvy a další. Podrobné informace o možnostech přizpůsobení grafu naleznete v Referenční příručce rozhraní API.

### Kde najdu další zdroje a dokumentaci?

 Komplexní dokumentaci a další zdroje naleznete na Aspose.Slides for Java na[Aspose webové stránky](https://reference.aspose.com/slides/java/).