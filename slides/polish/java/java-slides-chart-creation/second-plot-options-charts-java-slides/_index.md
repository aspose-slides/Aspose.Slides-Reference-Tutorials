---
"description": "Dowiedz się, jak dostosowywać wykresy w Java Slides przy użyciu Aspose.Slides for Java. Poznaj opcje drugiego wykresu i ulepsz swoje prezentacje."
"linktitle": "Drugie opcje wykresów dla wykresów w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Drugie opcje wykresów dla wykresów w slajdach Java"
"url": "/pl/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Drugie opcje wykresów dla wykresów w slajdach Java


## Wprowadzenie do drugich opcji wykresów dla wykresów w slajdach Java

tym samouczku pokażemy, jak dodać drugie opcje wykresu do wykresów za pomocą Aspose.Slides dla Java. Drugie opcje wykresu pozwalają dostosować wygląd i zachowanie wykresów, szczególnie w scenariuszach takich jak wykresy kołowe. Podamy instrukcje krok po kroku i przykłady kodu źródłowego, aby to osiągnąć. 

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Slides for Java w swoim projekcie Java.

## Krok 1: Utwórz prezentację
Zacznijmy od utworzenia nowej prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
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

// Ustaw rozmiar drugiego wykresu kołowego (w procentach)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Podziel ciasto procentowo
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ustaw pozycję podziału
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Krok 4: Zapisz prezentację
Na koniec zapisz prezentację z opcjami wykresu i drugiego wykresu:

```java
// Zapisz prezentację na dysku
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla drugiej opcji wykresu

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
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

W tym samouczku nauczyliśmy się, jak dodawać drugie opcje wykresu do wykresów w Java Slides przy użyciu Aspose.Slides for Java. Możesz dostosować różne właściwości, aby ulepszyć wygląd i funkcjonalność wykresów, dzięki czemu prezentacje będą bardziej informacyjne i atrakcyjne wizualnie.

## Najczęściej zadawane pytania

### Jak mogę zmienić rozmiar drugiego koła na wykresie kołowym?

Aby zmienić rozmiar drugiego koła w wykresie kołowym, użyj `setSecondPieSize` metoda pokazana w przykładzie kodu powyżej. Dostosuj wartość, aby określić rozmiar w procentach.

### Co robi `PieSplitBy` kontrola na wykresie kołowym?

Ten `PieSplitBy` właściwość kontroluje sposób podziału wykresu kołowego. Możesz ustawić ją na `PieSplitType.ByPercentage` Lub `PieSplitType.ByValue` aby podzielić wykres według procentów lub określonej wartości.

### Jak ustawić pozycję podziału na wykresie kołowym?

Pozycję podziału na wykresie kołowym można ustawić za pomocą `setPieSplitPosition` metoda. Dostosuj wartość, aby określić żądaną pozycję.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}