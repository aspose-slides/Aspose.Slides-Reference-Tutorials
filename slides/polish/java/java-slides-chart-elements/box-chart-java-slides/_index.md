---
"description": "Dowiedz się, jak tworzyć wykresy pudełkowe w prezentacjach Java za pomocą Aspose.Slides. Dołączony przewodnik krok po kroku i kod źródłowy do efektywnej wizualizacji danych."
"linktitle": "Wykres pudełkowy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres pudełkowy w slajdach Java"
"url": "/pl/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres pudełkowy w slajdach Java


## Wprowadzenie do wykresu pudełkowego w Aspose.Slides dla Java

tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu pudełkowego przy użyciu Aspose.Slides dla Java. Wykresy pudełkowe są przydatne do wizualizacji danych statystycznych z różnymi kwartylami i wartościami odstającymi. Zapewnimy instrukcje krok po kroku wraz z kodem źródłowym, aby pomóc Ci zacząć.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Biblioteka Aspose.Slides for Java została zainstalowana i skonfigurowana.
- Skonfigurowano środowisko programistyczne Java.

## Krok 1: Zainicjuj prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

W tym kroku zainicjujemy obiekt prezentacji, korzystając ze ścieżki do istniejącego pliku programu PowerPoint (w tym przykładzie „test.pptx”).

## Krok 2: Utwórz wykres pudełkowy

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

W tym kroku tworzymy kształt Box Chart na pierwszym slajdzie prezentacji. Usuwamy również wszelkie istniejące kategorie i serie z wykresu.

## Krok 3: Zdefiniuj kategorie

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

W tym kroku definiujemy kategorie dla wykresu pudełkowego. Używamy `IChartDataWorkbook` aby dodać kategorie i odpowiednio je oznaczyć.

## Krok 4: Utwórz serię

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Tutaj tworzymy serię BoxAndWhisker dla wykresu i konfigurujemy różne opcje, takie jak metoda kwartyli, linia średnia, znaczniki średniej, punkty wewnętrzne i punkty odstające.

## Krok 5: Dodaj punkty danych

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

W tym kroku dodajemy punkty danych do serii BoxAndWhisker. Te punkty danych reprezentują dane statystyczne dla wykresu.

## Krok 6: Zapisz prezentację

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Na koniec zapisujemy prezentację z wykresem pudełkowym do nowego pliku programu PowerPoint o nazwie „BoxAndWhisker.pptx”.

Gratulacje! Udało Ci się utworzyć wykres pudełkowy przy użyciu Aspose.Slides dla Java. Możesz dostosować wykres dalej, dostosowując różne właściwości i dodając więcej punktów danych w razie potrzeby.

## Kompletny kod źródłowy dla wykresu pudełkowego w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak utworzyć wykres pudełkowy przy użyciu Aspose.Slides dla Java. Wykresy pudełkowe to cenne narzędzia do wizualizacji danych statystycznych, w tym kwartyli i wartości odstających. Udostępniliśmy przewodnik krok po kroku wraz z kodem źródłowym, aby pomóc Ci rozpocząć tworzenie wykresów pudełkowych w aplikacjach Java.

## Najczęściej zadawane pytania

### Jak mogę zmienić wygląd wykresu pudełkowego?

Możesz dostosować wygląd wykresu pudełkowego, modyfikując właściwości, takie jak style linii, kolory i czcionki. Zapoznaj się z dokumentacją Aspose.Slides for Java, aby uzyskać szczegółowe informacje na temat dostosowywania wykresu.

### Czy mogę dodać dodatkowe serie danych do wykresu pudełkowego?

Tak, możesz dodać wiele serii danych do wykresu pudełkowego, tworząc dodatkowe `IChartSeries` obiektów i dodawanie do nich punktów danych.

### Co oznacza QuartileMethodType.Exclusive?

Ten `QuartileMethodType.Exclusive` ustawienie określa, że obliczenia kwartyli powinny być wykonywane przy użyciu metody wyłącznej. Możesz wybrać różne metody obliczania kwartyli w zależności od danych i wymagań.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}