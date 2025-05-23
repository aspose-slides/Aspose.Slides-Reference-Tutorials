---
"description": "Naučte se, jak upravovat grafy v Java Slides pomocí Aspose.Slides pro Javu. Prozkoumejte možnosti druhého grafu a vylepšete své prezentace."
"linktitle": "Možnosti druhého vykreslení grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Možnosti druhého vykreslení grafů v Javě Slides"
"url": "/cs/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Možnosti druhého vykreslení grafů v Javě Slides


## Úvod do možností druhého vykreslování grafů v Javě (prezentace)

tomto tutoriálu se podíváme na to, jak přidat možnosti druhého grafu do grafů pomocí Aspose.Slides pro Javu. Možnosti druhého grafu vám umožňují přizpůsobit vzhled a chování grafů, zejména ve scénářích, jako jsou koláčové grafy. Poskytneme podrobné pokyny a příklady zdrojového kódu, jak toho dosáhnout. 

## Předpoklady
Než začneme, ujistěte se, že máte ve svém projektu Java nainstalovaný a nastavený Aspose.Slides pro Javu.

## Krok 1: Vytvořte prezentaci
Začněme vytvořením nové prezentace:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Přidání grafu do snímku
Dále přidáme na snímek graf. V tomto příkladu vytvoříme koláčový graf:

```java
// Přidat graf na snímek
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Krok 3: Úprava vlastností grafu
Nyní nastavme různé vlastnosti grafu, včetně možností druhého grafu:

```java
// Zobrazit popisky dat pro první sérii
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Nastavte velikost druhého koláče (v procentech)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Rozdělte koláč procenty
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Nastavte polohu rozdělení
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Krok 4: Uložte prezentaci
Nakonec uložte prezentaci s grafem a druhým vykreslením:

```java
// Zapsat prezentaci na disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro možnosti druhého grafu

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
// Přidat graf na snímek
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Nastavení různých vlastností
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Zapsat prezentaci na disk
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přidat možnosti druhého grafu do grafů v Java Slides pomocí Aspose.Slides pro Javu. Můžete si přizpůsobit různé vlastnosti, abyste vylepšili vzhled a funkčnost grafů, a vaše prezentace tak byly informativnější a vizuálně atraktivnější.

## Často kladené otázky

### Jak mohu změnit velikost druhého koláčového grafu v koláčovém grafu?

Chcete-li změnit velikost druhého koláčového grafu, použijte `setSecondPieSize` metodu, jak je znázorněno ve výše uvedeném příkladu kódu. Upravte hodnotu tak, aby určovala velikost v procentech.

### Co dělá `PieSplitBy` kontrola v koláčovém grafu?

Ten/Ta/To `PieSplitBy` Vlastnost určuje, jak je koláčový graf rozdělen. Můžete ji nastavit na jednu z možností `PieSplitType.ByPercentage` nebo `PieSplitType.ByValue` rozdělit graf podle procenta nebo podle konkrétní hodnoty.

### Jak nastavím pozici rozdělení v koláčovém grafu?

Polohu rozdělení v koláčovém grafu můžete nastavit pomocí `setPieSplitPosition` metoda. Upravte hodnotu pro určení požadované polohy.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}