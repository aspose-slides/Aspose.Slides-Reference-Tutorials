---
"description": "Naučte se, jak vytvářet bodové grafy v Javě pomocí Aspose.Slides. Podrobný návod se zdrojovým kódem Java pro vizualizaci dat v prezentacích."
"linktitle": "Rozptýlený graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Rozptýlený graf v Javě Slides"
"url": "/cs/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Rozptýlený graf v Javě Slides


## Úvod do rozptýleného grafu v Aspose.Slides pro Javu

V tomto tutoriálu vás provedeme procesem vytvoření bodového grafu pomocí Aspose.Slides pro Javu. Bodové grafy jsou užitečné pro vizualizaci datových bodů na dvourozměrné rovině. Poskytneme podrobné pokyny a pro vaše pohodlí přiložíme zdrojový kód Javy.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. [Aspose.Slides pro Javu](https://products.aspose.com/slides/java) nainstalováno.
2. Nastavení vývojového prostředí v Javě.

## Krok 1: Inicializace prezentace

Nejprve importujte potřebné knihovny a vytvořte novou prezentaci.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Vytvořte novou prezentaci
Presentation pres = new Presentation();
```

## Krok 2: Přidání snímku a vytvoření bodového grafu

Dále přidejte snímek a vytvořte na něm bodový graf. Použijeme `ScatterWithSmoothLines` typ grafu v tomto příkladu.

```java
// Získejte první snímek
ISlide slide = pres.getSlides().get_Item(0);

// Vytvoření bodového grafu
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Krok 3: Příprava dat grafu

Nyní si připravme data pro náš bodový graf. Přidáme dvě řady, každou s více datovými body.

```java
// Získání výchozího indexu listu s daty grafu
int defaultWorksheetIndex = 0;

// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Smazat demo sérii
chart.getChartData().getSeries().clear();

// Přidat první sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Přidání datových bodů do první série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Upravit typ série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Změnit velikost značky
series.getMarker().setSymbol(MarkerStyleType.Star); // Symbol změny značky

// Vezměte si druhou sérii grafů
series = chart.getChartData().getSeries().get_Item(1);

// Přidání datových bodů do druhé série
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

To je vše! Úspěšně jste vytvořili bodový graf pomocí Aspose.Slides pro Javu. Nyní můžete tento příklad dále přizpůsobit svým specifickým požadavkům na data a design.

## Kompletní zdrojový kód pro rozptýlený graf v Javě - Slides
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Vytvoření výchozího grafu
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Získání výchozího indexu listu s daty grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat demo sérii
chart.getChartData().getSeries().clear();
// Přidat novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Přidejte tam nový bod (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Přidat nový bod (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Upravit typ série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Změna značky řady grafu
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Vezměte si druhou sérii grafů
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

V tomto tutoriálu jsme vás provedli procesem vytvoření bodového grafu pomocí Aspose.Slides pro Javu. Bodové grafy jsou výkonné nástroje pro vizualizaci datových bodů ve dvourozměrném prostoru, což usnadňuje analýzu a pochopení složitých datových vztahů.

## Často kladené otázky

### Jak mohu změnit typ grafu?

Chcete-li změnit typ grafu, použijte `setType` metodu na sérii grafů a zadejte požadovaný typ grafu. Například `series.setType(ChartType.Line)` by změnilo sérii na spojnicový graf.

### Jak si mohu přizpůsobit velikost a styl značky?

Velikost a styl značky můžete změnit pomocí `getMarker` metodu na sérii a poté nastavte vlastnosti velikosti a symbolu. Například:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Neváhejte prozkoumat další možnosti přizpůsobení v dokumentaci k Aspose.Slides pro Javu.

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}