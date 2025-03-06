---
title: Wykres lejkowy w slajdach Java
linktitle: Wykres lejkowy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Poznaj Aspose.Slides dla języka Java dzięki samouczkom krok po kroku. Twórz wspaniałe wykresy lejkowe i nie tylko.
weight: 14
url: /pl/java/chart-elements/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do wykresu lejkowego w slajdach Java

W tym samouczku pokażemy, jak utworzyć wykres lejkowy za pomocą Aspose.Slides dla Java. Wykresy lejkowe są przydatne do wizualizacji sekwencyjnego procesu z stopniowo zawężającymi się etapami, takimi jak konwersje sprzedażowe lub pozyskiwanie klientów.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że do projektu Java dodano bibliotekę Aspose.Slides. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Zainicjuj prezentację

Na początek zainicjujmy prezentację i dodajmy do niej slajd, na którym umieścimy nasz wykres lejkowy.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do katalogu projektu.

## Krok 2: Utwórz wykres lejkowy

Stwórzmy teraz wykres lejkowy i ustawmy jego wymiary na slajdzie.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

W powyższym kodzie do pierwszego slajdu dodajemy wykres lejkowy o współrzędnych (50, 50) o szerokości 500 i wysokości 400 pikseli.

## Krok 3: Zdefiniuj dane wykresu

Następnie zdefiniujemy dane dla naszego wykresu lejkowego. Ustalimy kategorie i serie dla wykresu.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

Tutaj czyścimy istniejące dane, dodajemy kategorie (w tym przypadku etapy lejka) i ustalamy ich etykiety.

## Krok 4: Dodaj punkty danych

Dodajmy teraz punkty danych do naszej serii wykresów lejkowych.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

Na tym etapie tworzymy serię dla naszego wykresu lejkowego i dodajemy punkty danych reprezentujące wartości na każdym etapie lejka.

## Krok 5: Zapisz prezentację

Na koniec zapisujemy prezentację wraz z wykresem lejkowym do pliku PowerPoint.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Pamiętaj o wymianie`"Your Document Directory"` z żądaną lokalizacją zapisu.

## Kompletny kod źródłowy wykresu lejkowego w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku pokazaliśmy, jak utworzyć wykres lejkowy w Java Slides przy użyciu Aspose.Slides dla Java. Możesz dodatkowo dostosować wykres, dostosowując kolory, etykiety i inne właściwości do swoich konkretnych potrzeb.

## Często zadawane pytania

### Jak mogę dostosować wygląd wykresu lejkowego?

Możesz dostosować wygląd wykresu lejkowego, modyfikując właściwości wykresu, serii i punktów danych. Szczegółowe opcje dostosowywania można znaleźć w dokumentacji Aspose.Slides.

### Czy mogę dodać więcej kategorii lub punktów danych do wykresu lejkowego?

Tak, możesz dodać więcej kategorii i punktów danych do wykresu lejkowego, odpowiednio rozszerzając kod w kroku 3 i kroku 4.

### Czy można zmienić typ wykresu na inny niż lejkowy?

 Tak, Aspose.Slides obsługuje różne typy wykresów. Typ wykresu można zmienić, zastępując go`ChartType.Funnel` z żądanym typem wykresu w kroku 2.

### Jak radzić sobie z błędami lub wyjątkami podczas pracy z Aspose.Slides?

Błędy i wyjątki można obsługiwać za pomocą standardowych mechanizmów obsługi wyjątków Java. Upewnij się, że w kodzie masz odpowiednią obsługę błędów, aby sprawnie obsługiwać nieoczekiwane sytuacje.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji dla Aspose.Slides dla Java?

 Więcej przykładów i szczegółową dokumentację dotyczącą korzystania z Aspose.Slides dla Java można znaleźć w pliku[dokumentacja](https://docs.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
