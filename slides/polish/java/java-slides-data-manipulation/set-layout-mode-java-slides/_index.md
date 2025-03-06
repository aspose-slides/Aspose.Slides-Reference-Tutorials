---
title: Ustaw tryb układu w slajdach Java
linktitle: Ustaw tryb układu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić tryby układu slajdów Java za pomocą Aspose.Slides. Dostosuj położenie i rozmiar wykresu w tym przewodniku krok po kroku z kodem źródłowym.
type: docs
weight: 23
url: /pl/java/data-manipulation/set-layout-mode-java-slides/
---

## Wprowadzenie do ustawiania trybu układu w slajdach Java

W tym samouczku dowiemy się, jak ustawić tryb układu wykresu na slajdach Java za pomocą Aspose.Slides for Java. Tryb układu określa położenie i rozmiar wykresu na slajdzie.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację

Najpierw musimy utworzyć nową prezentację.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj slajd i wykres

Następnie dodamy do niego slajd i wykres. W tym przykładzie utworzymy grupowany wykres kolumnowy.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Krok 3: Ustaw układ wykresu

 Teraz ustawmy układ wykresu. Położenie i rozmiar wykresu na slajdzie dopasujemy za pomocą przycisku`setX`, `setY`, `setWidth`, `setHeight` metody. Dodatkowo ustawimy`LayoutTargetType` aby określić tryb układu.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

W tym przykładzie ustawiliśmy docelowy układ wykresu na „Wewnętrzny”, co oznacza, że jego położenie i rozmiar zostaną dostosowane do wewnętrznego obszaru slajdu.

## Krok 4: Zapisz prezentację

Na koniec zapiszmy prezentację z ustawieniami układu wykresu.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do ustawiania trybu układu w slajdach Java

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

 W tym samouczku nauczyliśmy się, jak ustawić tryb układu wykresu na slajdach Java za pomocą Aspose.Slides for Java. Możesz dostosować położenie i rozmiar wykresu zgodnie ze swoimi konkretnymi wymaganiami, dostosowując wartości w pliku`setX`, `setY`, `setWidth`, `setHeight` , I`setLayoutTargetType`metody. Dzięki temu masz kontrolę nad rozmieszczeniem wykresów na slajdach.

## Często zadawane pytania

### Jak zmienić tryb układu wykresu w Aspose.Slides dla Java?

 Aby zmienić tryb układu wykresu w Aspose.Slides dla Java, możesz użyć opcji`setLayoutTargetType` metodę na obszarze wykresu. Możesz to ustawić na jedno i drugie`LayoutTargetType.Inner` Lub`LayoutTargetType.Outer` w zależności od pożądanego układu.

### Czy mogę dostosować położenie i rozmiar wykresu na slajdzie?

 Tak, możesz dostosować położenie i rozmiar wykresu na slajdzie, korzystając z opcji`setX`, `setY`, `setWidth` , I`setHeight` metody na obszarze wykresu. Dostosuj te wartości, aby ustawić położenie i rozmiar wykresu zgodnie z własnymi wymaganiami.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Slides dla Java?

 Więcej informacji na temat Aspose.Slides dla Java można znaleźć w[dokumentacja](https://reference.aspose.com/slides/java/). Zawiera szczegółowe odniesienia do API i przykłady, które pomogą Ci efektywnie pracować ze slajdami i wykresami w Javie.