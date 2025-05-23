---
"description": "Dowiedz się, jak łączyć filmy ze slajdami programu PowerPoint za pomocą Aspose.Slides dla .NET. Ten przewodnik krok po kroku zawiera kod źródłowy i wskazówki dotyczące tworzenia interaktywnych i angażujących prezentacji z połączonymi filmami."
"linktitle": "Łączenie wideo za pomocą kontrolki ActiveX"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Łączenie wideo za pomocą kontrolki ActiveX w programie PowerPoint"
"url": "/pl/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Łączenie wideo za pomocą kontrolki ActiveX w programie PowerPoint

Łączenie wideo za pomocą kontrolki ActiveX w prezentacji przy użyciu Aspose.Slides dla .NET

Aspose.Slides dla .NET możesz programowo połączyć wideo ze slajdem prezentacji za pomocą kontrolki ActiveX. Pozwala to na tworzenie interaktywnych prezentacji, w których zawartość wideo może być odtwarzana bezpośrednio w slajdzie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces łączenia wideo ze slajdem prezentacji za pomocą Aspose.Slides dla .NET.

## Wymagania wstępne:
- Visual Studio (lub dowolne inne środowisko programistyczne .NET)
- Biblioteka Aspose.Slides dla .NET. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).

## Krok 1: Utwórz nowy projekt
Utwórz nowy projekt w preferowanym środowisku programistycznym .NET (np. Visual Studio) i dodaj odwołania do biblioteki Aspose.Slides for .NET.

## Krok 2: Importuj niezbędne przestrzenie nazw
W swoim projekcie zaimportuj niezbędne przestrzenie nazw do pracy z Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Krok 3: Załaduj prezentację
Załaduj prezentację programu PowerPoint, do której chcesz dodać połączony film:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Twój kod do dodania powiązanego filmu wideo będzie tutaj
}
```

## Krok 4: Dodaj kontrolkę ActiveX
Utwórz instancję `IOleObjectFrame` interfejs umożliwiający dodanie kontrolki ActiveX do slajdu:

```csharp
ISlide slide = presentation.Slides[0]; // Wybierz slajd, do którego chcesz dodać wideo
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

W powyższym kodzie dodajemy ramkę kontrolki ActiveX o wymiarach 640x480 do slajdu. Określamy ProgID dla kontrolki ShockwaveFlash ActiveX, która jest powszechnie używana do osadzania filmów.

## Krok 5: Ustaw właściwości kontrolki ActiveX
Ustaw właściwości kontrolki ActiveX, aby określić połączone źródło wideo:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Zastąp rzeczywistą ścieżką do pliku wideo
oleObjectFrame.AlternativeText = "Linked Video";
```

Zastępować `"YourVideoPathHere"` z rzeczywistą ścieżką do pliku wideo. `AlternativeText` Właściwość zawiera opis powiązanego filmu.

## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Najczęściej zadawane pytania:

### Jak mogę określić rozmiar i pozycję połączonego filmu na slajdzie?
Wymiary i położenie ramki kontrolnej ActiveX można dostosować za pomocą parametrów `AddOleObjectFrame` metoda. Cztery argumenty numeryczne reprezentują odpowiednio współrzędne X i Y lewego górnego rogu oraz szerokość i wysokość ramki.

### Czy mogę linkować filmy w różnych formatach, stosując to podejście?
Tak, możesz łączyć filmy w różnych formatach, o ile odpowiednia kontrolka ActiveX jest dostępna dla tego formatu. Na przykład kontrolka ActiveX ShockwaveFlash używana w tym przewodniku nadaje się do filmów Flash (SWF). W przypadku innych formatów może być konieczne użycie innych ProgID.

### Czy istnieje ograniczenie rozmiaru linkowanego filmu?
Rozmiar połączonego filmu może mieć wpływ na ogólny rozmiar i wydajność prezentacji. Zaleca się optymalizację filmów do odtwarzania w sieci przed połączeniem ich z prezentacją.

### Wniosek:
Postępując zgodnie z krokami opisanymi w tym przewodniku, możesz łatwo połączyć wideo za pomocą kontrolki ActiveX w prezentacji przy użyciu Aspose.Slides dla .NET. Ta funkcja umożliwia tworzenie angażujących i interaktywnych prezentacji, które płynnie włączają treści multimedialne.

Więcej szczegółów i opcji zaawansowanych można znaleźć w [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}