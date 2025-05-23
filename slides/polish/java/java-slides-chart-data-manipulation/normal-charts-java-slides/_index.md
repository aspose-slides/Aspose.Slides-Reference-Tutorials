---
"description": "Twórz normalne wykresy w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku i kod źródłowy do tworzenia, dostosowywania i zapisywania wykresów w prezentacjach PowerPoint."
"linktitle": "Normalne wykresy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Normalne wykresy w slajdach Java"
"url": "/pl/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Normalne wykresy w slajdach Java


## Wprowadzenie do normalnych wykresów w slajdach Java

W tym samouczku przejdziemy przez proces tworzenia normalnych wykresów w Java Slides przy użyciu Aspose.Slides for Java API. Użyjemy instrukcji krok po kroku wraz z kodem źródłowym, aby pokazać, jak utworzyć wykres kolumnowy klastrowany w prezentacji PowerPoint.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano Aspose.Slides dla Java API.
2. Skonfigurowano środowisko programistyczne Java.
3. Podstawowa znajomość programowania w Javie.

## Krok 1: Konfigurowanie projektu

Upewnij się, że masz katalog dla swojego projektu. Nazwijmy go „Twoim katalogiem dokumentów”, jak wspomniano w kodzie. Możesz zastąpić to rzeczywistą ścieżką do katalogu swojego projektu.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Krok 2: Tworzenie prezentacji

Teraz utwórzmy prezentację w programie PowerPoint i przejdźmy do jej pierwszego slajdu.

```java
// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation pres = new Presentation();
// Dostęp do pierwszego slajdu
ISlide sld = pres.getSlides().get_Item(0);
```

## Krok 3: Dodawanie wykresu

Dodamy do slajdu wykres kolumnowy i ustalimy jego tytuł.

```java
// Dodaj wykres z domyślnymi danymi
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ustawienie tytułu wykresu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 4: Ustawianie danych wykresu

Następnie ustawimy dane wykresu poprzez zdefiniowanie serii i kategorii.

```java
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;

// Pobieranie arkusza danych wykresu
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

Teraz wypełnijmy punkty danych serii na wykresie.

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Wypełnianie danych serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ustawianie koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);

// Wypełnianie danych serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ustawianie koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 6: Dostosowywanie etykiet

Dostosujmy etykiety danych dla serii wykresów.

```java
// Pierwsza etykieta będzie pokazywać nazwę kategorii
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Pokaż wartość dla trzeciej etykiety z nazwą serii i separatorem
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

To wszystko! Udało Ci się utworzyć wykres kolumnowy klastrowany w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Możesz dostosować ten wykres dalej zgodnie ze swoimi wymaganiami.

## Kompletny kod źródłowy dla normalnych wykresów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation pres = new Presentation();
// Dostęp do pierwszego slajdu
ISlide sld = pres.getSlides().get_Item(0);
// Dodaj wykres z domyślnymi danymi
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ustawienie tytułu wykresu
// Chart.getChartTitle().getTextFrameForOverriding().setText("Przykładowy tytuł");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
// Pobieranie arkusza danych wykresu
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
// Teraz wypełniamy dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ustawianie koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniamy dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ustawianie koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Pierwsza etykieta będzie wyświetlać nazwę kategorii
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Pokaż wartość dla trzeciej etykiety
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Zapisz prezentację z wykresem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Wniosek

W tym samouczku nauczyliśmy się, jak tworzyć normalne wykresy w Java Slides przy użyciu Aspose.Slides for Java API. Przeszliśmy przez przewodnik krok po kroku z kodem źródłowym, aby utworzyć wykres kolumnowy klastrowany w prezentacji PowerPoint.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu?

Aby zmienić typ wykresu, zmodyfikuj `ChartType` parametr podczas dodawania wykresu za pomocą `sld.getShapes().addChart()`Możesz wybierać spośród różnych typów wykresów dostępnych w Aspose.Slides.

### Czy mogę zmienić kolory serii wykresów?

Tak, możesz zmienić kolory serii wykresu, ustawiając kolor wypełnienia dla każdej serii za pomocą `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Jak dodać więcej kategorii lub serii do wykresu?

Możesz dodać więcej kategorii lub serii do wykresu, dodając nowe punkty danych i etykiety za pomocą `chart.getChartData().getCategories().add()` I `chart.getChartData().getSeries().add()` metody.

### Jak mogę dodatkowo dostosować tytuł wykresu?

Możesz dodatkowo dostosować tytuł wykresu, modyfikując właściwości `chart.getChartTitle()` takie jak wyrównanie tekstu, rozmiar czcionki i kolor.

### Jak zapisać wykres w innym formacie pliku?

Aby zapisać wykres w innym formacie pliku, zmień `SaveFormat` parametr w `pres.save()` metodę do żądanego formatu (np. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}