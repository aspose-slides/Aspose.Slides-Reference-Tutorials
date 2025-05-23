---
"description": "Twórz wykresy wielokategoriowe w slajdach Java przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym do imponującej wizualizacji danych w prezentacjach."
"linktitle": "Wykres wielokategoriowy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres wielokategoriowy w slajdach Java"
"url": "/pl/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres wielokategoriowy w slajdach Java


## Wprowadzenie do wykresu wielokategoriowego w Java Slides z Aspose.Slides

W tym samouczku nauczymy się, jak utworzyć wykres wielokategorialny w slajdach Java przy użyciu Aspose.Slides for Java API. Ten przewodnik zawiera instrukcje krok po kroku wraz z kodem źródłowym, które pomogą Ci utworzyć wykres kolumnowy klastrowany z wieloma kategoriami i seriami.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w środowisku programistycznym Java.

## Krok 1: Konfigurowanie środowiska
Najpierw zaimportuj niezbędne klasy i utwórz nowy obiekt Presentation, aby pracować ze slajdami.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodawanie slajdu i wykresu
Następnie utwórz slajd i dodaj do niego wykres kolumnowy.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Krok 3: Czyszczenie istniejących danych
Wyczyść wszystkie istniejące dane na wykresie.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Krok 4: Konfigurowanie kategorii danych
Teraz skonfigurujmy kategorie danych dla wykresu. Utworzymy wiele kategorii i je pogrupujemy.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Dodaj kategorie i je grupuj
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Krok 5: Dodawanie serii
Teraz dodajmy serię do wykresu i punkty danych.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Krok 6: Zapisywanie prezentacji
Na koniec zapisz prezentację z wykresem.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć wykres wielokategoriowy w slajdzie Java przy użyciu Aspose.Slides. Możesz dostosować ten wykres dalej, aby odpowiadał Twoim konkretnym wymaganiom.

## Kompletny kod źródłowy dla wykresu wielokategorialnego w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            Dodawanie serii
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Zapisz prezentację z wykresem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Wniosek

tym samouczku nauczyliśmy się, jak utworzyć wykres wielokategorialny w slajdach Java przy użyciu Aspose.Slides for Java API. Przeszliśmy przez przewodnik krok po kroku z kodem źródłowym, aby utworzyć wykres kolumnowy klastrowany z wieloma kategoriami i seriami.

## Najczęściej zadawane pytania

### Jak mogę dostosować wygląd wykresu?

Możesz dostosować wygląd wykresu, modyfikując właściwości, takie jak kolory, czcionki i style. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje o opcjach dostosowywania.

### Czy mogę dodać więcej serii do wykresu?

Tak, możesz dodać dodatkowe serie do wykresu, wykonując podobną procedurę, jak pokazano w kroku 5.

### Jak zmienić typ wykresu?

Aby zmienić typ wykresu, zamień `ChartType.ClusteredColumn` z żądanym typem wykresu podczas dodawania wykresu w kroku 2.

### Jak mogę dodać tytuł do wykresu?

Możesz dodać tytuł do wykresu, używając `ch.getChartTitle().getTextFrame().setText("Chart Title");` metoda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}