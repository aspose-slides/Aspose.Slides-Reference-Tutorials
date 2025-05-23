---
"description": "Dowiedz się, jak ustawić automatyczny kolor wypełnienia serii w Java Slides przy użyciu Aspose.Slides for Java. Przewodnik krok po kroku z przykładami kodu dla dynamicznych prezentacji."
"linktitle": "Ustaw automatyczne wypełnienie kolorem serii w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw automatyczne wypełnienie kolorem serii w slajdach Java"
"url": "/pl/java/data-manipulation/set-automatic-series-fill-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw automatyczne wypełnienie kolorem serii w slajdach Java


## Wprowadzenie do ustawiania automatycznego koloru wypełnienia serii w slajdach Java

tym samouczku pokażemy, jak ustawić automatyczny kolor wypełnienia serii w Java Slides przy użyciu interfejsu API Aspose.Slides for Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i zarządzanie prezentacjami PowerPoint. Pod koniec tego przewodnika będziesz w stanie bez wysiłku tworzyć wykresy i ustawiać automatyczne kolory wypełnienia serii.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została dodana do Twojego projektu. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

Teraz, gdy mamy już gotowy plan, możemy przejść do przewodnika krok po kroku.

## Krok 1: Wprowadzenie do Aspose.Slides dla Java

Aspose.Slides for Java to API Java, które umożliwia programistom pracę z prezentacjami PowerPoint. Oferuje szeroki zakres funkcji, w tym tworzenie, edycję i manipulowanie slajdami, wykresami, kształtami i nie tylko.

## Krok 2: Konfigurowanie projektu Java

Zanim zaczniemy kodować, upewnij się, że skonfigurowałeś projekt Java w preferowanym Zintegrowanym Środowisku Programistycznym (IDE). Upewnij się, że dodałeś bibliotekę Aspose.Slides for Java do swojego projektu.

## Krok 3: Tworzenie prezentacji PowerPoint

Aby rozpocząć, utwórz nową prezentację programu PowerPoint, korzystając z następującego fragmentu kodu:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

Zastępować `"Your Document Directory"` ze ścieżką, pod którą chcesz zapisać prezentację.

## Krok 4: Dodawanie wykresu do prezentacji

Następnie dodajmy do prezentacji wykres kolumnowy klastrowany. Użyjemy następującego kodu, aby to osiągnąć:

```java
// Tworzenie wykresu kolumnowego klastrowanego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Ten kod tworzy wykres kolumnowy na pierwszym slajdzie prezentacji.

## Krok 5: Ustawianie automatycznego koloru wypełnienia serii

Teraz nadchodzi kluczowa część — ustawienie automatycznego koloru wypełnienia serii. Przejdziemy przez serie wykresu i ustawimy ich format wypełnienia na automatyczny:

```java
// Ustawianie automatycznego formatu wypełniania serii
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Ten kod zapewnia, że kolor wypełnienia serii zostanie ustawiony na automatyczny.

## Krok 6: Zapisywanie prezentacji

Aby zapisać prezentację użyj następującego kodu:

```java
// Zapisz plik prezentacji na dysku
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

Zastępować `"AutoFillSeries_out.pptx"` z żądaną nazwą pliku.

## Kompletny kod źródłowy do ustawienia automatycznego wypełnienia serii kolorem w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Tworzenie wykresu kolumnowego klastrowanego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Ustawianie automatycznego formatu wypełniania serii
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

Gratulacje! Udało Ci się ustawić automatyczne wypełnienie kolorem serii w Java Slide przy użyciu Aspose.Slides for Java. Teraz możesz wykorzystać tę wiedzę, aby tworzyć dynamiczne i atrakcyjne wizualnie prezentacje PowerPoint w swoich aplikacjach Java.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ wykresu na inny styl?

Możesz zmienić typ wykresu, zastępując `ChartType.ClusteredColumn` z wybranym typem wykresu, takim jak `ChartType.Line` Lub `ChartType.Pie`.

### Czy mogę dodatkowo dostosować wygląd wykresu?

Tak, możesz dostosować wygląd wykresu, modyfikując różne jego właściwości, takie jak kolory, czcionki i etykiety.

### Czy Aspose.Slides for Java nadaje się do użytku komercyjnego?

Tak, Aspose.Slides for Java może być używany zarówno do projektów osobistych, jak i komercyjnych. Więcej szczegółów można znaleźć w warunkach licencji.

### Czy Aspose.Slides udostępnia jakieś inne funkcje dla Java?

Tak, Aspose.Slides for Java oferuje szeroką gamę funkcji, w tym manipulację slajdami, formatowanie tekstu i obsługę animacji.

### Gdzie mogę znaleźć więcej materiałów i dokumentacji?

Pełną dokumentację Aspose.Slides dla języka Java można uzyskać pod adresem [Tutaj](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}