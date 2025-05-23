---
"description": "Naucz się tworzyć wykresy lejkowe w prezentacjach PowerPoint za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do efektywnej wizualizacji danych."
"linktitle": "Wykres lejkowy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres lejkowy w slajdach Java"
"url": "/pl/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres lejkowy w slajdach Java


## Wprowadzenie do tworzenia wykresu lejkowego w Aspose.Slides dla Java

tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu lejkowego w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Wykresy lejkowe są przydatne do wizualizacji danych, które stopniowo zawężają się lub „przechodzą” przez różne etapy lub kategorie. Zapewnimy instrukcje krok po kroku wraz z kodem źródłowym, aby pomóc Ci to osiągnąć.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- Biblioteka Aspose.Slides for Java została zainstalowana i skonfigurowana w projekcie.
- Plik prezentacji PowerPoint (PPTX), do którego chcesz wstawić wykres lejkowy.

## Krok 1: Importuj Aspose.Slides dla Java

Najpierw musisz zaimportować bibliotekę Aspose.Slides for Java do swojego projektu Java. Upewnij się, że dodałeś niezbędne zależności do konfiguracji kompilacji.

```java
import com.aspose.slides.*;
```

## Krok 2: Zainicjuj prezentację i wykres

W tym kroku inicjujemy prezentację i dodajemy wykres lejkowy do slajdu.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Dodaj wykres lejkowy do pierwszego slajdu na współrzędnych (50, 50) i wymiarach (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Krok 3: Zdefiniuj dane wykresu

Następnie definiujemy dane dla naszego Funnel Chart. Możesz dostosować kategorie i punkty danych zgodnie ze swoimi wymaganiami.

```java
// Wyczyść istniejące dane wykresu.
wb.clear(0);

// Zdefiniuj kategorie dla wykresu.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Dodaj punkty danych dla serii wykresów lejkowych.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Krok 4: Zapisz prezentację

Na koniec zapisujemy prezentację z wykresem lejkowym do określonego pliku.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć wykres lejkowy za pomocą Aspose.Slides dla Java i wstawić go do prezentacji PowerPoint.

## Kompletny kod źródłowy dla wykresu lejkowego w slajdach Java

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

W tym przewodniku krok po kroku pokazaliśmy, jak utworzyć wykres lejkowy w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Wykresy lejkowe są cennym narzędziem do wizualizacji danych, które podążają za postępem lub zawężającym się wzorcem, ułatwiając skuteczne przekazywanie informacji. 

## Najczęściej zadawane pytania

### Jak mogę dostosować wygląd wykresu lejkowego?

Możesz dostosować wygląd wykresu lejkowego, modyfikując różne właściwości wykresu, takie jak kolory, etykiety i style. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat opcji dostosowywania wykresu.

### Czy mogę dodać więcej punktów danych lub kategorii do wykresu lejkowego?

Tak, możesz dodać dodatkowe punkty danych i kategorie do wykresu lejkowego, rozszerzając kod podany w kroku 3. Wystarczy, że w razie potrzeby dodasz więcej etykiet kategorii i punktów danych.

### Jak mogę zmienić położenie i rozmiar wykresu lejkowego na slajdzie?

Możesz dostosować położenie i rozmiar wykresu lejkowego, modyfikując współrzędne i wymiary podane podczas dodawania wykresu do slajdu w kroku 2. Zaktualizuj odpowiednio wartości (50, 50, 500, 400).

### Czy mogę wyeksportować wykres do innych formatów, np. PDF lub obrazu?

Tak, Aspose.Slides dla Java pozwala eksportować prezentację z wykresem lejkowym do różnych formatów, w tym PDF, formatów obrazów i innych. Możesz użyć `SaveFormat` opcje umożliwiające określenie pożądanego formatu wyjściowego podczas zapisywania prezentacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}