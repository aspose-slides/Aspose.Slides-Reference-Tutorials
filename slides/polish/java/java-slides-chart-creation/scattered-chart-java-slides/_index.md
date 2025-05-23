---
"description": "Dowiedz się, jak tworzyć wykresy punktowe w Javie przy użyciu Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym Java do wizualizacji danych w prezentacjach."
"linktitle": "Wykres rozproszony w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres rozproszony w slajdach Java"
"url": "/pl/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres rozproszony w slajdach Java


## Wprowadzenie do wykresu rozproszonego w Aspose.Slides dla Java

W tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu punktowego przy użyciu Aspose.Slides dla Java. Wykresy punktowe są przydatne do wizualizacji punktów danych na dwuwymiarowej płaszczyźnie. Zapewnimy instrukcje krok po kroku i dołączymy kod źródłowy Java dla Twojej wygody.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. [Aspose.Slides dla Java](https://products.aspose.com/slides/java) zainstalowano.
2. Skonfigurowano środowisko programistyczne Java.

## Krok 1: Zainicjuj prezentację

Najpierw zaimportuj niezbędne biblioteki i utwórz nową prezentację.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Utwórz nową prezentację
Presentation pres = new Presentation();
```

## Krok 2: Dodaj slajd i utwórz wykres punktowy

Następnie dodaj slajd i utwórz na nim wykres punktowy. Użyjemy `ScatterWithSmoothLines` typ wykresu w tym przykładzie.

```java
// Zobacz pierwszy slajd
ISlide slide = pres.getSlides().get_Item(0);

// Tworzenie wykresu punktowego
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Krok 3: Przygotuj dane wykresu

Teraz przygotujmy dane do naszego wykresu punktowego. Dodamy dwie serie, każda z wieloma punktami danych.

```java
// Pobieranie domyślnego indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;

// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Usuń serię demonstracyjną
chart.getChartData().getSeries().clear();

// Dodaj pierwszą serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Dodaj punkty danych do pierwszej serii
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Edytuj typ serii
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Zmień rozmiar znacznika
series.getMarker().setSymbol(MarkerStyleType.Star); // Zmień symbol znacznika

// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);

// Dodaj punkty danych do drugiej serii
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Zmień styl znacznika dla drugiej serii
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację z wykresem punktowym w pliku PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć wykres punktowy przy użyciu Aspose.Slides dla Java. Teraz możesz dostosować ten przykład dalej, aby odpowiadał Twoim konkretnym wymaganiom dotyczącym danych i projektu.

## Kompletny kod źródłowy dla wykresu rozproszonego w slajdach Java
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Tworzenie domyślnego wykresu
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Pobieranie domyślnego indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Usuń serię demonstracyjną
chart.getChartData().getSeries().clear();
// Dodaj nową serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Dodaj tam nowy punkt (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Dodaj nowy punkt (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Edytuj typ serii
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Zmiana znacznika serii wykresu
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Dodaj tam nowy punkt (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Dodaj nowy punkt (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Dodaj nowy punkt (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Dodaj nowy punkt (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Zmiana znacznika serii wykresu
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku przeprowadziliśmy Cię przez proces tworzenia wykresu punktowego przy użyciu Aspose.Slides dla Java. Wykresy punktowe to potężne narzędzia do wizualizacji punktów danych w przestrzeni dwuwymiarowej, ułatwiające analizę i zrozumienie złożonych relacji danych.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu?

Aby zmienić typ wykresu, użyj `setType` metodę na serii wykresów i podaj żądany typ wykresu. Na przykład, `series.setType(ChartType.Line)` zmieni serię na wykres liniowy.

### Jak dostosować rozmiar i styl znacznika?

Możesz zmienić rozmiar i styl znacznika za pomocą `getMarker` metodę na serii, a następnie ustaw rozmiar i właściwości symbolu. Na przykład:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Więcej opcji dostosowywania znajdziesz w dokumentacji Aspose.Slides for Java.

Pamiętaj o wymianie `"Your Document Directory"` z rzeczywistą ścieżką, pod którą chcesz zapisać prezentację.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}