---
title: Wykres wielu kategorii w slajdach Java
linktitle: Wykres wielu kategorii w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz wykresy z wieloma kategoriami w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym umożliwiający imponującą wizualizację danych w prezentacjach.
weight: 20
url: /pl/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do wykresu wielu kategorii w slajdach Java z Aspose.Slides

W tym samouczku dowiemy się, jak utworzyć wykres z wieloma kategoriami na slajdach Java za pomocą interfejsu API Aspose.Slides for Java. Ten przewodnik zawiera instrukcje krok po kroku wraz z kodem źródłowym, które pomogą Ci utworzyć grupowany wykres kolumnowy z wieloma kategoriami i seriami.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim środowisku programistycznym Java.

## Krok 1: Konfigurowanie środowiska
Najpierw zaimportuj niezbędne klasy i utwórz nowy obiekt Prezentacja do pracy ze slajdami.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodawanie slajdu i wykresu
Następnie utwórz slajd i dodaj do niego grupowany wykres kolumnowy.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Krok 3: Usuwanie istniejących danych
Usuń wszelkie istniejące dane z wykresu.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Krok 4: Konfigurowanie kategorii danych
Teraz skonfigurujmy kategorie danych dla wykresu. Stworzymy wiele kategorii i pogrupujemy je.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Dodaj kategorie i pogrupuj je
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
Dodajmy teraz do wykresu serię wraz z punktami danych.

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

Otóż to! Pomyślnie utworzyłeś wykres z wieloma kategoriami na slajdzie Java za pomocą Aspose.Slides. Możesz dodatkowo dostosować ten wykres, aby odpowiadał Twoim konkretnym wymaganiom.

## Kompletny kod źródłowy wykresu z wieloma kategoriami w slajdach Java

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
// Dodawanie serii
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

W tym samouczku nauczyliśmy się tworzyć wykresy z wieloma kategoriami na slajdach Java przy użyciu interfejsu API Aspose.Slides for Java. Przeszliśmy przez przewodnik krok po kroku z kodem źródłowym, aby utworzyć grupowany wykres kolumnowy z wieloma kategoriami i seriami.

## Często zadawane pytania

### Jak mogę dostosować wygląd wykresu?

Można dostosować wygląd wykresu, modyfikując właściwości, takie jak kolory, czcionki i style. Szczegółowe opcje dostosowywania można znaleźć w dokumentacji Aspose.Slides.

### Czy mogę dodać więcej serii do wykresu?

Tak, możesz dodać dodatkowe serie do wykresu, wykonując podobny proces, jak pokazano w kroku 5.

### Jak zmienić typ wykresu?

 Aby zmienić typ wykresu, zamień`ChartType.ClusteredColumn` z żądanym typem wykresu podczas dodawania wykresu w kroku 2.

### Jak dodać tytuł do wykresu?

 Możesz dodać tytuł do wykresu, używając opcji`ch.getChartTitle().getTextFrame().setText("Chart Title");` metoda.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
