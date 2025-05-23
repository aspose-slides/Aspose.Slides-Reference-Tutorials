---
"description": "Naučte se vytvářet úžasné grafy a spravovat vlastnosti v Javě s Aspose.Slides. Podrobný návod se zdrojovým kódem pro působivé prezentace."
"linktitle": "Správa vlastností grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Správa vlastností grafů v Javě Slides"
"url": "/cs/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Správa vlastností grafů v Javě Slides


## Úvod do správy vlastností a grafů v Java Slides pomocí Aspose.Slides

V tomto tutoriálu se podíváme na to, jak spravovat vlastnosti a vytvářet grafy v Javě pomocí Aspose.Slides. Aspose.Slides je výkonné Java API pro práci s prezentacemi v PowerPointu. Projdeme si celý proces krok za krokem, včetně příkladů zdrojového kódu.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu nainstalovanou a nastavenou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Přidání grafu do snímku

Chcete-li přidat graf na snímek, postupujte takto:

1. Importujte potřebné třídy a vytvořte instanci třídy Presentation.

```java
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

2. Přejděte na snímek, na který chcete graf přidat. V tomto příkladu přejdeme na první snímek.

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

Pro nastavení dat grafu musíme vytvořit sešit s daty grafu a přidat řady a kategorie. Postupujte takto:

4. Nastavte index datového listu grafu.

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
```

5. Získejte sešit s daty grafu.

```java
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Přidejte do grafu řady. V tomto příkladu přidáme dvě řady s názvem „Řada 1“ a „Řada 2“.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Přidejte do grafu kategorie. Zde přidáme tři kategorie.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Nastavení vlastností 3D rotace

Nyní nastavme vlastnosti 3D rotace grafu:

8. Nastavte osy pravého úhlu.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Nastavte úhly natočení pro osy X a Y. V tomto příkladu otočíme X o 40 stupňů a Y o 270 stupňů.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Nastavte procentuální hloubku na 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Naplnění dat série

11. Vezměte druhou sérii grafů a naplňte ji datovými body.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Naplnění dat série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Úprava překrytí

12. Nastavte hodnotu překrytí pro série. Můžete ji například nastavit na 100, pokud se nepřekrývání nestane.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Uložení prezentace

Nakonec uložte prezentaci na disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili 3D skládaný sloupcový graf s vlastními vlastnostmi pomocí Aspose.Slides v Javě.

## Kompletní zdrojový kód pro správu grafů vlastností v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
// Přístup k prvnímu snímku
ISlide slide = presentation.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Nastavení vlastností Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Vezměte si druhou sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavení hodnoty OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Zapsat prezentaci na disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jsme se ponořili do světa správy vlastností a vytváření grafů v Javě pomocí Aspose.Slides. Aspose.Slides je robustní Java API, které umožňuje vývojářům efektivně pracovat s prezentacemi v PowerPointu. Probrali jsme základní kroky a poskytli příklady zdrojového kódu, které vás celým procesem provedou.

## Často kladené otázky

### Jak mohu změnit typ grafu?

Typ grafu můžete změnit úpravou `ChartType` parametr při přidávání grafu. Dostupné typy grafů naleznete v dokumentaci k Aspose.Slides.

### Mohu si přizpůsobit barvy grafu?

Ano, barvy grafu můžete přizpůsobit nastavením vlastností výplně datových bodů nebo kategorií řady.

### Jak mohu do série přidat další datové body?

Do série můžete přidat další datové body pomocí `series.getDataPoints().addDataPointForBarSeries()` metodu a určení buňky obsahující datovou hodnotu.

### Jak mohu nastavit jiný úhel natočení?

Chcete-li nastavit jiný úhel natočení pro osy X a Y, použijte `chart.getRotation3D().setRotationX()` a `chart.getRotation3D().setRotationY()` požadovanými hodnotami úhlů.

### Jaké další 3D vlastnosti si mohu přizpůsobit?

Další 3D vlastnosti grafu, jako je hloubka, perspektiva a osvětlení, si můžete prohlédnout v dokumentaci k Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}