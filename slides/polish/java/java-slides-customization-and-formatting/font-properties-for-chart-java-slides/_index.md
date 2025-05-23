---
"description": "Ulepsz właściwości czcionki wykresu w slajdach Java za pomocą Aspose.Slides dla Java. Dostosuj rozmiar, styl i kolor czcionki, aby prezentacje były efektowne."
"linktitle": "Właściwości czcionki dla wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Właściwości czcionki dla wykresu w slajdach Java"
"url": "/pl/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Właściwości czcionki dla wykresu w slajdach Java


## Wprowadzenie do właściwości czcionki dla wykresu w slajdach Java

Ten przewodnik przeprowadzi Cię przez ustawianie właściwości czcionki dla wykresu w Java Slides przy użyciu Aspose.Slides. Możesz dostosować rozmiar czcionki i wygląd tekstu wykresu, aby poprawić atrakcyjność wizualną swoich prezentacji.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz Aspose.Slides for Java API zintegrowane z projektem. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać je z [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację

Najpierw utwórz nową prezentację korzystając z następującego kodu:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Teraz dodajmy do prezentacji wykres kolumnowy klastrowany:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Tutaj dodajemy wykres kolumnowy klastrowany do pierwszego slajdu na współrzędnych (100, 100) o szerokości 500 jednostek i wysokości 400 jednostek.

## Krok 3: Dostosuj właściwości czcionki

Następnie dostosujemy właściwości czcionki wykresu. W tym przykładzie ustawiamy rozmiar czcionki na 20 dla całego tekstu wykresu:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ten kod ustawia rozmiar czcionki na 20 punktów dla całego tekstu na wykresie.

## Krok 4: Pokaż etykiety danych

Etykiety danych na wykresie można również wyświetlać, używając następującego kodu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Ten wiersz kodu włącza etykiety danych dla pierwszej serii na wykresie, wyświetlając wartości w kolumnach wykresu.

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację ze spersonalizowanymi właściwościami czcionki wykresu:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ten kod zapisze prezentację w określonym katalogu pod nazwą pliku „FontPropertiesForChart.pptx”.

## Kompletny kod źródłowy dla właściwości czcionki dla wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku nauczyłeś się, jak dostosować właściwości czcionki dla wykresu w Java Slides przy użyciu Aspose.Slides for Java. Możesz zastosować te techniki, aby poprawić wygląd wykresów i prezentacji. Odkryj więcej opcji w [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Najczęściej zadawane pytania

### Jak mogę zmienić kolor czcionki?

Aby zmienić kolor czcionki tekstu wykresu, użyj `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, zastępując `Color.RED` w wybranym kolorze.

### Czy mogę zmienić styl czcionki (pogrubienie, kursywa itp.)?

Tak, możesz zmienić styl czcionki. Użyj `chart.getTextFormat().getPortionFormat().setFontBold(true);` aby pogrubić czcionkę. Podobnie możesz użyć `setFontItalic(true)` aby zapisać kursywą.

### Jak dostosować właściwości czcionki do konkretnych elementów wykresu?

Aby dostosować właściwości czcionki do konkretnych elementów wykresu, np. etykiet osi lub tekstu legendy, możesz uzyskać dostęp do tych elementów i ustawić ich właściwości czcionki, korzystając z podobnych metod, jak pokazano powyżej.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}