---
title: Właściwości czcionki dla wykresu w slajdach Java
linktitle: Właściwości czcionki dla wykresu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz właściwości czcionek wykresów w slajdach Java za pomocą Aspose.Slides dla Java. Dostosuj rozmiar, styl i kolor czcionki, aby uzyskać efektowne prezentacje.
weight: 11
url: /pl/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do właściwości czcionek dla wykresów w slajdach Java

Ten przewodnik przeprowadzi Cię przez proces ustawiania właściwości czcionki dla wykresu w Java Slides za pomocą Aspose.Slides. Możesz dostosować rozmiar czcionki i wygląd tekstu wykresu, aby poprawić atrakcyjność wizualną swoich prezentacji.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zintegrowane z projektem Aspose.Slides for Java API. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go ze strony[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację

Najpierw utwórz nową prezentację, używając następującego kodu:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Dodajmy teraz do Twojej prezentacji grupowany wykres kolumnowy:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Tutaj dodajemy grupowany wykres kolumnowy do pierwszego slajdu o współrzędnych (100, 100) o szerokości 500 jednostek i wysokości 400 jednostek.

## Krok 3: Dostosuj właściwości czcionki

Następnie dostosujemy właściwości czcionki wykresu. W tym przykładzie ustawiamy rozmiar czcionki na 20 dla całego tekstu wykresu:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ten kod ustawia rozmiar czcionki na 20 punktów dla całego tekstu na wykresie.

## Krok 4: Pokaż etykiety danych

Etykiety danych możesz także wyświetlić na wykresie, korzystając z następującego kodu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Ten wiersz kodu włącza etykiety danych dla pierwszej serii na wykresie, wyświetlając wartości w kolumnach wykresu.

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację ze dostosowanymi właściwościami czcionki wykresu:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ten kod zapisze prezentację w określonym katalogu pod nazwą pliku „FontPropertiesForChart.pptx”.

## Kompletny kod źródłowy właściwości czcionki dla wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

 tym samouczku nauczyłeś się dostosowywać właściwości czcionki dla wykresu w Java Slides za pomocą Aspose.Slides dla Java. Możesz zastosować te techniki, aby poprawić wygląd wykresów i prezentacji. Odkryj więcej opcji w[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Często zadawane pytania

### Jak mogę zmienić kolor czcionki?

 Aby zmienić kolor czcionki tekstu wykresu, użyj`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , zastępowanie`Color.RED` z żądanym kolorem.

### Czy mogę zmienić styl czcionki (pogrubienie, kursywa itp.)?

 Tak, możesz zmienić styl czcionki. Używać`chart.getTextFormat().getPortionFormat().setFontBold(true);` aby pogrubić czcionkę. Podobnie możesz użyć`setFontItalic(true)` aby było kursywą.

### Jak dostosować właściwości czcionki dla określonych elementów wykresu?

Aby dostosować właściwości czcionki dla określonych elementów wykresu, takich jak etykiety osi lub tekst legendy, możesz uzyskać dostęp do tych elementów i ustawić ich właściwości czcionki, korzystając z metod podobnych do pokazanych powyżej.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
