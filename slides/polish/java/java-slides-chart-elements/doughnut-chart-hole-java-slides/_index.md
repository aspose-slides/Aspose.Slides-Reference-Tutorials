---
title: Dziura w wykresie pierścieniowym w slajdach Java
linktitle: Dziura w wykresie pierścieniowym w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz wykresy pierścieniowe z niestandardowymi rozmiarami otworów w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym umożliwiającym dostosowanie wykresu.
weight: 11
url: /pl/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do wykresu pierścieniowego z dziurą w slajdach Java

W tym samouczku poprowadzimy Cię przez proces tworzenia wykresu pierścieniowego z dziurą przy użyciu Aspose.Slides dla Java. Ten przewodnik krok po kroku przeprowadzi Cię przez proces z przykładami kodu źródłowego.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Można go pobrać z[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Zaimportuj wymagane biblioteki

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

// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

## Krok 3: Utwórz wykres pierścieniowy

```java
try {
    // Utwórz wykres pierścieniowy na pierwszym slajdzie
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ustaw rozmiar dziury na wykresie pierścieniowym (w procentach)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Zapisz prezentację na dysku
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Pozbądź się przedmiotu prezentacji
    if (presentation != null) presentation.dispose();
}
```

## Krok 4: Uruchom kod

 Uruchom kod Java w swoim IDE lub edytorze tekstu, aby utworzyć wykres pierścieniowy z określonym rozmiarem dziury. Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką, w której chcesz zapisać prezentację.

## Kompletny kod źródłowy dziury w wykresie pierścieniowym w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
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

 W tym samouczku nauczyłeś się tworzyć wykres pierścieniowy z dziurą za pomocą Aspose.Slides dla Java. Rozmiar otworu można dostosować, regulując`setDoughnutHoleSize` parametr metody.

## Często zadawane pytania

### Jak mogę zmienić kolor segmentów wykresu?

 Aby zmienić kolor segmentów wykresu, możesz użyć opcji`setDataPointsInLegend` metoda na`IChart` obiektu i ustaw żądany kolor dla każdego punktu danych.

### Czy mogę dodać etykiety do segmentów wykresu pierścieniowego?

 Tak, możesz dodawać etykiety do segmentów wykresu pierścieniowego za pomocą`setDataPointsLabelValue` metoda na`IChart` obiekt.

### Czy jest możliwość dodania tytułu do wykresu?

 Z pewnością! Możesz dodać tytuł do wykresu za pomocą`setTitle` metoda na`IChart` obiekt i podając żądany tekst tytułu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
