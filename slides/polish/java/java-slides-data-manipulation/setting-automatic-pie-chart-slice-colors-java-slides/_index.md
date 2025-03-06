---
title: Ustawianie automatycznych kolorów wycinków wykresu kołowego w slajdach Java
linktitle: Ustawianie automatycznych kolorów wycinków wykresu kołowego w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć dynamiczne wykresy kołowe z automatycznymi kolorami plasterków w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym.
weight: 24
url: /pl/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do ustawiania automatycznych kolorów wycinków wykresu kołowego w slajdach Java

W tym samouczku dowiemy się, jak utworzyć wykres kołowy w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java i ustawić automatyczne kolory plasterków dla wykresu. Zapewnimy wskazówki krok po kroku wraz z kodem źródłowym.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę można pobrać ze strony internetowej Aspose:[Pobierz Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).

## Krok 1: Zaimportuj wymagane pakiety

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

## Krok 2: Utwórz prezentację programu PowerPoint

 Utwórz instancję`Presentation` klasę, aby utworzyć nową prezentację programu PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 3: Dodaj slajd

Przejdź do pierwszego slajdu prezentacji i dodaj do niego wykres z domyślnymi danymi:

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

## Krok 5: Skonfiguruj dane wykresu

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

Włącz różne kolory plasterków dla wykresu kołowego:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Krok 9: Zapisz prezentację

Na koniec zapisz prezentację w pliku programu PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do ustawiania kolorów automatycznego wycinka wykresu kołowego w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Klasa prezentacji instancji reprezentująca plik PPTX
Presentation presentation = new Presentation();
try
{
	// Uzyskaj dostęp do pierwszego slajdu
	ISlide slides = presentation.getSlides().get_Item(0);
	// Dodaj wykres z danymi domyślnymi
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Tytuł tabeli ustawień
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
	// Teraz wypełniam dane serii
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

Pomyślnie utworzyłeś wykres kołowy w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java i skonfigurowałeś go tak, aby miał automatyczne kolory plasterków. W tym przewodniku krok po kroku znajdziesz kod źródłowy niezbędny do osiągnięcia tego celu. W razie potrzeby możesz dodatkowo dostosować wykres i prezentację.

## Często zadawane pytania

### Jak mogę dostosować kolory poszczególnych wycinków na wykresie kołowym?

 Aby dostosować kolory poszczególnych wycinków na wykresie kołowym, możesz użyć opcji`getAutomaticSeriesColors` metodę pobierania domyślnego schematu kolorów, a następnie modyfikowania kolorów w razie potrzeby. Oto przykład:

```java
//Uzyskaj domyślny schemat kolorów
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// W razie potrzeby zmodyfikuj kolory
colors.get_Item(0).setColor(Color.RED); // Ustaw kolor pierwszego plasterka na czerwony
colors.get_Item(1).setColor(Color.BLUE); // Ustaw kolor drugiego plasterka na niebieski
// W razie potrzeby dodaj więcej modyfikacji kolorów
```

### Jak dodać legendę do wykresu kołowego?

 Aby dodać legendę do wykresu kołowego, możesz użyć opcji`getLegend` metodę i skonfiguruj ją w następujący sposób:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Ustaw pozycję legendy
legend.setOverlay(true); // Wyświetl legendę nad wykresem
```

### Czy mogę zmienić czcionkę i styl tytułu?

Tak, możesz zmienić czcionkę i styl tytułu. Użyj poniższego kodu, aby ustawić czcionkę i styl tytułu:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Ustaw rozmiar czcionki
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Pogrubienie tytułu
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Ustaw tytuł kursywą
```

W razie potrzeby możesz dostosować rozmiar czcionki, pogrubienie i styl kursywy.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
