---
"description": "Dowiedz się, jak ulepszyć prezentacje PowerPoint za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z przewodnikiem krok po kroku, aby dodać przesunięcie rozciągania w celu wypełnienia obrazu."
"linktitle": "Dodawanie przesunięcia rozciągania w celu wypełnienia obrazem na slajdach"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Dodawanie przesunięcia rozciągania w celu wypełnienia obrazem w prezentacjach programu PowerPoint"
"url": "/pl/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie przesunięcia rozciągania w celu wypełnienia obrazem w prezentacjach programu PowerPoint

## Wstęp
W dynamicznym świecie prezentacji wizualizacje odgrywają kluczową rolę w przyciąganiu uwagi odbiorców. Aspose.Slides for .NET umożliwia programistom udoskonalanie prezentacji PowerPoint poprzez zapewnienie solidnego zestawu funkcji. Jedną z takich funkcji jest możliwość dodania przesunięcia rozciągającego w celu wypełnienia obrazu, co pozwala na tworzenie kreatywnych i atrakcyjnych wizualnie slajdów.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
1. Biblioteka Aspose.Slides dla platformy .NET: Pobierz i zainstaluj bibliotekę z [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane, działające środowisko programistyczne .NET.
Przejdźmy teraz do przewodnika krok po kroku.
## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw, aby wykorzystać funkcjonalność Aspose.Slides w aplikacji .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt .NET w preferowanym środowisku programistycznym. Upewnij się, że Aspose.Slides dla .NET jest prawidłowo przywoływany.
## Krok 2: Zainicjuj klasę prezentacji
Utwórz instancję `Presentation` Klasa reprezentująca plik programu PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Twój kod wpisz tutaj
}
```
## Krok 3: Pobierz pierwszy slajd
Pobierz pierwszy slajd prezentacji, aby nad nim pracować.
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Utwórz instancję klasy ImageEx
Utwórz instancję `ImageEx` Klasa obsługująca obraz, który chcesz dodać do slajdu.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Krok 5: Dodaj ramkę do zdjęcia
Wykorzystaj `AddPictureFrame` metoda dodania ramki do slajdu. Określ wymiary i położenie ramki.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację na dysku.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
To wszystko! Udało Ci się dodać offset rozciągania dla wypełnienia obrazem w slajdach przy użyciu Aspose.Slides dla .NET.
## Wniosek
Ulepszanie prezentacji PowerPoint jest teraz łatwiejsze niż kiedykolwiek dzięki Aspose.Slides dla .NET. Dzięki temu samouczkowi nauczyłeś się, jak włączyć rozciąganie offsetowe do wypełniania obrazu, co wnosi nowy poziom kreatywności do slajdów.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides for .NET w moich aplikacjach internetowych?
Tak, Aspose.Slides dla .NET nadaje się zarówno do zastosowań desktopowych, jak i internetowych.
### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną z [Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla platformy .NET?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) o wsparcie społeczności.
### Gdzie mogę znaleźć pełną dokumentację Aspose.Slides dla .NET?
Odnieś się do [dokumentacja](https://reference.aspose.com/slides/net/) Aby uzyskać szczegółowe informacje.
### Czy mogę kupić Aspose.Slides dla platformy .NET?
Tak, możesz kupić produkt [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}