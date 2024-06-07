---
title: Rozptýlený graf v Java Slides
linktitle: Rozptýlený graf v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet bodové grafy v Javě pomocí Aspose.Slides. Podrobný průvodce se zdrojovým kódem Java pro vizualizaci dat v prezentacích.
type: docs
weight: 11
url: /cs/java/chart-creation/scattered-chart-java-slides/
---

## Úvod do Scattered Chart v Aspose.Slides pro Javu

V tomto tutoriálu vás provedeme procesem vytváření bodového grafu pomocí Aspose.Slides for Java. Bodové grafy jsou užitečné pro vizualizaci datových bodů ve dvourozměrné rovině. Poskytneme vám podrobné pokyny a zahrneme zdrojový kód Java pro vaše pohodlí.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. [Aspose.Slides pro Javu](https://products.aspose.com/slides/java) nainstalováno.
2. Nastaveno vývojové prostředí Java.

## Krok 1: Inicializujte prezentaci

Nejprve importujte potřebné knihovny a vytvořte novou prezentaci.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Vytvořte novou prezentaci
Presentation pres = new Presentation();
```

## Krok 2: Přidejte snímek a vytvořte bodový graf

 Dále přidejte snímek a vytvořte na něm bodový graf. Použijeme`ScatterWithSmoothLines` typ grafu v tomto příkladu.

```java
// Získejte první snímek
ISlide slide = pres.getSlides().get_Item(0);

// Vytvoření bodového grafu
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Krok 3: Připravte data grafu

Nyní si připravíme data pro náš bodový graf. Přidáme dvě řady, každou s více datovými body.

```java
// Získání výchozího indexu listu dat grafu
int defaultWorksheetIndex = 0;

// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Smazat ukázkovou sérii
chart.getChartData().getSeries().clear();

// Přidejte první sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Přidejte datové body do první řady
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Upravte typ série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Změňte velikost značky
series.getMarker().setSymbol(MarkerStyleType.Star); // Změnit symbol značky

// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);

// Přidejte datové body do druhé řady
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Změňte styl značky pro druhou sérii
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Krok 4: Uložte prezentaci

Nakonec uložte prezentaci s bodovým grafem do souboru PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

je to! Úspěšně jste vytvořili bodový graf pomocí Aspose.Slides for Java. Nyní můžete tento příklad dále přizpůsobit tak, aby vyhovoval vašim specifickým požadavkům na data a design.

## Kompletní zdrojový kód pro Scattered Chart v Java Slides
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Vytvoření výchozího grafu
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Získání výchozího indexu listu dat grafu
int defaultWorksheetIndex = 0;
// Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat ukázkovou sérii
chart.getChartData().getSeries().clear();
// Přidat novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Přidejte tam nový bod (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Přidat nový bod (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Upravte typ série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Změna značky řady grafu
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);
// Přidejte tam nový bod (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Přidat nový bod (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Přidat nový bod (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Přidat nový bod (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Změna značky řady grafu
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jsme vás provedli procesem vytváření bodového grafu pomocí Aspose.Slides pro Java. Bodové grafy jsou výkonnými nástroji pro vizualizaci datových bodů ve dvourozměrném prostoru, což usnadňuje analýzu a pochopení komplexních datových vztahů.

## FAQ

### Jak mohu změnit typ grafu?

 Chcete-li změnit typ grafu, použijte`setType`metodu na sérii grafu a zadejte požadovaný typ grafu. Například,`series.setType(ChartType.Line)` změní řadu na spojnicový graf.

### Jak přizpůsobím velikost a styl značky?

 Velikost a styl značky můžete změnit pomocí`getMarker` metodu na sérii a poté nastavte vlastnosti velikosti a symbolu. Například:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Neváhejte a prozkoumejte další možnosti přizpůsobení v dokumentaci Aspose.Slides for Java.

 Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.