---
title: Správa grafů vlastností v aplikaci Java Slides
linktitle: Správa grafů vlastností v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet úžasné grafy a spravovat vlastnosti na snímcích Java pomocí Aspose.Slides. Podrobný průvodce se zdrojovým kódem pro výkonné prezentace.
weight: 13
url: /cs/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa grafů vlastností v aplikaci Java Slides


## Úvod do správy vlastností a grafů v Java Slides pomocí Aspose.Slides

V tomto tutoriálu prozkoumáme, jak spravovat vlastnosti a vytvářet grafy na snímcích Java pomocí Aspose.Slides. Aspose.Slides je výkonné Java API pro práci s PowerPoint prezentacemi. Projdeme si procesem krok za krokem, včetně příkladů zdrojového kódu.

## Předpoklady

Než začneme, ujistěte se, že máte v projektu nainstalovanou a nastavenou knihovnu Aspose.Slides pro Javu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Přidání grafu na snímek

Chcete-li přidat graf na snímek, postupujte takto:

1. Importujte potřebné třídy a vytvořte instanci třídy Presentation.

```java
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
```

2. Otevřete snímek, kam chcete přidat graf. V tomto příkladu přistupujeme k prvnímu snímku.

```java
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Přidejte graf s výchozími daty. V tomto případě přidáváme graf StackedColumn3D.

```java
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Nastavení dat grafu

Chcete-li nastavit data grafu, musíme vytvořit sešit dat grafu a přidat řady a kategorie. Následuj tyto kroky:

4. Nastavte index listu dat grafu.

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
```

5. Získejte sešit dat grafu.

```java
// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Přidejte řadu do grafu. V tomto příkladu přidáme dvě série s názvem „Série 1“ a „Série 2“.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Přidejte do grafu kategorie. Zde přidáváme tři kategorie.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Nastavení vlastností 3D rotace

Nyní nastavíme vlastnosti 3D rotace pro graf:

8. Nastavte osy pravého úhlu.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Nastavte úhly rotace pro osy X a Y. V tomto příkladu otočíme X o 40 stupňů a Y o 270 stupňů.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Nastavte procento hloubky na 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Vyplnění dat řady

11. Vezměte druhou řadu grafů a naplňte ji datovými body.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Vyplňte data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Úprava přesahu

12. Nastavte hodnotu překrytí pro série. Můžete jej například nastavit na 100 bez překrývání.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Ukládání prezentace

Nakonec prezentaci uložte na disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste vytvořili 3D skládaný sloupcový graf s uživatelskými vlastnostmi pomocí Aspose.Slides v Javě.

## Kompletní zdrojový kód pro správu grafů vlastností v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Přidat sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Přidat kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Nastavte vlastnosti Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Vezměte druhou řadu grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavte hodnotu OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Zápis prezentace na disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jsme se ponořili do světa správy vlastností a vytváření grafů na snímcích Java pomocí Aspose.Slides. Aspose.Slides je robustní Java API, které umožňuje vývojářům efektivně pracovat s prezentacemi v PowerPointu. Popsali jsme základní kroky a poskytli příklady zdrojového kódu, které vás provedou celým procesem.

## FAQ

### Jak mohu změnit typ grafu?

 Typ grafu můžete změnit úpravou`ChartType` parametr při přidávání grafu. Dostupné typy grafů najdete v dokumentaci Aspose.Slides.

### Mohu přizpůsobit barvy grafu?

Ano, barvy grafu můžete přizpůsobit nastavením vlastností výplně datových bodů nebo kategorií řad.

### Jak přidám další datové body do série?

 Do řady můžete přidat další datové body pomocí`series.getDataPoints().addDataPointForBarSeries()` a určení buňky obsahující hodnotu dat.

### Jak mohu nastavit jiný úhel natočení?

 Chcete-li nastavit jiný úhel natočení pro osy X a Y, použijte`chart.getRotation3D().setRotationX()` a`chart.getRotation3D().setRotationY()` s požadovanými hodnotami úhlu.

### Jaké další 3D vlastnosti mohu přizpůsobit?

Další 3D vlastnosti grafu, jako je hloubka, perspektiva a osvětlení, můžete prozkoumat pomocí dokumentace Aspose.Slides.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
