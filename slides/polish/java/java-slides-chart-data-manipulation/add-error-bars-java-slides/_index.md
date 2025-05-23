---
"description": "Dowiedz się, jak dodawać paski błędów do wykresów PowerPoint w Javie za pomocą Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym do dostosowywania pasków błędów."
"linktitle": "Dodaj paski błędów w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj paski błędów w slajdach Java"
"url": "/pl/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj paski błędów w slajdach Java


## Wprowadzenie do dodawania pasków błędów w slajdach Java przy użyciu Aspose.Slides

W tym samouczku pokażemy, jak dodać paski błędów do wykresu w slajdzie programu PowerPoint za pomocą Aspose.Slides for Java. Paski błędów dostarczają cennych informacji o zmienności lub niepewności punktów danych na wykresie. Utworzymy wykres bąbelkowy i dodamy do niego paski błędów. Zaczynajmy!

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w Twoim projekcie Java. Możesz pobrać bibliotekę ze strony [Strona internetowa Aspose](https://downloads.aspose.com/slides/java).

## Krok 1: Utwórz pustą prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
```

W tym kroku utworzymy pustą prezentację, do której dodamy wykres z paskami błędów.

## Krok 2: Utwórz wykres bąbelkowy

```java
// Tworzenie wykresu bąbelkowego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Tutaj tworzymy wykres bąbelkowy i określamy jego położenie oraz wymiary na slajdzie.

## Krok 3: Dodawanie pasków błędów i ustawianie formatu

```java
// Dodawanie pasków błędów i ustawianie ich formatu
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

W tym kroku dodajemy paski błędów do wykresu i ustawiamy ich format. Możesz dostosować paski błędów, zmieniając wartości, typy i inne właściwości.

- `errBarX` przedstawia paski błędów wzdłuż osi X.
- `errBarY` przedstawia paski błędów wzdłuż osi Y.
- Uwidaczniamy paski błędów X i Y.
- `setValueType` określa typ wartości dla słupków błędów (np. Stały lub Procentowy).
- `setValue` ustawia wartości dla słupków błędów.
- `setType` definiuje typ słupków błędów (np. Plus lub Minus).
- Ustawiamy szerokość linii słupka błędu za pomocą `getFormat().getLine().setWidth(2)`.
- `setEndCap` określa, czy na paskach błędów mają być umieszczane zaślepki.

## Krok 4: Zapisz prezentację

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację z dodanymi paskami błędów w określonej lokalizacji.

To wszystko! Udało Ci się dodać paski błędów do wykresu na slajdzie programu PowerPoint przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy do dodawania pasków błędów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
try
{
	// Tworzenie wykresu bąbelkowego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Dodawanie pasków błędów i ustawianie ich formatu
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Zapisywanie prezentacji
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku sprawdziliśmy, jak ulepszyć prezentacje PowerPoint, dodając paski błędów do wykresów za pomocą Aspose.Slides for Java. Paski błędów dostarczają cennych informacji na temat zmienności danych i niepewności, dzięki czemu prezentacje są bardziej pouczające i atrakcyjne wizualnie.

## Najczęściej zadawane pytania

### W jaki sposób mogę jeszcze bardziej dostosować wygląd pasków błędów?

Możesz dostosować paski błędów, modyfikując ich właściwości, takie jak styl linii, kolor i szerokość, jak pokazano w kroku 3.

### Czy mogę dodać słupki błędów do różnych typów wykresów?

Tak, możesz dodać paski błędów do różnych typów wykresów obsługiwanych przez Aspose.Slides dla Java. Po prostu utwórz żądany typ wykresu i wykonaj te same kroki dostosowywania paska błędów.

### Jak mogę zmienić położenie i rozmiar wykresu na slajdzie?

Możesz kontrolować położenie i wymiary wykresu, dostosowując parametry w `addChart` metodę, jak pokazano w kroku 2.

### Gdzie mogę znaleźć więcej informacji o Aspose.Slides dla Java?

Możesz zapoznać się z [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) Aby uzyskać szczegółowe informacje dotyczące korzystania z biblioteki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}