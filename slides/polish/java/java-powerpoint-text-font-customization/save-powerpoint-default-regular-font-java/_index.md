---
title: Zapisz program PowerPoint z domyślną czcionką zwykłą przy użyciu języka Java
linktitle: Zapisz program PowerPoint z domyślną czcionką zwykłą przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak programowo manipulować prezentacjami programu PowerPoint przy użyciu Aspose.Slides dla Java. Opanuj obsługę języka Java PowerPoint dzięki samouczkom krok po kroku.
weight: 12
url: /pl/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W dziedzinie programowania w języku Java programowe tworzenie prezentacji programu PowerPoint i manipulowanie nimi może znacznie zwiększyć produktywność i możliwości dostosowywania. Aspose.Slides dla Java to solidna biblioteka, która umożliwia programistom efektywną obsługę plików programu PowerPoint, oferując kompleksowy zestaw funkcji, od prostych modyfikacji po złożone prezentacje.
## Warunki wstępne
Zanim zaczniesz korzystać z Aspose.Slides dla Java, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Aspose.Slides for Java wymaga do prawidłowego działania pakietu JDK 1.8 lub nowszego.
2. Aspose.Slides dla Java JAR: Pobierz najnowszą wersję Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Użyj IntelliJ IDEA, Eclipse lub innego wybranego środowiska Java IDE.
4. Podstawowa znajomość języka Java: Konieczna jest znajomość podstaw języka programowania Java.

## Importuj pakiety
Aby rozpocząć korzystanie z Aspose.Slides dla Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Dzięki temu masz dostęp do wszystkich klas i metod udostępnianych przez Aspose.Slides dla Java.
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java w swoim IDE i dołącz plik JAR Aspose.Slides for Java do ścieżki kompilacji projektu.
## Krok 2: Zainicjuj obiekt prezentacji
 Utwórz instancję a`Presentation` obiekt, ładując istniejący plik programu PowerPoint (.pptx) z katalogu lokalnego.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Załaduj prezentację
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Zastępować`"Your Document Directory"` I`"Your Output Directory"` z rzeczywistymi ścieżkami plików.
## Krok 3: Zapisz prezentację z domyślnymi zwykłymi czcionkami
 Określ domyślną zwykłą czcionkę dla używanych formatów wyjściowych (HTML i PDF).`HtmlOptions` I`PdfOptions` odpowiednio.
```java
try {
    // Opcje zapisywania HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opcje zapisywania plików PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Pamiętaj o wymianie`"Arial Black"` I`"Lucida Console"` z żądanymi domyślnymi zwykłymi czcionkami.

## Wniosek
Wykonując poniższe kroki, nauczyłeś się efektywnie manipulować prezentacjami programu PowerPoint przy użyciu Aspose.Slides for Java. Ta funkcja umożliwia automatyzację zadań, dostosowywanie prezentacji i ulepszanie aplikacji Java dzięki zaawansowanym funkcjom obsługi programu PowerPoint.
## Często zadawane pytania
### Czy Aspose.Slides for Java może współpracować ze starszymi wersjami JDK?
Aspose.Slides dla Java wymaga JDK 1.8 lub nowszego dla kompatybilności.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
 Licencję tymczasową można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć bardziej szczegółową dokumentację dotyczącą Aspose.Slides dla Java?
 Zapoznaj się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/slides/java/).
### Czy dostępna jest pomoc społeczności dla Aspose.Slides dla Java?
 Tak, możesz uzyskać wsparcie społeczne[Tutaj](https://forum.aspose.com/c/slides/11).
### Czy mogę bezpłatnie wypróbować Aspose.Slides dla Java?
 Tak, pobierz bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
