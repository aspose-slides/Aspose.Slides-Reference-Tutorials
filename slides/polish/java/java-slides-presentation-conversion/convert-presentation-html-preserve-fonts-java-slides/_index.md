---
title: Konwersja prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java
linktitle: Konwersja prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Konwertuj prezentacje programu PowerPoint do formatu HTML, zachowując oryginalne czcionki, korzystając z Aspose.Slides for Java.
weight: 14
url: /pl/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do konwertowania prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java

W tym samouczku przyjrzymy się, jak przekonwertować prezentację programu PowerPoint (PPTX) na format HTML, zachowując jednocześnie oryginalne czcionki, za pomocą Aspose.Slides dla Java. Dzięki temu wynikowy kod HTML będzie bardzo przypominał wygląd oryginalnej prezentacji.

## Krok 1: Konfiguracja projektu
Zanim zagłębimy się w kod, upewnijmy się, że masz niezbędną konfigurację:

1. Pobierz Aspose.Slides for Java: Jeśli jeszcze tego nie zrobiłeś, pobierz i dołącz bibliotekę Aspose.Slides for Java do swojego projektu.

2. Utwórz projekt Java: Skonfiguruj projekt Java w swoim ulubionym IDE i upewnij się, że masz folder „lib”, w którym możesz umieścić plik JAR Aspose.Slides.

3. Importuj wymagane klasy: Zaimportuj niezbędne klasy na początku pliku Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Konwersja prezentacji do formatu HTML przy użyciu oryginalnych czcionek

Teraz przekonwertujmy prezentację programu PowerPoint na format HTML, zachowując oryginalne czcionki:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Załaduj prezentację
Presentation pres = new Presentation("input.pptx");

try {
    // Wyklucz domyślne czcionki prezentacyjne, takie jak Calibri i Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Utwórz opcje HTML i ustaw niestandardowy formater HTML
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Zapisz prezentację jako HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Pozbądź się przedmiotu prezentacji
    if (pres != null) pres.dispose();
}
```

W tym fragmencie kodu:

-  Ładujemy wejściową prezentację PowerPoint za pomocą`Presentation`.

- Definiujemy listę czcionek (`fontNameExcludeList`), które chcemy wykluczyć z osadzania w kodzie HTML. Jest to przydatne do wykluczania popularnych czcionek, takich jak Calibri i Arial, w celu zmniejszenia rozmiaru pliku.

-  Tworzymy instancję`EmbedAllFontsHtmlController` i przekaż mu listę wykluczeń czcionek.

-  Tworzymy`HtmlOptions` i ustaw niestandardowy formater HTML za pomocą`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Na koniec zapisujemy prezentację jako HTML z określonymi opcjami.

## Kompletny kod źródłowy do konwersji prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// wyklucz domyślne czcionki prezentacyjne
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się, jak przekonwertować prezentację programu PowerPoint do formatu HTML, zachowując jednocześnie oryginalne czcionki, za pomocą Aspose.Slides for Java. Jest to przydatne, gdy chcesz zachować wierność wizualną prezentacji podczas udostępniania ich w Internecie.

## Często zadawane pytania

### Jak pobrać Aspose.Slides dla Java?

 Możesz pobrać Aspose.Slides dla Java ze strony internetowej Aspose. Odwiedzać[Tutaj](https://downloads.aspose.com/slides/java/) aby uzyskać najnowszą wersję.

### Czy mogę dostosować listę wykluczonych czcionek?

 Tak, możesz dostosować`fontNameExcludeList` array, aby uwzględnić lub wykluczyć określone czcionki zgodnie z wymaganiami.

### Czy ta metoda działa w przypadku starszych formatów programu PowerPoint, takich jak PPT?

Ten przykładowy kod jest przeznaczony dla plików PPTX. Jeśli chcesz przekonwertować starsze pliki PPT, może być konieczne wprowadzenie zmian w kodzie.

### Jak mogę dodatkowo dostosować dane wyjściowe HTML?

 Możesz zwiedzać`HtmlOptions` class, aby dostosować różne aspekty wyniku HTML, takie jak rozmiar slajdu, jakość obrazu i inne.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
