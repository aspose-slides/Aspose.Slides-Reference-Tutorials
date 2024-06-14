---
title: Określ domyślny język tekstu w programie Java PowerPoint
linktitle: Określ domyślny język tekstu w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak określić domyślny język tekstu w programie Java PowerPoint przy użyciu Aspose.Slides dla języka Java. Idealny dla programistów chcących programowo lokalizować tekst.
type: docs
weight: 21
url: /pl/java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---
## Wstęp
W dziedzinie tworzenia aplikacji Java programowe zarządzanie prezentacjami PowerPoint i manipulowanie nimi jest powszechnym wymogiem. Aspose.Slides for Java oferuje solidny zestaw funkcji, które umożliwiają programistom płynne tworzenie, modyfikowanie i ulepszanie prezentacji programu PowerPoint za pomocą kodu Java. Ten samouczek ma na celu poprowadzić Cię przez podstawowe kroki określania domyślnego języka tekstu w prezentacji Java PowerPoint przy użyciu Aspose.Slides.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Konfiguracja zintegrowanego środowiska programistycznego (IDE), takiego jak IntelliJ IDEA lub Eclipse.
-  Zainstalowana biblioteka Aspose.Slides dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
-  Dostęp do dokumentacji Aspose.Slides for Java, którą można znaleźć[Tutaj](https://reference.aspose.com/slides/java/).

## Importuj pakiety
Zanim zaczniesz kodować, pamiętaj o zaimportowaniu niezbędnych klas Aspose.Slides do pliku Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Skonfiguruj opcje ładowania
pierwszej kolejności skonfiguruj opcje ładowania prezentacji, określając domyślny język tekstu (`en-US` w tym przypadku).
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setDefaultTextLanguage("en-US");
```
## Krok 2: Załaduj prezentację
 Utwórz instancję a`Presentation` obiekt, korzystając ze skonfigurowanych opcji ładowania, aby załadować istniejącą prezentację programu PowerPoint lub utworzyć nową.
```java
Presentation pres = new Presentation(loadOptions);
```
## Krok 3: Dodaj kształt z tekstem
Dodaj kształt prostokąta do pierwszego slajdu prezentacji i ustaw jego zawartość tekstową.
```java
IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
shp.getTextFrame().setText("New Text");
```
## Krok 4: Sprawdź język fragmentów tekstu
Pobierz i sprawdź ustawienia językowe fragmentów tekstu w dodanym kształcie.
```java
PortionFormat portionFormat = shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
System.out.println(portionFormat.getLanguageId());
```
## Krok 5: Pozbądź się obiektu prezentacji
 Zapewnij właściwą utylizację`Presentation` sprzeciwiać się zwolnieniu zasobów po ich użyciu.
```java
finally {
    if (pres != null) pres.dispose();
}
```

## Wniosek
W tym samouczku nauczyłeś się wykorzystywać Aspose.Slides dla języka Java do programowego określania domyślnego języka tekstu w prezentacji programu PowerPoint. Ta funkcja ma kluczowe znaczenie dla zapewnienia spójnych ustawień językowych elementów tekstowych w prezentacjach, zwiększenia czytelności i wysiłków związanych z lokalizacją.
## Często zadawane pytania
### Czy mogę zmienić domyślny język tekstu na inny, na przykład francuski lub hiszpański?
Tak, możesz określić dowolny obsługiwany kod języka podczas ustawiania domyślnego języka tekstu za pomocą Aspose.Slides dla Java.
### Czy Aspose.Slides for Java nadaje się do aplikacji na poziomie przedsiębiorstwa?
Absolutnie. Aspose.Slides for Java został zaprojektowany z myślą o skalowalności i wydajności, dzięki czemu idealnie nadaje się do środowisk korporacyjnych.
### Gdzie mogę znaleźć więcej przykładów i zasobów dotyczących Aspose.Slides dla Java?
 Możesz zapoznać się z obszerną dokumentacją i dodatkowymi przykładami na stronie[Strona dokumentacji Aspose.Slides for Java](https://reference.aspose.com/slides/java/).
### Czy Aspose.Slides for Java obsługuje integrację z usługami w chmurze?
Tak, Aspose.Slides for Java udostępnia interfejsy API obsługujące integrację z popularnymi platformami chmurowymi.
### Czy mogę przetestować Aspose.Slides dla Java przed zakupem?
 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Slides dla Java od[Tutaj](https://releases.aspose.com/).