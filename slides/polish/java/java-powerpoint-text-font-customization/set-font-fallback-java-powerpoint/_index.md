---
title: Ustaw funkcję zastępowania czcionek w programie Java PowerPoint
linktitle: Ustaw funkcję zastępowania czcionek w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić zastępcze czcionki w Java PowerPoint przy użyciu Aspose.Slides dla Java, aby zapewnić spójne wyświetlanie tekstu.
weight: 16
url: /pl/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku zagłębimy się w zawiłości ustawiania zastępczych czcionek w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Zastępcze czcionki mają kluczowe znaczenie dla zapewnienia prawidłowego wyświetlania tekstu w prezentacjach na różnych urządzeniach i systemach operacyjnych, nawet jeśli wymagane czcionki nie są dostępne.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość języka programowania Java.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Najpierw dołącz niezbędne pakiety Aspose.Slides for Java do swojej klasy Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Krok 1: Zainicjuj reguły zastępcze czcionek
Aby ustawić czcionki zastępcze, należy zdefiniować reguły określające zakresy Unicode i odpowiadające im czcionki zastępcze. Oto jak możesz zainicjować te reguły:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Krok 2: Zastosuj reguły zastępcze czcionek
Następnie zastosuj te reguły do prezentacji lub slajdu, w którym należy ustawić czcionki zastępcze. Poniżej znajduje się przykład zastosowania tych reguł do slajdu w prezentacji PowerPoint:
```java
// Zakładając, że slajd jest obiektem Slide
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Wniosek
Ustawianie zastępczych czcionek w prezentacjach Java PowerPoint przy użyciu Aspose.Slides for Java jest niezbędne do zapewnienia spójnego wyświetlania tekstu w różnych środowiskach. Definiując reguły awaryjne, jak pokazano w tym samouczku, możesz poradzić sobie z sytuacjami, w których określone czcionki są niedostępne, zachowując integralność prezentacji.

## Często zadawane pytania
### Jakie są zastępcze czcionki w prezentacjach programu PowerPoint?
Zastępcze czcionki zapewniają prawidłowe wyświetlanie tekstu, zastępując dostępne czcionki tymi, które nie są zainstalowane.
### Jak mogę pobrać Aspose.Slides dla Java?
 Możesz pobrać Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi środowiskami IDE Java?
Tak, Aspose.Slides for Java jest kompatybilny z popularnymi środowiskami IDE Java, takimi jak IntelliJ IDEA i Eclipse.
### Czy mogę uzyskać tymczasowe licencje na produkty Aspose?
Tak, można uzyskać tymczasowe licencje na produkty Aspose[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć pomoc dotyczącą Aspose.Slides dla Java?
 Aby uzyskać pomoc związaną z Aspose.Slides dla Java, odwiedź stronę[forum dyskusyjne](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
