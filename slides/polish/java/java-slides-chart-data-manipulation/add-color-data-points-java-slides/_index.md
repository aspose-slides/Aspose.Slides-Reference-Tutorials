---
title: Dodaj kolor do punktów danych w slajdach Java
linktitle: Dodaj kolor do punktów danych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodać kolor do punktów danych na slajdach Java przy użyciu Aspose.Slides dla Java.
type: docs
weight: 10
url: /pl/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Wprowadzenie do dodawania koloru do punktów danych w slajdach Java

W tym samouczku pokażemy, jak dodać kolor do punktów danych na slajdach Java za pomocą Aspose.Slides for Java. Ten przewodnik krok po kroku zawiera przykłady kodu źródłowego, które pomogą Ci osiągnąć to zadanie.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Aspose.Slides dla biblioteki Java

## Krok 1: Utwórz nową prezentację

Najpierw utworzymy nową prezentację za pomocą Aspose.Slides dla Java. Ta prezentacja będzie służyć jako kontener dla naszego wykresu.

```java
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres Sunburst

Dodajmy teraz do prezentacji wykres Sunburst. Określamy typ wykresu, jego położenie i rozmiar.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Krok 3: Uzyskaj dostęp do punktów danych

 Aby zmodyfikować punkty danych na wykresie, musimy uzyskać dostęp do pliku`IChartDataPointCollection` obiekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Krok 4: Dostosuj punkty danych

Na tym etapie dostosujemy określone punkty danych. Tutaj zmieniamy kolor punktów danych i konfigurujemy ustawienia etykiet.

```java
// Dostosuj punkt danych 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Dostosuj punkt danych 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację z dostosowanym wykresem.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Otóż to! Pomyślnie dodałeś kolor do określonych punktów danych na slajdzie Java przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy umożliwiający dodawanie koloru do punktów danych w slajdach Java

```java
Presentation pres = new Presentation();
try
{
	// Ścieżka do katalogu dokumentów.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//DO ZROBIENIA
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się dodawać kolor do punktów danych na slajdach Java za pomocą Aspose.Slides for Java. Możesz dodatkowo dostosować wykresy i prezentacje do swoich konkretnych wymagań.

## Często zadawane pytania

### Jak mogę zmienić kolor innych punktów danych?

Aby zmienić kolor innych punktów danych, możesz zastosować podobne podejście, jak pokazano w kroku 4. Uzyskaj dostęp do punktu danych, który chcesz dostosować, i zmodyfikuj jego ustawienia koloru i etykiety.

### Czy mogę dostosować inne aspekty wykresu?

 Tak, możesz dostosować różne aspekty wykresu, w tym czcionki, etykiety, tytuły i inne. Patrz[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) szczegółowe opcje dostosowywania.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?

 Więcej przykładów i szczegółową dokumentację dotyczącą korzystania z Aspose.Slides dla Java można znaleźć na stronie[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) strona internetowa.