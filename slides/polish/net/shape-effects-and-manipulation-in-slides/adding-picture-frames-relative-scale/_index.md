---
title: Samouczek dodawania ramek do zdjęć za pomocą Aspose.Slides .NET
linktitle: Dodawanie ramek obrazów o względnej wysokości skali w Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodawać ramki obrazów ze względną wysokością skali w Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać płynne prezentacje.
weight: 17
url: /pl/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Aspose.Slides dla .NET to potężna biblioteka, która pozwala programistom na łatwe tworzenie, manipulowanie i konwertowanie prezentacji PowerPoint w aplikacjach .NET. W tym samouczku zagłębimy się w proces dodawania ramek obrazów o względnej wysokości w skali za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby udoskonalić swoje umiejętności budowania prezentacji.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawowa znajomość języka programowania C#.
- Zainstalowano Visual Studio lub inne preferowane środowisko programistyczne C#.
- Do Twojego projektu dodano bibliotekę Aspose.Slides for .NET.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do kodu C#. Ten krok zapewnia dostęp do zajęć i funkcjonalności udostępnianych przez bibliotekę Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Skonfiguruj swój projekt
Zacznij od utworzenia nowego projektu C# w preferowanym środowisku programistycznym. Pamiętaj, aby dodać bibliotekę Aspose.Slides for .NET do swojego projektu, odwołując się do niej.
## Krok 2: Załaduj prezentację i obraz
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Załaduj obraz, który ma zostać dodany do kolekcji obrazów prezentacji
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
Teraz dodaj ramkę obrazu do pierwszego slajdu prezentacji. Dostosuj parametry, takie jak typ kształtu, położenie i wymiary, zgodnie z własnymi wymaganiami.
## Krok 4: Ustaw względną szerokość i wysokość skali
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Ustaw względną wysokość i szerokość skali ramki obrazu, aby uzyskać pożądany efekt skalowania.
## Krok 5: Zapisz prezentację
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Na koniec zapisz prezentację z dodaną ramką obrazu w określonym formacie wyjściowym.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać ramki obrazów o względnej wysokości w skali przy użyciu Aspose.Slides dla .NET. Eksperymentuj z różnymi obrazami, pozycjami i skalami, aby stworzyć atrakcyjne wizualnie prezentacje dostosowane do Twoich potrzeb.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Aspose.Slides obsługuje przede wszystkim języki .NET, ale możesz eksplorować inne produkty Aspose pod kątem kompatybilności z różnymi platformami.
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla .NET?
 Patrz[dokumentacja](https://reference.aspose.com/slides/net/) w celu uzyskania wyczerpujących informacji i przykładów.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz dostać[bezpłatna wersja próbna](https://releases.aspose.com/) ocenić możliwości biblioteki.
### Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) aby zwrócić się o pomoc do społeczności i ekspertów Aspose.
### Gdzie mogę kupić Aspose.Slides dla .NET?
 Możesz kupić Aspose.Slides dla .NET w sklepie[strona zakupu](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
