---
"description": "Dowiedz się, jak renderować tekst za pomocą czcionek zapasowych w prezentacjach PowerPoint w języku Java przy użyciu Aspose.Slides. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać bezproblemową implementację."
"linktitle": "Renderowanie z czcionką zapasową w programie Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Renderowanie z czcionką zapasową w programie Java PowerPoint"
"url": "/pl/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Renderowanie z czcionką zapasową w programie Java PowerPoint

## Wstęp
Tworzenie i manipulowanie prezentacjami PowerPoint w Javie może być trudne, ale dzięki Aspose.Slides możesz to robić wydajnie. Jedną z kluczowych funkcji jest możliwość renderowania tekstu za pomocą czcionek zapasowych. Ten artykuł zawiera szczegółowy przewodnik krok po kroku, jak wdrożyć czcionki zapasowe w slajdach PowerPoint za pomocą Aspose.Slides dla Javy.
## Wymagania wstępne
Zanim przejdziemy do implementacji, upewnijmy się, że masz wszystko, czego potrzebujesz:
1. Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany JDK.
2. Aspose.Slides dla Java: Możesz pobrać ze strony [Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): IDE, takie jak IntelliJ IDEA lub Eclipse, usprawni proces tworzenia oprogramowania.
4. Zależności: uwzględnij Aspose.Slides w zależnościach swojego projektu.
## Importuj pakiety
Najpierw musimy zaimportować niezbędne pakiety do naszego programu Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Podzielmy ten proces na łatwiejsze do opanowania kroki.
## Krok 1: Skonfiguruj swój projekt
Przed napisaniem jakiegokolwiek kodu upewnij się, że projekt jest poprawnie skonfigurowany. Obejmuje to dodanie biblioteki Aspose.Slides do projektu. Możesz to zrobić, pobierając bibliotekę z [Aspose.Slides dla Java](https://releases.aspose.com/slides/java/) i dodając go do ścieżki kompilacji.
## Krok 2: Zainicjuj reguły zapasowe czcionek
Musisz utworzyć instancję `IFontFallBackRulesCollection` i dodaj do niej reguły. Reguły te definiują zapasowe czcionki dla określonych zakresów Unicode.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz nową instancję zbioru reguł
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Utwórz szereg reguł
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Krok 3: Modyfikuj reguły awaryjne
W tym kroku zmodyfikujemy reguły zapasowe poprzez usunięcie istniejących czcionek zapasowych i zaktualizowanie reguł dla określonych zakresów Unicode.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Próba usunięcia czcionki FallBack „Tahoma” z załadowanych reguł
    fallBackRule.remove("Tahoma");
    // Aktualizuj reguły dla określonego zakresu
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Usuń wszystkie istniejące reguły z listy
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Krok 4: Załaduj prezentację
Załaduj prezentację PowerPoint, którą chcesz zmodyfikować.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Krok 5: Przypisz reguły zapasowe do prezentacji
Przypisz przygotowane reguły zapasowe do menedżera czcionek prezentacji.
```java
try {
    // Przypisanie przygotowanej listy reguł do wykorzystania
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
Na koniec zapisz swoją pracę i przetestuj implementację, aby upewnić się, że wszystko działa zgodnie z oczekiwaniami. Jeśli napotkasz jakiekolwiek problemy, sprawdź dwukrotnie swoją konfigurację i upewnij się, że wszystkie zależności zostały poprawnie dodane.
## Wniosek
Postępując zgodnie z tym przewodnikiem, możesz efektywnie renderować tekst za pomocą czcionek zapasowych w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Ten proces zapewnia, że Twoje prezentacje zachowują spójne formatowanie, nawet jeśli podstawowe czcionki są niedostępne. Miłego kodowania!
## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to biblioteka umożliwiająca programistom tworzenie, modyfikowanie i renderowanie prezentacji PowerPoint w aplikacjach Java.
### Jak dodać Aspose.Slides do mojego projektu?
Bibliotekę można pobrać ze strony [Strona pobierania Aspose.Slides](https://releases.aspose.com/slides/java/) i dodaj go do ścieżki kompilacji swojego projektu.
### Czym są czcionki zapasowe?
Czcionki zapasowe to alternatywne czcionki używane w przypadku, gdy określona czcionka jest niedostępna lub nie obsługuje niektórych znaków.
### Czy mogę używać wielu reguł zapasowych?
Tak, można dodać wiele reguł zapasowych obsługujących różne zakresy Unicode i czcionki.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides?
Możesz uzyskać wsparcie od [Forum wsparcia Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}