---
title: Renderuj z czcionką zastępczą w programie Java PowerPoint
linktitle: Renderuj z czcionką zastępczą w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak renderować tekst przy użyciu czcionek zastępczych w prezentacjach Java PowerPoint przy użyciu Aspose.Slides. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby zapewnić bezproblemową implementację.
weight: 13
url: /pl/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Tworzenie prezentacji PowerPoint i manipulowanie nimi w Javie może być wyzwaniem, ale dzięki Aspose.Slides możesz to zrobić efektywnie. Jedną z kluczowych funkcji jest możliwość renderowania tekstu przy użyciu czcionek zastępczych. Ten artykuł zawiera szczegółowy przewodnik krok po kroku dotyczący implementowania czcionek zastępczych na slajdach programu PowerPoint przy użyciu Aspose.Slides for Java.
## Warunki wstępne
Zanim przejdziemy do wdrożenia, upewnijmy się, że masz wszystko, czego potrzebujesz:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Slides dla Java: Możesz pobrać go z[Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): IDE takie jak IntelliJ IDEA lub Eclipse sprawi, że proces programowania stanie się płynniejszy.
4. Zależności: Dołącz Aspose.Slides do zależności swojego projektu.
## Importuj pakiety
Najpierw musimy zaimportować niezbędne pakiety do naszego programu Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Podzielmy proces na łatwe do wykonania etapy.
## Krok 1: Skonfiguruj swój projekt
 Przed napisaniem jakiegokolwiek kodu upewnij się, że projekt jest poprawnie skonfigurowany. Obejmuje to dodanie biblioteki Aspose.Slides do projektu. Można to zrobić, pobierając bibliotekę ze strony[Aspose.Slides dla Java](https://releases.aspose.com/slides/java/) i dodanie go do ścieżki kompilacji.
## Krok 2: Zainicjuj reguły zastępcze czcionek
 Musisz utworzyć instancję`IFontFallBackRulesCollection` class i dodaj do niej reguły. Te reguły definiują zastępcze czcionki dla określonych zakresów Unicode.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz nową instancję kolekcji reguł
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Utwórz kilka reguł
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Krok 3: Zmodyfikuj reguły zastępcze
Na tym etapie zmodyfikujemy reguły zastępcze, usuwając istniejące czcionki zastępcze i aktualizując reguły dla określonych zakresów Unicode.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Próbuję usunąć czcionkę FallBack „Tahoma” z załadowanych reguł
    fallBackRule.remove("Tahoma");
    // Aktualizuj reguły dla określonego zakresu
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Usuń wszystkie istniejące reguły z listy
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Krok 4: Załaduj prezentację
Załaduj prezentację programu PowerPoint, którą chcesz zmodyfikować.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Krok 5: Przypisz reguły zastępcze do prezentacji
Przypisz przygotowane reguły awaryjne do menedżera czcionek prezentacji.
```java
try {
    // Przypisanie przygotowanej listy reguł do użycia
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Renderowanie miniatury przy użyciu zainicjowanej kolekcji reguł i zapisywanie jej w formacie PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Krok 6: Zapisz i przetestuj
Na koniec zapisz swoją pracę i przetestuj implementację, aby upewnić się, że wszystko działa zgodnie z oczekiwaniami. Jeśli napotkasz jakiekolwiek problemy, sprawdź dokładnie swoją konfigurację i upewnij się, że wszystkie zależności zostały poprawnie dodane.
## Wniosek
Postępując zgodnie z tym przewodnikiem, możesz efektywnie renderować tekst przy użyciu czcionek zastępczych w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Ten proces zapewnia zachowanie spójnego formatowania prezentacji, nawet jeśli podstawowe czcionki są niedostępne. Miłego kodowania!
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i renderowanie prezentacji programu PowerPoint w aplikacjach Java.
### Jak dodać Aspose.Slides do mojego projektu?
 Bibliotekę można pobrać ze strony[Strona pobierania Aspose.Slides](https://releases.aspose.com/slides/java/) i dodaj go do ścieżki kompilacji projektu.
### Co to są czcionki zastępcze?
Czcionki zastępcze to czcionki alternatywne używane, gdy określona czcionka nie jest dostępna lub nie obsługuje niektórych znaków.
### Czy mogę używać wielu reguł awaryjnych?
Tak, możesz dodać wiele reguł zastępczych, aby obsługiwać różne zakresy i czcionki Unicode.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides?
 Możesz uzyskać wsparcie od[Forum wsparcia Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
