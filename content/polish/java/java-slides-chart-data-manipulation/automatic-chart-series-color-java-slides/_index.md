---
title: Automatyczny kolor serii wykresów w slajdach Java
linktitle: Automatyczny kolor serii wykresów w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć dynamiczne wykresy z automatycznym kolorem serii w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Ulepsz swoje wizualizacje danych bez wysiłku.
type: docs
weight: 14
url: /pl/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Wprowadzenie do automatycznego koloru serii wykresów w Aspose.Slides dla Java

tym samouczku dowiemy się, jak utworzyć prezentację programu PowerPoint z wykresem przy użyciu Aspose.Slides dla Java i ustawić automatyczne kolory wypełnienia dla serii wykresów. Automatyczne kolory wypełnienia mogą sprawić, że Twoje wykresy będą bardziej atrakcyjne wizualnie i zaoszczędzić czas, pozwalając bibliotece wybrać kolory za Ciebie.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java w swoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację

Najpierw utworzymy nową prezentację PowerPoint i dodamy do niej slajd.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie dodamy do slajdu grupowany wykres kolumnowy. Ustawimy także pierwszą serię tak, aby pokazywała wartości.

```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres z danymi domyślnymi
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Krok 3: Wypełnij dane wykresu

Teraz wypełnimy wykres danymi. Zaczniemy od usunięcia domyślnie wygenerowanych serii i kategorii, a następnie dodamy nowe serie i kategorie.

```java
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

## Krok 4: Wypełnij dane serii

Wypełnimy dane serii zarówno dla Serii 1, jak i Serii 2.

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniam dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Krok 5: Ustaw automatyczny kolor wypełnienia dla serii

Teraz ustawmy automatyczne kolory wypełnienia serii wykresów. Dzięki temu biblioteka wybierze za nas kolory.

```java
// Ustawianie automatycznego koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Krok 6: Zapisz prezentację

Na koniec zapiszemy prezentację wraz z wykresem w pliku PowerPoint.

```java
// Zapisz prezentację z wykresem
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy automatycznego koloru serii wykresów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
try
{
	// Uzyskaj dostęp do pierwszego slajdu
	ISlide slide = presentation.getSlides().get_Item(0);
	// Dodaj wykres z danymi domyślnymi
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Ustawianie automatycznego koloru wypełnienia serii
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Weź drugą serię wykresów
	series = chart.getChartData().getSeries().get_Item(1);
	// Teraz wypełniam dane serii
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Ustawianie koloru wypełnienia serii
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Zapisz prezentację z wykresem
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak utworzyć prezentację programu PowerPoint z wykresem przy użyciu Aspose.Slides dla Java i ustawić automatyczne kolory wypełnienia dla serii wykresów. Automatyczne kolory mogą poprawić atrakcyjność wizualną wykresów i uczynić prezentacje bardziej wciągającymi. Możesz dodatkowo dostosować wykres zgodnie z potrzebami.

## Często zadawane pytania

### Jak ustawić automatyczne kolory wypełniania serii wykresów w Aspose.Slides dla Java?

Aby ustawić automatyczne kolory wypełniania serii wykresów w Aspose.Slides dla Java, użyj następującego kodu:

```java
// Ustawianie automatycznego koloru wypełnienia serii
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Ten kod pozwoli bibliotece automatycznie wybrać kolory dla serii wykresów.

### Czy w razie potrzeby mogę dostosować kolory wykresów?

 Tak, możesz dostosować kolory wykresu według potrzeb. W podanym przykładzie użyliśmy automatycznych kolorów wypełnienia, ale możesz ustawić określone kolory, modyfikując plik`FillType` I`SolidFillColor` właściwości formatu serii.

### Jak mogę dodać dodatkowe serie lub kategorie do wykresu?

 Aby dodać do wykresu dodatkowe serie lub kategorie, użyj opcji`getSeries()` I`getCategories()` metody wykresów`ChartData` obiekt. Możesz dodawać nowe serie i kategorie, określając ich dane i etykiety.

### Czy można dodatkowo sformatować wykres i etykiety?

Tak, w razie potrzeby możesz dodatkowo sformatować wykres, serię i etykiety. Aspose.Slides dla Java zapewnia rozbudowane opcje formatowania wykresów, w tym czcionki, kolory, style i inne. Więcej szczegółów na temat opcji formatowania można znaleźć w dokumentacji.

### Gdzie mogę znaleźć więcej informacji na temat pracy z Aspose.Slides dla Java?

 Aby uzyskać więcej informacji i szczegółową dokumentację dotyczącą Aspose.Slides for Java, możesz odwiedzić dokumentację referencyjną[Tutaj](https://reference.aspose.com/slides/java/).