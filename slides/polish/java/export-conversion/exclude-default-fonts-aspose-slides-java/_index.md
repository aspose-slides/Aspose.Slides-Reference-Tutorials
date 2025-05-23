---
"date": "2025-04-17"
"description": "Dowiedz się, jak wykluczyć domyślne czcionki podczas konwersji HTML za pomocą Aspose.Slides dla Java, zapewniając spójną typografię na wszystkich platformach."
"title": "Jak wykluczyć domyślne czcionki z konwersji HTML za pomocą Aspose.Slides dla Java"
"url": "/pl/java/export-conversion/exclude-default-fonts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak wykluczyć domyślne czcionki z konwersji HTML za pomocą Aspose.Slides dla Java
## Wstęp
Podczas konwersji prezentacji do HTML, utrzymanie niestandardowych czcionek jest kluczowe ze względu na domyślne ustawienia czcionek. Ten przewodnik pokazuje, jak Aspose.Slides dla Java może pomóc Ci wykluczyć te ustawienia domyślne i zapewnić spójną typografię na różnych platformach.
**Czego się nauczysz:**
- Konfigurowanie środowiska z Aspose.Slides dla Java
- Techniki wykluczania domyślnych czcionek podczas konwersji HTML
- Kluczowe opcje konfiguracji i ich wpływ na wynik
- Praktyczne zastosowania w scenariuszach z życia wziętych
Zanim przejdziemy do przewodnika wdrażania, na początek omówimy wymagania wstępne.
## Wymagania wstępne
Aby skutecznie skorzystać z tego samouczka, upewnij się, że posiadasz:
- **Aspose.Slides dla biblioteki Java**: Zainstaluj wersję 25.4 lub nowszą.
- **Zestaw narzędzi programistycznych Java (JDK)**:Ten przykład kodu dotyczy JDK 16. Upewnij się, że jest zainstalowany na Twoim komputerze.
- **Podstawowa wiedza z zakresu programowania w Javie**:Zakłada się znajomość składni języka Java i podstawowych pojęć programowania.
## Konfigurowanie Aspose.Slides dla Java
### Instalacja zależności
**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
**Stopień:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
Alternatywnie możesz pobrać bibliotekę bezpośrednio z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).
### Nabycie licencji
Zacznij od bezpłatnego okresu próbnego lub poproś o tymczasową licencję, aby odkryć wszystkie funkcje bez ograniczeń. Do długoterminowego użytkowania zaleca się zakup licencji.
**Podstawowa konfiguracja:**
Aby zainicjować Aspose.Slides w projekcie:
```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation("your-pptx-file-path");
        // Twój kod do manipulowania prezentacją
    }
}
```
## Przewodnik wdrażania
### Omówienie funkcji: Wykluczanie domyślnych czcionek z konwersji HTML
Funkcja ta umożliwia dostosowanie obsługi czcionek podczas konwersji pliku PowerPoint do formatu HTML, co zwiększa spójność i wzmacnia identyfikację marki.
#### Krok 1: Przygotuj swoje środowisko
Upewnij się, że Aspose.Slides jest poprawnie skonfigurowany zgodnie z powyższymi instrukcjami. Obejmuje to dodanie zależności lub pobranie pliku JAR bezpośrednio do projektu.
#### Krok 2: Załaduj prezentację
Załaduj prezentację za pomocą `Presentation` klasa:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/presentation.pptx";
try {
    Presentation pres = new Presentation(dataDir);
```
#### Krok 3: Zdefiniuj wykluczenia czcionek
Utwórz tablicę, aby określić czcionki, które chcesz wykluczyć. W tym przykładzie zaczynamy od pustej listy jako symbolu zastępczego:
```java
String[] fontNameExcludeList = {};
```
#### Krok 4: Zainicjuj niestandardowy kontroler HTML
Ten `LinkAllFontsHtmlController` Klasa ta służy do obsługi niestandardowych czcionek w trakcie procesu konwersji.
```java
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "YOUR_DOCUMENT_DIRECTORY");
```
#### Krok 5: Skonfiguruj opcje HTML
Skonfiguruj swoje `HtmlOptions` aby użyć formatera niestandardowego:
```java
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
```
#### Krok 6: Zapisz jako HTML
Na koniec zapisz przekonwertowaną prezentację w formacie HTML:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/pres.html", SaveFormat.Html, htmlOptionsEmbed);
} catch (Exception e) {
    e.printStackTrace();
}
```
**Wyjaśnienie:** Ten fragment kodu pokazuje, jak wykluczyć domyślne czcionki poprzez skonfigurowanie niestandardowego formatera podczas konwersji HTML.
## Zastosowania praktyczne
1. **Prezentacje internetowe**:Umieść prezentacje na stronach internetowych firm, zachowując spójność marki.
2. **Przenośność dokumentów**: Upewnij się, że dokumenty wyglądają tak samo na różnych urządzeniach i platformach.
3. **Integracja z CMS**:Bezproblemowa integracja z systemami zarządzania treścią, w których niestandardowe czcionki są niezbędne.
## Rozważania dotyczące wydajności
- **Optymalizacja wykorzystania pamięci**:Użyj funkcji zarządzania pamięcią Aspose.Slides, aby wydajnie obsługiwać duże prezentacje.
- **Zarządzanie zasobami**:Zamykaj strumienie prawidłowo po operacjach, aby zwolnić zasoby.
- **Najlepsze praktyki**: Regularnie aktualizuj wersję swojej biblioteki, aby zwiększyć wydajność i usunąć błędy.
## Wniosek
Nauczyłeś się, jak wykluczać domyślne czcionki podczas konwersji HTML za pomocą Aspose.Slides dla Java. Ta możliwość zwiększa spójność prezentacji na różnych platformach, co jest kluczowe dla brandingu i profesjonalnej dokumentacji.
Aby jeszcze bardziej rozwinąć swoje umiejętności, poznaj inne funkcje pakietu Aspose.Slides lub zintegruj tę funkcjonalność z większymi projektami.
**Następne kroki:**
Eksperymentuj z różnymi wykluczeniami czcionek i zobacz, jak wpływają one na ostateczny wynik HTML. Rozważ zintegrowanie tych technik z automatycznymi przepływami pracy, aby usprawnić procesy konwersji dokumentów.
## Sekcja FAQ
1. **Czym jest Aspose.Slides dla Java?**
   - Potężna biblioteka do tworzenia prezentacji w aplikacjach Java.
2. **Jak uzyskać licencję na użytkowanie długoterminowe?**
   - Odwiedź [strona zakupu](https://purchase.aspose.com/buy) aby kupić lub dowiedzieć się o opcjach licencjonowania.
3. **Czy mogę wykluczyć kilka czcionek jednocześnie?**
   - Tak, dodaj wszystkie nazwy czcionek, które chcesz wykluczyć w `fontNameExcludeList` szyk.
4. **Co powinienem zrobić, jeśli w moim pliku wyjściowym HTML brakuje czcionek?**
   - Upewnij się, że Twój niestandardowy kontroler HTML jest poprawnie skonfigurowany i ścieżki są ustawione poprawnie.
5. **Czy wykluczenie czcionek ma wpływ na wydajność?**
   - Duże biblioteki czcionek mogą mieć wpływ na wydajność; w razie potrzeby należy dokonać optymalizacji za pomocą funkcji zarządzania pamięcią pakietu Aspose.
## Zasoby
- [Dokumentacja](https://reference.aspose.com/slides/java/)
- [Pobierz bibliotekę](https://releases.aspose.com/slides/java/)
- [Kup licencję](https://purchase.aspose.com/buy)
- [Bezpłatna wersja próbna](https://releases.aspose.com/slides/java/)
- [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/)
- [Forum wsparcia](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}