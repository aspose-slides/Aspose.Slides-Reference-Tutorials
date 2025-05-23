---
"description": "Dowiedz się, jak ukryć elementy wykresu w Java Slides za pomocą Aspose.Slides for Java. Dostosuj prezentacje pod kątem przejrzystości i estetyki dzięki wskazówkom krok po kroku i kodowi źródłowemu."
"linktitle": "Ukryj informacje z wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ukryj informacje z wykresu w slajdach Java"
"url": "/pl/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ukryj informacje z wykresu w slajdach Java


## Wprowadzenie do ukrywania informacji z wykresu w slajdach Java

tym samouczku pokażemy, jak ukryć różne elementy na wykresie w Java Slides, używając Aspose.Slides for Java API. Możesz użyć tego kodu, aby dostosować wykresy do swoich prezentacji.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides for Java została dodana do Twojego projektu. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 2: Utwórz nową prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Dodawanie wykresu do slajdu

Dodamy do slajdu wykres liniowy ze znacznikami, a następnie ukryjemy różne elementy wykresu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Krok 4: Ukryj tytuł wykresu

Możesz ukryć tytuł wykresu w następujący sposób:

```java
chart.setTitle(false);
```

## Krok 5: Ukryj oś wartości

Aby ukryć oś wartości (oś pionową), użyj następującego kodu:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Krok 6: Ukryj oś kategorii

Aby ukryć oś kategorii (oś poziomą), użyj tego kodu:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Krok 7: Ukryj legendę

Możesz ukryć legendę wykresu w następujący sposób:

```java
chart.setLegend(false);
```

## Krok 8: Ukryj główne linie siatki

Aby ukryć główne linie siatki osi poziomej, możesz użyć następującego kodu:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Krok 9: Usuń serię

Jeśli chcesz usunąć wszystkie serie z wykresu, możesz użyć takiej pętli:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Krok 10: Dostosuj serię wykresów

Możesz dostosować serię wykresu według potrzeb. W tym przykładzie zmieniamy styl znacznika, pozycję etykiety danych, rozmiar znacznika, kolor linii i styl kreski:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Krok 11: Zapisz prezentację

Na koniec zapisz prezentację do pliku:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się ukryć różne elementy z wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Możesz dalej dostosowywać wykresy i prezentacje według potrzeb do swoich konkretnych wymagań.

## Kompletny kod źródłowy do ukrywania informacji z wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Ukrywanie tytułu wykresu
	chart.setTitle(false);
	///Ukrywanie osi wartości
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Widoczność osi kategorii
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Ukrywanie legendy
	chart.setLegend(false);
	//Ukrywanie głównych linii siatki
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Ustawianie koloru linii serii
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Wniosek

tym przewodniku krok po kroku sprawdziliśmy, jak ukryć różne elementy wykresu w Java Slides, korzystając z Aspose.Slides for Java API. Może to być niezwykle przydatne, gdy trzeba dostosować wykresy do prezentacji i uczynić je bardziej atrakcyjnymi wizualnie lub dostosowanymi do konkretnych potrzeb.

## Najczęściej zadawane pytania

### W jaki sposób mogę dodatkowo dostosować wygląd elementów wykresu?

Można dostosować różne właściwości elementów wykresu, takie jak kolor linii, kolor wypełnienia, styl znacznika i inne, uzyskując dostęp do odpowiednich właściwości serii wykresu, znaczników, etykiet i formatu.

### Czy mogę ukryć konkretne punkty danych na wykresie?

Tak, możesz ukryć określone punkty danych, manipulując danymi w serii wykresu. Możesz usunąć punkty danych lub ustawić ich wartości na null, aby je ukryć.

### Jak mogę dodać dodatkowe serie do wykresu?

Możesz dodać więcej serii do wykresu, używając `IChartData.getSeries().add` metodę i określenie punktów danych dla nowej serii.

### Czy można dynamicznie zmieniać typ wykresu?

Tak, możesz dynamicznie zmienić typ wykresu, tworząc nowy wykres o żądanym typie i kopiując dane ze starego wykresu do nowego.

### Jak mogę programowo zmienić tytuł wykresu i etykiety osi?

Tytuł i etykiety wykresu oraz osi można ustawić, uzyskując dostęp do ich odpowiednich właściwości i ustawiając żądany tekst oraz formatowanie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}