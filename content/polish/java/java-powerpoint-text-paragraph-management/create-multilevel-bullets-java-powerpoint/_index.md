---
title: Twórz wielopoziomowe punktory w Java PowerPoint
linktitle: Twórz wielopoziomowe punktory w Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć wielopoziomowe punktory w programie PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu i często zadawanymi pytaniami.
type: docs
weight: 14
url: /pl/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---
## Wstęp
W tym samouczku omówimy, jak tworzyć wielopoziomowe punktory w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Dodawanie wypunktowań jest częstym wymogiem tworzenia zorganizowanej i atrakcyjnej wizualnie treści w prezentacjach. Przejdziemy przez ten proces krok po kroku, upewniając się, że pod koniec tego przewodnika będziesz w stanie wzbogacić swoje prezentacje o uporządkowane wypunktowania na wielu poziomach.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następującą konfigurację:
- Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK).
-  Biblioteka Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
- IDE: Użyj preferowanego zintegrowanego środowiska programistycznego Java (IDE), takiego jak IntelliJ IDEA, Eclipse lub inne.
- Podstawowa wiedza: Pomocna będzie znajomość programowania w języku Java i podstawowych koncepcji programu PowerPoint.

## Importuj pakiety
Zanim przejdziemy do samouczka, zaimportujmy niezbędne pakiety z Aspose.Slides dla Java, których będziemy używać w całym samouczku.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java w swoim IDE i dodaj Aspose.Slides for Java do zależności swojego projektu. Upewnij się, że niezbędny plik JAR Aspose.Slides znajduje się w ścieżce kompilacji projektu.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
```
## Krok 2: Zainicjuj obiekt prezentacji
Rozpocznij od utworzenia nowej instancji prezentacji. Będzie to służyć jako dokument programu PowerPoint, w którym będziesz dodawać slajdy i zawartość.
```java
Presentation pres = new Presentation();
```
## Krok 3: Uzyskaj dostęp do slajdu
Następnie przejdź do slajdu, do którego chcesz dodać wielopoziomowe punktory. W tym przykładzie będziemy pracować z pierwszym slajdem (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj Autokształt z ramką tekstową
Dodaj Autokształt do slajdu, w którym umieścisz tekst z wielopoziomowymi punktorami.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Krok 5: Uzyskaj dostęp do ramki tekstowej
Uzyskaj dostęp do ramki tekstowej w Autokształcie, w której będziesz dodawać akapity z punktorami.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Wyczyść domyślne akapity
```
## Krok 6: Dodaj akapity z punktorami
Dodaj akapity z różnymi poziomami punktorów. Oto jak dodać punktory wielopoziomowe:
```java
// Pierwszy poziom
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// Drugi poziom
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Trzeci poziom
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Czwarty poziom
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Krok 7: Zapisz prezentację
Na koniec zapisz prezentację jako plik PPTX w wybranym katalogu.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku omówiliśmy, jak tworzyć wielopoziomowe punktory w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Wykonując poniższe kroki, możesz skutecznie uporządkować treść za pomocą uporządkowanych wypunktowań na różnych poziomach, zwiększając przejrzystość i atrakcyjność wizualną prezentacji.
## Często zadawane pytania
### Czy mogę bardziej dostosować symbole punktorów?
Tak, możesz dostosować symbole punktorów, dostosowując znaki Unicode lub używając różnych kształtów.
### Czy Aspose.Slides obsługuje inne typy punktorów?
Tak, Aspose.Slides obsługuje różne typy punktorów, w tym symbole, liczby i niestandardowe obrazy.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides generuje prezentacje kompatybilne z Microsoft PowerPoint 2007 i nowszymi wersjami.
### Czy mogę zautomatyzować generowanie slajdów za pomocą Aspose.Slides?
Tak, Aspose.Slides udostępnia interfejsy API umożliwiające automatyzację tworzenia, modyfikowania i manipulowania prezentacjami programu PowerPoint.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać wsparcie od społeczności i ekspertów Aspose.Slides pod adresem[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).