---
"description": "Ulepsz prezentacje PowerPoint, stosując niestandardowe style, rozmiary i kolory czcionek dla poszczególnych legend w Java Slides, korzystając z Aspose.Slides for Java."
"linktitle": "Właściwości czcionki dla indywidualnej legendy w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Właściwości czcionki dla indywidualnej legendy w slajdach Java"
"url": "/pl/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Właściwości czcionki dla indywidualnej legendy w slajdach Java


## Wprowadzenie do właściwości czcionki dla indywidualnej legendy w slajdach Java

W tym samouczku pokażemy, jak ustawić właściwości czcionki dla pojedynczej legendy w Java Slides przy użyciu Aspose.Slides for Java. Dostosowując właściwości czcionki, możesz sprawić, że legendy będą bardziej atrakcyjne wizualnie i pouczające w prezentacjach PowerPoint.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zintegrowana z Twoim projektem. Możesz ją pobrać ze strony [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Zainicjuj prezentację i dodaj wykres

Najpierw zacznijmy od zainicjowania prezentacji PowerPoint i dodania do niej wykresu. W tym przykładzie użyjemy wykresu kolumnowego klastrowanego jako ilustracji.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Reszta kodu znajduje się tutaj
} finally {
    if (pres != null) pres.dispose();
}
```

Zastępować `"Your Document Directory"` z faktycznym katalogiem, w którym znajduje się dokument PowerPoint.

## Krok 2: Dostosuj właściwości czcionki dla legendy

Teraz dostosujmy właściwości czcionki dla pojedynczego wpisu legendy w wykresie. W tym przykładzie celujemy w drugi wpis legendy (indeks 1), ale możesz dostosować indeks zgodnie ze swoimi konkretnymi wymaganiami.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Oto, co robi każda linijka kodu:

- `get_Item(1)` pobiera drugi wpis legendy (indeks 1). Możesz zmienić indeks, aby wskazać inny wpis legendy.
- `setFontBold(NullableBool.True)` ustawia czcionkę na pogrubioną.
- `setFontHeight(20)` ustawia rozmiar czcionki na 20 punktów.
- `setFontItalic(NullableBool.True)` ustawia czcionkę na kursywę.
- `setFillType(FillType.Solid)` określa, że tekst wpisu legendy powinien mieć pełne wypełnienie.
- `getSolidFillColor().setColor(Color.BLUE)` ustawia kolor wypełnienia na niebieski. Możesz zastąpić `Color.BLUE` z wybranym przez Ciebie kolorem.

## Krok 3: Zapisz zmodyfikowaną prezentację

Na koniec zapisz zmodyfikowaną prezentację w nowym pliku, aby zachować zmiany.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Zastępować `"output.pptx"` z preferowaną nazwą pliku wyjściowego.

To wszystko! Udało Ci się dostosować właściwości czcionki dla pojedynczego wpisu legendy w prezentacji Java Slides przy użyciu Aspose.Slides for Java.

## Pełny kod źródłowy dla właściwości czcionki dla indywidualnej legendy w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dostosować właściwości czcionki dla pojedynczej legendy w Java Slides przy użyciu Aspose.Slides for Java. Dostosowując style, rozmiary i kolory czcionek, możesz poprawić atrakcyjność wizualną i przejrzystość swoich prezentacji PowerPoint.

## Najczęściej zadawane pytania

### Jak mogę zmienić kolor czcionki?

Aby zmienić kolor czcionki, użyj `tf.getPortionFormat().getFontColor().setColor(yourColor)` zamiast zmieniać kolor wypełnienia. Zastąp `yourColor` z wybranym kolorem czcionki.

### Jak modyfikować inne właściwości legendy?

Możesz modyfikować różne inne właściwości legendy, takie jak pozycja, rozmiar i format. Zapoznaj się z dokumentacją Aspose.Slides for Java, aby uzyskać szczegółowe informacje na temat pracy z legendami.

### Czy mogę zastosować te zmiany do wielu wpisów legendy?

Tak, możesz przechodzić przez wpisy legendy i stosować te zmiany do wielu wpisów, dostosowując indeks w `get_Item(index)` i powtórzenie kodu personalizacji.

Pamiętaj, aby pozbyć się obiektu prezentacji po zakończeniu zwalniania zasobów:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}