---
"description": "Dowiedz się, jak ustawić czcionki zapasowe w programie Java PowerPoint przy użyciu pakietu Aspose.Slides for Java, aby zapewnić spójne wyświetlanie tekstu."
"linktitle": "Ustaw czcionkę zapasową w programie Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw czcionkę zapasową w programie Java PowerPoint"
"url": "/pl/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw czcionkę zapasową w programie Java PowerPoint

## Wstęp
W tym samouczku zagłębimy się w zawiłości ustawiania zapasowych czcionek w prezentacjach Java PowerPoint przy użyciu Aspose.Slides for Java. Zapasowe czcionki są kluczowe dla zapewnienia, że tekst w prezentacjach będzie wyświetlany poprawnie na różnych urządzeniach i w różnych systemach operacyjnych, nawet gdy wymagane czcionki nie są dostępne.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość języka programowania Java.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Najpierw należy uwzględnić niezbędne pakiety Aspose.Slides for Java w swojej klasie Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Krok 1: Zainicjuj reguły zapasowe czcionek
Aby ustawić czcionki zapasowe, musisz zdefiniować reguły określające zakresy Unicode i odpowiadające im czcionki zapasowe. Oto, jak możesz zainicjować te reguły:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Krok 2: Zastosuj reguły zapasowe czcionek
Następnie zastosuj te reguły do prezentacji lub slajdu, w którym należy ustawić zapasowe czcionki. Poniżej znajduje się przykład zastosowania tych reguł do slajdu w prezentacji programu PowerPoint:
```java
// Zakładając, że slajd jest obiektem slajdu
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Wniosek
Ustawianie zapasowych czcionek w prezentacjach Java PowerPoint przy użyciu Aspose.Slides for Java jest niezbędne do zapewnienia spójnego wyświetlania tekstu w różnych środowiskach. Definiując reguły zapasowe, jak pokazano w tym samouczku, możesz poradzić sobie z sytuacjami, w których określone czcionki są niedostępne, zachowując integralność prezentacji.

## Najczęściej zadawane pytania
### Jakie są czcionki zapasowe w prezentacjach programu PowerPoint?
Zapasowe czcionki zapewniają prawidłowe wyświetlanie tekstu poprzez zastępowanie dostępnych czcionek tymi, które nie są zainstalowane.
### Jak mogę pobrać Aspose.Slides dla Java?
Możesz pobrać Aspose.Slides dla Java ze strony [Tutaj](https://releases.aspose.com/slides/java/).
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi środowiskami IDE Java?
Tak, Aspose.Slides for Java jest kompatybilny z popularnymi środowiskami IDE Java, takimi jak IntelliJ IDEA i Eclipse.
### Czy mogę otrzymać tymczasową licencję na produkty Aspose?
Tak, tymczasowe licencje na produkty Aspose można uzyskać od [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć pomoc techniczną dotyczącą Aspose.Slides dla Java?
Aby uzyskać pomoc dotyczącą Aspose.Slides dla Java, odwiedź stronę [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}