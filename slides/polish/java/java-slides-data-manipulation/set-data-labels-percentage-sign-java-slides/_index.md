---
"description": "Dowiedz się, jak ustawiać etykiety danych ze znakami procentowymi w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Twórz angażujące wykresy z instrukcjami krok po kroku i kodem źródłowym."
"linktitle": "Ustaw etykiety danych Znak procentowy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw etykiety danych Znak procentowy w slajdach Java"
"url": "/pl/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw etykiety danych Znak procentowy w slajdach Java


## Wprowadzenie do ustawiania etykiet danych Znak procentowy w Aspose.Slides dla Java

W tym przewodniku przeprowadzimy Cię przez proces ustawiania etykiet danych ze znakiem procentowym przy użyciu Aspose.Slides dla Java. Utworzymy prezentację PowerPoint z wykresem kolumnowym i skonfigurujemy etykiety danych, aby wyświetlały procenty.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java została dodana do Twojego projektu. Możesz ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację

Najpierw utworzymy nową prezentację PowerPoint za pomocą Aspose.Slides.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj slajd i wykres

Następnie dodajemy do prezentacji slajd i wykres kolumnowy.

```java
// Uzyskaj odniesienie do slajdu
ISlide slide = presentation.getSlides().get_Item(0);

// Dodaj wykres kolumnowy procentowy skumulowany na slajdzie
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Krok 3: Skonfiguruj format numeru osi

Aby wyświetlić procenty, musimy skonfigurować format liczbowy dla osi pionowej wykresu.

```java
// Ustaw NumberFormatLinkedToSource na false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Krok 4: Dodaj dane wykresu

Dodajemy dane do wykresu, tworząc serie i punkty danych. W tym przykładzie dodajemy dwie serie z ich odpowiednimi punktami danych.

```java
// Pobieranie arkusza danych wykresu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Dodaj nową serię
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Dodaj nową serię
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Krok 5: Dostosuj etykiety danych

Teraz dostosujemy wygląd etykiet danych.

```java
// Ustawianie właściwości LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Krok 6: Zapisz prezentację

Na koniec zapisujemy prezentację do pliku PowerPoint.

```java
// Zapisz prezentację na dysku
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć prezentację PowerPoint z wykresem kolumnowym i skonfigurować etykiety danych, aby wyświetlały procenty przy użyciu Aspose.Slides dla Java.

## Kompletny kod źródłowy dla zestawu etykiet danych Znak procentowy w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
// Uzyskaj odniesienie do slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres kolumnowy procentowy skumulowany na slajdzie
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Ustaw NumberFormatLinkedToSource na false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Pobieranie arkusza danych wykresu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Dodaj nową serię
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Ustawianie koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ustawianie właściwości LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Dodaj nową serię
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Ustawianie typu wypełnienia i koloru
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Zapisz prezentację na dysku
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Wniosek

Dzięki temu przewodnikowi dowiedziałeś się, jak tworzyć angażujące prezentacje z etykietami danych opartymi na procentach, które mogą być szczególnie przydatne do skutecznego przekazywania informacji w raportach biznesowych, materiałach edukacyjnych i nie tylko.

## Najczęściej zadawane pytania

### Jak mogę zmienić kolory serii wykresów?

Możesz zmienić kolor wypełnienia serii wykresu za pomocą `setFill` metodę jak pokazano w przykładzie.

### Czy mogę dostosować rozmiar czcionki etykiet danych?

Tak, możesz dostosować rozmiar czcionki etykiet danych, ustawiając `setFontHeight` nieruchomość, jak pokazano w kodzie.

### Jak mogę dodać więcej serii do wykresu?

Możesz dodać dodatkowe serie do wykresu, używając `add` metoda na `IChartSeriesCollection` obiekt.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}