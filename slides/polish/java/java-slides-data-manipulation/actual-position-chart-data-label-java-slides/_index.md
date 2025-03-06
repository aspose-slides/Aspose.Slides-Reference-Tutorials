---
title: Uzyskaj rzeczywistą pozycję etykiety danych wykresu w slajdach Java
linktitle: Uzyskaj rzeczywistą pozycję etykiety danych wykresu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak uzyskać rzeczywistą pozycję etykiet danych wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym.
weight: 18
url: /pl/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uzyskaj rzeczywistą pozycję etykiety danych wykresu w slajdach Java


## Wprowadzenie do uzyskiwania rzeczywistej pozycji etykiety danych wykresu w slajdach Java

W tym samouczku dowiesz się, jak pobrać rzeczywistą pozycję etykiet danych wykresu za pomocą Aspose.Slides dla Java. Stworzymy program w języku Java, który wygeneruje prezentację PowerPoint z wykresem, dostosuje etykiety danych, a następnie doda kształty reprezentujące pozycje tych etykiet danych.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że w projekcie Java masz skonfigurowaną bibliotekę Aspose.Slides for Java.

## Krok 1: Utwórz prezentację programu PowerPoint

Najpierw utwórzmy nową prezentację PowerPoint i dodajmy do niej wykres. W dalszej części samouczka dostosujemy etykiety danych wykresu.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 2: Dostosuj etykiety danych
Teraz dostosujmy etykiety danych dla serii wykresów. Ustalimy ich położenie i pokażemy wartości.

```java
try {
    // ... (poprzedni kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (pozostał kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 3: Uzyskaj rzeczywistą pozycję etykiet danych
tym kroku będziemy iterować po punktach danych serii wykresów i pobierać rzeczywistą pozycję etykiet danych, które mają wartość większą niż 4. Następnie dodamy elipsy, aby przedstawić te pozycje.

```java
try {
    // ... (poprzedni kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (pozostał kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 4: Zapisz prezentację
Na koniec zapisz wygenerowaną prezentację do pliku.

```java
try {
    // ... (poprzedni kod)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kompletny kod źródłowy funkcji Uzyskaj rzeczywistą pozycję etykiety danych wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//DO ZROBIENIA
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się pobierać rzeczywistą pozycję etykiet danych wykresu w Java Slides za pomocą Aspose.Slides for Java. Możesz teraz wykorzystać tę wiedzę, aby ulepszyć swoje prezentacje programu PowerPoint za pomocą niestandardowych etykiet danych i wizualnych reprezentacji ich pozycji.

## Często zadawane pytania

### Jak dostosować etykiety danych na wykresie?

 Aby dostosować etykiety danych na wykresie, możesz użyć opcji`setDefaultDataLabelFormat` metodę na serii wykresów i ustaw właściwości, takie jak pozycja i widoczność. Na przykład:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Jak mogę dodać kształty reprezentujące pozycje etykiet danych?

 Można iterować po punktach danych serii wykresów i używać metody`getActualX`, `getActualY`, `getActualWidth` , I`getActualHeight`metody etykiety danych, aby uzyskać jej pozycję. Następnie możesz dodawać kształty za pomocą`addAutoShape` metoda. Oto przykład:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Jak zapisać wygenerowaną prezentację?

 Wygenerowaną prezentację możesz zapisać za pomocą pliku`save` metoda. Podaj żądaną ścieżkę pliku i plik`SaveFormat` jako parametry. Na przykład:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
