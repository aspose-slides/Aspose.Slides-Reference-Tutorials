---
"description": "Dowiedz się, jak dodawać niestandardowe paski błędów do wykresów PowerPoint w Java Slides przy użyciu Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym do precyzyjnej wizualizacji danych."
"linktitle": "Dodaj niestandardowy błąd w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj niestandardowy błąd w slajdach Java"
"url": "/pl/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj niestandardowy błąd w slajdach Java


## Wprowadzenie do dodawania niestandardowych pasków błędów w slajdach Java przy użyciu Aspose.Slides

W tym samouczku dowiesz się, jak dodawać niestandardowe paski błędów do wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Paski błędów są przydatne do wyświetlania zmienności lub niepewności w punktach danych na wykresie.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Biblioteka Aspose.Slides for Java została zainstalowana i skonfigurowana w projekcie.
- Skonfigurowano środowisko programistyczne Java.

## Krok 1: Utwórz pustą prezentację

Najpierw utwórz pustą prezentację programu PowerPoint.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres bąbelkowy

Następnie dodamy do prezentacji wykres bąbelkowy.

```java
// Tworzenie wykresu bąbelkowego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Krok 3: Dodaj niestandardowe paski błędów

Teraz dodajmy niestandardowe słupki błędów do serii wykresów.

```java
// Dodawanie niestandardowych pasków błędów i ustawianie ich formatu
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Krok 4: Ustaw dane słupków błędów

tym kroku uzyskamy dostęp do punktów danych serii wykresów i ustawimy niestandardowe wartości słupków błędów dla każdego punktu.

```java
// Uzyskiwanie dostępu do punktów danych serii wykresów i ustawianie wartości słupków błędów dla poszczególnych punktów
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Ustawianie słupków błędów dla punktów serii wykresów
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację z niestandardowymi paskami błędów.

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się dodać niestandardowe paski błędów do wykresu w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java.

## Kompletny kod źródłowy do dodawania niestandardowego błędu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
try
{
	// Tworzenie wykresu bąbelkowego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Dodawanie niestandardowych pasków błędów i ustawianie ich formatu
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Uzyskiwanie dostępu do punktów danych serii wykresów i ustawianie wartości słupków błędów dla poszczególnych punktów
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Ustawianie słupków błędów dla punktów serii wykresów
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Zapisywanie prezentacji
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

tym kompleksowym samouczku dowiedziałeś się, jak ulepszyć swoje prezentacje PowerPoint, dodając niestandardowe paski błędów do wykresów za pomocą Aspose.Slides dla Java. Paski błędów dostarczają cennych informacji na temat zmienności i niepewności danych, dzięki czemu wykresy są bardziej informacyjne i atrakcyjne wizualnie.

## Najczęściej zadawane pytania

### Jak dostosować wygląd pasków błędów?

Możesz dostosować wygląd pasków błędów, modyfikując właściwości `IErrorBarsFormat` obiekt, taki jak styl linii, kolor linii i szerokość paska błędu.

### Czy mogę dodać słupki błędów do innych typów wykresów?

Tak, możesz dodawać słupki błędów do różnych typów wykresów obsługiwanych przez Aspose.Slides dla Java, w tym wykresów słupkowych, liniowych i punktowych.

### Jak ustawić różne wartości słupków błędów dla każdego punktu danych?

Można przechodzić przez punkty danych i ustawiać niestandardowe wartości słupków błędów dla każdego punktu, jak pokazano w kodzie powyżej.

### Czy można ukryć paski błędów dla określonych punktów danych?

Tak, możesz kontrolować widoczność pasków błędów dla poszczególnych punktów danych, ustawiając `setVisible` własność `IErrorBarsFormat` obiekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}