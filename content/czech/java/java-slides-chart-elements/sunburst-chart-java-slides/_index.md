---
title: Sunburst Chart v Java Slides
linktitle: Sunburst Chart v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vytvářejte úžasné grafy Sunburst v Java Slides pomocí Aspose.Slides. Naučte se krok za krokem vytvářet grafy a manipulovat s daty.
type: docs
weight: 16
url: /cs/java/chart-elements/sunburst-chart-java-slides/
---

## Úvod do Sunburst Chart v Java Slides s Aspose.Slides

V tomto tutoriálu se naučíte, jak vytvořit graf Sunburst v powerpointové prezentaci pomocí Aspose.Slides for Java API. Graf Sunburst je radiální graf používaný k reprezentaci hierarchických dat. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

Nejprve importujte potřebné knihovny pro práci s Aspose.Slides a vytvořte graf Sunburst ve vaší aplikaci Java.

```java
import com.aspose.slides.*;
```

## Krok 2: Inicializujte prezentaci

Inicializujte prezentaci PowerPoint a určete adresář, do kterého se uloží soubor prezentace.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Vytvořte Sunburst Chart

Vytvořte Sunburst graf na snímku. Určíme polohu (X, Y) a rozměry (šířku, výšku) grafu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Krok 4: Připravte data grafu

Vymažte z grafu všechna existující data kategorií a řad a vytvořte pro graf datový sešit.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Krok 5: Definujte hierarchii grafů

Definujte hierarchickou strukturu grafu Sunburst. Větve, stonky a listy můžete přidat jako kategorie.

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

## Krok 6: Přidejte data do grafu

Přidejte datové body do řady grafů Sunburst.

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

## Kompletní zdrojový kód pro Sunburst Chart v Java Slides

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
	//větev 1
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

tomto tutoriálu jste se naučili, jak vytvořit graf Sunburst v prezentaci PowerPoint pomocí rozhraní Aspose.Slides for Java API. Viděli jste, jak inicializovat prezentaci, vytvořit graf, definovat hierarchii grafu, přidat datové body a uložit prezentaci. Nyní můžete tyto znalosti využít k vytváření interaktivních a informativních grafů Sunburst ve vašich aplikacích Java.

## FAQ

### Jak přizpůsobím vzhled grafu Sunburst?

Vzhled grafu Sunburst můžete přizpůsobit úpravou vlastností, jako jsou barvy, popisky a styly. Podrobné možnosti přizpůsobení naleznete v dokumentaci Aspose.Slides.

### Mohu do grafu přidat další datové body?

 Ano, do grafu můžete přidat další datové body pomocí`series.getDataPoints().addDataPointForSunburstSeries()` pro každý datový bod, který chcete zahrnout.

### Jak mohu přidat popisky do grafu Sunburst?

Chcete-li do grafu Sunburst přidat nápovědu, můžete nastavit formát štítku dat tak, aby se při najetí myší na segmenty grafu zobrazovaly další informace, jako jsou hodnoty nebo popisy.

### Je možné vytvořit interaktivní grafy Sunburst s hypertextovými odkazy?

Ano, můžete vytvářet interaktivní grafy Sunburst s hypertextovými odkazy přidáním hypertextových odkazů na konkrétní prvky grafu nebo segmenty. Podrobnosti o přidávání hypertextových odkazů naleznete v dokumentaci Aspose.Slides.