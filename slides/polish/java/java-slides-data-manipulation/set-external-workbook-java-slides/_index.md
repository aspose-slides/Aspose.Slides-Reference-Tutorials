---
"description": "Dowiedz się, jak ustawić zewnętrzne skoroszyty w Java Slides przy użyciu Aspose.Slides for Java. Twórz dynamiczne prezentacje z integracją danych Excel."
"linktitle": "Ustaw zewnętrzny skoroszyt w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw zewnętrzny skoroszyt w slajdach Java"
"url": "/pl/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw zewnętrzny skoroszyt w slajdach Java


## Wprowadzenie do ustawiania zewnętrznego skoroszytu w slajdach Java

tym samouczku pokażemy, jak ustawić zewnętrzny skoroszyt w Java Slides przy użyciu Aspose.Slides. Dowiesz się, jak utworzyć prezentację PowerPoint z wykresem, który odwołuje się do danych z zewnętrznego skoroszytu Excel. Pod koniec tego przewodnika będziesz mieć jasne zrozumienie, jak zintegrować dane zewnętrzne z prezentacjami Java Slides.

## Wymagania wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełnione są następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została dodana do projektu.
- Skoroszyt programu Excel zawierający dane, do których chcesz odwołać się w prezentacji.

## Krok 1: Utwórz nową prezentację

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Zacznijmy od utworzenia nowej prezentacji PowerPoint za pomocą Aspose.Slides.

## Krok 2: Dodaj wykres

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Następnie wstawiamy wykres kołowy do prezentacji. Możesz dostosować typ wykresu i jego położenie według potrzeb.

## Krok 3: Dostęp do skoroszytu zewnętrznego

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Aby uzyskać dostęp do skoroszytu zewnętrznego, używamy `setExternalWorkbook` metodę i podaj ścieżkę do skoroszytu programu Excel zawierającego dane.

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

Na koniec zapisujemy prezentację z odniesieniem do skoroszytu zewnętrznego jako plik programu PowerPoint.

## Kompletny kod źródłowy dla zestawu zewnętrznych skoroszytów w slajdach Java

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

W tym samouczku nauczyliśmy się, jak ustawić zewnętrzny skoroszyt w Java Slides przy użyciu Aspose.Slides. Teraz możesz tworzyć prezentacje, które dynamicznie odwołują się do danych z skoroszytów programu Excel, zwiększając elastyczność i interaktywność slajdów.

## Najczęściej zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Aspose.Slides for Java można zainstalować, dodając bibliotekę do projektu Java. Możesz pobrać bibliotekę ze strony internetowej Aspose i postępować zgodnie z instrukcjami instalacji podanymi w dokumentacji.

### Czy mogę używać różnych typów wykresów w skoroszytach zewnętrznych?

Tak, możesz używać różnych typów wykresów obsługiwanych przez Aspose.Slides i wiązać je z danymi z zewnętrznych skoroszytów. Proces może się nieznacznie różnić w zależności od wybranego typu wykresu.

### Co się stanie, jeśli struktura danych mojego zewnętrznego skoroszytu ulegnie zmianie?

Jeśli struktura danych zewnętrznego skoroszytu ulegnie zmianie, może zaistnieć konieczność zaktualizowania odwołań do komórek w kodzie Java, aby mieć pewność, że dane wykresu pozostaną dokładne.

### Czy Aspose.Slides jest kompatybilny z najnowszymi wersjami Java?

Aspose.Slides for Java jest regularnie aktualizowany, aby zapewnić zgodność z najnowszymi wersjami Java. Pamiętaj, aby sprawdzać aktualizacje i używać najnowszej wersji biblioteki, aby uzyskać optymalną wydajność i zgodność.

### Czy mogę dodać wiele wykresów odwołujących się do tego samego skoroszytu zewnętrznego?

Tak, możesz dodać wiele wykresów do swojej prezentacji, wszystkie odwołujące się do tego samego zewnętrznego skoroszytu. Po prostu powtórz kroki opisane w tym samouczku dla każdego wykresu, który chcesz utworzyć.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}