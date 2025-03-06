---
title: Dodaj punktory akapitów w programie PowerPoint przy użyciu języka Java
linktitle: Dodaj punktory akapitów w programie PowerPoint przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać punktory akapitów na slajdach programu PowerPoint przy użyciu Aspose.Slides dla Java. Ten samouczek przeprowadzi Cię krok po kroku za pomocą przykładów kodu.
weight: 15
url: /pl/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Dodanie punktorów akapitów poprawia czytelność i strukturę prezentacji programu PowerPoint. Aspose.Slides dla Java zapewnia solidne narzędzia do programowego manipulowania prezentacjami, w tym możliwość formatowania tekstu przy użyciu różnych stylów punktorów. W tym samouczku dowiesz się, jak zintegrować wypunktowania ze slajdami programu PowerPoint przy użyciu kodu Java, wykorzystując Aspose.Slides.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Podstawowa znajomość programowania w języku Java.
- JDK (Java Development Kit) zainstalowany w twoim systemie.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

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
Zainicjuj obiekt prezentacji (`Presentation`), aby rozpocząć pracę ze slajdami.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Tworzenie instancji prezentacji
Presentation pres = new Presentation();
```
## Krok 3: Uzyskaj dostęp do slajdu i ramki tekstowej
Uzyskaj dostęp do slajdu (`ISlide`i jego ramka tekstowa (`ITextFrame`), w którym chcesz dodać punktory.
```java
// Dostęp do pierwszego slajdu
ISlide slide = pres.getSlides().get_Item(0);
// Dodawanie i uzyskiwanie dostępu do Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Dostęp do ramki tekstowej utworzonego autokształtu
ITextFrame txtFrm = aShp.getTextFrame();
```
## Krok 4: Utwórz i sformatuj akapity za pomocą punktorów
Utwórz akapity (`Paragraph`) i ustaw ich style punktorów, wcięcia i tekst.
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
// Zapisanie prezentacji jako pliku PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Oczyść zasoby
Pozbądź się obiektu prezentacji, aby zwolnić zasoby.
```java
// Pozbądź się obiektu prezentacji
if (pres != null) {
    pres.dispose();
}
```

## Wniosek
Dodawanie punktorów akapitów w programie PowerPoint przy użyciu Aspose.Slides dla Java jest proste dzięki dostarczonym przykładom kodu. Dostosuj style i formatowanie punktorów, aby bezproblemowo dopasować je do potrzeb prezentacji.

## Często zadawane pytania
### Czy mogę dostosować kolory punktorów?
Tak, możesz ustawić niestandardowe kolory punktorów za pomocą interfejsu API Aspose.Slides.
### Jak dodać zagnieżdżone punktory?
Zagnieżdżanie punktorów polega na dodawaniu akapitów w akapitach i odpowiednim dostosowaniu wcięć.
### Czy mogę utworzyć różne style punktorów dla różnych slajdów?
Tak, możesz programowo zastosować unikalne style punktorów do różnych slajdów.
### Czy Aspose.Slides jest kompatybilny z Java 11?
Tak, Aspose.Slides obsługuje Java 11 i nowsze wersje.
### Gdzie mogę znaleźć więcej przykładów i dokumentacji?
 Odwiedzać[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) obszerne przewodniki i przykłady.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
