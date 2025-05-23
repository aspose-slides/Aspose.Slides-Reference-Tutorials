---
"description": "Dowiedz się, jak tworzyć wykresy radarowe w prezentacjach PowerPoint w języku Java, korzystając z interfejsu API Aspose.Slides for Java."
"linktitle": "Tworzenie wykresu radarowego w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Tworzenie wykresu radarowego w slajdach Java"
"url": "/pl/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie wykresu radarowego w slajdach Java


## Wprowadzenie do tworzenia wykresu radarowego w slajdach Java

tym samouczku przeprowadzimy Cię przez proces tworzenia Radar Chart przy użyciu Aspose.Slides for Java API. Radar charts są przydatne do wizualizacji danych w formie kołowej, ułatwiając porównywanie wielu serii danych. Podamy instrukcje krok po kroku wraz z kodem źródłowym Java.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides for Java jest zintegrowana z Twoim projektem. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Konfigurowanie prezentacji

Zacznijmy od utworzenia nowej prezentacji programu PowerPoint i dodania do niej slajdu.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Krok 2: Dodawanie wykresu radarowego

Następnie dodamy do slajdu wykres radarowy. Określimy położenie i wymiary wykresu.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Krok 3: Ustawianie danych wykresu

Teraz ustawimy dane wykresu. Wiąże się to z utworzeniem skoroszytu danych, dodaniem kategorii i dodaniem serii.

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

Dostosujmy oś i legendę naszego wykresu radarowego.

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

// Ustawianie właściwości tekstu legend
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

// Ustawianie formatu liczby osi wartości
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Ustawienie wartości głównej jednostki wykresu
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Krok 6: Zapisywanie prezentacji

Na koniec zapisz wygenerowaną prezentację z wykresem radarowym

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

To wszystko! Udało Ci się utworzyć wykres radarowy w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Teraz możesz dostosować ten przykład dalej, aby odpowiadał Twoim konkretnym potrzebom.

## Kompletny kod źródłowy do tworzenia wykresu radarowego w slajdach Java

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Dostęp do pierwszego slajdu
	ISlide sld = pres.getSlides().get_Item(0);
	// Dodaj wykres radarowy
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Ustawianie indeksu arkusza danych wykresu
	int defaultWorksheetIndex = 0;
	// Pobieranie arkusza roboczego danych wykresu
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
	// Teraz wypełniamy dane serii
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
	// Teraz wypełniamy dane innej serii
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
	// Ustawianie właściwości tekstu legend
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
	// Ustawianie formatu liczby osi wartości
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Ustawienie wartości głównej jednostki wykresu
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

W tym samouczku nauczyłeś się, jak utworzyć wykres radarowy w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Możesz zastosować te koncepcje, aby skutecznie wizualizować i prezentować dane w aplikacjach Java.

## Najczęściej zadawane pytania

### Jak mogę zmienić tytuł wykresu?

Aby zmienić tytuł wykresu, zmodyfikuj następujący wiersz:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Czy mogę dodać więcej serii danych do wykresu radarowego?

Tak, możesz dodać więcej serii danych, wykonując czynności opisane w „Kroku 3” i „Kroku 4” dla każdej dodatkowej serii, którą chcesz uwzględnić.

### Jak dostosować kolory wykresu?

Możesz dostosować kolory serii, modyfikując linie, które je ustawiają `SolidFillColor` właściwość dla każdej serii. Na przykład:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Jak mogę zmienić etykiety i formatowanie osi?

Aby dostosować etykiety osi i formatowanie, w tym rozmiar i kolor czcionki, zapoznaj się z „Krokiem 5”.

### Jak zapisać wykres w innym formacie pliku?

Możesz zmienić format wyjściowy, modyfikując rozszerzenie pliku w `outPath` zmienna i używająca odpowiedniej `SaveFormat`Na przykład, aby zapisać jako PDF, użyj `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}