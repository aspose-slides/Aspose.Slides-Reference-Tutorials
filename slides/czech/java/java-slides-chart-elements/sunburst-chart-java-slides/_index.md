---
"description": "Vytvořte úžasné Sunburst grafy v Java Slides s Aspose.Slides. Naučte se krok za krokem vytvářet grafy a manipulovat s daty."
"linktitle": "Sunburst graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Sunburst graf v Javě Slides"
"url": "/cs/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sunburst graf v Javě Slides


## Úvod do Sunburst Chart v Javě - Slides s Aspose.Slides

V tomto tutoriálu se naučíte, jak vytvořit graf Sunburst v prezentaci PowerPointu pomocí rozhraní Aspose.Slides pro Java API. Graf Sunburst je radiální graf používaný k reprezentaci hierarchických dat. Poskytneme podrobné pokyny spolu se zdrojovým kódem.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

Nejprve importujte potřebné knihovny pro práci s Aspose.Slides a vytvořte graf Sunburst ve vaší aplikaci Java.

```java
import com.aspose.slides.*;
```

## Krok 2: Inicializace prezentace

Inicializujte prezentaci v PowerPointu a zadejte adresář, kam bude soubor prezentace uložen.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Vytvořte graf Sunburst

Vytvořte na snímku graf Sunburst. Určíme pozici (X, Y) a rozměry (šířka, výška) grafu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Krok 4: Příprava dat grafu

Odstraňte z grafu všechny existující kategorie a data řad a vytvořte pro graf datový sešit.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Krok 5: Definování hierarchie grafů

Definujte hierarchickou strukturu grafu Sunburst. Jako kategorie můžete přidat větve, stonky a listy.

```java
// Pobočka 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Pobočka 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Krok 6: Přidání dat do grafu

Přidejte datové body do série grafů Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Krok 7: Uložte prezentaci

Nakonec uložte prezentaci s grafem Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro Sunburst Chart v Javě Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//pobočka 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//větev 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit graf Sunburst v prezentaci PowerPointu pomocí rozhraní Aspose.Slides pro Java API. Viděli jste, jak inicializovat prezentaci, vytvořit graf, definovat hierarchii grafů, přidat datové body a uložit prezentaci. Nyní můžete tyto znalosti využít k vytváření interaktivních a informativních grafů Sunburst ve vašich aplikacích Java.

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled grafu Sunburst?

Vzhled grafu Sunburst si můžete přizpůsobit úpravou vlastností, jako jsou barvy, popisky a styly. Podrobné možnosti přizpůsobení naleznete v dokumentaci k Aspose.Slides.

### Mohu do grafu přidat další datové body?

Ano, do grafu můžete přidat další datové body pomocí `series.getDataPoints().addDataPointForSunburstSeries()` metodu pro každý datový bod, který chcete zahrnout.

### Jak mohu přidat popisky do grafu Sunburst?

Chcete-li do grafu Sunburst přidat popisky, můžete nastavit formát popisků dat tak, aby se při najetí myší na segmenty grafu zobrazovaly další informace, jako jsou hodnoty nebo popisy.

### Je možné vytvářet interaktivní Sunburst grafy s hypertextovými odkazy?

Ano, interaktivní grafy Sunburst s hypertextovými odkazy můžete vytvářet přidáním hypertextových odkazů na konkrétní prvky nebo segmenty grafu. Podrobnosti o přidávání hypertextových odkazů naleznete v dokumentaci k Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}