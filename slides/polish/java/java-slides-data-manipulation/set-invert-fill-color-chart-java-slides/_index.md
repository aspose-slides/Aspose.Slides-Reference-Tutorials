---
title: Ustaw tabelę kolorów odwróconego wypełnienia w slajdach Java
linktitle: Ustaw tabelę kolorów odwróconego wypełnienia w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić odwracanie kolorów wypełnienia wykresów Java Slides za pomocą Aspose.Slides. Ulepsz swoje wizualizacje wykresów dzięki temu przewodnikowi krok po kroku i kodowi źródłowemu.
weight: 22
url: /pl/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw tabelę kolorów odwróconego wypełnienia w slajdach Java


## Wprowadzenie do ustawiania tabeli kolorów odwróconego wypełnienia w slajdach Java

tym samouczku pokażemy, jak ustawić odwrócony kolor wypełnienia wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Odwracanie koloru wypełnienia jest przydatną funkcją, gdy chcesz wyróżnić wartości ujemne na wykresie określonym kolorem. Dostarczymy instrukcje krok po kroku i kod źródłowy, jak to osiągnąć.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowana biblioteka Aspose.Slides dla Java.
2. Skonfigurowano środowisko programistyczne Java.

## Krok 1: Utwórz prezentację

Najpierw musimy stworzyć prezentację, do której dodamy nasz wykres. Aby utworzyć prezentację, możesz użyć poniższego kodu:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Następnie do prezentacji dodamy grupowany wykres kolumnowy. Oto jak możesz to zrobić:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Krok 3: Skonfiguruj dane wykresu

Teraz skonfigurujmy dane wykresu, w tym serie i kategorie:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Dodawanie nowych serii i kategorii
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Krok 4: Wypełnij dane serii

Teraz wypełnijmy dane serii dla wykresu:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Krok 5: Ustaw Odwróć kolor wypełnienia

Aby ustawić odwrócony kolor wypełnienia serii wykresów, możesz użyć następującego kodu:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

W powyższym kodzie ustawiamy serię tak, aby odwracała kolor wypełnienia dla wartości ujemnych i określała kolor odwróconego wypełnienia.

## Krok 6: Zapisz prezentację

Na koniec zapisz prezentację z wykresem:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy zestawu odwracania tabeli kolorów wypełnienia w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Dodawanie nowych serii i kategorii
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Weź pierwszą serię wykresów i wypełnij dane serii.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku pokazaliśmy, jak ustawić odwrócony kolor wypełnienia wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Ta funkcja umożliwia wyróżnianie wartości ujemnych na wykresach określonym kolorem, dzięki czemu dane stają się bardziej wizualne.

## Często zadawane pytania

W tej sekcji zajmiemy się niektórymi typowymi pytaniami związanymi z ustawianiem odwróconego koloru wypełnienia wykresu w Java Slides przy użyciu Aspose.Slides dla Java.

### Jak zainstalować Aspose.Slides dla Java?

 Możesz zainstalować Aspose.Slides dla Java, dołączając pliki JAR Aspose.Slides do swojego projektu Java. Bibliotekę można pobrać ze strony[Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji konkretnego środowiska programistycznego.

### Czy mogę dostosować kolor odwróconego wypełnienia serii wykresów?

Tak, możesz dostosować kolor odwróconego wypełnienia serii wykresów. W podanym przykładzie kodu`series.getInvertedSolidFillColor().setColor(Color.RED)` line ustawia kolor odwróconego wypełnienia na czerwony. Możesz wymienić`Color.RED` z dowolnym innym wybranym kolorem.

### Jak mogę zmodyfikować typ wykresu w Aspose.Slides dla Java?

 Typ wykresu można modyfikować, zmieniając`ChartType` parametr podczas dodawania wykresu do prezentacji. W przykładzie kodu użyliśmy`ChartType.ClusteredColumn` . Możesz eksplorować inne typy wykresów, takie jak wykresy liniowe, wykresy słupkowe, wykresy kołowe itp., określając odpowiednie`ChartType` wartość wyliczeniowa.

### Jak dodać wiele serii danych do wykresu?

 Aby dodać wiele serii danych do wykresu, możesz użyć opcji`chart.getChartData().getSeries().add(...)` metodę dla każdej serii, którą chcesz dodać. Upewnij się, że dla każdej serii podano odpowiednie punkty danych i etykiety, aby zapełnić wykres wieloma seriami.

### Czy istnieje sposób na dostosowanie innych aspektów wyglądu wykresu?

Tak, możesz dostosować różne aspekty wyglądu wykresu, w tym etykiety osi, tytuły, legendy i inne elementy, używając Aspose.Slides for Java. Szczegółowe wskazówki dotyczące dostosowywania elementów wykresu i wyglądu można znaleźć w dokumentacji.

### Czy mogę zapisać wykres w różnych formatach?

 Tak, możesz zapisać wykres w różnych formatach, używając Aspose.Slides for Java. W podanym przykładzie kodu zapisaliśmy prezentację jako plik PPTX. Możesz użyć innego`SaveFormat` opcje zapisania go w innych formatach, takich jak PDF, PNG lub SVG, w zależności od wymagań.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
