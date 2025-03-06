---
title: Wykres mapy w slajdach Java
linktitle: Wykres mapy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz oszałamiające wykresy map w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku i kod źródłowy dla programistów Java.
weight: 15
url: /pl/java/chart-elements/map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wykres mapy w slajdach Java


## Wprowadzenie do mapy mapy w Java Slides przy użyciu Aspose.Slides dla Java

W tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu mapy w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Wykresy mapowe to świetny sposób na wizualizację danych geograficznych w prezentacjach.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zintegrowaną bibliotekę Aspose.Slides for Java z projektem Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Skonfiguruj swój projekt

Upewnij się, że skonfigurowałeś projekt Java i dodałeś bibliotekę Aspose.Slides for Java do ścieżki klas swojego projektu.

## Krok 2: Utwórz prezentację programu PowerPoint

Najpierw utwórzmy nową prezentację programu PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 3: Dodaj wykres mapy

Teraz do prezentacji dodamy wykres mapy.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Krok 4: Dodaj dane do wykresu mapy

Dodajmy trochę danych do wykresu mapy. Utworzymy serię i dodamy do niej punkty danych.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Krok 5: Dodaj kategorie

Musimy dodać kategorie do wykresu mapy, reprezentujące różne regiony geograficzne.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Krok 6: Dostosuj punkty danych

Możesz dostosować poszczególne punkty danych. W tym przykładzie zmieniamy kolor i wartość określonego punktu danych.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 7: Zapisz prezentację

Na koniec zapisz prezentację z wykresem mapy.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

Otóż to! Utworzyłeś wykres mapy w prezentacji programu PowerPoint przy użyciu programu Aspose.Slides for Java. Możesz dodatkowo dostosować wykres i poznać inne funkcje oferowane przez Aspose.Slides, aby ulepszyć swoje prezentacje.

## Kompletny kod źródłowy wykresu mapy w slajdach Java

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//utwórz pusty wykres
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Dodaj serię i kilka punktów danych
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//dodaj kategorie
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//zmienić wartość punktu danych
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//ustaw wygląd punktu danych
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

tym samouczku omówiliśmy proces tworzenia wykresu mapy w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Wykresy map to skuteczny sposób wizualizacji danych geograficznych, dzięki czemu Twoje prezentacje są bardziej wciągające i pouczające. Podsumujmy kluczowe kroki:

## Często zadawane pytania

### Jak mogę zmienić typ wykresu mapy?

 Typ wykresu można zmienić, zastępując go`ChartType.Map` z żądanym typem wykresu podczas tworzenia wykresu w kroku 3.

### Jak mogę dostosować wygląd wykresu mapy?

 Możesz dostosować wygląd wykresu, modyfikując właściwości pliku`dataPoint` obiekt w kroku 6. Możesz zmieniać kolory, wartości i nie tylko.

### Czy mogę dodać więcej punktów danych i kategorii?

 Tak, możesz dodać dowolną liczbę punktów danych i kategorii. Po prostu skorzystaj z`series.getDataPoints().addDataPointForMapSeries()` I`chart.getChartData().getCategories().add()` metody ich dodawania.

### Jak zintegrować Aspose.Slides for Java z moim projektem?

 Pobierz bibliotekę z[Tutaj](https://releases.aspose.com/slides/java/) i dodaj go do ścieżki klas swojego projektu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
