---
"description": "Dowiedz się, jak tworzyć dynamiczne wykresy kołowe z automatycznymi kolorami wycinków w prezentacjach PowerPoint w języku Java przy użyciu Aspose.Slides dla języka Java. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Ustawianie automatycznych kolorów wycinków wykresu kołowego w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustawianie automatycznych kolorów wycinków wykresu kołowego w slajdach Java"
"url": "/pl/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie automatycznych kolorów wycinków wykresu kołowego w slajdach Java


## Wprowadzenie do ustawiania automatycznych kolorów wycinków wykresu kołowego w slajdach Java

W tym samouczku pokażemy, jak utworzyć wykres kołowy w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java i ustawić automatyczne kolory wycinków dla wykresu. Zapewnimy wskazówki krok po kroku wraz z kodem źródłowym.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę ze strony internetowej Aspose: [Pobierz Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).

## Krok 1: Importuj wymagane pakiety

Najpierw musisz zaimportować niezbędne pakiety z Aspose.Slides dla Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Krok 2: Utwórz prezentację PowerPoint

Utwórz instancję `Presentation` klasa, aby utworzyć nową prezentację PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 3: Dodaj slajd

Otwórz pierwszy slajd prezentacji i dodaj do niego wykres z domyślnymi danymi:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Krok 4: Ustaw tytuł wykresu

Ustaw tytuł wykresu:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 5: Konfigurowanie danych wykresu

Ustaw wykres tak, aby pokazywał wartości dla pierwszej serii i skonfiguruj dane wykresu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Krok 6: Dodaj kategorie i serie

Dodaj nowe kategorie i serie do wykresu:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Krok 7: Wypełnij dane serii

Wypełnij dane serii dla wykresu kołowego:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Krok 8: Włącz różne kolory plasterków

Włącz różne kolory wycinków dla wykresu kołowego:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Krok 9: Zapisz prezentację

Na koniec zapisz prezentację w pliku PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do ustawiania automatycznych kolorów wycinków wykresu kołowego w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation presentation = new Presentation();
try
{
	// Dostęp do pierwszego slajdu
	ISlide slides = presentation.getSlides().get_Item(0);
	// Dodaj wykres z domyślnymi danymi
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Ustawienie tytułu wykresu
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
	// Dodawanie nowych kategorii
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Dodawanie nowej serii
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Teraz wypełniamy dane serii
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

Udało Ci się utworzyć wykres kołowy w prezentacji PowerPoint przy użyciu Aspose.Slides for Java i skonfigurować go tak, aby miał automatyczne kolory wycinków. Ten przewodnik krok po kroku dostarcza Ci niezbędnego kodu źródłowego, aby to osiągnąć. Możesz dalej dostosowywać wykres i prezentację według potrzeb.

## Najczęściej zadawane pytania

### Jak mogę dostosować kolory poszczególnych wycinków wykresu kołowego?

Aby dostosować kolory poszczególnych wycinków na wykresie kołowym, możesz użyć `getAutomaticSeriesColors` metoda pobierania domyślnego schematu kolorów, a następnie modyfikowania kolorów w razie potrzeby. Oto przykład:

```java
// Pobierz domyślny schemat kolorów
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Zmień kolory według potrzeb
colors.get_Item(0).setColor(Color.RED); // Ustaw kolor pierwszego wycinka na czerwony
colors.get_Item(1).setColor(Color.BLUE); // Ustaw kolor drugiego wycinka na niebieski
// W razie potrzeby dodaj więcej modyfikacji kolorów
```

### Jak dodać legendę do wykresu kołowego?

Aby dodać legendę do wykresu kołowego, możesz użyć `getLegend` metodę i skonfiguruj ją w następujący sposób:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Ustaw pozycję legendy
legend.setOverlay(true); // Wyświetl legendę nad wykresem
```

### Czy mogę zmienić czcionkę i styl tytułu?

Tak, możesz zmienić czcionkę i styl tytułu. Użyj następującego kodu, aby ustawić czcionkę i styl tytułu:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Ustaw rozmiar czcionki
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Pogrub tytuł
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Tytuł należy pisać kursywą
```

W razie potrzeby możesz dostosować rozmiar czcionki, pogrubienie i kursywę.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}