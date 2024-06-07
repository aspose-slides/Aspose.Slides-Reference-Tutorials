---
title: Istniejący wykres w slajdach Java
linktitle: Istniejący wykres w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz swoje prezentacje PowerPoint za pomocą Aspose.Slides dla Java. Dowiedz się, jak programowo modyfikować istniejące wykresy. Przewodnik krok po kroku z kodem źródłowym umożliwiającym dostosowanie wykresu.
type: docs
weight: 12
url: /pl/java/chart-elements/existing-chart-java-slides/
---

## Wprowadzenie do istniejącego wykresu w slajdach Java przy użyciu Aspose.Slides dla Java

W tym samouczku pokażemy, jak zmodyfikować istniejący wykres w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Przeprowadzimy przez kolejne kroki, aby zmienić dane wykresu, nazwy kategorii, nazwy serii i dodać nową serię do wykresu. Upewnij się, że w swoim projekcie masz skonfigurowane Aspose.Slides for Java.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Biblioteka Aspose.Slides for Java zawarta w Twoim projekcie.
2. Istniejąca prezentacja programu PowerPoint z wykresem, który chcesz zmodyfikować.
3. Skonfigurowano środowisko programistyczne Java.

## Krok 1: Załaduj prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Klasa prezentacji instancji reprezentująca plik PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Krok 2: Uzyskaj dostęp do slajdu i wykresu

```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide sld = pres.getSlides().get_Item(0);

// Uzyskaj dostęp do wykresu na slajdzie
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Krok 3: Zmień dane wykresu i nazwy kategorii

```java
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;

// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Zmień nazwy kategorii wykresów
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Krok 4: Zaktualizuj pierwszą serię wykresów

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Zaktualizuj nazwę serii
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Zaktualizuj dane serii
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Krok 5: Zaktualizuj drugą serię wykresów

```java
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);

// Zaktualizuj nazwę serii
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Zaktualizuj dane serii
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Krok 6: Dodaj nową serię do wykresu

```java
// Dodanie nowej serii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Weź trzecią serię wykresów
series = chart.getChartData().getSeries().get_Item(2);

// Wypełnij dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Krok 7: Zmień typ wykresu

```java
//Zmień typ wykresu na Cylinder klastrowany
chart.setType(ChartType.ClusteredCylinder);
```

## Krok 8: Zapisz zmodyfikowaną prezentację

```java
// Zapisz prezentację ze zmodyfikowanym wykresem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulacje! Pomyślnie zmodyfikowałeś istniejący wykres w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Możesz teraz używać tego kodu do programowego dostosowywania wykresów w prezentacjach programu PowerPoint.

## Kompletny kod źródłowy istniejącego wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Klasa prezentacji instancji reprezentującej plik PPTX// Klasa prezentacji instancji reprezentującej plik PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Uzyskaj dostęp do pierwszego slideMarkera
ISlide sld = pres.getSlides().get_Item(0);
// Dodaj wykres z danymi domyślnymi
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Zmiana nazwy kategorii wykresu
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Teraz aktualizuję dane serii
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modyfikowanie nazwy serii
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Teraz aktualizuję dane serii
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modyfikowanie nazwy serii
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Teraz dodaję nową serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Weź trzecią serię wykresów
series = chart.getChartData().getSeries().get_Item(2);
//Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Zapisz prezentację z wykresem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Wniosek

tym obszernym samouczku nauczyliśmy się, jak modyfikować istniejący wykres w prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java. Postępując zgodnie ze szczegółowym przewodnikiem i wykorzystując przykłady kodu źródłowego, możesz łatwo dostosowywać i aktualizować wykresy, aby spełniały Twoje specyficzne wymagania. Oto podsumowanie tego, co omówiliśmy:

## Często zadawane pytania

### Jak mogę zmienić typ wykresu?

 Typ wykresu można zmienić za pomocą opcji`chart.setType(ChartType.ChartTypeHere)` metoda. Zastępować`ChartTypeHere` z żądanym typem wykresu, np`ChartType.ClusteredCylinder` w naszym przykładzie.

### Czy mogę dodać więcej punktów danych do serii?

 Tak, możesz dodać więcej punktów danych do serii za pomocą`series.getDataPoints().addDataPointForBarSeries(cell)` metoda. Upewnij się, że podałeś odpowiednie dane komórki.

### Jak zaktualizować nazwy kategorii?

 Możesz zaktualizować nazwy kategorii za pomocą`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` aby ustawić nowe nazwy kategorii.

### Jak modyfikować nazwy serii?

 Aby zmodyfikować nazwy serii, użyj`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` aby ustawić nazwy nowych serii.

### Czy istnieje sposób na usunięcie serii z wykresu?

 Tak, możesz usunąć serię z wykresu za pomocą`chart.getChartData().getSeries().removeAt(index)` metoda, gdzie`index`to indeks serii, którą chcesz usunąć.