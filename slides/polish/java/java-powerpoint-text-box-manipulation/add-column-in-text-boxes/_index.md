---
title: Dodaj kolumnę w polach tekstowych za pomocą Aspose.Slides dla Java
linktitle: Dodaj kolumnę w polach tekstowych za pomocą Aspose.Slides dla Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać kolumny do pól tekstowych w programie PowerPoint przy użyciu Aspose.Slides dla Java. Ulepsz swoje prezentacje dzięki temu przewodnikowi krok po kroku.
weight: 10
url: /pl/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
tym samouczku przyjrzymy się, jak ulepszyć pola tekstowe, dodając kolumny za pomocą Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka Java, która umożliwia programistom programowe tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint bez konieczności korzystania z pakietu Microsoft Office. Dodanie kolumn do pól tekstowych może znacznie poprawić czytelność i organizację treści na slajdach, dzięki czemu Twoje prezentacje będą bardziej wciągające i profesjonalne.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- JDK (Java Development Kit) zainstalowany na twoim komputerze.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Aby rozpocząć, musisz zaimportować niezbędne klasy Aspose.Slides do pliku Java. Oto jak możesz to zrobić:
```java
import com.aspose.slides.*;
```
## Krok 1: Zainicjuj prezentację i slajd
Najpierw utwórz nową prezentację programu PowerPoint i zainicjuj pierwszy slajd.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Pobierz pierwszy slajd prezentacji
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 2: Dodaj autokształt (prostokąt)
Następnie dodaj do slajdu typ Autokształtu prostokąta.
```java
    // Dodaj typ Autokształtu prostokąta
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Krok 3: Dodaj ramkę tekstową do prostokąta
Teraz dodaj ramkę tekstową do autokształtu prostokąta i ustaw jej początkowy tekst.
```java
    // Dodaj ramkę tekstową do prostokąta
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Krok 4: Ustaw liczbę kolumn
Określ liczbę kolumn w ramce tekstowej.
```java
    // Pobierz format tekstowy TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Określ liczbę kolumn w ramce tekstowej
    format.setColumnCount(3);
```
## Krok 5: Dostosuj odstępy między kolumnami
Ustaw odstępy między kolumnami w ramce tekstowej.
```java
    // Określ odstępy między kolumnami
    format.setColumnSpacing(10);
```
## Krok 6: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację w pliku programu PowerPoint.
```java
    // Zapisz utworzoną prezentację
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Wniosek
Wykonując poniższe kroki, możesz łatwo dodawać kolumny do pól tekstowych w prezentacjach programu PowerPoint przy użyciu Aspose.Slides for Java. Ta funkcja pozwala poprawić strukturę i czytelność slajdów, czyniąc je bardziej atrakcyjnymi wizualnie i profesjonalnymi.
## Często zadawane pytania
### Czy mogę dodać więcej niż trzy kolumny do pola tekstowego?
Tak, możesz programowo określić dowolną liczbę kolumn za pomocą Aspose.Slides.
### Czy Aspose.Slides jest kompatybilny z Java 11?
Tak, Aspose.Slides obsługuje Java 11 i nowsze wersje.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy Aspose.Slides wymaga zainstalowanego pakietu Microsoft Office?
Nie, Aspose.Slides nie wymaga instalacji pakietu Microsoft Office na komputerze.
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
 Dostępna jest szczegółowa dokumentacja[Tutaj](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
