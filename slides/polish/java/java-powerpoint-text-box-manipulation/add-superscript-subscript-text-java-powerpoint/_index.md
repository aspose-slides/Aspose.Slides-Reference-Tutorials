---
"description": "Dowiedz się, jak dodawać tekst w indeksie górnym i dolnym w prezentacjach PowerPoint w Javie przy użyciu Aspose.Slides dla Javy. Idealne do ulepszania slajdów."
"linktitle": "Dodawanie tekstu indeksu górnego i dolnego w programie Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodawanie tekstu indeksu górnego i dolnego w programie Java PowerPoint"
"url": "/pl/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie tekstu indeksu górnego i dolnego w programie Java PowerPoint

## Wstęp
Tworzenie angażujących i pouczających prezentacji PowerPoint często wymaga użycia funkcji formatowania, takich jak tekst w indeksie górnym i dolnym. Ten samouczek przeprowadzi Cię przez proces włączania tekstu w indeksie górnym i dolnym do prezentacji PowerPoint w języku Java przy użyciu Aspose.Slides for Java.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse, przeznaczone do programowania w języku Java.
- Podstawowa znajomość programowania w Javie i prezentacji PowerPoint.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety z Aspose.Slides dla Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Skonfiguruj prezentację
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Dostęp do slajdu
```java
// Zobacz pierwszy slajd
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 3: Utwórz pole tekstowe
```java
// Utwórz Autokształt, który będzie służył jako pole tekstowe
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Krok 4: Dodaj tekst w indeksie górnym
```java
// Utwórz akapit dla tekstu głównego
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Utwórz część dla tekstu w indeksie górnym
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Ustaw wychwyt dla indeksu górnego
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Dodaj akapit główny z indeksem górnym do pola tekstowego
textFrame.getParagraphs().add(mainParagraph);
```
## Krok 5: Dodaj tekst w indeksie dolnym
```java
// Utwórz kolejny akapit dla tekstu w indeksie dolnym
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Utwórz część dla tekstu indeksu dolnego
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Ustaw wychwyt dla indeksu dolnego
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Dodaj akapit z indeksem dolnym do pola tekstowego
textFrame.getParagraphs().add(subscriptParagraph);
```
## Krok 6: Zapisz prezentację
```java
// Zapisz prezentację
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku przyjrzeliśmy się, jak ulepszyć prezentacje Java PowerPoint za pomocą tekstu w indeksie górnym i dolnym przy użyciu Aspose.Slides for Java. Postępując zgodnie z tymi krokami, możesz tworzyć bardziej atrakcyjne wizualnie i informacyjne slajdy, które skutecznie przekazują Twoją treść.

## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to rozbudowana biblioteka umożliwiająca programistom programistyczne tworzenie, edytowanie i konwertowanie prezentacji PowerPoint.
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
Szczegółową dokumentację można znaleźć [Tutaj](https://reference.aspose.com/slides/java/).
### W jaki sposób mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
Możesz uzyskać tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy mogę wypróbować Aspose.Slides for Java za darmo?
Tak, możesz pobrać bezpłatną wersję próbną ze strony [Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
Aby uzyskać wsparcie i wziąć udział w dyskusjach, odwiedź stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}