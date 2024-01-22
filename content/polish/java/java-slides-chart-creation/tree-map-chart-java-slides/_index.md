---
title: Wykres mapy drzewa w slajdach Java
linktitle: Wykres mapy drzewa w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz wykresy mapy drzewa w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do wizualizacji danych hierarchicznych.
type: docs
weight: 13
url: /pl/java/chart-creation/tree-map-chart-java-slides/
---

## Wprowadzenie do wykresu mapy drzewa w slajdach Java

W tym samouczku pokażemy, jak utworzyć wykres mapy drzewa w prezentacji programu PowerPoint przy użyciu biblioteki Aspose.Slides for Java. Wykresy mapy drzewa to skuteczny sposób wizualizacji danych hierarchicznych.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że w projekcie Java masz skonfigurowaną bibliotekę Aspose.Slides for Java.

## Krok 1: Zaimportuj wymagane biblioteki

```java
import com.aspose.slides.*;
```

## Krok 2: Załaduj prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Utwórz wykres mapy drzewa

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    //Utwórz oddział 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // Utwórz oddział 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Dodaj punkty danych
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Zapisz prezentację z wykresem Mapy Drzewa
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kompletny kod źródłowy wykresu mapy drzewa w slajdach Java
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//oddział 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//oddział 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się tworzyć wykres mapy drzewa w prezentacji programu PowerPoint przy użyciu biblioteki Aspose.Slides for Java. Wykresy mapy drzewa są cennym narzędziem do wizualizacji danych hierarchicznych, dzięki czemu Twoje prezentacje są bardziej pouczające i wciągające.

## Często zadawane pytania

### Jak dodać dane do wykresu mapy drzewa?

 Aby dodać dane do wykresu Mapy Drzewa, użyj opcji`series.getDataPoints().addDataPointForTreemapSeries()` metodę, przekazując wartości danych jako parametry.

### Jak mogę dostosować wygląd wykresu mapy drzewa?

 Można dostosować wygląd wykresu mapy drzewa, modyfikując różne właściwości pliku`chart` I`series` obiektów, takich jak kolory, etykiety i układy.

### Czy mogę utworzyć wiele wykresów mapy drzewa w jednej prezentacji?

Tak, możesz utworzyć wiele wykresów Mapy Drzewa w jednej prezentacji, wykonując te same kroki i określając różne pozycje slajdów.

### Jak zapisać prezentację z wykresem Mapy Drzewa?

 Użyj`pres.save()` metoda zapisania prezentacji z wykresem Mapy Drzewa w żądanym formacie (np. PPTX).