---
"description": "Naucz się tworzyć i dostosowywać wykresy Java Slides za pomocą Aspose.Slides. Ulepsz swoje prezentacje za pomocą potężnych encji wykresów."
"linktitle": "Wykresy jednostek w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykresy jednostek w slajdach Java"
"url": "/pl/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykresy jednostek w slajdach Java


## Wprowadzenie do encji wykresu w slajdach Java

Wykresy to potężne narzędzia do wizualizacji danych w prezentacjach. Niezależnie od tego, czy tworzysz raporty biznesowe, prezentacje akademickie czy jakąkolwiek inną formę treści, wykresy pomagają skutecznie przekazywać informacje. Aspose.Slides for Java oferuje solidne funkcje do pracy z wykresami, co czyni go wyborem dla programistów Java.

## Wymagania wstępne

Zanim zagłębimy się w świat encji wykresu, upewnij się, że spełnione są następujące wymagania wstępne:

- Zainstalowano Java Development Kit (JDK)
- Biblioteka Aspose.Slides for Java została pobrana i dodana do projektu
- Podstawowa znajomość programowania w Javie

Teraz zajmiemy się tworzeniem i dostosowywaniem wykresów za pomocą Aspose.Slides dla Java.

## Krok 1: Tworzenie prezentacji

Pierwszym krokiem jest utworzenie nowej prezentacji, do której dodasz swój wykres. Oto fragment kodu do utworzenia prezentacji:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodawanie wykresu

Gdy prezentacja będzie gotowa, czas dodać wykres. W tym przykładzie dodamy prosty wykres liniowy ze znacznikami. Oto, jak to zrobić:

```java
// Dostęp do pierwszego slajdu
ISlide slide = pres.getSlides().get_Item(0);

// Dodawanie przykładowego wykresu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 3: Dostosowywanie tytułu wykresu

Dobrze zdefiniowany wykres powinien mieć tytuł. Ustawmy tytuł dla naszego wykresu:

```java
// Ustawianie tytułu wykresu
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Krok 4: Formatowanie linii siatki

Możesz sformatować główne i podrzędne linie siatki swojego wykresu. Ustawmy formatowanie dla linii siatki osi pionowej:

```java
// Ustawianie formatu głównych linii siatki dla osi wartości
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ustawianie formatu linii siatki pomocniczej dla osi wartości
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Krok 5: Dostosowywanie osi wartości

Masz kontrolę nad formatem liczb, wartościami maksymalnymi i minimalnymi osi wartości. Oto jak to dostosować:

```java
// Ustawianie formatu liczby osi wartości
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Ustawianie maksymalnych i minimalnych wartości wykresu
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Krok 6: Dodawanie tytułu osi wartości

Aby wykres był bardziej informacyjny, możesz dodać tytuł do osi wartości:

```java
// Ustawianie tytułu osi wartości
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Krok 7: Formatowanie osi kategorii

Oś kategorii, która zazwyczaj reprezentuje kategorie danych, można również dostosować:

```java
// Ustawianie formatu głównych linii siatki dla osi kategorii
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Ustawianie formatu linii siatki pomocniczej dla osi kategorii
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Krok 8: Dodawanie legend

Legendy pomagają wyjaśnić serie danych na wykresie. Dostosujmy legendy:

```java
// Ustawianie właściwości tekstu legend
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Ustaw legendy wykresu bez nakładania się wykresu
chart.getLegend().setOverlay(true);
```

## Krok 9: Zapisywanie prezentacji

Na koniec zapisz prezentację z wykresem:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla jednostek wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Tworzenie instancji prezentacji// Tworzenie instancji prezentacji
Presentation pres = new Presentation();
try
{
	// Dostęp do pierwszego slajdu
	ISlide slide = pres.getSlides().get_Item(0);
	// Dodawanie przykładowego wykresu
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Ustawianie tytułu wykresu
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ustawianie formatu głównych linii siatki dla osi wartości
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Ustawianie formatu linii siatki pomocniczej dla osi wartości
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ustawianie formatu liczby osi wartości
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Ustawianie maksymalnych i minimalnych wartości wykresu
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Ustawianie właściwości tekstu osi wartości
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Ustawianie tytułu osi wartości
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ustawianie formatu linii osi wartości: Teraz przestarzałe
	// wykres.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// wykres.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Ustawianie formatu głównych linii siatki dla osi kategorii
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Ustawianie formatu linii siatki pomocniczej dla osi kategorii
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ustawianie właściwości tekstu osi kategorii
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Ustawianie tytułu kategorii
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ustawianie pozycji etykiety osi kategorii
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Ustawianie kąta obrotu etykiety osi kategorii
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Ustawianie właściwości tekstu legend
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ustaw legendy wykresu bez nakładania się wykresu
	chart.getLegend().setOverlay(true);
	// Wykreślanie pierwszej serii na osi wartości drugorzędnych
	// Wykres.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Ustawianie koloru tylnej ściany wykresu
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Ustawianie koloru obszaru wykresu
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Zapisz prezentację
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym artykule zbadaliśmy świat encji wykresów w Java Slides przy użyciu Aspose.Slides for Java. Nauczyłeś się, jak tworzyć, dostosowywać i manipulować wykresami, aby ulepszyć swoje prezentacje. Wykresy nie tylko sprawiają, że Twoje dane są atrakcyjne wizualnie, ale także pomagają odbiorcom łatwiej zrozumieć złożone informacje.

## Najczęściej zadawane pytania

### Jak zmienić typ wykresu?

Aby zmienić typ wykresu, użyj `chart.setType()` metodę i określ pożądany typ wykresu.

### Czy mogę dodać do wykresu wiele serii danych?

Tak, możesz dodać wiele serii danych do wykresu za pomocą `chart.getChartData().getSeries().addSeries()` metoda.

### Jak dostosować kolory wykresu?

Możesz dostosować kolory wykresu, ustawiając format wypełnienia różnych elementów wykresu, takich jak linie siatki, tytuł i legenda.

### Czy mogę tworzyć wykresy 3D?

Tak, Aspose.Slides dla Java obsługuje tworzenie wykresów 3D. Możesz ustawić `ChartType` do wykresu 3D, aby go utworzyć.

### Czy Aspose.Slides for Java jest kompatybilny z najnowszymi wersjami Java?

Tak, Aspose.Slides for Java jest regularnie aktualizowany, aby obsługiwać najnowsze wersje Java i zapewnia kompatybilność z szeroką gamą środowisk Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}