---
"description": "Dowiedz się, jak konwertować slajdy programu PowerPoint do formatu PDF z notatkami w Javie przy użyciu Aspose.Slides dla Javy. Przewodnik krok po kroku dla programistów Javy. Ulepsz udostępnianie prezentacji."
"linktitle": "Konwertuj slajdy do formatu PDF z notatkami w Java Slides"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Konwertuj slajdy do formatu PDF z notatkami w Java Slides"
"url": "/pl/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj slajdy do formatu PDF z notatkami w Java Slides


## Wprowadzenie do konwersji slajdów do formatu PDF z notatkami w języku Java

W świecie prezentacji cyfrowych możliwość konwersji slajdów do formatu PDF z towarzyszącymi notatkami jest cenną funkcją. Programiści Java mogą to osiągnąć, korzystając z biblioteki Aspose.Slides for Java, która zapewnia solidny zestaw narzędzi do pracy z prezentacjami PowerPoint programowo. W tym przewodniku krok po kroku przyjrzymy się, jak konwertować slajdy do formatu PDF z notatkami przy użyciu Java i Aspose.Slides for Java.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

Teraz, gdy mamy już zarys projektu, możemy przejść do jego realizacji krok po kroku.
## Krok 1: Konfigurowanie projektu

Najpierw utwórz projekt Java i dodaj bibliotekę Aspose.Slides for Java do zależności projektu.

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

## Krok 6: Konfigurowanie opcji PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 7: Zapisywanie jako PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Kompletny kod źródłowy do konwersji slajdów do formatu PDF z notatkami w Java Slides

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz obiekt Prezentacja reprezentujący plik prezentacji 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Ustawianie typu i rozmiaru slajdu
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
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

tym samouczku nauczyliśmy się, jak konwertować slajdy do PDF z notatkami w Javie przy użyciu Aspose.Slides for Java. Omówiliśmy konfigurowanie projektu, ładowanie prezentacji, tworzenie nowej prezentacji, kopiowanie slajdów, dostosowywanie rozmiaru slajdu, konfigurowanie opcji PDF i na koniec zapisywanie prezentacji jako PDF z notatkami.

## Najczęściej zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Aby zainstalować Aspose.Slides dla Java, wykonaj następujące kroki:
1. Pobierz bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).
2. Dodaj plik JAR do ścieżki klas swojego projektu Java.

### Czy mogę dostosować położenie notatek w wygenerowanym pliku PDF?

Tak, możesz dostosować położenie notatek, modyfikując `NotesPositions` enum w opcjach PDF. W tym samouczku ustawiliśmy to na `BottomFull`, ale możesz również rozważyć inne opcje.

### Czy istnieją jakieś wymagania licencyjne dotyczące korzystania z Aspose.Slides dla Java?

Tak, Aspose.Slides for Java jest biblioteką komercyjną i może być konieczne nabycie licencji, aby używać jej w środowisku produkcyjnym. Odwiedź witrynę Aspose, aby uzyskać szczegółowe informacje na temat licencjonowania.

### Czy mogę przekonwertować wiele slajdów jednocześnie?

Oczywiście! Możesz przeglądać slajdy w swojej prezentacji i klonować je do nowej prezentacji, co pozwoli Ci przekonwertować wiele slajdów do PDF z notatkami za jednym razem.

### Gdzie mogę znaleźć więcej dokumentacji dla Aspose.Slides dla Java?

Szczegółową dokumentację Aspose.Slides dla Java można znaleźć na stronie: [Aspose.Slides dla Java API Reference](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}