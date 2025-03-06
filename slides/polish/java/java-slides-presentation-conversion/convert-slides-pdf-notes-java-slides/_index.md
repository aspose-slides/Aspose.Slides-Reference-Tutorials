---
title: Konwertuj slajdy do formatu PDF za pomocą notatek w aplikacji Java Slides
linktitle: Konwertuj slajdy do formatu PDF za pomocą notatek w aplikacji Java Slides
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak konwertować slajdy programu PowerPoint do formatu PDF z notatkami w Javie przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku dla programistów Java. Usprawnij udostępnianie prezentacji.
weight: 19
url: /pl/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do konwertowania slajdów do formatu PDF za pomocą notatek w Javie

świecie prezentacji cyfrowych możliwość konwersji slajdów do formatu PDF wraz z towarzyszącymi im notatkami jest cenną funkcją. Programiści Java mogą to osiągnąć, korzystając z biblioteki Aspose.Slides for Java, która zapewnia solidny zestaw narzędzi do programowej pracy z prezentacjami programu PowerPoint. W tym przewodniku krok po kroku omówimy, jak konwertować slajdy do formatu PDF z notatkami przy użyciu języka Java i Aspose.Slides for Java.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

Teraz, gdy mamy już zarys, przejdźmy do wdrożenia krok po kroku.
## Krok 1: Konfiguracja projektu

Najpierw utwórz projekt Java i dodaj bibliotekę Aspose.Slides for Java do zależności swojego projektu.

## Krok 2: Ładowanie prezentacji

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Krok 3: Tworzenie nowej prezentacji

```java
Presentation auxPresentation = new Presentation();
```

## Krok 4: Kopiowanie slajdów

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Krok 5: Dostosowywanie rozmiaru slajdu

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Krok 6: Konfiguracja opcji PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 7: Zapisywanie w formacie PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Kompletny kod źródłowy do konwersji slajdów do formatu PDF z notatkami w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję obiektu Prezentacja reprezentującego plik prezentacji
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Ustawianie typu i rozmiaru slajdu
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), prezentacja.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się konwertować slajdy do formatu PDF z notatkami w Javie przy użyciu Aspose.Slides for Java. Omówiliśmy konfigurację projektu, ładowanie prezentacji, tworzenie nowej prezentacji, kopiowanie slajdów, dostosowywanie rozmiaru slajdów, konfigurowanie opcji PDF i na koniec zapisywanie prezentacji w formacie PDF z notatkami.

## Często zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Aby zainstalować Aspose.Slides dla Java, wykonaj następujące kroki:
1.  Pobierz bibliotekę z[Tutaj](https://releases.aspose.com/slides/java/).
2. Dodaj plik JAR do ścieżki klas projektu Java.

### Czy mogę dostosować położenie notatek w wygenerowanym pliku PDF?

 Tak, możesz dostosować położenie notatek, modyfikując plik`NotesPositions` enum w opcjach PDF. W tym samouczku ustawiliśmy to na`BottomFull`, ale możesz także sprawdzić inne opcje.

### Czy są jakieś wymagania licencyjne dotyczące korzystania z Aspose.Slides dla Java?

Tak, Aspose.Slides for Java jest biblioteką komercyjną i może być konieczne uzyskanie licencji, aby móc z niej korzystać w środowisku produkcyjnym. Odwiedź stronę internetową Aspose, aby uzyskać szczegółowe informacje na temat licencji.

### Czy mogę konwertować wiele slajdów jednocześnie?

pewnością! Możesz przeglądać slajdy w prezentacji i klonować je do nowej prezentacji, co pozwala na konwersję wielu slajdów do formatu PDF z notatkami za jednym razem.

### Gdzie mogę znaleźć więcej dokumentacji dla Aspose.Slides dla Java?

 Szczegółową dokumentację Aspose.Slides dla Java można znaleźć na stronie:[Aspose.Slides dla odniesienia do API Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
