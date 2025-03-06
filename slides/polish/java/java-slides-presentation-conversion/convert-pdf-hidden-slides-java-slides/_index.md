---
title: Konwertuj na format PDF za pomocą ukrytych slajdów w aplikacji Java Slides
linktitle: Konwertuj na format PDF za pomocą ukrytych slajdów w aplikacji Java Slides
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak konwertować prezentacje programu PowerPoint do formatu PDF z ukrytymi slajdami przy użyciu Aspose.Slides dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku z kodem źródłowym, aby bezproblemowo generować pliki PDF.
weight: 27
url: /pl/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do konwertowania prezentacji programu PowerPoint do formatu PDF z ukrytymi slajdami przy użyciu Aspose.Slides dla Java

tym przewodniku krok po kroku dowiesz się, jak przekonwertować prezentację programu PowerPoint do formatu PDF, zachowując jednocześnie ukryte slajdy za pomocą Aspose.Slides for Java. Ukryte slajdy to te, które nie są wyświetlane podczas zwykłej prezentacji, ale można je uwzględnić w pliku wyjściowym PDF. Dostarczymy Ci kod źródłowy i szczegółowe instrukcje dotyczące wykonania tego zadania.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Biblioteka Aspose.Slides for Java: Upewnij się, że w projekcie Java skonfigurowano bibliotekę Aspose.Slides for Java. Można go pobrać z[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

2. Środowisko programistyczne Java: Powinieneś mieć zainstalowane środowisko programistyczne Java w swoim systemie.

## Krok 1: Zaimportuj Aspose.Slides dla Java

Najpierw musisz zaimportować bibliotekę Aspose.Slides do swojego projektu Java. Upewnij się, że dodałeś bibliotekę do ścieżki kompilacji projektu.

```java
import com.aspose.slides.*;
```

## Krok 2: Załaduj prezentację programu PowerPoint

 Zaczniesz od załadowania prezentacji programu PowerPoint, którą chcesz przekonwertować do formatu PDF. Zastępować`"Your Document Directory"` I`"HiddingSlides.pptx"` z odpowiednią ścieżką pliku.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Krok 3: Skonfiguruj opcje PDF

Skonfiguruj opcje PDF, aby uwzględnić ukryte slajdy w wyjściowym pliku PDF. Można to zrobić ustawiając`setShowHiddenSlides` własność`PdfOptions` klasa do`true`.

```java
// Utwórz instancję klasy PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Określ, że wygenerowany dokument powinien zawierać ukryte slajdy
pdfOptions.setShowHiddenSlides(true);
```

## Krok 4: Zapisz prezentację jako plik PDF

 Teraz zapisz prezentację w pliku PDF z określonymi opcjami. Zastępować`"PDFWithHiddenSlides_out.pdf"` z żądaną nazwą pliku wyjściowego.

```java
// Zapisz prezentację w formacie PDF z określonymi opcjami
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Krok 5: Zasoby oczyszczania

Po zakończeniu prezentacji pamiętaj o zwolnieniu zasobów używanych przez prezentację.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Kompletny kod źródłowy do konwersji do formatu PDF z ukrytymi slajdami w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Utwórz instancję klasy PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Określ, że wygenerowany dokument powinien zawierać ukryte slajdy
	pdfOptions.setShowHiddenSlides(true);
	// Zapisz prezentację w formacie PDF z określonymi opcjami
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym obszernym przewodniku nauczyłeś się, jak konwertować prezentację programu PowerPoint do formatu PDF, zachowując jednocześnie ukryte slajdy za pomocą Aspose.Slides dla Java. Udostępniliśmy Ci samouczek krok po kroku wraz z niezbędnym kodem źródłowym, aby bezproblemowo wykonać to zadanie.

## Często zadawane pytania

### Jak ukryć slajdy w prezentacji programu PowerPoint?

Aby ukryć slajd w prezentacji programu PowerPoint, wykonaj następujące kroki:
1. Wybierz slajd, który chcesz ukryć w widoku sortowania slajdów.
2. Kliknij prawym przyciskiem myszy wybrany slajd.
3. Z menu kontekstowego wybierz opcję „Ukryj slajd”.

### Czy mogę programowo odkryć ukryte slajdy w Aspose.Slides dla Java?

 Tak, możesz programowo odkryć ukryte slajdy w Aspose.Slides dla Java, ustawiając`Hidden` własność`Slide` klasa do`false`. Oto przykład:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Zamień slideIndex na indeks ukrytego slajdu
slide.setHidden(false);
```

### Jak pobrać Aspose.Slides dla Java?

 Możesz pobrać Aspose.Slides dla Java ze strony internetowej Aspose. Odwiedzić[Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/) aby uzyskać najnowszą wersję.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
