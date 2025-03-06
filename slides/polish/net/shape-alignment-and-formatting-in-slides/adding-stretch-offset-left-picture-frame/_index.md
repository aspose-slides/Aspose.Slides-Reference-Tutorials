---
title: Dodawanie przesunięcia rozciągania do lewej w programie PowerPoint za pomocą Aspose.Slide
linktitle: Dodawanie przesunięcia rozciągania w lewo dla ramki obrazu w Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ulepszyć prezentacje programu PowerPoint za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby dodać przesunięcie rozciągania w lewo w przypadku ramek do zdjęć.
weight: 14
url: /pl/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Aspose.Slides dla .NET to potężna biblioteka, która umożliwia programistom łatwe manipulowanie prezentacjami programu PowerPoint. W tym samouczku omówimy proces dodawania przesunięcia rozciągania w lewo dla ramki obrazu przy użyciu Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby udoskonalić swoje umiejętności pracy z obrazami i kształtami w prezentacjach programu PowerPoint.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Jeśli nie, pobierz go z[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).
- Środowisko programistyczne: Posiadaj działające środowisko programistyczne z możliwościami .NET.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt lub otwórz istniejący. Upewnij się, że w projekcie znajduje się odwołanie do biblioteki Aspose.Slides.
## Krok 2: Utwórz obiekt prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca plik PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Twój kod kolejnych kroków trafi tutaj.
}
```
## Krok 3: Zdobądź pierwszy slajd
Pobierz pierwszy slajd z prezentacji:
```csharp
ISlide slide = pres.Slides[0];
```
## Krok 4: Utwórz instancję obrazu
Załaduj obraz, którego chcesz użyć:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Krok 5: Dodaj autokształt prostokąta
Utwórz autokształt typu prostokąta:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Krok 6: Ustaw typ wypełnienia i tryb wypełnienia obrazem
Skonfiguruj typ wypełnienia kształtu i tryb wypełnienia obrazkiem:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Krok 7: Ustaw obraz, aby wypełnił kształt
Określ obraz, który ma wypełnić kształt:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Krok 8: Określ przesunięcia rozciągania
Zdefiniuj przesunięcia obrazu od odpowiednich krawędzi obwiedni kształtu:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Krok 9: Zapisz prezentację
Zapisz plik PPTX na dysku:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Gratulacje! Pomyślnie dodałeś przesunięcie rozciągania w lewo dla ramki obrazu przy użyciu Aspose.Slides dla .NET.
## Wniosek
W tym samouczku omówiliśmy proces manipulowania ramkami obrazów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, uzyskałeś wgląd w pracę z obrazami, kształtami i przesunięciami.
## Często Zadawane Pytania
### P: Czy mogę zastosować przesunięcia rozciągania do innych kształtów oprócz prostokątów?
Odp.: Chociaż ten samouczek koncentruje się na prostokątach, przesunięcia rozciągania można zastosować do różnych kształtów obsługiwanych przez Aspose.Slides.
### P: Jak mogę dostosować przesunięcia rozciągania dla różnych efektów?
Odp.: Eksperymentuj z różnymi wartościami przesunięcia, aby uzyskać pożądany efekt wizualny. Dostosuj wartości tak, aby odpowiadały Twoim konkretnym wymaganiom.
### P: Czy Aspose.Slides jest kompatybilny z najnowszym frameworkiem .NET?
Odp.: Aspose.Slides jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami platformy .NET.
### P: Gdzie mogę znaleźć dodatkowe przykłady i zasoby dotyczące Aspose.Slides?
 O: Poznaj[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) w celu uzyskania wyczerpujących przykładów i wskazówek.
### P: Czy mogę zastosować wiele przesunięć rozciągania do jednego kształtu?
Odp.: Tak, możesz łączyć wiele przesunięć rozciągania, aby uzyskać złożone i dostosowane efekty wizualne.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
