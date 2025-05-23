---
"description": "Dowiedz się, jak ustawić format daty dla osi kategorii na wykresie programu PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Ustawianie formatu daty dla osi kategorii w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustawianie formatu daty dla osi kategorii w slajdach Java"
"url": "/pl/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie formatu daty dla osi kategorii w slajdach Java


## Wprowadzenie do ustawiania formatu daty dla osi kategorii w slajdach Java

tym samouczku nauczymy się, jak ustawić format daty dla osi kategorii na wykresie programu PowerPoint przy użyciu Aspose.Slides for Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i zarządzanie prezentacjami programu PowerPoint.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

1. Biblioteka Aspose.Slides dla Java (można ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).
2. Konfiguracja środowiska programistycznego Java.

## Krok 1: Utwórz prezentację PowerPoint

Najpierw musimy utworzyć prezentację PowerPoint, do której dodamy wykres. Upewnij się, że zaimportowałeś niezbędne klasy Aspose.Slides.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Teraz dodajmy wykres do slajdu programu PowerPoint. W tym przykładzie użyjemy wykresu obszarowego.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Krok 3: Przygotuj dane wykresu

Skonfigurujemy dane wykresu i kategorie. W tym przykładzie użyjemy kategorii dat.

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
Na koniec zapisz prezentację PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się ustawić format daty dla osi kategorii na wykresie PowerPoint przy użyciu Aspose.Slides dla Java.

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

Udało Ci się dostosować format daty dla osi kategorii na wykresie Java Slides przy użyciu Aspose.Slides for Java. Pozwala to na prezentowanie wartości dat w pożądanym formacie na wykresach. Możesz swobodnie eksplorować dalsze opcje dostosowywania w oparciu o swoje konkretne wymagania.

## Najczęściej zadawane pytania

### Jak zmienić format daty dla osi kategorii?

Aby zmienić format daty dla osi kategorii, użyj `setNumberFormat` metodę na osi kategorii i podaj pożądany wzór formatu daty, taki jak „yyyy-MM-dd” lub „MM/yyyy”. Upewnij się, że ustawiłeś `setNumberFormatLinkedToSource(false)` aby zastąpić format domyślny.

### Czy mogę używać różnych formatów dat dla różnych wykresów w tej samej prezentacji?

Tak, możesz ustawić różne formaty daty dla osi kategorii na różnych wykresach w tej samej prezentacji. Po prostu dostosuj oś kategorii dla każdego wykresu według potrzeb.

### Jak dodać więcej punktów danych do wykresu?

Aby dodać więcej punktów danych do wykresu, użyj `getDataPoints().addDataPointForLineSeries` metodę na szeregu danych i podaj wartości danych.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}