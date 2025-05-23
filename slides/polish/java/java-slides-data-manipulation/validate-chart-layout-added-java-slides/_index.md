---
"description": "Opanuj walidację układu wykresu w programie PowerPoint z Aspose.Slides dla Java. Naucz się manipulować wykresami programowo, aby tworzyć oszałamiające prezentacje."
"linktitle": "Sprawdź układ wykresu dodany w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Sprawdź układ wykresu dodany w slajdach Java"
"url": "/pl/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sprawdź układ wykresu dodany w slajdach Java


## Wprowadzenie do walidacji układu wykresu w Aspose.Slides dla Java

W tym samouczku pokażemy, jak sprawdzić układ wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Ta biblioteka umożliwia programową pracę z prezentacjami PowerPoint, ułatwiając manipulowanie i sprawdzanie poprawności różnych elementów, w tym wykresów.

## Krok 1: Inicjalizacja prezentacji

Najpierw musimy zainicjować obiekt prezentacji i załadować istniejącą prezentację PowerPoint. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji (`test.pptx` w tym przykładzie).

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 2: Dodawanie wykresu

Następnie dodamy wykres do prezentacji. W tym przykładzie dodajemy wykres kolumnowy klastrowany, ale możesz zmienić `ChartType` w razie potrzeby.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Krok 3: Weryfikacja układu wykresu

Teraz sprawdzimy układ wykresu za pomocą `validateChartLayout()` Metoda ta zapewnia, że wykres jest prawidłowo rozłożony na slajdzie.

```java
chart.validateChartLayout();
```

## Krok 4: Pobieranie pozycji i rozmiaru wykresu

Po sprawdzeniu układu wykresu możesz chcieć pobrać informacje o jego położeniu i rozmiarze. Możemy uzyskać rzeczywiste współrzędne X i Y, a także szerokość i wysokość obszaru wykresu.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Krok 5: Zapisywanie prezentacji

Na koniec nie zapomnij zapisać zmodyfikowanej prezentacji. W tym przykładzie zapisujemy ją jako `Result.pptx`, ale jeśli zajdzie taka potrzeba, możesz podać inną nazwę pliku.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Pełny kod źródłowy dla układu wykresu walidacyjnego dodany do slajdów Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Zapisywanie prezentacji
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku zagłębiliśmy się w świat pracy z wykresami w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java. Omówiliśmy podstawowe kroki, aby sprawdzić układ wykresu, pobrać jego pozycję i rozmiar oraz zapisać zmodyfikowaną prezentację. Oto krótkie podsumowanie:

## Najczęściej zadawane pytania

### Jak zmienić typ wykresu?

Aby zmienić typ wykresu, wystarczy go zastąpić `ChartType.ClusteredColumn` żądanym typem wykresu w `addChart()` metoda.

### Czy mogę dostosować dane na wykresie?

Tak, możesz dostosować dane wykresu, dodając i modyfikując serie danych, kategorie i wartości. Więcej szczegółów znajdziesz w dokumentacji Aspose.Slides.

### Co zrobić, jeśli chcę zmodyfikować inne właściwości wykresu?

Możesz uzyskać dostęp do różnych właściwości wykresu i dostosować je do swoich wymagań. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać kompleksowe informacje na temat manipulacji wykresem.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}