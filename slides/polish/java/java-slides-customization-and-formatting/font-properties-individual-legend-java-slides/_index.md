---
title: Właściwości czcionki dla indywidualnej legendy w slajdach Java
linktitle: Właściwości czcionki dla indywidualnej legendy w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz prezentacje programu PowerPoint za pomocą niestandardowych stylów czcionek, rozmiarów i kolorów poszczególnych legend w Java Slides za pomocą Aspose.Slides for Java.
weight: 12
url: /pl/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do właściwości czcionek dla poszczególnych legend w slajdach Java

W tym samouczku przyjrzymy się, jak ustawić właściwości czcionki dla pojedynczej legendy w Java Slides przy użyciu Aspose.Slides dla Java. Dostosowując właściwości czcionki, możesz sprawić, że legendy będą bardziej atrakcyjne wizualnie i pouczające w prezentacjach programu PowerPoint.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zintegrowaną bibliotekę Aspose.Slides for Java ze swoim projektem. Można go pobrać z[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

## Krok 1: Zainicjuj prezentację i dodaj wykres

Zacznijmy od zainicjowania prezentacji programu PowerPoint i dodania do niej wykresu. W tym przykładzie jako ilustracji użyjemy grupowanego wykresu kolumnowego.

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

 Zastępować`"Your Document Directory"` z rzeczywistym katalogiem, w którym znajduje się dokument programu PowerPoint.

## Krok 2: Dostosuj właściwości czcionki dla legendy

Teraz dostosujmy właściwości czcionki dla pojedynczego wpisu legendy na wykresie. W tym przykładzie skupiamy się na drugim wpisie legendy (indeks 1), ale możesz dostosować indeks zgodnie ze swoimi konkretnymi wymaganiami.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Oto, co robi każda linia kodu:

- `get_Item(1)` pobiera drugi wpis legendy (indeks 1). Można zmienić indeks, aby uwzględnić inny wpis legendy.
- `setFontBold(NullableBool.True)` ustawia czcionkę na pogrubioną.
- `setFontHeight(20)` ustawia rozmiar czcionki na 20 punktów.
- `setFontItalic(NullableBool.True)` ustawia czcionkę na kursywę.
- `setFillType(FillType.Solid)` określa, że tekst wpisu legendy powinien mieć pełne wypełnienie.
- `getSolidFillColor().setColor(Color.BLUE)` ustawia kolor wypełnienia na niebieski. Możesz wymienić`Color.BLUE` z wybranym kolorem.

## Krok 3: Zapisz zmodyfikowaną prezentację

Na koniec zapisz zmodyfikowaną prezentację w nowym pliku, aby zachować zmiany.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Zastępować`"output.pptx"` z preferowaną nazwą pliku wyjściowego.

Otóż to! Pomyślnie dostosowałeś właściwości czcionki dla pojedynczego wpisu legendy w prezentacji Java Slides przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy właściwości czcionki dla poszczególnych legend w slajdach Java

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

W tym samouczku dowiedzieliśmy się, jak dostosować właściwości czcionki dla pojedynczej legendy w Java Slides za pomocą Aspose.Slides dla Java. Dostosowując style, rozmiary i kolory czcionek, możesz poprawić atrakcyjność wizualną i przejrzystość prezentacji programu PowerPoint.

## Często zadawane pytania

### Jak mogę zmienić kolor czcionki?

 Aby zmienić kolor czcionki, użyj`tf.getPortionFormat().getFontColor().setColor(yourColor)` zamiast zmieniać kolor wypełnienia. Zastępować`yourColor` z żądanym kolorem czcionki.

### Jak zmodyfikować inne właściwości legendy?

Można modyfikować różne inne właściwości legendy, takie jak położenie, rozmiar i format. Szczegółowe informacje na temat pracy z legendami można znaleźć w dokumentacji Aspose.Slides for Java.

### Czy mogę zastosować te zmiany do wielu wpisów w legendzie?

 Tak, możesz przeglądać wpisy legendy i stosować te zmiany do wielu wpisów, dostosowując indeks w`get_Item(index)` i powtórzenie kodu dostosowywania.

Pamiętaj, aby po zakończeniu zwalniania zasobów pozbyć się obiektu prezentacji:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
