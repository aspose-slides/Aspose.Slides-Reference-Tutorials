---
title: Konwertuj slajdy do formatu PDF za pomocą notatek
linktitle: Konwertuj slajdy do formatu PDF za pomocą notatek
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Bez wysiłku konwertuj slajdy prezentacji z notatkami prelegenta do formatu PDF za pomocą Aspose.Slides dla .NET. Bezproblemowo zachowuj treść i kontekst.
weight: 18
url: /pl/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj slajdy do formatu PDF za pomocą notatek


# Napisz przewodnik krok po kroku dotyczący konwertowania slajdów do formatu PDF z notatkami przy użyciu Aspose.Slides dla .NET

Szukasz niezawodnego sposobu na konwersję slajdów programu PowerPoint do formatu PDF przy jednoczesnym zachowaniu wszystkich ważnych notatek? Nie szukaj dalej! W tym kompleksowym samouczku przeprowadzimy Cię krok po kroku przez proces korzystania z Aspose.Slides dla .NET, aby osiągnąć to zadanie.

## 1. Wstęp

Konwertowanie slajdów programu PowerPoint do formatu PDF z notatkami może być cennym narzędziem do udostępniania prezentacji, zapewniając jednocześnie zachowanie ważnego kontekstu i komentarzy. Aspose.Slides dla .NET zapewnia potężne rozwiązanie tego zadania.

## 2. Konfigurowanie środowiska

Zanim zagłębimy się w proces kodowania, upewnij się, że masz skonfigurowane niezbędne środowisko. Będziesz potrzebował:

- Visual Studio lub preferowane środowisko programistyczne .NET.
- Zainstalowana biblioteka Aspose.Slides dla .NET.
- Prezentacja programu PowerPoint z notatkami, które chcesz przekonwertować.

## 3. Ładowanie prezentacji

W kodzie C# musisz załadować prezentację programu PowerPoint, którą chcesz przekonwertować. Oto jak możesz to zrobić:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Klonowanie slajdu

Aby mieć pewność, że plik PDF będzie zawierał wszystkie niezbędne slajdy z notatkami, możesz sklonować je z oryginalnej prezentacji. Oto jak:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Dostosowywanie rozmiaru slajdu

Możesz dostosować rozmiar slajdu, aby dopasować go do pliku PDF. Aspose.Slides dla .NET pozwala to zrobić z łatwością:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Konfigurowanie opcji PDF

Aby kontrolować sposób wyświetlania notatek w pliku PDF, możesz skonfigurować opcje pliku PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Zapisywanie w formacie PDF z notatkami

Na koniec możesz zapisać swoją prezentację w formacie PDF z notatkami:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Wniosek

Gratulacje! Pomyślnie przekonwertowałeś slajdy programu PowerPoint do formatu PDF, zachowując wszystkie ważne notatki. Aspose.Slides dla .NET sprawia, że proces ten jest prosty i wydajny.

## 9. Często zadawane pytania

### P1: Czy mogę dostosować układ notatek w pliku PDF?

 Tak, możesz dostosować układ notatek za pomocą`INotesCommentsLayoutingOptions` w opcjach PDF.

### P2: Czy Aspose.Slides dla .NET obsługuje inne formaty wyjściowe oprócz PDF?

Tak, Aspose.Slides dla .NET obsługuje różne formaty wyjściowe, w tym PPTX, DOCX i inne.

### P3: Czy dostępna jest wersja próbna Aspose.Slides dla .NET?

 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Slides dla .NET pod adresem[https://releases.aspose.com/](https://releases.aspose.com/).

### P4: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?

 Wsparcie i dyskusje w społeczności można znaleźć pod adresem[https://forum.aspose.com/](https://forum.aspose.com/).

### P5: Czy mogę kupić tymczasową licencję na Aspose.Slides dla .NET?

 Tak, możesz kupić tymczasową licencję na stronie[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Podsumowując, używając Aspose.Slides dla .NET, możesz łatwo konwertować slajdy programu PowerPoint do formatu PDF z nienaruszonymi notatkami. Jest to cenne narzędzie dla profesjonalistów, którzy muszą udostępniać prezentacje współpracownikom i klientom, jednocześnie dbając o to, aby nie utracić ważnego kontekstu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
