---
title: Wykres Sunburst w slajdach Java
linktitle: Wykres Sunburst w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz oszałamiające wykresy Sunburst w Java Slides za pomocą Aspose.Slides. Dowiedz się, jak krok po kroku tworzyć wykresy i manipulować danymi.
weight: 16
url: /pl/java/chart-elements/sunburst-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do wykresu Sunburst w Java Slides z Aspose.Slides

W tym samouczku dowiesz się, jak utworzyć wykres Sunburst w prezentacji programu PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Wykres Sunburst to wykres promieniowy używany do reprezentowania danych hierarchicznych. Udostępnimy instrukcje krok po kroku wraz z kodem źródłowym.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Zaimportuj wymagane biblioteki

Najpierw zaimportuj niezbędne biblioteki do pracy z Aspose.Slides i utwórz wykres Sunburst w swojej aplikacji Java.

```java
import com.aspose.slides.*;
```

## Krok 2: Zainicjuj prezentację

Zainicjuj prezentację programu PowerPoint i określ katalog, w którym zostanie zapisany plik prezentacji.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Utwórz wykres rozbłysku słońca

Utwórz wykres Sunburst na slajdzie. Określamy położenie (X, Y) i wymiary (szerokość, wysokość) wykresu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Krok 4: Przygotuj dane wykresu

Usuń wszystkie istniejące dane kategorii i serii z wykresu, a następnie utwórz skoroszyt danych dla wykresu.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Krok 5: Zdefiniuj hierarchię wykresów

Zdefiniuj hierarchiczną strukturę wykresu Sunburst. Możesz dodawać gałęzie, łodygi i liście jako kategorie.

```java
// Oddział 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Oddział 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Krok 6: Dodaj dane do wykresu

Dodaj punkty danych do serii wykresów Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Krok 7: Zapisz prezentację

Na koniec zapisz prezentację z wykresem Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy wykresu Sunburst w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//oddział 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//oddział 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku nauczyłeś się tworzyć wykres Sunburst w prezentacji programu PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Widziałeś, jak zainicjować prezentację, utworzyć wykres, zdefiniować hierarchię wykresu, dodać punkty danych i zapisać prezentację. Możesz teraz wykorzystać tę wiedzę do tworzenia interaktywnych i informacyjnych wykresów Sunburst w aplikacjach Java.

## Często zadawane pytania

### Jak dostosować wygląd wykresu Sunburst?

Możesz dostosować wygląd wykresu Sunburst, modyfikując właściwości, takie jak kolory, etykiety i style. Szczegółowe opcje dostosowywania można znaleźć w dokumentacji Aspose.Slides.

### Czy mogę dodać więcej punktów danych do wykresu?

 Tak, możesz dodać więcej punktów danych do wykresu, korzystając z opcji`series.getDataPoints().addDataPointForSunburstSeries()` metodę dla każdego punktu danych, który chcesz uwzględnić.

### Jak mogę dodać podpowiedzi do wykresu Sunburst?

Aby dodać podpowiedzi do wykresu Sunburst, możesz ustawić format etykiety danych tak, aby po najechaniu kursorem na segmenty wykresu wyświetlały dodatkowe informacje, takie jak wartości lub opisy.

### Czy można tworzyć interaktywne wykresy Sunburst z hiperłączami?

Tak, możesz tworzyć interaktywne wykresy Sunburst z hiperłączami, dodając hiperłącza do określonych elementów lub segmentów wykresu. Szczegółowe informacje na temat dodawania hiperłączy można znaleźć w dokumentacji Aspose.Slides.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
