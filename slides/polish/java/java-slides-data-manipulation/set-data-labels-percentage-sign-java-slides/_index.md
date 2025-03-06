---
title: Ustaw znak procentowy etykiet danych w slajdach Java
linktitle: Ustaw znak procentowy etykiet danych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić etykiety danych ze znakami procentowymi w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Twórz atrakcyjne wykresy, korzystając ze wskazówek krok po kroku i kodu źródłowego.
weight: 17
url: /pl/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw znak procentowy etykiet danych w slajdach Java


## Wprowadzenie do ustawiania znaku procentowego etykiet danych w Aspose.Slides dla Java

tym przewodniku przeprowadzimy Cię przez proces ustawiania etykiet danych ze znakiem procentu za pomocą Aspose.Slides dla Java. Stworzymy prezentację PowerPoint ze skumulowanym wykresem kolumnowym i skonfigurujemy etykiety danych tak, aby wyświetlały wartości procentowe.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że do projektu dodano bibliotekę Aspose.Slides for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację

Najpierw tworzymy nową prezentację programu PowerPoint za pomocą Aspose.Slides.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj slajd i wykres

Następnie do prezentacji dodajemy slajd i skumulowany wykres kolumnowy.

```java
// Uzyskaj odniesienie do slajdu
ISlide slide = presentation.getSlides().get_Item(0);

// Dodaj wykres PercentsStackedColumn na slajdzie
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Krok 3: Skonfiguruj format numeru osi

Aby wyświetlić wartości procentowe, musimy skonfigurować format liczb dla osi pionowej wykresu.

```java
// Ustaw NumberFormatLinkedToSource na false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Krok 4: Dodaj dane wykresu

Dodajemy dane do wykresu tworząc serie i punkty danych. W tym przykładzie dodajemy dwie serie z odpowiadającymi im punktami danych.

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

Teraz dostosujmy wygląd etykiet danych.

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

Otóż to! Pomyślnie utworzyłeś prezentację programu PowerPoint ze skumulowanym wykresem kolumnowym i skonfigurowałeś etykiety danych do wyświetlania wartości procentowych za pomocą Aspose.Slides for Java.

## Kompletny kod źródłowy dla zestawu etykiet danych procentowego logowania w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
// Uzyskaj odniesienie do slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres PercentsStackedColumn na slajdzie
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
// Ustawianie typu i koloru wypełnienia
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

Postępując zgodnie z tym przewodnikiem, nauczyłeś się tworzyć atrakcyjne prezentacje z etykietami danych procentowymi, które mogą być szczególnie przydatne do skutecznego przekazywania informacji w raportach biznesowych, materiałach edukacyjnych i nie tylko.

## Często zadawane pytania

### Jak mogę zmienić kolory serii wykresów?

 Kolor wypełnienia serii wykresów można zmienić za pomocą opcji`setFill` sposób pokazany w przykładzie.

### Czy mogę dostosować rozmiar czcionki etykiet danych?

Tak, możesz dostosować rozmiar czcionki etykiet danych, ustawiając opcję`setFontHeight` właściwość, jak pokazano w kodzie.

### Jak dodać więcej serii do wykresu?

 Możesz dodać dodatkowe serie do wykresu, korzystając z opcji`add` metoda na`IChartSeriesCollection` obiekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
