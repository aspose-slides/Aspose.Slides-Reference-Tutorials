---
title: Konwertuj indywidualny slajd w slajdach Java
linktitle: Konwertuj indywidualny slajd w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak krok po kroku konwertować poszczególne slajdy programu PowerPoint do formatu HTML, korzystając z przykładów kodu przy użyciu Aspose.Slides dla Java.
weight: 12
url: /pl/java/presentation-conversion/convert-individual-slide-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do konwertowania poszczególnych slajdów w slajdach Java

W tym samouczku omówimy proces konwersji poszczególnych slajdów z prezentacji programu PowerPoint do formatu HTML przy użyciu Aspose.Slides for Java. W tym przewodniku krok po kroku znajdziesz kod źródłowy i wyjaśnienia, które pomogą Ci osiągnąć to zadanie.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

- Zainstalowana biblioteka Aspose.Slides dla Java.
- Plik prezentacji programu PowerPoint (`Individual-Slide.pptx`), który chcesz przekonwertować.
- Skonfigurowano środowisko programistyczne Java.

## Krok 1: Skonfiguruj projekt

1. Utwórz projekt Java w preferowanym środowisku programistycznym.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu.

## Krok 2: Zaimportuj niezbędne klasy

W klasie Java zaimportuj wymagane klasy i skonfiguruj początkową konfigurację.

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

 Utwórz metodę przeprowadzania konwersji poszczególnych slajdów. Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

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

## Krok 4: Zaimplementuj CustomFormattingController

 Utwórz`CustomFormattingController` class do obsługi niestandardowego formatowania podczas konwersji.

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

 Na koniec zadzwoń do`convertIndividualSlides` metoda wykonania procesu konwersji.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Kompletny kod źródłowy do konwersji poszczególnych slajdów w slajdach Java

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

Pomyślnie przekonwertowałeś pojedyncze slajdy z prezentacji programu PowerPoint do formatu HTML przy użyciu Aspose.Slides for Java. W tym samouczku przedstawiono niezbędny kod i kroki umożliwiające wykonanie tego zadania. Możesz dostosować wydruk i formatowanie zgodnie z własnymi wymaganiami.

## Często zadawane pytania

### Jak mogę bardziej dostosować dane wyjściowe HTML?

 Możesz dostosować dane wyjściowe HTML, modyfikując plik`CustomFormattingController` klasa. Poprawić`writeSlideStart` I`writeSlideEnd` metody zmiany struktury i stylu HTML slajdu.

### Czy mogę przekonwertować wiele prezentacji programu PowerPoint za jednym razem?

 Tak, możesz zmodyfikować kod, aby przeglądać wiele plików prezentacji i konwertować je indywidualnie, wywołując metodę`convertIndividualSlides` sposób na każdą prezentację.

### Jak sobie poradzić z dodatkowym formatowaniem kształtów i tekstu na slajdach?

 Możesz przedłużyć`CustomFormattingController` klasę do obsługi formatowania specyficznego dla kształtu poprzez implementację metody`writeShapeStart` I`writeShapeEnd` metod i stosując w nich niestandardową logikę formatowania.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
