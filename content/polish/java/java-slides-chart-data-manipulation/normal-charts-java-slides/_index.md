---
title: Normalne wykresy w slajdach Java
linktitle: Normalne wykresy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz normalne wykresy w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku i kod źródłowy tworzenia, dostosowywania i zapisywania wykresów w prezentacjach programu PowerPoint.
type: docs
weight: 21
url: /pl/java/chart-data-manipulation/normal-charts-java-slides/
---

## Wprowadzenie do normalnych wykresów w slajdach Java

W tym samouczku omówimy proces tworzenia normalnych wykresów w Java Slides przy użyciu Aspose.Slides for Java API. Użyjemy instrukcji krok po kroku wraz z kodem źródłowym, aby zademonstrować, jak utworzyć grupowany wykres kolumnowy w prezentacji PowerPoint.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano Aspose.Slides dla Java API.
2. Skonfigurowano środowisko programistyczne Java.
3. Podstawowa znajomość programowania w języku Java.

## Krok 1: Konfiguracja projektu

Upewnij się, że masz katalog dla swojego projektu. Nazwijmy go „Katalogiem Twoich dokumentów”, jak wspomniano w kodzie. Możesz zastąpić to rzeczywistą ścieżką do katalogu projektu.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Krok 2: Tworzenie prezentacji

Utwórzmy teraz prezentację programu PowerPoint i uzyskaj dostęp do jej pierwszego slajdu.

```java
// Klasa prezentacji instancji reprezentująca plik PPTX
Presentation pres = new Presentation();
// Uzyskaj dostęp do pierwszego slajdu
ISlide sld = pres.getSlides().get_Item(0);
```

## Krok 3: Dodawanie wykresu

Do slajdu dodamy grupowany wykres kolumnowy i ustalimy jego tytuł.

```java
// Dodaj wykres z danymi domyślnymi
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Tytuł tabeli ustawień
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 4: Ustawianie danych wykresu

Następnie ustalimy dane wykresu, definiując serie i kategorie.

```java
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;

//Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Usuń domyślnie wygenerowane serie i kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Dodawanie nowej serii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Dodawanie nowych kategorii
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Krok 5: Wypełnianie danych serii

Teraz wypełnijmy punkty danych serii dla wykresu.

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Wypełnianie danych serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ustawianie koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);

// Wypełnianie danych serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ustawianie koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 6: Dostosowywanie etykiet

Dostosujmy etykiety danych dla serii wykresów.

```java
// Pierwsza etykieta będzie zawierać nazwę kategorii
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Pokaż wartość trzeciej etykiety z nazwą serii i separatorem
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Krok 7: Zapisywanie prezentacji

Na koniec zapisz prezentację z wykresem w katalogu projektu.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Otóż to! Pomyślnie utworzyłeś grupowany wykres kolumnowy w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Możesz dodatkowo dostosować ten wykres do swoich wymagań.

## Kompletny kod źródłowy normalnych wykresów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Klasa prezentacji instancji reprezentująca plik PPTX
Presentation pres = new Presentation();
// Uzyskaj dostęp do pierwszego slajdu
ISlide sld = pres.getSlides().get_Item(0);
// Dodaj wykres z danymi domyślnymi
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Tytuł tabeli ustawień
// Chart.getChartTitle().getTextFrameForOverriding().setText("Przykładowy tytuł");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
//Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Usuń domyślnie wygenerowane serie i kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Dodawanie nowej serii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Dodawanie nowych kategorii
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ustawianie koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ustawianie koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//Pierwsza etykieta wyświetli nazwę kategorii
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Pokaż wartość trzeciej etykiety
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Zapisz prezentację z wykresem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Wniosek

W tym samouczku nauczyliśmy się, jak tworzyć normalne wykresy w Java Slides przy użyciu Aspose.Slides for Java API. Przeszliśmy przez przewodnik krok po kroku z kodem źródłowym, jak utworzyć grupowany wykres kolumnowy w prezentacji programu PowerPoint.

## Często zadawane pytania

### Jak mogę zmienić typ wykresu?

 Aby zmienić typ wykresu, zmodyfikuj plik`ChartType` parametr podczas dodawania wykresu za pomocą`sld.getShapes().addChart()`. Możesz wybierać spośród różnych typów wykresów dostępnych w Aspose.Slides.

### Czy mogę zmienić kolory serii wykresów?

 Tak, możesz zmienić kolory serii wykresów, ustawiając kolor wypełnienia dla każdej serii`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Jak dodać więcej kategorii lub serii do wykresu?

 Możesz dodać więcej kategorii lub serii do wykresu, dodając nowe punkty danych i etykiety za pomocą przycisku`chart.getChartData().getCategories().add()` I`chart.getChartData().getSeries().add()` metody.

### Jak mogę bardziej dostosować tytuł wykresu?

 Możesz dodatkowo dostosować tytuł wykresu, modyfikując właściwości`chart.getChartTitle()` takie jak wyrównanie tekstu, rozmiar czcionki i kolor.

### Jak zapisać wykres w innym formacie pliku?

Aby zapisać wykres w innym formacie pliku, zmień opcję`SaveFormat` parametr w`pres.save()` metodę do żądanego formatu (np. PDF, PNG, JPEG).