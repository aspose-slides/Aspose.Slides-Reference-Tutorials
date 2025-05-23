---
"description": "Ulepsz swoje prezentacje PowerPoint dzięki Aspose.Slides for Java. Naucz się programowo modyfikować istniejące wykresy. Przewodnik krok po kroku z kodem źródłowym do dostosowywania wykresów."
"linktitle": "Istniejący wykres w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Istniejący wykres w slajdach Java"
"url": "/pl/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Istniejący wykres w slajdach Java


## Wprowadzenie do istniejących wykresów w slajdach Java przy użyciu Aspose.Slides dla Java

tym samouczku pokażemy, jak zmodyfikować istniejący wykres w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Przejdziemy przez kroki, aby zmienić dane wykresu, nazwy kategorii, nazwy serii i dodać nową serię do wykresu. Upewnij się, że Aspose.Slides for Java jest skonfigurowany w Twoim projekcie.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Biblioteka Aspose.Slides for Java dołączona do projektu.
2. Istniejąca prezentacja programu PowerPoint zawierająca wykres, który chcesz zmodyfikować.
3. Konfiguracja środowiska programistycznego Java.

## Krok 1: Załaduj prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz klasę prezentacji reprezentującą plik PPTX
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

## Krok 4: Aktualizacja pierwszej serii wykresów

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aktualizuj nazwę serii
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Aktualizuj dane serii
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Krok 5: Aktualizacja drugiej serii wykresów

```java
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);

// Aktualizuj nazwę serii
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Aktualizuj dane serii
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Krok 6: Dodaj nową serię do wykresu

```java
// Dodawanie nowej serii
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
// Zmień typ wykresu na Cylindryczny klaster
chart.setType(ChartType.ClusteredCylinder);
```

## Krok 8: Zapisz zmodyfikowaną prezentację

```java
// Zapisz prezentację ze zmodyfikowanym wykresem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulacje! Udało Ci się zmodyfikować istniejący wykres w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Teraz możesz użyć tego kodu, aby programowo dostosować wykresy w prezentacjach PowerPoint.

## Kompletny kod źródłowy dla istniejącego wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz klasę prezentacji reprezentującą plik PPTX// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Uzyskaj dostęp do pierwszego slideMarkera
ISlide sld = pres.getSlides().get_Item(0);
// Dodaj wykres z domyślnymi danymi
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
// Aktualizowanie danych serii
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modyfikowanie nazwy serii
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Aktualizowanie danych serii
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modyfikowanie nazwy serii
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Teraz dodajemy nową serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Weź 3 serię wykresów
series = chart.getChartData().getSeries().get_Item(2);
// Teraz wypełniamy dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Zapisz prezentację z wykresem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Wniosek

W tym kompleksowym samouczku nauczyliśmy się, jak modyfikować istniejący wykres w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Postępując zgodnie z przewodnikiem krok po kroku i wykorzystując przykłady kodu źródłowego, możesz łatwo dostosowywać i aktualizować wykresy, aby spełniały Twoje specyficzne wymagania. Oto podsumowanie tego, co omówiliśmy:

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu?

Możesz zmienić typ wykresu, używając `chart.setType(ChartType.ChartTypeHere)` metoda. Zastąp `ChartTypeHere` z wybranym typem wykresu, takim jak `ChartType.ClusteredCylinder` naszym przykładzie.

### Czy mogę dodać więcej punktów danych do serii?

Tak, możesz dodać więcej punktów danych do serii za pomocą `series.getDataPoints().addDataPointForBarSeries(cell)` metoda. Upewnij się, że podajesz właściwe dane komórki.

### Jak aktualizować nazwy kategorii?

Nazwy kategorii można aktualizować za pomocą `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` aby ustawić nowe nazwy kategorii.

### Jak modyfikować nazwy serii?

Aby zmienić nazwy serii, użyj `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` aby ustalić nowe nazwy serii.

### Czy istnieje sposób na usunięcie serii z wykresu?

Tak, możesz usunąć serię z wykresu, używając `chart.getChartData().getSeries().removeAt(index)` metoda, gdzie `index` jest indeksem serii, którą chcesz usunąć.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}