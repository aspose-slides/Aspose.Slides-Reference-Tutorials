---
"description": "Naucz się formatować kształty prostokątne w prezentacjach PowerPoint za pomocą Aspose.Slides dla .NET. Ulepsz swoje slajdy za pomocą dynamicznych elementów wizualnych."
"linktitle": "Formatowanie kształtu prostokąta w slajdach prezentacji za pomocą Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Ulepsz prezentacje — formatuj kształty prostokątne za pomocą Aspose.Slides"
"url": "/pl/net/shape-geometry-and-positioning-in-slides/formatting-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ulepsz prezentacje — formatuj kształty prostokątne za pomocą Aspose.Slides

## Wstęp
Aspose.Slides for .NET to potężna biblioteka, która ułatwia pracę z prezentacjami PowerPoint w środowisku .NET. Jeśli chcesz ulepszyć swoje prezentacje, dynamicznie formatując kształty prostokątne, ten samouczek jest dla Ciebie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces formatowania kształtu prostokątnego w prezentacji przy użyciu Aspose.Slides for .NET.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Środowisko programistyczne z zainstalowanym Aspose.Slides dla .NET.
- Podstawowa znajomość języka programowania C#.
- Znajomość tworzenia i edytowania prezentacji PowerPoint.
Zacznijmy więc samouczek!
## Importuj przestrzenie nazw
W kodzie C# musisz zaimportować niezbędne przestrzenie nazw, aby używać funkcjonalności Aspose.Slides. Dodaj następujące przestrzenie nazw na początku kodu:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
```
## Krok 1: Skonfiguruj katalog dokumentów
Zacznij od ustawienia katalogu, w którym chcesz zapisać plik prezentacji PowerPoint. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką do Twojego katalogu.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Krok 2: Utwórz obiekt prezentacji
Utwórz instancję `Presentation` klasa do reprezentowania pliku PPTX. Będzie to podstawa twojej prezentacji PowerPoint.
```csharp
using (Presentation pres = new Presentation())
{
    // Twój kod wpisz tutaj
}
```
## Krok 3: Pobierz pierwszy slajd
Przejdź do pierwszego slajdu prezentacji. To właśnie na tym slajdzie dodasz i sformatujesz kształt prostokąta.
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Dodaj kształt prostokąta
Użyj `Shapes` właściwość slajdu, aby dodać automatyczny kształt typu prostokąt. Określ pozycję i wymiary prostokąta.
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
## Krok 5: Zastosuj formatowanie do kształtu prostokąta
Teraz zastosujmy formatowanie do kształtu prostokąta. Ustaw kolor wypełnienia, kolor linii i szerokość kształtu, aby dostosować jego wygląd.
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację na dysku za pomocą `Save` metodę, określając format pliku jako PPTX.
```csharp
pres.Save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Gratulacje! Udało Ci się sformatować kształt prostokąta w prezentacji przy użyciu Aspose.Slides dla .NET.
## Wniosek
W tym samouczku omówiliśmy podstawy pracy z kształtami prostokątnymi w Aspose.Slides dla .NET. Dowiedziałeś się, jak skonfigurować projekt, utworzyć prezentację, dodać kształt prostokątny i zastosować formatowanie, aby poprawić jego atrakcyjność wizualną. W miarę jak będziesz poznawać Aspose.Slides, odkryjesz jeszcze więcej sposobów na podniesienie poziomu prezentacji PowerPoint.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Slides dla .NET z innymi językami .NET?
Tak, Aspose.Slides obsługuje oprócz języka C# również inne języki .NET, takie jak VB.NET i F#.
### P2: Gdzie mogę znaleźć dokumentację Aspose.Slides?
Możesz zapoznać się z dokumentacją [Tutaj](https://reference.aspose.com/slides/net/).
### P3: W jaki sposób mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides?
Aby uzyskać wsparcie i wziąć udział w dyskusjach, odwiedź stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### P4: Czy jest dostępna bezpłatna wersja próbna?
Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej [Tutaj](https://releases.aspose.com/).
### P5: Gdzie mogę kupić Aspose.Slides dla platformy .NET?
Możesz kupić Aspose.Slides dla .NET [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}