---
title: Ustaw wcięcie akapitu w programie Java PowerPoint
linktitle: Ustaw wcięcie akapitu w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak programowo ustawiać wcięcia akapitów na slajdach programu PowerPoint przy użyciu Aspose.Slides dla Java. Ulepsz formatowanie prezentacji bez wysiłku.
weight: 16
url: /pl/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw wcięcie akapitu w programie Java PowerPoint

## Wstęp
W tym samouczku dowiesz się, jak programowo manipulować prezentacjami programu PowerPoint przy użyciu Aspose.Slides dla Java. W szczególności skupimy się na ustawianiu wcięć akapitów na slajdach. Aspose.Slides for Java zapewnia potężny zestaw interfejsów API, które pozwalają programistom tworzyć, modyfikować, konwertować i zarządzać prezentacjami programu PowerPoint bez polegania na Microsoft Office Automation.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następującą konfigurację:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Pobrano bibliotekę Aspose.Slides dla Java. Można go uzyskać od[Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość języka programowania Java.
## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety, aby uzyskać dostęp do funkcjonalności Aspose.Slides:
```java
import com.aspose.slides.*;
import java.io.File;
```
Przyjrzyjmy się krok po kroku procesowi ustawiania wcięć akapitów na slajdzie programu PowerPoint przy użyciu programu Aspose.Slides dla języka Java.
## Krok 1: Utwórz obiekt prezentacji
 Utwórz instancję`Presentation` klasę, aby rozpocząć pracę z nową prezentacją programu PowerPoint.
```java
// Natychmiastowa klasa prezentacji
Presentation pres = new Presentation();
```
## Krok 2: Uzyskaj dostęp do slajdu
Pobierz pierwszy slajd z prezentacji. W razie potrzeby możesz manipulować różnymi slajdami według indeksu.
```java
// Zdobądź pierwszy slajd
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Dodaj kształt prostokąta
Dodaj do slajdu kształt prostokąta, który będzie zawierał tekst z wciętymi akapitami.
```java
// Dodaj kształt prostokąta
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## Krok 4: Dodaj tekst do prostokąta
Utwórz ramkę tekstową w kształcie prostokąta i ustaw zawartość tekstu.
```java
// Dodaj ramkę tekstową do prostokąta
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## Krok 5: Ustaw automatyczne dopasowanie tekstu
Ustaw automatyczne dopasowanie tekstu tak, aby mieścił się w granicach kształtu.
```java
// Ustaw tekst tak, aby pasował do kształtu
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## Krok 6: Dostosuj wcięcia akapitu
Uzyskaj dostęp do każdego akapitu w ramce tekstowej i ustaw jego wcięcie.
```java
// Pobierz pierwszy akapit w ramce tekstowej i ustaw jego wcięcie
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// Pobierz drugi akapit w ramce tekstowej i ustaw jego wcięcie
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
//Pobierz trzeci akapit w ramce tekstowej i ustaw jego wcięcie
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## Krok 7: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację na dysku.
```java
// Zapisz prezentację na dysku
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## Wniosek
Wykonując poniższe kroki, możesz łatwo ustawić wcięcia akapitu na slajdzie programu PowerPoint za pomocą Aspose.Slides for Java. Ta funkcja umożliwia programową precyzyjną kontrolę nad formatowaniem i prezentacją tekstu na slajdach.

## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężna biblioteka do programowej pracy z prezentacjami programu PowerPoint.
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/java/).
### Jak mogę pobrać Aspose.Slides dla Java?
 Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla Java?
 Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać wsparcie na forum społeczności[Tutaj](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
