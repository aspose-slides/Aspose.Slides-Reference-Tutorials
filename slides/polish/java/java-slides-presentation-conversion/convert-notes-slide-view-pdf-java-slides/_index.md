---
title: Konwertuj widok slajdów notatek na format PDF w slajdach Java
linktitle: Konwertuj widok slajdów notatek na format PDF w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak konwertować prezentacje programu PowerPoint z notatkami do plików PDF przy użyciu Aspose.Slides dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku z kodem źródłowym.
weight: 16
url: /pl/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj widok slajdów notatek na format PDF w slajdach Java


## Wprowadzenie do konwertowania widoku slajdu notatek do formatu PDF w slajdach Java

W tym samouczku przeprowadzimy Cię przez proces konwertowania prezentacji programu PowerPoint z widokiem slajdu z notatkami do pliku PDF przy użyciu biblioteki Aspose.Slides for Java. Ta biblioteka zapewnia zaawansowane funkcje do pracy z prezentacjami programu PowerPoint w języku Java.

## Warunki wstępne
1. Zainstalowany zestaw Java Development Kit (JDK).
2. Do Twojego projektu dodano bibliotekę Aspose.Slides for Java.

## Krok 1: Zaimportuj niezbędne klasy
Aby rozpocząć, musisz zaimportować niezbędne klasy z biblioteki Aspose.Slides. Oto kod, aby to zrobić:

```java
import com.aspose.slides.*;
```

## Krok 2: Załaduj prezentację programu PowerPoint
 Powinieneś mieć gotowy plik prezentacji PowerPoint. Zastępować`"Your Document Directory"` ze ścieżką do katalogu, w którym znajduje się plik prezentacji. Oto kod ładujący prezentację:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Krok 3: Skonfiguruj opcje PDF
Teraz skonfigurujmy opcje eksportu PDF. W szczególności ustawimy położenie notatek na „BottomFull”, aby uwzględnić notatki pod slajdami w pliku PDF. Oto kod:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Możesz dostosować inne opcje plików PDF zgodnie ze swoimi wymaganiami.

## Krok 4: Zapisz prezentację jako plik PDF z notatkami
 Na koniec zapiszmy prezentację jako plik PDF wraz z notatkami. Możesz określić nazwę pliku wyjściowego (np.`"Pdf_Notes_out.pdf"`) i wybierz format (`SaveFormat.Pdf`). Oto kod, aby to zrobić:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Krok 5: Oczyść zasoby
Nie zapomnij zwolnić zasobów po zakończeniu prezentacji:

```java
if (presentation != null) presentation.dispose();
```

## Kompletny kod źródłowy do konwersji widoku slajdów notatek do formatu PDF w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję obiektu Prezentacja reprezentującego plik prezentacji
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Zapisywanie prezentacji w notatkach PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku omówiliśmy, jak konwertować prezentacje programu PowerPoint z widokami slajdów z notatkami na pliki PDF przy użyciu biblioteki Aspose.Slides for Java. Aby osiągnąć tę konwersję, postępowaliśmy zgodnie z przewodnikiem krok po kroku z kodem źródłowym. Oto najważniejsze wnioski:

## Często zadawane pytania

### Jak zmienić położenie notatek w pliku PDF?

 Możesz zmienić położenie notatek w pliku PDF, modyfikując plik`setNotesPosition` argument metody. Można to ustawić na przykład`NotesPositions.RightFull` aby umieścić notatki po prawej stronie slajdów.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Czy mogę bardziej dostosować eksport do pliku PDF?

 Tak, możesz dostosować eksport do pliku PDF, dostosowując różne opcje w pliku`PdfOptions` obiekt. Możesz na przykład ustawić jakość, kompresję i inne parametry zgodnie ze swoimi potrzebami.

### Jak mogę uzyskać Aspose.Slides dla Java?

 Możesz pobrać Aspose.Slides dla Java ze strony internetowej pod adresem[Tutaj](https://releases.aspose.com/slides/java/).

### Czy są jakieś wymagania licencyjne dotyczące korzystania z Aspose.Slides?

Tak, Aspose.Slides wymaga ważnej licencji do użytku komercyjnego. Licencję można uzyskać ze strony internetowej Aspose.

### Gdzie mogę znaleźć więcej dokumentacji i przykładów?

 Obszerną dokumentację i przykłady Aspose.Slides for Java można znaleźć pod adresem[Tutaj](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
