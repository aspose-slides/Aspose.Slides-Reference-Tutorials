---
"description": "Naucz się dodawać ramki do zdjęć z względną wysokością skali w Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać płynne prezentacje."
"linktitle": "Dodawanie ramek obrazów z względną wysokością skali w Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Samouczek dodawania ramek do zdjęć za pomocą Aspose.Slides .NET"
"url": "/pl/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Samouczek dodawania ramek do zdjęć za pomocą Aspose.Slides .NET

## Wstęp
Aspose.Slides for .NET to potężna biblioteka, która umożliwia deweloperom łatwe tworzenie, manipulowanie i konwertowanie prezentacji PowerPoint w aplikacjach .NET. W tym samouczku zagłębimy się w proces dodawania ramek obrazu z względną wysokością skali za pomocą Aspose.Slides for .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby udoskonalić swoje umiejętności tworzenia prezentacji.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- Podstawowa znajomość języka programowania C#.
- Zainstalowany program Visual Studio lub inne preferowane środowisko programistyczne C#.
- Biblioteka Aspose.Slides dla .NET została dodana do projektu.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do kodu C#. Ten krok zapewnia dostęp do klas i funkcjonalności udostępnianych przez bibliotekę Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Skonfiguruj swój projekt
Zacznij od utworzenia nowego projektu C# w preferowanym środowisku programistycznym. Upewnij się, że dodałeś bibliotekę Aspose.Slides for .NET do swojego projektu, odwołując się do niej.
## Krok 2: Załaduj prezentację i obraz
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Załaduj obraz, który ma zostać dodany do kolekcji obrazów prezentacji
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
W tym kroku tworzymy nowy obiekt prezentacji i ładujemy obraz, który chcemy dodać do prezentacji.
## Krok 3: Dodaj ramkę obrazu do slajdu
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Teraz dodaj ramkę obrazu do pierwszego slajdu prezentacji. Dostosuj parametry, takie jak typ kształtu, położenie i wymiary zgodnie ze swoimi wymaganiami.
## Krok 4: Ustaw względną szerokość i wysokość skali
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Ustaw względną wysokość i szerokość ramki obrazu, aby uzyskać pożądany efekt skalowania.
## Krok 5: Zapisz prezentację
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Na koniec zapisz prezentację z dodaną ramką obrazu w określonym formacie wyjściowym.
## Wniosek
Gratulacje! Udało Ci się nauczyć, jak dodawać ramki do zdjęć z względną wysokością skali za pomocą Aspose.Slides dla .NET. Eksperymentuj z różnymi obrazami, pozycjami i skalami, aby tworzyć atrakcyjne wizualnie prezentacje dostosowane do Twoich potrzeb.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Aspose.Slides obsługuje przede wszystkim języki .NET, ale możesz sprawdzić zgodność innych produktów Aspose z różnymi platformami.
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla .NET?
Odnieś się do [dokumentacja](https://reference.aspose.com/slides/net/) aby uzyskać kompleksowe informacje i przykłady.
### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides dla .NET?
Tak, możesz dostać [bezpłatny okres próbny](https://releases.aspose.com/) aby ocenić możliwości biblioteki.
### Jak mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla platformy .NET?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) aby zwrócić się o pomoc do społeczności i ekspertów Aspose.
### Gdzie mogę kupić Aspose.Slides dla platformy .NET?
Aspose.Slides dla .NET można kupić w sklepie [strona zakupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}