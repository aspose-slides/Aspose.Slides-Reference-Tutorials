---
title: Ustaw kolor automatycznego wypełnienia serią w slajdach Java
linktitle: Ustaw kolor automatycznego wypełnienia serią w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić automatyczny kolor wypełnienia serii w Java Slides przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu do prezentacji dynamicznych.
weight: 14
url: /pl/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw kolor automatycznego wypełnienia serią w slajdach Java


## Wprowadzenie do ustawiania koloru automatycznego wypełnienia serii w slajdach Java

W tym samouczku omówimy, jak ustawić automatyczny kolor wypełnienia serii w slajdach Java za pomocą interfejsu API Aspose.Slides for Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i zarządzanie prezentacjami programu PowerPoint. Pod koniec tego przewodnika będziesz mógł bez wysiłku tworzyć wykresy i ustawiać kolory automatycznego wypełniania serii.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Do Twojego projektu dodano bibliotekę Aspose.Slides for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

Skoro mamy już gotowy zarys, zacznijmy od przewodnika krok po kroku.

## Krok 1: Wprowadzenie do Aspose.Slides dla Java

Aspose.Slides for Java to interfejs API języka Java, który umożliwia programistom pracę z prezentacjami programu PowerPoint. Zapewnia szeroką gamę funkcji, w tym tworzenie, edytowanie i manipulowanie slajdami, wykresami, kształtami i nie tylko.

## Krok 2: Konfigurowanie projektu Java

Zanim zaczniemy kodować, upewnij się, że skonfigurowałeś projekt Java w preferowanym zintegrowanym środowisku programistycznym (IDE). Pamiętaj, aby dodać do swojego projektu bibliotekę Aspose.Slides for Java.

## Krok 3: Tworzenie prezentacji PowerPoint

Aby rozpocząć, utwórz nową prezentację programu PowerPoint, korzystając z następującego fragmentu kodu:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 Zastępować`"Your Document Directory"` ze ścieżką, w której chcesz zapisać prezentację.

## Krok 4: Dodawanie wykresu do prezentacji

Następnie dodajmy do prezentacji grupowany wykres kolumnowy. Aby to osiągnąć, użyjemy następującego kodu:

```java
// Tworzenie grupowanego wykresu kolumnowego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Ten kod tworzy grupowany wykres kolumnowy na pierwszym slajdzie prezentacji.

## Krok 5: Ustawianie automatycznego koloru wypełnienia serią

Teraz następuje kluczowa część — ustawienie automatycznego koloru wypełnienia serią. Będziemy przeglądać serie wykresów i ustawiać ich format wypełnienia na automatyczny:

```java
// Ustawianie formatu wypełniania serią na automatyczny
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Ten kod gwarantuje, że kolor wypełnienia serii zostanie ustawiony na automatyczny.

## Krok 6: Zapisywanie prezentacji

Aby zapisać prezentację użyj następującego kodu:

```java
// Zapisz plik prezentacji na dysku
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 Zastępować`"AutoFillSeries_out.pptx"` z żądaną nazwą pliku.

## Kompletny kod źródłowy dla automatycznego ustawiania koloru wypełnienia serii w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Tworzenie grupowanego wykresu kolumnowego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Ustawianie formatu wypełniania serią na automatyczny
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Zapisz plik prezentacji na dysku
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

Gratulacje! Pomyślnie ustawiłeś kolor automatycznego wypełnienia serii na slajdzie Java przy użyciu Aspose.Slides dla Java. Możesz teraz wykorzystać tę wiedzę do tworzenia dynamicznych i atrakcyjnych wizualnie prezentacji PowerPoint w aplikacjach Java.

## Często zadawane pytania

### Jak zmienić typ wykresu na inny styl?

 Typ wykresu można zmienić, zastępując go`ChartType.ClusteredColumn` z żądanym typem wykresu, np`ChartType.Line` Lub`ChartType.Pie`.

### Czy mogę bardziej dostosować wygląd wykresu?

Tak, możesz dostosować wygląd wykresu, modyfikując różne właściwości wykresu, takie jak kolory, czcionki i etykiety.

### Czy Aspose.Slides dla Java nadaje się do użytku komercyjnego?

Tak, Aspose.Slides for Java może być używany zarówno w projektach osobistych, jak i komercyjnych. Więcej szczegółów znajdziesz w warunkach licencji.

### Czy są jakieś inne funkcje udostępniane przez Aspose.Slides dla Java?

Tak, Aspose.Slides dla Java oferuje szeroką gamę funkcji, w tym manipulowanie slajdami, formatowanie tekstu i obsługę animacji.

### Gdzie mogę znaleźć więcej zasobów i dokumentacji?

 Dostęp do obszernej dokumentacji Aspose.Slides for Java można uzyskać pod adresem[Tutaj](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
