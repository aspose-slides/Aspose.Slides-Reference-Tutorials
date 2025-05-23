---
"description": "Dowiedz się, jak ustawić niestandardowe numery punktów w programie Java PowerPoint za pomocą Aspose.Slides, zwiększając przejrzystość i strukturę prezentacji za pomocą programowania."
"linktitle": "Ustaw niestandardową liczbę punktów w programie Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw niestandardową liczbę punktów w programie Java PowerPoint"
"url": "/pl/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw niestandardową liczbę punktów w programie Java PowerPoint

## Wstęp
dzisiejszej erze cyfrowej tworzenie dynamicznych prezentacji jest kluczowe dla skutecznej komunikacji idei i danych. Aspose.Slides for Java zapewnia potężny zestaw narzędzi do programowego manipulowania prezentacjami PowerPoint, oferując rozbudowane funkcje usprawniające proces tworzenia prezentacji. Ten artykuł zagłębia się w ustawianie niestandardowych numerów wypunktowań w prezentacjach Java PowerPoint przy użyciu Aspose.Slides. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, ten samouczek przeprowadzi Cię krok po kroku przez proces, zapewniając, że będziesz mógł efektywnie wykorzystać tę możliwość.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że w Twoim środowisku programistycznym są spełnione następujące wymagania wstępne:
- Zainstalowano Java Development Kit (JDK)
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/)
- Podstawowa znajomość języka programowania Java i koncepcji obiektowych

## Importuj pakiety
Najpierw zaimportuj niezbędne klasy Aspose.Slides i inne standardowe biblioteki Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Utwórz obiekt prezentacji
Zacznij od utworzenia nowej prezentacji PowerPoint za pomocą Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Dodaj Autokształt z tekstem
Wstaw Autokształt (Prostokąt) na slajd i uzyskaj dostęp do jego ramki tekstowej.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Krok 3: Usuń domyślny akapit
Usuń domyślny istniejący akapit z ramki tekstowej.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 4: Dodaj ponumerowane punkty
Dodawaj akapity z niestandardowymi numerowanymi punktami, zaczynając od określonych liczb.
```java
// Przykładowy akapit z punktem rozpoczynającym się od 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Przykładowy akapit z punktem rozpoczynającym się od 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Przykładowy akapit z punktem rozpoczynającym się od 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Krok 5: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację w wybranej lokalizacji.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Wniosek
Podsumowując, Aspose.Slides for Java upraszcza proces ustawiania niestandardowych numerów wypunktowań w prezentacjach PowerPoint programowo. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz skutecznie poprawić przejrzystość wizualną i strukturę swoich prezentacji.
## Najczęściej zadawane pytania
### Czy mogę dodatkowo dostosować wygląd punktorów?
Tak, Aspose.Slides oferuje rozbudowane opcje dostosowywania typu, rozmiaru, koloru i innych elementów punktowania.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje formaty PowerPoint od wersji 97-2003 aż po najnowsze.
### Jak mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides?
Odwiedzać [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania pomocy technicznej.
### Czy mogę wypróbować Aspose.Slides przed zakupem?
Tak, możesz pobrać bezpłatną wersję próbną z [Tutaj](https://releases.aspose.com/).
### Gdzie mogę kupić Aspose.Slides?
Możesz zakupić Aspose.Slides od [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}