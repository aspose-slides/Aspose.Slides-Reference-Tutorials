---
title: Osadzaj czcionki w formacie HTML za pomocą Aspose.Slides dla Java
linktitle: Osadzaj czcionki w formacie HTML za pomocą Aspose.Slides dla Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak osadzać czcionki w formacie HTML za pomocą Aspose.Slides dla Java, aby zapewnić spójną typografię na różnych platformach i urządzeniach.
weight: 13
url: /pl/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Aspose.Slides for Java to potężne narzędzie dla programistów Java, którzy chcą programowo manipulować prezentacjami programu PowerPoint. W tym samouczku zagłębimy się w proces osadzania czcionek w formacie HTML za pomocą Aspose.Slides dla Java. Osadzając czcionki, masz pewność, że Twoje prezentacje zachowają zamierzony wygląd na różnych platformach i urządzeniach, nawet jeśli wymagane czcionki nie są zainstalowane lokalnie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[strona pobierania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko IDE do programowania w języku Java, takie jak IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby rozpocząć osadzanie czcionek w formacie HTML przy użyciu Aspose.Slides for Java.
```java
import com.aspose.slides.*;
```
## Krok 1: Zdefiniuj katalogi dokumentów i wyjściowe
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 Upewnij się, że wymieniłeś`"Your Document Directory"` I`"Your Output Directory"` ze ścieżkami odpowiednio do wejściowej prezentacji programu PowerPoint i żądanego katalogu wyjściowego.
## Krok 2: Załaduj prezentację
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Ten krok ładuje prezentację programu PowerPoint do pamięci, umożliwiając wykonanie na niej różnych operacji.
## Krok 3: Wyklucz domyślne czcionki
```java
String[] fontNameExcludeList = { "Arial" };
```
Określ czcionki, które chcesz wykluczyć z osadzania. W tym przykładzie wykluczamy Arial.
## Krok 4: Osadź czcionki w formacie HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 Na tym etapie tworzymy instancję`EmbedAllFontsHtmlController` aby osadzić wszystkie czcionki z wyjątkiem tych określonych na liście wykluczeń. Następnie definiujemy`HtmlOptions` ustaw niestandardowy formater HTML, aby osadzić czcionki. Na koniec zapisujemy prezentację w formacie HTML z osadzonymi czcionkami.

## Wniosek
W tym samouczku omówiliśmy, jak osadzać czcionki w formacie HTML za pomocą Aspose.Slides dla Java. Wykonując podane kroki, możesz mieć pewność, że Twoje prezentacje zachowują spójną typografię na różnych platformach i urządzeniach, poprawiając ogólne wrażenia z oglądania.
## Często zadawane pytania
### Czy mogę osadzić określone czcionki zamiast je wykluczać?
 Tak, możesz określić czcionki, które chcesz osadzić, modyfikując plik`fontNameExcludeList` odpowiednio tablicę.
### Czy Aspose.Slides for Java obsługuje osadzanie czcionek w innych formatach niż HTML?
Tak, Aspose.Slides obsługuje osadzanie czcionek w różnych formatach wyjściowych, w tym PDF i obrazy.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dotyczącą Aspose.Slides for Java?
 Możesz odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania wsparcia społeczności lub skontaktuj się z obsługą Aspose w celu uzyskania profesjonalnej pomocy.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla Java?
Tak, możesz nabyć tymczasową licencję od[strona zakupu](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
