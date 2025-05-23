---
"description": "Dowiedz się, jak uzyskać dostęp i manipulować formatami układu w Java Slides za pomocą Aspose.Slides for Java. Bezproblemowo dostosuj style kształtów i linii w prezentacjach PowerPoint."
"linktitle": "Dostęp do formatów układu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dostęp do formatów układu w slajdach Java"
"url": "/pl/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dostęp do formatów układu w slajdach Java


## Wprowadzenie do formatów układu Access w slajdach Java

tym samouczku pokażemy, jak uzyskać dostęp i pracować z formatami układu w Java Slides przy użyciu Aspose.Slides for Java API. Formaty układu pozwalają kontrolować wygląd kształtów i linii w slajdach układu prezentacji. Omówimy, jak pobierać formaty wypełnienia i formaty linii dla kształtów na slajdach układu.

## Wymagania wstępne

1. Biblioteka Aspose.Slides dla Java.
2. Prezentacja w programie PowerPoint (format PPTX) ze slajdami układu.

## Krok 1: Załaduj prezentację

Najpierw musimy załadować prezentację PowerPoint, która zawiera slajdy układu. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Krok 2: Dostęp do formatów układu

Teraz przejrzyjmy slajdy układu w prezentacji i uzyskajmy dostęp do formatów wypełnienia i formatów linii kształtów na każdym slajdzie układu.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Uzyskaj dostęp do formatów wypełniania kształtów
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Dostęp do formatów linii kształtów
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

W powyższym kodzie:

- Powtarzamy każdy slajd układu, używając `for` pętla.
- Dla każdego slajdu układu tworzymy tablice, w których przechowujemy formaty wypełnień i formaty linii dla kształtów na danym slajdzie.
- Używamy zagnieżdżonych `for` pętle umożliwiające iteracyjne przeglądanie kształtów na slajdzie układu i pobieranie ich formatów wypełnienia i linii.

## Krok 3: Praca z formatami układu

Teraz, gdy uzyskaliśmy dostęp do formatów wypełnienia i formatów linii dla kształtów na slajdach układu, możesz wykonać na nich różne operacje według potrzeb. Na przykład możesz zmienić kolor wypełnienia, styl linii lub inne właściwości kształtów.

## Kompletny kod źródłowy dla formatów układu dostępu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku zbadaliśmy, jak uzyskać dostęp i manipulować formatami układu w Java Slides przy użyciu Aspose.Slides for Java API. Formaty układu są niezbędne do kontrolowania wyglądu kształtów i linii w slajdach układu w prezentacjach PowerPoint.

## Najczęściej zadawane pytania

### Jak zmienić kolor wypełnienia kształtu?

Aby zmienić kolor wypełnienia kształtu, możesz użyć `IFillFormat` metody obiektu. Oto przykład:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Ustaw typ wypełnienia na jednolity kolor
fillFormat.getSolidFillColor().setColor(Color.RED); // Ustaw kolor wypełnienia na czerwony
```

### Jak zmienić styl linii kształtu?

Aby zmienić styl linii kształtu, możesz użyć `ILineFormat` metody obiektu. Oto przykład:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Ustaw styl linii na pojedynczy
lineFormat.setWidth(2.0); // Ustaw szerokość linii na 2,0 punktów
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Ustaw kolor linii na niebieski
```

### Jak zastosować te zmiany do kształtu na slajdzie układu?

Aby zastosować te zmiany do określonego kształtu na slajdzie układu, możesz uzyskać dostęp do kształtu, używając jego indeksu w kolekcji kształtów slajdu układu. Na przykład:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Uzyskaj dostęp do pierwszego kształtu na slajdzie układu
```

Następnie możesz użyć `IFillFormat` I `ILineFormat` metody pokazane w poprzednich odpowiedziach, służące do modyfikacji formatu wypełnienia i linii kształtu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}