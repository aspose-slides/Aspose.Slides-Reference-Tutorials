---
"description": "Dowiedz się, jak dodawać punkty akapitów w slajdach programu PowerPoint za pomocą Aspose.Slides for Java. Ten samouczek przeprowadzi Cię krok po kroku za pomocą przykładów kodu."
"linktitle": "Dodawanie punktów akapitu w programie PowerPoint za pomocą języka Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodawanie punktów akapitu w programie PowerPoint za pomocą języka Java"
"url": "/pl/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie punktów akapitu w programie PowerPoint za pomocą języka Java

## Wstęp
Dodawanie punktów akapitu poprawia czytelność i strukturę prezentacji PowerPoint. Aspose.Slides for Java zapewnia solidne narzędzia do manipulowania prezentacjami programowo, w tym możliwość formatowania tekstu za pomocą różnych stylów punktów. W tym samouczku dowiesz się, jak integrować punkty wypunktowania ze slajdami PowerPoint za pomocą kodu Java, wykorzystując Aspose.Slides.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
- Podstawowa znajomość programowania w Javie.
- JDK (Java Development Kit) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety Aspose.Slides do swojego projektu Java:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java i dodaj bibliotekę Aspose.Slides for Java do ścieżki kompilacji projektu.
## Krok 2: Zainicjuj prezentację
Zainicjuj obiekt prezentacji (`Presentation`) aby rozpocząć pracę ze slajdami.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie instancji prezentacji
Presentation pres = new Presentation();
```
## Krok 3: Uzyskaj dostęp do slajdu i ramki tekstowej
Uzyskaj dostęp do slajdu (`ISlide`) i jego ramka tekstowa (`ITextFrame`) w miejscu, w którym chcesz dodać punkty.
```java
// Dostęp do pierwszego slajdu
ISlide slide = pres.getSlides().get_Item(0);
// Dodawanie i uzyskiwanie dostępu do Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Dostęp do ramki tekstowej utworzonego kształtu automatycznego
ITextFrame txtFrm = aShp.getTextFrame();
```
## Krok 4: Tworzenie i formatowanie akapitów z punktami
Utwórz akapity (`Paragraph`) i ustaw ich style punktowania, wcięcia i tekst.
```java
// Tworzenie akapitu
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Tworzenie kolejnego akapitu
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację w pliku programu PowerPoint (`PPTX`).
```java
// Pisanie prezentacji jako pliku PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Oczyść zasoby
Usuń obiekt prezentacji, aby zwolnić zasoby.
```java
// Usuń obiekt prezentacji
if (pres != null) {
    pres.dispose();
}
```

## Wniosek
Dodawanie punktów akapitu w programie PowerPoint przy użyciu Aspose.Slides dla języka Java jest proste dzięki podanym przykładom kodu. Dostosuj style i formatowanie punktów, aby bezproblemowo dopasować je do potrzeb prezentacji.

## Często zadawane pytania
### Czy mogę dostosować kolory punktów?
Tak, możesz ustawić niestandardowe kolory punktów za pomocą interfejsu API Aspose.Slides.
### Jak dodać zagnieżdżone punkty?
Zagnieżdżanie punktorów polega na dodawaniu akapitów w akapitach i odpowiednim dostosowywaniu wcięć.
### Czy mogę utworzyć różne style punktów dla różnych slajdów?
Tak, możesz programowo stosować unikalne style punktowania do różnych slajdów.
### Czy Aspose.Slides jest kompatybilny z Java 11?
Tak, Aspose.Slides obsługuje Java 11 i nowsze wersje.
### Gdzie mogę znaleźć więcej przykładów i dokumentacji?
Odwiedzać [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) aby uzyskać kompleksowe przewodniki i przykłady.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}