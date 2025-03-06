---
title: Ustaw niestandardowe opcje legendy w slajdach Java
linktitle: Ustaw niestandardowe opcje legendy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić niestandardowe opcje legendy w Java Slides za pomocą Aspose.Slides dla Java. Dostosuj położenie i rozmiar legendy na wykresach programu PowerPoint.
weight: 14
url: /pl/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do ustawiania niestandardowych opcji legendy w slajdach Java

W tym samouczku pokażemy, jak dostosować właściwości legendy wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Możesz modyfikować położenie, rozmiar i inne atrybuty legendy, aby dostosować je do potrzeb prezentacji.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowano Aspose.Slides dla Java API.
- Skonfigurowano środowisko programistyczne Java.

## Krok 1: Zaimportuj niezbędne klasy:

```java
// Importuj Aspose.Slides dla klas Java
import com.aspose.slides.*;
```

## Krok 2: Określ ścieżkę do katalogu dokumentów:

```java
String dataDir = "Your Document Directory";
```

##  Krok 3: Utwórz instancję`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Krok 4: Dodaj slajd do prezentacji:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Krok 5: Dodaj do slajdu grupowany wykres kolumnowy:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Krok 6. Ustaw właściwości legendy:

- Ustaw pozycję X legendy (w stosunku do szerokości wykresu):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Ustaw pozycję Y legendy (w stosunku do wysokości wykresu):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Ustaw szerokość legendy (w stosunku do szerokości wykresu):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Ustaw wysokość legendy (w stosunku do wysokości wykresu):

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

Otóż to! Pomyślnie dostosowałeś właściwości legendy wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy dla opcji niestandardowych zestawu legendy w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
try
{
	// Uzyskaj odniesienie do slajdu
	ISlide slide = presentation.getSlides().get_Item(0);
	// Dodaj grupowany wykres kolumnowy na slajdzie
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

W tym samouczku dowiedzieliśmy się, jak dostosować właściwości legendy wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Możesz modyfikować położenie, rozmiar i inne atrybuty legendy, aby stworzyć atrakcyjne wizualnie i pouczające prezentacje.

## Często zadawane pytania

## Jak mogę zmienić położenie legendy?

 Aby zmienić położenie legendy, użyj przycisku`setX` I`setY` metody obiektu legendy. Wartości są określone w odniesieniu do szerokości i wysokości wykresu.

## Jak mogę dostosować rozmiar legendy?

 Rozmiar legendy można dostosować za pomocą opcji`setWidth` I`setHeight` metody obiektu legendy. Wartości te odnoszą się także do szerokości i wysokości wykresu.

## Czy mogę dostosować inne atrybuty legendy?

Tak, możesz dostosować różne atrybuty legendy, takie jak styl czcionki, obramowanie, kolor tła i inne. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat dalszego dostosowywania legend.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
