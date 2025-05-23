---
"description": "Konwertuj prezentacje PowerPoint do formatu HTML, zachowując oryginalne czcionki, korzystając z Aspose.Slides dla Java."
"linktitle": "Konwersja prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Konwersja prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java"
"url": "/pl/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwersja prezentacji do formatu HTML z zachowaniem oryginalnych czcionek w slajdach Java


## Wprowadzenie do konwersji prezentacji do HTML z zachowaniem oryginalnych czcionek w slajdach Java

W tym samouczku pokażemy, jak przekonwertować prezentację PowerPoint (PPTX) na HTML, zachowując oryginalne czcionki przy użyciu Aspose.Slides dla Java. Dzięki temu wynikowy HTML będzie bardzo przypominał wygląd oryginalnej prezentacji.

## Krok 1: Konfigurowanie projektu
Zanim zagłębimy się w kod, upewnijmy się, że masz wszystkie niezbędne ustawienia:

1. Pobierz Aspose.Slides for Java: Jeśli jeszcze tego nie zrobiłeś, pobierz i dołącz bibliotekę Aspose.Slides for Java do swojego projektu.

2. Utwórz projekt Java: Utwórz projekt Java w swoim ulubionym środowisku IDE i upewnij się, że masz folder „lib”, w którym możesz umieścić plik JAR Aspose.Slides.

3. Importuj wymagane klasy: Zaimportuj wymagane klasy na początku pliku Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Konwersja prezentacji do formatu HTML z oryginalnymi czcionkami

Teraz przekonwertujemy prezentację PowerPoint do formatu HTML, zachowując oryginalne czcionki:

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
    // Usuń obiekt prezentacji
    if (pres != null) pres.dispose();
}
```

W tym fragmencie kodu:

- Załaduj prezentację wejściową PowerPoint za pomocą `Presentation`.

- Definiujemy listę czcionek (`fontNameExcludeList`) które chcemy wykluczyć z osadzania w HTML. Jest to przydatne do wykluczania popularnych czcionek, takich jak Calibri i Arial, aby zmniejszyć rozmiar pliku.

- Tworzymy instancję `EmbedAllFontsHtmlController` i przekazać mu listę wykluczonych czcionek.

- Tworzymy `HtmlOptions` i ustaw niestandardowy formater HTML za pomocą `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Na koniec zapisujemy prezentację w formacie HTML ze wskazanymi opcjami.

## Kompletny kod źródłowy do konwersji prezentacji do HTML z zachowaniem oryginalnych czcionek w slajdach Java

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

W tym samouczku dowiedziałeś się, jak przekonwertować prezentację PowerPoint na HTML, zachowując oryginalne czcionki za pomocą Aspose.Slides dla Java. Jest to przydatne, gdy chcesz zachować wierność wizualną swoich prezentacji podczas udostępniania ich w sieci.

## Najczęściej zadawane pytania

### Jak pobrać Aspose.Slides dla Java?

Możesz pobrać Aspose.Slides dla Java ze strony internetowej Aspose. Odwiedź [Tutaj](https://downloads.aspose.com/slides/java/) aby pobrać najnowszą wersję.

### Czy mogę dostosować listę wykluczonych czcionek?

Tak, możesz dostosować `fontNameExcludeList` tablicę umożliwiającą uwzględnienie lub wykluczenie konkretnych czcionek zgodnie z Twoimi wymaganiami.

### Czy ta metoda działa w przypadku starszych formatów PowerPoint, takich jak PPT?

Ten przykład kodu jest przeznaczony dla plików PPTX. Jeśli musisz przekonwertować starsze pliki PPT, może być konieczne wprowadzenie zmian w kodzie.

### W jaki sposób mogę jeszcze bardziej dostosować wyjście HTML?

Możesz zbadać `HtmlOptions` Klasa umożliwiająca dostosowanie różnych aspektów wyjścia HTML, takich jak rozmiar slajdu, jakość obrazu i inne.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}