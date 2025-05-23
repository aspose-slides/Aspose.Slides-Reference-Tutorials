---
"description": "Naucz się dodawać wywołania pierścieniowe w slajdach Java przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym dla ulepszonych prezentacji."
"linktitle": "Dodaj wywołanie pierścieniowe w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj wywołanie pierścieniowe w slajdach Java"
"url": "/pl/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj wywołanie pierścieniowe w slajdach Java


## Wprowadzenie do dodawania wywołania pierścieniowego w slajdach Java przy użyciu Aspose.Slides dla Java

W tym samouczku przeprowadzimy Cię przez proces dodawania Doughnut Callout do slajdu w Javie przy użyciu Aspose.Slides for Java. Doughnut Callout to element wykresu, który może być używany do wyróżniania określonych punktów danych na wykresie Doughnut. Dla Twojej wygody udostępnimy Ci instrukcje krok po kroku i kompletny kod źródłowy.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Środowisko programistyczne Java
2. Biblioteka Aspose.Slides dla Java
3. Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA
4. Prezentacja programu PowerPoint, do której chcesz dodać wyróżnienie w kształcie pączka

## Krok 1: Skonfiguruj swój projekt Java

1. Utwórz nowy projekt Java w wybranym środowisku IDE.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu jako zależność.

## Krok 2: Zainicjuj prezentację

Aby zacząć, musisz zainicjować prezentację PowerPoint i utworzyć slajd, na którym chcesz dodać Doughnut Callout. Oto kod, który to umożliwia:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Pamiętaj o wymianie `"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji PowerPoint.

## Krok 3: Utwórz wykres pierścieniowy

Następnie utworzysz wykres pierścieniowy na slajdzie. Możesz dostosować położenie i rozmiar wykresu zgodnie ze swoimi wymaganiami. Oto kod do dodania wykresu pierścieniowego:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 4: Dostosuj wykres pierścieniowy

Teraz czas dostosować wykres pierścieniowy. Ustawimy różne właściwości, takie jak usuwanie legendy, konfigurowanie rozmiaru otworu i dostosowywanie pierwszego kąta wycinka. Oto kod:

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

Ten fragment kodu ustawia właściwości dla wykresu pierścieniowego. Możesz dostosować wartości, aby spełnić swoje konkretne potrzeby.

## Krok 5: Dodaj dane do wykresu pierścieniowego

Teraz dodajmy dane do wykresu pierścieniowego. Dostosujemy również wygląd punktów danych. Oto kod, który to umożliwia:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Tutaj możesz dostosować wygląd punktu danych
        i++;
    }
    categoryIndex++;
}
```

W tym kodzie dodajemy kategorie i punkty danych do wykresu pierścieniowego. Możesz dalej dostosowywać wygląd punktów danych według potrzeb.

## Krok 6: Zapisz prezentację

Na koniec nie zapomnij zapisać prezentacji po dodaniu Doughnut Callout. Oto kod do zapisania prezentacji:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Pamiętaj o wymianie `"chart.pptx"` z wybraną przez Ciebie nazwą pliku.

Gratulacje! Udało Ci się dodać Doughnut Callout do slajdu Java przy użyciu Aspose.Slides for Java. Teraz możesz uruchomić aplikację Java, aby wygenerować prezentację PowerPoint z wykresem Doughnut i Callout.

## Kompletny kod źródłowy dla funkcji Dodaj wywołanie pierścieniowe w slajdach Java

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

W tym samouczku omówiliśmy proces dodawania Doughnut Callout do slajdu Java przy użyciu Aspose.Slides for Java. Nauczyłeś się, jak utworzyć wykres Doughnut, dostosować jego wygląd i dodać punkty danych. Możesz dalej ulepszać swoje prezentacje za pomocą tej potężnej biblioteki i odkrywać więcej opcji wykresów.

## Najczęściej zadawane pytania

### Jak mogę zmienić wygląd symbolu pierścienia?

Możesz dostosować wygląd Doughnut Callout, modyfikując właściwości punktów danych na wykresie. W podanym kodzie możesz zobaczyć, jak ustawić kolor wypełnienia, kolor linii, styl czcionki i inne atrybuty punktów danych.

### Czy mogę dodać więcej punktów danych do wykresu pierścieniowego?

Tak, możesz dodać tyle punktów danych, ile potrzebujesz do wykresu pierścieniowego. Po prostu rozszerz pętle w kodzie, w których dodawane są kategorie i punkty danych, i podaj odpowiednie dane i formatowanie.

### Jak mogę dostosować położenie i rozmiar wykresu pierścieniowego na slajdzie?

Możesz zmienić położenie i rozmiar wykresu pierścieniowego, modyfikując parametry w `addChart` metoda. Cztery liczby w tej metodzie odpowiadają współrzędnym X i Y lewego górnego rogu wykresu oraz jego szerokości i wysokości.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}