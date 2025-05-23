---
"description": "Naucz się tworzyć oszałamiające wykresy i zarządzać właściwościami w slajdach Java za pomocą Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym dla potężnych prezentacji."
"linktitle": "Zarządzaj wykresami właściwości w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zarządzaj wykresami właściwości w slajdach Java"
"url": "/pl/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj wykresami właściwości w slajdach Java


## Wprowadzenie do zarządzania właściwościami i wykresami w slajdach Java przy użyciu Aspose.Slides

W tym samouczku pokażemy, jak zarządzać właściwościami i tworzyć wykresy w slajdach Java przy użyciu Aspose.Slides. Aspose.Slides to potężne API Java do pracy z prezentacjami PowerPoint. Przeprowadzimy Cię przez proces krok po kroku, w tym przykłady kodu źródłowego.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides dla Java jest zainstalowana i skonfigurowana w Twoim projekcie. Możesz ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Dodawanie wykresu do slajdu

Aby dodać wykres do slajdu, wykonaj następujące kroki:

1. Zaimportuj niezbędne klasy i utwórz instancję klasy Presentation.

```java
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
```

2. Uzyskaj dostęp do slajdu, do którego chcesz dodać wykres. W tym przykładzie uzyskujemy dostęp do pierwszego slajdu.

```java
// Dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Dodaj wykres z domyślnymi danymi. W tym przypadku dodajemy wykres StackedColumn3D.

```java
// Dodaj wykres z domyślnymi danymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Ustawianie danych wykresu

Aby ustawić dane wykresu, musimy utworzyć skoroszyt danych wykresu i dodać serie i kategorie. Wykonaj następujące kroki:

4. Ustaw indeks arkusza danych wykresu.

```java
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
```

5. Pobierz skoroszyt z danymi wykresu.

```java
// Pobieranie arkusza danych wykresu
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

8. Ustaw osie kąta prostego.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Ustaw kąty obrotu dla osi X i Y. W tym przykładzie obracamy X o 40 stopni, a Y o 270 stopni.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Ustaw głębokość procentową na 150.

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

12. Ustaw wartość nakładania się dla serii. Na przykład możesz ustawić ją na 100, aby nie nakładała się.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Zapisywanie prezentacji

Na koniec zapisz prezentację na dysku.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć wykres kolumnowy 3D ze właściwościami niestandardowymi przy użyciu Aspose.Slides w Javie.

## Kompletny kod źródłowy do zarządzania wykresami właściwości w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
// Dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres z domyślnymi danymi
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Ustaw właściwości Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Weź drugą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniamy dane serii
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

tym samouczku zagłębiliśmy się w świat zarządzania właściwościami i tworzenia wykresów w slajdach Java przy użyciu Aspose.Slides. Aspose.Slides to solidny interfejs API Java, który umożliwia programistom wydajną pracę z prezentacjami PowerPoint. Omówiliśmy podstawowe kroki i dostarczyliśmy przykłady kodu źródłowego, aby przeprowadzić Cię przez ten proces.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu?

Możesz zmienić typ wykresu, modyfikując `ChartType` parametr podczas dodawania wykresu. Zapoznaj się z dokumentacją Aspose.Slides, aby poznać dostępne typy wykresów.

### Czy mogę dostosować kolory wykresu?

Tak, możesz dostosować kolory wykresu, ustawiając właściwości wypełnienia punktów danych serii lub kategorii.

### Jak dodać więcej punktów danych do serii?

Możesz dodać więcej punktów danych do serii, używając `series.getDataPoints().addDataPointForBarSeries()` metodę i określając komórkę zawierającą wartość danych.

### Jak mogę ustawić inny kąt obrotu?

Aby ustawić inny kąt obrotu dla osi X i Y, użyj `chart.getRotation3D().setRotationX()` I `chart.getRotation3D().setRotationY()` żądanymi wartościami kąta.

### Jakie inne właściwości 3D mogę dostosować?

Możesz zapoznać się z dokumentacją Aspose.Slides i poznać inne właściwości wykresu 3D, takie jak głębokość, perspektywa i oświetlenie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}