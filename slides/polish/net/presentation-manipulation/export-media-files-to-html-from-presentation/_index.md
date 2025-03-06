---
title: Eksportuj pliki multimedialne do formatu HTML z prezentacji
linktitle: Eksportuj pliki multimedialne do formatu HTML z prezentacji
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Zoptymalizuj udostępnianie prezentacji za pomocą Aspose.Slides dla .NET! Z tego przewodnika krok po kroku dowiesz się, jak eksportować pliki multimedialne do formatu HTML z prezentacji.
weight: 15
url: /pl/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


W tym samouczku przeprowadzimy Cię przez proces eksportowania plików multimedialnych do formatu HTML z prezentacji przy użyciu Aspose.Slides dla .NET. Aspose.Slides to potężny interfejs API, który umożliwia programową pracę z prezentacjami programu PowerPoint. Po przeczytaniu tego przewodnika będziesz w stanie z łatwością konwertować swoje prezentacje do formatu HTML. Więc zacznijmy!

## 1. Wstęp

Prezentacje programu PowerPoint często zawierają elementy multimedialne, takie jak filmy, i może być konieczne wyeksportowanie tych prezentacji do formatu HTML w celu zapewnienia zgodności z Internetem. Aspose.Slides dla .NET zapewnia wygodny sposób programowego wykonania tego zadania.

## 2. Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Slides dla .NET: Powinieneś mieć zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

## 3. Ładowanie prezentacji

Aby rozpocząć, musisz załadować prezentację PowerPoint, którą chcesz przekonwertować do formatu HTML. Musisz także określić katalog wyjściowy, w którym zostanie zapisany plik HTML. Oto kod ładujący prezentację:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Ładowanie prezentacji
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Twój kod tutaj
}
```

## 4. Konfigurowanie opcji HTML

Teraz skonfigurujmy opcje HTML dla konwersji. Skonfigurujemy kontroler HTML, formater HTML i format obrazu slajdu. Ten kod zapewni, że Twój plik HTML będzie zawierał niezbędne komponenty do wyświetlania elementów multimedialnych.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Ustawianie opcji HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Zapisywanie pliku HTML

 Po skonfigurowaniu opcji HTML możesz teraz zapisać plik HTML. The`Save` metoda obiektu prezentacji wygeneruje plik HTML z osadzonymi elementami multimedialnymi.

```csharp
// Zapisywanie pliku
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Wniosek

Gratulacje! Pomyślnie wyeksportowałeś pliki multimedialne do formatu HTML z prezentacji programu PowerPoint przy użyciu Aspose.Slides dla .NET. Dzięki temu możesz z łatwością udostępniać swoje prezentacje online i mieć pewność, że elementy multimedialne będą prawidłowo wyświetlane.

## 7. Często zadawane pytania

### P1: Czy Aspose.Slides dla .NET jest bezpłatną biblioteką?
 O1: Aspose.Slides dla .NET to biblioteka komercyjna, ale możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/) żeby to wypróbować.

### P2: Czy mogę bardziej dostosować dane wyjściowe HTML?
Odpowiedź 2: Tak, możesz dostosować wyjście HTML, modyfikując opcje HTML w kodzie.

### P3: Czy Aspose.Slides dla .NET obsługuje inne formaty eksportu?
O3: Tak, Aspose.Slides dla .NET obsługuje różne formaty eksportu, w tym PDF, formaty obrazów i inne.

### P4: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?
 Odpowiedź 4: Możesz znaleźć wsparcie i zadawać pytania na forach Aspose[Tutaj](https://forum.aspose.com/).

### P5: Jak kupić licencję na Aspose.Slides dla .NET?
 Odpowiedź 5: Możesz kupić licencję od[ten link](https://purchase.aspose.com/buy).

Teraz, gdy ukończyłeś ten samouczek, masz umiejętności eksportowania plików multimedialnych do formatu HTML z prezentacji programu PowerPoint przy użyciu Aspose.Slides dla .NET. Ciesz się możliwością udostępniania bogatych w multimedia prezentacji online!
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
