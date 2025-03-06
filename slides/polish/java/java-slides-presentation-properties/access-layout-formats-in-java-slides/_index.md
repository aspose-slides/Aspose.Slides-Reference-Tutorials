---
title: Uzyskaj dostęp do formatów układu w slajdach Java
linktitle: Uzyskaj dostęp do formatów układu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak uzyskać dostęp do formatów układu i manipulować nimi w Java Slides za pomocą Aspose.Slides dla Java. Dostosuj style kształtów i linii bez wysiłku w prezentacjach programu PowerPoint.
weight: 10
url: /pl/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Uzyskaj dostęp do formatów układu w slajdach Java


## Wprowadzenie do formatów układu dostępu w slajdach Java

W tym samouczku przyjrzymy się, jak uzyskać dostęp do formatów układu w Java Slides i pracować z nimi, korzystając z interfejsu API Aspose.Slides for Java. Formaty układu umożliwiają kontrolowanie wyglądu kształtów i linii na slajdach układu prezentacji. Omówimy sposób pobierania formatów wypełnienia i formatów linii dla kształtów na slajdach układu.

## Warunki wstępne

1. Aspose.Slides dla biblioteki Java.
2. Prezentacja programu PowerPoint (format PPTX) ze slajdami układu.

## Krok 1: Załaduj prezentację

 Najpierw musimy załadować prezentację programu PowerPoint zawierającą slajdy układu. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Krok 2: Uzyskaj dostęp do formatów układu

Teraz przejrzyjmy slajdy układu w prezentacji i uzyskajmy dostęp do formatów wypełnienia i formatów linii kształtów na każdym slajdzie układu.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Dostęp do formatów wypełniania kształtów
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Dostęp do formatów kształtów
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

- Wykonujemy iterację po każdym slajdzie układu za pomocą a`for` pętla.
- Dla każdego slajdu układu tworzymy tablice do przechowywania formatów wypełnienia i formatów linii dla kształtów na tym slajdzie.
-  Używamy zagnieżdżonych`for` pętle umożliwiające przeglądanie kształtów na slajdzie układu i pobieranie ich formatów wypełnienia i linii.

## Krok 3: Pracuj z formatami układu

Teraz, gdy mamy już dostęp do formatów wypełnienia i formatów linii kształtów na slajdach układu, możesz w razie potrzeby wykonywać na nich różne operacje. Można na przykład zmienić kolor wypełnienia, styl linii lub inne właściwości kształtów.

## Kompletny kod źródłowy formatów układu dostępu w slajdach Java

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

W tym samouczku omówiliśmy, jak uzyskać dostęp do formatów układu w slajdach Java i manipulować nimi przy użyciu interfejsu API Aspose.Slides for Java. Formaty układów są niezbędne do kontrolowania wyglądu kształtów i linii na slajdach układu w prezentacjach programu PowerPoint.

## Często zadawane pytania

### Jak zmienić kolor wypełnienia kształtu?

 Aby zmienić kolor wypełnienia kształtu, możesz użyć opcji`IFillFormat`metody obiektu. Oto przykład:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Ustaw typ wypełnienia na jednolity kolor
fillFormat.getSolidFillColor().setColor(Color.RED); // Ustaw kolor wypełnienia na czerwony
```

### Jak zmienić styl linii kształtu?

 Aby zmienić styl linii kształtu, możesz użyć opcji`ILineFormat`metody obiektu. Oto przykład:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Ustaw styl linii na pojedynczy
lineFormat.setWidth(2.0); // Ustaw szerokość linii na 2,0 punkty
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Ustaw kolor linii na niebieski
```

### Jak zastosować te zmiany do kształtu na slajdzie układu?

Aby zastosować te zmiany do określonego kształtu na slajdzie układu, możesz uzyskać dostęp do kształtu, korzystając z jego indeksu w kolekcji kształtów slajdu układu. Na przykład:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Uzyskaj dostęp do pierwszego kształtu na slajdzie układu
```

 Następnie możesz użyć`IFillFormat` I`ILineFormat` metody pokazane w poprzednich odpowiedziach, aby zmodyfikować formaty wypełnienia i linii kształtu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
