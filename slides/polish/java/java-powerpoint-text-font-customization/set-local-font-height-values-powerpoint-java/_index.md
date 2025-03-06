---
title: Ustaw lokalne wartości wysokości czcionki w programie PowerPoint przy użyciu języka Java
linktitle: Ustaw lokalne wartości wysokości czcionki w programie PowerPoint przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dostosować wysokość czcionek w prezentacjach programu PowerPoint przy użyciu języka Java z Aspose.Slides. Bez wysiłku ulepszaj formatowanie tekstu na slajdach.
weight: 17
url: /pl/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw lokalne wartości wysokości czcionki w programie PowerPoint przy użyciu języka Java

## Wstęp
W tym samouczku dowiesz się, jak manipulować wysokościami czcionek na różnych poziomach w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java. Kontrolowanie rozmiarów czcionek ma kluczowe znaczenie dla tworzenia atrakcyjnych wizualnie i uporządkowanych prezentacji. Przeanalizujemy przykłady krok po kroku ilustrujące sposób ustawiania wysokości czcionek dla różnych elementów tekstowych.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
-  Aspose.Slides dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość programowania w języku Java i prezentacji PowerPoint
## Importuj pakiety
Pamiętaj o dołączeniu niezbędnych pakietów Aspose.Slides do pliku Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Zainicjuj obiekt prezentacji
Najpierw utwórz nowy obiekt prezentacji PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 2: Dodaj kształt i ramkę tekstową
Dodaj automatyczny kształt z ramką tekstową do pierwszego slajdu:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Krok 3: Utwórz fragmenty tekstowe
Zdefiniuj fragmenty tekstu o różnej wysokości czcionki:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Krok 4: Ustaw wysokość czcionek
Ustaw wysokość czcionek na różnych poziomach:
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
W tym samouczku pokazano, jak programowo dostosować wysokość czcionek na slajdach programu PowerPoint przy użyciu Aspose.Slides dla Java. Manipulując rozmiarami czcionek na różnych poziomach (w całej prezentacji, akapitach i fragmentach), możesz uzyskać precyzyjną kontrolę nad formatowaniem tekstu w swoich prezentacjach.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API do programowego manipulowania prezentacjami programu PowerPoint.
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/java/).
### Czy mogę wypróbować Aspose.Slides dla Java przed zakupem?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Aby uzyskać pomoc, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Gdzie mogę kupić licencję na Aspose.Slides dla Java?
 Możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
