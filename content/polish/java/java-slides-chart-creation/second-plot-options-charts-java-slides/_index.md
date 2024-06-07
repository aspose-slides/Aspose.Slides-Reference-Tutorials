---
title: Drugie opcje wykresów w slajdach Java
linktitle: Drugie opcje wykresów w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dostosowywać wykresy w Java Slides za pomocą Aspose.Slides dla Java. Przeglądaj opcje drugiej fabuły i ulepszaj swoje prezentacje.
type: docs
weight: 12
url: /pl/java/chart-creation/second-plot-options-charts-java-slides/
---

## Wprowadzenie do opcji drugiego wykresu dla wykresów w slajdach Java

tym samouczku przyjrzymy się, jak dodać drugie opcje wykresu do wykresów za pomocą Aspose.Slides dla Java. Drugie opcje wykresu umożliwiają dostosowanie wyglądu i zachowania wykresów, szczególnie w scenariuszach takich jak wykresy kołowe. Aby to osiągnąć, udostępnimy instrukcje krok po kroku i przykłady kodu źródłowego. 

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Slides for Java w swoim projekcie Java.

## Krok 1: Utwórz prezentację
Zacznijmy od stworzenia nowej prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu
Następnie dodamy wykres do slajdu. W tym przykładzie utworzymy wykres kołowy:

```java
// Dodaj wykres na slajdzie
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Krok 3: Dostosuj właściwości wykresu
Teraz ustawmy różne właściwości wykresu, w tym opcje drugiego wykresu:

```java
// Pokaż etykiety danych dla pierwszej serii
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ustaw rozmiar drugiego ciasta (w procentach)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Podziel ciasto procentowo
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ustaw pozycję podziału
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Krok 4: Zapisz prezentację
Na koniec zapisz prezentację z wykresem i drugą opcją wykresu:

```java
// Zapisz prezentację na dysku
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla opcji drugiej fabuły

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
// Dodaj wykres na slajdzie
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Ustaw różne właściwości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Zapisz prezentację na dysku
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dodawać drugie opcje wykresu do wykresów w Java Slides przy użyciu Aspose.Slides dla Java. Możesz dostosować różne właściwości, aby poprawić wygląd i funkcjonalność wykresów, dzięki czemu Twoje prezentacje będą bardziej informacyjne i atrakcyjne wizualnie.

## Często zadawane pytania

### Jak zmienić rozmiar drugiego koła na wykresie kołowym?

 Aby zmienić rozmiar drugiego koła na wykresie kołowym, użyj opcji`setSecondPieSize` metodę, jak pokazano w powyższym przykładzie kodu. Dostosuj wartość, aby określić rozmiar w procentach.

###  Co robi`PieSplitBy` control in a Pie of Pie chart?

 The`PieSplitBy` właściwość kontroluje sposób podziału wykresu kołowego. Możesz to ustawić na jedno i drugie`PieSplitType.ByPercentage` Lub`PieSplitType.ByValue` aby podzielić wykres odpowiednio procentowo lub według określonej wartości.

### Jak ustawić pozycję podziału na wykresie kołowym?

Możesz ustawić pozycję podziału na wykresie kołowym za pomocą opcji`setPieSplitPosition` metoda. Dostosuj wartość, aby określić żądaną pozycję.