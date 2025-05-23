---
"description": "Bezproblemowo konwertuj slajdy prezentacji z notatkami mówcy do formatu PDF za pomocą Aspose.Slides dla .NET. Bezproblemowo zachowaj zawartość i kontekst."
"linktitle": "Konwertuj slajdy do formatu PDF z notatkami"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Konwertuj slajdy do formatu PDF z notatkami"
"url": "/pl/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj slajdy do formatu PDF z notatkami


# Napisz przewodnik krok po kroku dotyczący konwersji slajdów do formatu PDF z notatkami przy użyciu Aspose.Slides dla platformy .NET

Szukasz niezawodnego sposobu na konwersję slajdów programu PowerPoint do formatu PDF, zachowując jednocześnie wszystkie ważne notatki? Nie szukaj dalej! W tym kompleksowym samouczku przeprowadzimy Cię przez proces korzystania z Aspose.Slides dla .NET, aby krok po kroku wykonać to zadanie.

## 1. Wprowadzenie

Konwersja slajdów programu PowerPoint do formatu PDF z notatkami może być cennym narzędziem do udostępniania prezentacji, zapewniając jednocześnie zachowanie ważnego kontekstu i komentarzy. Aspose.Slides for .NET zapewnia potężne rozwiązanie do tego zadania.

## 2. Konfigurowanie środowiska

Zanim przejdziemy do procesu kodowania, upewnij się, że masz skonfigurowane niezbędne środowisko. Będziesz potrzebować:

- Visual Studio lub preferowane środowisko programistyczne .NET.
- Zainstalowano bibliotekę Aspose.Slides dla .NET.
- Prezentacja programu PowerPoint zawierająca notatki, które chcesz przekonwertować.

## 3. Ładowanie prezentacji

kodzie C# musisz załadować prezentację PowerPoint, którą chcesz przekonwertować. Oto, jak możesz to zrobić:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Klonowanie slajdu

Aby mieć pewność, że Twój plik PDF zawiera wszystkie niezbędne slajdy z notatkami, możesz je sklonować z oryginalnej prezentacji. Oto jak to zrobić:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Dostosowywanie rozmiaru slajdu

Możesz chcieć dostosować rozmiar slajdu do swojego pliku PDF. Aspose.Slides dla .NET pozwala to zrobić z łatwością:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Konfigurowanie opcji PDF

Aby kontrolować sposób wyświetlania notatek w pliku PDF, możesz skonfigurować opcje PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Zapisywanie jako PDF z notatkami

Na koniec możesz zapisać swoją prezentację w formacie PDF z notatkami:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Wnioski

Gratulacje! Udało Ci się przekonwertować slajdy programu PowerPoint do formatu PDF, zachowując jednocześnie wszystkie ważne notatki. Aspose.Slides dla .NET sprawia, że ten proces jest prosty i wydajny.

## 9. Często zadawane pytania

### P1: Czy mogę dostosować układ notatek w pliku PDF?

Tak, możesz dostosować układ notatek za pomocą `INotesCommentsLayoutingOptions` w opcjach PDF.

### P2: Czy Aspose.Slides dla platformy .NET obsługuje inne formaty wyjściowe oprócz PDF?

Tak, Aspose.Slides dla platformy .NET obsługuje różne formaty wyjściowe, w tym PPTX, DOCX i inne.

### P3: Czy jest dostępna wersja próbna Aspose.Slides dla .NET?

Tak, możesz otrzymać bezpłatną wersję próbną Aspose.Slides dla .NET pod adresem [https://releases.aspose.com/](https://releases.aspose.com/).

### P4: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?

Wsparcie i dyskusje społecznościowe można znaleźć na stronie [https://forum.aspose.com/](https://forum.aspose.com/).

### P5: Czy mogę kupić tymczasową licencję na Aspose.Slides dla platformy .NET?

Tak, możesz zakupić licencję tymczasową na [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Podsumowując, używając Aspose.Slides dla .NET, możesz łatwo przekonwertować slajdy PowerPoint do formatu PDF z nienaruszonymi notatkami. To cenne narzędzie dla profesjonalistów, którzy muszą udostępniać prezentacje współpracownikom i klientom, jednocześnie dbając o to, aby ważny kontekst nie został utracony.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}