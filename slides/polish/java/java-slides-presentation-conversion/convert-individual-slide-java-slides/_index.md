---
"description": "Dowiedz się, jak krok po kroku konwertować pojedyncze slajdy programu PowerPoint do formatu HTML za pomocą przykładów kodu przy użyciu Aspose.Slides for Java."
"linktitle": "Konwertuj pojedynczy slajd w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Konwertuj pojedynczy slajd w slajdach Java"
"url": "/pl/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj pojedynczy slajd w slajdach Java


## Wprowadzenie do konwersji pojedynczych slajdów w Java Slides

W tym samouczku przeprowadzimy Cię przez proces konwersji pojedynczych slajdów z prezentacji PowerPoint do HTML przy użyciu Aspose.Slides for Java. Ten przewodnik krok po kroku dostarczy Ci kod źródłowy i wyjaśnienia, które pomogą Ci wykonać to zadanie.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- Zainstalowano bibliotekę Aspose.Slides for Java.
- Plik prezentacji PowerPoint (`Individual-Slide.pptx`) który chcesz przekonwertować.
- Konfiguracja środowiska programistycznego Java.

## Krok 1: Skonfiguruj projekt

1. Utwórz projekt Java w preferowanym środowisku programistycznym.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu.

## Krok 2: Importuj niezbędne klasy

W swojej klasie Java zaimportuj wymagane klasy i skonfiguruj je początkowo.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## Krok 3: Zdefiniuj główną metodę konwersji

Utwórz metodę wykonywania konwersji pojedynczych slajdów. Upewnij się, że zastąpisz `"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Zapisywanie pliku
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Krok 4: Implementacja CustomFormattingController

Utwórz `CustomFormattingController` Klasa obsługująca formatowanie niestandardowe podczas konwersji.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## Krok 5: Wykonaj konwersję

Na koniec zadzwoń `convertIndividualSlides` metoda wykonania procesu konwersji.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Kompletny kod źródłowy do konwersji pojedynczych slajdów w slajdach Java

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Zapisywanie pliku              
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## Wniosek

Udało Ci się przekonwertować poszczególne slajdy z prezentacji PowerPoint na HTML przy użyciu Aspose.Slides for Java. Ten samouczek dostarczył Ci niezbędnego kodu i kroków do wykonania tego zadania. Możesz dostosować dane wyjściowe i formatowanie zgodnie ze swoimi konkretnymi wymaganiami.

## Najczęściej zadawane pytania

### W jaki sposób mogę jeszcze bardziej dostosować wyjście HTML?

Możesz dostosować wynik HTML, modyfikując `CustomFormattingController` klasa. Dostosuj `writeSlideStart` I `writeSlideEnd` metody zmiany struktury i stylu HTML slajdu.

### Czy mogę przekonwertować wiele prezentacji PowerPoint na raz?

Tak, możesz zmodyfikować kod, aby przechodził przez wiele plików prezentacji i konwertował je indywidualnie, wywołując `convertIndividualSlides` metodę dla każdej prezentacji.

### Jak radzić sobie z dodatkowym formatowaniem kształtów i tekstu na slajdach?

Możesz rozszerzyć `CustomFormattingController` klasa do obsługi formatowania specyficznego dla kształtu poprzez implementację `writeShapeStart` I `writeShapeEnd` metod i stosowania w nich niestandardowej logiki formatowania.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}