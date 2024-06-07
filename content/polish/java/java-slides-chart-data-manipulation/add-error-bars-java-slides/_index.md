---
title: Dodaj paski błędów w slajdach Java
linktitle: Dodaj paski błędów w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać słupki błędów do wykresów programu PowerPoint w Javie przy użyciu Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym umożliwiającym dostosowywanie słupków błędów.
type: docs
weight: 13
url: /pl/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Wprowadzenie do dodawania słupków błędów w slajdach Java przy użyciu Aspose.Slides

W tym samouczku pokażemy, jak dodać słupki błędów do wykresu na slajdzie programu PowerPoint za pomocą Aspose.Slides dla Java. Słupki błędów dostarczają cennych informacji na temat zmienności lub niepewności punktów danych na wykresie. Stworzymy wykres bąbelkowy i dodamy do niego słupki błędów. Zacznijmy!

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę można pobrać ze strony[Strona Aspose](https://downloads.aspose.com/slides/java).

## Krok 1: Utwórz pustą prezentację

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
```

tym kroku tworzymy pustą prezentację, do której dodamy nasz wykres ze słupkami błędów.

## Krok 2: Utwórz wykres bąbelkowy

```java
// Tworzenie wykresu bąbelkowego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Tutaj tworzymy wykres bąbelkowy oraz określamy jego położenie i wymiary na slajdzie.

## Krok 3: Dodawanie słupków błędów i ustawianie formatu

```java
// Dodawanie słupków błędów i ustawianie ich formatu
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

W tym kroku dodajemy słupki błędów do wykresu i ustalamy ich format. Można dostosować słupki błędów, zmieniając wartości, typy i inne właściwości.

- `errBarX` reprezentuje słupki błędów wzdłuż osi X.
- `errBarY` reprezentuje słupki błędów wzdłuż osi Y.
- Widoczne są słupki błędów X i Y.
- `setValueType` określa typ wartości słupków błędów (np. Stały lub Procentowy).
- `setValue` ustawia wartość słupków błędów.
- `setType` określa rodzaj słupków błędów (np. Plus lub Minus).
-  Szerokość linii słupków błędu ustalamy za pomocą`getFormat().getLine().setWidth(2)`.
- `setEndCap` określa, czy słupki błędów mają uwzględniać zaślepki końcowe.

## Krok 4: Zapisz prezentację

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację z dodanymi słupkami błędów w określonej lokalizacji.

Otóż to! Pomyślnie dodałeś słupki błędów do wykresu na slajdzie programu PowerPoint przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy umożliwiający dodawanie słupków błędów w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
try
{
	// Tworzenie wykresu bąbelkowego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Dodawanie słupków błędów i ustawianie ich formatu
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

W tym samouczku omówiliśmy, jak ulepszyć prezentacje programu PowerPoint, dodając słupki błędów do wykresów za pomocą Aspose.Slides dla Java. Słupki błędów dostarczają cennych informacji na temat zmienności i niepewności danych, dzięki czemu Twoje prezentacje są bardziej pouczające i atrakcyjne wizualnie.

## Często zadawane pytania

### Jak mogę bardziej dostosować wygląd słupków błędów?

Możesz dostosować słupki błędów, modyfikując ich właściwości, takie jak styl linii, kolor i szerokość, jak pokazano w kroku 3.

### Czy mogę dodać słupki błędów do różnych typów wykresów?

Tak, możesz dodać słupki błędów do różnych typów wykresów obsługiwanych przez Aspose.Slides dla Java. Po prostu utwórz żądany typ wykresu i wykonaj te same kroki dostosowywania paska błędów.

### Jak mogę dostosować położenie i rozmiar wykresu na slajdzie?

Możesz kontrolować położenie i wymiary wykresu, dostosowując parametry w pliku`addChart` metodę, jak pokazano w kroku 2.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Slides dla Java?

 Możesz odwołać się do[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) szczegółowe informacje na temat korzystania z biblioteki.