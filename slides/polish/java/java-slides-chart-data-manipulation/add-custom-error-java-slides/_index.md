---
title: Dodaj niestandardowy błąd w slajdach Java
linktitle: Dodaj niestandardowy błąd w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać niestandardowe słupki błędów do wykresów programu PowerPoint w aplikacji Java Slides za pomocą Aspose.Slides. Przewodnik krok po kroku z kodem źródłowym umożliwiający precyzyjną wizualizację danych.
weight: 11
url: /pl/java/chart-data-manipulation/add-custom-error-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do dodawania niestandardowych słupków błędów w slajdach Java przy użyciu Aspose.Slides

W tym samouczku dowiesz się, jak dodawać niestandardowe słupki błędów do wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Słupki błędów są przydatne do wyświetlania zmienności lub niepewności punktów danych na wykresie.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Biblioteka Aspose.Slides dla Java zainstalowana i skonfigurowana w Twoim projekcie.
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

Następnie do prezentacji dodamy wykres bąbelkowy.

```java
// Tworzenie wykresu bąbelkowego
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Krok 3: Dodaj niestandardowe słupki błędów

Dodajmy teraz niestandardowe słupki błędów do serii wykresów.

```java
// Dodawanie niestandardowych słupków błędów i ustawianie ich formatu
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Krok 4: Ustaw dane słupków błędów

W tym kroku uzyskamy dostęp do punktów danych serii wykresów i ustawimy niestandardowe wartości słupków błędów dla każdego punktu.

```java
// Dostęp do punktów danych serii wykresów i ustawianie wartości słupków błędów dla poszczególnych punktów
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

Na koniec zapisz prezentację z niestandardowymi słupkami błędów.

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Otóż to! Pomyślnie dodałeś niestandardowe słupki błędów do wykresu w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy dotyczący dodawania niestandardowego błędu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie pustej prezentacji
Presentation presentation = new Presentation();
try
{
	// Tworzenie wykresu bąbelkowego
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Dodawanie niestandardowych słupków błędów i ustawianie ich formatu
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Dostęp do punktów danych serii wykresów i ustawianie wartości słupków błędów dla poszczególnych punktów
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

W tym obszernym samouczku nauczyłeś się, jak ulepszyć swoje prezentacje PowerPoint, dodając niestandardowe słupki błędów do wykresów za pomocą Aspose.Slides dla Java. Słupki błędów dostarczają cennych informacji na temat zmienności i niepewności danych, dzięki czemu wykresy zawierają więcej informacji i są atrakcyjne wizualnie.

## Często zadawane pytania

### Jak dostosować wygląd słupków błędów?

 Można dostosować wygląd słupków błędów, modyfikując właściwości pliku`IErrorBarsFormat` obiektu, takie jak styl linii, kolor linii i szerokość paska błędów.

### Czy mogę dodać słupki błędów do innych typów wykresów?

Tak, możesz dodawać słupki błędów do różnych typów wykresów obsługiwanych przez Aspose.Slides dla Java, w tym wykresów słupkowych, wykresów liniowych i wykresów punktowych.

### Jak ustawić różne wartości słupków błędów dla każdego punktu danych?

Możesz przechodzić przez punkty danych i ustawiać niestandardowe wartości słupków błędów dla każdego punktu, jak pokazano w powyższym kodzie.

### Czy można ukryć słupki błędów dla określonych punktów danych?

 Tak, możesz kontrolować widoczność słupków błędów dla poszczególnych punktów danych, ustawiając opcję`setVisible` własność`IErrorBarsFormat` obiekt.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
