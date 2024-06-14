---
title: Ustaw dane wykresu ze skoroszytu w slajdach Java
linktitle: Ustaw dane wykresu ze skoroszytu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić dane wykresu ze skoroszytu programu Excel w aplikacji Java Slides za pomocą Aspose.Slides. Przewodnik krok po kroku z przykładami kodu do prezentacji dynamicznych.
type: docs
weight: 15
url: /pl/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Wprowadzenie do ustawiania danych wykresu ze skoroszytu w slajdach Java

Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom programową pracę z prezentacjami programu PowerPoint. Zapewnia rozbudowane funkcje do tworzenia, manipulowania i zarządzania slajdami programu PowerPoint. Jednym z typowych wymagań podczas pracy z prezentacjami jest dynamiczne ustawianie danych wykresu z zewnętrznego źródła danych, takiego jak skoroszyt programu Excel. W tym samouczku pokażemy, jak to osiągnąć za pomocą języka Java.

## Warunki wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełniasz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Do Twojego projektu dodano bibliotekę Aspose.Slides for Java.
- Skoroszyt programu Excel zawierający dane, których chcesz użyć na wykresie.

## Krok 1: Utwórz prezentację

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Zaczynamy od stworzenia nowej prezentacji PowerPoint przy użyciu Aspose.Slides for Java.

## Krok 2: Dodaj wykres

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Następnie dodajemy wykres do jednego ze slajdów w prezentacji. W tym przykładzie dodajemy wykres kołowy, ale możesz wybrać typ wykresu odpowiadający Twoim potrzebom.

## Krok 3: Wyczyść dane wykresu

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Usuwamy z wykresu wszelkie istniejące dane, aby przygotować je na nowe dane ze skoroszytu programu Excel.

## Krok 4: Załaduj skoroszyt programu Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Ładujemy skoroszyt Excela, który zawiera dane, które chcemy wykorzystać na wykresie. Zastępować`"book1.xlsx"` ze ścieżką do pliku Excel.

## Krok 5: Zapisz strumień skoroszytu do danych wykresu

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Konwertujemy dane ze skoroszytu programu Excel na strumień i zapisujemy je do danych wykresu.

## Krok 6: Ustaw zakres danych wykresu

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Określamy zakres komórek ze skoroszytu Excela, które mają zostać wykorzystane jako dane do wykresu. Dostosuj zakres zgodnie z potrzebami danych.

## Krok 7: Dostosuj serię wykresów

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Możesz dostosować różne właściwości serii wykresów, aby dopasować je do swoich wymagań. W tym przykładzie umożliwiamy różne kolory serii wykresów.

## Krok 8: Zapisz prezentację

```java
pres.save(outPath, SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację ze zaktualizowanymi danymi wykresu do określonej ścieżki wyjściowej.

## Kompletny kod źródłowy dla zestawu danych wykresu ze skoroszytu w slajdach Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak ustawiać dane wykresu ze skoroszytu programu Excel w aplikacji Java Slides przy użyciu biblioteki Aspose.Slides for Java. Postępując zgodnie z przewodnikiem krok po kroku i korzystając z dostarczonych przykładów kodu źródłowego, możesz łatwo zintegrować dane wykresów dynamicznych z prezentacjami programu PowerPoint.

## Często zadawane pytania

### Jak mogę dostosować wygląd wykresu w mojej prezentacji?

Możesz dostosować wygląd wykresu, modyfikując właściwości, takie jak kolory, czcionki, etykiety i inne. Szczegółowe informacje na temat opcji dostosowywania wykresów można znaleźć w dokumentacji Aspose.Slides for Java.

### Czy do wykresu mogę użyć danych z innego pliku Excel?

Tak, możesz wykorzystać dane z dowolnego pliku Excel podając poprawną ścieżkę pliku podczas ładowania skoroszytu w kodzie.

### Jakie inne typy wykresów mogę tworzyć za pomocą Aspose.Slides dla Java?

Aspose.Slides for Java obsługuje różne typy wykresów, w tym wykresy słupkowe, wykresy liniowe, wykresy punktowe i inne. Możesz wybrać typ wykresu, który najlepiej odpowiada Twoim potrzebom w zakresie reprezentacji danych.

### Czy można dynamicznie aktualizować dane wykresu w działającej prezentacji?

Tak, możesz dynamicznie aktualizować dane wykresu w prezentacji, modyfikując bazowy skoroszyt, a następnie odświeżając dane wykresu.

### Gdzie mogę znaleźć więcej przykładów i zasobów dotyczących pracy z Aspose.Slides dla Java?

 Dodatkowe przykłady i zasoby można znaleźć na stronie[Strona Aspose](https://www.aspose.com/). Dodatkowo dokumentacja Aspose.Slides for Java zawiera kompleksowe wskazówki dotyczące pracy z biblioteką.