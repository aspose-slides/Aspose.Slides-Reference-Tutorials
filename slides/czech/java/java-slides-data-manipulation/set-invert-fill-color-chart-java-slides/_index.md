---
title: Nastavte Invertovat barevný graf výplně v Java Slides
linktitle: Nastavte Invertovat barevný graf výplně v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit invertní barvy výplně pro grafy Java Slides pomocí Aspose.Slides. Vylepšete své vizualizace grafů pomocí tohoto podrobného průvodce a zdrojového kódu.
weight: 22
url: /cs/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod k nastavení invertního barevného grafu výplně v Java Slides

tomto tutoriálu si ukážeme, jak nastavit invertní barvu výplně pro graf v Java Slides pomocí Aspose.Slides for Java. Invertování barvy výplně je užitečná funkce, když chcete zvýraznit záporné hodnoty v grafu určitou barvou. Poskytneme vám podrobné pokyny a zdrojový kód, jak toho dosáhnout.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Nainstalovaná knihovna Aspose.Slides for Java.
2. Nastavení vývojového prostředí Java.

## Krok 1: Vytvořte prezentaci

Nejprve musíme vytvořit prezentaci, do které přidáme náš graf. K vytvoření prezentace můžete použít následující kód:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf

Dále do prezentace přidáme seskupený sloupcový graf. Můžete to udělat takto:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Krok 3: Nastavení dat grafu

Nyní nastavíme data grafu, včetně řad a kategorií:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nových sérií a kategorií
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Krok 4: Vyplňte data série

Nyní vyplníme data řady pro graf:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Krok 5: Nastavte Invertovat barvu výplně

Chcete-li nastavit invertní barvu výplně pro řadu grafů, můžete použít následující kód:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Ve výše uvedeném kódu nastavíme řadu tak, aby invertovala barvu výplně pro záporné hodnoty a určila barvu pro inverzní výplň.

## Krok 6: Uložte prezentaci

Nakonec uložte prezentaci s grafem:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení Invertního barevného grafu výplně v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Přidávání nových sérií a kategorií
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Vezměte první sérii grafů a naplňte data série.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme vám ukázali, jak nastavit invertní barvu výplně pro graf v Java Slides pomocí Aspose.Slides for Java. Tato funkce vám umožňuje zvýraznit záporné hodnoty v grafech specifickou barvou, díky čemuž jsou vaše data vizuálně informativnější.

## FAQ

V této části se budeme zabývat některými běžnými otázkami souvisejícími s nastavením inverzní barvy výplně pro graf v aplikaci Java Slides pomocí Aspose.Slides for Java.

### Jak nainstaluji Aspose.Slides for Java?

 Aspose.Slides for Java můžete nainstalovat tak, že do svého projektu Java zahrnete soubory JAR Aspose.Slides. Knihovnu si můžete stáhnout z[Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/). Postupujte podle pokynů k instalaci uvedených v dokumentaci pro vaše konkrétní vývojové prostředí.

### Mohu přizpůsobit barvu pro obrácenou výplň v sérii grafů?

Ano, můžete přizpůsobit barvu obrácené výplně v řadě grafů. V uvedeném příkladu kódu je`series.getInvertedSolidFillColor().setColor(Color.RED)` line nastaví barvu na červenou pro obrácenou výplň. Můžete vyměnit`Color.RED` s jakoukoli jinou barvou dle vašeho výběru.

### Jak mohu upravit typ grafu v Aspose.Slides pro Java?

 Typ grafu můžete upravit změnou`ChartType` parametr při přidávání grafu do prezentace. V příkladu kódu jsme použili`ChartType.ClusteredColumn` . Můžete prozkoumat další typy grafů, jako jsou spojnicové grafy, sloupcové grafy, koláčové grafy atd., zadáním příslušného`ChartType` hodnotu enum.

### Jak přidám do grafu více datových řad?

 Chcete-li do grafu přidat více datových řad, můžete použít`chart.getChartData().getSeries().add(...)` pro každou sérii, kterou chcete přidat. Ujistěte se, že jste pro každou řadu poskytli příslušné datové body a štítky, aby se váš graf naplnil několika řadami.

### Existuje způsob, jak přizpůsobit další aspekty vzhledu grafu?

Ano, pomocí Aspose.Slides for Java si můžete přizpůsobit různé aspekty vzhledu grafu, včetně popisků os, nadpisů, legend a dalších. Podrobné pokyny k přizpůsobení prvků grafu a vzhledu najdete v dokumentaci.

### Mohu uložit graf v různých formátech?

 Ano, graf můžete uložit v různých formátech pomocí Aspose.Slides for Java. V uvedeném příkladu kódu jsme prezentaci uložili jako soubor PPTX. Můžete použít různé`SaveFormat` možnosti uložení v jiných formátech, jako je PDF, PNG nebo SVG, v závislosti na vašich požadavcích.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
