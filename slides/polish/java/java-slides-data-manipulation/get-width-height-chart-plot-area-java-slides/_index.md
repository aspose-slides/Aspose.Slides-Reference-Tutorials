---
title: Uzyskaj szerokość i wysokość z obszaru wykresu w Java Slides
linktitle: Uzyskaj szerokość i wysokość z obszaru wykresu w Java Slides
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak pobrać wymiary obszaru wykresu w Java Slides za pomocą Aspose.Slides dla Java. Popraw swoje umiejętności automatyzacji programu PowerPoint.
weight: 21
url: /pl/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uzyskaj szerokość i wysokość z obszaru wykresu w Java Slides


## Wstęp

Wykresy to skuteczny sposób wizualizacji danych w prezentacjach programu PowerPoint. Czasami znajomość wymiarów obszaru wykresu może być konieczna z różnych powodów, takich jak zmiana rozmiaru lub położenia elementów na wykresie. W tym przewodniku zademonstrujemy, jak uzyskać szerokość i wysokość obszaru działki przy użyciu języka Java i Aspose.Slides dla języka Java.

## Warunki wstępne

 Zanim zagłębimy się w kod, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę można pobrać ze strony internetowej Aspose[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Konfigurowanie środowiska

Upewnij się, że do projektu Java dodano bibliotekę Aspose.Slides for Java. Możesz to zrobić włączając bibliotekę do zależności projektu lub ręcznie dodając plik JAR.

## Krok 2: Tworzenie prezentacji PowerPoint

Zacznijmy od stworzenia prezentacji PowerPoint i dodania do niej slajdu. Będzie to służyć jako pojemnik na nasz wykres.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Zastępować`"Your Document Directory"` ze ścieżką do katalogu dokumentów.

## Krok 3: Dodawanie wykresu

Dodajmy teraz do slajdu grupowany wykres kolumnowy. Zweryfikujemy również układ wykresu.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Ten kod tworzy grupowany wykres kolumnowy w pozycji (100, 100) z wymiarami (500, 350).

## Krok 4: Uzyskanie wymiarów powierzchni działki

Aby pobrać szerokość i wysokość obszaru wykresu, możemy użyć następującego kodu:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Teraz zmienne`x`, `y`, `w` , I`h` zawierają odpowiednie wartości współrzędnej X, współrzędnej Y, szerokości i wysokości obszaru kreślenia.

## Krok 5: Zapisywanie prezentacji

Na koniec zapisz prezentację z wykresem.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Pamiętaj o wymianie`"Chart_out.pptx"` z żądaną nazwą pliku wyjściowego.

## Kompletny kod źródłowy umożliwiający uzyskanie szerokości i wysokości z obszaru wykresu w aplikacji Java Slides

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

tym artykule omówiliśmy, jak uzyskać szerokość i wysokość obszaru wykresu w aplikacji Java Slides przy użyciu interfejsu API Aspose.Slides for Java. Informacje te mogą być przydatne, gdy trzeba dynamicznie dostosowywać układ wykresów w prezentacjach programu PowerPoint.

## Często zadawane pytania

### Jak zmienić typ wykresu na inny niż kolumnowy?

 Typ wykresu można zmienić, zastępując go`ChartType.ClusteredColumn` z żądanym wyliczeniem typu wykresu, np`ChartType.Line` Lub`ChartType.Pie`.

### Czy mogę modyfikować inne właściwości wykresu?

Tak, możesz modyfikować różne właściwości wykresu, takie jak dane, etykiety i formatowanie, używając interfejsu API Aspose.Slides for Java. Więcej szczegółów można znaleźć w dokumentacji.

### Czy Aspose.Slides for Java nadaje się do profesjonalnej automatyzacji programu PowerPoint?

Tak, Aspose.Slides for Java to potężna biblioteka do automatyzacji zadań programu PowerPoint w aplikacjach Java. Zapewnia wszechstronne funkcje do pracy z prezentacjami, slajdami, kształtami, wykresami i nie tylko.

### Jak mogę dowiedzieć się więcej o Aspose.Slides dla Java?

 Obszerną dokumentację i przykłady można znaleźć na stronie dokumentacji Aspose.Slides for Java[Tutaj](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
