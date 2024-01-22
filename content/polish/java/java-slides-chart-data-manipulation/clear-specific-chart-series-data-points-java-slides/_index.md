---
title: Wyczyść dane dotyczące punktów danych określonych serii wykresów w slajdach Java
linktitle: Wyczyść dane dotyczące punktów danych określonych serii wykresów w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak wyczyścić określone punkty danych z serii wykresów w Java Slides za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym umożliwiający skuteczne zarządzanie wizualizacją danych.
type: docs
weight: 15
url: /pl/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

## Wprowadzenie do czyszczenia danych punktów danych określonych serii wykresów w slajdach Java

tym samouczku przeprowadzimy Cię przez proces usuwania określonych punktów danych z serii wykresów w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Może to być przydatne, gdy chcesz usunąć określone punkty danych z wykresu w celu aktualizacji lub modyfikacji wizualizacji danych.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że masz zintegrowaną bibliotekę Aspose.Slides for Java ze swoim projektem. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Załaduj prezentację

 Najpierw musimy załadować prezentację PowerPoint zawierającą wykres, który chcesz zmodyfikować. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## Krok 2: Uzyskaj dostęp do wykresu

Następnie uzyskamy dostęp do wykresu ze slajdu. W tym przykładzie zakładamy, że wykres znajduje się na pierwszym slajdzie (slajd o indeksie 0). W razie potrzeby możesz dostosować indeks slajdu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## Krok 3: Wyczyść określone punkty danych

Teraz będziemy iterować po punktach danych pierwszej serii wykresu i usuwać ich wartości X i Y.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

 Ten kod przechodzi przez każdy punkt danych w pierwszej serii (indeks 0) i ustawia wartości X i Y`null`skutecznie usuwając punkty danych.

## Krok 4: Usuń wyczyszczone punkty danych

Aby mieć pewność, że usunięte punkty danych zostaną usunięte z serii, wyczyścimy całą serię.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Ten kod usuwa wszystkie punkty danych z pierwszej serii.

## Krok 5: Zapisz zmodyfikowaną prezentację

Na koniec zapiszemy zmodyfikowaną prezentację w nowym pliku.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy umożliwiający wyczyszczenie danych punktów danych z określonych serii wykresów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

 W tym przewodniku nauczyłeś się, jak usuwać określone punkty danych z serii wykresów w prezentacji programu PowerPoint przy użyciu programu Aspose.Slides dla języka Java. Może to być przydatne, gdy trzeba dynamicznie aktualizować lub modyfikować dane wykresów w aplikacjach Java. Jeśli masz dalsze pytania lub potrzebujesz dodatkowej pomocy, zapoznaj się z sekcją[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Często zadawane pytania

### Jak mogę usunąć określone punkty danych z serii wykresów w Aspose.Slides dla Java?

Aby usunąć określone punkty danych z serii wykresów w Aspose.Slides dla Java, wykonaj następujące kroki:

1. Załaduj prezentację.
2. Uzyskaj dostęp do wykresu na slajdzie.
3. Iteruj po punktach danych żądanej serii i usuń ich wartości X i Y.
4. Wyczyść całą serię, aby usunąć usunięte punkty danych.
5. Zapisz zmodyfikowaną prezentację.

### Czy mogę wyczyścić punkty danych z wielu serii na tym samym wykresie?

Tak, możesz wyczyścić punkty danych z wielu serii na tym samym wykresie, iterując po punktach danych każdej serii i czyszcząc je indywidualnie.

### Czy istnieje sposób na wyczyszczenie punktów danych na podstawie warunku lub kryteriów?

Tak, możesz wyczyścić punkty danych na podstawie warunku, dodając logikę warunkową w pętli, która iteruje przez punkty danych. Możesz sprawdzić wartości punktów danych i zdecydować, czy je wyczyścić, czy nie, w oparciu o swoje kryteria.

### Jak mogę dodać nowe punkty danych do serii wykresów za pomocą Aspose.Slides dla Java?

 Aby dodać nowe punkty danych do serii wykresów, możesz użyć opcji`addDataPoint`metoda serii. Po prostu utwórz nowe punkty danych i dodaj je do serii, korzystając z tej metody.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Slides dla Java?

 Obszerną dokumentację i przykłady można znaleźć w pliku[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).