---
title: Zarządzaj wykresami właściwości w slajdach Java
linktitle: Zarządzaj wykresami właściwości w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Naucz się tworzyć wspaniałe wykresy i zarządzać właściwościami slajdów Java za pomocą Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym umożliwiającym tworzenie potężnych prezentacji.
type: docs
weight: 13
url: /pl/java/data-manipulation/manage-properties-charts-java-slides/
---

## Wprowadzenie do zarządzania właściwościami i wykresami w slajdach Java przy użyciu Aspose.Slides

W tym samouczku omówimy, jak zarządzać właściwościami i tworzyć wykresy na slajdach Java za pomocą Aspose.Slides. Aspose.Slides to potężny interfejs API Java do pracy z prezentacjami programu PowerPoint. Przeprowadzimy Cię przez proces krok po kroku, włączając przykłady kodu źródłowego.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides dla Java w swoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Dodawanie wykresu do slajdu

Aby dodać wykres do slajdu, wykonaj następujące kroki:

1. Zaimportuj niezbędne klasy i utwórz instancję klasy Prezentacja.

```java
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

2. Przejdź do slajdu, do którego chcesz dodać wykres. W tym przykładzie uzyskujemy dostęp do pierwszego slajdu.

```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Dodaj wykres z danymi domyślnymi. W tym przypadku dodajemy wykres StackedColumn3D.

```java
// Dodaj wykres z danymi domyślnymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Ustawianie danych wykresu

Aby ustawić dane wykresu, musimy utworzyć skoroszyt danych wykresu i dodać serie i kategorie. Wykonaj następujące kroki:

4. Ustaw indeks arkusza danych wykresu.

```java
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
```

5. Pobierz skoroszyt danych wykresu.

```java
//Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Dodaj serię do wykresu. W tym przykładzie dodajemy dwie serie o nazwach „Seria 1” i „Seria 2”.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Dodaj kategorie do wykresu. Tutaj dodajemy trzy kategorie.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Ustawianie właściwości obrotu 3D

Teraz ustawmy właściwości obrotu 3D dla wykresu:

8. Ustaw osie pod kątem prostym.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Ustaw kąty obrotu dla osi X i Y. W tym przykładzie obracamy X o 40 stopni, a Y o 270 stopni.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Ustaw procent głębokości na 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Wypełnianie danych serii

11. Weź drugą serię wykresów i wypełnij ją punktami danych.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Wypełnij dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Regulacja nakładania się

12. Ustaw wartość nakładania się serii. Na przykład możesz ustawić wartość 100, aby uniknąć nakładania się.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Zapisywanie prezentacji

Na koniec zapisz prezentację na dysku.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Otóż to! Pomyślnie utworzyłeś skumulowany wykres kolumnowy 3D z niestandardowymi właściwościami przy użyciu Aspose.Slides w Javie.

## Kompletny kod źródłowy do zarządzania wykresami właściwości w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres z danymi domyślnymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
//Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Dodaj serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Dodaj kategorie
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ustaw właściwości Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Weź drugą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ustaw wartość OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Zapisz prezentację na dysku
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku zagłębiliśmy się w świat zarządzania właściwościami i tworzenia wykresów na slajdach Java za pomocą Aspose.Slides. Aspose.Slides to solidny interfejs API Java, który umożliwia programistom efektywną pracę z prezentacjami programu PowerPoint. Omówiliśmy najważniejsze kroki i udostępniliśmy przykłady kodu źródłowego, które poprowadzą Cię przez cały proces.

## Często zadawane pytania

### Jak mogę zmienić typ wykresu?

 Typ wykresu można zmienić, modyfikując plik`ChartType`parametr podczas dodawania wykresu. Informacje o dostępnych typach wykresów można znaleźć w dokumentacji Aspose.Slides.

### Czy mogę dostosować kolory wykresów?

Tak, możesz dostosować kolory wykresu, ustawiając właściwości wypełnienia punktów danych serii lub kategorii.

### Jak dodać więcej punktów danych do serii?

 Możesz dodać więcej punktów danych do serii, korzystając z opcji`series.getDataPoints().addDataPointForBarSeries()` metody i określenie komórki zawierającej wartość danych.

### Jak ustawić inny kąt obrotu?

 Aby ustawić inny kąt obrotu dla osi X i Y, należy użyć`chart.getRotation3D().setRotationX()` I`chart.getRotation3D().setRotationY()` z żądanymi wartościami kąta.

### Jakie inne właściwości 3D mogę dostosować?

Możesz poznać inne właściwości 3D wykresu, takie jak głębokość, perspektywa i oświetlenie, odwołując się do dokumentacji Aspose.Slides.