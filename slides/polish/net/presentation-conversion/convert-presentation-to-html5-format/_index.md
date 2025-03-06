---
title: Konwertuj prezentację do formatu HTML5
linktitle: Konwertuj prezentację do formatu HTML5
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak konwertować prezentacje programu PowerPoint do formatu HTML5 przy użyciu Aspose.Slides dla .NET. Łatwa i wydajna konwersja do udostępniania w Internecie.
weight: 22
url: /pl/net/presentation-conversion/convert-presentation-to-html5-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Konwertuj prezentację do formatu HTML5 za pomocą Aspose.Slides dla .NET

W tym przewodniku przeprowadzimy Cię przez proces konwersji prezentacji programu PowerPoint (PPT/PPTX) do formatu HTML5 przy użyciu biblioteki Aspose.Slides for .NET. Aspose.Slides to potężna biblioteka, która umożliwia manipulowanie i konwertowanie prezentacji programu PowerPoint w różnych formatach.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Visual Studio: Musisz zainstalować Visual Studio w swoim systemie.
2.  Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Slides dla .NET z[Tutaj](https://downloads.aspose.com/slides/net).

## Kroki konwersji

Wykonaj poniższe kroki, aby przekonwertować prezentację do formatu HTML5:

### Utwórz nowy projekt

Otwórz Visual Studio i utwórz nowy projekt.

### Dodaj odniesienie do Aspose.Slides

W swoim projekcie kliknij prawym przyciskiem myszy „Odniesienia” w Eksploratorze rozwiązań i wybierz „Dodaj odniesienie”. Przeglądaj i dodaj pobraną bibliotekę DLL Aspose.Slides.

### Napisz kod konwersji

W edytorze kodu napisz następujący kod, aby przekonwertować prezentację do formatu HTML5:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // Załaduj prezentację
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // Zdefiniuj opcje HTML5
                Html5Options options = new Html5Options();

                // Zapisz prezentację jako HTML5
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

 Zastępować`"input.pptx"` ze ścieżką do prezentacji wejściowej i`"output.html"` z żądaną ścieżką wyjściowego pliku HTML.

## Uruchom aplikację

Zbuduj i uruchom swoją aplikację. Konwertuje prezentację do formatu HTML5 i zapisuje ją jako plik HTML.

## Wniosek

Wykonując poniższe kroki, możesz łatwo przekonwertować prezentacje programu PowerPoint do formatu HTML5 przy użyciu biblioteki Aspose.Slides for .NET. Dzięki temu możesz udostępniać prezentacje w Internecie bez konieczności korzystania z oprogramowania PowerPoint.

## Często zadawane pytania

### Jak mogę dostosować wygląd wyniku HTML5?

 Możesz dostosować wygląd wyniku HTML5, ustawiając różne opcje w pliku`Html5Options`klasa. Patrz[dokumentacja](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) dla dostępnych opcji dostosowywania.

### Czy mogę konwertować prezentacje za pomocą animacji i przejść?

Tak, Aspose.Slides dla .NET obsługuje konwersję prezentacji z animacjami i przejściami do formatu HTML5.

### Czy dostępna jest wersja próbna Aspose.Slides?

 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Slides dla .NET z[strona pobierania](https://releases.aspose.com/slides/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
