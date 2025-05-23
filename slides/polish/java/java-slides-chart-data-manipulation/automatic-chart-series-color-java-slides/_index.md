---
"description": "Dowiedz się, jak tworzyć dynamiczne wykresy z automatycznym kolorem serii w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Ulepszaj swoje wizualizacje danych bez wysiłku."
"linktitle": "Automatyczny kolor serii wykresów w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Automatyczny kolor serii wykresów w slajdach Java"
"url": "/pl/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatyczny kolor serii wykresów w slajdach Java


## Wprowadzenie do automatycznego kolorowania serii wykresów w Aspose.Slides dla Java

W tym samouczku pokażemy, jak utworzyć prezentację PowerPoint z wykresem przy użyciu Aspose.Slides for Java i ustawić automatyczne kolory wypełnienia dla serii wykresów. Automatyczne kolory wypełnienia mogą sprawić, że wykresy będą bardziej atrakcyjne wizualnie i zaoszczędzić czas, pozwalając bibliotece wybrać kolory za Ciebie.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana w Twoim projekcie. Możesz ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację

Najpierw utworzymy nową prezentację programu PowerPoint i dodamy do niej slajd.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie dodamy do slajdu wykres kolumnowy klastrowany. Ustawimy również pierwszą serię tak, aby pokazywała wartości.

```java
// Dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
// Dodaj wykres z domyślnymi danymi
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ustaw pierwszą serię na Pokaż wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Krok 3: Wypełnij dane wykresu

Teraz wypełnimy wykres danymi. Zaczniemy od usunięcia domyślnie wygenerowanych serii i kategorii, a następnie dodamy nowe serie i kategorie.

```java
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

## Krok 4: Wypełnij dane serii

Wypełnimy dane serii zarówno dla serii 1, jak i serii 2.

```java
// Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Teraz wypełniamy dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Weź drugą serię wykresów
series = chart.getChartData().getSeries().get_Item(1);
// Teraz wypełniamy dane serii
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Krok 5: Ustaw automatyczny kolor wypełnienia dla serii

Teraz ustawmy automatyczne kolory wypełnienia dla serii wykresów. Spowoduje to, że biblioteka wybierze kolory za nas.

```java
// Ustawianie automatycznego koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Krok 6: Zapisz prezentację

Na koniec zapiszemy prezentację z wykresem w pliku PowerPoint.

```java
// Zapisz prezentację z wykresem
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla automatycznego koloru serii wykresów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
try
{
	// Dostęp do pierwszego slajdu
	ISlide slide = presentation.getSlides().get_Item(0);
	// Dodaj wykres z domyślnymi danymi
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Ustawianie automatycznego koloru wypełnienia dla serii
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Weź drugą serię wykresów
	series = chart.getChartData().getSeries().get_Item(1);
	// Teraz wypełniamy dane serii
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Ustawianie koloru wypełnienia dla serii
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

tym samouczku nauczyliśmy się, jak utworzyć prezentację PowerPoint z wykresem przy użyciu Aspose.Slides dla Java i ustawić automatyczne kolory wypełnienia dla serii wykresów. Automatyczne kolory mogą poprawić atrakcyjność wizualną wykresów i sprawić, że prezentacje będą bardziej angażujące. Możesz dalej dostosowywać wykres zgodnie ze swoimi konkretnymi wymaganiami.

## Najczęściej zadawane pytania

### Jak ustawić automatyczne kolory wypełnienia dla serii wykresów w Aspose.Slides dla Java?

Aby ustawić automatyczne kolory wypełnienia dla serii wykresów w Aspose.Slides dla Java, użyj następującego kodu:

```java
// Ustawianie automatycznego koloru wypełnienia dla serii
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Ten kod umożliwi bibliotece automatyczny wybór kolorów dla serii wykresów.

### Czy w razie potrzeby mogę dostosować kolory wykresu?

Tak, możesz dostosować kolory wykresu według potrzeb. W podanym przykładzie użyliśmy automatycznych kolorów wypełnienia, ale możesz ustawić konkretne kolory, modyfikując `FillType` I `SolidFillColor` właściwości formatu serii.

### Jak mogę dodać do wykresu dodatkowe serie lub kategorie?

Aby dodać do wykresu dodatkowe serie lub kategorie, użyj `getSeries()` I `getCategories()` metody wykresu `ChartData` obiekt. Możesz dodać nowe serie i kategorie, określając ich dane i etykiety.

### Czy jest możliwość dalszego formatowania wykresu i etykiet?

Tak, możesz dalej formatować wykres, serie i etykiety według potrzeb. Aspose.Slides for Java oferuje rozbudowane opcje formatowania wykresów, w tym czcionki, kolory, style i wiele więcej. Możesz przejrzeć dokumentację, aby uzyskać więcej szczegółów na temat opcji formatowania.

### Gdzie mogę znaleźć więcej informacji na temat pracy z Aspose.Slides dla Java?

Aby uzyskać więcej informacji i szczegółową dokumentację Aspose.Slides dla języka Java, zapoznaj się z dokumentacją referencyjną [Tutaj](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}