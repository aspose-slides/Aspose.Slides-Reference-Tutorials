---
title: Tworzenie wykresów radarowych w slajdach Java
linktitle: Tworzenie wykresów radarowych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć wykresy radarowe w prezentacjach Java PowerPoint przy użyciu Aspose.Slides for Java API.
weight: 10
url: /pl/java/chart-creation/radar-chart-creating-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie wykresów radarowych w slajdach Java


## Wprowadzenie do tworzenia wykresu radarowego w Java Slides

tym samouczku przeprowadzimy Cię przez proces tworzenia wykresu radarowego przy użyciu interfejsu API Aspose.Slides for Java. Wykresy radarowe są przydatne do wizualizacji danych w formie kołowej, co ułatwia porównywanie wielu serii danych. Dostarczymy instrukcje krok po kroku wraz z kodem źródłowym Java.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że masz zintegrowaną bibliotekę Aspose.Slides for Java ze swoim projektem. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Konfiguracja prezentacji

Zacznijmy od skonfigurowania nowej prezentacji PowerPoint i dodania do niej slajdu.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Krok 2: Dodawanie mapy radarowej

Następnie dodamy do slajdu wykres radarowy. Określimy położenie i wymiary wykresu.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Krok 3: Ustawianie danych wykresu

Teraz ustawimy dane wykresu. Obejmuje to utworzenie skoroszytu danych, dodanie kategorii i dodanie serii.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Ustaw tytuł wykresu
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Usuń domyślnie wygenerowane serie i kategorie
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Dodawanie nowych kategorii
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Dodawanie nowej serii
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Krok 4: Wypełnianie danych serii

Teraz wypełnimy dane serii dla naszego wykresu radarowego.

```java
// Wypełnij dane serii dla serii 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Ustaw kolor serii
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Wypełnij dane serii dla serii 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Ustaw kolor serii
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Krok 5: Dostosowywanie osi i legend

Dostosujmy oś i legendy naszego wykresu radarowego.

```java
// Ustaw pozycję legendy
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Ustawianie właściwości tekstu osi kategorii
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Ustawianie właściwości tekstu legendy
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Ustawianie właściwości tekstu osi wartości
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Ustawianie formatu numeru osi wartości
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Ustawianie wartości jednostki głównej wykresu
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Krok 6: Zapisywanie prezentacji

Na koniec zapisz wygenerowaną prezentację z wykresem radarowym

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Otóż to! Pomyślnie utworzyłeś wykres radarowy w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Możesz teraz dostosować ten przykład do swoich konkretnych potrzeb.

## Kompletny kod źródłowy do tworzenia wykresów radarowych w slajdach Java

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Uzyskaj dostęp do pierwszego slajdu
	ISlide sld = pres.getSlides().get_Item(0);
	// Dodaj wykres radarowy
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Ustawianie indeksu arkusza danych wykresu
	int defaultWorksheetIndex = 0;
	// Pobieranie danych wykresu Arkusz roboczy
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Ustaw tytuł wykresu
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Usuń domyślnie wygenerowane serie i kategorie
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Dodawanie nowych kategorii
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Dodawanie nowej serii
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Teraz wypełniam dane serii
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Ustaw kolor serii
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//Teraz wypełniam dane z kolejnej serii
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Ustaw kolor serii
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Ustaw pozycję legendy
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Ustawianie właściwości tekstu osi kategorii
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Ustawianie właściwości tekstu legendy
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Ustawianie właściwości tekstu osi wartości
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Ustawianie formatu numeru osi wartości
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Ustawianie wartości jednostki głównej wykresu
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Zapisz wygenerowaną prezentację
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się tworzyć wykres radarowy w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Możesz zastosować te koncepcje, aby skutecznie wizualizować i prezentować dane w aplikacjach Java.

## Często zadawane pytania

### Jak mogę zmienić tytuł wykresu?

Aby zmienić tytuł wykresu, zmodyfikuj następujący wiersz:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Czy mogę dodać więcej serii danych do wykresu radarowego?

Tak, możesz dodać więcej serii danych, wykonując czynności opisane w „Kroku 3” i „Kroku 4” dla każdej dodatkowej serii, którą chcesz uwzględnić.

### Jak dostosować kolory wykresu?

 Kolory serii można dostosować, modyfikując linie określające`SolidFillColor` własności każdego szeregu. Na przykład:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Jak mogę zmienić etykiety osi i formatowanie?

Aby dostosować etykiety osi i formatowanie, w tym rozmiar i kolor czcionki, zobacz „Krok 5”.

### Jak zapisać wykres w innym formacie pliku?

Możesz zmienić format wyjściowy, modyfikując rozszerzenie pliku w formacie`outPath` zmiennej i używając odpowiedniego`SaveFormat` . Na przykład, aby zapisać jako plik PDF, użyj`SaveFormat.Pdf`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
