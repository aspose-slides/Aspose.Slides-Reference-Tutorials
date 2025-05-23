---
"description": "Dowiedz się, jak ustawić dane wykresu z skoroszytu programu Excel w Java Slides przy użyciu Aspose.Slides. Przewodnik krok po kroku z przykładami kodu dla dynamicznych prezentacji."
"linktitle": "Ustaw dane wykresu z skoroszytu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw dane wykresu z skoroszytu w slajdach Java"
"url": "/pl/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw dane wykresu z skoroszytu w slajdach Java


## Wprowadzenie do ustawiania danych wykresu z skoroszytu w slajdach Java

Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom programową pracę z prezentacjami PowerPoint. Oferuje ona rozbudowane funkcje tworzenia, manipulowania i zarządzania slajdami PowerPoint. Jednym z powszechnych wymagań podczas pracy z prezentacjami jest dynamiczne ustawianie danych wykresu z zewnętrznego źródła danych, takiego jak skoroszyt programu Excel. W tym samouczku pokażemy, jak to osiągnąć za pomocą języka Java.

## Wymagania wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełnione są następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została dodana do projektu.
- Skoroszyt programu Excel zawierający dane, których chcesz użyć w wykresie.

## Krok 1: Utwórz prezentację

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Zacznijmy od utworzenia nowej prezentacji PowerPoint za pomocą Aspose.Slides dla Java.

## Krok 2: Dodaj wykres

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Następnie dodajemy wykres do jednego ze slajdów prezentacji. W tym przykładzie dodajemy wykres kołowy, ale możesz wybrać typ wykresu, który odpowiada Twoim potrzebom.

## Krok 3: Wyczyść dane wykresu

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Usuwamy wszelkie istniejące dane z wykresu, aby przygotować go na nowe dane z arkusza kalkulacyjnego programu Excel.

## Krok 4: Załaduj skoroszyt programu Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Ładujemy skoroszyt programu Excel zawierający dane, których chcemy użyć do wykresu. Zastąp `"book1.xlsx"` ze ścieżką do pliku Excel.

## Krok 5: Zapisz strumień skoroszytu na dane wykresu

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Konwertujemy dane z arkusza kalkulacyjnego Excel na strumień i zapisujemy go w danych wykresu.

## Krok 6: Ustaw zakres danych wykresu

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Określamy zakres komórek z skoroszytu programu Excel, które powinny być użyte jako dane dla wykresu. Dostosuj zakres zgodnie z potrzebami swoich danych.

## Krok 7: Dostosuj serię wykresów

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Możesz dostosować różne właściwości serii wykresów, aby dopasować je do swoich wymagań. W tym przykładzie włączamy różne kolory dla serii wykresów.

## Krok 8: Zapisz prezentację

```java
pres.save(outPath, SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację ze zaktualizowanymi danymi wykresu w określonej ścieżce wyjściowej.

## Kompletny kod źródłowy dla zestawu danych wykresu z skoroszytu w slajdach Java

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

W tym samouczku nauczyliśmy się, jak ustawić dane wykresu z skoroszytu programu Excel w Java Slides przy użyciu biblioteki Aspose.Slides for Java. Postępując zgodnie z przewodnikiem krok po kroku i korzystając z podanych przykładów kodu źródłowego, możesz łatwo zintegrować dynamiczne dane wykresu z prezentacjami PowerPoint.

## Najczęściej zadawane pytania

### Jak mogę dostosować wygląd wykresu w mojej prezentacji?

Możesz dostosować wygląd wykresu, modyfikując właściwości, takie jak kolory, czcionki, etykiety i inne. Zapoznaj się z dokumentacją Aspose.Slides for Java, aby uzyskać szczegółowe informacje na temat opcji dostosowywania wykresu.

### Czy mogę wykorzystać dane z innego pliku Excela do wykresu?

Tak, możesz wykorzystać dane z dowolnego pliku Excel, podając prawidłową ścieżkę pliku podczas ładowania skoroszytu w kodzie.

### Jakie inne typy wykresów mogę tworzyć za pomocą Aspose.Slides dla Java?

Aspose.Slides for Java obsługuje różne typy wykresów, w tym wykresy słupkowe, wykresy liniowe, wykresy punktowe i inne. Możesz wybrać typ wykresu, który najlepiej odpowiada Twoim potrzebom w zakresie reprezentacji danych.

### Czy można dynamicznie aktualizować dane na wykresie w trwającej prezentacji?

Tak, możesz dynamicznie aktualizować dane na wykresie w prezentacji, modyfikując skoroszyt, a następnie odświeżając dane na wykresie.

### Gdzie mogę znaleźć więcej przykładów i materiałów dotyczących pracy z Aspose.Slides dla Java?

Możesz zapoznać się z dodatkowymi przykładami i zasobami na stronie [Strona internetowa Aspose](https://www.aspose.com/). Ponadto dokumentacja Aspose.Slides for Java zapewnia kompleksowe wskazówki dotyczące pracy z tą biblioteką.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}