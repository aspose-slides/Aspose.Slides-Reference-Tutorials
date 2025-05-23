---
"description": "Naučte se, jak nastavit invertované barvy výplně pro grafy v Java Slides pomocí Aspose.Slides. Vylepšete vizualizace grafů pomocí tohoto podrobného návodu a zdrojového kódu."
"linktitle": "Nastavení invertovaného barevného grafu výplně v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení invertovaného barevného grafu výplně v Java Slides"
"url": "/cs/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení invertovaného barevného grafu výplně v Java Slides


## Úvod do nastavení invertované výplně barev v Java Slides

V tomto tutoriálu si ukážeme, jak nastavit invertovanou barvu výplně pro graf v Java Slides pomocí Aspose.Slides for Java. Invertování barvy výplně je užitečná funkce, pokud chcete zvýraznit záporné hodnoty v grafu určitou barvou. Poskytneme podrobné pokyny a zdrojový kód, jak toho dosáhnout.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Nainstalována knihovna Aspose.Slides pro Javu.
2. Nastavení vývojového prostředí v Javě.

## Krok 1: Vytvořte prezentaci

Nejprve musíme vytvořit prezentaci, do které přidáme náš graf. K vytvoření prezentace můžete použít následující kód:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Dále do prezentace přidáme shlukový sloupcový graf. Zde je návod, jak to udělat:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Krok 3: Nastavení dat grafu

Nyní si nastavme data grafu, včetně řad a kategorií:

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

## Krok 4: Naplnění dat série

Nyní naplňme graf daty řady:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Krok 5: Nastavení invertované barvy výplně

Chcete-li nastavit invertovanou barvu výplně pro sérii grafů, můžete použít následující kód:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Ve výše uvedeném kódu nastavíme sérii tak, aby invertovala barvu výplně pro záporné hodnoty a určíme barvu pro invertovanou výplň.

## Krok 6: Uložte prezentaci

Nakonec uložte prezentaci s grafem:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení invertované výplně barevného grafu v Java Slides

```java
// Cesta k adresáři s dokumenty.
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
// Vezměte si první sérii grafů a naplňte ji daty z řady.
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

V tomto tutoriálu jsme vám ukázali, jak nastavit invertovanou barvu výplně pro graf v Java Slides pomocí Aspose.Slides pro Javu. Tato funkce umožňuje zvýraznit záporné hodnoty v grafech určitou barvou, čímž se vaše data stanou vizuálně informativnějšími.

## Často kladené otázky

V této části se budeme zabývat některými běžnými otázkami týkajícími se nastavení invertované barvy výplně grafu v Java Slides pomocí Aspose.Slides pro Javu.

### Jak nainstaluji Aspose.Slides pro Javu?

Aspose.Slides pro Javu můžete nainstalovat zahrnutím souborů Aspose.Slides JAR do vašeho projektu Java. Knihovnu si můžete stáhnout z [Stránka ke stažení Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/)Postupujte podle pokynů k instalaci uvedených v dokumentaci pro vaše konkrétní vývojové prostředí.

### Mohu si přizpůsobit barvu pro invertovanou výplň v sérii grafů?

Ano, barvu invertované výplně v grafu si můžete přizpůsobit. V uvedeném příkladu kódu `series.getInvertedSolidFillColor().setColor(Color.RED)` Čára nastaví barvu invertované výplně na červenou. Můžete nahradit `Color.RED` s jakoukoli jinou barvou dle vašeho výběru.

### Jak mohu upravit typ grafu v Aspose.Slides pro Javu?

Typ grafu můžete upravit změnou `ChartType` parametr při přidávání grafu do prezentace. V příkladu kódu jsme použili `ChartType.ClusteredColumn`Můžete prozkoumat další typy grafů, jako jsou spojnicové grafy, sloupcové grafy, koláčové grafy atd., zadáním příslušných `ChartType` hodnota výčtu.

### Jak přidám do grafu více datových řad?

Chcete-li do grafu přidat více datových řad, můžete použít `chart.getChartData().getSeries().add(...)` metodu pro každou řadu, kterou chcete přidat. Ujistěte se, že jste pro každou řadu poskytli příslušné datové body a popisky, aby se váš graf mohl naplnit více řadami.

### Existuje způsob, jak přizpůsobit další aspekty vzhledu grafu?

Ano, pomocí Aspose.Slides pro Javu si můžete přizpůsobit různé aspekty vzhledu grafu, včetně popisků os, nadpisů, legend a dalších prvků. Podrobné pokyny k přizpůsobení prvků a vzhledu grafu naleznete v dokumentaci.

### Mohu graf uložit v různých formátech?

Ano, graf můžete uložit v různých formátech pomocí Aspose.Slides pro Javu. V uvedeném příkladu kódu jsme prezentaci uložili jako soubor PPTX. Můžete použít různé `SaveFormat` možnosti uložení v jiných formátech, jako je PDF, PNG nebo SVG, v závislosti na vašich požadavcích.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}