---
title: Legenda rozmiaru czcionki w slajdach Java
linktitle: Legenda rozmiaru czcionki w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz prezentacje programu PowerPoint za pomocą Aspose.Slides dla Java. Z naszego przewodnika krok po kroku dowiesz się, jak dostosować rozmiary czcionek legendy i nie tylko.
type: docs
weight: 13
url: /pl/java/chart-elements/font-size-legend-java-slides/
---

## Wprowadzenie do legendy rozmiaru czcionki w slajdach Java

W tym samouczku dowiesz się, jak dostosować rozmiar czcionki legendy na slajdzie programu PowerPoint za pomocą Aspose.Slides dla Java. Dostarczymy instrukcje krok po kroku i kod źródłowy, aby osiągnąć to zadanie.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Zainicjuj prezentację

Najpierw zaimportuj niezbędne klasy i zainicjuj prezentację programu PowerPoint.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do pliku programu PowerPoint.

## Krok 2: Dodaj wykres

Następnie dodamy wykres do slajdu i ustalimy rozmiar czcionki legendy.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 W tym kodzie tworzymy grupowany wykres kolumnowy na pierwszym slajdzie i ustawiamy rozmiar czcionki tekstu legendy na 20 punktów. Możesz dostosować`setFontHeight`wartość, aby zmienić rozmiar czcionki według potrzeb.

## Krok 3: Dostosuj wartości osi

Teraz dostosujmy wartości osi pionowej wykresu.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Tutaj ustawiamy wartości minimalne i maksymalne dla osi pionowej. Możesz modyfikować wartości zgodnie z wymaganiami dotyczącymi danych.

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

Pomyślnie dostosowałeś rozmiar czcionki legendy na slajdzie Java PowerPoint za pomocą Aspose.Slides for Java. Możesz dalej eksplorować możliwości Aspose.Slides, aby tworzyć interaktywne i atrakcyjne wizualnie prezentacje.

## Często zadawane pytania

### Jak zmienić rozmiar czcionki tekstu legendy na wykresie?

Aby zmienić rozmiar czcionki tekstu legendy na wykresie, możesz użyć następującego kodu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 W tym kodzie tworzymy wykres i ustawiamy rozmiar czcionki tekstu legendy na 20 punktów. Możesz dostosować`setFontHeight` wartość, aby zmienić rozmiar czcionki.

### Czy mogę dostosować inne właściwości legendy na wykresie?

Tak, możesz dostosować różne właściwości legendy na wykresie za pomocą Aspose.Slides. Niektóre z typowych właściwości, które można dostosować, obejmują formatowanie tekstu, położenie, widoczność i inne. Na przykład, aby zmienić położenie legendy, możesz użyć:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ten kod ustawia wyświetlanie legendy na dole wykresu. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać więcej opcji dostosowywania.

### Jak ustawić minimalne i maksymalne wartości osi pionowej na wykresie?

Aby ustawić minimalne i maksymalne wartości osi pionowej na wykresie, możesz użyć następującego kodu:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Tutaj wyłączamy automatyczne skalowanie osi i określamy minimalne i maksymalne wartości dla osi pionowej. Dostosuj wartości zgodnie z potrzebami danych wykresu.

### Gdzie mogę znaleźć więcej informacji i dokumentacji dla Aspose.Slides?

 Obszerną dokumentację i odniesienia do API dla Aspose.Slides for Java można znaleźć na stronie dokumentacji Aspose. Odwiedzać[Tutaj](https://reference.aspose.com/slides/java/) szczegółowe informacje na temat korzystania z biblioteki.