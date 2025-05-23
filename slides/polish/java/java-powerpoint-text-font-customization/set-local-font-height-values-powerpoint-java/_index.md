---
"description": "Dowiedz się, jak dostosować wysokość czcionki w prezentacjach PowerPoint za pomocą Javy z Aspose.Slides. Ulepsz formatowanie tekstu na slajdach bez wysiłku."
"linktitle": "Ustawianie lokalnych wartości wysokości czcionki w programie PowerPoint za pomocą języka Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustawianie lokalnych wartości wysokości czcionki w programie PowerPoint za pomocą języka Java"
"url": "/pl/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie lokalnych wartości wysokości czcionki w programie PowerPoint za pomocą języka Java

## Wstęp
W tym samouczku dowiesz się, jak manipulować wysokościami czcionek na różnych poziomach w prezentacjach PowerPoint za pomocą Aspose.Slides for Java. Kontrola rozmiarów czcionek jest kluczowa dla tworzenia atrakcyjnych wizualnie i uporządkowanych prezentacji. Przejdziemy przez przykłady krok po kroku, aby zilustrować, jak ustawić wysokość czcionek dla różnych elementów tekstowych.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
- Zestaw Java Development Kit (JDK) zainstalowany w Twoim systemie
- Biblioteka Aspose.Slides dla Java. Możesz ją pobrać [Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość programowania w języku Java i prezentacji PowerPoint
## Importuj pakiety
Pamiętaj o dołączeniu niezbędnych pakietów Aspose.Slides do pliku Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Zainicjuj obiekt prezentacji
Najpierw utwórz nowy obiekt prezentacji programu PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 2: Dodaj kształt i ramkę tekstową
Dodaj do pierwszego slajdu automatyczny kształt z ramką tekstową:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Krok 3: Utwórz części tekstowe
Zdefiniuj fragmenty tekstu o różnej wysokości czcionki:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Krok 4: Ustaw wysokość czcionki
Ustaw wysokość czcionki na różnych poziomach:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację do pliku:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Wniosek
Ten samouczek pokazał, jak programowo dostosować wysokość czcionki w slajdach programu PowerPoint przy użyciu Aspose.Slides for Java. Manipulując rozmiarami czcionki na różnych poziomach (w całej prezentacji, akapicie i części), możesz uzyskać precyzyjną kontrolę nad formatowaniem tekstu w swoich prezentacjach.
## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to zaawansowany interfejs API umożliwiający programowe modyfikowanie prezentacji PowerPoint.
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
Dokumentację można znaleźć [Tutaj](https://reference.aspose.com/slides/java/).
### Czy mogę wypróbować Aspose.Slides dla Java przed zakupem?
Tak, możesz otrzymać bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla Java?
Aby uzyskać pomoc, odwiedź stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Gdzie mogę nabyć licencję na Aspose.Slides dla Java?
Możesz kupić licencję [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}