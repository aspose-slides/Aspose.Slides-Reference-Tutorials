---
"description": "Dowiedz się, jak tworzyć slajdy Java z domyślnymi znacznikami na wykresach, używając Aspose.Slides for Java. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Domyślne znaczniki w wykresie w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Domyślne znaczniki w wykresie w slajdach Java"
"url": "/pl/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Domyślne znaczniki w wykresie w slajdach Java


## Wprowadzenie do domyślnych znaczników w wykresie w Java Slajdy

W tym samouczku pokażemy, jak utworzyć wykres z domyślnymi znacznikami przy użyciu Aspose.Slides dla Java. Domyślne znaczniki to symbole lub kształty dodawane do punktów danych na wykresie w celu ich wyróżnienia. Utworzymy wykres liniowy ze znacznikami w celu wizualizacji danych.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w projekcie Java.

## Krok 1: Utwórz prezentację

Najpierw utwórzmy prezentację i dodajmy do niej slajd. Następnie dodamy wykres do slajdu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Krok 2: Dodaj wykres liniowy ze znacznikami

Teraz dodajmy wykres liniowy ze znacznikami do slajdu. Wyczyścimy również wszystkie domyślne dane z wykresu.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 3: Wypełnij dane wykresu

Wypełnimy wykres przykładowymi danymi. W tym przykładzie utworzymy dwie serie z punktami danych i kategoriami.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Seria 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Seria 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Wypełnianie danych serii
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Krok 4: Dostosuj wykres

Możesz dodatkowo dostosować wykres, na przykład dodając legendę i zmieniając jego wygląd.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację z wykresem w wybranym miejscu.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

To wszystko! Stworzyłeś wykres liniowy z domyślnymi znacznikami przy użyciu Aspose.Slides dla Java.

## Kompletny kod źródłowy dla domyślnych znaczników w wykresie w slajdach Java

```java
        // Ścieżka do katalogu dokumentów.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Weź drugą serię wykresów
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Teraz wypełniamy dane serii
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Wniosek

tym kompleksowym samouczku nauczyłeś się, jak tworzyć slajdy Java z domyślnymi znacznikami na wykresach przy użyciu Aspose.Slides for Java. Omówiliśmy cały proces, od konfiguracji prezentacji po dostosowanie wyglądu wykresu i zapisanie wyniku.

## Najczęściej zadawane pytania

### Jak mogę zmienić symbole znaczników?

Możesz dostosować symbole znaczników, ustawiając styl znacznika dla każdego punktu danych. Użyj `IDataPoint.setMarkerStyle()` aby zmienić symbol znacznika.

### Jak mogę dostosować kolory wykresu?

Aby zmienić kolory wykresu, możesz użyć `IChartSeriesFormat` I `IShapeFillFormat` interfejsy umożliwiające ustawienie właściwości wypełnienia i linii.

### Czy mogę dodać etykiety do punktów danych?

Tak, możesz dodawać etykiety do punktów danych za pomocą `IDataPoint.getLabel()` metodę i dostosować ją według potrzeb.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}