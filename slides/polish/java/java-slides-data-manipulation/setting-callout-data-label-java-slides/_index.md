---
title: Ustawianie objaśnienia etykiety danych w slajdach Java
linktitle: Ustawianie objaśnienia etykiety danych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak skonfigurować objaśnienia dla etykiet danych w Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym.
weight: 25
url: /pl/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do ustawiania objaśnień dla etykiety danych w Aspose.Slides dla Java

tym samouczku pokażemy, jak skonfigurować objaśnienia etykiet danych na wykresie za pomocą Aspose.Slides dla Java. Objaśnienia mogą być przydatne do wyróżniania określonych punktów danych na wykresie. Przejdziemy przez kod krok po kroku i udostępnimy niezbędny kod źródłowy.

## Warunki wstępne

- Powinieneś mieć zainstalowany Aspose.Slides dla Java.
- Utwórz projekt Java i dodaj do niego bibliotekę Aspose.Slides.

## Krok 1: Utwórz prezentację i dodaj wykres

 Najpierw musimy stworzyć prezentację i dodać wykres do slajdu. Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 2: Skonfiguruj wykres

Następnie skonfigurujemy wykres, ustawiając właściwości, takie jak legenda, seria i kategorie.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Skonfiguruj serie i kategorie (Możesz dostosować liczbę serii i kategorii)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Dodaj tutaj punkty danych
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Krok 3: Dostosuj etykiety danych

Teraz dostosujemy etykiety danych, w tym skonfigurujemy objaśnienia dla ostatniej serii.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Dostosuj formatowanie punktów danych (wypełnienie, linia itp.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Dostosuj formatowanie etykiet (czcionka, wypełnienie itp.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Włącz objaśnienia
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację ze skonfigurowanym wykresem.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Teraz pomyślnie skonfigurowałeś objaśnienia etykiet danych na wykresie za pomocą Aspose.Slides for Java. Dostosuj kod zgodnie ze swoimi konkretnymi wymaganiami dotyczącymi wykresów i danych.

## Kompletny kod źródłowy do ustawiania objaśnień dla etykiety danych w slajdach Java

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku omówiliśmy, jak skonfigurować objaśnienia etykiet danych na wykresie za pomocą Aspose.Slides dla Java. Objaśnienia to cenne narzędzia służące do podkreślania określonych punktów danych na wykresach i prezentacjach. Udostępniliśmy przewodnik krok po kroku wraz z kodem źródłowym, który pomoże Ci w osiągnięciu tego dostosowania.

## Często zadawane pytania

### Jak dostosować wygląd etykiet danych?

Aby dostosować wygląd etykiet danych, możesz modyfikować właściwości, takie jak czcionka, wypełnienie i style linii. Na przykład:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Jak włączyć lub wyłączyć objaśnienia etykiet danych?

 Aby włączyć lub wyłączyć objaśnienia etykiet danych, użyj opcji`setShowLabelAsDataCallout` metoda. Ustaw to na`true` aby włączyć objaśnienia i`false`aby je wyłączyć.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Włącz objaśnienia
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Wyłącz objaśnienia
```

### Czy mogę dostosować linie odniesienia dla etykiet danych?

Tak, możesz dostosować linie odniesienia dla etykiet danych, korzystając z takich właściwości, jak styl linii, kolor i szerokość. Na przykład:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Włącz linie odniesienia
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Oto kilka typowych opcji dostosowywania etykiet danych i objaśnień w Aspose.Slides dla Java. Możesz dodatkowo dostosować wygląd do swoich konkretnych potrzeb.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
