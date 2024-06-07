---
title: Druhé možnosti vykreslování pro grafy v Java Slides
linktitle: Druhé možnosti vykreslování pro grafy v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přizpůsobit grafy v Java Slides pomocí Aspose.Slides pro Java. Prozkoumejte možnosti druhého grafu a vylepšete své prezentace.
type: docs
weight: 12
url: /cs/java/chart-creation/second-plot-options-charts-java-slides/
---

## Úvod do možností druhého vykreslování pro grafy v Java Slides

tomto tutoriálu prozkoumáme, jak přidat druhé možnosti vykreslování do grafů pomocí Aspose.Slides pro Java. Druhé možnosti vykreslování umožňují přizpůsobit vzhled a chování grafů, zejména ve scénářích, jako jsou výsečové grafy. Poskytneme vám podrobné pokyny a příklady zdrojového kódu, jak toho dosáhnout. 

## Předpoklady
Než začneme, ujistěte se, že máte Aspose.Slides for Java nainstalovaný a nastavený ve vašem projektu Java.

## Krok 1: Vytvořte prezentaci
Začněme vytvořením nové prezentace:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte graf do snímku
Dále na snímek přidáme graf. V tomto příkladu vytvoříme výsečový graf:

```java
// Přidejte graf na snímek
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Krok 3: Přizpůsobte vlastnosti grafu
Nyní nastavíme různé vlastnosti grafu, včetně možností druhého vykreslování:

```java
// Zobrazit popisky dat pro první sérii
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Nastavte velikost druhého koláče (v procentech)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Rozdělte koláč podle procent
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Nastavte polohu rozdělení
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Krok 4: Uložte prezentaci
Nakonec uložte prezentaci s možností grafu a druhého grafu:

```java
// Zápis prezentace na disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro možnosti druhého pozemku

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
// Přidejte graf na snímek
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Nastavte různé vlastnosti
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Zápis prezentace na disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přidat druhé možnosti vykreslování do grafů v Java Slides pomocí Aspose.Slides for Java. Můžete přizpůsobit různé vlastnosti, abyste zlepšili vzhled a funkčnost svých grafů, díky čemuž budou vaše prezentace informativnější a vizuálně přitažlivější.

## FAQ

### Jak mohu změnit velikost druhého koláče v koláčovém grafu?

 Chcete-li změnit velikost druhého výsečového grafu, použijte`setSecondPieSize` metoda, jak je znázorněno v příkladu kódu výše. Upravte hodnotu pro určení velikosti v procentech.

###  Co dělá`PieSplitBy` control in a Pie of Pie chart?

 The`PieSplitBy` vlastnost řídí, jak je výsečový graf rozdělen. Můžete jej nastavit na obojí`PieSplitType.ByPercentage` nebo`PieSplitType.ByValue` pro rozdělení grafu podle procent nebo podle konkrétní hodnoty.

### Jak nastavím polohu rozdělení v koláčovém grafu?

Polohu rozdělení v koláčovém grafu můžete nastavit pomocí`setPieSplitPosition` metoda. Upravte hodnotu pro určení požadované polohy.