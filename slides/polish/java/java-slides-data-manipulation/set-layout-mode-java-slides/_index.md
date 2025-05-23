---
"description": "Dowiedz się, jak ustawić tryby układu dla slajdów Java za pomocą Aspose.Slides. Dostosuj pozycjonowanie i rozmiar wykresu w tym przewodniku krok po kroku z kodem źródłowym."
"linktitle": "Ustaw tryb układu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw tryb układu w slajdach Java"
"url": "/pl/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw tryb układu w slajdach Java


## Wprowadzenie do ustawiania trybu układu w slajdach Java

tym samouczku nauczymy się, jak ustawić tryb układu dla wykresu w slajdach Java przy użyciu Aspose.Slides for Java. Tryb układu określa pozycjonowanie i rozmiar wykresu w slajdzie.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację

Najpierw musimy utworzyć nową prezentację.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj slajd i wykres

Następnie dodamy do niego slajd i wykres. W tym przykładzie utworzymy wykres kolumnowy klastrowany.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Krok 3: Ustaw układ wykresu

Teraz ustawmy układ wykresu. Dostosujemy położenie i rozmiar wykresu w slajdzie za pomocą `setX`, `setY`, `setWidth`, `setHeight` metody. Dodatkowo ustawimy `LayoutTargetType` aby określić tryb układu.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

tym przykładzie ustawiliśmy typ układu docelowego wykresu na „Wewnętrzny”, co oznacza, że będzie on pozycjonowany i skalowany względem wewnętrznego obszaru slajdu.

## Krok 4: Zapisz prezentację

Na koniec zapiszemy prezentację z ustawieniami układu wykresu.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla trybu ustawiania układu w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak ustawić tryb układu dla wykresu w slajdach Java przy użyciu Aspose.Slides for Java. Możesz dostosować położenie i rozmiar wykresu zgodnie ze swoimi konkretnymi wymaganiami, dostosowując wartości w `setX`, `setY`, `setWidth`, `setHeight`, I `setLayoutTargetType` metod. Dzięki temu możesz kontrolować rozmieszczenie wykresów na slajdach.

## Najczęściej zadawane pytania

### Jak zmienić tryb układu wykresu w Aspose.Slides dla Java?

Aby zmienić tryb układu wykresu w Aspose.Slides dla Java, możesz użyć `setLayoutTargetType` metodę na obszarze wykresu. Możesz ustawić ją na `LayoutTargetType.Inner` Lub `LayoutTargetType.Outer` zależności od pożądanego układu.

### Czy mogę dostosować położenie i rozmiar wykresu na slajdzie?

Tak, możesz dostosować położenie i rozmiar wykresu na slajdzie, korzystając z `setX`, `setY`, `setWidth`, I `setHeight` metody na obszarze wykresu. Dostosuj te wartości, aby ustawić i zmienić rozmiar wykresu zgodnie ze swoimi wymaganiami.

### Gdzie mogę znaleźć więcej informacji o Aspose.Slides dla Java?

Więcej informacji na temat Aspose.Slides dla Java można znaleźć w [dokumentacja](https://reference.aspose.com/slides/java/)Zawiera szczegółowe odniesienia do API i przykłady, które pomogą Ci efektywnie pracować ze slajdami i wykresami w Javie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}