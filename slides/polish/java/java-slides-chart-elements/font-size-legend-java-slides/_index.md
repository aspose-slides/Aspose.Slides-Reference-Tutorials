---
"description": "Ulepsz prezentacje PowerPoint dzięki Aspose.Slides dla Java. Dowiedz się, jak dostosować rozmiary czcionek legendy i nie tylko w naszym przewodniku krok po kroku."
"linktitle": "Legenda rozmiaru czcionki w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Legenda rozmiaru czcionki w slajdach Java"
"url": "/pl/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda rozmiaru czcionki w slajdach Java


## Wprowadzenie do legendy rozmiaru czcionki w slajdach Java

tym samouczku dowiesz się, jak dostosować rozmiar czcionki legendy w slajdzie programu PowerPoint za pomocą Aspose.Slides for Java. Podamy instrukcje krok po kroku i kod źródłowy, aby wykonać to zadanie.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Zainicjuj prezentację

Najpierw zaimportuj niezbędne klasy i zainicjuj prezentację programu PowerPoint.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Zastępować `"Your Document Directory"` z rzeczywistą ścieżką do pliku PowerPoint.

## Krok 2: Dodaj wykres

Następnie dodamy wykres do slajdu i ustawimy rozmiar czcionki legendy.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

W tym kodzie tworzymy wykres kolumnowy klastrowany na pierwszym slajdzie i ustawiamy rozmiar czcionki tekstu legendy na 20 punktów. Możesz dostosować `setFontHeight` wartość umożliwiająca zmianę rozmiaru czcionki w razie potrzeby.

## Krok 3: Dostosuj wartości osi

Teraz dostosujemy wartości osi pionowej wykresu.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Tutaj ustawiamy minimalne i maksymalne wartości dla osi pionowej. Możesz modyfikować wartości zgodnie z wymaganiami danych.

## Krok 4: Zapisz prezentację

Na koniec zapisz zmodyfikowaną prezentację w nowym pliku.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Ten kod zapisuje zmodyfikowaną prezentację jako „output.pptx” w określonym katalogu.

## Kompletny kod źródłowy legendy rozmiaru czcionki w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Udało Ci się dostosować rozmiar czcionki legendy w slajdzie Java PowerPoint przy użyciu Aspose.Slides for Java. Możesz dalej eksplorować możliwości Aspose.Slides, aby tworzyć interaktywne i atrakcyjne wizualnie prezentacje.

## Najczęściej zadawane pytania

### Jak zmienić rozmiar czcionki tekstu legendy na wykresie?

Aby zmienić rozmiar czcionki tekstu legendy na wykresie, możesz użyć następującego kodu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

tym kodzie tworzymy wykres i ustawiamy rozmiar czcionki tekstu legendy na 20 punktów. Możesz dostosować `setFontHeight` wartość umożliwiająca zmianę rozmiaru czcionki.

### Czy mogę dostosować inne właściwości legendy na wykresie?

Tak, możesz dostosować różne właściwości legendy na wykresie za pomocą Aspose.Slides. Niektóre z typowych właściwości, które możesz dostosować, obejmują formatowanie tekstu, pozycję, widoczność i inne. Na przykład, aby zmienić pozycję legendy, możesz użyć:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ten kod ustawia legendę tak, aby pojawiała się na dole wykresu. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać więcej opcji dostosowywania.

### Jak ustawić wartości minimalne i maksymalne dla osi pionowej na wykresie?

Aby ustawić minimalne i maksymalne wartości dla osi pionowej na wykresie, możesz użyć następującego kodu:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Tutaj wyłączamy automatyczne skalowanie osi i określamy minimalne i maksymalne wartości dla osi pionowej. Dostosuj wartości zgodnie z potrzebami danych wykresu.

### Gdzie mogę znaleźć więcej informacji i dokumentacji na temat Aspose.Slides?

Możesz znaleźć pełną dokumentację i odniesienia API dla Aspose.Slides dla Java na stronie dokumentacji Aspose. Odwiedź [Tutaj](https://reference.aspose.com/slides/java/) Aby uzyskać szczegółowe informacje dotyczące korzystania z biblioteki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}