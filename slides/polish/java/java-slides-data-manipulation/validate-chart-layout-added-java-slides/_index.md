---
title: Sprawdź układ wykresu dodany w slajdach Java
linktitle: Sprawdź układ wykresu dodany w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Sprawdzanie poprawności układu wykresu głównego w programie PowerPoint za pomocą Aspose.Slides dla języka Java. Naucz się programowo manipulować wykresami, aby uzyskać wspaniałe prezentacje.
weight: 10
url: /pl/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do sprawdzania układu wykresu w Aspose.Slides dla Java

W tym samouczku przyjrzymy się, jak sprawdzić układ wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Ta biblioteka umożliwia programową pracę z prezentacjami programu PowerPoint, ułatwiając manipulowanie i sprawdzanie różnych elementów, w tym wykresów.

## Krok 1: Inicjowanie prezentacji

 Najpierw musimy zainicjować obiekt prezentacji i załadować istniejącą prezentację programu PowerPoint. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji (`test.pptx` w tym przykładzie).

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 2: Dodawanie wykresu

 Następnie dodamy wykres do prezentacji. W tym przykładzie dodajemy grupowany wykres kolumnowy, ale możesz zmienić`ChartType` w razie potrzeby.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Krok 3: Sprawdzanie układu wykresu

 Teraz sprawdzimy układ wykresu za pomocą metody`validateChartLayout()` metoda. Dzięki temu wykres będzie prawidłowo ułożony na slajdzie.

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

 Na koniec nie zapomnij zapisać zmodyfikowanej prezentacji. W tym przykładzie zapisujemy go jako`Result.pptx`, ale w razie potrzeby możesz określić inną nazwę pliku.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do sprawdzania układu wykresu dodany w slajdach Java

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

W tym samouczku zagłębiliśmy się w świat pracy z wykresami w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java. Omówiliśmy podstawowe kroki, aby sprawdzić układ wykresu, pobrać jego położenie i rozmiar oraz zapisać zmodyfikowaną prezentację. Oto krótkie podsumowanie:

## Często zadawane pytania

### Jak zmienić typ wykresu?

 Aby zmienić typ wykresu, po prostu zamień`ChartType.ClusteredColumn` żądanym typem wykresu w pliku`addChart()` metoda.

### Czy mogę dostosować dane wykresu?

Tak, możesz dostosować dane wykresu, dodając i modyfikując serie danych, kategorie i wartości. Więcej szczegółów znajdziesz w dokumentacji Aspose.Slides.

### Co się stanie, jeśli chcę zmodyfikować inne właściwości wykresu?

Możesz uzyskać dostęp do różnych właściwości wykresów i dostosować je do swoich wymagań. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać wyczerpujące informacje na temat manipulacji wykresami.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
