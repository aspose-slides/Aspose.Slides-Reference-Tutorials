---
title: Dodawanie przesunięcia rozciągania dla wypełnienia obrazem w prezentacjach programu PowerPoint
linktitle: Dodawanie przesunięcia rozciągania dla wypełnienia obrazem na slajdach
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ulepszyć prezentacje programu PowerPoint za pomocą Aspose.Slides dla .NET. Postępuj zgodnie ze szczegółowym przewodnikiem, aby dodać przesunięcie rozciągania dla wypełnienia obrazem.
weight: 18
url: /pl/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W dynamicznym świecie prezentacji elementy wizualne odgrywają kluczową rolę w przyciąganiu uwagi publiczności. Aspose.Slides dla .NET umożliwia programistom ulepszanie prezentacji programu PowerPoint poprzez zapewnienie solidnego zestawu funkcji. Jedną z takich funkcji jest możliwość dodania przesunięcia rozciągania do wypełnienia obrazem, co pozwala na tworzenie kreatywnych i atrakcyjnych wizualnie slajdów.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Biblioteka Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę z[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane działające środowisko programistyczne .NET.
Zacznijmy teraz od przewodnika krok po kroku.
## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw, aby wykorzystać funkcjonalność Aspose.Slides w aplikacji .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt .NET w preferowanym środowisku programistycznym. Upewnij się, że Aspose.Slides for .NET ma odpowiednie odniesienia.
## Krok 2: Zainicjuj klasę prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca plik programu PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Twój kod trafia tutaj
}
```
## Krok 3: Zdobądź pierwszy slajd
Pobierz pierwszy slajd z prezentacji, z którym będziesz mógł pracować.
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Utwórz instancję klasy ImageEx
 Utwórz instancję`ImageEx`klasę do obsługi obrazu, który chcesz dodać do slajdu.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Krok 5: Dodaj ramkę na zdjęcie
 Skorzystaj z`AddPictureFrame` metoda dodawania ramki obrazu do slajdu. Określ wymiary i położenie ramy.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację na dysku.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Otóż to! Pomyślnie dodałeś przesunięcie rozciągania dla wypełnienia obrazem na slajdach przy użyciu Aspose.Slides dla .NET.
## Wniosek
Udoskonalanie prezentacji programu PowerPoint jest teraz łatwiejsze niż kiedykolwiek dzięki Aspose.Slides dla .NET. Wykonując ten samouczek, nauczyłeś się, jak włączyć przesunięcie rozciągania do wypełnienia obrazem, co wniesie nowy poziom kreatywności do Twoich slajdów.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides for .NET w moich aplikacjach internetowych?
Tak, Aspose.Slides dla .NET jest odpowiedni zarówno dla aplikacji stacjonarnych, jak i internetowych.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności.
### Gdzie mogę znaleźć pełną dokumentację Aspose.Slides dla .NET?
 Patrz[dokumentacja](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje.
### Czy mogę kupić Aspose.Slides dla .NET?
 Tak, możesz kupić produkt[Tutaj](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
