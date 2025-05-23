---
"description": "Dowiedz się, jak ustawić odwrócone kolory wypełnienia dla wykresów Java Slides przy użyciu Aspose.Slides. Ulepsz swoje wizualizacje wykresów dzięki temu przewodnikowi krok po kroku i kodowi źródłowemu."
"linktitle": "Ustaw odwrócony wykres kolorów wypełnienia w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw odwrócony wykres kolorów wypełnienia w slajdach Java"
"url": "/pl/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw odwrócony wykres kolorów wypełnienia w slajdach Java


## Wprowadzenie do Ustaw Odwróć Wypełnienie Kolorem Wykresu w Slajdach Java

W tym samouczku pokażemy, jak ustawić kolor wypełnienia odwróconego dla wykresu w Java Slides przy użyciu Aspose.Slides for Java. Odwrócenie koloru wypełnienia jest przydatną funkcją, gdy chcesz wyróżnić wartości ujemne na wykresie określonym kolorem. Podamy instrukcje krok po kroku i kod źródłowy, aby to osiągnąć.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano bibliotekę Aspose.Slides for Java.
2. Konfiguracja środowiska programistycznego Java.

## Krok 1: Utwórz prezentację

Najpierw musimy utworzyć prezentację, do której dodamy nasz wykres. Możesz użyć następującego kodu, aby utworzyć prezentację:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Następnie dodamy do prezentacji wykres kolumnowy klastrowany. Oto jak możesz to zrobić:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Krok 3: Skonfiguruj dane wykresu

Teraz skonfigurujemy dane wykresu, uwzględniając serie i kategorie:

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

## Krok 5: Ustaw kolor wypełnienia odwrotnego

Aby ustawić kolor wypełnienia odwróconego dla serii wykresów, możesz użyć następującego kodu:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

W powyższym kodzie ustawiamy serię tak, aby odwrócić kolor wypełnienia dla wartości ujemnych i określamy kolor dla odwróconego wypełnienia.

## Krok 6: Zapisz prezentację

Na koniec zapisz prezentację z wykresem:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla zestawu odwróć wykres kolorów wypełnienia w slajdach Java

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
// Weź pierwszą serię wykresów i wypełnij dane szeregowe.
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

W tym samouczku pokazaliśmy, jak ustawić kolor wypełnienia odwróconego dla wykresu w Java Slides przy użyciu Aspose.Slides for Java. Ta funkcja umożliwia wyróżnienie wartości ujemnych na wykresach określonym kolorem, dzięki czemu dane stają się bardziej pouczające wizualnie.

## Najczęściej zadawane pytania

W tej sekcji odpowiemy na kilka typowych pytań związanych z ustawianiem odwróconego koloru wypełnienia wykresu w Java Slides przy użyciu Aspose.Slides for Java.

### Jak zainstalować Aspose.Slides dla Java?

Możesz zainstalować Aspose.Slides dla Java, dołączając pliki JAR Aspose.Slides do swojego projektu Java. Możesz pobrać bibliotekę z [Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji dla Twojego konkretnego środowiska programistycznego.

### Czy mogę dostosować kolor wypełnienia odwróconego w serii wykresów?

Tak, możesz dostosować kolor wypełnienia odwróconego w serii wykresów. W podanym przykładzie kodu, `series.getInvertedSolidFillColor().setColor(Color.RED)` linia ustawia kolor na czerwony dla odwróconego wypełnienia. Możesz zastąpić `Color.RED` z dowolnym innym kolorem według własnego wyboru.

### Jak mogę zmodyfikować typ wykresu w Aspose.Slides dla Java?

Możesz zmienić typ wykresu, zmieniając `ChartType` parametr podczas dodawania wykresu do prezentacji. W przykładzie kodu użyliśmy `ChartType.ClusteredColumn`Możesz eksplorować inne typy wykresów, takie jak wykresy liniowe, wykresy słupkowe, wykresy kołowe itp., określając odpowiedni `ChartType` wartość wyliczeniowa.

### Jak dodać wiele serii danych do wykresu?

Aby dodać wiele serii danych do wykresu, możesz użyć `chart.getChartData().getSeries().add(...)` metoda dla każdej serii, którą chcesz dodać. Upewnij się, że podajesz odpowiednie punkty danych i etykiety dla każdej serii, aby wypełnić wykres wieloma seriami.

### Czy istnieje sposób na dostosowanie innych aspektów wyglądu wykresu?

Tak, możesz dostosować różne aspekty wyglądu wykresu, w tym etykiety osi, tytuły, legendy i inne, używając Aspose.Slides dla Java. Zapoznaj się z dokumentacją, aby uzyskać szczegółowe wskazówki dotyczące dostosowywania elementów wykresu i wyglądu.

### Czy mogę zapisać wykres w różnych formatach?

Tak, możesz zapisać wykres w różnych formatach, używając Aspose.Slides dla Java. W podanym przykładzie kodu zapisaliśmy prezentację jako plik PPTX. Możesz użyć różnych `SaveFormat` opcje zapisu w innych formatach, takich jak PDF, PNG lub SVG, w zależności od Twoich wymagań.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}