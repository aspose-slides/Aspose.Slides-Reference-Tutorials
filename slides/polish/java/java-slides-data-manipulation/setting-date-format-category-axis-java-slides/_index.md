---
title: Ustawianie formatu daty dla osi kategorii w slajdach Java
linktitle: Ustawianie formatu daty dla osi kategorii w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić format daty dla osi kategorii na wykresie programu PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym.
weight: 26
url: /pl/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do ustawiania formatu daty dla osi kategorii w slajdach Java

W tym samouczku dowiemy się, jak ustawić format daty dla osi kategorii na wykresie programu PowerPoint za pomocą Aspose.Slides dla Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i zarządzanie prezentacjami programu PowerPoint.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Biblioteka Aspose.Slides for Java (możesz ją pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
2. Skonfigurowano środowisko programistyczne Java.

## Krok 1: Utwórz prezentację programu PowerPoint

Najpierw musimy stworzyć prezentację PowerPoint, do której dodamy wykres. Upewnij się, że zaimportowałeś niezbędne klasy Aspose.Slides.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Teraz dodajmy wykres do slajdu programu PowerPoint. W tym przykładzie użyjemy wykresu warstwowego.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Krok 3: Przygotuj dane wykresu

Skonfigurujemy dane i kategorie wykresu. W tym przykładzie użyjemy kategorii dat.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Dodawanie kategorii dat
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Dodawanie serii danych
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Krok 4: Dostosuj oś kategorii
Teraz dostosujmy oś kategorii, aby wyświetlała daty w określonym formacie (np. rrrr).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Krok 5: Zapisz prezentację
Na koniec zapisz prezentację programu PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Otóż to! Pomyślnie ustawiłeś format daty dla osi kategorii na wykresie programu PowerPoint przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy do ustawiania formatu daty dla osi kategorii w slajdach Java

```java
	// Ścieżka do katalogu dokumentów.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Wniosek

Pomyślnie dostosowałeś format daty dla osi kategorii na wykresie Java Slides przy użyciu Aspose.Slides for Java. Dzięki temu możesz prezentować na wykresach wartości dat w żądanym formacie. Zachęcamy do zapoznania się z dalszymi opcjami dostosowywania w oparciu o konkretne wymagania.

## Często zadawane pytania

### Jak zmienić format daty dla osi kategorii?

 Aby zmienić format daty dla osi kategorii, użyj opcji`setNumberFormat` metodę na osi kategorii i podaj żądany wzorzec formatu daty, taki jak „rrrr-MM-dd” lub „MM/rrrr”. Upewnij się, że ustawiłeś`setNumberFormatLinkedToSource(false)` aby zastąpić domyślny format.

### Czy mogę używać różnych formatów dat dla różnych wykresów w tej samej prezentacji?

Tak, możesz ustawić różne formaty dat dla osi kategorii na różnych wykresach w tej samej prezentacji. W razie potrzeby po prostu dostosuj oś kategorii dla każdego wykresu.

### Jak dodać więcej punktów danych do wykresu?

 Aby dodać więcej punktów danych do wykresu, użyj opcji`getDataPoints().addDataPointForLineSeries`metodę na serii danych i podaj wartości danych.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
