---
"description": "Dowiedz się, jak uzyskać rzeczywistą pozycję etykiet danych wykresu w Java Slides przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Pobierz rzeczywistą pozycję etykiety danych wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Pobierz rzeczywistą pozycję etykiety danych wykresu w slajdach Java"
"url": "/pl/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz rzeczywistą pozycję etykiety danych wykresu w slajdach Java


## Wprowadzenie do pobierania rzeczywistej pozycji etykiety danych wykresu w slajdach Java

tym samouczku dowiesz się, jak pobrać rzeczywistą pozycję etykiet danych wykresu za pomocą Aspose.Slides dla Java. Utworzymy program Java, który generuje prezentację PowerPoint z wykresem, dostosowuje etykiety danych, a następnie dodaje kształty reprezentujące pozycje tych etykiet danych.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest skonfigurowana w projekcie Java.

## Krok 1: Utwórz prezentację PowerPoint

Najpierw utwórzmy nową prezentację PowerPoint i dodajmy do niej wykres. Później w tym samouczku dostosujemy etykiety danych wykresu.

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
Teraz dostosujmy etykiety danych dla serii wykresów. Ustawimy ich pozycję i pokażemy wartości.

```java
try {
    // ... (poprzedni kod)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (pozostały kod)
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 3: Uzyskaj rzeczywistą pozycję etykiet danych
tym kroku przejdziemy przez punkty danych serii wykresów i pobierzemy rzeczywistą pozycję etykiet danych, które mają wartość większą niż 4. Następnie dodamy elipsy, aby reprezentować te pozycje.

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
    // ... (pozostały kod)
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

## Kompletny kod źródłowy do pobrania rzeczywistej pozycji etykiety danych wykresu w slajdach Java

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//Do zrobienia
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

W tym samouczku nauczyłeś się, jak pobrać rzeczywistą pozycję etykiet danych wykresu w Java Slides przy użyciu Aspose.Slides for Java. Teraz możesz wykorzystać tę wiedzę, aby ulepszyć swoje prezentacje PowerPoint za pomocą niestandardowych etykiet danych i wizualnych reprezentacji ich pozycji.

## Najczęściej zadawane pytania

### Jak mogę dostosować etykiety danych na wykresie?

Aby dostosować etykiety danych na wykresie, możesz użyć `setDefaultDataLabelFormat` metoda na serii wykresów i ustaw właściwości, takie jak pozycja i widoczność. Na przykład:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Jak mogę dodać kształty reprezentujące pozycje etykiet danych?

Możesz iterować punkty danych serii wykresów i używać `getActualX`, `getActualY`, `getActualWidth`, I `getActualHeight` metody etykiety danych, aby uzyskać jej pozycję. Następnie możesz dodać kształty za pomocą `addAutoShape` metoda. Oto przykład:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Jak mogę zapisać wygenerowaną prezentację?

Możesz zapisać wygenerowaną prezentację za pomocą `save` metoda. Podaj żądaną ścieżkę do pliku i `SaveFormat` jako parametry. Na przykład:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}