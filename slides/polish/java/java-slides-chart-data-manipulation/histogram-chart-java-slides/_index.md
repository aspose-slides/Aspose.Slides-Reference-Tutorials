---
title: Wykres histogramu w slajdach Java
linktitle: Wykres histogramu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć wykresy histogramów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do wizualizacji danych.
weight: 19
url: /pl/java/chart-data-manipulation/histogram-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do wykresu histogramu w slajdach Java przy użyciu Aspose.Slides

W tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu histogramu w prezentacji programu PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Wykres histogramu służy do przedstawienia rozkładu danych w ciągłym przedziale czasu.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java. Można go pobrać z[Strona Aspose](https://releases.aspose.com/slides/java/).

## Krok 1: Zainicjuj swój projekt

Utwórz projekt Java i dołącz bibliotekę Aspose.Slides do zależności swojego projektu.

## Krok 2: Zaimportuj niezbędne biblioteki

```java
import com.aspose.slides.*;
```

## Krok 3: Załaduj istniejącą prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do dokumentu programu PowerPoint.

## Krok 4: Utwórz wykres histogramu

Utwórzmy teraz wykres histogramu na slajdzie w prezentacji.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Dodaj punkty danych do serii
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Ustaw typ agregacji osi poziomej na Automatyczny
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Zapisz prezentację
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 W tym kodzie najpierw usuwamy z wykresu wszelkie istniejące kategorie i serie. Następnie dodajemy punkty danych do serii za pomocą`getDataPoints().addDataPointForHistogramSeries` metoda. Na koniec ustawiamy typ agregacji osi poziomej na Automatyczny i zapisujemy prezentację.

## Kompletny kod źródłowy wykresu histogramu w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku omówiliśmy, jak utworzyć wykres histogramu w prezentacji programu PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Wykresy histogramowe to cenne narzędzia do wizualizacji rozkładu danych w ciągłym przedziale czasu i mogą stanowić potężny dodatek do prezentacji, zwłaszcza gdy mamy do czynienia z treściami statystycznymi lub analitycznymi.

## Często zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

 Możesz pobrać bibliotekę Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji podanymi na ich stronie internetowej.

### Do czego służy wykres histogramu?

Wykres histogramu służy do wizualizacji rozkładu danych w ciągłym przedziale czasu. Jest powszechnie stosowany w statystykach do przedstawiania rozkładów częstotliwości.

### Czy mogę dostosować wygląd wykresu histogramu?

Tak, możesz dostosować wygląd wykresu, w tym jego kolory, etykiety i osie, korzystając z interfejsu API Aspose.Slides.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
