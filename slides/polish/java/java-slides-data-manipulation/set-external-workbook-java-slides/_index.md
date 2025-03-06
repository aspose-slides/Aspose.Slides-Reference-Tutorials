---
title: Ustaw skoroszyt zewnętrzny w slajdach Java
linktitle: Ustaw skoroszyt zewnętrzny w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić zewnętrzne skoroszyty w Java Slides przy użyciu Aspose.Slides dla Java. Twórz dynamiczne prezentacje dzięki integracji danych Excel.
type: docs
weight: 19
url: /pl/java/data-manipulation/set-external-workbook-java-slides/
---

## Wprowadzenie do ustawiania skoroszytu zewnętrznego w slajdach Java

tym samouczku przyjrzymy się, jak ustawić zewnętrzny skoroszyt w Java Slides za pomocą Aspose.Slides. Dowiesz się jak stworzyć prezentację PowerPoint zawierającą wykres odwołujący się do danych z zewnętrznego skoroszytu Excela. Po przeczytaniu tego przewodnika będziesz już jasno wiedział, jak integrować dane zewnętrzne z prezentacjami Java Slides.

## Warunki wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełniasz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Do Twojego projektu dodano bibliotekę Aspose.Slides for Java.
- Skoroszyt programu Excel zawierający dane, do których chcesz się odwołać w prezentacji.

## Krok 1: Utwórz nową prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Zaczynamy od stworzenia nowej prezentacji PowerPoint przy użyciu Aspose.Slides.

## Krok 2: Dodaj wykres

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Następnie wstawiamy do prezentacji wykres kołowy. W razie potrzeby możesz dostosować typ i położenie wykresu.

## Krok 3: Uzyskaj dostęp do zewnętrznego skoroszytu

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Aby uzyskać dostęp do zewnętrznego skoroszytu, używamy metody`setExternalWorkbook` metodę i podaj ścieżkę do skoroszytu programu Excel zawierającego dane.

## Krok 4: Powiąż dane wykresu

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Łączymy wykres z danymi z zewnętrznego skoroszytu, określając odwołania do komórek dla serii i kategorii.

## Krok 5: Zapisz prezentację

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację z odnośnikiem do zewnętrznego skoroszytu jako plik programu PowerPoint.

## Kompletny kod źródłowy zestawu zewnętrznego skoroszytu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak ustawić zewnętrzny skoroszyt w Java Slides za pomocą Aspose.Slides. Możesz teraz tworzyć prezentacje, które dynamicznie odwołują się do danych ze skoroszytów programu Excel, zwiększając elastyczność i interaktywność slajdów.

## Często zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Aspose.Slides for Java można zainstalować, dodając bibliotekę do projektu Java. Możesz pobrać bibliotekę ze strony Aspose i postępować zgodnie z instrukcjami instalacji podanymi w dokumentacji.

### Czy mogę używać różnych typów wykresów w zewnętrznych skoroszytach?

Tak, możesz używać różnych typów wykresów obsługiwanych przez Aspose.Slides i wiązać je z danymi z zewnętrznych skoroszytów. Proces może się nieznacznie różnić w zależności od wybranego typu wykresu.

### Co się stanie, jeśli zmieni się struktura danych mojego zewnętrznego skoroszytu?

Jeśli struktura danych zewnętrznego skoroszytu ulegnie zmianie, może zaistnieć potrzeba zaktualizowania odwołań do komórek w kodzie Java, aby zapewnić dokładność danych wykresu.

### Czy Aspose.Slides jest kompatybilny z najnowszymi wersjami Java?

Aspose.Slides dla Java jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami Java. Pamiętaj, aby sprawdzić dostępność aktualizacji i skorzystać z najnowszej wersji biblioteki, aby uzyskać optymalną wydajność i kompatybilność.

### Czy mogę dodać wiele wykresów odwołujących się do tego samego zewnętrznego skoroszytu?

Tak, możesz dodać do prezentacji wiele wykresów, a wszystkie odwołują się do tego samego zewnętrznego skoroszytu. Po prostu powtórz kroki opisane w tym samouczku dla każdego wykresu, który chcesz utworzyć.