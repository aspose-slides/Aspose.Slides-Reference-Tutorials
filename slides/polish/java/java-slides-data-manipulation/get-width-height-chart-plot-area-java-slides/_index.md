---
"description": "Dowiedz się, jak pobrać wymiary obszaru wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Udoskonal swoje umiejętności automatyzacji programu PowerPoint."
"linktitle": "Pobierz szerokość i wysokość z obszaru wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Pobierz szerokość i wysokość z obszaru wykresu w slajdach Java"
"url": "/pl/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz szerokość i wysokość z obszaru wykresu w slajdach Java


## Wstęp

Wykresy to potężny sposób wizualizacji danych w prezentacjach PowerPoint. Czasami możesz potrzebować znać wymiary obszaru wykresu z różnych powodów, takich jak zmiana rozmiaru lub położenia elementów na wykresie. Ten przewodnik pokaże, jak uzyskać szerokość i wysokość obszaru wykresu za pomocą Java i Aspose.Slides dla Java.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę ze strony internetowej Aspose [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Konfigurowanie środowiska

Upewnij się, że biblioteka Aspose.Slides for Java została dodana do projektu Java. Możesz to zrobić, włączając bibliotekę do zależności projektu lub ręcznie dodając plik JAR.

## Krok 2: Tworzenie prezentacji PowerPoint

Zacznijmy od utworzenia prezentacji PowerPoint i dodania do niej slajdu. Będzie on służył jako pojemnik na nasz wykres.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Zastępować `"Your Document Directory"` ze ścieżką do katalogu dokumentów.

## Krok 3: Dodawanie wykresu

Teraz dodajmy do slajdu wykres kolumnowy klastrowany. Sprawdzimy również układ wykresu.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Ten kod tworzy wykres kolumnowy klastrowany w pozycji (100, 100) o wymiarach (500, 350).

## Krok 4: Uzyskanie wymiarów obszaru wykresu

Aby pobrać szerokość i wysokość obszaru wykresu, możemy użyć następującego kodu:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Teraz zmienne `x`, `y`, `w`, I `h` zawierają odpowiednie wartości współrzędnej X, współrzędnej Y, szerokości i wysokości obszaru wykresu.

## Krok 5: Zapisywanie prezentacji

Na koniec zapisz prezentację z wykresem.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Pamiętaj o wymianie `"Chart_out.pptx"` z wybraną nazwą pliku wyjściowego.

## Kompletny kod źródłowy do pobierania szerokości i wysokości z obszaru wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Zapisz prezentację z wykresem
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym artykule omówiliśmy, jak uzyskać szerokość i wysokość obszaru wykresu w Java Slides przy użyciu Aspose.Slides for Java API. Informacje te mogą być cenne, gdy trzeba dynamicznie dostosować układ wykresów w prezentacjach PowerPoint.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu na inny niż wykres kolumnowy?

Możesz zmienić typ wykresu, zastępując `ChartType.ClusteredColumn` z pożądanym wyliczeniem typu wykresu, takim jak `ChartType.Line` Lub `ChartType.Pie`.

### Czy mogę modyfikować inne właściwości wykresu?

Tak, możesz modyfikować różne właściwości wykresu, takie jak dane, etykiety i formatowanie, używając Aspose.Slides for Java API. Zapoznaj się z dokumentacją, aby uzyskać więcej szczegółów.

### Czy Aspose.Slides for Java nadaje się do profesjonalnej automatyzacji prezentacji PowerPoint?

Tak, Aspose.Slides for Java to potężna biblioteka do automatyzacji zadań PowerPoint w aplikacjach Java. Zapewnia kompleksowe funkcje do pracy z prezentacjami, slajdami, kształtami, wykresami i nie tylko.

### Jak mogę dowiedzieć się więcej o Aspose.Slides dla Java?

Obszerną dokumentację i przykłady można znaleźć na stronie dokumentacji Aspose.Slides for Java [Tutaj](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}