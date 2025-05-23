---
"description": "Twórz oszałamiające wykresy Sunburst w slajdach Java z Aspose.Slides. Naucz się krok po kroku tworzenia wykresów i manipulowania danymi."
"linktitle": "Wykres słoneczny w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykres słoneczny w slajdach Java"
"url": "/pl/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykres słoneczny w slajdach Java


## Wprowadzenie do wykresu Sunburst w Java Slajdy z Aspose.Slides

W tym samouczku dowiesz się, jak utworzyć wykres Sunburst w prezentacji PowerPoint przy użyciu Aspose.Slides for Java API. Wykres Sunburst to wykres promieniowy używany do przedstawiania danych hierarchicznych. Podamy instrukcje krok po kroku wraz z kodem źródłowym.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w projekcie Java. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Importuj wymagane biblioteki

Najpierw zaimportuj niezbędne biblioteki do pracy z Aspose.Slides i utwórz wykres sunburst w swojej aplikacji Java.

```java
import com.aspose.slides.*;
```

## Krok 2: Zainicjuj prezentację

Zainicjuj prezentację programu PowerPoint i określ katalog, w którym zostanie zapisany plik prezentacji.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Utwórz wykres słoneczny

Utwórz wykres Sunburst na slajdzie. Określamy pozycję (X, Y) i wymiary (szerokość, wysokość) wykresu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Krok 4: Przygotuj dane wykresu

Wyczyść wszystkie istniejące kategorie i serie danych na wykresie, a następnie utwórz skoroszyt danych dla wykresu.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Krok 5: Zdefiniuj hierarchię wykresu

Zdefiniuj hierarchiczną strukturę wykresu Sunburst. Możesz dodać gałęzie, łodygi i liście jako kategorie.

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

Na koniec zapisz prezentację z wykresem słonecznym.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla wykresu Sunburst w slajdach Java

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

W tym samouczku nauczyłeś się, jak utworzyć wykres Sunburst w prezentacji PowerPoint przy użyciu interfejsu API Aspose.Slides for Java. Zobaczyłeś, jak zainicjować prezentację, utworzyć wykres, zdefiniować hierarchię wykresów, dodać punkty danych i zapisać prezentację. Teraz możesz wykorzystać tę wiedzę, aby tworzyć interaktywne i informacyjne wykresy Sunburst w swoich aplikacjach Java.

## Najczęściej zadawane pytania

### Jak mogę dostosować wygląd wykresu Sunburst?

Możesz dostosować wygląd wykresu Sunburst, modyfikując właściwości, takie jak kolory, etykiety i style. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat opcji dostosowywania.

### Czy mogę dodać więcej punktów danych do wykresu?

Tak, możesz dodać więcej punktów danych do wykresu, używając `series.getDataPoints().addDataPointForSunburstSeries()` wybierz metodę dla każdego punktu danych, który chcesz uwzględnić.

### Jak mogę dodać podpowiedzi do wykresu słonecznego?

Aby dodać podpowiedzi do wykresu słonecznego, możesz ustawić format etykiety danych tak, aby po najechaniu kursorem na segmenty wykresu wyświetlały się dodatkowe informacje, takie jak wartości lub opisy.

### Czy można tworzyć interaktywne wykresy Sunburst z hiperłączami?

Tak, możesz tworzyć interaktywne wykresy Sunburst z hiperlinkami, dodając hiperlinki do określonych elementów wykresu lub segmentów. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat dodawania hiperlinków.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}