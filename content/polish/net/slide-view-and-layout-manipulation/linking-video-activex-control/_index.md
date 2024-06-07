---
title: Łączenie wideo za pomocą kontrolki ActiveX w programie PowerPoint
linktitle: Łączenie wideo za pomocą formantu ActiveX
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak łączyć filmy ze slajdami programu PowerPoint za pomocą Aspose.Slides dla .NET. Ten przewodnik krok po kroku zawiera kod źródłowy i wskazówki dotyczące tworzenia interaktywnych i wciągających prezentacji z połączonymi filmami.
type: docs
weight: 12
url: /pl/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
Łączenie wideo za pomocą kontrolki ActiveX w prezentacji przy użyciu Aspose.Slides dla .NET

W Aspose.Slides dla .NET możesz programowo połączyć wideo ze slajdem prezentacji za pomocą kontrolki ActiveX. Umożliwia to tworzenie interaktywnych prezentacji, w których zawartość wideo można odtwarzać bezpośrednio na slajdzie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces łączenia filmu ze slajdem prezentacji za pomocą Aspose.Slides dla .NET.

## Warunki wstępne:
- Visual Studio (lub dowolne inne środowisko programistyczne .NET)
-  Aspose.Slides dla biblioteki .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

## Krok 1: Utwórz nowy projekt
Utwórz nowy projekt w preferowanym środowisku programistycznym .NET (np. Visual Studio) i dodaj odniesienia do biblioteki Aspose.Slides for .NET.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw
swoim projekcie zaimportuj niezbędne przestrzenie nazw do pracy z Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Krok 3: Załaduj prezentację
Załaduj prezentację programu PowerPoint, do której chcesz dodać połączone wideo:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Twój kod umożliwiający dodanie połączonego filmu wideo zostanie umieszczony tutaj
}
```

## Krok 4: Dodaj formant ActiveX
 Utwórz instancję`IOleObjectFrame` interfejs umożliwiający dodanie kontrolki ActiveX do slajdu:

```csharp
ISlide slide = presentation.Slides[0]; // Wybierz slajd, do którego chcesz dodać wideo
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

W powyższym kodzie dodajemy do slajdu ramkę kontrolną ActiveX o wymiarach 640x480. Podajemy ProgID dla kontrolki ActiveX ShockwaveFlash, która jest powszechnie używana do osadzania filmów.

## Krok 5: Ustaw właściwości formantu ActiveX
Ustaw właściwości kontrolki ActiveX, aby określić połączone źródło wideo:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Zastąp rzeczywistą ścieżką pliku wideo
oleObjectFrame.AlternativeText = "Linked Video";
```

 Zastępować`"YourVideoPathHere"` z rzeczywistą ścieżką do pliku wideo. The`AlternativeText` Właściwość zawiera opis połączonego wideo.

## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Często zadawane pytania:

### Jak określić rozmiar i położenie połączonego wideo na slajdzie?
Możesz dostosować wymiary i położenie ramki kontrolnej ActiveX za pomocą parametrów pliku`AddOleObjectFrame` metoda. Cztery argumenty liczbowe reprezentują odpowiednio współrzędne X i Y lewego górnego rogu oraz szerokość i wysokość ramki.

### Czy przy użyciu tej metody mogę łączyć filmy w różnych formatach?
Tak, możesz łączyć filmy w różnych formatach, jeśli dla tego formatu dostępna jest odpowiednia kontrolka ActiveX. Na przykład formant ActiveX ShockwaveFlash użyty w tym przewodniku jest odpowiedni dla filmów Flash (SWF). W przypadku innych formatów może być konieczne użycie różnych identyfikatorów ProgID.

### Czy istnieje ograniczenie rozmiaru połączonego filmu wideo?
Rozmiar połączonego wideo może mieć wpływ na ogólny rozmiar i wydajność prezentacji. Zaleca się optymalizację plików wideo do odtwarzania w Internecie przed połączeniem ich z prezentacją.

### Wniosek:
Wykonując kroki opisane w tym przewodniku, możesz łatwo połączyć wideo za pomocą kontrolki ActiveX w prezentacji przy użyciu Aspose.Slides dla .NET. Ta funkcja umożliwia tworzenie wciągających i interaktywnych prezentacji płynnie zawierających treści multimedialne.

 Więcej szczegółów i opcji zaawansowanych można znaleźć na stronie[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).