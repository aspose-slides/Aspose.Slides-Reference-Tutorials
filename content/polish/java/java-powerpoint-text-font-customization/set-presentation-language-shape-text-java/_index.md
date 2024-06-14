---
title: Ustaw język prezentacji i kształt tekstu w Javie
linktitle: Ustaw język prezentacji i kształt tekstu w Javie
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zautomatyzować prezentacje programu PowerPoint za pomocą Aspose.Slides dla Java. Programowo z łatwością twórz, modyfikuj i ulepszaj slajdy.
type: docs
weight: 19
url: /pl/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---
## Wstęp
Programowe tworzenie prezentacji programu PowerPoint w języku Java i manipulowanie nimi może usprawnić automatyzację przepływu pracy i zwiększyć produktywność. Aspose.Slides dla Java zapewnia solidny zestaw narzędzi do wydajnej realizacji tych zadań. Ten samouczek poprowadzi Cię przez niezbędne kroki, aby ustawić język prezentacji i kształtować tekst za pomocą Aspose.Slides dla Java.
## Warunki wstępne
Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:
- Zainstalowany zestaw Java Development Kit (JDK).
-  Biblioteka Aspose.Slides for Java, z której możesz pobrać[Tutaj](https://releases.aspose.com/slides/java/)
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse, skonfigurowane w systemie
- Podstawowa znajomość języka programowania Java
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety Aspose.Slides do pliku Java:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Krok 1: Utwórz obiekt prezentacji
 Zacznij od inicjalizacji a`Presentation` obiekt:
```java
Presentation pres = new Presentation();
```
Spowoduje to utworzenie nowej prezentacji programu PowerPoint.
## Krok 2: Dodaj i skonfiguruj Autokształt
Następnie dodaj Autokształt do pierwszego slajdu i skonfiguruj jego właściwości:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Tutaj dodajemy prostokątny Autokształt o współrzędnych (50, 50) o wymiarach 200x50 pikseli.
## Krok 3: Ustaw tekst i język
Ustaw treść tekstu i określ język sprawdzania pisowni:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 Zastępować`"Text to apply spellcheck language"` z wybranym tekstem. Identyfikator języka`"en-EN"`określa język angielski (Stany Zjednoczone).
## Krok 4: Zapisz prezentację
Zapisz zmodyfikowaną prezentację w określonym katalogu wyjściowym:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 Pamiętaj o wymianie`"Your Output Directory"` z rzeczywistą ścieżką katalogu, w którym chcesz zapisać plik.
## Krok 5: Pozbądź się zasobów
 Prawidłowo pozbądź się`Presentation` sprzeciw do zwolnienia zasobów:
```java
pres.dispose();
```
Ten krok jest kluczowy, aby uniknąć wycieków pamięci.

## Wniosek
Podsumowując, Aspose.Slides dla Java upraszcza proces programowego tworzenia prezentacji PowerPoint i manipulowania nimi. Wykonując poniższe kroki, możesz efektywnie ustawić język prezentacji i skonfigurować właściwości tekstu zgodnie ze swoimi wymaganiami.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides for Java do tworzenia prezentacji PowerPoint od podstaw?
Tak, Aspose.Slides zapewnia kompleksowe interfejsy API do tworzenia prezentacji całkowicie programowo.
### Jak mogę zastosować różne czcionki do tekstu na slajdach programu PowerPoint przy użyciu Aspose.Slides dla Java?
 Możesz ustawić właściwości czcionki za pomocą`IPortionFormat` obiekty powiązane z fragmentami tekstu.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Dostępna jest szczegółowa dokumentacja[Tutaj](https://reference.aspose.com/slides/java/).
### Jakie opcje wsparcia są dostępne dla Aspose.Slides dla Java?
 Możesz odwiedzić forum Aspose.Slides[Tutaj](https://forum.aspose.com/c/slides/11) za wsparcie społeczności.