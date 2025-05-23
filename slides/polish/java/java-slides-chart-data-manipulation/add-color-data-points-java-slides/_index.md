---
"description": "Dowiedz się, jak dodawać kolor do punktów danych w slajdach Java przy użyciu Aspose.Slides for Java."
"linktitle": "Dodawanie koloru do punktów danych w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodawanie koloru do punktów danych w slajdach Java"
"url": "/pl/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie koloru do punktów danych w slajdach Java


## Wprowadzenie do dodawania koloru do punktów danych w slajdach Java

W tym samouczku pokażemy, jak dodać kolor do punktów danych w slajdach Java przy użyciu Aspose.Slides for Java. Ten przewodnik krok po kroku zawiera przykłady kodu źródłowego, które pomogą Ci wykonać to zadanie.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Biblioteka Aspose.Slides dla Java

## Krok 1: Utwórz nową prezentację

Najpierw utworzymy nową prezentację przy użyciu Aspose.Slides dla Java. Ta prezentacja będzie służyć jako kontener dla naszego wykresu.

```java
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres słoneczny

Teraz dodajmy wykres Sunburst do prezentacji. Określamy typ wykresu, pozycję i rozmiar.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Krok 3: Dostęp do punktów danych

Aby zmodyfikować punkty danych na wykresie, musimy uzyskać dostęp do `IChartDataPointCollection` obiekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Krok 4: Dostosuj punkty danych

W tym kroku dostosujemy określone punkty danych. Tutaj zmieniamy kolor punktów danych i konfigurujemy ustawienia etykiet.

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

To wszystko! Udało Ci się dodać kolor do określonych punktów danych w slajdzie Java przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy do dodawania koloru do punktów danych w slajdach Java

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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//Do zrobienia
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku dowiedziałeś się, jak dodawać kolor do punktów danych w slajdach Java przy użyciu Aspose.Slides for Java. Możesz dalej dostosowywać wykresy i prezentacje na podstawie swoich konkretnych wymagań.

## Najczęściej zadawane pytania

### Jak mogę zmienić kolor innych punktów danych?

Aby zmienić kolor innych punktów danych, możesz zastosować podejście podobne do przedstawionego w kroku 4. Uzyskaj dostęp do punktu danych, który chcesz dostosować, i zmień ustawienia jego koloru i etykiety.

### Czy mogę dostosować inne aspekty wykresu?

Tak, możesz dostosować różne aspekty wykresu, w tym czcionki, etykiety, tytuły i inne. Zapoznaj się z [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) aby zobaczyć szczegółowe opcje personalizacji.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?

Więcej przykładów i szczegółową dokumentację dotyczącą korzystania z Aspose.Slides dla języka Java można znaleźć na stronie [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) strona internetowa.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}