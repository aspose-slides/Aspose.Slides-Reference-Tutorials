---
title: Ukryj informacje z wykresu w slajdach Java
linktitle: Ukryj informacje z wykresu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ukryć elementy wykresu w Java Slides za pomocą Aspose.Slides for Java. Dostosuj prezentacje pod kątem przejrzystości i estetyki, korzystając ze wskazówek krok po kroku i kodu źródłowego.
weight: 13
url: /pl/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ukryj informacje z wykresu w slajdach Java


## Wprowadzenie do ukrywania informacji na wykresie w slajdach Java

W tym samouczku pokażemy, jak ukryć różne elementy wykresu w aplikacji Java Slides za pomocą interfejsu API Aspose.Slides for Java. Możesz użyć tego kodu, aby dostosować wykresy do potrzeb prezentacji.

## Krok 1: Konfigurowanie środowiska

 Zanim zaczniemy, upewnij się, że masz dodaną bibliotekę Aspose.Slides for Java do swojego projektu. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 2: Utwórz nową prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Dodawanie wykresu do slajdu

Do slajdu dodamy wykres liniowy ze znacznikami, a następnie przystąpimy do ukrywania poszczególnych elementów wykresu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Krok 4: Ukryj tytuł wykresu

Tytuł wykresu możesz ukryć w następujący sposób:

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

W razie potrzeby możesz dostosować serię wykresów. W tym przykładzie zmieniamy styl znacznika, położenie etykiety danych, rozmiar znacznika, kolor linii i styl kreski:

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

Otóż to! Pomyślnie ukryłeś różne elementy wykresu w Java Slides przy użyciu Aspose.Slides for Java. Możesz dodatkowo dostosować wykresy i prezentacje do swoich konkretnych wymagań.

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
	//Ukrywanie MajorGridLines
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

W tym przewodniku krok po kroku omówiliśmy, jak ukryć różne elementy wykresu w aplikacji Java Slides za pomocą interfejsu API Aspose.Slides for Java. Może to być niezwykle przydatne, gdy chcesz dostosować wykresy do prezentacji i uczynić je bardziej atrakcyjnymi wizualnie lub dostosowanymi do Twoich konkretnych potrzeb.

## Często zadawane pytania

### Jak jeszcze bardziej dostosować wygląd elementów wykresu?

Możesz dostosować różne właściwości elementów wykresu, takie jak kolor linii, kolor wypełnienia, styl znacznika i inne, uzyskując dostęp do odpowiednich właściwości serii wykresu, znaczników, etykiet i formatu.

### Czy mogę ukryć określone punkty danych na wykresie?

Tak, możesz ukryć określone punkty danych, manipulując danymi w serii wykresów. Możesz usunąć punkty danych lub ustawić ich wartości na null, aby je ukryć.

### Jak dodać kolejne serie do wykresu?

 Możesz dodać więcej serii do wykresu, korzystając z opcji`IChartData.getSeries().add` metody i określenie punktów danych dla nowej serii.

### Czy można dynamicznie zmieniać typ wykresu?

Tak, możesz dynamicznie zmieniać typ wykresu, tworząc nowy wykres żądanego typu i kopiując dane ze starego wykresu do nowego.

### Jak mogę programowo zmienić tytuł i etykiety osi wykresu?

Możesz ustawić tytuł i etykiety wykresu i osi, uzyskując dostęp do ich odpowiednich właściwości i ustawiając żądany tekst i formatowanie.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
