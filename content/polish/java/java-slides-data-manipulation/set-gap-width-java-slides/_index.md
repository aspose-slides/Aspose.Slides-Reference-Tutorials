---
title: Ustaw szerokość przerwy w slajdach Java
linktitle: Ustaw szerokość przerwy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić szerokość przerwy w slajdach Java za pomocą Aspose.Slides dla Java. Ulepsz wizualizacje wykresów w prezentacjach programu PowerPoint.
type: docs
weight: 21
url: /pl/java/data-manipulation/set-gap-width-java-slides/
---

## Wprowadzenie do ustawiania szerokości odstępu w Aspose.Slides dla Java

W tym samouczku przeprowadzimy Cię przez proces ustawiania szerokości odstępu dla wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Szerokość odstępu określa odstępy między kolumnami lub słupkami na wykresie, umożliwiając kontrolowanie wyglądu wykresu.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java. Można go pobrać ze strony Aspose[Tutaj](https://releases.aspose.com/slides/java/).

## Przewodnik krok po kroku

Wykonaj poniższe kroki, aby ustawić szerokość przerwy na wykresie za pomocą Aspose.Slides for Java:

### 1. Utwórz pustą prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
```

### 2. Uzyskaj dostęp do pierwszego slajdu

```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Dodaj wykres z danymi domyślnymi

```java
// Dodaj wykres z danymi domyślnymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Ustaw indeks arkusza danych wykresu

```java
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
```

### 5. Pobierz skoroszyt danych wykresu

```java
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Dodaj serię do wykresu

```java
// Dodaj serię do wykresu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Dodaj kategorie do wykresu

```java
// Dodaj kategorie do wykresu
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Wypełnij dane serii

```java
// Wypełnij dane serii
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Wypełnianie punktów danych serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Ustaw szerokość odstępu

```java
// Ustaw wartość szerokości odstępu
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Zapisz prezentację

```java
// Zapisz prezentację z wykresem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy umożliwiający ustawienie szerokości odstępu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres z danymi domyślnymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Dodaj serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Dodaj kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Weź drugą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ustaw wartość GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Zapisz prezentację z wykresem
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku nauczyłeś się, jak ustawić szerokość odstępu dla wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Dostosowanie szerokości odstępu umożliwia kontrolowanie odstępów między kolumnami lub słupkami na wykresie, poprawiając wizualną reprezentację danych.

## Często zadawane pytania

### Jak zmienić wartość szerokości odstępu?

 Aby zmienić szerokość odstępu, użyj opcji`setGapWidth` metoda na`ParentSeriesGroup` serii wykresów. W podanym przykładzie ustawiliśmy szerokość odstępu na 50, ale możesz dostosować tę wartość do żądanych odstępów.

### Czy mogę dostosować inne właściwości wykresu?

Tak, Aspose.Slides for Java zapewnia szerokie możliwości dostosowywania wykresów. Możesz modyfikować różne właściwości wykresów, takie jak kolory, etykiety, tytuły i inne. Szczegółowe informacje na temat opcji dostosowywania wykresów można znaleźć w dokumentacji API.

### Gdzie mogę znaleźć więcej zasobów i dokumentacji?

 Obszerną dokumentację i dodatkowe zasoby dotyczące Aspose.Slides for Java można znaleźć na stronie[Strona Aspose](https://reference.aspose.com/slides/java/).