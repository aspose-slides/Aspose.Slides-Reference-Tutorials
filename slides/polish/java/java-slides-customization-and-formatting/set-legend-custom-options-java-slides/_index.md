---
"description": "Dowiedz się, jak ustawić niestandardowe opcje legendy w Java Slides przy użyciu Aspose.Slides for Java. Dostosuj położenie i rozmiar legendy na wykresach PowerPoint."
"linktitle": "Ustaw opcje niestandardowe legendy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw opcje niestandardowe legendy w slajdach Java"
"url": "/pl/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw opcje niestandardowe legendy w slajdach Java


## Wprowadzenie do ustawiania niestandardowych opcji legendy w slajdach Java

tym samouczku pokażemy, jak dostosować właściwości legendy wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Możesz modyfikować położenie, rozmiar i inne atrybuty legendy, aby dopasować je do potrzeb prezentacji.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowano Aspose.Slides dla Java API.
- Konfiguracja środowiska programistycznego Java.

## Krok 1: Importuj niezbędne klasy:

```java
// Importuj Aspose.Slides dla klas Java
import com.aspose.slides.*;
```

## Krok 2: Określ ścieżkę do katalogu dokumentów:

```java
String dataDir = "Your Document Directory";
```

## Krok 3: Utwórz instancję `Presentation` klasa:

```java
Presentation presentation = new Presentation();
```

## Krok 4: Dodaj slajd do prezentacji:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Krok 5: Dodaj do slajdu wykres kolumnowy klastrowany:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Krok 6. Ustaw właściwości legendy:

- Ustaw pozycję X legendy (względem szerokości wykresu):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Ustaw pozycję Y legendy (względem wysokości wykresu):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Ustaw szerokość legendy (względem szerokości wykresu):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Ustaw wysokość legendy (względem wysokości wykresu):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Krok 7: Zapisz prezentację na dysku:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

To wszystko! Udało Ci się dostosować właściwości legendy wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java.

## Kompletny kod źródłowy dla opcji niestandardowych legendy w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
try
{
	// Uzyskaj odniesienie do slajdu
	ISlide slide = presentation.getSlides().get_Item(0);
	// Dodaj wykres kolumnowy klastrowany na slajdzie
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Ustaw właściwości legendy
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Zapisz prezentację na dysku
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Wniosek

W tym samouczku nauczyliśmy się, jak dostosować właściwości legendy wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Możesz modyfikować położenie, rozmiar i inne atrybuty legendy, aby tworzyć atrakcyjne wizualnie i informacyjne prezentacje.

## Najczęściej zadawane pytania

## Jak mogę zmienić położenie legendy?

Aby zmienić położenie legendy, użyj `setX` I `setY` metody obiektu legendy. Wartości są określone w odniesieniu do szerokości i wysokości wykresu.

## Jak mogę zmienić rozmiar legendy?

Możesz dostosować rozmiar legendy za pomocą `setWidth` I `setHeight` metody obiektu legendy. Wartości te są również względne do szerokości i wysokości wykresu.

## Czy mogę dostosować inne atrybuty legendy?

Tak, możesz dostosować różne atrybuty legendy, takie jak styl czcionki, obramowanie, kolor tła i inne. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat dalszego dostosowywania legend.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}