---
"description": "Dowiedz się, jak tworzyć oszałamiające wykresy kołowe w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym dla programistów Java."
"linktitle": "Wykres kołowy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres kołowy w slajdach Java"
"url": "/pl/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres kołowy w slajdach Java


## Wprowadzenie do tworzenia wykresu kołowego w slajdach Java przy użyciu Aspose.Slides

W tym samouczku pokażemy, jak utworzyć wykres kołowy w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Udostępnimy instrukcje krok po kroku i kod źródłowy Java, aby pomóc Ci zacząć. Ten przewodnik zakłada, że skonfigurowałeś już środowisko programistyczne przy użyciu Aspose.Slides for Java.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w Twoim projekcie. Możesz ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Importuj wymagane biblioteki

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Pamiętaj o zaimportowaniu niezbędnych klas z biblioteki Aspose.Slides.

## Krok 2: Zainicjuj prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation presentation = new Presentation();
```

Utwórz nowy obiekt Prezentacja, aby reprezentować plik PowerPoint. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką, pod którą chcesz zapisać prezentację.

## Krok 3: Dodaj slajd

```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
```

Wybierz pierwszy slajd prezentacji, do którego chcesz dodać wykres kołowy.

## Krok 4: Dodaj wykres kołowy

```java
// Dodaj wykres kołowy z domyślnymi danymi
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Dodaj wykres kołowy do slajdu w określonym miejscu i rozmiarze.

## Krok 5: Ustaw tytuł wykresu

```java
// Ustaw tytuł wykresu
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Ustaw tytuł dla wykresu kołowego. Możesz dostosować tytuł według potrzeb.

## Krok 6: Dostosuj dane wykresu

```java
// Ustaw pierwszą serię tak, aby pokazywała wartości
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ustawianie indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;

// Pobieranie arkusza danych wykresu
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Usuń domyślnie wygenerowane serie i kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Dodawanie nowych kategorii
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Dodawanie nowej serii
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Wypełnianie danych serii
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Dostosuj dane wykresu, dodając kategorie i serie oraz ustawiając ich wartości. W tym przykładzie mamy trzy kategorie i jedną serię z odpowiadającymi im punktami danych.

## Krok 7: Dostosuj sektory wykresu kołowego

```java
// Ustaw kolory sektorów
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Dostosuj wygląd każdego sektora
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Dostosuj granicę sektora
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Dostosuj inne sektory w podobny sposób
```

Dostosuj wygląd każdego sektora na wykresie kołowym. Możesz zmienić kolory, style obramowania i inne właściwości wizualne.

## Krok 8: Dostosuj etykiety danych

```java
// Dostosuj etykiety danych
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// W podobny sposób dostosuj etykiety danych dla innych punktów danych
```

Dostosuj etykiety danych dla każdego punktu danych na wykresie kołowym. Możesz kontrolować, które wartości są wyświetlane na wykresie.

## Krok 9: Pokaż linie odniesienia

```java
// Pokaż linie odniesienia dla wykresu
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Włącz linie odniesienia, aby połączyć etykiety danych z odpowiadającymi im sektorami.

## Krok 10: Ustaw kąt obrotu wykresu kołowego

```java
// Ustaw kąt obrotu dla sektorów wykresu kołowego
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Ustaw kąt obrotu dla sektorów wykresu kołowego. W tym przykładzie ustawiliśmy go na 180 stopni.

## Krok 11: Zapisz prezentację

```java
// Zapisz prezentację z wykresem kołowym
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Zapisz prezentację z wykresem kołowym w określonym katalogu.

## Kompletny kod źródłowy dla wykresu kołowego w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation presentation = new Presentation();
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
// Nie działa w nowej wersji
// Dodawanie nowych punktów i ustawianie koloru sektora
// series.IsColorVaried = prawda;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Ustawianie granicy sektora
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Ustawianie granicy sektora
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Ustawianie granicy sektora
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Utwórz niestandardowe etykiety dla każdej kategorii dla nowych serii
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Wyświetlanie linii wiodących dla wykresu
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Ustawianie kąta obrotu dla sektorów wykresu kołowego
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Zapisz prezentację z wykresem
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Wniosek

Udało Ci się utworzyć wykres kołowy w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Możesz dostosować wygląd wykresu i etykiety danych zgodnie ze swoimi konkretnymi wymaganiami. Ten samouczek zawiera podstawowy przykład, a Ty możesz dalej ulepszać i dostosowywać swoje wykresy według potrzeb.

## Najczęściej zadawane pytania

### Jak mogę zmienić kolory poszczególnych sektorów na wykresie kołowym?

Aby zmienić kolory poszczególnych sektorów na wykresie kołowym, możesz dostosować kolor wypełnienia dla każdego punktu danych. W podanym przykładzie kodu pokazaliśmy, jak ustawić kolor wypełnienia dla każdego sektora za pomocą `getSolidFillColor().setColor()` metoda. Możesz modyfikować wartości kolorów, aby uzyskać pożądany wygląd.

### Czy mogę dodać więcej kategorii i serii danych do wykresu kołowego?

Tak, możesz dodać dodatkowe kategorie i serie danych do wykresu kołowego. Aby to zrobić, możesz użyć `getChartData().getCategories().add()` I `getChartData().getSeries().add()` metody, jak pokazano w przykładzie. Po prostu podaj odpowiednie dane i etykiety dla nowych kategorii i serii, aby rozszerzyć wykres.

### Jak dostosować wygląd etykiet danych?

Możesz dostosować wygląd etykiet danych za pomocą `getDataLabelFormat()` metoda na etykiecie każdego punktu danych. W tym przykładzie pokazaliśmy, jak pokazać wartość na etykietach danych, używając `getDataLabelFormat().setShowValue(true)`Możesz dodatkowo dostosować etykiety danych, kontrolując, które wartości są wyświetlane, pokazując klucze legendy i dostosowując inne opcje formatowania.

### Czy mogę zmienić tytuł wykresu kołowego?

Tak, możesz zmienić tytuł wykresu kołowego. W podanym kodzie ustawiliśmy tytuł wykresu za pomocą `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Możesz zastąpić `"Sample Title"` z wybranym przez Ciebie tytułem.

### Jak zapisać wygenerowaną prezentację z wykresem kołowym?

Aby zapisać prezentację z wykresem kołowym, użyj `presentation.save()` metoda. Podaj żądaną ścieżkę i nazwę pliku wraz z formatem, w którym chcesz zapisać prezentację. Na przykład:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Upewnij się, że podałeś prawidłową ścieżkę do pliku i format.

### Czy mogę tworzyć inne typy wykresów za pomocą Aspose.Slides dla Java?

Tak, Aspose.Slides dla Java obsługuje różne typy wykresów, w tym wykresy słupkowe, wykresy liniowe i inne. Możesz tworzyć różne typy wykresów, zmieniając `ChartType` podczas dodawania wykresu. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać więcej szczegółów na temat tworzenia różnych typów wykresów.

### Gdzie mogę znaleźć więcej informacji i przykładów dotyczących pracy z Aspose.Slides dla Java?

Aby uzyskać więcej informacji, szczegółową dokumentację i dodatkowe przykłady, odwiedź stronę [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/). Zawiera kompleksowe zasoby, które pomogą Ci efektywnie korzystać z biblioteki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}