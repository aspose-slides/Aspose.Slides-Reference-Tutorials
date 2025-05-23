---
"description": "Twórz wykresy pierścieniowe z niestandardowymi rozmiarami otworów w slajdach Java przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do dostosowywania wykresów."
"linktitle": "Dziura w wykresie pierścieniowym w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dziura w wykresie pierścieniowym w slajdach Java"
"url": "/pl/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dziura w wykresie pierścieniowym w slajdach Java


## Wprowadzenie do wykresu pierścieniowego z dziurą w slajdach Java

W tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu pierścieniowego z otworem przy użyciu Aspose.Slides dla Java. Ten przewodnik krok po kroku przeprowadzi Cię przez proces z przykładami kodu źródłowego.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w Twoim projekcie Java. Możesz ją pobrać ze strony [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Importowanie wymaganych bibliotek

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Zainicjuj prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
```

## Krok 3: Utwórz wykres pierścieniowy

```java
try {
    // Utwórz wykres kołowy na pierwszym slajdzie
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ustaw rozmiar otworu na wykresie pierścieniowym (w procentach)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Zapisz prezentację na dysku
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Usuń obiekt prezentacji
    if (presentation != null) presentation.dispose();
}
```

## Krok 4: Uruchom kod

Uruchom kod Java w swoim IDE lub edytorze tekstu, aby utworzyć wykres pierścieniowy z określonym rozmiarem otworu. Pamiętaj o zastąpieniu `"Your Document Directory"` z rzeczywistą ścieżką, pod którą chcesz zapisać prezentację.

## Kompletny kod źródłowy dla dziury w wykresie pierścieniowym w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Zapisz prezentację na dysku
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się, jak utworzyć wykres pierścieniowy z otworem za pomocą Aspose.Slides dla Java. Możesz dostosować rozmiar otworu, dostosowując `setDoughnutHoleSize` parametr metody.

## Najczęściej zadawane pytania

### Jak mogę zmienić kolor segmentów wykresu?

Aby zmienić kolor segmentów wykresu, możesz użyć `setDataPointsInLegend` metoda na `IChart` obiekt i ustaw żądany kolor dla każdego punktu danych.

### Czy mogę dodawać etykiety do segmentów wykresu pierścieniowego?

Tak, możesz dodawać etykiety do segmentów wykresu pierścieniowego za pomocą `setDataPointsLabelValue` metoda na `IChart` obiekt.

### Czy można dodać tytuł do wykresu?

Oczywiście! Możesz dodać tytuł do wykresu za pomocą `setTitle` metoda na `IChart` obiekt i podając żądany tekst tytułu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}