---
"description": "Dowiedz się, jak programowo manipulować prezentacjami PowerPoint za pomocą Aspose.Slides dla Java. Opanuj obsługę Java PowerPoint dzięki samouczkom krok po kroku."
"linktitle": "Zapisywanie programu PowerPoint z domyślną zwykłą czcionką za pomocą języka Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zapisywanie programu PowerPoint z domyślną zwykłą czcionką za pomocą języka Java"
"url": "/pl/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zapisywanie programu PowerPoint z domyślną zwykłą czcionką za pomocą języka Java

## Wstęp
dziedzinie rozwoju Java tworzenie i manipulowanie prezentacjami PowerPoint programowo może znacznie zwiększyć wydajność i opcje dostosowywania. Aspose.Slides for Java to solidna biblioteka, która umożliwia programistom wydajne zarządzanie plikami PowerPoint, oferując kompleksowy zestaw funkcji od prostych modyfikacji po złożone prezentacje.
## Wymagania wstępne
Zanim zaczniesz korzystać z Aspose.Slides dla Java, upewnij się, że spełnione są następujące wymagania wstępne:
1. Java Development Kit (JDK): Aspose.Slides for Java do prawidłowego działania wymaga JDK w wersji 1.8 lub nowszej.
2. Aspose.Slides dla Java JAR: Pobierz najnowszą wersję Aspose.Slides dla Java ze strony [Tutaj](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Użyj IntelliJ IDEA, Eclipse lub innego wybranego środowiska IDE Java.
4. Podstawowa znajomość języka Java: konieczna jest znajomość podstaw języka programowania Java.

## Importuj pakiety
Aby rozpocząć korzystanie z Aspose.Slides dla Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Dzięki temu masz pewność, że masz dostęp do wszystkich klas i metod udostępnianych przez Aspose.Slides dla Java.
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java w środowisku IDE i dołącz plik JAR Aspose.Slides for Java do ścieżki kompilacji projektu.
## Krok 2: Zainicjuj obiekt prezentacji
Utwórz instancję `Presentation` obiekt, ładując istniejący plik PowerPoint (.pptx) z lokalnego katalogu.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Załaduj prezentację
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Zastępować `"Your Document Directory"` I `"Your Output Directory"` z rzeczywistymi ścieżkami plików.
## Krok 3: Zapisz prezentację z domyślnymi standardowymi czcionkami
Określ domyślną czcionkę standardową dla formatów wyjściowych (HTML i PDF) za pomocą `HtmlOptions` I `PdfOptions` odpowiednio.
```java
try {
    // Opcje zapisywania HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opcje zapisywania PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Upewnij się, że wymienisz `"Arial Black"` I `"Lucida Console"` z wybranymi przez Ciebie domyślnymi, regularnymi czcionkami.

## Wniosek
Wykonując te kroki, nauczyłeś się, jak skutecznie manipulować prezentacjami PowerPoint za pomocą Aspose.Slides for Java. Ta możliwość pozwala automatyzować zadania, dostosowywać prezentacje i ulepszać aplikacje Java za pomocą zaawansowanych funkcji obsługi PowerPoint.
## Najczęściej zadawane pytania
### Czy Aspose.Slides for Java działa ze starszymi wersjami JDK?
Do zapewnienia zgodności Aspose.Slides for Java wymagany jest JDK w wersji 1.8 lub nowszej.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
Możesz uzyskać tymczasową licencję od [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć bardziej szczegółową dokumentację Aspose.Slides dla Java?
Przeglądaj kompleksową dokumentację [Tutaj](https://reference.aspose.com/slides/java/).
### Czy istnieje wsparcie społeczności dla Aspose.Slides for Java?
Tak, możesz uzyskać wsparcie społeczności [Tutaj](https://forum.aspose.com/c/slides/11).
### Czy mogę wypróbować Aspose.Slides for Java za darmo?
Tak, pobierz bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}