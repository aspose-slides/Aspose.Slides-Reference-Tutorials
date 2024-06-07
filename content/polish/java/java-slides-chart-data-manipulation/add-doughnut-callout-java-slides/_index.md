---
title: Dodaj objaśnienie pączka w slajdach Java
linktitle: Dodaj objaśnienie pączka w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać objaśnienia pączków w slajdach Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym dla ulepszonych prezentacji.
type: docs
weight: 12
url: /pl/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Wprowadzenie do dodawania objaśnienia pączka w slajdach Java przy użyciu Aspose.Slides dla Java

W tym samouczku przeprowadzimy Cię przez proces dodawania objaśnienia Donut do slajdu w Javie przy użyciu Aspose.Slides dla Java. Objaśnienie pierścieniowe to element wykresu, którego można użyć do wyróżnienia określonych punktów danych na wykresie pierścieniowym. Dla Twojej wygody udostępnimy instrukcje krok po kroku i pełny kod źródłowy.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Środowisko programistyczne Java
2. Aspose.Slides dla biblioteki Java
3. Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA
4. Prezentacja programu PowerPoint, do której chcesz dodać objaśnienie pączka

## Krok 1: Skonfiguruj swój projekt Java

1. Utwórz nowy projekt Java w wybranym IDE.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu jako zależność.

## Krok 2: Zainicjuj prezentację

Aby rozpocząć, musisz zainicjować prezentację programu PowerPoint i utworzyć slajd, na którym chcesz dodać objaśnienie pączka. Oto kod, aby to osiągnąć:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji programu PowerPoint.

## Krok 3: Utwórz wykres pierścieniowy

Następnie utworzysz na slajdzie wykres pierścieniowy. Możesz dostosować położenie i rozmiar wykresu zgodnie ze swoimi wymaganiami. Oto kod umożliwiający dodanie wykresu pierścieniowego:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 4: Dostosuj wykres pierścieniowy

Teraz nadszedł czas, aby dostosować wykres pierścieniowy. Ustawimy różne właściwości, takie jak usunięcie legendy, skonfigurowanie rozmiaru otworu i dostosowanie kąta pierwszego przekroju. Oto kod:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Ten fragment kodu ustawia właściwości wykresu pierścieniowego. Możesz dostosować wartości do swoich konkretnych potrzeb.

## Krok 5: Dodaj dane do wykresu pierścieniowego

Dodajmy teraz dane do wykresu pierścieniowego. Dostosujemy także wygląd punktów danych. Oto kod, aby to osiągnąć:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Dostosuj tutaj wygląd punktu danych
        i++;
    }
    categoryIndex++;
}
```

W tym kodzie dodajemy kategorie i punkty danych do wykresu pierścieniowego. W razie potrzeby możesz dodatkowo dostosować wygląd punktów danych.

## Krok 6: Zapisz prezentację

Na koniec nie zapomnij zapisać prezentacji po dodaniu objaśnienia pączka. Oto kod umożliwiający zapisanie prezentacji:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Pamiętaj o wymianie`"chart.pptx"` z żądaną nazwą pliku.

Gratulacje! Pomyślnie dodałeś objaśnienie pączka do slajdu Java przy użyciu Aspose.Slides for Java. Możesz teraz uruchomić aplikację Java, aby wygenerować prezentację programu PowerPoint z wykresem pierścieniowym i objaśnieniem.

## Kompletny kod źródłowy dla dodawania objaśnienia pączka w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Wniosek

tym samouczku omówiliśmy proces dodawania objaśnienia Donut do slajdu Java za pomocą Aspose.Slides dla Java. Wiesz już, jak utworzyć wykres pierścieniowy, dostosować jego wygląd i dodać punkty danych. Możesz dalej ulepszać swoje prezentacje dzięki tej potężnej bibliotece i odkrywać więcej opcji wykresów.

## Często zadawane pytania

### Jak mogę zmienić wygląd objaśnienia pączka?

Możesz dostosować wygląd objaśnienia pierścieniowego, modyfikując właściwości punktów danych na wykresie. W dostarczonym kodzie można zobaczyć, jak ustawić kolor wypełnienia, kolor linii, styl czcionki i inne atrybuty punktów danych.

### Czy mogę dodać więcej punktów danych do wykresu pierścieniowego?

Tak, możesz dodać dowolną liczbę punktów danych do wykresu pierścieniowego. Po prostu rozszerz pętle w kodzie, w których dodawane są kategorie i punkty danych, a następnie podaj odpowiednie dane i formatowanie.

### Jak dostosować położenie i rozmiar wykresu pierścieniowego na slajdzie?

Możesz zmienić położenie i rozmiar wykresu pierścieniowego, modyfikując parametry w pliku`addChart` metoda. Cztery liczby w tej metodzie odpowiadają współrzędnym X i Y lewego górnego rogu wykresu oraz odpowiednio jego szerokości i wysokości.