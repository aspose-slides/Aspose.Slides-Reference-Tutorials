---
"description": "Dowiedz się, jak tworzyć wielopoziomowe punkty w programie PowerPoint za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu i często zadawanymi pytaniami."
"linktitle": "Tworzenie wielopoziomowych punktów w programie PowerPoint Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Tworzenie wielopoziomowych punktów w programie PowerPoint Java"
"url": "/pl/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie wielopoziomowych punktów w programie PowerPoint Java

## Wstęp
tym samouczku pokażemy, jak tworzyć wielopoziomowe punkty w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java. Dodawanie punktów wypunktowania jest powszechnym wymogiem tworzenia zorganizowanej i wizualnie atrakcyjnej treści w prezentacjach. Przejdziemy przez ten proces krok po kroku, zapewniając, że do końca tego przewodnika będziesz wyposażony w narzędzia do ulepszania swoich prezentacji za pomocą ustrukturyzowanych punktów wypunktowania na wielu poziomach.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące ustawienia:
- Środowisko programistyczne Java: upewnij się, że w systemie jest zainstalowany Java Development Kit (JDK).
- Biblioteka Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z [Tutaj](https://releases.aspose.com/slides/java/).
- IDE: Użyj preferowanego zintegrowanego środowiska programistycznego Java (IDE), takiego jak IntelliJ IDEA, Eclipse lub innego.
- Wiedza podstawowa: Znajomość programowania w języku Java i podstawowych koncepcji programu PowerPoint będzie pomocna.

## Importuj pakiety
Zanim przejdziemy do samouczka, zaimportujmy niezbędne pakiety z Aspose.Slides dla Java, z których będziemy korzystać w całym samouczku.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java w swoim IDE i dodaj Aspose.Slides for Java do zależności swojego projektu. Upewnij się, że niezbędny plik JAR Aspose.Slides jest uwzględniony w ścieżce kompilacji Twojego projektu.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
```
## Krok 2: Zainicjuj obiekt prezentacji
Zacznij od utworzenia nowej instancji prezentacji. Będzie ona służyć jako dokument PowerPoint, do którego będziesz dodawać slajdy i treści.
```java
Presentation pres = new Presentation();
```
## Krok 3: Dostęp do slajdu
Następnie przejdź do slajdu, do którego chcesz dodać wielopoziomowe punkty. W tym przykładzie będziemy pracować z pierwszym slajdem (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj Autokształt z Ramką Tekstową
Dodaj Autokształt do slajdu, w którym umieścisz tekst z punktami wielopoziomowymi.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Krok 5: Dostęp do ramki tekstowej
Przejdź do ramki tekstowej w autokształcie, w której chcesz dodać akapity z punktami wypunktowanymi.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); // Wyczyść domyślne akapity
```
## Krok 6: Dodaj akapity z punktami
Dodaj akapity z różnymi poziomami wypunktowań. Oto jak możesz dodać wielopoziomowe wypunktowania:
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
W tym samouczku omówiliśmy, jak tworzyć wielopoziomowe punkty w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Postępując zgodnie z tymi krokami, możesz skutecznie ustrukturyzować swoją treść za pomocą uporządkowanych punktów wypunktowania na różnych poziomach, zwiększając przejrzystość i atrakcyjność wizualną swoich prezentacji.
## Najczęściej zadawane pytania
### Czy mogę dodatkowo dostosować symbole punktorów?
Tak, możesz dostosować symbole punktorów, zmieniając znaki Unicode lub używając innych kształtów.
### Czy Aspose.Slides obsługuje inne typy punktów?
Tak, Aspose.Slides obsługuje wiele typów punktorów, w tym symbole, liczby i niestandardowe obrazy.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides generuje prezentacje zgodne z programem Microsoft PowerPoint 2007 i nowszymi wersjami.
### Czy mogę zautomatyzować generowanie slajdów za pomocą Aspose.Slides?
Tak, Aspose.Slides udostępnia interfejsy API umożliwiające automatyzację tworzenia, modyfikowania i modyfikowania prezentacji PowerPoint.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
Możesz uzyskać pomoc od społeczności i ekspertów Aspose.Slides pod adresem [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}