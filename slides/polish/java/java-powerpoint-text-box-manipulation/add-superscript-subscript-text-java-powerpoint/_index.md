---
title: Dodaj tekst indeksu górnego i dolnego w programie Java PowerPoint
linktitle: Dodaj tekst indeksu górnego i dolnego w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodać tekst indeksu górnego i dolnego w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Idealny do ulepszania slajdów.
weight: 13
url: /pl/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie angażujących i pouczających prezentacji programu PowerPoint często wymaga użycia funkcji formatowania, takich jak indeks górny i dolny. Ten samouczek poprowadzi Cię przez proces włączania indeksu górnego i dolnego do prezentacji Java PowerPoint przy użyciu Aspose.Slides for Java.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse, skonfigurowane do programowania w języku Java.
- Podstawowa znajomość programowania w języku Java i prezentacji PowerPoint.

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
## Krok 2: Uzyskaj dostęp do slajdu
```java
// Zdobądź pierwszy slajd
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 3: Utwórz pole tekstowe
```java
// Utwórz autokształt, który będzie służył jako pole tekstowe
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Krok 4: Dodaj tekst indeksu górnego
```java
// Utwórz akapit dla tekstu głównego
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Utwórz część tekstu indeksu górnego
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Ustaw wychwyt dla indeksu górnego
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Dodaj główny akapit z indeksem górnym do pola tekstowego
textFrame.getParagraphs().add(mainParagraph);
```
## Krok 5: Dodaj tekst indeksu dolnego
```java
// Utwórz kolejny akapit dla tekstu indeksu dolnego
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Utwórz część tekstu indeksu dolnego
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
W tym samouczku omówiliśmy, jak ulepszyć prezentacje Java PowerPoint za pomocą indeksu górnego i dolnego za pomocą Aspose.Slides dla Java. Wykonując poniższe kroki, możesz utworzyć bardziej atrakcyjne wizualnie i pouczające slajdy, które skutecznie przekazują treść.

## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides dla Java to solidna biblioteka, która umożliwia programistom programowe tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint.
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/slides/java/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy mogę bezpłatnie wypróbować Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Aby uzyskać wsparcie i dyskusje, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
