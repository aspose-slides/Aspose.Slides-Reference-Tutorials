---
"description": "Dowiedz się, jak tworzyć wykresy histogramu w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do wizualizacji danych."
"linktitle": "Wykres histogramu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres histogramu w slajdach Java"
"url": "/pl/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres histogramu w slajdach Java


## Wprowadzenie do wykresu histogramu w slajdach Java przy użyciu Aspose.Slides

W tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu histogramu w prezentacji PowerPoint przy użyciu Aspose.Slides for Java API. Wykres histogramu służy do przedstawiania rozkładu danych w ciągłym przedziale.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java. Możesz ją pobrać ze strony [Strona internetowa Aspose](https://releases.aspose.com/slides/java/).

## Krok 1: Zainicjuj swój projekt

Utwórz projekt Java i uwzględnij bibliotekę Aspose.Slides w zależnościach projektu.

## Krok 2: Importuj niezbędne biblioteki

```java
import com.aspose.slides.*;
```

## Krok 3: Załaduj istniejącą prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Pamiętaj o wymianie `"Your Document Directory"` z rzeczywistą ścieżką do dokumentu PowerPoint.

## Krok 4: Utwórz wykres histogramu

Teraz utwórzmy histogram na slajdzie prezentacji.

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

W tym kodzie najpierw usuwamy wszelkie istniejące kategorie i serie z wykresu. Następnie dodajemy punkty danych do serii za pomocą `getDataPoints().addDataPointForHistogramSeries` metoda. Na koniec ustawiamy typ agregacji osi poziomej na Automatyczny i zapisujemy prezentację.

## Kompletny kod źródłowy dla wykresu histogramu w slajdach Java

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

tym samouczku sprawdziliśmy, jak utworzyć wykres histogramu w prezentacji PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Wykresy histogramu to cenne narzędzia do wizualizacji rozkładu danych w ciągłym przedziale i mogą być potężnym dodatkiem do prezentacji, zwłaszcza w przypadku treści statystycznych lub analitycznych.

## Najczęściej zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Bibliotekę Aspose.Slides for Java można pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji podanymi na ich stronie internetowej.

### Do czego służy wykres histogramu?

Wykres histogramu służy do wizualizacji rozkładu danych w ciągłym przedziale. Jest powszechnie używany w statystyce do przedstawiania rozkładów częstotliwości.

### Czy mogę dostosować wygląd wykresu histogramu?

Tak, możesz dostosować wygląd wykresu, w tym jego kolory, etykiety i osie, korzystając z interfejsu API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}