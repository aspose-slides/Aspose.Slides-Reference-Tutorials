---
title: Ustaw niestandardową liczbę punktorów w programie Java PowerPoint
linktitle: Ustaw niestandardową liczbę punktorów w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić niestandardowe numery punktorów w programie Java PowerPoint za pomocą Aspose.Slides, programowo zwiększając przejrzystość i strukturę prezentacji.
weight: 15
url: /pl/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W dzisiejszej erze cyfrowej tworzenie dynamicznych prezentacji ma kluczowe znaczenie dla skutecznego komunikowania pomysłów i danych. Aspose.Slides for Java zapewnia potężny zestaw narzędzi do programowego manipulowania prezentacjami programu PowerPoint, oferując rozbudowane funkcje usprawniające proces tworzenia prezentacji. W tym artykule opisano ustawianie niestandardowych numerów punktorów w prezentacjach Java PowerPoint przy użyciu Aspose.Slides. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, ten samouczek poprowadzi Cię krok po kroku przez proces, zapewniając efektywne wykorzystanie tej możliwości.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że w środowisku programistycznym skonfigurowano następujące wymagania wstępne:
- Zainstalowany zestaw Java Development Kit (JDK).
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/)
- Podstawowa znajomość języka programowania Java i koncepcji obiektowych

## Importuj pakiety
Najpierw zaimportuj niezbędne klasy Aspose.Slides i inne standardowe biblioteki Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Utwórz obiekt prezentacji
Rozpocznij od utworzenia nowej prezentacji programu PowerPoint przy użyciu Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Dodaj autokształt z tekstem
Wstaw autokształt (prostokąt) na slajdzie i uzyskaj dostęp do jego ramki tekstowej.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Krok 3: Usuń domyślny akapit
Usuń domyślny istniejący akapit z ramki tekstowej.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 4: Dodaj numerowane punktory
Dodaj akapity z niestandardowymi numerowanymi punktorami, zaczynając od określonych numerów.
```java
// Przykładowy akapit z punktorem zaczynającym się od 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Przykładowy akapit z punktorem zaczynającym się od 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Przykładowy akapit z punktorem zaczynającym się od 7
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
Podsumowując, Aspose.Slides dla Java upraszcza proces programowego ustawiania niestandardowych numerów punktorów w prezentacjach programu PowerPoint. Wykonując kroki opisane w tym samouczku, możesz skutecznie poprawić przejrzystość wizualną i strukturę swoich prezentacji.
## Często zadawane pytania
### Czy mogę bardziej dostosować wygląd pocisków?
Tak, Aspose.Slides oferuje szerokie opcje dostosowywania typu, rozmiaru, koloru i innych punktorów.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje formaty programu PowerPoint od wersji 97-2003 do najnowszych.
### Jak mogę uzyskać pomoc techniczną dla Aspose.Slides?
 Odwiedzać[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za pomoc techniczną.
### Czy mogę wypróbować Aspose.Slides przed zakupem?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę kupić Aspose.Slides?
 Możesz kupić Aspose.Slides od[Tutaj](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
