---
title: Dodawanie niestandardowych linii w slajdach Java
linktitle: Dodawanie niestandardowych linii w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz swoje slajdy Java za pomocą niestandardowych linii. Przewodnik krok po kroku dotyczący korzystania z Aspose.Slides dla Java. Dowiedz się, jak dodawać i dostosowywać linie w prezentacjach, aby uzyskać efektowne efekty wizualne.
weight: 10
url: /pl/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie niestandardowych linii w slajdach Java


## Wprowadzenie do dodawania niestandardowych linii w slajdach Java

tym samouczku dowiesz się, jak dodawać niestandardowe linie do slajdów Java za pomocą Aspose.Slides for Java. Niestandardowych linii można użyć w celu ulepszenia wizualnej reprezentacji slajdów i wyróżnienia określonej treści. Dostarczymy Ci instrukcje krok po kroku wraz z kodem źródłowym, jak to osiągnąć. Zacznijmy!

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że w projekcie Java masz skonfigurowaną bibliotekę Aspose.Slides dla Java. Bibliotekę można pobrać ze strony:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## Krok 1: Zainicjuj prezentację

Najpierw musisz utworzyć nową prezentację. W tym przykładzie utworzymy pustą prezentację.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Następnie dodamy wykres do slajdu. W tym przykładzie dodajemy grupowany wykres kolumnowy. Możesz wybrać typ wykresu odpowiadający Twoim potrzebom.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## Krok 3: Dodaj linię niestandardową

 Dodajmy teraz niestandardową linię do wykresu. Stworzymy`IAutoShape` typu`ShapeType.Line` i umieść go na wykresie.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Krok 4: Dostosuj linię

Możesz dostosować wygląd linii, ustawiając jej właściwości. W tym przykładzie ustawiamy kolor linii na czerwony.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 5: Zapisz prezentację

Na koniec zapisz prezentację w wybranej lokalizacji.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do dodawania niestandardowych linii w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Gratulacje! Pomyślnie dodałeś niestandardową linię do slajdu Java za pomocą Aspose.Slides for Java. Możesz dodatkowo dostosować właściwości linii, aby uzyskać pożądane efekty wizualne.

## Często zadawane pytania

### Jak zmienić kolor linii?

Aby zmienić kolor linii, użyj następującego kodu:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 Zastępować`YOUR_COLOR` z żądanym kolorem.

### Czy mogę dodać niestandardowe linie do innych kształtów?

 Tak, możesz dodawać niestandardowe linie do różnych kształtów, a nie tylko do wykresów. Po prostu utwórz`IAutoShape` i dostosuj go do swoich potrzeb.

### Jak mogę zmienić grubość linii?

 Grubość linii można zmienić, ustawiając opcję`Width` właściwość formatu linii. Na przykład:
```java
shape.getLineFormat().setWidth(2); // Ustaw grubość linii na 2 punkty
```

### Czy można dodać wiele linii do slajdu?

Tak, możesz dodać wiele linii do slajdu, powtarzając kroki opisane w tym samouczku. Każdą linię można dostosować niezależnie.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
